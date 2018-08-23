---
title: IMAPIProgress IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress
api_type:
- COM
ms.assetid: 7a872296-0378-456f-b4d6-cb4d96b09d6e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 42d09fd92edf4dc221b73dac4948e78a7c6898ac
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589327"
---
# <a name="imapiprogress--iunknown"></a><span data-ttu-id="a397d-103">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a397d-103">IMAPIProgress : IUnknown</span></span>

  
  
<span data-ttu-id="a397d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a397d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a397d-105">实现提供与进度指示器的客户端应用程序的进度对象。</span><span class="sxs-lookup"><span data-stu-id="a397d-105">Implements a progress object that provides client applications with a progress indicator.</span></span> <span data-ttu-id="a397d-106">显示的操作，如复制文件夹消息存储库之间的完成百分比的用户界面显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="a397d-106">A progress indicator is a user-interface display that shows the percentage of completion of an operation, such as copying folders between message stores.</span></span> <span data-ttu-id="a397d-107">MAPI 和客户端应用程序实现进度对象，服务提供商使用它们。</span><span class="sxs-lookup"><span data-stu-id="a397d-107">MAPI and client applications implement progress objects and service providers use them.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a397d-108">头文件：</span><span class="sxs-lookup"><span data-stu-id="a397d-108">Header file:</span></span>  <br/> |<span data-ttu-id="a397d-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a397d-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="a397d-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="a397d-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="a397d-111">进度对象</span><span class="sxs-lookup"><span data-stu-id="a397d-111">Progress objects</span></span>  <br/> |
|<span data-ttu-id="a397d-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="a397d-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="a397d-113">MAPI 和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="a397d-113">MAPI and client applications</span></span>  <br/> |
|<span data-ttu-id="a397d-114">调用：</span><span class="sxs-lookup"><span data-stu-id="a397d-114">Called by:</span></span>  <br/> |<span data-ttu-id="a397d-115">服务提供商</span><span class="sxs-lookup"><span data-stu-id="a397d-115">Service providers</span></span>  <br/> |
|<span data-ttu-id="a397d-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="a397d-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="a397d-117">IID_IMAPIProgress</span><span class="sxs-lookup"><span data-stu-id="a397d-117">IID_IMAPIProgress</span></span>  <br/> |
|<span data-ttu-id="a397d-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="a397d-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="a397d-119">LPMAPIPROGRESS</span><span class="sxs-lookup"><span data-stu-id="a397d-119">LPMAPIPROGRESS</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="a397d-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="a397d-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="a397d-121">Progress</span><span class="sxs-lookup"><span data-stu-id="a397d-121">Progress</span></span>](imapiprogress-progress.md) <br/> |<span data-ttu-id="a397d-122">更新进度指示器进度的显示做出的操作完成。</span><span class="sxs-lookup"><span data-stu-id="a397d-122">Updates the progress indicator with a display of the progress as it is made toward completion of the operation.</span></span>  <br/> |
|[<span data-ttu-id="a397d-123">GetFlags</span><span class="sxs-lookup"><span data-stu-id="a397d-123">GetFlags</span></span>](imapiprogress-getflags.md) <br/> |<span data-ttu-id="a397d-124">返回标记的操作对其计算进度信息的级别的进度对象中的设置。</span><span class="sxs-lookup"><span data-stu-id="a397d-124">Returns flag settings from the progress object for the level of operation on which progress information is calculated.</span></span>  <br/> |
|[<span data-ttu-id="a397d-125">GetMax</span><span class="sxs-lookup"><span data-stu-id="a397d-125">GetMax</span></span>](imapiprogress-getmax.md) <br/> |<span data-ttu-id="a397d-126">对于的进度的信息将显示的操作中返回的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="a397d-126">Returns the maximum number of items in the operation for which progress information is displayed.</span></span>  <br/> |
|[<span data-ttu-id="a397d-127">GetMin</span><span class="sxs-lookup"><span data-stu-id="a397d-127">GetMin</span></span>](imapiprogress-getmin.md) <br/> |<span data-ttu-id="a397d-128">对于的进度的信息将显示在[SetLimits](imapiprogress-setlimits.md)方法中返回的最小值。</span><span class="sxs-lookup"><span data-stu-id="a397d-128">Returns the minimum value in the [SetLimits](imapiprogress-setlimits.md) method for which progress information is displayed.</span></span>  <br/> |
|[<span data-ttu-id="a397d-129">SetLimits</span><span class="sxs-lookup"><span data-stu-id="a397d-129">SetLimits</span></span>](imapiprogress-setlimits.md) <br/> |<span data-ttu-id="a397d-130">设置项的数目的上限和下限限制中操作，并且控制操作的进度信息的计算方式的标志。</span><span class="sxs-lookup"><span data-stu-id="a397d-130">Sets the lower and upper limits for the number of items in the operation, and the flags that control how progress information is calculated for the operation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a397d-131">注解</span><span class="sxs-lookup"><span data-stu-id="a397d-131">Remarks</span></span>

<span data-ttu-id="a397d-132">MAPI 中的许多方法执行可能长时间的操作包括_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="a397d-132">MAPI includes an  _lpProgress_ parameter in many of the methods that perform potentially lengthy operations.</span></span>  <span data-ttu-id="a397d-133">_lpProgress_指向进度对象的客户端实现。</span><span class="sxs-lookup"><span data-stu-id="a397d-133">_lpProgress_ points to a client implementation of a progress object.</span></span> <span data-ttu-id="a397d-134">客户端实现**IMAPIProgress**接口的设置此参数可指向其实现;客户端不实现**IMAPIProgress**参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a397d-134">Clients that implement the **IMAPIProgress** interface set this parameter to point to their implementation; clients that do not implement **IMAPIProgress** set the parameter to NULL.</span></span> <span data-ttu-id="a397d-135">若要处理的操作过程中显示进度指示器，服务提供商使用的进度对象，提供由客户端，如果可用，或者 （指示_lpProgress_设置为 NULL 时） 的 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="a397d-135">To display a progress indicator during processing of the operation, service providers use the progress object supplied by the client, if available, or a MAPI implementation (indicated when  _lpProgress_ is set to NULL).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a397d-136">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="a397d-136">MFCMAPI reference</span></span>

<span data-ttu-id="a397d-137">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a397d-137">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a397d-138">**文件**</span><span class="sxs-lookup"><span data-stu-id="a397d-138">**Files**</span></span>|<span data-ttu-id="a397d-139">**函数**</span><span class="sxs-lookup"><span data-stu-id="a397d-139">**Function**</span></span>|<span data-ttu-id="a397d-140">**Comment**</span><span class="sxs-lookup"><span data-stu-id="a397d-140">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a397d-141">MapiProgress.h 和 MapiProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="a397d-141">MapiProgress.h and MapiProgress.cpp</span></span>  <br/> |<span data-ttu-id="a397d-142">不适用</span><span class="sxs-lookup"><span data-stu-id="a397d-142">Not applicable</span></span>  <br/> |<span data-ttu-id="a397d-143">如果启用 IMAPIProgress 设置后，MFCMAPI 将**IMAPIProgress**实现将传递给所有 MFCMAPI 调用接受实现的功能。</span><span class="sxs-lookup"><span data-stu-id="a397d-143">If the IMAPIProgress setting is enabled, MFCMAPI will pass an **IMAPIProgress** implementation to all functions that MFCMAPI invokes that accept an implementation.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a397d-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a397d-144">See also</span></span>



[<span data-ttu-id="a397d-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a397d-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="a397d-146">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="a397d-146">MAPI Interfaces</span></span>](mapi-interfaces.md)

