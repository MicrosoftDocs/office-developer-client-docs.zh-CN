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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348942"
---
# <a name="iablogonpreparerecips"></a><span data-ttu-id="a5238-103">IABLogon::PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="a5238-103">IABLogon::PrepareRecips</span></span>

<span data-ttu-id="a5238-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a5238-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a5238-105">准备收件人列表, 以供邮件系统以后使用。</span><span class="sxs-lookup"><span data-stu-id="a5238-105">Prepares a recipient list for later use by the messaging system.</span></span>
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="a5238-106">参数</span><span class="sxs-lookup"><span data-stu-id="a5238-106">Parameters</span></span>

<span data-ttu-id="a5238-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a5238-107">_ulFlags_</span></span>
  
> <span data-ttu-id="a5238-108">实时用于控制返回的字符串中的文本类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a5238-108">[in] A bitmask of flags that controls the type of the text in the returned strings.</span></span> <span data-ttu-id="a5238-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a5238-109">The following flag can be set:</span></span>
    
  - <span data-ttu-id="a5238-110">MAPI_CACHE_ONLY: 仅使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="a5238-110">MAPI_CACHE_ONLY: Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="a5238-111">例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="a5238-111">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="a5238-112">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="a5238-112">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="a5238-113">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="a5238-113">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="a5238-114">实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含指示需要更新的属性的属性标记的数组 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="a5238-114">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags that indicate the properties that require updating, if any.</span></span> <span data-ttu-id="a5238-115">_lpPropTagArray_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a5238-115">The  _lpPropTagArray_ parameter can be NULL.</span></span> 
    
<span data-ttu-id="a5238-116">_lpRecipList_</span><span class="sxs-lookup"><span data-stu-id="a5238-116">_lpRecipList_</span></span>
  
