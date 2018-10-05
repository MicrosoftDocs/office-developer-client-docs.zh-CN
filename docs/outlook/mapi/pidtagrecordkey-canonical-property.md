---
title: PidTagRecordKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecordKey
api_type:
- COM
ms.assetid: a12fb9a2-799d-4112-b26c-4b2854c47cc2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7a3ae7db1fb97e97f7d0939b67f139af62477bf7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401697"
---
# <a name="pidtagrecordkey-canonical-property"></a><span data-ttu-id="55ba3-103">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="55ba3-103">PidTagRecordKey Canonical Property</span></span>

  
  
<span data-ttu-id="55ba3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55ba3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55ba3-105">包含特定对象的唯一的二进制相当标识符。</span><span class="sxs-lookup"><span data-stu-id="55ba3-105">Contains a unique binary-comparable identifier for a specific object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="55ba3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="55ba3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="55ba3-107">PR_RECORD_KEY</span><span class="sxs-lookup"><span data-stu-id="55ba3-107">PR_RECORD_KEY</span></span>  <br/> |
|<span data-ttu-id="55ba3-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="55ba3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="55ba3-109">0x0FF9</span><span class="sxs-lookup"><span data-stu-id="55ba3-109">0x0FF9</span></span>  <br/> |
|<span data-ttu-id="55ba3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="55ba3-110">Data type:</span></span>  <br/> |<span data-ttu-id="55ba3-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="55ba3-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="55ba3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="55ba3-112">Area:</span></span>  <br/> |<span data-ttu-id="55ba3-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="55ba3-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="55ba3-114">说明</span><span class="sxs-lookup"><span data-stu-id="55ba3-114">Remarks</span></span>

<span data-ttu-id="55ba3-115">该属性从而便于查找引用对象，如内容表中查找其所在行。</span><span class="sxs-lookup"><span data-stu-id="55ba3-115">This property facilitates locating references to an object, such as finding its row in a contents table.</span></span> <span data-ttu-id="55ba3-116">此属性不能用于打开对象;使用此目的的项标识符。</span><span class="sxs-lookup"><span data-stu-id="55ba3-116">This property cannot be used to open an object; use the entry identifier for that purpose.</span></span>
  
<span data-ttu-id="55ba3-117">附件子对象应唯一标识邮件中，此属性。</span><span class="sxs-lookup"><span data-stu-id="55ba3-117">An attachment subobject should be uniquely identified within a message by this property.</span></span> <span data-ttu-id="55ba3-118">此标识符是保证保持不变后关闭并重新打开该邮件的唯一附件特征。</span><span class="sxs-lookup"><span data-stu-id="55ba3-118">This identifier is the only attachment characteristic guaranteed to stay the same after the message is closed and reopened.</span></span> <span data-ttu-id="55ba3-119">存储提供程序必须各个会话，以确保此保证保留此属性。</span><span class="sxs-lookup"><span data-stu-id="55ba3-119">The store provider must preserve this property across sessions to ensure this guarantee.</span></span>
  
<span data-ttu-id="55ba3-120">对于文件夹，此属性包含在文件夹层次结构表中使用的密钥。</span><span class="sxs-lookup"><span data-stu-id="55ba3-120">For folders, this property contains a key used in the folder hierarchy table.</span></span> <span data-ttu-id="55ba3-121">通常，这是由**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性提供的相同的值。</span><span class="sxs-lookup"><span data-stu-id="55ba3-121">Typically this is the same value as that provided by the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="55ba3-122">对于邮件存储区，该属性等同于**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="55ba3-122">For message stores, this property is identical to the **PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="55ba3-123">在消息存储对象中，此属性应是唯一的跨所有存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="55ba3-123">In a message store object, this property should be unique across all store providers.</span></span> <span data-ttu-id="55ba3-124">一种方法执行此操作是用[GUID](guid.md)结构或其他特有的特定邮件存储的值组合 （特有的提供程序类型） 的存储的**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="55ba3-124">One way to do this is to combine the value of the **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) property for the store (unique to that provider type) with a [GUID](guid.md) structure or other value unique to the specific message store.</span></span> 
  
