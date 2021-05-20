---
title: ITnefFinish
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.Finish
api_type:
- COM
ms.assetid: 01a868f4-afda-43ba-bc17-c33ae56b7b7d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5b76f9daec89e9229fc7f81e1332c3075c951067
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435675"
---
# <a name="itneffinish"></a><span data-ttu-id="b783b-103">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="b783b-103">ITnef::Finish</span></span>

  
  
<span data-ttu-id="b783b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b783b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b783b-105">完成 TNEF 中Transport-Neutral和 (TNEF) 封装格式的处理。</span><span class="sxs-lookup"><span data-stu-id="b783b-105">Finishes processing for all Transport-Neutral Encapsulation Format (TNEF) operations that are queued and waiting.</span></span> 
  
```cpp
HRESULT Finish(
  ULONG ulFlags,
  WORD FAR * lpKey,
  LPSTnefProblemArray FAR * lpProblem
);
```

## <a name="parameters"></a><span data-ttu-id="b783b-106">参数</span><span class="sxs-lookup"><span data-stu-id="b783b-106">Parameters</span></span>

 <span data-ttu-id="b783b-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b783b-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b783b-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="b783b-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="b783b-109">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="b783b-109">_lpKey_</span></span>
  
> <span data-ttu-id="b783b-110">[out]指向附件PR_ATTACH_NUM ( [PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 键属性的指针。</span><span class="sxs-lookup"><span data-stu-id="b783b-110">[out] A pointer to the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) key property of an attachment.</span></span> <span data-ttu-id="b783b-111">TNEF 封装对象使用此键将附件与邮件中的附件放置标记相匹配。</span><span class="sxs-lookup"><span data-stu-id="b783b-111">The TNEF encapsulation object uses this key to match an attachment to its attachment placement tag in a message.</span></span> <span data-ttu-id="b783b-112">此键应对于每个附件是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b783b-112">This key should be unique to each attachment.</span></span>
    
 <span data-ttu-id="b783b-113">_lpProblem_</span><span class="sxs-lookup"><span data-stu-id="b783b-113">_lpProblem_</span></span>
  
> <span data-ttu-id="b783b-114">[out]指向返回的 [STnefProblemArray 结构的指针的](stnefproblemarray.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="b783b-114">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="b783b-115">**STnefProblemArray** 结构指示哪些属性（如果有）未正确编码。</span><span class="sxs-lookup"><span data-stu-id="b783b-115">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="b783b-116">如果在  _lpProblem_ 参数中传递 NULL，则不返回任何属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="b783b-116">If NULL is passed in the  _lpProblem_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b783b-117">返回值</span><span class="sxs-lookup"><span data-stu-id="b783b-117">Return value</span></span>

<span data-ttu-id="b783b-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="b783b-118">S_OK</span></span> 
  
> <span data-ttu-id="b783b-119">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="b783b-119">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b783b-120">备注</span><span class="sxs-lookup"><span data-stu-id="b783b-120">Remarks</span></span>

<span data-ttu-id="b783b-121">传输提供程序、邮件存储提供程序和网关调用 **ITnef：：Finish** 方法，以执行对 [ITnef：：AddProps](itnef-addprops.md) 和 [ITnef：：SetProps](itnef-setprops.md) 方法的调用中请求编码的所有属性的编码。</span><span class="sxs-lookup"><span data-stu-id="b783b-121">Transport providers, message store providers, and gateways call the **ITnef::Finish** method to perform the encoding of all properties for which encoding was requested in calls to the [ITnef::AddProps](itnef-addprops.md) and [ITnef::SetProps](itnef-setprops.md) methods.</span></span> <span data-ttu-id="b783b-122">如果 TNEF 对象是使用 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md)函数的 TNEF_ENCODE 标志打开的，**则 Finish** 方法将请求的属性编码为传递给该对象的封装流。 [](opentnefstreamex.md)</span><span class="sxs-lookup"><span data-stu-id="b783b-122">If the TNEF object was opened with the TNEF_ENCODE flag for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function, the **Finish** method encodes the requested properties into the encapsulation stream passed to that object.</span></span> <span data-ttu-id="b783b-123">如果 TNEF 对象是使用 TNEF_DECODE 标志打开的 **，Finish** 方法将解码 TNEF 流中的属性，并写回它们所属的消息。</span><span class="sxs-lookup"><span data-stu-id="b783b-123">If the TNEF object was opened with the TNEF_DECODE flag, the **Finish** method decodes the properties from the TNEF stream and writes them back to the message they belong to.</span></span> 
  
<span data-ttu-id="b783b-124">完成 **调用** 后，指向封装流的指针指向 TNEF 数据的末尾。</span><span class="sxs-lookup"><span data-stu-id="b783b-124">After the **Finish** call, the pointer to the encapsulation stream points to the end of the TNEF data.</span></span> <span data-ttu-id="b783b-125">如果提供商或网关需要在 **Finish** 调用后使用 TNEF 流数据，则必须将流指针重置为 TNEF 流数据的开头。</span><span class="sxs-lookup"><span data-stu-id="b783b-125">If the provider or gateway needs to use the TNEF stream data after the **Finish** call, it must reset the stream pointer to the beginning of the TNEF stream data.</span></span> 
  
<span data-ttu-id="b783b-126">TNEF 实现报告 TNEF 流编码问题，而不停止 **Finish** 过程。</span><span class="sxs-lookup"><span data-stu-id="b783b-126">The TNEF implementation reports TNEF stream encoding problems without stopping the **Finish** process.</span></span> <span data-ttu-id="b783b-127">_lpProblem_ 参数中返回的 [STnefProblemArray](stnefproblemarray.md)结构指示无法处理哪些 TNEF 属性或 MAPI 属性（如果有）。</span><span class="sxs-lookup"><span data-stu-id="b783b-127">The [STnefProblemArray](stnefproblemarray.md) structure returned in the  _lpProblem_ parameter indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="b783b-128">**STnefProblemArray** 中包含的 **STnefProblem** 结构之一的 **scode** 成员中返回的值指示特定问题。</span><span class="sxs-lookup"><span data-stu-id="b783b-128">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="b783b-129">提供商或网关可以基于以下假设工作 **：Finish** 不返回问题报告的所有属性或属性都已成功处理。</span><span class="sxs-lookup"><span data-stu-id="b783b-129">The provider or gateway can work on the assumption that all properties or attributes for which **Finish** does not return a problem report were processed successfully.</span></span> 
  
<span data-ttu-id="b783b-130">如果提供程序或网关不处理问题数组，它可以在  _lpProblem_ 中传递 NULL;在这种情况下，不会返回问题数组。</span><span class="sxs-lookup"><span data-stu-id="b783b-130">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lpProblem_; in this case, no problem array is returned.</span></span> 
  
<span data-ttu-id="b783b-131">_lpProblem_ 中返回的值仅在调用返回值时S_OK。</span><span class="sxs-lookup"><span data-stu-id="b783b-131">The value returned in  _lpProblem_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="b783b-132">返回S_OK时，提供商或网关应检查 **STnefProblemArray** 结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="b783b-132">When S_OK is returned, the provider or gateway should check the values returned in the **STnefProblemArray** structure.</span></span> <span data-ttu-id="b783b-133">如果呼叫出错， **则 STnefProblemArray** 结构不会填充，并且调用提供程序或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="b783b-133">If an error occurs on the call, the **STnefProblemArray** structure is not filled in and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="b783b-134">如果呼叫中未发生错误，则调用提供程序或网关必须通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放 **STnefProblemArray** 的内存。</span><span class="sxs-lookup"><span data-stu-id="b783b-134">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b783b-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="b783b-135">MFCMAPI reference</span></span>

<span data-ttu-id="b783b-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b783b-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b783b-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="b783b-137">**File**</span></span>|<span data-ttu-id="b783b-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="b783b-138">**Function**</span></span>|<span data-ttu-id="b783b-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="b783b-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b783b-140">File.cpp</span><span class="sxs-lookup"><span data-stu-id="b783b-140">File.cpp</span></span>  <br/> |<span data-ttu-id="b783b-141">SaveToTNEF</span><span class="sxs-lookup"><span data-stu-id="b783b-141">SaveToTNEF</span></span>  <br/> |<span data-ttu-id="b783b-142">MFCMAPI 使用 **ITnef：：Finish** 方法完成新 TNEF 流的处理。</span><span class="sxs-lookup"><span data-stu-id="b783b-142">MFCMAPI uses the **ITnef::Finish** method to finish processing of the new TNEF stream.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b783b-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b783b-143">See also</span></span>



[<span data-ttu-id="b783b-144">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="b783b-144">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="b783b-145">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="b783b-145">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="b783b-146">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="b783b-146">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="b783b-147">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="b783b-147">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="b783b-148">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="b783b-148">PidTagAttachNumber Canonical Property</span></span>](pidtagattachnumber-canonical-property.md)
  
[<span data-ttu-id="b783b-149">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="b783b-149">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="b783b-150">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b783b-150">ITnef : IUnknown</span></span>](itnefiunknown.md)


[<span data-ttu-id="b783b-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b783b-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

