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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c42077528a4f7227321d8f987cc5dd0ccd4c966c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589740"
---
# <a name="iablogonpreparerecips"></a><span data-ttu-id="82c22-103">IABLogon::PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="82c22-103">IABLogon::PrepareRecips</span></span>

<span data-ttu-id="82c22-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82c22-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82c22-105">通过在邮件系统，以供以后使用准备收件人列表。</span><span class="sxs-lookup"><span data-stu-id="82c22-105">Prepares a recipient list for later use by the messaging system.</span></span>
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="82c22-106">参数</span><span class="sxs-lookup"><span data-stu-id="82c22-106">Parameters</span></span>

<span data-ttu-id="82c22-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="82c22-107">_ulFlags_</span></span>
  
> <span data-ttu-id="82c22-108">[in]位掩码的标志的控制返回的字符串中的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="82c22-108">[in] A bitmask of flags that controls the type of the text in the returned strings.</span></span> <span data-ttu-id="82c22-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="82c22-109">The following flag can be set:</span></span>
    
  - <span data-ttu-id="82c22-110">MAPI_CACHE_ONLY： 使用仅脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="82c22-110">MAPI_CACHE_ONLY: Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="82c22-111">例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="82c22-111">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="82c22-112">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="82c22-112">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="82c22-113">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="82c22-113">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="82c22-114">[in]一个指向[SPropTagArray](sproptagarray.md)结构，其中包含指示需要更新，如果有属性的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="82c22-114">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags that indicate the properties that require updating, if any.</span></span> <span data-ttu-id="82c22-115">_LpPropTagArray_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="82c22-115">The  _lpPropTagArray_ parameter can be NULL.</span></span> 
    
<span data-ttu-id="82c22-116">_lpRecipList_</span><span class="sxs-lookup"><span data-stu-id="82c22-116">_lpRecipList_</span></span>
  
