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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355263"
---
# <a name="pidtagrecordkey-canonical-property"></a><span data-ttu-id="eb418-103">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="eb418-103">PidTagRecordKey Canonical Property</span></span>

  
  
<span data-ttu-id="eb418-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eb418-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eb418-105">包含特定对象的唯一的二进制可比较标识符。</span><span class="sxs-lookup"><span data-stu-id="eb418-105">Contains a unique binary-comparable identifier for a specific object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eb418-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="eb418-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="eb418-107">PR_RECORD_KEY</span><span class="sxs-lookup"><span data-stu-id="eb418-107">PR_RECORD_KEY</span></span>  <br/> |
|<span data-ttu-id="eb418-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="eb418-108">Identifier:</span></span>  <br/> |<span data-ttu-id="eb418-109">0x0FF9</span><span class="sxs-lookup"><span data-stu-id="eb418-109">0x0FF9</span></span>  <br/> |
|<span data-ttu-id="eb418-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="eb418-110">Data type:</span></span>  <br/> |<span data-ttu-id="eb418-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="eb418-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="eb418-112">区域：</span><span class="sxs-lookup"><span data-stu-id="eb418-112">Area:</span></span>  <br/> |<span data-ttu-id="eb418-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="eb418-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eb418-114">注解</span><span class="sxs-lookup"><span data-stu-id="eb418-114">Remarks</span></span>

<span data-ttu-id="eb418-115">此属性有利于查找对某个对象的引用, 例如, 在内容表中查找其行。</span><span class="sxs-lookup"><span data-stu-id="eb418-115">This property facilitates locating references to an object, such as finding its row in a contents table.</span></span> <span data-ttu-id="eb418-116">此属性不能用于打开对象;为该目的使用条目标识符。</span><span class="sxs-lookup"><span data-stu-id="eb418-116">This property cannot be used to open an object; use the entry identifier for that purpose.</span></span>
  
<span data-ttu-id="eb418-117">应通过此属性在邮件中唯一标识附件子属性。</span><span class="sxs-lookup"><span data-stu-id="eb418-117">An attachment subobject should be uniquely identified within a message by this property.</span></span> <span data-ttu-id="eb418-118">此标识符是在关闭并重新打开邮件后, 保证其保持不变的唯一附件特征。</span><span class="sxs-lookup"><span data-stu-id="eb418-118">This identifier is the only attachment characteristic guaranteed to stay the same after the message is closed and reopened.</span></span> <span data-ttu-id="eb418-119">存储提供程序必须跨会话保留此属性, 以确保此保证。</span><span class="sxs-lookup"><span data-stu-id="eb418-119">The store provider must preserve this property across sessions to ensure this guarantee.</span></span>
  
<span data-ttu-id="eb418-120">对于文件夹, 此属性包含在文件夹层次结构表中使用的密钥。</span><span class="sxs-lookup"><span data-stu-id="eb418-120">For folders, this property contains a key used in the folder hierarchy table.</span></span> <span data-ttu-id="eb418-121">通常情况下, 这与**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性提供的值相同。</span><span class="sxs-lookup"><span data-stu-id="eb418-121">Typically this is the same value as that provided by the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="eb418-122">对于邮件存储区, 此属性与**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) 属性相同。</span><span class="sxs-lookup"><span data-stu-id="eb418-122">For message stores, this property is identical to the **PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="eb418-123">在邮件存储对象中, 此属性在所有存储提供程序中应是唯一的。</span><span class="sxs-lookup"><span data-stu-id="eb418-123">In a message store object, this property should be unique across all store providers.</span></span> <span data-ttu-id="eb418-124">执行此操作的一种方法是, 将**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性的值与特定邮件存储区的[GUID](guid.md)结构或其他值进行合并 (该提供程序类型唯一) 的值。</span><span class="sxs-lookup"><span data-stu-id="eb418-124">One way to do this is to combine the value of the **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) property for the store (unique to that provider type) with a [GUID](guid.md) structure or other value unique to the specific message store.</span></span> 
  
