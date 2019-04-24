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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278884"
---
# <a name="itneffinishcomponent"></a><span data-ttu-id="2e1ec-103">ITnef::FinishComponent</span><span class="sxs-lookup"><span data-stu-id="2e1ec-103">ITnef::FinishComponent</span></span>

  
  
<span data-ttu-id="2e1ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e1ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e1ec-105">将邮件中的单个组件一次性处理为非特定传输封装格式 (TNEF) 流。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-105">Processes individual components from a message one at a time into a Transport-Neutral Encapsulation Format (TNEF) stream.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="2e1ec-106">参数</span><span class="sxs-lookup"><span data-stu-id="2e1ec-106">Parameters</span></span>

 <span data-ttu-id="2e1ec-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2e1ec-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2e1ec-108">实时用于控制要完成的组件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-108">[in] A bitmask of flags that controls which component will be finished.</span></span> <span data-ttu-id="2e1ec-109">必须设置以下一个或多个标志:</span><span class="sxs-lookup"><span data-stu-id="2e1ec-109">One or the other of the following flags must be set:</span></span>
    
<span data-ttu-id="2e1ec-110">TNEF_COMPONENT_ATTACHMENT</span><span class="sxs-lookup"><span data-stu-id="2e1ec-110">TNEF_COMPONENT_ATTACHMENT</span></span> 
  
> <span data-ttu-id="2e1ec-111">将完成对附件对象的处理;_ulComponentID_参数包含附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-111">Processing will be finished for an attachment object; the  _ulComponentID_ parameter contains the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property of the attachment.</span></span> 
    
<span data-ttu-id="2e1ec-112">TNEF_COMPONENT_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="2e1ec-112">TNEF_COMPONENT_MESSAGE</span></span> 
  
> <span data-ttu-id="2e1ec-113">将完成对 message 对象的处理。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-113">Processing will be finished for a message object.</span></span> 
    
 <span data-ttu-id="2e1ec-114">_ulComponentID_</span><span class="sxs-lookup"><span data-stu-id="2e1ec-114">_ulComponentID_</span></span>
  
> <span data-ttu-id="2e1ec-115">[输入] 0 指示对邮件的处理, 或要处理的附件的**PR_ATTACH_NUM**属性。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-115">[in] 0 to indicate processing for a message, or the **PR_ATTACH_NUM** property of an attachment to be processed.</span></span> <span data-ttu-id="2e1ec-116">如果在_ulFlags_参数中设置了 TNEF_COMPONENT_MESSAGE 标志, 则_ulComponentID_必须为0。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-116">If the TNEF_COMPONENT_MESSAGE flag is set in the  _ulFlags_ parameter,  _ulComponentID_ must be 0.</span></span> 
    
 <span data-ttu-id="2e1ec-117">_lpCustomPropList_</span><span class="sxs-lookup"><span data-stu-id="2e1ec-117">_lpCustomPropList_</span></span>
  
> <span data-ttu-id="2e1ec-118">实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含用于标识在_lpCustomProps_参数中传递的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-118">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains property tags that identify the properties passed in the  _lpCustomProps_ parameter.</span></span> <span data-ttu-id="2e1ec-119">_lpCustomProps_中的每个属性值与_lpCustomPropList_参数中的一个属性标记之间必须有一对一的对应关系。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-119">There must be a one-to-one correspondence between each property value in  _lpCustomProps_ and a property tag in the  _lpCustomPropList_ parameter.</span></span> 
    
 <span data-ttu-id="2e1ec-120">_lpCustomProps_</span><span class="sxs-lookup"><span data-stu-id="2e1ec-120">_lpCustomProps_</span></span>
  
> <span data-ttu-id="2e1ec-121">实时指向[SPropValue](spropvalue.md)结构的指针, 该结构包含要编码的属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-121">[in] A pointer to an [SPropValue](spropvalue.md) structure that contains property values for the properties to encode.</span></span> 
    
 <span data-ttu-id="2e1ec-122">_lpPropList_</span><span class="sxs-lookup"><span data-stu-id="2e1ec-122">_lpPropList_</span></span>
  
> <span data-ttu-id="2e1ec-123">实时指向**SPropTagArray**结构的指针, 该结构包含要编码的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-123">[in] A pointer to an **SPropTagArray** structure that contains property tags for the properties to encode.</span></span> 
    
 <span data-ttu-id="2e1ec-124">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="2e1ec-124">_lppProblems_</span></span>
  
