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
# <a name="itnefextractprops"></a><span data-ttu-id="011b3-103">ITnef::ExtractProps</span><span class="sxs-lookup"><span data-stu-id="011b3-103">ITnef::ExtractProps</span></span>

  
  
<span data-ttu-id="011b3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="011b3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="011b3-105">从 TNEF 封装中提取属性。</span><span class="sxs-lookup"><span data-stu-id="011b3-105">Extracts the properties from a TNEF encapsulation.</span></span> 
  
```cpp
HRESULT ExtractProps(
  ULONG ulFlags,
  LPSPropTagArray lpPropList,
  LPSTnefProblemArray FAR * lpProblems
);
```

## <a name="parameters"></a><span data-ttu-id="011b3-106">参数</span><span class="sxs-lookup"><span data-stu-id="011b3-106">Parameters</span></span>

 <span data-ttu-id="011b3-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="011b3-107">_ulFlags_</span></span>
  
> <span data-ttu-id="011b3-108">实时用于控制如何对属性进行解码的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="011b3-108">[in] A bitmask of flags that controls how properties are decoded.</span></span> <span data-ttu-id="011b3-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="011b3-109">The following flags can be set:</span></span>
    
<span data-ttu-id="011b3-110">TNEF_PROP_EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="011b3-110">TNEF_PROP_EXCLUDE</span></span> 
  
> <span data-ttu-id="011b3-111">对未在_lpPropList_参数中指定的所有属性进行解码。</span><span class="sxs-lookup"><span data-stu-id="011b3-111">Decodes all properties not specified in the  _lpPropList_ parameter.</span></span> 
    
<span data-ttu-id="011b3-112">TNEF_PROP_INCLUDE</span><span class="sxs-lookup"><span data-stu-id="011b3-112">TNEF_PROP_INCLUDE</span></span> 
  
> <span data-ttu-id="011b3-113">对在_lpPropList_中指定的所有属性进行解码。</span><span class="sxs-lookup"><span data-stu-id="011b3-113">Decodes all properties specified in  _lpPropList_.</span></span>
    
 <span data-ttu-id="011b3-114">_lpPropList_</span><span class="sxs-lookup"><span data-stu-id="011b3-114">_lpPropList_</span></span>
  
> <span data-ttu-id="011b3-115">实时一个指针, 指向要在解码操作中包含或排除的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="011b3-115">[in] A pointer to the list of properties to include in or exclude from the decoding operation.</span></span>
    
 <span data-ttu-id="011b3-116">_lpProblems_</span><span class="sxs-lookup"><span data-stu-id="011b3-116">_lpProblems_</span></span>
  