<span data-ttu-id="55ba3-125">此属性始终是可通过以下方法[IMAPIProp::SaveChanges](imapiprop-savechanges.md)第一次调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="55ba3-125">This property is always available through the [IMAPIProp::GetProps](imapiprop-getprops.md) method following the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="55ba3-126">某些提供程序可以使其可实例化后立即。</span><span class="sxs-lookup"><span data-stu-id="55ba3-126">Some providers can make it available immediately after instantiation.</span></span> 
  
<span data-ttu-id="55ba3-127">客户端或服务提供程序可以将此属性的值进行比较使用 memcmp。</span><span class="sxs-lookup"><span data-stu-id="55ba3-127">A client or service provider can compare values from this property by using memcmp.</span></span> <span data-ttu-id="55ba3-128">此方法不可行的条目标识符值。</span><span class="sxs-lookup"><span data-stu-id="55ba3-128">This is not possible for entry identifier values.</span></span> <span data-ttu-id="55ba3-129">但是，保证此属性是唯一的相同的消息存储中或通讯簿容器;从不同的容器的两个对象可以具有相同的此属性的值。</span><span class="sxs-lookup"><span data-stu-id="55ba3-129">However, this property is guaranteed to be unique within the same message store or address book container; two objects from different containers can have the same value of this property.</span></span>
  
<span data-ttu-id="55ba3-130">一个记录和搜索键之间的区别是记录密钥是特定于该对象，而搜索关键字可以复制到其他对象。</span><span class="sxs-lookup"><span data-stu-id="55ba3-130">One distinction between the record and search keys is that the record key is specific to the object, whereas the search key can be copied to other objects.</span></span> <span data-ttu-id="55ba3-131">例如，两个对象的副本可以具有相同的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 值，但必须具有不同的值，此属性。</span><span class="sxs-lookup"><span data-stu-id="55ba3-131">For example, two copies of the object can have the same **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) value but must have different values for this property.</span></span>
  
<span data-ttu-id="55ba3-132">下表总结了**PR_ENTRYID**、 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 和此属性之间的重要不同之处。</span><span class="sxs-lookup"><span data-stu-id="55ba3-132">The following table summarizes important differences among **PR_ENTRYID**, **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) and this property.</span></span> 
  
