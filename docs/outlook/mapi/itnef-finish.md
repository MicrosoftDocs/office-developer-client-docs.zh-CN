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
ms.openlocfilehash: 2b95e0dd62d83dd83a064ee4627811fcb24af921
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776113"
---
# <a name="itneffinish"></a><span data-ttu-id="d7f1c-103">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="d7f1c-103">ITnef::Finish</span></span>

  
  
<span data-ttu-id="d7f1c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d7f1c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d7f1c-105">处理排队的所有传输中性封装格式 (TNEF) 操作和等待完成。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-105">Finishes processing for all Transport-Neutral Encapsulation Format (TNEF) operations that are queued and waiting.</span></span> 
  
```cpp
HRESULT Finish(
  ULONG ulFlags,
  WORD FAR * lpKey,
  LPSTnefProblemArray FAR * lpProblem
);
```

## <a name="parameters"></a><span data-ttu-id="d7f1c-106">参数</span><span class="sxs-lookup"><span data-stu-id="d7f1c-106">Parameters</span></span>

 <span data-ttu-id="d7f1c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d7f1c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="d7f1c-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="d7f1c-109">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="d7f1c-109">_lpKey_</span></span>
  
> <span data-ttu-id="d7f1c-110">[输出]一个指向附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 关键属性。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-110">[out] A pointer to the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) key property of an attachment.</span></span> <span data-ttu-id="d7f1c-111">TNEF 封装对象使用此项匹配附件的邮件及其附件放置标记。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-111">The TNEF encapsulation object uses this key to match an attachment to its attachment placement tag in a message.</span></span> <span data-ttu-id="d7f1c-112">此参数应是唯一的每个附件。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-112">This key should be unique to each attachment.</span></span>
    
 <span data-ttu-id="d7f1c-113">_lpProblem_</span><span class="sxs-lookup"><span data-stu-id="d7f1c-113">_lpProblem_</span></span>
  
> <span data-ttu-id="d7f1c-114">[输出]指向返回[STnefProblemArray](stnefproblemarray.md)结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-114">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="d7f1c-115">**STnefProblemArray**结构表明哪些属性中，如果有，已未编码的正确。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-115">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="d7f1c-116">如果_lpProblem_参数中传递了 NULL，则返回没有属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-116">If NULL is passed in the  _lpProblem_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d7f1c-117">返回值</span><span class="sxs-lookup"><span data-stu-id="d7f1c-117">Return value</span></span>

<span data-ttu-id="d7f1c-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7f1c-118">S_OK</span></span> 
  
> <span data-ttu-id="d7f1c-119">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-119">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d7f1c-120">说明</span><span class="sxs-lookup"><span data-stu-id="d7f1c-120">Remarks</span></span>

<span data-ttu-id="d7f1c-121">传输提供程序、 消息存储提供程序，和网关呼叫给[ITnef::AddProps](itnef-addprops.md)和[ITnef::SetProps](itnef-setprops.md)方法的调用中请求的**ITnef::Finish**方法执行的编码的所有属性的都编码。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-121">Transport providers, message store providers, and gateways call the **ITnef::Finish** method to perform the encoding of all properties for which encoding was requested in calls to the [ITnef::AddProps](itnef-addprops.md) and [ITnef::SetProps](itnef-setprops.md) methods.</span></span> <span data-ttu-id="d7f1c-122">如果 TNEF 对象已打开了 TNEF_ENCODE 标记[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数中，**完成**方法将编码为传递到该对象的封装流请求的属性。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-122">If the TNEF object was opened with the TNEF_ENCODE flag for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function, the **Finish** method encodes the requested properties into the encapsulation stream passed to that object.</span></span> <span data-ttu-id="d7f1c-123">如果 TNEF 对象已打开了 TNEF_DECODE 标记，**完成**方法解码 TNEF 流中的属性，并将它们写回其所属的消息。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-123">If the TNEF object was opened with the TNEF_DECODE flag, the **Finish** method decodes the properties from the TNEF stream and writes them back to the message they belong to.</span></span> 
  
