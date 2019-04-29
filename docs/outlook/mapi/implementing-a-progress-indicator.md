---
title: 实现进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3a062a88-e87e-4c0c-944e-544a8f080930
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6972c960705c336aa6ff96d81b48ccbd490a22ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435094"
---
# <a name="implementing-a-progress-indicator"></a><span data-ttu-id="60155-103">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="60155-103">Implementing a Progress Indicator</span></span>

  
  
<span data-ttu-id="60155-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="60155-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="60155-105">客户端启动的许多操作花费的时间很长。</span><span class="sxs-lookup"><span data-stu-id="60155-105">Many of the operations initiated by clients take a significant amount of time.</span></span> <span data-ttu-id="60155-106">这些可能漫长的操作的输入参数之一是指向进度对象的指针, 该对象是一个实现[IMAPIProgress: IUnknown](imapiprogressiunknown.md)接口的对象。</span><span class="sxs-lookup"><span data-stu-id="60155-106">One of the input parameters to these potentially lengthy operations is a pointer to a progress object — an object that implements the [IMAPIProgress : IUnknown](imapiprogressiunknown.md) interface.</span></span> <span data-ttu-id="60155-107">进度对象控制进度指示器的外观和显示, 并由客户端和 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="60155-107">Progress objects control the appearance and display of progress indicators and are implemented by clients and by MAPI.</span></span> <span data-ttu-id="60155-108">您可以选择是否实现进度对象。</span><span class="sxs-lookup"><span data-stu-id="60155-108">You can choose whether or not to implement a progress object.</span></span> <span data-ttu-id="60155-109">如果选择不提供实现, 则可使用 MAPI 实施服务提供商。</span><span class="sxs-lookup"><span data-stu-id="60155-109">The MAPI implementation is available for service providers to use if you elect not to supply an implementation.</span></span> 
  
<span data-ttu-id="60155-110">进度对象使用以下数据片段:</span><span class="sxs-lookup"><span data-stu-id="60155-110">Progress objects work with the following pieces of data:</span></span>
  
- <span data-ttu-id="60155-111">一个全局最小值, 在调用[IMAPIProgress::P rogress](imapiprogress-progress.md)方法时, 应小于或等于_ulValue_参数的值。</span><span class="sxs-lookup"><span data-stu-id="60155-111">A global minimum value which, when your [IMAPIProgress::Progress](imapiprogress-progress.md) method is called, should be less than or equal to the value of the  _ulValue_ parameter.</span></span> <span data-ttu-id="60155-112">在操作开始时, _ulValue_将等于此最小值。</span><span class="sxs-lookup"><span data-stu-id="60155-112">At the beginning of the operation,  _ulValue_ will be equal to this minimum value.</span></span> 
    
- <span data-ttu-id="60155-113">当调用**IMAPIProgress::P rogress**方法时, 全局最大值应大于或等于_ulValue_参数。</span><span class="sxs-lookup"><span data-stu-id="60155-113">A global maximum value which, when your **IMAPIProgress::Progress** method is called, should be greater than or equal to the  _ulValue_ parameter.</span></span> <span data-ttu-id="60155-114">在操作结束时, _ulValue_将等于此最大值。</span><span class="sxs-lookup"><span data-stu-id="60155-114">At the end of the operation,  _ulValue_ will be equal to this maximum value.</span></span> 
    
- <span data-ttu-id="60155-115">一个标志值, 指示进度是否对应于顶层或较低级别的项。</span><span class="sxs-lookup"><span data-stu-id="60155-115">A flags value which indicates whether the progress corresponds to a top or lower level item.</span></span>
    
- <span data-ttu-id="60155-116">一个指示操作的当前进度级别的值。</span><span class="sxs-lookup"><span data-stu-id="60155-116">A value that indicates the current level of progress for the operation.</span></span>
    
- <span data-ttu-id="60155-117">当前处理的项相对于总数的数目。</span><span class="sxs-lookup"><span data-stu-id="60155-117">The number of the currently processed items relative to the total.</span></span>
    
- <span data-ttu-id="60155-118">操作过程中要处理的项目总数。</span><span class="sxs-lookup"><span data-stu-id="60155-118">The total number of items to be processed during the operation.</span></span>
    
