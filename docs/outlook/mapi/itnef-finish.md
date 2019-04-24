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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348585"
---
# <a name="itneffinish"></a><span data-ttu-id="ab3a0-103">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="ab3a0-103">ITnef::Finish</span></span>

  
  
<span data-ttu-id="ab3a0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ab3a0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ab3a0-105">完成排队和等待的所有传输中性封装格式 (TNEF) 操作的处理。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-105">Finishes processing for all Transport-Neutral Encapsulation Format (TNEF) operations that are queued and waiting.</span></span> 
  
```cpp
HRESULT Finish(
  ULONG ulFlags,
  WORD FAR * lpKey,
  LPSTnefProblemArray FAR * lpProblem
);
```

## <a name="parameters"></a><span data-ttu-id="ab3a0-106">参数</span><span class="sxs-lookup"><span data-stu-id="ab3a0-106">Parameters</span></span>

 <span data-ttu-id="ab3a0-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ab3a0-107">_ulFlags_</span></span>
  
> <span data-ttu-id="ab3a0-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="ab3a0-109">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="ab3a0-109">_lpKey_</span></span>
  
> <span data-ttu-id="ab3a0-110">排除指向附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 键属性的指针。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-110">[out] A pointer to the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) key property of an attachment.</span></span> <span data-ttu-id="ab3a0-111">TNEF 封装对象使用此键将附件与邮件中的附件放置标记相匹配。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-111">The TNEF encapsulation object uses this key to match an attachment to its attachment placement tag in a message.</span></span> <span data-ttu-id="ab3a0-112">此键对于每个附件应是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-112">This key should be unique to each attachment.</span></span>
    
 <span data-ttu-id="ab3a0-113">_lpProblem_</span><span class="sxs-lookup"><span data-stu-id="ab3a0-113">_lpProblem_</span></span>
  