<span data-ttu-id="d7f1c-124">在**完成**调用后，该指针指向封装流指向 TNEF 数据的末尾。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-124">After the **Finish** call, the pointer to the encapsulation stream points to the end of the TNEF data.</span></span> <span data-ttu-id="d7f1c-125">如果提供程序或网关需要**完成**呼叫后，请使用 TNEF 流数据，它必须重流指针置到 TNEF 流数据的开头。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-125">If the provider or gateway needs to use the TNEF stream data after the **Finish** call, it must reset the stream pointer to the beginning of the TNEF stream data.</span></span> 
  
<span data-ttu-id="d7f1c-126">TNEF 实现报告而不停止**完成**进程 TNEF 流编码问题。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-126">The TNEF implementation reports TNEF stream encoding problems without stopping the **Finish** process.</span></span> <span data-ttu-id="d7f1c-127">返回_lpProblem_参数中的[STnefProblemArray](stnefproblemarray.md)结构指示哪些 TNEF 属性或 MAPI 属性，如果有，无法进行处理。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-127">The [STnefProblemArray](stnefproblemarray.md) structure returned in the  _lpProblem_ parameter indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="d7f1c-128">在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指示特定问题。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-128">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="d7f1c-129">所有属性或特性为其**完成**不会返回问题报告都已成功都处理假定可以处理提供程序或网关。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-129">The provider or gateway can work on the assumption that all properties or attributes for which **Finish** does not return a problem report were processed successfully.</span></span> 
  
<span data-ttu-id="d7f1c-130">如果提供程序或网关不适用于问题数组，它可以在_lpProblem_; 传递 NULL在这种情况下，则返回没有问题数组。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-130">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lpProblem_; in this case, no problem array is returned.</span></span> 
  
<span data-ttu-id="d7f1c-131">仅当呼叫，则返回 S_OK 有效_lpProblem_中返回的值。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-131">The value returned in  _lpProblem_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="d7f1c-132">返回 S_OK 时，提供程序或网关应检查**STnefProblemArray**结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-132">When S_OK is returned, the provider or gateway should check the values returned in the **STnefProblemArray** structure.</span></span> <span data-ttu-id="d7f1c-133">如果在调用出错， **STnefProblemArray**结构未填写并调用提供程序或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-133">If an error occurs on the call, the **STnefProblemArray** structure is not filled in and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="d7f1c-134">如果在调用不产生任何错误，呼叫提供商或网关必须释放内存的**STnefProblemArray**通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-134">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d7f1c-135">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="d7f1c-135">MFCMAPI reference</span></span>

<span data-ttu-id="d7f1c-136">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d7f1c-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-137">**File**</span></span>|<span data-ttu-id="d7f1c-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-138">**Function**</span></span>|<span data-ttu-id="d7f1c-139">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d7f1c-140">File.cpp</span><span class="sxs-lookup"><span data-stu-id="d7f1c-140">File.cpp</span></span>  <br/> |<span data-ttu-id="d7f1c-141">SaveToTNEF</span><span class="sxs-lookup"><span data-stu-id="d7f1c-141">SaveToTNEF</span></span>  <br/> |<span data-ttu-id="d7f1c-142">MFCMAPI 使用**ITnef::Finish**方法完成在新的 TNEF 流处理。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-142">MFCMAPI uses the **ITnef::Finish** method to finish processing of the new TNEF stream.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d7f1c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7f1c-143">See also</span></span>



[<span data-ttu-id="d7f1c-144">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="d7f1c-144">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="d7f1c-145">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d7f1c-145">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="d7f1c-146">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="d7f1c-146">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="d7f1c-147">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="d7f1c-147">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="d7f1c-148">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="d7f1c-148">PidTagAttachNumber Canonical Property</span></span>](pidtagattachnumber-canonical-property.md)
  
[<span data-ttu-id="d7f1c-149">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="d7f1c-149">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="d7f1c-150">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d7f1c-150">ITnef : IUnknown</span></span>](itnefiunknown.md)


[<span data-ttu-id="d7f1c-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d7f1c-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