> <span data-ttu-id="011b3-117">排除指向返回的[STnefProblemArray](stnefproblemarray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="011b3-117">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="011b3-118">**STnefProblemArray**结构指示哪些属性 (如果有) 未正确编码。</span><span class="sxs-lookup"><span data-stu-id="011b3-118">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="011b3-119">如果在_lpProblems_参数中传递 NULL, 则不返回属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="011b3-119">If NULL is passed in the  _lpProblems_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="011b3-120">返回值</span><span class="sxs-lookup"><span data-stu-id="011b3-120">Return value</span></span>

<span data-ttu-id="011b3-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="011b3-121">S_OK</span></span> 
  
> <span data-ttu-id="011b3-122">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="011b3-122">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="011b3-123">MAPI_E_CORRUPT_DATA</span><span class="sxs-lookup"><span data-stu-id="011b3-123">MAPI_E_CORRUPT_DATA</span></span> 
  
> <span data-ttu-id="011b3-124">解码为流的数据已损坏。</span><span class="sxs-lookup"><span data-stu-id="011b3-124">Data being decoded into a stream is corrupted.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="011b3-125">说明</span><span class="sxs-lookup"><span data-stu-id="011b3-125">Remarks</span></span>

<span data-ttu-id="011b3-126">传输提供程序、邮件存储提供程序和网关调用**ITnef:: ExtractProps**方法从传递给[OpenTnefStream](opentnefstream.md)函数的邮件或附件的封装中提取 (即解码) 属性。</span><span class="sxs-lookup"><span data-stu-id="011b3-126">Transport providers, message store providers, and gateways call the **ITnef::ExtractProps** method to extract (that is, decode) properties from the encapsulation of a message or an attachment that was passed to the [OpenTnefStream](opentnefstream.md) function.</span></span> <span data-ttu-id="011b3-127">调用提供程序或网关可以指定要解码的属性列表。</span><span class="sxs-lookup"><span data-stu-id="011b3-127">The calling provider or gateway can specify a list of properties to decode.</span></span> <span data-ttu-id="011b3-128">提供程序和网关也可以使用**ExtractProps**来提供有关附件的任何特殊处理的信息。</span><span class="sxs-lookup"><span data-stu-id="011b3-128">Providers and gateways can also use **ExtractProps** to provide information about any special handling for attachments.</span></span> 
  
 <span data-ttu-id="011b3-129">**ExtractProps**使用已解码的属性填充传递给**OpenTnefStream**的原始邮件。</span><span class="sxs-lookup"><span data-stu-id="011b3-129">**ExtractProps** populates the original message passed into **OpenTnefStream** with the decoded properties.</span></span> <span data-ttu-id="011b3-130">随后的**ExtractProps**调用将返回到邮件并提取新的属性列表。</span><span class="sxs-lookup"><span data-stu-id="011b3-130">Subsequent **ExtractProps** calls go back to the message and extract the new list of properties.</span></span> 
  
<span data-ttu-id="011b3-131">与[ITnef:: AddProps](itnef-addprops.md)方法 (该方法在调用**ITnef:: Finish**方法之前对所请求的操作进行排队) 不同, **ExtractProps**方法会在调用时立即对封装的属性进行解码。</span><span class="sxs-lookup"><span data-stu-id="011b3-131">Unlike the [ITnef::AddProps](itnef-addprops.md) method, which queues requested actions until the **ITnef::Finish** method is called, the **ExtractProps** method decodes the encapsulated properties immediately when it is called.</span></span> <span data-ttu-id="011b3-132">因此, 封装解码的目标邮件应相对空。</span><span class="sxs-lookup"><span data-stu-id="011b3-132">For that reason, the target message for encapsulation decoding should be relatively empty.</span></span> <span data-ttu-id="011b3-133">目标邮件中的现有属性将被封装属性覆盖。</span><span class="sxs-lookup"><span data-stu-id="011b3-133">Existing properties in the target message are overwritten by encapsulated properties.</span></span> 
  
 <span data-ttu-id="011b3-134">仅在使用**OpenTnefStream**或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_DECODE 标志打开的对象中, 才支持**ExtractProps** 。</span><span class="sxs-lookup"><span data-stu-id="011b3-134">**ExtractProps** is supported only for objects that are opened with the TNEF_DECODE flag for the **OpenTnefStream** or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
  
<span data-ttu-id="011b3-135">tnef 实现在不停止**ExtractProps**进程的情况下报告 TNEF 流编码问题。</span><span class="sxs-lookup"><span data-stu-id="011b3-135">The TNEF implementation reports TNEF stream encoding problems without stopping the **ExtractProps** process.</span></span> <span data-ttu-id="011b3-136">_lpProblems_中返回的[STnefProblemArray](stnefproblemarray.md)结构指示无法处理 TNEF 属性或 MAPI 属性 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="011b3-136">The [STnefProblemArray](stnefproblemarray.md) structure returned in  _lpProblems_ indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="011b3-137">在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指出了具体的问题。</span><span class="sxs-lookup"><span data-stu-id="011b3-137">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="011b3-138">提供程序或网关可以在假定**ExtractProps**未返回问题报告的所有属性或属性已成功处理时进行工作。</span><span class="sxs-lookup"><span data-stu-id="011b3-138">The provider or gateway can work on the assumption that all properties or attributes for which **ExtractProps** does not return a problem report were processed successfully.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="011b3-139">如果无法处理 MAPI 封装块中的某个属性, 并且在解码 TNEF 流的过程中使该流不可靠, 则会停止对封装块进行解码, 并报告问题。</span><span class="sxs-lookup"><span data-stu-id="011b3-139">If a property in the MAPI encapsulation block cannot be processed and leaves the stream unreliable during the decoding of a TNEF stream, decoding of the encapsulation block is stopped and a problem is reported.</span></span> <span data-ttu-id="011b3-140">此类问题的问题数组中`attMAPIProps` `attAttachment`包含**ulPropTag**成员的0L 或**ulAttribute**成员的问题, 以及**scode**成员的 MAPI_E_UNABLE_TO_COMPLETE。</span><span class="sxs-lookup"><span data-stu-id="011b3-140">The problem array for this type of problem contains 0L for the **ulPropTag** member,  `attMAPIProps` or  `attAttachment` for the **ulAttribute** member, and MAPI_E_UNABLE_TO_COMPLETE for the **scode** member.</span></span> <span data-ttu-id="011b3-141">请注意, 流的解码不会暂停, 只是对 MAPI 封装块进行解码。</span><span class="sxs-lookup"><span data-stu-id="011b3-141">Note that the decoding of the stream is not halted, just the decoding of the MAPI encapsulation block.</span></span> <span data-ttu-id="011b3-142">流解码将继续进行下一个属性块。</span><span class="sxs-lookup"><span data-stu-id="011b3-142">The stream decoding continues with the next attribute block.</span></span> 
  
<span data-ttu-id="011b3-143">如果提供程序或网关无法处理问题数组, 则它可以在_lppProblems_中传递 NULL;在这种情况下, 不会返回任何问题数组。</span><span class="sxs-lookup"><span data-stu-id="011b3-143">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lppProblems_; in this case, no problem array is returned.</span></span> 
  
<span data-ttu-id="011b3-144">仅当调用返回 S_OK 时, _lpProblems_中返回的值才有效。</span><span class="sxs-lookup"><span data-stu-id="011b3-144">The value returned in  _lpProblems_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="011b3-145">当返回 S_OK 时, 提供程序或网关应检查**STnefProblemArray**结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="011b3-145">When S_OK is returned, the provider or gateway should check the values returned in the **STnefProblemArray** structure.</span></span> <span data-ttu-id="011b3-146">如果调用时出现错误, 则不会填写**STnefProblemArray**结构, 并且调用提供程序或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="011b3-146">If an error occurs on the call, the **STnefProblemArray** structure is not filled in and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="011b3-147">如果调用中没有发生错误, 则调用提供程序或网关必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放**STnefProblemArray**结构的内存。</span><span class="sxs-lookup"><span data-stu-id="011b3-147">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="011b3-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="011b3-148">See also</span></span>



[<span data-ttu-id="011b3-149">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="011b3-149">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="011b3-150">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="011b3-150">ITnef::Finish</span></span>](itnef-finish.md)
  
[<span data-ttu-id="011b3-151">ITnef::SetProps</span><span class="sxs-lookup"><span data-stu-id="011b3-151">ITnef::SetProps</span></span>](itnef-setprops.md)
  
[<span data-ttu-id="011b3-152">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="011b3-152">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="011b3-153">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="011b3-153">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="011b3-154">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="011b3-154">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="011b3-155">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="011b3-155">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="011b3-156">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="011b3-156">ITnef : IUnknown</span></span>](itnefiunknown.md)