<span data-ttu-id="eb418-125">在第一次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法后, 此属性始终可通过[IMAPIProp:: GetProps](imapiprop-getprops.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="eb418-125">This property is always available through the [IMAPIProp::GetProps](imapiprop-getprops.md) method following the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="eb418-126">某些提供程序可使其在实例化后立即可用。</span><span class="sxs-lookup"><span data-stu-id="eb418-126">Some providers can make it available immediately after instantiation.</span></span> 
  
<span data-ttu-id="eb418-127">客户端或服务提供程序可以使用 memcmp 比较此属性中的值。</span><span class="sxs-lookup"><span data-stu-id="eb418-127">A client or service provider can compare values from this property by using memcmp.</span></span> <span data-ttu-id="eb418-128">对于条目标识符值, 这是不可能的。</span><span class="sxs-lookup"><span data-stu-id="eb418-128">This is not possible for entry identifier values.</span></span> <span data-ttu-id="eb418-129">但是, 此属性在同一邮件存储或通讯簿容器中保证是唯一的;来自不同容器的两个对象可以具有该属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="eb418-129">However, this property is guaranteed to be unique within the same message store or address book container; two objects from different containers can have the same value of this property.</span></span>
  
<span data-ttu-id="eb418-130">记录和搜索关键字之间的一种区别在于, 该记录键是特定于该对象的, 而搜索关键字可以复制到其他对象。</span><span class="sxs-lookup"><span data-stu-id="eb418-130">One distinction between the record and search keys is that the record key is specific to the object, whereas the search key can be copied to other objects.</span></span> <span data-ttu-id="eb418-131">例如, 两个对象副本可以具有相同的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 值, 但必须具有此属性的不同值。</span><span class="sxs-lookup"><span data-stu-id="eb418-131">For example, two copies of the object can have the same **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) value but must have different values for this property.</span></span>
  
<span data-ttu-id="eb418-132">下表汇总了**PR_ENTRYID**、 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 和此属性之间的重要区别。</span><span class="sxs-lookup"><span data-stu-id="eb418-132">The following table summarizes important differences among **PR_ENTRYID**, **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) and this property.</span></span> 
  
