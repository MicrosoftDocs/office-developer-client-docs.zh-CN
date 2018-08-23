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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0765e46a6f0545682b16e484d08d296ea13e2136
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571344"
---
# <a name="itnefextractprops"></a><span data-ttu-id="921e8-103">ITnef::ExtractProps</span><span class="sxs-lookup"><span data-stu-id="921e8-103">ITnef::ExtractProps</span></span>

  
  
<span data-ttu-id="921e8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="921e8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="921e8-105">从 TNEF 封装提取属性。</span><span class="sxs-lookup"><span data-stu-id="921e8-105">Extracts the properties from a TNEF encapsulation.</span></span> 
  
```cpp
HRESULT ExtractProps(
  ULONG ulFlags,
  LPSPropTagArray lpPropList,
  LPSTnefProblemArray FAR * lpProblems
);
```

## <a name="parameters"></a><span data-ttu-id="921e8-106">参数</span><span class="sxs-lookup"><span data-stu-id="921e8-106">Parameters</span></span>

 <span data-ttu-id="921e8-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="921e8-107">_ulFlags_</span></span>
  
> <span data-ttu-id="921e8-108">[in]位掩码的标志，控制如何能够解码属性。</span><span class="sxs-lookup"><span data-stu-id="921e8-108">[in] A bitmask of flags that controls how properties are decoded.</span></span> <span data-ttu-id="921e8-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="921e8-109">The following flags can be set:</span></span>
    
<span data-ttu-id="921e8-110">TNEF_PROP_EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="921e8-110">TNEF_PROP_EXCLUDE</span></span> 
  
> <span data-ttu-id="921e8-111">解码未在_lpPropList_参数中指定的所有属性。</span><span class="sxs-lookup"><span data-stu-id="921e8-111">Decodes all properties not specified in the  _lpPropList_ parameter.</span></span> 
    
<span data-ttu-id="921e8-112">TNEF_PROP_INCLUDE</span><span class="sxs-lookup"><span data-stu-id="921e8-112">TNEF_PROP_INCLUDE</span></span> 
  
> <span data-ttu-id="921e8-113">解码_lpPropList_中指定的所有属性。</span><span class="sxs-lookup"><span data-stu-id="921e8-113">Decodes all properties specified in  _lpPropList_.</span></span>
    
 <span data-ttu-id="921e8-114">_lpPropList_</span><span class="sxs-lookup"><span data-stu-id="921e8-114">_lpPropList_</span></span>
  
> <span data-ttu-id="921e8-115">[in]一个指向属性中包含或排除解码操作的列表。</span><span class="sxs-lookup"><span data-stu-id="921e8-115">[in] A pointer to the list of properties to include in or exclude from the decoding operation.</span></span>
    
 <span data-ttu-id="921e8-116">_lpProblems_</span><span class="sxs-lookup"><span data-stu-id="921e8-116">_lpProblems_</span></span>
  
> <span data-ttu-id="921e8-117">[输出]指向返回[STnefProblemArray](stnefproblemarray.md)结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="921e8-117">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="921e8-118">**STnefProblemArray**结构表明哪些属性中，如果有，已未编码的正确。</span><span class="sxs-lookup"><span data-stu-id="921e8-118">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="921e8-119">如果_lpProblems_参数中传递了 NULL，则返回没有属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="921e8-119">If NULL is passed in the  _lpProblems_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="921e8-120">返回值</span><span class="sxs-lookup"><span data-stu-id="921e8-120">Return value</span></span>

<span data-ttu-id="921e8-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="921e8-121">S_OK</span></span> 
  
> <span data-ttu-id="921e8-122">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="921e8-122">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="921e8-123">MAPI_E_CORRUPT_DATA</span><span class="sxs-lookup"><span data-stu-id="921e8-123">MAPI_E_CORRUPT_DATA</span></span> 
  
