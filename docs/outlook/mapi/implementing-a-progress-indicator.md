---
title: 实现进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3a062a88-e87e-4c0c-944e-544a8f080930
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 767b8723d9a544a31ee5c4bbc1d6186a15387b44
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775784"
---
# <a name="implementing-a-progress-indicator"></a><span data-ttu-id="a5731-103">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="a5731-103">Implementing a Progress Indicator</span></span>

  
  
<span data-ttu-id="a5731-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a5731-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a5731-105">由客户端启动的操作的许多需要很长的时间。</span><span class="sxs-lookup"><span data-stu-id="a5731-105">Many of the operations initiated by clients take a significant amount of time.</span></span> <span data-ttu-id="a5731-106">这些可能冗长的操作的输入参数之一是指向进度对象的指针 — 实现的对象[IMAPIProgress: IUnknown](imapiprogressiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a5731-106">One of the input parameters to these potentially lengthy operations is a pointer to a progress object — an object that implements the [IMAPIProgress : IUnknown](imapiprogressiunknown.md) interface.</span></span> <span data-ttu-id="a5731-107">进度对象控制的外观和显示进度指示器，客户端和 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="a5731-107">Progress objects control the appearance and display of progress indicators and are implemented by clients and by MAPI.</span></span> <span data-ttu-id="a5731-108">您可以选择要实现进度对象。</span><span class="sxs-lookup"><span data-stu-id="a5731-108">You can choose whether or not to implement a progress object.</span></span> <span data-ttu-id="a5731-109">MAPI 实现了可供服务提供商使用如果您选择不提供的实现。</span><span class="sxs-lookup"><span data-stu-id="a5731-109">The MAPI implementation is available for service providers to use if you elect not to supply an implementation.</span></span> 
  
<span data-ttu-id="a5731-110">进度对象使用数据的以下部分：</span><span class="sxs-lookup"><span data-stu-id="a5731-110">Progress objects work with the following pieces of data:</span></span>
  
- <span data-ttu-id="a5731-111">一个全局最小值，当调用[IMAPIProgress::Progress](imapiprogress-progress.md)方法时，应小于或等于_ulValue_参数的值。</span><span class="sxs-lookup"><span data-stu-id="a5731-111">A global minimum value which, when your [IMAPIProgress::Progress](imapiprogress-progress.md) method is called, should be less than or equal to the value of the  _ulValue_ parameter.</span></span> <span data-ttu-id="a5731-112">在操作的开头， _ulValue_将等于此最小值。</span><span class="sxs-lookup"><span data-stu-id="a5731-112">At the beginning of the operation,  _ulValue_ will be equal to this minimum value.</span></span> 
    
- <span data-ttu-id="a5731-113">一个全局最大值，当调用**IMAPIProgress::Progress**方法时，应大于或等于_ulValue_参数。</span><span class="sxs-lookup"><span data-stu-id="a5731-113">A global maximum value which, when your **IMAPIProgress::Progress** method is called, should be greater than or equal to the  _ulValue_ parameter.</span></span> <span data-ttu-id="a5731-114">在操作末尾， _ulValue_将等于此最大值。</span><span class="sxs-lookup"><span data-stu-id="a5731-114">At the end of the operation,  _ulValue_ will be equal to this maximum value.</span></span> 
    
- <span data-ttu-id="a5731-115">标志值表示进度是否对应于顶部或项目级别较低。</span><span class="sxs-lookup"><span data-stu-id="a5731-115">A flags value which indicates whether the progress corresponds to a top or lower level item.</span></span>
    
- <span data-ttu-id="a5731-116">一个值，指示操作的进度的当前级别。</span><span class="sxs-lookup"><span data-stu-id="a5731-116">A value that indicates the current level of progress for the operation.</span></span>
    
- <span data-ttu-id="a5731-117">相对于总当前处理的项目数。</span><span class="sxs-lookup"><span data-stu-id="a5731-117">The number of the currently processed items relative to the total.</span></span>
    
- <span data-ttu-id="a5731-118">在操作过程中处理的项目总数。</span><span class="sxs-lookup"><span data-stu-id="a5731-118">The total number of items to be processed during the operation.</span></span>
    
<span data-ttu-id="a5731-119">最小和最大值表示的开头和结尾数值窗体中的操作。</span><span class="sxs-lookup"><span data-stu-id="a5731-119">The minimum and maximum values represent the beginning and end of the operation in numeric form.</span></span> <span data-ttu-id="a5731-120">用于初始的最小值和初始的最大值，这些值传递给服务提供商的[IMAPIProgress::GetMin](imapiprogress-getmin.md)和[IMAPIProgress::GetMax](imapiprogress-getmax.md)方法 1000年 1。</span><span class="sxs-lookup"><span data-stu-id="a5731-120">Use 1 for the initial minimum value and 1000 for the initial maximum value, passing these values to service providers in the [IMAPIProgress::GetMin](imapiprogress-getmin.md) and [IMAPIProgress::GetMax](imapiprogress-getmax.md) methods.</span></span> <span data-ttu-id="a5731-121">呼叫[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)时，服务提供商重置这些值。</span><span class="sxs-lookup"><span data-stu-id="a5731-121">Service providers reset these values when they call [IMAPIProgress::SetLimits](imapiprogress-setlimits.md).</span></span> 
  
<span data-ttu-id="a5731-122">服务提供商使用的标志值来确定其应该如何设置其他值。</span><span class="sxs-lookup"><span data-stu-id="a5731-122">The flags value is used by service providers to determine how they should set the other values.</span></span> <span data-ttu-id="a5731-123">初始化 MAPI_TOP_LEVEL 的标志值，并返回此值中的**GetFlags**实现，直到服务提供商将其重置通过调用**SetLimits**。</span><span class="sxs-lookup"><span data-stu-id="a5731-123">Initialize the flags value to MAPI_TOP_LEVEL and return this value in your implementation of **GetFlags** until the service provider resets it by calling **SetLimits**.</span></span> 
  
<span data-ttu-id="a5731-124">**SetLimits**方法的实现中, 保存的每个参数的本地副本： _lpulMin_、 _lpulMax_和_lpulFlags_。</span><span class="sxs-lookup"><span data-stu-id="a5731-124">In your implementation of the **SetLimits** method, save local copies of each of the parameters:  _lpulMin_,  _lpulMax_, and  _lpulFlags_.</span></span> <span data-ttu-id="a5731-125">服务提供商呼叫**GetMin**、 **GetMax**或**GetFlags**方法时，这些值应为随时可用。</span><span class="sxs-lookup"><span data-stu-id="a5731-125">These values should be readily available when a service provider calls your **GetMin**, **GetMax**, or **GetFlags** methods.</span></span> 
  
<span data-ttu-id="a5731-126">若要更新进度指示器显示，服务提供商，请调用**IMAPIProgress::Progress**方法。</span><span class="sxs-lookup"><span data-stu-id="a5731-126">To update the display of the progress indicator, service providers call your **IMAPIProgress::Progress** method.</span></span> <span data-ttu-id="a5731-127">有此方法的三个参数： 一个值，计数，并且总。</span><span class="sxs-lookup"><span data-stu-id="a5731-127">There are three parameters to this method: a value, a count, and a total.</span></span> <span data-ttu-id="a5731-128">第一个参数， _ulValue_，用于显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="a5731-128">Use the first parameter,  _ulValue_, to display the progress indicator.</span></span> <span data-ttu-id="a5731-129">_UlValue_参数进度指示器并且将等于在一开始操作的仅全局_ulMin_和等于全局_ulMax_仅在完成该操作。</span><span class="sxs-lookup"><span data-stu-id="a5731-129">The  _ulValue_ parameter is the progress indicator and will be equal to global  _ulMin_ only at the very beginning of the operation and equal to global  _ulMax_ only at the completion of the operation.</span></span> 
  
<span data-ttu-id="a5731-130">使用第二个和第三个参数、 _ulCount_和_ulTotal_，如果可用，以显示可选消息，例如"5 项目完成 10。"</span><span class="sxs-lookup"><span data-stu-id="a5731-130">Use the second and third parameters,  _ulCount_ and  _ulTotal_, if available, to display an optional message such as "5 items completed out of 10."</span></span> <span data-ttu-id="a5731-131">如果第二个和第三个参数设置为 0，则可以选择以可视方式更改进度指示器。</span><span class="sxs-lookup"><span data-stu-id="a5731-131">If the second and third parameters are set to 0, you can choose whether or not to visually change the progress indicator.</span></span> <span data-ttu-id="a5731-132">某些服务提供商将这些参数设置为零，以指示它们处理相对于父对象监视其进度的子对象。</span><span class="sxs-lookup"><span data-stu-id="a5731-132">Some service providers set these parameters to zeroes to indicate that they are processing a subobject whose progress is monitored relative to a parent object.</span></span> <span data-ttu-id="a5731-133">在此情况下，有意义的父对象报告进度时仅显示更改。</span><span class="sxs-lookup"><span data-stu-id="a5731-133">In this situation, it makes sense to change the display only when the parent object reports progress.</span></span> <span data-ttu-id="a5731-134">某些服务提供商传递零为这些参数每次。</span><span class="sxs-lookup"><span data-stu-id="a5731-134">Some service providers pass zeroes for these parameters every time.</span></span> 
  

