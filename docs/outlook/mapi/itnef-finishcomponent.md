---
title: ITnefFinishComponent
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.FinishComponent
api_type:
- COM
ms.assetid: bcdd0688-0897-47d7-9601-f592ba453b39
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c8dc10bdb8bcde15dccf7bab4d9e10d2481cef11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416438"
---
# <a name="itneffinishcomponent"></a><span data-ttu-id="66117-103">ITnef::FinishComponent</span><span class="sxs-lookup"><span data-stu-id="66117-103">ITnef::FinishComponent</span></span>

  
  
<span data-ttu-id="66117-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66117-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66117-105">将邮件中的单个组件一次处理成一个Transport-Neutral封装格式 (TNEF) 流。</span><span class="sxs-lookup"><span data-stu-id="66117-105">Processes individual components from a message one at a time into a Transport-Neutral Encapsulation Format (TNEF) stream.</span></span>
  
```cpp
HRESULT FinishComponent(
  ULONG ulFlags,
  ULONG ulComponentID,
  LPSPropTagArray lpCustomPropList,
  LPSPropValue lpCustomProps,
  LPSPropTagArray lpPropList,
  LPSTnefProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="66117-106">参数</span><span class="sxs-lookup"><span data-stu-id="66117-106">Parameters</span></span>

 <span data-ttu-id="66117-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="66117-107">_ulFlags_</span></span>
  
> <span data-ttu-id="66117-108">[in]用于控制哪些组件将完成的标记的位掩码。</span><span class="sxs-lookup"><span data-stu-id="66117-108">[in] A bitmask of flags that controls which component will be finished.</span></span> <span data-ttu-id="66117-109">必须设置以下标志之一：</span><span class="sxs-lookup"><span data-stu-id="66117-109">One or the other of the following flags must be set:</span></span>
    
<span data-ttu-id="66117-110">TNEF_COMPONENT_ATTACHMENT</span><span class="sxs-lookup"><span data-stu-id="66117-110">TNEF_COMPONENT_ATTACHMENT</span></span> 
  
> <span data-ttu-id="66117-111">将完成附件对象的处理;_ulComponentID_ 参数包含PR_ATTACH_NUM ([的 PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="66117-111">Processing will be finished for an attachment object; the  _ulComponentID_ parameter contains the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property of the attachment.</span></span> 
    
<span data-ttu-id="66117-112">TNEF_COMPONENT_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="66117-112">TNEF_COMPONENT_MESSAGE</span></span> 
  
> <span data-ttu-id="66117-113">将完成消息对象的处理。</span><span class="sxs-lookup"><span data-stu-id="66117-113">Processing will be finished for a message object.</span></span> 
    
 <span data-ttu-id="66117-114">_ulComponentID_</span><span class="sxs-lookup"><span data-stu-id="66117-114">_ulComponentID_</span></span>
  
> <span data-ttu-id="66117-115">[in] 0 指示邮件的处理，或 **PR_ATTACH_NUM** 附件的 属性。</span><span class="sxs-lookup"><span data-stu-id="66117-115">[in] 0 to indicate processing for a message, or the **PR_ATTACH_NUM** property of an attachment to be processed.</span></span> <span data-ttu-id="66117-116">如果在  _ulFlags_ 参数中设置了 TNEF_COMPONENT_MESSAGE 标志，  _则 ulComponentID_ 必须为 0。</span><span class="sxs-lookup"><span data-stu-id="66117-116">If the TNEF_COMPONENT_MESSAGE flag is set in the  _ulFlags_ parameter,  _ulComponentID_ must be 0.</span></span> 
    
 <span data-ttu-id="66117-117">_lpCustomPropList_</span><span class="sxs-lookup"><span data-stu-id="66117-117">_lpCustomPropList_</span></span>
  
> <span data-ttu-id="66117-118">[in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含标识在  _lpCustomProps_ 参数中传递的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="66117-118">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains property tags that identify the properties passed in the  _lpCustomProps_ parameter.</span></span> <span data-ttu-id="66117-119">_lpCustomProps_ 中每个属性值与 _lpCustomPropList_ 参数中的属性标记之间必须存在一对一的对应关系。</span><span class="sxs-lookup"><span data-stu-id="66117-119">There must be a one-to-one correspondence between each property value in  _lpCustomProps_ and a property tag in the  _lpCustomPropList_ parameter.</span></span> 
    
 <span data-ttu-id="66117-120">_lpCustomProps_</span><span class="sxs-lookup"><span data-stu-id="66117-120">_lpCustomProps_</span></span>
  
> <span data-ttu-id="66117-121">[in]指向 [SPropValue](spropvalue.md) 结构的指针，其中包含要编码的属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="66117-121">[in] A pointer to an [SPropValue](spropvalue.md) structure that contains property values for the properties to encode.</span></span> 
    
 <span data-ttu-id="66117-122">_lpPropList_</span><span class="sxs-lookup"><span data-stu-id="66117-122">_lpPropList_</span></span>
  
> <span data-ttu-id="66117-123">[in]指向 **SPropTagArray** 结构的指针，其中包含要编码的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="66117-123">[in] A pointer to an **SPropTagArray** structure that contains property tags for the properties to encode.</span></span> 
    
 <span data-ttu-id="66117-124">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="66117-124">_lppProblems_</span></span>
  
> <span data-ttu-id="66117-125">[out]指向返回的 [STnefProblemArray 结构的指针的](stnefproblemarray.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="66117-125">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="66117-126">**STnefProblemArray** 结构指示哪些属性（如果有）未正确编码。</span><span class="sxs-lookup"><span data-stu-id="66117-126">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="66117-127">如果在  _lppProblems_ 参数中传递 NULL，则不返回任何属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="66117-127">If NULL is passed in the  _lppProblems_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="66117-128">返回值</span><span class="sxs-lookup"><span data-stu-id="66117-128">Return value</span></span>

<span data-ttu-id="66117-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="66117-129">S_OK</span></span> 
  
> <span data-ttu-id="66117-130">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="66117-130">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="66117-131">备注</span><span class="sxs-lookup"><span data-stu-id="66117-131">Remarks</span></span>

<span data-ttu-id="66117-132">传输提供程序、邮件存储提供程序和网关调用 **ITnef：：FinishComponent** 方法来对一个组件（邮件或附件）执行 TNEF 处理，如  _ulFlags_ 参数中设置的标志所指示。</span><span class="sxs-lookup"><span data-stu-id="66117-132">Transport providers, message store providers, and gateways call the **ITnef::FinishComponent** method to perform TNEF processing for one component, either a message or an attachment, as indicated by the flag set in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="66117-133">为了启用组件处理，调用提供程序或网关在  _ulFlags_ 中为 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md) 函数传递 TNEF_COMPONENT_ENCODING 标志，该 [函数](opentnefstreamex.md) 打开对象以接收编码。</span><span class="sxs-lookup"><span data-stu-id="66117-133">For component processing to be enabled, the calling provider or gateway pass the TNEF_COMPONENT_ENCODING flag in  _ulFlags_ for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function that opened the object to receive encoding.</span></span> 
  
<span data-ttu-id="66117-134">在  _lpCustomPropList_ 和  _lpCustomProps_ 参数中传递值将执行与 [ITnef：：SetProps](itnef-setprops.md) 方法所完成的组件编码等效的组件编码。</span><span class="sxs-lookup"><span data-stu-id="66117-134">Passing values in the  _lpCustomPropList_ and  _lpCustomProps_ parameters performs component encoding equivalent to that done by the [ITnef::SetProps](itnef-setprops.md) method.</span></span> <span data-ttu-id="66117-135">在  _lpPropList_ 参数中传递值将执行与 [ITnef：：AddProps](itnef-addprops.md) 方法等效的组件编码，该方法在  _ulFlags_ 中设置了 TNEF_PROP_INCLUDE 标志。</span><span class="sxs-lookup"><span data-stu-id="66117-135">Passing a value in the  _lpPropList_ parameter performs component encoding equivalent to that done by the [ITnef::AddProps](itnef-addprops.md) method with the TNEF_PROP_INCLUDE flag set in  _ulFlags_.</span></span> <span data-ttu-id="66117-136">通过传递这些值，可以通过单个调用（而不是多个呼叫）执行编码。</span><span class="sxs-lookup"><span data-stu-id="66117-136">Passing these values enables you to perform encodings with a single call instead of multiple calls.</span></span>
  
<span data-ttu-id="66117-137">TNEF 实现报告 TNEF 流编码问题，而不停止 **FinishComponent** 进程。</span><span class="sxs-lookup"><span data-stu-id="66117-137">The TNEF implementation reports TNEF stream encoding problems without stopping the **FinishComponent** process.</span></span> <span data-ttu-id="66117-138">_lppProblems_ 中返回的 **STnefProblemArray** 结构指示无法处理哪些 TNEF 属性或 MAPI 属性（如果有）。</span><span class="sxs-lookup"><span data-stu-id="66117-138">The **STnefProblemArray** structure returned in  _lppProblems_ indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="66117-139">**STnefProblemArray** 中包含的 **STnefProblem** 结构之一的 **scode** 成员中返回的值指示特定问题。</span><span class="sxs-lookup"><span data-stu-id="66117-139">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="66117-140">提供商或网关可以在以下假设下工作 **：FinishComponent** 未返回问题报告的所有属性或属性都已成功处理。</span><span class="sxs-lookup"><span data-stu-id="66117-140">The provider or gateway can work on the assumption that all properties or attributes for which **FinishComponent** does not return a problem report were processed successfully.</span></span> 
  
<span data-ttu-id="66117-141">如果提供程序或网关不处理问题数组，它可以在  _lppProblems_ 中传递 NULL;在这种情况下，不会返回问题数组。</span><span class="sxs-lookup"><span data-stu-id="66117-141">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lppProblems_; in this case, no problem array is returned.</span></span>
  
<span data-ttu-id="66117-142">_lppProblems_ 中返回的值仅在调用返回值时S_OK。</span><span class="sxs-lookup"><span data-stu-id="66117-142">The value returned in  _lppProblems_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="66117-143">返回S_OK时，提供商或网关应检查 [STnefProblemArray](stnefproblemarray.md) 结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="66117-143">When S_OK is returned, the provider or gateway should check the values returned in the [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="66117-144">如果呼叫出错， **则不填充 STnefProblemArray** 结构，并且调用提供程序或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="66117-144">If an error occurs on the call, the **STnefProblemArray** structure is not filled in, and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="66117-145">如果呼叫中未发生错误，则调用提供程序或网关必须通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放 **STnefProblemArray** 的内存。</span><span class="sxs-lookup"><span data-stu-id="66117-145">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="66117-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66117-146">See also</span></span>



[<span data-ttu-id="66117-147">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="66117-147">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="66117-148">ITnef::SetProps</span><span class="sxs-lookup"><span data-stu-id="66117-148">ITnef::SetProps</span></span>](itnef-setprops.md)
  
[<span data-ttu-id="66117-149">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="66117-149">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="66117-150">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="66117-150">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="66117-151">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="66117-151">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="66117-152">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="66117-152">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="66117-153">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="66117-153">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="66117-154">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="66117-154">ITnef : IUnknown</span></span>](itnefiunknown.md)