> <span data-ttu-id="ab3a0-114">排除指向返回的[STnefProblemArray](stnefproblemarray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-114">[out] A pointer to a pointer to a returned [STnefProblemArray](stnefproblemarray.md) structure.</span></span> <span data-ttu-id="ab3a0-115">**STnefProblemArray**结构指示哪些属性 (如果有) 未正确编码。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-115">The **STnefProblemArray** structure indicates which properties, if any, were not encoded properly.</span></span> <span data-ttu-id="ab3a0-116">如果在_lpProblem_参数中传递 NULL, 则不返回属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-116">If NULL is passed in the  _lpProblem_ parameter, no property problem array is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ab3a0-117">返回值</span><span class="sxs-lookup"><span data-stu-id="ab3a0-117">Return value</span></span>

<span data-ttu-id="ab3a0-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab3a0-118">S_OK</span></span> 
  
> <span data-ttu-id="ab3a0-119">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-119">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ab3a0-120">注解</span><span class="sxs-lookup"><span data-stu-id="ab3a0-120">Remarks</span></span>

<span data-ttu-id="ab3a0-121">传输提供程序、邮件存储提供程序和网关调用**ITnef:: Finish**方法, 以执行在对[ITnef:: AddProps](itnef-addprops.md)和[ITnef:: SetProps](itnef-setprops.md)方法的调用中请求进行编码的所有属性的编码。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-121">Transport providers, message store providers, and gateways call the **ITnef::Finish** method to perform the encoding of all properties for which encoding was requested in calls to the [ITnef::AddProps](itnef-addprops.md) and [ITnef::SetProps](itnef-setprops.md) methods.</span></span> <span data-ttu-id="ab3a0-122">如果使用[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_ENCODE 标志打开 TNEF 对象, 则**完成**方法会将请求的属性编码到传递给该对象的封装流中。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-122">If the TNEF object was opened with the TNEF_ENCODE flag for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function, the **Finish** method encodes the requested properties into the encapsulation stream passed to that object.</span></span> <span data-ttu-id="ab3a0-123">如果使用 TNEF_DECODE 标志打开 tnef 对象, 则**完成**方法会对 TNEF 流中的属性进行解码, 并将其写回到其所属的邮件中。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-123">If the TNEF object was opened with the TNEF_DECODE flag, the **Finish** method decodes the properties from the TNEF stream and writes them back to the message they belong to.</span></span> 
  
<span data-ttu-id="ab3a0-124">**完成**调用后, 指向封装流的指针指向 TNEF 数据的末尾。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-124">After the **Finish** call, the pointer to the encapsulation stream points to the end of the TNEF data.</span></span> <span data-ttu-id="ab3a0-125">如果提供程序或网关需要在**完成**呼叫后使用 tnef 流数据, 则必须将 stream 指针重置为 TNEF 流数据的开头。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-125">If the provider or gateway needs to use the TNEF stream data after the **Finish** call, it must reset the stream pointer to the beginning of the TNEF stream data.</span></span> 
  
<span data-ttu-id="ab3a0-126">tnef 实现在不停止**完成**过程的情况下报告 TNEF 流编码问题。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-126">The TNEF implementation reports TNEF stream encoding problems without stopping the **Finish** process.</span></span> <span data-ttu-id="ab3a0-127">在_lpProblem_参数中返回的[STnefProblemArray](stnefproblemarray.md)结构指示无法处理 TNEF 属性或 MAPI 属性 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-127">The [STnefProblemArray](stnefproblemarray.md) structure returned in the  _lpProblem_ parameter indicates which TNEF attributes or MAPI properties, if any, could not be processed.</span></span> <span data-ttu-id="ab3a0-128">在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指出了具体的问题。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-128">The value returned in the **scode** member of the one of the **STnefProblem** structures contained in **STnefProblemArray** indicates the specific problem.</span></span> <span data-ttu-id="ab3a0-129">提供程序或网关可以在假定**完成**时未返回问题报告的所有属性或属性均已成功处理。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-129">The provider or gateway can work on the assumption that all properties or attributes for which **Finish** does not return a problem report were processed successfully.</span></span> 
  
<span data-ttu-id="ab3a0-130">如果提供程序或网关无法处理问题数组, 则它可以在_lpProblem_中传递 NULL;在这种情况下, 不会返回任何问题数组。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-130">If a provider or gateway does not work with problem arrays, it can pass NULL in  _lpProblem_; in this case, no problem array is returned.</span></span> 
  
<span data-ttu-id="ab3a0-131">仅当调用返回 S_OK 时, _lpProblem_中返回的值才有效。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-131">The value returned in  _lpProblem_ is valid only if the call returns S_OK.</span></span> <span data-ttu-id="ab3a0-132">当返回 S_OK 时, 提供程序或网关应检查**STnefProblemArray**结构中返回的值。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-132">When S_OK is returned, the provider or gateway should check the values returned in the **STnefProblemArray** structure.</span></span> <span data-ttu-id="ab3a0-133">如果调用时出现错误, 则不会填写**STnefProblemArray**结构, 并且调用提供程序或网关不应使用或释放结构。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-133">If an error occurs on the call, the **STnefProblemArray** structure is not filled in and the calling provider or gateway should not use or free the structure.</span></span> <span data-ttu-id="ab3a0-134">如果调用中没有发生错误, 则调用提供程序或网关必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放**STnefProblemArray**的内存。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-134">If no error occurs on the call, the calling provider or gateway must release the memory for the **STnefProblemArray** by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ab3a0-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="ab3a0-135">MFCMAPI reference</span></span>

<span data-ttu-id="ab3a0-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ab3a0-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="ab3a0-137">**File**</span></span>|<span data-ttu-id="ab3a0-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="ab3a0-138">**Function**</span></span>|<span data-ttu-id="ab3a0-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="ab3a0-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ab3a0-140">文件 .cpp</span><span class="sxs-lookup"><span data-stu-id="ab3a0-140">File.cpp</span></span>  <br/> |<span data-ttu-id="ab3a0-141">SaveToTNEF</span><span class="sxs-lookup"><span data-stu-id="ab3a0-141">SaveToTNEF</span></span>  <br/> |<span data-ttu-id="ab3a0-142">MFCMAPI 使用**ITnef:: finish**方法完成对新的 TNEF 流的处理。</span><span class="sxs-lookup"><span data-stu-id="ab3a0-142">MFCMAPI uses the **ITnef::Finish** method to finish processing of the new TNEF stream.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ab3a0-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab3a0-143">See also</span></span>



[<span data-ttu-id="ab3a0-144">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="ab3a0-144">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="ab3a0-145">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="ab3a0-145">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="ab3a0-146">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="ab3a0-146">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="ab3a0-147">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="ab3a0-147">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="ab3a0-148">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab3a0-148">PidTagAttachNumber Canonical Property</span></span>](pidtagattachnumber-canonical-property.md)
  
[<span data-ttu-id="ab3a0-149">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="ab3a0-149">STnefProblemArray</span></span>](stnefproblemarray.md)
  
[<span data-ttu-id="ab3a0-150">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ab3a0-150">ITnef : IUnknown</span></span>](itnefiunknown.md)


[<span data-ttu-id="ab3a0-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ab3a0-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