<span data-ttu-id="60155-119">最小值和最大值代表数字形式的操作的开始和结束。</span><span class="sxs-lookup"><span data-stu-id="60155-119">The minimum and maximum values represent the beginning and end of the operation in numeric form.</span></span> <span data-ttu-id="60155-120">使用1作为初始最小值, 并1000将这些值传递给[IMAPIProgress:: GetMin](imapiprogress-getmin.md)和[IMAPIProgress:: GetMax](imapiprogress-getmax.md)方法中的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="60155-120">Use 1 for the initial minimum value and 1000 for the initial maximum value, passing these values to service providers in the [IMAPIProgress::GetMin](imapiprogress-getmin.md) and [IMAPIProgress::GetMax](imapiprogress-getmax.md) methods.</span></span> <span data-ttu-id="60155-121">服务提供程序在调用[IMAPIProgress:: SetLimits](imapiprogress-setlimits.md)时重置这些值。</span><span class="sxs-lookup"><span data-stu-id="60155-121">Service providers reset these values when they call [IMAPIProgress::SetLimits](imapiprogress-setlimits.md).</span></span> 
  
<span data-ttu-id="60155-122">"flags" 值由服务提供商用来确定应如何设置其他值。</span><span class="sxs-lookup"><span data-stu-id="60155-122">The flags value is used by service providers to determine how they should set the other values.</span></span> <span data-ttu-id="60155-123">将 flags 值初始化为 MAPI_TOP_LEVEL, 并在**GetFlags**的实现中返回此值, 直到服务提供程序通过调用**SetLimits**重置它。</span><span class="sxs-lookup"><span data-stu-id="60155-123">Initialize the flags value to MAPI_TOP_LEVEL and return this value in your implementation of **GetFlags** until the service provider resets it by calling **SetLimits**.</span></span> 
  
<span data-ttu-id="60155-124">在**SetLimits**方法的实现中, 保存每个参数的本地副本: _lpulMin_、 _lpulMax_和_lpulFlags_。</span><span class="sxs-lookup"><span data-stu-id="60155-124">In your implementation of the **SetLimits** method, save local copies of each of the parameters:  _lpulMin_,  _lpulMax_, and  _lpulFlags_.</span></span> <span data-ttu-id="60155-125">当服务提供商调用您的**GetMin**、 **GetMax**或**GetFlags**方法时, 这些值应易于使用。</span><span class="sxs-lookup"><span data-stu-id="60155-125">These values should be readily available when a service provider calls your **GetMin**, **GetMax**, or **GetFlags** methods.</span></span> 
  
<span data-ttu-id="60155-126">若要更新进度指示器的显示, 服务提供商将呼叫您的**IMAPIProgress::P rogress**方法。</span><span class="sxs-lookup"><span data-stu-id="60155-126">To update the display of the progress indicator, service providers call your **IMAPIProgress::Progress** method.</span></span> <span data-ttu-id="60155-127">此方法有三个参数: 值、计数和总计。</span><span class="sxs-lookup"><span data-stu-id="60155-127">There are three parameters to this method: a value, a count, and a total.</span></span> <span data-ttu-id="60155-128">使用第一个参数_ulValue_显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="60155-128">Use the first parameter,  _ulValue_, to display the progress indicator.</span></span> <span data-ttu-id="60155-129">_ulValue_参数是进度指示器, 它将等于全局_ulMin_仅在操作开始时等于全局 ulMax, 并且仅在操作完成时才等于全局__ 。</span><span class="sxs-lookup"><span data-stu-id="60155-129">The  _ulValue_ parameter is the progress indicator and will be equal to global  _ulMin_ only at the very beginning of the operation and equal to global  _ulMax_ only at the completion of the operation.</span></span> 
  
<span data-ttu-id="60155-130">使用第二个和第三个参数_ulCount_和_ulTotal_(如果可用) 显示可选的消息, 如 "5 个项目已完成10次"。</span><span class="sxs-lookup"><span data-stu-id="60155-130">Use the second and third parameters,  _ulCount_ and  _ulTotal_, if available, to display an optional message such as "5 items completed out of 10."</span></span> <span data-ttu-id="60155-131">如果第二个和第三个参数设置为 0, 则可以选择是否以可视方式更改进度指示器。</span><span class="sxs-lookup"><span data-stu-id="60155-131">If the second and third parameters are set to 0, you can choose whether or not to visually change the progress indicator.</span></span> <span data-ttu-id="60155-132">某些服务提供程序将这些参数设置为零, 以指示它们正在处理其进度受监视的子对象相对于父对象。</span><span class="sxs-lookup"><span data-stu-id="60155-132">Some service providers set these parameters to zeroes to indicate that they are processing a subobject whose progress is monitored relative to a parent object.</span></span> <span data-ttu-id="60155-133">在这种情况下, 仅在父对象报告进度时更改显示是有意义的。</span><span class="sxs-lookup"><span data-stu-id="60155-133">In this situation, it makes sense to change the display only when the parent object reports progress.</span></span> <span data-ttu-id="60155-134">某些服务提供程序每次传递这些参数的零。</span><span class="sxs-lookup"><span data-stu-id="60155-134">Some service providers pass zeroes for these parameters every time.</span></span> 
  