> <span data-ttu-id="82c22-117">[in]指向包含收件人列表的[ADRLIST](adrlist.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="82c22-117">[in] A pointer to an [ADRLIST](adrlist.md) structure that holds the recipient list.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="82c22-118">返回值</span><span class="sxs-lookup"><span data-stu-id="82c22-118">Return value</span></span>

<span data-ttu-id="82c22-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="82c22-119">S_OK</span></span> 
  
> <span data-ttu-id="82c22-120">已成功准备好的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="82c22-120">The recipient list was successfully prepared.</span></span>
    
<span data-ttu-id="82c22-121">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="82c22-121">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="82c22-122">不存在一个或多个_lpRecipList_参数中的收件人。</span><span class="sxs-lookup"><span data-stu-id="82c22-122">One or more of the recipients in the  _lpRecipList_ parameter do not exist.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="82c22-123">返回值</span><span class="sxs-lookup"><span data-stu-id="82c22-123">Return value</span></span>

<span data-ttu-id="82c22-124">客户端调用 MAPI [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)方法来修改或重新排列的一个或多个收件人的一组属性。</span><span class="sxs-lookup"><span data-stu-id="82c22-124">A client calls the MAPI [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) method to modify or rearrange a set of properties for one or more recipients.</span></span> <span data-ttu-id="82c22-125">收件人可能也可能不是传出邮件的收件人列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="82c22-125">The recipients may or may not be part of the recipient list of an outgoing message.</span></span> <span data-ttu-id="82c22-126">MAPI 传输对通讯簿提供程序的**IABLogon::PrepareRecips**方法的调用。</span><span class="sxs-lookup"><span data-stu-id="82c22-126">MAPI transfers this call to an address book provider's **IABLogon::PrepareRecips** method.</span></span> 
  
<span data-ttu-id="82c22-127">**IABLogon::PrepareRecips**执行四个主要任务：</span><span class="sxs-lookup"><span data-stu-id="82c22-127">**IABLogon::PrepareRecips** performs four main tasks:</span></span> 
  
- <span data-ttu-id="82c22-128">确保地址列表中的所有收件人都指向_lpRecipList_参数具有长期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="82c22-128">Ensures that all recipients in the address list pointed to by the  _lpRecipList_ parameter have a long-term entry identifier.</span></span> 
    
- <span data-ttu-id="82c22-129">确保所有收件人都有_lpPropTagArray_参数指向的属性值数组中指定的属性。</span><span class="sxs-lookup"><span data-stu-id="82c22-129">Ensures that all recipients have the properties specified in the property value array pointed to by the  _lpPropTagArray_ parameter.</span></span> 
    
- <span data-ttu-id="82c22-130">确保在呼叫之前存在的任何其他属性之前出现属性值数组中的属性。</span><span class="sxs-lookup"><span data-stu-id="82c22-130">Ensures that the properties from the property value array appear before any other properties that existed before the call.</span></span>
    
- <span data-ttu-id="82c22-131">确保**ADRLIST**结构中的每个收件人的[ADRENTRY](adrentry.md)结构中属性的顺序相同属性值数组。</span><span class="sxs-lookup"><span data-stu-id="82c22-131">Ensures that the order of the properties in each recipient's [ADRENTRY](adrentry.md) structure in the **ADRLIST** structure is the same as in the property value array.</span></span> 
    
<span data-ttu-id="82c22-132">**ADRENTRY**结构_lpRecipList_参数中的包含一个**ADRENTRY**结构，每个收件人。</span><span class="sxs-lookup"><span data-stu-id="82c22-132">The **ADRENTRY** structure in the  _lpRecipList_ parameter contains one **ADRENTRY** structure for each recipient.</span></span> <span data-ttu-id="82c22-133">每个**ADRENTRY**结构包含数组[SPropValue](spropvalue.md)结构来描述收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="82c22-133">Each **ADRENTRY** structure contains an array of [SPropValue](spropvalue.md) structures to describe the recipient's properties.</span></span> <span data-ttu-id="82c22-134">**IABLogon::PrepareRecips**返回时，每个收件人的**SPropValue**结构数组包含从_lpPropTagArray_收件人后跟其他属性的属性。</span><span class="sxs-lookup"><span data-stu-id="82c22-134">When **IABLogon::PrepareRecips** returns, the **SPropValue** structure array for each recipient includes the properties from the  _lpPropTagArray_ followed by the other properties for the recipient.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="82c22-135">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="82c22-135">Notes to implementers</span></span>

<span data-ttu-id="82c22-136">实现**IABLogon::PrepareRecips**涉及将属性放在特定的顺序，检索属性值，并将其转换到长期条目标识符短期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="82c22-136">Implementing **IABLogon::PrepareRecips** involves putting properties in a specific order, retrieving property values, and converting short-term entry identifiers to long-term entry identifiers.</span></span> <span data-ttu-id="82c22-137">属性值数组_lpRecipList_参数中的每个收件人的**ADRENTRY**结构相关联的开头必须请求_lpPropTagArray_参数中的属性。</span><span class="sxs-lookup"><span data-stu-id="82c22-137">The properties that are requested in the  _lpPropTagArray_ parameter must be at the start of the property value array associated with each recipient's **ADRENTRY** structure in the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="82c22-138">如果不存在这些属性的值，使用其条目标识符打开相关联的邮件用户或通讯组列表，并检索缺少的属性值。</span><span class="sxs-lookup"><span data-stu-id="82c22-138">If values for these properties do not exist, open the associated messaging user or distribution list by using its entry identifier and retrieve the missing property values.</span></span> 
  
<span data-ttu-id="82c22-139">分配每个**SPropValue**结构中传递_lpRecipList_单独，以便可以单独释放结构。</span><span class="sxs-lookup"><span data-stu-id="82c22-139">Allocate each **SPropValue** structure passed in  _lpRecipList_ separately so that the structures can be freed individually.</span></span> <span data-ttu-id="82c22-140">如果您必须为任何**SPropValue**结构来分配额外的空间，例如，来存储对于字符串属性，数据[MAPIAllocateBuffer](mapiallocatebuffer.md)函数用于为完整的属性值数组分配额外的空间。</span><span class="sxs-lookup"><span data-stu-id="82c22-140">If you must allocate additional space for any **SPropValue** structure, for example, to store the data for a string property, use the [MAPIAllocateBuffer](mapiallocatebuffer.md) function to allocate additional space for the full property value array.</span></span> <span data-ttu-id="82c22-141">使用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放原始属性值数组，然后使用[MAPIAllocateMore](mapiallocatemore.md)函数分配任何其他所需的内存。</span><span class="sxs-lookup"><span data-stu-id="82c22-141">Use the [MAPIFreeBuffer](mapifreebuffer.md) function to free the original property value array, and then use the [MAPIAllocateMore](mapiallocatemore.md) function to allocate any additional memory that is required.</span></span> 
  
<span data-ttu-id="82c22-142">若要实现**IABLogon::PrepareRecips**，使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="82c22-142">To implement **IABLogon::PrepareRecips**, use the following procedure:</span></span>
  
1. <span data-ttu-id="82c22-143">检查_lpPropTagArray_参数中的项。</span><span class="sxs-lookup"><span data-stu-id="82c22-143">Check for entries in the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="82c22-144">如果属性值数组为空，则执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="82c22-144">If the property value array is empty, there is no work to do.</span></span> <span data-ttu-id="82c22-145">返回一个成功值。</span><span class="sxs-lookup"><span data-stu-id="82c22-145">Return a success value.</span></span> 
    
2. <span data-ttu-id="82c22-146">处理_lpRecipList_参数中的每个收件人。</span><span class="sxs-lookup"><span data-stu-id="82c22-146">Process each recipient in the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="82c22-147">没有为每个收件人列表中的一个**ADRENTRY**结构成员。</span><span class="sxs-lookup"><span data-stu-id="82c22-147">There is one **ADRENTRY** structure member for each recipient in the list.</span></span> <span data-ttu-id="82c22-148">忽略以下类型的收件人：</span><span class="sxs-lookup"><span data-stu-id="82c22-148">Ignore the following types of recipients:</span></span> 
    
   - <span data-ttu-id="82c22-149">没有其**ADRENTRY**结构 （即未解析的收件人） 的**rgPropVals**成员中的项标识符的收件人。</span><span class="sxs-lookup"><span data-stu-id="82c22-149">Recipients without an entry identifier in the **rgPropVals** member of their **ADRENTRY** structure (that is, unresolved recipients).</span></span> 
    
   - <span data-ttu-id="82c22-150">使用不属于您的提供商的项标识符的收件人。</span><span class="sxs-lookup"><span data-stu-id="82c22-150">Recipients with an entry identifier that does not belong to your provider.</span></span> <span data-ttu-id="82c22-151">这些收件人将传递给另一个通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="82c22-151">These recipients will be passed to another address book provider.</span></span>
    
3. <span data-ttu-id="82c22-152">打开收件人，并检索收件人已设置的属性。</span><span class="sxs-lookup"><span data-stu-id="82c22-152">Open the recipient and retrieve the properties that are already set for the recipient.</span></span>
    
4. <span data-ttu-id="82c22-153">合并_lpRecipList_在阵列中从**GetProps**返回的属性中指定的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="82c22-153">Merge the property value array specified in the  _lpRecipList_ with the array of properties returned from **GetProps**.</span></span> <span data-ttu-id="82c22-154">如果同一属性发生两个属性数组中，使用_lpRecipList_的值。</span><span class="sxs-lookup"><span data-stu-id="82c22-154">If the same property occurs in both property arrays, use the value from  _lpRecipList_.</span></span>
    
5. <span data-ttu-id="82c22-155">如果足以容纳所有必要的属性_lpRecipList_属性值数组，只需替换它合并的数组。</span><span class="sxs-lookup"><span data-stu-id="82c22-155">If the  _lpRecipList_ property value array is big enough to hold all of the necessary properties, just replace it with the merged array.</span></span> <span data-ttu-id="82c22-156">如果_lpRecipList_属性值数组不足够大，将其与新分配的数组。</span><span class="sxs-lookup"><span data-stu-id="82c22-156">If the  _lpRecipList_ property value array is not big enough, replace it with a newly allocated array.</span></span> <span data-ttu-id="82c22-157">确保新数组中每个其**cValues**成员具有更新的值。</span><span class="sxs-lookup"><span data-stu-id="82c22-157">Be sure the new array has an updated value in each of its **cValues** members.</span></span> 
    
6. <span data-ttu-id="82c22-158">如果您不认识一个或多个_lpPropTagArray_参数中的属性，PT_ERROR 和到 MAPI_E_NOT_FOUND 或另一个值，该值提供更多的属性值的收件人的**ADRENTRY**结构中设置的属性类型该属性不可用的特定原因。</span><span class="sxs-lookup"><span data-stu-id="82c22-158">If you do not recognize one or more of the properties in the  _lpPropTagArray_ parameter, set the property type in the recipient's **ADRENTRY** structure to PT_ERROR and the property value either to MAPI_E_NOT_FOUND or to another value that gives a more specific reason for the unavailability of the property.</span></span> <span data-ttu-id="82c22-159">有关 PT_ERROR 的信息，请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="82c22-159">For information about PT_ERROR, see [Property Types](property-types.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="82c22-160">从不重新分配到**IABLogon::PrepareRecips**传递的**ADRLIST**结构或更改其项数。</span><span class="sxs-lookup"><span data-stu-id="82c22-160">Never reallocate the **ADRLIST** structure that is passed into **IABLogon::PrepareRecips** or change its number of entries.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="82c22-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82c22-161">See also</span></span>

- [<span data-ttu-id="82c22-162">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="82c22-162">ADRLIST</span></span>](adrlist.md)
- [<span data-ttu-id="82c22-163">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="82c22-163">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
- [<span data-ttu-id="82c22-164">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="82c22-164">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
- [<span data-ttu-id="82c22-165">SPropValue</span><span class="sxs-lookup"><span data-stu-id="82c22-165">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="82c22-166">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="82c22-166">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