|<span data-ttu-id="55ba3-133">**特征**</span><span class="sxs-lookup"><span data-stu-id="55ba3-133">**Characteristic**</span></span>|<span data-ttu-id="55ba3-134">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="55ba3-134">**PR_ENTRYID**</span></span>|<span data-ttu-id="55ba3-135">**PR_RECORD_KEY**</span><span class="sxs-lookup"><span data-stu-id="55ba3-135">**PR_RECORD_KEY**</span></span>|<span data-ttu-id="55ba3-136">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="55ba3-136">**PR_SEARCH_KEY**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55ba3-137">Attachment 对象上所需</span><span class="sxs-lookup"><span data-stu-id="55ba3-137">Required on attachment objects</span></span>  <br/> |<span data-ttu-id="55ba3-138">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-138">No</span></span>  <br/> |<span data-ttu-id="55ba3-139">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-139">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-140">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-140">No</span></span>  <br/> |
|<span data-ttu-id="55ba3-141">需要对文件夹对象</span><span class="sxs-lookup"><span data-stu-id="55ba3-141">Required on folder objects</span></span>  <br/> |<span data-ttu-id="55ba3-142">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-142">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-143">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-143">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-144">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-144">No</span></span>  <br/> |
|<span data-ttu-id="55ba3-145">消息存储对象上所需</span><span class="sxs-lookup"><span data-stu-id="55ba3-145">Required on message store objects</span></span>  <br/> |<span data-ttu-id="55ba3-146">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-146">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-147">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-147">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-148">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-148">No</span></span>  <br/> |
|<span data-ttu-id="55ba3-149">状态对象上所需</span><span class="sxs-lookup"><span data-stu-id="55ba3-149">Required on status objects</span></span>  <br/> |<span data-ttu-id="55ba3-150">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-150">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-151">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-151">No</span></span>  <br/> |<span data-ttu-id="55ba3-152">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-152">No</span></span>  <br/> |
|<span data-ttu-id="55ba3-153">可创建由客户端</span><span class="sxs-lookup"><span data-stu-id="55ba3-153">Creatable by client</span></span>  <br/> |<span data-ttu-id="55ba3-154">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-154">No</span></span>  <br/> |<span data-ttu-id="55ba3-155">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-155">No</span></span>  <br/> |<span data-ttu-id="55ba3-156">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-156">Yes</span></span>  <br/> |
|<span data-ttu-id="55ba3-157">**SaveChanges**调用前可用</span><span class="sxs-lookup"><span data-stu-id="55ba3-157">Available before a call to **SaveChanges**</span></span> <br/> |<span data-ttu-id="55ba3-158">也许</span><span class="sxs-lookup"><span data-stu-id="55ba3-158">Maybe</span></span>  <br/> |<span data-ttu-id="55ba3-159">也许</span><span class="sxs-lookup"><span data-stu-id="55ba3-159">Maybe</span></span>  <br/> |<span data-ttu-id="55ba3-160">邮件可能是其他人</span><span class="sxs-lookup"><span data-stu-id="55ba3-160">Messages Yes Others Maybe</span></span>  <br/> |
|<span data-ttu-id="55ba3-161">复制操作中发生的更改</span><span class="sxs-lookup"><span data-stu-id="55ba3-161">Changed in a copy operation</span></span>  <br/> |<span data-ttu-id="55ba3-162">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-162">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-163">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-163">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-164">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-164">No</span></span>  <br/> |
|<span data-ttu-id="55ba3-165">可更改后副本的客户端</span><span class="sxs-lookup"><span data-stu-id="55ba3-165">Changeable by a client after a copy</span></span>  <br/> |<span data-ttu-id="55ba3-166">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-166">No</span></span>  <br/> |<span data-ttu-id="55ba3-167">否</span><span class="sxs-lookup"><span data-stu-id="55ba3-167">No</span></span>  <br/> |<span data-ttu-id="55ba3-168">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-168">Yes</span></span>  <br/> |
|<span data-ttu-id="55ba3-169">中的唯一...</span><span class="sxs-lookup"><span data-stu-id="55ba3-169">Unique within ...</span></span>  <br/> |<span data-ttu-id="55ba3-170">整个 world</span><span class="sxs-lookup"><span data-stu-id="55ba3-170">Entire world</span></span>  <br/> |<span data-ttu-id="55ba3-171">提供程序实例</span><span class="sxs-lookup"><span data-stu-id="55ba3-171">Provider instance</span></span>  <br/> |<span data-ttu-id="55ba3-172">整个 world</span><span class="sxs-lookup"><span data-stu-id="55ba3-172">Entire world</span></span>  <br/> |
|<span data-ttu-id="55ba3-173">二进制 （与 memcmp) 相当</span><span class="sxs-lookup"><span data-stu-id="55ba3-173">Binary comparable (as with memcmp)</span></span>  <br/> |<span data-ttu-id="55ba3-174">否 — 使用**IMAPISupport:: CompareEntryIDs**</span><span class="sxs-lookup"><span data-stu-id="55ba3-174">No -- use **IMAPISupport:: CompareEntryIDs**</span></span> <br/> |<span data-ttu-id="55ba3-175">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-175">Yes</span></span>  <br/> |<span data-ttu-id="55ba3-176">是</span><span class="sxs-lookup"><span data-stu-id="55ba3-176">Yes</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="55ba3-177">相关资源</span><span class="sxs-lookup"><span data-stu-id="55ba3-177">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="55ba3-178">协议规范</span><span class="sxs-lookup"><span data-stu-id="55ba3-178">Protocol specifications</span></span>

<span data-ttu-id="55ba3-179">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="55ba3-179">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="55ba3-180">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="55ba3-180">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="55ba3-181">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="55ba3-181">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="55ba3-182">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="55ba3-182">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="55ba3-183">[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="55ba3-183">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="55ba3-184">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="55ba3-184">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="55ba3-185">头文件</span><span class="sxs-lookup"><span data-stu-id="55ba3-185">Header files</span></span>

<span data-ttu-id="55ba3-186">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="55ba3-186">Mapidefs.h</span></span>
  
> <span data-ttu-id="55ba3-187">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="55ba3-187">Provides data type definitions.</span></span>
    
<span data-ttu-id="55ba3-188">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="55ba3-188">Mapitags.h</span></span>
  
> <span data-ttu-id="55ba3-189">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="55ba3-189">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="55ba3-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55ba3-190">See also</span></span>



[<span data-ttu-id="55ba3-191">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="55ba3-191">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="55ba3-192">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="55ba3-192">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="55ba3-193">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="55ba3-193">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="55ba3-194">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="55ba3-194">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

