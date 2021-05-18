---
title: ITnefExtractProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.ExtractProps
api_type:
- COM
ms.assetid: 9169a5be-21dd-4938-8db3-522bea165c92
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a01c65bbec061248537558257c66d1a90128b5e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407499"
---
# <a name="itnefextractprops"></a><span data-ttu-id="95a87-103">ITnef::ExtractProps</span><span class="sxs-lookup"><span data-stu-id="95a87-103">ITnef::ExtractProps</span></span>

  
  
<span data-ttu-id="95a87-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95a87-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95a87-105">从 TNEF 封装中提取属性。</span><span class="sxs-lookup"><span data-stu-id="95a87-105">Extracts the properties from a TNEF encapsulation.</span></span> 
  
```cpp
HRESULT ExtractProps(
  ULONG ulFlags,
  LPSPropTagArray lpPropList,
  LPSTnefProblemArray FAR * lpProblems
);
```

## <a name="parameters"></a><span data-ttu-id="95a87-106">参数</span><span class="sxs-lookup"><span data-stu-id="95a87-106">Parameters</span></span>

 <span data-ttu-id="95a87-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="95a87-107">_ulFlags_</span></span>
  
> <span data-ttu-id="95a87-108">[in]控制属性解码方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="95a87-108">[in] A bitmask of flags that controls how properties are decoded.</span></span> <span data-ttu-id="95a87-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="95a87-109">The following flags can be set:</span></span>
    
<span data-ttu-id="95a87-110">TNEF_PROP_EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="95a87-110">TNEF_PROP_EXCLUDE</span></span> 
  
> <span data-ttu-id="95a87-111">解码  _lpPropList_ 参数中未指定的所有属性。</span><span class="sxs-lookup"><span data-stu-id="95a87-111">Decodes all properties not specified in the  _lpPropList_ parameter.</span></span> 
    
<span data-ttu-id="95a87-112">TNEF_PROP_INCLUDE</span><span class="sxs-lookup"><span data-stu-id="95a87-112">TNEF_PROP_INCLUDE</span></span> 
  
> <span data-ttu-id="95a87-113">解码在  _lpPropList 中指定的所有属性_。</span><span class="sxs-lookup"><span data-stu-id="95a87-113">Decodes all properties specified in  _lpPropList_.</span></span>
    
 <span data-ttu-id="95a87-114">_lpPropList_</span><span class="sxs-lookup"><span data-stu-id="95a87-114">_lpPropList_</span></span>
  
> <span data-ttu-id="95a87-115">[in]指向要包括在解码操作中或从解码操作中排除的属性列表的指针。</span><span class="sxs-lookup"><span data-stu-id="95a87-115">[in] A pointer to the list of properties to include in or exclude from the decoding operation.</span></span>
    
 <span data-ttu-id="95a87-116">_lpProblems_</span><span class="sxs-lookup"><span data-stu-id="95a87-116">_lpProblems_</span></span>
  
