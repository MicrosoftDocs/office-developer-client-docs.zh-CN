---
title: IABLogonPrepareRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.PrepareRecips
api_type:
- COM
ms.assetid: 3c1845ea-e291-4855-9afd-51d2c64d7e85
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0a9b88d762ca88cebd6d9acecf06db53a0b778f6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423858"
---
# <a name="iablogonpreparerecips"></a><span data-ttu-id="18fce-103">IABLogon::PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="18fce-103">IABLogon::PrepareRecips</span></span>

<span data-ttu-id="18fce-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="18fce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="18fce-105">准备收件人列表供邮件系统稍后使用。</span><span class="sxs-lookup"><span data-stu-id="18fce-105">Prepares a recipient list for later use by the messaging system.</span></span>
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="18fce-106">参数</span><span class="sxs-lookup"><span data-stu-id="18fce-106">Parameters</span></span>

<span data-ttu-id="18fce-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="18fce-107">_ulFlags_</span></span>
  
> <span data-ttu-id="18fce-108">[in]控制返回的字符串中的文本类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="18fce-108">[in] A bitmask of flags that controls the type of the text in the returned strings.</span></span> <span data-ttu-id="18fce-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="18fce-109">The following flag can be set:</span></span>
    
  - <span data-ttu-id="18fce-110">MAPI_CACHE_ONLY：使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="18fce-110">MAPI_CACHE_ONLY: Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="18fce-111">例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="18fce-111">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="18fce-112">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="18fce-112">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="18fce-113">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="18fce-113">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="18fce-114">[in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含指示需要更新的属性（如果有）的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="18fce-114">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags that indicate the properties that require updating, if any.</span></span> <span data-ttu-id="18fce-115">_lpPropTagArray_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="18fce-115">The  _lpPropTagArray_ parameter can be NULL.</span></span> 
    
<span data-ttu-id="18fce-116">_lpRecipList_</span><span class="sxs-lookup"><span data-stu-id="18fce-116">_lpRecipList_</span></span>
  
> <span data-ttu-id="18fce-117">[in]指向包含收件人 [列表的 ADRLIST](adrlist.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="18fce-117">[in] A pointer to an [ADRLIST](adrlist.md) structure that holds the recipient list.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="18fce-118">返回值</span><span class="sxs-lookup"><span data-stu-id="18fce-118">Return value</span></span>

<span data-ttu-id="18fce-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="18fce-119">S_OK</span></span> 
  
> <span data-ttu-id="18fce-120">已成功准备收件人列表。</span><span class="sxs-lookup"><span data-stu-id="18fce-120">The recipient list was successfully prepared.</span></span>
    
<span data-ttu-id="18fce-121">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="18fce-121">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="18fce-122">_lpRecipList_ 参数中的一个或多个收件人不存在。</span><span class="sxs-lookup"><span data-stu-id="18fce-122">One or more of the recipients in the  _lpRecipList_ parameter do not exist.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="18fce-123">返回值</span><span class="sxs-lookup"><span data-stu-id="18fce-123">Return value</span></span>

<span data-ttu-id="18fce-124">客户端调用 MAPI [IAddrBook：:P repareRecips](iaddrbook-preparerecips.md) 方法来修改或重新排列一个或多个收件人的一组属性。</span><span class="sxs-lookup"><span data-stu-id="18fce-124">A client calls the MAPI [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) method to modify or rearrange a set of properties for one or more recipients.</span></span> <span data-ttu-id="18fce-125">收件人可能是传出邮件的收件人列表的一部分，也可能不是该收件人列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="18fce-125">The recipients may or may not be part of the recipient list of an outgoing message.</span></span> <span data-ttu-id="18fce-126">MAPI 将此调用转接到通讯簿提供商的 **IABLogon：:P repareRecips** 方法。</span><span class="sxs-lookup"><span data-stu-id="18fce-126">MAPI transfers this call to an address book provider's **IABLogon::PrepareRecips** method.</span></span> 
  
<span data-ttu-id="18fce-127">**IABLogon：:P repareRecips** 执行四个主要任务：</span><span class="sxs-lookup"><span data-stu-id="18fce-127">**IABLogon::PrepareRecips** performs four main tasks:</span></span> 
  
- <span data-ttu-id="18fce-128">确保  _lpRecipList_ 参数指向的地址列表中的所有收件人都有一个长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="18fce-128">Ensures that all recipients in the address list pointed to by the  _lpRecipList_ parameter have a long-term entry identifier.</span></span> 
    
- <span data-ttu-id="18fce-129">确保所有收件人都有由  _lpPropTagArray_ 参数指向的属性值数组中指定的属性。</span><span class="sxs-lookup"><span data-stu-id="18fce-129">Ensures that all recipients have the properties specified in the property value array pointed to by the  _lpPropTagArray_ parameter.</span></span> 
    
- <span data-ttu-id="18fce-130">确保属性值数组中的属性显示在调用之前已存在的其他任何属性之前。</span><span class="sxs-lookup"><span data-stu-id="18fce-130">Ensures that the properties from the property value array appear before any other properties that existed before the call.</span></span>
    
- <span data-ttu-id="18fce-131">确保 **ADRLIST** 结构中每个收件人 [的 ADRENTRY](adrentry.md)结构中属性的顺序与属性值数组中的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="18fce-131">Ensures that the order of the properties in each recipient's [ADRENTRY](adrentry.md) structure in the **ADRLIST** structure is the same as in the property value array.</span></span> 
    
<span data-ttu-id="18fce-132">_lpRecipList_ 参数中的 **ADRENTRY** 结构包含每个收件人的一个 **ADRENTRY** 结构。</span><span class="sxs-lookup"><span data-stu-id="18fce-132">The **ADRENTRY** structure in the  _lpRecipList_ parameter contains one **ADRENTRY** structure for each recipient.</span></span> <span data-ttu-id="18fce-133">每个 **ADRENTRY** 结构都包含一个 [SPropValue](spropvalue.md) 结构数组，用于描述收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="18fce-133">Each **ADRENTRY** structure contains an array of [SPropValue](spropvalue.md) structures to describe the recipient's properties.</span></span> <span data-ttu-id="18fce-134">**当 IABLogon：:P repareRecips** 返回时，每个收件人的 **SPropValue** 结构数组包括 _lpPropTagArray_ 中的属性，后跟收件人的其他属性。</span><span class="sxs-lookup"><span data-stu-id="18fce-134">When **IABLogon::PrepareRecips** returns, the **SPropValue** structure array for each recipient includes the properties from the  _lpPropTagArray_ followed by the other properties for the recipient.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="18fce-135">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="18fce-135">Notes to implementers</span></span>

<span data-ttu-id="18fce-136">实现 **IABLogon：:P repareRecips** 涉及按特定顺序放置属性、检索属性值以及将短期条目标识符转换为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="18fce-136">Implementing **IABLogon::PrepareRecips** involves putting properties in a specific order, retrieving property values, and converting short-term entry identifiers to long-term entry identifiers.</span></span> <span data-ttu-id="18fce-137">_lpPropTagArray_ 参数中请求的属性必须位于与 _lpRecipList_ 参数中每个收件人 **的 ADRENTRY** 结构关联的属性值数组的起始点。</span><span class="sxs-lookup"><span data-stu-id="18fce-137">The properties that are requested in the  _lpPropTagArray_ parameter must be at the start of the property value array associated with each recipient's **ADRENTRY** structure in the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="18fce-138">如果这些属性不存在，则使用关联的邮件用户或通讯组列表的条目标识符打开它，并检索缺少的属性值。</span><span class="sxs-lookup"><span data-stu-id="18fce-138">If values for these properties do not exist, open the associated messaging user or distribution list by using its entry identifier and retrieve the missing property values.</span></span> 
  
<span data-ttu-id="18fce-139">单独分配传入 _lpRecipList_ 的每个 **SPropValue** 结构，以便可以单独释放结构。</span><span class="sxs-lookup"><span data-stu-id="18fce-139">Allocate each **SPropValue** structure passed in  _lpRecipList_ separately so that the structures can be freed individually.</span></span> <span data-ttu-id="18fce-140">例如，如果必须为任何 **SPropValue** 结构分配额外空间以存储字符串属性的数据，请使用 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数为完整属性值数组分配额外空间。</span><span class="sxs-lookup"><span data-stu-id="18fce-140">If you must allocate additional space for any **SPropValue** structure, for example, to store the data for a string property, use the [MAPIAllocateBuffer](mapiallocatebuffer.md) function to allocate additional space for the full property value array.</span></span> <span data-ttu-id="18fce-141">使用 [MAPIFreeBuffer](mapifreebuffer.md) 函数释放原始属性值数组，然后使用 [MAPIAllocateMore](mapiallocatemore.md) 函数分配所需的任何其他内存。</span><span class="sxs-lookup"><span data-stu-id="18fce-141">Use the [MAPIFreeBuffer](mapifreebuffer.md) function to free the original property value array, and then use the [MAPIAllocateMore](mapiallocatemore.md) function to allocate any additional memory that is required.</span></span> 
  
<span data-ttu-id="18fce-142">若要实现 **IABLogon：:P repareRecips，** 请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="18fce-142">To implement **IABLogon::PrepareRecips**, use the following procedure:</span></span>
  
1. <span data-ttu-id="18fce-143">检查  _lpPropTagArray_ 参数中的条目。</span><span class="sxs-lookup"><span data-stu-id="18fce-143">Check for entries in the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="18fce-144">如果属性值数组为空，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="18fce-144">If the property value array is empty, there is no work to do.</span></span> <span data-ttu-id="18fce-145">返回成功值。</span><span class="sxs-lookup"><span data-stu-id="18fce-145">Return a success value.</span></span> 
    
2. <span data-ttu-id="18fce-146">处理  _lpRecipList 参数中的每个_ 收件人。</span><span class="sxs-lookup"><span data-stu-id="18fce-146">Process each recipient in the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="18fce-147">列表中每个收件人都有一个 **ADRENTRY** 结构成员。</span><span class="sxs-lookup"><span data-stu-id="18fce-147">There is one **ADRENTRY** structure member for each recipient in the list.</span></span> <span data-ttu-id="18fce-148">忽略以下类型的收件人：</span><span class="sxs-lookup"><span data-stu-id="18fce-148">Ignore the following types of recipients:</span></span> 
    
   - <span data-ttu-id="18fce-149">**ADRENTRY** 结构的 **rgPropVals** 成员中没有条目标识符 (，即未解析的收件人) 。</span><span class="sxs-lookup"><span data-stu-id="18fce-149">Recipients without an entry identifier in the **rgPropVals** member of their **ADRENTRY** structure (that is, unresolved recipients).</span></span> 
    
   - <span data-ttu-id="18fce-150">具有不属于您的提供程序的条目标识符的收件人。</span><span class="sxs-lookup"><span data-stu-id="18fce-150">Recipients with an entry identifier that does not belong to your provider.</span></span> <span data-ttu-id="18fce-151">这些收件人将被传递到另一个通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="18fce-151">These recipients will be passed to another address book provider.</span></span>
    
3. <span data-ttu-id="18fce-152">打开收件人并检索为收件人设置的属性。</span><span class="sxs-lookup"><span data-stu-id="18fce-152">Open the recipient and retrieve the properties that are already set for the recipient.</span></span>
    
4. <span data-ttu-id="18fce-153">将  _lpRecipList_ 中指定的属性值数组与从 **GetProps** 返回的属性数组合并。</span><span class="sxs-lookup"><span data-stu-id="18fce-153">Merge the property value array specified in the  _lpRecipList_ with the array of properties returned from **GetProps**.</span></span> <span data-ttu-id="18fce-154">如果同一属性出现在两个属性数组中，请使用  _lpRecipList 中的值_。</span><span class="sxs-lookup"><span data-stu-id="18fce-154">If the same property occurs in both property arrays, use the value from  _lpRecipList_.</span></span>
    
5. <span data-ttu-id="18fce-155">如果  _lpRecipList_ 属性值数组足够大，足以容纳所有必需的属性，只需将其替换为合并的数组。</span><span class="sxs-lookup"><span data-stu-id="18fce-155">If the  _lpRecipList_ property value array is big enough to hold all of the necessary properties, just replace it with the merged array.</span></span> <span data-ttu-id="18fce-156">如果  _lpRecipList_ 属性值数组不够大，请将其替换为新分配的数组。</span><span class="sxs-lookup"><span data-stu-id="18fce-156">If the  _lpRecipList_ property value array is not big enough, replace it with a newly allocated array.</span></span> <span data-ttu-id="18fce-157">确保新数组的每个 **cValues** 成员中都有更新的值。</span><span class="sxs-lookup"><span data-stu-id="18fce-157">Be sure the new array has an updated value in each of its **cValues** members.</span></span> 
    
6. <span data-ttu-id="18fce-158">如果您无法识别  _lpPropTagArray_ 参数中的一个或多个属性，将收件人 **的 ADRENTRY** 结构中的属性类型设置为 PT_ERROR，将属性值设置为 MAPI_E_NOT_FOUND 或设置为其他值，以更具体地解释属性不可用的原因。</span><span class="sxs-lookup"><span data-stu-id="18fce-158">If you do not recognize one or more of the properties in the  _lpPropTagArray_ parameter, set the property type in the recipient's **ADRENTRY** structure to PT_ERROR and the property value either to MAPI_E_NOT_FOUND or to another value that gives a more specific reason for the unavailability of the property.</span></span> <span data-ttu-id="18fce-159">有关属性类型PT_ERROR，请参阅 [属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="18fce-159">For information about PT_ERROR, see [Property Types](property-types.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="18fce-160">切勿重新分配传递到 **IABLogon：:P repareRecips 的** **ADRLIST** 结构或更改其条目数。</span><span class="sxs-lookup"><span data-stu-id="18fce-160">Never reallocate the **ADRLIST** structure that is passed into **IABLogon::PrepareRecips** or change its number of entries.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="18fce-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18fce-161">See also</span></span>

- [<span data-ttu-id="18fce-162">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="18fce-162">ADRLIST</span></span>](adrlist.md)
- [<span data-ttu-id="18fce-163">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="18fce-163">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
- [<span data-ttu-id="18fce-164">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="18fce-164">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
- [<span data-ttu-id="18fce-165">SPropValue</span><span class="sxs-lookup"><span data-stu-id="18fce-165">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="18fce-166">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="18fce-166">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

