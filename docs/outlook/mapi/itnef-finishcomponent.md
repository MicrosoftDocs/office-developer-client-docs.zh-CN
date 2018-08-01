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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7008549111f1b914cf2025c8d61ebc07196706fb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776104"
---
# <a name="itneffinishcomponent"></a><span data-ttu-id="9af8a-103">ITnef::FinishComponent</span><span class="sxs-lookup"><span data-stu-id="9af8a-103">ITnef::FinishComponent</span></span>

  
  
<span data-ttu-id="9af8a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9af8a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9af8a-105">到传输中性封装格式 (TNEF) stream 一次处理从一个一条消息的各个组件。</span><span class="sxs-lookup"><span data-stu-id="9af8a-105">Processes individual components from a message one at a time into a Transport-Neutral Encapsulation Format (TNEF) stream.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="9af8a-106">参数</span><span class="sxs-lookup"><span data-stu-id="9af8a-106">Parameters</span></span>

 <span data-ttu-id="9af8a-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9af8a-107">_ulFlags_</span></span>
  
> <span data-ttu-id="9af8a-108">[in]将完成控制哪些组件的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="9af8a-108">[in] A bitmask of flags that controls which component will be finished.</span></span> <span data-ttu-id="9af8a-109">必须设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="9af8a-109">One or the other of the following flags must be set:</span></span>
    
<span data-ttu-id="9af8a-110">TNEF_COMPONENT_ATTACHMENT</span><span class="sxs-lookup"><span data-stu-id="9af8a-110">TNEF_COMPONENT_ATTACHMENT</span></span> 
  
> <span data-ttu-id="9af8a-111">处理将完成的 attachment 对象;_ulComponentID_参数包含附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="9af8a-111">Processing will be finished for an attachment object; the  _ulComponentID_ parameter contains the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property of the attachment.</span></span> 
    
<span data-ttu-id="9af8a-112">TNEF_COMPONENT_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="9af8a-112">TNEF_COMPONENT_MESSAGE</span></span> 
  
> <span data-ttu-id="9af8a-113">处理将完成的消息对象中。</span><span class="sxs-lookup"><span data-stu-id="9af8a-113">Processing will be finished for a message object.</span></span> 
    
 <span data-ttu-id="9af8a-114">_ulComponentID_</span><span class="sxs-lookup"><span data-stu-id="9af8a-114">_ulComponentID_</span></span>
  
> <span data-ttu-id="9af8a-115">[in] 0，以指示一条消息，或附件的**PR_ATTACH_NUM**属性处理的处理。</span><span class="sxs-lookup"><span data-stu-id="9af8a-115">[in] 0 to indicate processing for a message, or the **PR_ATTACH_NUM** property of an attachment to be processed.</span></span> <span data-ttu-id="9af8a-116">如果_ulFlags_参数中设置 TNEF_COMPONENT_MESSAGE 标志， _ulComponentID_必须为 0。</span><span class="sxs-lookup"><span data-stu-id="9af8a-116">If the TNEF_COMPONENT_MESSAGE flag is set in the  _ulFlags_ parameter,  _ulComponentID_ must be 0.</span></span> 
    
 <span data-ttu-id="9af8a-117">_lpCustomPropList_</span><span class="sxs-lookup"><span data-stu-id="9af8a-117">_lpCustomPropList_</span></span>
  
> <span data-ttu-id="9af8a-118">[in]一个指向[SPropTagArray](sproptagarray.md)结构，其中包含属性标记来标识_lpCustomProps_参数中传递的属性。</span><span class="sxs-lookup"><span data-stu-id="9af8a-118">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains property tags that identify the properties passed in the  _lpCustomProps_ parameter.</span></span> <span data-ttu-id="9af8a-119">必须有一一对应_lpCustomProps_中的每个属性值与_lpCustomPropList_参数中的属性标记之间。</span><span class="sxs-lookup"><span data-stu-id="9af8a-119">There must be a one-to-one correspondence between each property value in  _lpCustomProps_ and a property tag in the  _lpCustomPropList_ parameter.</span></span> 
    
 <span data-ttu-id="9af8a-120">_lpCustomProps_</span><span class="sxs-lookup"><span data-stu-id="9af8a-120">_lpCustomProps_</span></span>
  
> <span data-ttu-id="9af8a-121">[in]一个指向[SPropValue](spropvalue.md)结构，其中包含要编码的属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="9af8a-121">[in] A pointer to an [SPropValue](spropvalue.md) structure that contains property values for the properties to encode.</span></span> 
    
 <span data-ttu-id="9af8a-122">_lpPropList_</span><span class="sxs-lookup"><span data-stu-id="9af8a-122">_lpPropList_</span></span>
  
> <span data-ttu-id="9af8a-123">[in]指向**SPropTagArray**结构，其中包含要编码的属性的属性标记的指针。</span><span class="sxs-lookup"><span data-stu-id="9af8a-123">[in] A pointer to an **SPropTagArray** structure that contains property tags for the properties to encode.</span></span> 
    
 <span data-ttu-id="9af8a-124">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="9af8a-124">_lppProblems_</span></span>
  
> <span data-ttu-id="9af8a-125">[输出]指向返回[STnefProblemArray](stnefproblemarray.md)结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9af8a-125">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="9af8a-126">**STnefProblemArray**结构表明哪些属性中，如果有，已未编码的正确。</span><span class="sxs-lookup"><span data-stu-id="9af8a-126">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="9af8a-127">如果_lppProblems_参数中传递了 NULL，则返回没有属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="9af8a-127">If NULL is passed in the  _lppProblems_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9af8a-128">返回值</span><span class="sxs-lookup"><span data-stu-id="9af8a-128">Return value</span></span>