> <span data-ttu-id="2e1ec-125">排除指向返回的[STnefProblemArray](stnefproblemarray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-125">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="2e1ec-126">**STnefProblemArray**结构指示哪些属性 (如果有) 未正确编码。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-126">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="2e1ec-127">如果在_lppProblems_参数中传递 NULL, 则不返回属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-127">If NULL is passed in the  _lppProblems_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2e1ec-128">返回值</span><span class="sxs-lookup"><span data-stu-id="2e1ec-128">Return value</span></span>

<span data-ttu-id="2e1ec-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e1ec-129">S_OK</span></span> 
  
> <span data-ttu-id="2e1ec-130">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-130">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2e1ec-131">注解</span><span class="sxs-lookup"><span data-stu-id="2e1ec-131">Remarks</span></span>

<span data-ttu-id="2e1ec-132">传输提供程序、邮件存储提供程序和网关调用**ITnef:: FinishComponent**方法, 以执行一个组件 (由_ulFlags_参数中设置的标志所指示) 的 TNEF 处理 (无论是邮件还是附件)。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-132">Transport providers, message store providers, and gateways call the **ITnef::FinishComponent** method to perform TNEF processing for one component, either a message or an attachment, as indicated by the flag set in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="2e1ec-133">若要启用组件处理, 调用提供程序或网关在_ulFlags_中传递打开要接收编码的对象的[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_COMPONENT_ENCODING 标志。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-133">For component processing to be enabled, the calling provider or gateway pass the TNEF_COMPONENT_ENCODING flag in  _ulFlags_ for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function that opened the object to receive encoding.</span></span> 
  
<span data-ttu-id="2e1ec-134">传递_lpCustomPropList_和_lpCustomProps_参数中的值会执行与[ITnef:: SetProps](itnef-setprops.md)方法所执行的组件编码等效的组件编码。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-134">Passing values in the  _lpCustomPropList_ and  _lpCustomProps_ parameters performs component encoding equivalent to that done by the [ITnef::SetProps](itnef-setprops.md) method.</span></span> <span data-ttu-id="2e1ec-135">传递_lpPropList_参数中的值会执行与 ulFlags:: AddProps 方法中的[ITnef::](itnef-addprops.md)方法所做的操作等效的组件编码, 并在__ 中设置 TNEF_PROP_INCLUDE 标志。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-135">Passing a value in the  _lpPropList_ parameter performs component encoding equivalent to that done by the [ITnef::AddProps](itnef-addprops.md) method with the TNEF_PROP_INCLUDE flag set in  _ulFlags_.</span></span> <span data-ttu-id="2e1ec-136">通过传递这些值, 可以执行单个调用 (而不是多个调用) 执行编码。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-136">Passing these values enables you to perform encodings with a single call instead of multiple calls.</span></span>
  
<span data-ttu-id="2e1ec-137">tnef 实现在不停止**FinishComponent**进程的情况下报告 TNEF 流编码问题。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-137">The TNEF implementation reports TNEF stream encoding problems without stopping the **FinishComponent** process.</span></span> <span data-ttu-id="2e1ec-138">_lppProblems_中返回的**STnefProblemArray**结构指示无法处理 TNEF 属性或 MAPI 属性 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-138">The **STnefProblemArray** structure returned in  _lppProblems_ indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="2e1ec-139">在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指出了具体的问题。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-139">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="2e1ec-140">提供程序或网关可以在假定**FinishComponent**未返回问题报告的所有属性或属性已成功处理时进行工作。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-140">The provider or gateway can work on the assumption that all properties or attributes for which **FinishComponent** does not return a problem report were processed successfully.</span></span> 
  
<span data-ttu-id="2e1ec-141">如果提供程序或网关无法处理问题数组, 则它可以在_lppProblems_中传递 NULL;在这种情况下, 不会返回任何问题数组。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-141">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lppProblems_; in this case, no problem array is returned.</span></span>
  
<span data-ttu-id="2e1ec-142">仅当调用返回 S_OK 时, _lppProblems_中返回的值才有效。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-142">The value returned in  _lppProblems_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="2e1ec-143">当返回 S_OK 时, 提供程序或网关应检查[STnefProblemArray](stnefproblemarray.md)结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-143">When S_OK is returned, the provider or gateway should check the values returned in the [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="2e1ec-144">如果调用时出现错误, 则不会填写**STnefProblemArray**结构, 并且调用提供程序或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-144">If an error occurs on the call, the **STnefProblemArray** structure is not filled in, and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="2e1ec-145">如果调用中没有发生错误, 则调用提供程序或网关必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放**STnefProblemArray**的内存。</span><span class="sxs-lookup"><span data-stu-id="2e1ec-145">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2e1ec-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e1ec-146">See also</span></span>



[<span data-ttu-id="2e1ec-147">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="2e1ec-147">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="2e1ec-148">ITnef::SetProps</span><span class="sxs-lookup"><span data-stu-id="2e1ec-148">ITnef::SetProps</span></span>](itnef-setprops.md)
  
[<span data-ttu-id="2e1ec-149">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="2e1ec-149">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="2e1ec-150">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="2e1ec-150">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="2e1ec-151">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="2e1ec-151">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="2e1ec-152">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="2e1ec-152">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="2e1ec-153">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="2e1ec-153">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="2e1ec-154">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2e1ec-154">ITnef : IUnknown</span></span>](itnefiunknown.md)

