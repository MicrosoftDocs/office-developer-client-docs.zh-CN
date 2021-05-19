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
ms.openlocfilehash: 3a3d54ac9485cc3915d3606bb84b4f3191d1ca5b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419644"
---
# <a name="imapiprogress--iunknown"></a><span data-ttu-id="fe515-103">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fe515-103">IMAPIProgress : IUnknown</span></span>

  
  
<span data-ttu-id="fe515-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fe515-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fe515-105">实现一个进度对象，该对象为客户端应用程序提供进度指示器。</span><span class="sxs-lookup"><span data-stu-id="fe515-105">Implements a progress object that provides client applications with a progress indicator.</span></span> <span data-ttu-id="fe515-106">进度指示器是显示操作完成百分比的用户界面显示，例如复制邮件存储之间的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fe515-106">A progress indicator is a user-interface display that shows the percentage of completion of an operation, such as copying folders between message stores.</span></span> <span data-ttu-id="fe515-107">MAPI 和客户端应用程序实现进度对象，服务提供商使用它们。</span><span class="sxs-lookup"><span data-stu-id="fe515-107">MAPI and client applications implement progress objects and service providers use them.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fe515-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fe515-108">Header file:</span></span>  <br/> |<span data-ttu-id="fe515-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fe515-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="fe515-110">公开者：</span><span class="sxs-lookup"><span data-stu-id="fe515-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="fe515-111">进度对象</span><span class="sxs-lookup"><span data-stu-id="fe515-111">Progress objects</span></span>  <br/> |
|<span data-ttu-id="fe515-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="fe515-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="fe515-113">MAPI 和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="fe515-113">MAPI and client applications</span></span>  <br/> |
|<span data-ttu-id="fe515-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="fe515-114">Called by:</span></span>  <br/> |<span data-ttu-id="fe515-115">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="fe515-115">Service providers</span></span>  <br/> |
|<span data-ttu-id="fe515-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="fe515-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="fe515-117">IID_IMAPIProgress</span><span class="sxs-lookup"><span data-stu-id="fe515-117">IID_IMAPIProgress</span></span>  <br/> |
|<span data-ttu-id="fe515-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="fe515-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="fe515-119">LPMAPIPROGRESS</span><span class="sxs-lookup"><span data-stu-id="fe515-119">LPMAPIPROGRESS</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="fe515-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="fe515-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="fe515-121">Progress</span><span class="sxs-lookup"><span data-stu-id="fe515-121">Progress</span></span>](imapiprogress-progress.md) <br/> |<span data-ttu-id="fe515-122">更新进度指示器，并显示在操作完成时的进度。</span><span class="sxs-lookup"><span data-stu-id="fe515-122">Updates the progress indicator with a display of the progress as it is made toward completion of the operation.</span></span>  <br/> |
|[<span data-ttu-id="fe515-123">GetFlags</span><span class="sxs-lookup"><span data-stu-id="fe515-123">GetFlags</span></span>](imapiprogress-getflags.md) <br/> |<span data-ttu-id="fe515-124">从计算进度信息的操作级别的进度对象中返回标志设置。</span><span class="sxs-lookup"><span data-stu-id="fe515-124">Returns flag settings from the progress object for the level of operation on which progress information is calculated.</span></span>  <br/> |
|[<span data-ttu-id="fe515-125">GetMax</span><span class="sxs-lookup"><span data-stu-id="fe515-125">GetMax</span></span>](imapiprogress-getmax.md) <br/> |<span data-ttu-id="fe515-126">返回操作中显示其进度信息的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="fe515-126">Returns the maximum number of items in the operation for which progress information is displayed.</span></span>  <br/> |
|[<span data-ttu-id="fe515-127">GetMin</span><span class="sxs-lookup"><span data-stu-id="fe515-127">GetMin</span></span>](imapiprogress-getmin.md) <br/> |<span data-ttu-id="fe515-128">返回 [SetLimits](imapiprogress-setlimits.md) 方法中显示进度信息的最小值。</span><span class="sxs-lookup"><span data-stu-id="fe515-128">Returns the minimum value in the [SetLimits](imapiprogress-setlimits.md) method for which progress information is displayed.</span></span>  <br/> |
|[<span data-ttu-id="fe515-129">SetLimits</span><span class="sxs-lookup"><span data-stu-id="fe515-129">SetLimits</span></span>](imapiprogress-setlimits.md) <br/> |<span data-ttu-id="fe515-130">设置操作中项数的下限和上限，以及控制如何计算操作进度信息的标志。</span><span class="sxs-lookup"><span data-stu-id="fe515-130">Sets the lower and upper limits for the number of items in the operation, and the flags that control how progress information is calculated for the operation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fe515-131">备注</span><span class="sxs-lookup"><span data-stu-id="fe515-131">Remarks</span></span>

<span data-ttu-id="fe515-132">MAPI 在很多执行可能过长操作的方法中包含  _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="fe515-132">MAPI includes an  _lpProgress_ parameter in many of the methods that perform potentially lengthy operations.</span></span>  <span data-ttu-id="fe515-133">_lpProgress_ 指向进度对象的客户端实现。</span><span class="sxs-lookup"><span data-stu-id="fe515-133">_lpProgress_ points to a client implementation of a progress object.</span></span> <span data-ttu-id="fe515-134">实现 **IMAPIProgress 接口** 的客户端设置此参数以指向其实现;不实现 **IMAPIProgress 的客户端将** 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fe515-134">Clients that implement the **IMAPIProgress** interface set this parameter to point to their implementation; clients that do not implement **IMAPIProgress** set the parameter to NULL.</span></span> <span data-ttu-id="fe515-135">若要在处理操作期间显示进度指示器，服务提供商将使用客户端提供的进度对象（如果可用）或 MAPI 实现 (当  _lpProgress_ 设置为 NULL) 。</span><span class="sxs-lookup"><span data-stu-id="fe515-135">To display a progress indicator during processing of the operation, service providers use the progress object supplied by the client, if available, or a MAPI implementation (indicated when  _lpProgress_ is set to NULL).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="fe515-136">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="fe515-136">MFCMAPI reference</span></span>

<span data-ttu-id="fe515-137">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fe515-137">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fe515-138">**Files**</span><span class="sxs-lookup"><span data-stu-id="fe515-138">**Files**</span></span>|<span data-ttu-id="fe515-139">**函数**</span><span class="sxs-lookup"><span data-stu-id="fe515-139">**Function**</span></span>|<span data-ttu-id="fe515-140">**备注**</span><span class="sxs-lookup"><span data-stu-id="fe515-140">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fe515-141">MapiProgress.h 和 MapiProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="fe515-141">MapiProgress.h and MapiProgress.cpp</span></span>  <br/> |<span data-ttu-id="fe515-142">不适用</span><span class="sxs-lookup"><span data-stu-id="fe515-142">Not applicable</span></span>  <br/> |<span data-ttu-id="fe515-143">如果启用了 IMAPIProgress 设置，则 MFCMAPI 将 **IMAPIProgress** 实现传递给 MFCMAPI 调用接受实现的所有函数。</span><span class="sxs-lookup"><span data-stu-id="fe515-143">If the IMAPIProgress setting is enabled, MFCMAPI will pass an **IMAPIProgress** implementation to all functions that MFCMAPI invokes that accept an implementation.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fe515-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe515-144">See also</span></span>



[<span data-ttu-id="fe515-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fe515-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="fe515-146">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="fe515-146">MAPI Interfaces</span></span>](mapi-interfaces.md)