> <span data-ttu-id="95a87-117">[out]指向返回的 [STnefProblemArray 结构的指针的](stnefproblemarray.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="95a87-117">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="95a87-118">**STnefProblemArray** 结构指示哪些属性（如果有）未正确编码。</span><span class="sxs-lookup"><span data-stu-id="95a87-118">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="95a87-119">如果在  _lpProblems_ 参数中传递 NULL，则不返回任何属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="95a87-119">If NULL is passed in the  _lpProblems_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="95a87-120">返回值</span><span class="sxs-lookup"><span data-stu-id="95a87-120">Return value</span></span>

<span data-ttu-id="95a87-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="95a87-121">S_OK</span></span> 
  
> <span data-ttu-id="95a87-122">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="95a87-122">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="95a87-123">MAPI_E_CORRUPT_DATA</span><span class="sxs-lookup"><span data-stu-id="95a87-123">MAPI_E_CORRUPT_DATA</span></span> 
  
> <span data-ttu-id="95a87-124">解码为流的数据已损坏。</span><span class="sxs-lookup"><span data-stu-id="95a87-124">Data being decoded into a stream is corrupted.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="95a87-125">备注</span><span class="sxs-lookup"><span data-stu-id="95a87-125">Remarks</span></span>

<span data-ttu-id="95a87-126">传输提供程序、邮件存储提供程序和网关调用 **ITnef：：ExtractProps** 方法来提取 (，即从传递到 [OpenTnefStream](opentnefstream.md) 函数的邮件或附件的封装中解码) 属性。</span><span class="sxs-lookup"><span data-stu-id="95a87-126">Transport providers, message store providers, and gateways call the **ITnef::ExtractProps** method to extract (that is, decode) properties from the encapsulation of a message or an attachment that was passed to the [OpenTnefStream](opentnefstream.md) function.</span></span> <span data-ttu-id="95a87-127">呼叫提供商或网关可以指定要解码的属性列表。</span><span class="sxs-lookup"><span data-stu-id="95a87-127">The calling provider or gateway can specify a list of properties to decode.</span></span> <span data-ttu-id="95a87-128">提供程序和网关还可使用 **ExtractProps** 提供有关附件的任何特殊处理的信息。</span><span class="sxs-lookup"><span data-stu-id="95a87-128">Providers and gateways can also use **ExtractProps** to provide information about any special handling for attachments.</span></span> 
  
 <span data-ttu-id="95a87-129">**ExtractProps** 使用解码的属性填充传递到 **OpenTnefStream** 的原始消息。</span><span class="sxs-lookup"><span data-stu-id="95a87-129">**ExtractProps** populates the original message passed into **OpenTnefStream** with the decoded properties.</span></span> <span data-ttu-id="95a87-130">后续 **的 ExtractProps** 调用将返回到邮件并提取新的属性列表。</span><span class="sxs-lookup"><span data-stu-id="95a87-130">Subsequent **ExtractProps** calls go back to the message and extract the new list of properties.</span></span> 
  
<span data-ttu-id="95a87-131">与 [ITnef：：AddProps](itnef-addprops.md) 方法不同，该方法在 **调用 ITnef：：Finish** 方法之前对请求的操作进行排队，而 **ExtractProps** 方法在调用它时会立即对封装的属性进行解码。</span><span class="sxs-lookup"><span data-stu-id="95a87-131">Unlike the [ITnef::AddProps](itnef-addprops.md) method, which queues requested actions until the **ITnef::Finish** method is called, the **ExtractProps** method decodes the encapsulated properties immediately when it is called.</span></span> <span data-ttu-id="95a87-132">因此，封装解码的目标消息应相对空白。</span><span class="sxs-lookup"><span data-stu-id="95a87-132">For that reason, the target message for encapsulation decoding should be relatively empty.</span></span> <span data-ttu-id="95a87-133">目标邮件中的现有属性被封装属性覆盖。</span><span class="sxs-lookup"><span data-stu-id="95a87-133">Existing properties in the target message are overwritten by encapsulated properties.</span></span> 
  
 <span data-ttu-id="95a87-134">只有使用 **OpenTnefStream 或 OpenTnefStreamEx** 函数的 TNEF_DECODE 标志打开的对象 [](opentnefstreamex.md)才支持 **ExtractProps。**</span><span class="sxs-lookup"><span data-stu-id="95a87-134">**ExtractProps** is supported only for objects that are opened with the TNEF_DECODE flag for the **OpenTnefStream** or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
  
<span data-ttu-id="95a87-135">TNEF 实现报告 TNEF 流编码问题，而不停止 **ExtractProps** 进程。</span><span class="sxs-lookup"><span data-stu-id="95a87-135">The TNEF implementation reports TNEF stream encoding problems without stopping the **ExtractProps** process.</span></span> <span data-ttu-id="95a87-136">_lpProblems_ 中返回的 [STnefProblemArray](stnefproblemarray.md)结构指示无法处理哪些 TNEF 属性或 MAPI 属性（如果有）。</span><span class="sxs-lookup"><span data-stu-id="95a87-136">The [STnefProblemArray](stnefproblemarray.md) structure returned in  _lpProblems_ indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="95a87-137">**STnefProblemArray** 中包含的 **STnefProblem** 结构之一的 **scode** 成员中返回的值指示特定问题。</span><span class="sxs-lookup"><span data-stu-id="95a87-137">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="95a87-138">提供商或网关可以假定 **ExtractProps** 未返回问题报告的所有属性或属性都已成功处理。</span><span class="sxs-lookup"><span data-stu-id="95a87-138">The provider or gateway can work on the assumption that all properties or attributes for which **ExtractProps** does not return a problem report were processed successfully.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="95a87-139">如果在 TNEF 流解码期间无法处理 MAPI 封装块中的属性，并且流不可靠，将停止封装块的解码并报告问题。</span><span class="sxs-lookup"><span data-stu-id="95a87-139">If a property in the MAPI encapsulation block cannot be processed and leaves the stream unreliable during the decoding of a TNEF stream, decoding of the encapsulation block is stopped and a problem is reported.</span></span> <span data-ttu-id="95a87-140">此类型的问题的问题数组包含 **ulPropTag** 成员或 `attMAPIProps` `attAttachment` **ulAttribute** 成员为 0L，而 scode 成员MAPI_E_UNABLE_TO_COMPLETE为 **0L。**</span><span class="sxs-lookup"><span data-stu-id="95a87-140">The problem array for this type of problem contains 0L for the **ulPropTag** member,  `attMAPIProps` or  `attAttachment` for the **ulAttribute** member, and MAPI_E_UNABLE_TO_COMPLETE for the **scode** member.</span></span> <span data-ttu-id="95a87-141">请注意，流解码不会停止，只是对 MAPI 封装块的解码。</span><span class="sxs-lookup"><span data-stu-id="95a87-141">Note that the decoding of the stream is not halted, just the decoding of the MAPI encapsulation block.</span></span> <span data-ttu-id="95a87-142">流解码将继续处理下一个属性块。</span><span class="sxs-lookup"><span data-stu-id="95a87-142">The stream decoding continues with the next attribute block.</span></span> 
  
<span data-ttu-id="95a87-143">如果提供程序或网关不处理问题数组，它可以在  _lppProblems_ 中传递 NULL;在这种情况下，不会返回问题数组。</span><span class="sxs-lookup"><span data-stu-id="95a87-143">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lppProblems_; in this case, no problem array is returned.</span></span> 
  
<span data-ttu-id="95a87-144">_lpProblems_ 中返回的值仅在调用返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="95a87-144">The value returned in  _lpProblems_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="95a87-145">返回S_OK时，提供商或网关应检查 **STnefProblemArray** 结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="95a87-145">When S_OK is returned, the provider or gateway should check the values returned in the **STnefProblemArray** structure.</span></span> <span data-ttu-id="95a87-146">如果呼叫出错， **则 STnefProblemArray** 结构不会填充，并且调用提供程序或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="95a87-146">If an error occurs on the call, the **STnefProblemArray** structure is not filled in and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="95a87-147">如果呼叫中未发生错误，则调用提供程序或网关必须通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放 **STnefProblemArray** 结构的内存。</span><span class="sxs-lookup"><span data-stu-id="95a87-147">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="95a87-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95a87-148">See also</span></span>



[<span data-ttu-id="95a87-149">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="95a87-149">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="95a87-150">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="95a87-150">ITnef::Finish</span></span>](itnef-finish.md)
  
[<span data-ttu-id="95a87-151">ITnef::SetProps</span><span class="sxs-lookup"><span data-stu-id="95a87-151">ITnef::SetProps</span></span>](itnef-setprops.md)
  
[<span data-ttu-id="95a87-152">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="95a87-152">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="95a87-153">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="95a87-153">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="95a87-154">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="95a87-154">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="95a87-155">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="95a87-155">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="95a87-156">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="95a87-156">ITnef : IUnknown</span></span>](itnefiunknown.md)