> <span data-ttu-id="921e8-124">正在为流解码的数据已损坏。</span><span class="sxs-lookup"><span data-stu-id="921e8-124">Data being decoded into a stream is corrupted.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="921e8-125">注解</span><span class="sxs-lookup"><span data-stu-id="921e8-125">Remarks</span></span>

<span data-ttu-id="921e8-126">传输提供程序、 消息存储提供程序，和网关调用**ITnef::ExtractProps**方法以提取 （即，解码） 从邮件或附件已传递给[OpenTnefStream](opentnefstream.md)函数封装的属性。</span><span class="sxs-lookup"><span data-stu-id="921e8-126">Transport providers, message store providers, and gateways call the **ITnef::ExtractProps** method to extract (that is, decode) properties from the encapsulation of a message or an attachment that was passed to the [OpenTnefStream](opentnefstream.md) function.</span></span> <span data-ttu-id="921e8-127">呼叫提供商或网关可以指定要解码属性的列表。</span><span class="sxs-lookup"><span data-stu-id="921e8-127">The calling provider or gateway can specify a list of properties to decode.</span></span> <span data-ttu-id="921e8-128">提供程序和网关还可以使用**ExtractProps**提供信息的附件的任何特殊处理。</span><span class="sxs-lookup"><span data-stu-id="921e8-128">Providers and gateways can also use **ExtractProps** to provide information about any special handling for attachments.</span></span> 
  
 <span data-ttu-id="921e8-129">**ExtractProps**填充原始邮件传递到**OpenTnefStream**具有已解码的属性。</span><span class="sxs-lookup"><span data-stu-id="921e8-129">**ExtractProps** populates the original message passed into **OpenTnefStream** with the decoded properties.</span></span> <span data-ttu-id="921e8-130">后续**ExtractProps**调用返回到邮件并提取的属性的新列表。</span><span class="sxs-lookup"><span data-stu-id="921e8-130">Subsequent **ExtractProps** calls go back to the message and extract the new list of properties.</span></span> 
  
<span data-ttu-id="921e8-131">与[ITnef::AddProps](itnef-addprops.md)方法，调用**ITnef::Finish**方法之前，队列将请求操作，不同**ExtractProps**方法在被调用时立即解码封装的属性。</span><span class="sxs-lookup"><span data-stu-id="921e8-131">Unlike the [ITnef::AddProps](itnef-addprops.md) method, which queues requested actions until the **ITnef::Finish** method is called, the **ExtractProps** method decodes the encapsulated properties immediately when it is called.</span></span> <span data-ttu-id="921e8-132">因此，用于封装解码的目标消息应为相对空。</span><span class="sxs-lookup"><span data-stu-id="921e8-132">For that reason, the target message for encapsulation decoding should be relatively empty.</span></span> <span data-ttu-id="921e8-133">通过封装属性来覆盖目标邮件中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="921e8-133">Existing properties in the target message are overwritten by encapsulated properties.</span></span> 
  
 <span data-ttu-id="921e8-134">**ExtractProps**仅支持使用 TNEF_DECODE 标志**OpenTnefStream**或[OpenTnefStreamEx](opentnefstreamex.md)函数打开的对象。</span><span class="sxs-lookup"><span data-stu-id="921e8-134">**ExtractProps** is supported only for objects that are opened with the TNEF_DECODE flag for the **OpenTnefStream** or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
  