|<span data-ttu-id="eb418-133">**特征**</span><span class="sxs-lookup"><span data-stu-id="eb418-133">**Characteristic**</span></span>|<span data-ttu-id="eb418-134">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="eb418-134">**PR_ENTRYID**</span></span>|<span data-ttu-id="eb418-135">**PR_RECORD_KEY**</span><span class="sxs-lookup"><span data-stu-id="eb418-135">**PR_RECORD_KEY**</span></span>|<span data-ttu-id="eb418-136">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="eb418-136">**PR_SEARCH_KEY**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb418-137">对附件对象是必需的</span><span class="sxs-lookup"><span data-stu-id="eb418-137">Required on attachment objects</span></span>  <br/> |<span data-ttu-id="eb418-138">否</span><span class="sxs-lookup"><span data-stu-id="eb418-138">No</span></span>  <br/> |<span data-ttu-id="eb418-139">是</span><span class="sxs-lookup"><span data-stu-id="eb418-139">Yes</span></span>  <br/> |<span data-ttu-id="eb418-140">否</span><span class="sxs-lookup"><span data-stu-id="eb418-140">No</span></span>  <br/> |
|<span data-ttu-id="eb418-141">对 folder 对象是必需的</span><span class="sxs-lookup"><span data-stu-id="eb418-141">Required on folder objects</span></span>  <br/> |<span data-ttu-id="eb418-142">是</span><span class="sxs-lookup"><span data-stu-id="eb418-142">Yes</span></span>  <br/> |<span data-ttu-id="eb418-143">是</span><span class="sxs-lookup"><span data-stu-id="eb418-143">Yes</span></span>  <br/> |<span data-ttu-id="eb418-144">否</span><span class="sxs-lookup"><span data-stu-id="eb418-144">No</span></span>  <br/> |
|<span data-ttu-id="eb418-145">对邮件存储对象是必需的</span><span class="sxs-lookup"><span data-stu-id="eb418-145">Required on message store objects</span></span>  <br/> |<span data-ttu-id="eb418-146">是</span><span class="sxs-lookup"><span data-stu-id="eb418-146">Yes</span></span>  <br/> |<span data-ttu-id="eb418-147">是</span><span class="sxs-lookup"><span data-stu-id="eb418-147">Yes</span></span>  <br/> |<span data-ttu-id="eb418-148">否</span><span class="sxs-lookup"><span data-stu-id="eb418-148">No</span></span>  <br/> |
|<span data-ttu-id="eb418-149">对状态对象是必需的</span><span class="sxs-lookup"><span data-stu-id="eb418-149">Required on status objects</span></span>  <br/> |<span data-ttu-id="eb418-150">是</span><span class="sxs-lookup"><span data-stu-id="eb418-150">Yes</span></span>  <br/> |<span data-ttu-id="eb418-151">否</span><span class="sxs-lookup"><span data-stu-id="eb418-151">No</span></span>  <br/> |<span data-ttu-id="eb418-152">否</span><span class="sxs-lookup"><span data-stu-id="eb418-152">No</span></span>  <br/> |
|<span data-ttu-id="eb418-153">可由客户端创建</span><span class="sxs-lookup"><span data-stu-id="eb418-153">Creatable by client</span></span>  <br/> |<span data-ttu-id="eb418-154">否</span><span class="sxs-lookup"><span data-stu-id="eb418-154">No</span></span>  <br/> |<span data-ttu-id="eb418-155">否</span><span class="sxs-lookup"><span data-stu-id="eb418-155">No</span></span>  <br/> |<span data-ttu-id="eb418-156">是</span><span class="sxs-lookup"><span data-stu-id="eb418-156">Yes</span></span>  <br/> |
|<span data-ttu-id="eb418-157">在调用**SaveChanges**之前可用</span><span class="sxs-lookup"><span data-stu-id="eb418-157">Available before a call to **SaveChanges**</span></span> <br/> |<span data-ttu-id="eb418-158">也</span><span class="sxs-lookup"><span data-stu-id="eb418-158">Maybe</span></span>  <br/> |<span data-ttu-id="eb418-159">也</span><span class="sxs-lookup"><span data-stu-id="eb418-159">Maybe</span></span>  <br/> |<span data-ttu-id="eb418-160">邮件是其他可能的</span><span class="sxs-lookup"><span data-stu-id="eb418-160">Messages Yes Others Maybe</span></span>  <br/> |
|<span data-ttu-id="eb418-161">在复制操作中更改</span><span class="sxs-lookup"><span data-stu-id="eb418-161">Changed in a copy operation</span></span>  <br/> |<span data-ttu-id="eb418-162">是</span><span class="sxs-lookup"><span data-stu-id="eb418-162">Yes</span></span>  <br/> |<span data-ttu-id="eb418-163">是</span><span class="sxs-lookup"><span data-stu-id="eb418-163">Yes</span></span>  <br/> |<span data-ttu-id="eb418-164">否</span><span class="sxs-lookup"><span data-stu-id="eb418-164">No</span></span>  <br/> |
|<span data-ttu-id="eb418-165">在复制后, 客户端可对其进行更改</span><span class="sxs-lookup"><span data-stu-id="eb418-165">Changeable by a client after a copy</span></span>  <br/> |<span data-ttu-id="eb418-166">否</span><span class="sxs-lookup"><span data-stu-id="eb418-166">No</span></span>  <br/> |<span data-ttu-id="eb418-167">否</span><span class="sxs-lookup"><span data-stu-id="eb418-167">No</span></span>  <br/> |<span data-ttu-id="eb418-168">是</span><span class="sxs-lookup"><span data-stu-id="eb418-168">Yes</span></span>  <br/> |
|<span data-ttu-id="eb418-169">中的唯一 .。。</span><span class="sxs-lookup"><span data-stu-id="eb418-169">Unique within ...</span></span>  <br/> |<span data-ttu-id="eb418-170">整个世界</span><span class="sxs-lookup"><span data-stu-id="eb418-170">Entire world</span></span>  <br/> |<span data-ttu-id="eb418-171">提供程序实例</span><span class="sxs-lookup"><span data-stu-id="eb418-171">Provider instance</span></span>  <br/> |<span data-ttu-id="eb418-172">整个世界</span><span class="sxs-lookup"><span data-stu-id="eb418-172">Entire world</span></span>  <br/> |
|<span data-ttu-id="eb418-173">二进制可比较 (与 memcmp 一样)</span><span class="sxs-lookup"><span data-stu-id="eb418-173">Binary comparable (as with memcmp)</span></span>  <br/> |<span data-ttu-id="eb418-174">No--use **IMAPISupport:: CompareEntryIDs**</span><span class="sxs-lookup"><span data-stu-id="eb418-174">No -- use **IMAPISupport:: CompareEntryIDs**</span></span> <br/> |<span data-ttu-id="eb418-175">是</span><span class="sxs-lookup"><span data-stu-id="eb418-175">Yes</span></span>  <br/> |<span data-ttu-id="eb418-176">是</span><span class="sxs-lookup"><span data-stu-id="eb418-176">Yes</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="eb418-177">相关资源</span><span class="sxs-lookup"><span data-stu-id="eb418-177">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="eb418-178">协议规范</span><span class="sxs-lookup"><span data-stu-id="eb418-178">Protocol specifications</span></span>

<span data-ttu-id="eb418-179">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eb418-179">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eb418-180">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="eb418-180">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="eb418-181">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eb418-181">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eb418-182">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="eb418-182">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="eb418-183">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eb418-183">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eb418-184">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="eb418-184">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="eb418-185">头文件</span><span class="sxs-lookup"><span data-stu-id="eb418-185">Header files</span></span>

<span data-ttu-id="eb418-186">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="eb418-186">Mapidefs.h</span></span>
  
> <span data-ttu-id="eb418-187">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="eb418-187">Provides data type definitions.</span></span>
    
<span data-ttu-id="eb418-188">Mapitags</span><span class="sxs-lookup"><span data-stu-id="eb418-188">Mapitags.h</span></span>
  
> <span data-ttu-id="eb418-189">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="eb418-189">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eb418-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb418-190">See also</span></span>



[<span data-ttu-id="eb418-191">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="eb418-191">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="eb418-192">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="eb418-192">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="eb418-193">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="eb418-193">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="eb418-194">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="eb418-194">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