<span data-ttu-id="9af8a-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="9af8a-129">S_OK</span></span> 
  
> <span data-ttu-id="9af8a-130">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="9af8a-130">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9af8a-131">说明</span><span class="sxs-lookup"><span data-stu-id="9af8a-131">Remarks</span></span>

<span data-ttu-id="9af8a-132">传输提供程序、 消息存储提供程序，和网关呼叫**ITnef::FinishComponent**方法执行 TNEF 处理的一个组件，一条消息或附件，如标志所指示的_ulFlags_参数中设置。</span><span class="sxs-lookup"><span data-stu-id="9af8a-132">Transport providers, message store providers, and gateways call the **ITnef::FinishComponent** method to perform TNEF processing for one component, either a message or an attachment, as indicated by the flag set in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="9af8a-133">若要启用的组件处理，呼叫提供商或网关 TNEF_COMPONENT_ENCODING 标志中传递_ulFlags_ [OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数打开要接收编码的对象。</span><span class="sxs-lookup"><span data-stu-id="9af8a-133">For component processing to be enabled, the calling provider or gateway pass the TNEF_COMPONENT_ENCODING flag in  _ulFlags_ for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function that opened the object to receive encoding.</span></span> 
  
<span data-ttu-id="9af8a-134">在_lpCustomPropList_和_lpCustomProps_参数中传递值执行组件编码等价于[ITnef::SetProps](itnef-setprops.md)方法执行的。</span><span class="sxs-lookup"><span data-stu-id="9af8a-134">Passing values in the  _lpCustomPropList_ and  _lpCustomProps_ parameters performs component encoding equivalent to that done by the [ITnef::SetProps](itnef-setprops.md) method.</span></span> <span data-ttu-id="9af8a-135">_LpPropList_参数中传递值执行组件编码等效项以的[ITnef::AddProps](itnef-addprops.md)方法通过_ulFlags_中设置 TNEF_PROP_INCLUDE 标志。</span><span class="sxs-lookup"><span data-stu-id="9af8a-135">Passing a value in the  _lpPropList_ parameter performs component encoding equivalent to that done by the [ITnef::AddProps](itnef-addprops.md) method with the TNEF_PROP_INCLUDE flag set in  _ulFlags_.</span></span> <span data-ttu-id="9af8a-136">将这些值传递使您可以执行而不是多个呼叫的单个调用进行编码。</span><span class="sxs-lookup"><span data-stu-id="9af8a-136">Passing these values enables you to perform encodings with a single call instead of multiple calls.</span></span>
  
<span data-ttu-id="9af8a-137">TNEF 实现报告而不停止**FinishComponent**进程 TNEF 流编码问题。</span><span class="sxs-lookup"><span data-stu-id="9af8a-137">The TNEF implementation reports TNEF stream encoding problems without stopping the **FinishComponent** process.</span></span> <span data-ttu-id="9af8a-138">返回在_lppProblems_ **STnefProblemArray**结构指示哪些 TNEF 属性或 MAPI 属性，如果有，无法进行处理。</span><span class="sxs-lookup"><span data-stu-id="9af8a-138">The **STnefProblemArray** structure returned in  _lppProblems_ indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="9af8a-139">在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指示特定问题。</span><span class="sxs-lookup"><span data-stu-id="9af8a-139">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="9af8a-140">所有属性或特性**FinishComponent**不会返回问题报告都已成功都处理假定可以处理提供程序或网关。</span><span class="sxs-lookup"><span data-stu-id="9af8a-140">The provider or gateway can work on the assumption that all properties or attributes for which **FinishComponent** does not return a problem report were processed successfully.</span></span> 
  
<span data-ttu-id="9af8a-141">如果提供程序或网关不适用于问题数组，它可以在_lppProblems_; 传递 NULL在这种情况下，则返回没有问题数组。</span><span class="sxs-lookup"><span data-stu-id="9af8a-141">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lppProblems_; in this case, no problem array is returned.</span></span>
  
<span data-ttu-id="9af8a-142">仅当呼叫，则返回 S_OK 有效_lppProblems_中返回的值。</span><span class="sxs-lookup"><span data-stu-id="9af8a-142">The value returned in  _lppProblems_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="9af8a-143">返回 S_OK 时，提供程序或网关应检查[STnefProblemArray](stnefproblemarray.md)结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="9af8a-143">When S_OK is returned, the provider or gateway should check the values returned in the [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="9af8a-144">如果调用时出现错误，不填写**STnefProblemArray**结构，并且呼叫提供商或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="9af8a-144">If an error occurs on the call, the **STnefProblemArray** structure is not filled in, and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="9af8a-145">如果在调用不产生任何错误，呼叫提供商或网关必须释放内存的**STnefProblemArray**通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="9af8a-145">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9af8a-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9af8a-146">See also</span></span>



[<span data-ttu-id="9af8a-147">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="9af8a-147">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="9af8a-148">ITnef::SetProps</span><span class="sxs-lookup"><span data-stu-id="9af8a-148">ITnef::SetProps</span></span>](itnef-setprops.md)
  
[<span data-ttu-id="9af8a-149">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="9af8a-149">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="9af8a-150">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="9af8a-150">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="9af8a-151">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="9af8a-151">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="9af8a-152">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="9af8a-152">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="9af8a-153">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="9af8a-153">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="9af8a-154">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9af8a-154">ITnef : IUnknown</span></span>](itnefiunknown.md)