<span data-ttu-id="921e8-135">TNEF 实现报告而不停止**ExtractProps**进程 TNEF 流编码问题。</span><span class="sxs-lookup"><span data-stu-id="921e8-135">The TNEF implementation reports TNEF stream encoding problems without stopping the **ExtractProps** process.</span></span> <span data-ttu-id="921e8-136">返回在_lpProblems_ [STnefProblemArray](stnefproblemarray.md)结构指示哪些 TNEF 属性或 MAPI 属性，如果有，无法进行处理。</span><span class="sxs-lookup"><span data-stu-id="921e8-136">The [STnefProblemArray](stnefproblemarray.md) structure returned in  _lpProblems_ indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="921e8-137">在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指示特定问题。</span><span class="sxs-lookup"><span data-stu-id="921e8-137">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="921e8-138">所有属性或特性**ExtractProps**不会返回问题报告都已成功都处理假定可以处理提供程序或网关。</span><span class="sxs-lookup"><span data-stu-id="921e8-138">The provider or gateway can work on the assumption that all properties or attributes for which **ExtractProps** does not return a problem report were processed successfully.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="921e8-139">如果 MAPI 封装块中的属性不能处理，并保持流解码 TNEF 流过程不可靠，解码封装块的已停止并报告问题。</span><span class="sxs-lookup"><span data-stu-id="921e8-139">If a property in the MAPI encapsulation block cannot be processed and leaves the stream unreliable during the decoding of a TNEF stream, decoding of the encapsulation block is stopped and a problem is reported.</span></span> <span data-ttu-id="921e8-140">此类型的问题的问题数组包含 0 L **ulPropTag**成员，`attMAPIProps`或`attAttachment` **ulAttribute**成员和 MAPI_E_UNABLE_TO_COMPLETE **scode**成员。</span><span class="sxs-lookup"><span data-stu-id="921e8-140">The problem array for this type of problem contains 0L for the **ulPropTag** member,  `attMAPIProps` or  `attAttachment` for the **ulAttribute** member, and MAPI_E_UNABLE_TO_COMPLETE for the **scode** member.</span></span> <span data-ttu-id="921e8-141">请注意，流的解码不停止，只需解码的 MAPI 封装块。</span><span class="sxs-lookup"><span data-stu-id="921e8-141">Note that the decoding of the stream is not halted, just the decoding of the MAPI encapsulation block.</span></span> <span data-ttu-id="921e8-142">流解码继续下一个属性块。</span><span class="sxs-lookup"><span data-stu-id="921e8-142">The stream decoding continues with the next attribute block.</span></span> 
  
<span data-ttu-id="921e8-143">如果提供程序或网关不适用于问题数组，它可以在_lppProblems_; 传递 NULL在这种情况下，则返回没有问题数组。</span><span class="sxs-lookup"><span data-stu-id="921e8-143">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lppProblems_; in this case, no problem array is returned.</span></span> 
  
<span data-ttu-id="921e8-144">仅当呼叫，则返回 S_OK 有效_lpProblems_中返回的值。</span><span class="sxs-lookup"><span data-stu-id="921e8-144">The value returned in  _lpProblems_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="921e8-145">返回 S_OK 时，提供程序或网关应检查**STnefProblemArray**结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="921e8-145">When S_OK is returned, the provider or gateway should check the values returned in the **STnefProblemArray** structure.</span></span> <span data-ttu-id="921e8-146">如果在调用出错， **STnefProblemArray**结构未填写并调用提供程序或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="921e8-146">If an error occurs on the call, the **STnefProblemArray** structure is not filled in and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="921e8-147">如果在调用不产生任何错误，呼叫提供商或网关必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放**STnefProblemArray**结构的内存。</span><span class="sxs-lookup"><span data-stu-id="921e8-147">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="921e8-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="921e8-148">See also</span></span>



[<span data-ttu-id="921e8-149">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="921e8-149">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="921e8-150">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="921e8-150">ITnef::Finish</span></span>](itnef-finish.md)
  
[<span data-ttu-id="921e8-151">ITnef::SetProps</span><span class="sxs-lookup"><span data-stu-id="921e8-151">ITnef::SetProps</span></span>](itnef-setprops.md)
  
[<span data-ttu-id="921e8-152">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="921e8-152">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="921e8-153">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="921e8-153">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="921e8-154">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="921e8-154">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="921e8-155">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="921e8-155">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="921e8-156">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="921e8-156">ITnef : IUnknown</span></span>](itnefiunknown.md)