> <span data-ttu-id="a5238-117">实时指向包含收件人列表的[ADRLIST](adrlist.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a5238-117">[in] A pointer to an [ADRLIST](adrlist.md) structure that holds the recipient list.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a5238-118">返回值</span><span class="sxs-lookup"><span data-stu-id="a5238-118">Return value</span></span>

<span data-ttu-id="a5238-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5238-119">S_OK</span></span> 
  
> <span data-ttu-id="a5238-120">已成功准备收件人列表。</span><span class="sxs-lookup"><span data-stu-id="a5238-120">The recipient list was successfully prepared.</span></span>
    
<span data-ttu-id="a5238-121">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="a5238-121">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="a5238-122">_lpRecipList_参数中的一个或多个收件人不存在。</span><span class="sxs-lookup"><span data-stu-id="a5238-122">One or more of the recipients in the  _lpRecipList_ parameter do not exist.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a5238-123">返回值</span><span class="sxs-lookup"><span data-stu-id="a5238-123">Return value</span></span>

<span data-ttu-id="a5238-124">客户端调用 MAPI [IAddrBook::P reparerecips](iaddrbook-preparerecips.md)方法来修改或重新排列一个或多个收件人的一组属性。</span><span class="sxs-lookup"><span data-stu-id="a5238-124">A client calls the MAPI [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) method to modify or rearrange a set of properties for one or more recipients.</span></span> <span data-ttu-id="a5238-125">收件人可能会有, 也可能不是传出邮件的收件人列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="a5238-125">The recipients may or may not be part of the recipient list of an outgoing message.</span></span> <span data-ttu-id="a5238-126">MAPI 将此呼叫传送到通讯簿提供程序的**IABLogon::P reparerecips**方法。</span><span class="sxs-lookup"><span data-stu-id="a5238-126">MAPI transfers this call to an address book provider's **IABLogon::PrepareRecips** method.</span></span> 
  
<span data-ttu-id="a5238-127">**IABLogon::P reparerecips**执行四个主要任务:</span><span class="sxs-lookup"><span data-stu-id="a5238-127">**IABLogon::PrepareRecips** performs four main tasks:</span></span> 
  
- <span data-ttu-id="a5238-128">确保_lpRecipList_参数指向的地址列表中的所有收件人都具有长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a5238-128">Ensures that all recipients in the address list pointed to by the  _lpRecipList_ parameter have a long-term entry identifier.</span></span> 
    
- <span data-ttu-id="a5238-129">确保所有收件人具有在由_lpPropTagArray_参数指向的属性值数组中指定的属性。</span><span class="sxs-lookup"><span data-stu-id="a5238-129">Ensures that all recipients have the properties specified in the property value array pointed to by the  _lpPropTagArray_ parameter.</span></span> 
    
- <span data-ttu-id="a5238-130">确保属性值数组中的属性显示在调用之前存在的任何其他属性之前。</span><span class="sxs-lookup"><span data-stu-id="a5238-130">Ensures that the properties from the property value array appear before any other properties that existed before the call.</span></span>
    
- <span data-ttu-id="a5238-131">确保**ADRLIST**结构中每个收件人的[ADRENTRY](adrentry.md)结构中的属性顺序与属性值数组中的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="a5238-131">Ensures that the order of the properties in each recipient's [ADRENTRY](adrentry.md) structure in the **ADRLIST** structure is the same as in the property value array.</span></span> 
    
<span data-ttu-id="a5238-132">_lpRecipList_参数中的**ADRENTRY**结构包含每个收件人的一个**ADRENTRY**结构。</span><span class="sxs-lookup"><span data-stu-id="a5238-132">The **ADRENTRY** structure in the  _lpRecipList_ parameter contains one **ADRENTRY** structure for each recipient.</span></span> <span data-ttu-id="a5238-133">每个**ADRENTRY**结构包含[SPropValue](spropvalue.md)结构的数组, 用于描述收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="a5238-133">Each **ADRENTRY** structure contains an array of [SPropValue](spropvalue.md) structures to describe the recipient's properties.</span></span> <span data-ttu-id="a5238-134">当**IABLogon::P reparerecips**返回时, 每个收件人的**SPropValue**结构数组包括_lpPropTagArray_中的属性以及收件人的其他属性。</span><span class="sxs-lookup"><span data-stu-id="a5238-134">When **IABLogon::PrepareRecips** returns, the **SPropValue** structure array for each recipient includes the properties from the  _lpPropTagArray_ followed by the other properties for the recipient.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a5238-135">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="a5238-135">Notes to implementers</span></span>

<span data-ttu-id="a5238-136">实现**IABLogon::P reparerecips**包括按特定顺序放置属性、检索属性值, 以及将短期条目标识符转换为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a5238-136">Implementing **IABLogon::PrepareRecips** involves putting properties in a specific order, retrieving property values, and converting short-term entry identifiers to long-term entry identifiers.</span></span> <span data-ttu-id="a5238-137">在_lpPropTagArray_参数中请求的属性必须位于与_lpRecipList_参数中的每个收件人的**ADRENTRY**结构相关联的属性值数组的开头。</span><span class="sxs-lookup"><span data-stu-id="a5238-137">The properties that are requested in the  _lpPropTagArray_ parameter must be at the start of the property value array associated with each recipient's **ADRENTRY** structure in the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="a5238-138">如果这些属性的值不存在, 请使用其条目标识符打开关联的邮件用户或通讯组列表, 并检索缺少的属性值。</span><span class="sxs-lookup"><span data-stu-id="a5238-138">If values for these properties do not exist, open the associated messaging user or distribution list by using its entry identifier and retrieve the missing property values.</span></span> 
  
<span data-ttu-id="a5238-139">分别分配_lpRecipList_中传递的每个**SPropValue**结构, 以便可以单独释放这些结构。</span><span class="sxs-lookup"><span data-stu-id="a5238-139">Allocate each **SPropValue** structure passed in  _lpRecipList_ separately so that the structures can be freed individually.</span></span> <span data-ttu-id="a5238-140">如果必须为任何**SPropValue**结构分配额外的空间, 例如, 若要存储 string 属性的数据, 请使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为完整属性值数组分配额外的空间。</span><span class="sxs-lookup"><span data-stu-id="a5238-140">If you must allocate additional space for any **SPropValue** structure, for example, to store the data for a string property, use the [MAPIAllocateBuffer](mapiallocatebuffer.md) function to allocate additional space for the full property value array.</span></span> <span data-ttu-id="a5238-141">使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放原始属性值数组, 然后使用[MAPIAllocateMore](mapiallocatemore.md)函数分配所需的其他任何内存。</span><span class="sxs-lookup"><span data-stu-id="a5238-141">Use the [MAPIFreeBuffer](mapifreebuffer.md) function to free the original property value array, and then use the [MAPIAllocateMore](mapiallocatemore.md) function to allocate any additional memory that is required.</span></span> 
  
<span data-ttu-id="a5238-142">若要实现**IABLogon::P reparerecips**, 请使用以下过程:</span><span class="sxs-lookup"><span data-stu-id="a5238-142">To implement **IABLogon::PrepareRecips**, use the following procedure:</span></span>
  
1. <span data-ttu-id="a5238-143">检查_lpPropTagArray_参数中的条目。</span><span class="sxs-lookup"><span data-stu-id="a5238-143">Check for entries in the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="a5238-144">如果属性值数组为空, 则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a5238-144">If the property value array is empty, there is no work to do.</span></span> <span data-ttu-id="a5238-145">返回一个成功值。</span><span class="sxs-lookup"><span data-stu-id="a5238-145">Return a success value.</span></span> 
    
2. <span data-ttu-id="a5238-146">处理_lpRecipList_参数中的每个收件人。</span><span class="sxs-lookup"><span data-stu-id="a5238-146">Process each recipient in the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="a5238-147">列表中的每个收件人都有一个**ADRENTRY**结构成员。</span><span class="sxs-lookup"><span data-stu-id="a5238-147">There is one **ADRENTRY** structure member for each recipient in the list.</span></span> <span data-ttu-id="a5238-148">忽略下列类型的收件人:</span><span class="sxs-lookup"><span data-stu-id="a5238-148">Ignore the following types of recipients:</span></span> 
    
   - <span data-ttu-id="a5238-149">在其**ADRENTRY**结构的**rgPropVals**成员中没有条目标识符的收件人 (即未解析的收件人)。</span><span class="sxs-lookup"><span data-stu-id="a5238-149">Recipients without an entry identifier in the **rgPropVals** member of their **ADRENTRY** structure (that is, unresolved recipients).</span></span> 
    
   - <span data-ttu-id="a5238-150">其条目标识符不属于您的提供程序的收件人。</span><span class="sxs-lookup"><span data-stu-id="a5238-150">Recipients with an entry identifier that does not belong to your provider.</span></span> <span data-ttu-id="a5238-151">这些收件人将被传递到另一个通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="a5238-151">These recipients will be passed to another address book provider.</span></span>
    
3. <span data-ttu-id="a5238-152">打开收件人, 并检索已为收件人设置的属性。</span><span class="sxs-lookup"><span data-stu-id="a5238-152">Open the recipient and retrieve the properties that are already set for the recipient.</span></span>
    
4. <span data-ttu-id="a5238-153">将_lpRecipList_中指定的属性值数组与**GetProps**返回的属性数组合并。</span><span class="sxs-lookup"><span data-stu-id="a5238-153">Merge the property value array specified in the  _lpRecipList_ with the array of properties returned from **GetProps**.</span></span> <span data-ttu-id="a5238-154">如果两个属性数组中都出现相同的属性, 请使用_lpRecipList_中的值。</span><span class="sxs-lookup"><span data-stu-id="a5238-154">If the same property occurs in both property arrays, use the value from  _lpRecipList_.</span></span>
    
5. <span data-ttu-id="a5238-155">如果_lpRecipList_属性值数组的大小足以容纳所有必需的属性, 只需将其替换为合并后的数组即可。</span><span class="sxs-lookup"><span data-stu-id="a5238-155">If the  _lpRecipList_ property value array is big enough to hold all of the necessary properties, just replace it with the merged array.</span></span> <span data-ttu-id="a5238-156">如果_lpRecipList_属性值数组不够大, 请将其替换为新分配的数组。</span><span class="sxs-lookup"><span data-stu-id="a5238-156">If the  _lpRecipList_ property value array is not big enough, replace it with a newly allocated array.</span></span> <span data-ttu-id="a5238-157">确保新的数组在其每个**cValues**成员中都有更新的值。</span><span class="sxs-lookup"><span data-stu-id="a5238-157">Be sure the new array has an updated value in each of its **cValues** members.</span></span> 
    
6. <span data-ttu-id="a5238-158">如果您不识别_lpPropTagArray_参数中的一个或多个属性, 请将收件人的**ADRENTRY**结构中的属性类型设置为 PT_ERROR, 并将属性值设置为 MAPI_E_NOT_FOUND 或其他值, 以提供更属性不可用的特定原因。</span><span class="sxs-lookup"><span data-stu-id="a5238-158">If you do not recognize one or more of the properties in the  _lpPropTagArray_ parameter, set the property type in the recipient's **ADRENTRY** structure to PT_ERROR and the property value either to MAPI_E_NOT_FOUND or to another value that gives a more specific reason for the unavailability of the property.</span></span> <span data-ttu-id="a5238-159">有关 PT_ERROR 的信息, 请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a5238-159">For information about PT_ERROR, see [Property Types](property-types.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a5238-160">永远不要重新分配传递到 IABLogon 中的**ADRLIST**结构 **::P reparerecips**或更改其条目数。</span><span class="sxs-lookup"><span data-stu-id="a5238-160">Never reallocate the **ADRLIST** structure that is passed into **IABLogon::PrepareRecips** or change its number of entries.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a5238-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5238-161">See also</span></span>

- [<span data-ttu-id="a5238-162">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="a5238-162">ADRLIST</span></span>](adrlist.md)
- [<span data-ttu-id="a5238-163">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="a5238-163">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
- [<span data-ttu-id="a5238-164">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="a5238-164">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
- [<span data-ttu-id="a5238-165">SPropValue</span><span class="sxs-lookup"><span data-stu-id="a5238-165">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="a5238-166">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a5238-166">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

