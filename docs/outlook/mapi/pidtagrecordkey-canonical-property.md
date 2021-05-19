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
# <a name="pidtagrecordkey-canonical-property"></a><span data-ttu-id="e9f3b-103">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9f3b-103">PidTagRecordKey Canonical Property</span></span>

  
  
<span data-ttu-id="e9f3b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9f3b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e9f3b-105">包含特定对象的唯一二进制比较标识符。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-105">Contains a unique binary-comparable identifier for a specific object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e9f3b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e9f3b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e9f3b-107">PR_RECORD_KEY</span><span class="sxs-lookup"><span data-stu-id="e9f3b-107">PR_RECORD_KEY</span></span>  <br/> |
|<span data-ttu-id="e9f3b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e9f3b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e9f3b-109">0x0FF9</span><span class="sxs-lookup"><span data-stu-id="e9f3b-109">0x0FF9</span></span>  <br/> |
|<span data-ttu-id="e9f3b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e9f3b-110">Data type:</span></span>  <br/> |<span data-ttu-id="e9f3b-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e9f3b-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e9f3b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e9f3b-112">Area:</span></span>  <br/> |<span data-ttu-id="e9f3b-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="e9f3b-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e9f3b-114">备注</span><span class="sxs-lookup"><span data-stu-id="e9f3b-114">Remarks</span></span>

<span data-ttu-id="e9f3b-115">此属性便于查找对对象的引用，如在内容表中查找其行。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-115">This property facilitates locating references to an object, such as finding its row in a contents table.</span></span> <span data-ttu-id="e9f3b-116">此属性不能用于打开对象;将条目标识符用于该目的。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-116">This property cannot be used to open an object; use the entry identifier for that purpose.</span></span>
  
<span data-ttu-id="e9f3b-117">附件子对象应在邮件中通过此属性进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-117">An attachment subobject should be uniquely identified within a message by this property.</span></span> <span data-ttu-id="e9f3b-118">此标识符是唯一保证在关闭并重新打开邮件后保持不变的附件特征。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-118">This identifier is the only attachment characteristic guaranteed to stay the same after the message is closed and reopened.</span></span> <span data-ttu-id="e9f3b-119">存储提供程序必须跨会话保留此属性以确保此保证。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-119">The store provider must preserve this property across sessions to ensure this guarantee.</span></span>
  
<span data-ttu-id="e9f3b-120">对于文件夹，此属性包含文件夹层次结构表中使用的键。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-120">For folders, this property contains a key used in the folder hierarchy table.</span></span> <span data-ttu-id="e9f3b-121">通常，此值与[PidTagEntryId](pidtagentryid-canonical-property.md)  PR_ENTRYID (提供的值) 相同。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-121">Typically this is the same value as that provided by the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="e9f3b-122">对于邮件存储，此属性与[PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md) PR_STORE_RECORD_KEY (属性) 相同。 </span><span class="sxs-lookup"><span data-stu-id="e9f3b-122">For message stores, this property is identical to the **PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="e9f3b-123">在邮件存储对象中，此属性在所有存储提供程序中应是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-123">In a message store object, this property should be unique across all store providers.</span></span> <span data-ttu-id="e9f3b-124">实现此目标的方法之一是，将存储的 **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性值与提供程序类型) 所特有的 (属性值与 [GUID](guid.md) 结构或其他特定于特定邮件存储的值组合在一起。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-124">One way to do this is to combine the value of the **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) property for the store (unique to that provider type) with a [GUID](guid.md) structure or other value unique to the specific message store.</span></span> 
  
<span data-ttu-id="e9f3b-125">首次调用[IMAPIProp：：SaveChanges 方法后，此属性始终可以通过 IMAPIProp：：GetProps](imapiprop-savechanges.md)方法使用。 [](imapiprop-getprops.md)</span><span class="sxs-lookup"><span data-stu-id="e9f3b-125">This property is always available through the [IMAPIProp::GetProps](imapiprop-getprops.md) method following the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="e9f3b-126">某些提供程序可以在实例化后立即提供。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-126">Some providers can make it available immediately after instantiation.</span></span> 
  
<span data-ttu-id="e9f3b-127">客户端或服务提供商可以使用 memcmp 比较此属性的值。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-127">A client or service provider can compare values from this property by using memcmp.</span></span> <span data-ttu-id="e9f3b-128">条目标识符值不能这样做。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-128">This is not possible for entry identifier values.</span></span> <span data-ttu-id="e9f3b-129">但是，此属性保证在同一邮件存储或通讯簿容器中是唯一的;不同容器中的两个对象可以具有相同的此属性的值。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-129">However, this property is guaranteed to be unique within the same message store or address book container; two objects from different containers can have the same value of this property.</span></span>
  
<span data-ttu-id="e9f3b-130">记录和搜索键之间的一个区别是记录键特定于对象，而搜索键可以复制到其他对象。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-130">One distinction between the record and search keys is that the record key is specific to the object, whereas the search key can be copied to other objects.</span></span> <span data-ttu-id="e9f3b-131">例如，该对象的两个副本的[PidTagSearchKey PR_SEARCH_KEY (PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 值相同，但此属性必须具有不同的值。 </span><span class="sxs-lookup"><span data-stu-id="e9f3b-131">For example, two copies of the object can have the same **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) value but must have different values for this property.</span></span>
  
<span data-ttu-id="e9f3b-132">下表总结了 PidTagSearchKey PR_ENTRYID **、PR_SEARCH_KEY** **(** [PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 和此属性之间的重要差异。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-132">The following table summarizes important differences among **PR_ENTRYID**, **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) and this property.</span></span> 
  
|<span data-ttu-id="e9f3b-133">**特征**</span><span class="sxs-lookup"><span data-stu-id="e9f3b-133">**Characteristic**</span></span>|<span data-ttu-id="e9f3b-134">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="e9f3b-134">**PR_ENTRYID**</span></span>|<span data-ttu-id="e9f3b-135">**PR_RECORD_KEY**</span><span class="sxs-lookup"><span data-stu-id="e9f3b-135">**PR_RECORD_KEY**</span></span>|<span data-ttu-id="e9f3b-136">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="e9f3b-136">**PR_SEARCH_KEY**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e9f3b-137">附件对象上必需</span><span class="sxs-lookup"><span data-stu-id="e9f3b-137">Required on attachment objects</span></span>  <br/> |<span data-ttu-id="e9f3b-138">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-138">No</span></span>  <br/> |<span data-ttu-id="e9f3b-139">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-139">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-140">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-140">No</span></span>  <br/> |
|<span data-ttu-id="e9f3b-141">文件夹对象上必需</span><span class="sxs-lookup"><span data-stu-id="e9f3b-141">Required on folder objects</span></span>  <br/> |<span data-ttu-id="e9f3b-142">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-142">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-143">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-143">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-144">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-144">No</span></span>  <br/> |
|<span data-ttu-id="e9f3b-145">在邮件存储对象上是必需的</span><span class="sxs-lookup"><span data-stu-id="e9f3b-145">Required on message store objects</span></span>  <br/> |<span data-ttu-id="e9f3b-146">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-146">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-147">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-147">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-148">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-148">No</span></span>  <br/> |
|<span data-ttu-id="e9f3b-149">状态对象上必需</span><span class="sxs-lookup"><span data-stu-id="e9f3b-149">Required on status objects</span></span>  <br/> |<span data-ttu-id="e9f3b-150">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-150">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-151">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-151">No</span></span>  <br/> |<span data-ttu-id="e9f3b-152">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-152">No</span></span>  <br/> |
|<span data-ttu-id="e9f3b-153">按客户端创建</span><span class="sxs-lookup"><span data-stu-id="e9f3b-153">Creatable by client</span></span>  <br/> |<span data-ttu-id="e9f3b-154">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-154">No</span></span>  <br/> |<span data-ttu-id="e9f3b-155">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-155">No</span></span>  <br/> |<span data-ttu-id="e9f3b-156">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-156">Yes</span></span>  <br/> |
|<span data-ttu-id="e9f3b-157">在调用 **SaveChanges 之前可用**</span><span class="sxs-lookup"><span data-stu-id="e9f3b-157">Available before a call to **SaveChanges**</span></span> <br/> |<span data-ttu-id="e9f3b-158">也许</span><span class="sxs-lookup"><span data-stu-id="e9f3b-158">Maybe</span></span>  <br/> |<span data-ttu-id="e9f3b-159">也许</span><span class="sxs-lookup"><span data-stu-id="e9f3b-159">Maybe</span></span>  <br/> |<span data-ttu-id="e9f3b-160">消息是其他可能</span><span class="sxs-lookup"><span data-stu-id="e9f3b-160">Messages Yes Others Maybe</span></span>  <br/> |
|<span data-ttu-id="e9f3b-161">复制操作中已更改</span><span class="sxs-lookup"><span data-stu-id="e9f3b-161">Changed in a copy operation</span></span>  <br/> |<span data-ttu-id="e9f3b-162">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-162">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-163">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-163">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-164">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-164">No</span></span>  <br/> |
|<span data-ttu-id="e9f3b-165">复制后客户端可更改</span><span class="sxs-lookup"><span data-stu-id="e9f3b-165">Changeable by a client after a copy</span></span>  <br/> |<span data-ttu-id="e9f3b-166">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-166">No</span></span>  <br/> |<span data-ttu-id="e9f3b-167">否</span><span class="sxs-lookup"><span data-stu-id="e9f3b-167">No</span></span>  <br/> |<span data-ttu-id="e9f3b-168">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-168">Yes</span></span>  <br/> |
|<span data-ttu-id="e9f3b-169">在 ... 中是唯一的</span><span class="sxs-lookup"><span data-stu-id="e9f3b-169">Unique within ...</span></span>  <br/> |<span data-ttu-id="e9f3b-170">整个世界</span><span class="sxs-lookup"><span data-stu-id="e9f3b-170">Entire world</span></span>  <br/> |<span data-ttu-id="e9f3b-171">提供程序实例</span><span class="sxs-lookup"><span data-stu-id="e9f3b-171">Provider instance</span></span>  <br/> |<span data-ttu-id="e9f3b-172">整个世界</span><span class="sxs-lookup"><span data-stu-id="e9f3b-172">Entire world</span></span>  <br/> |
|<span data-ttu-id="e9f3b-173">二进制 (与 memcmp) </span><span class="sxs-lookup"><span data-stu-id="e9f3b-173">Binary comparable (as with memcmp)</span></span>  <br/> |<span data-ttu-id="e9f3b-174">否 -- 使用 **IMAPISupport：： CompareEntryIDs**</span><span class="sxs-lookup"><span data-stu-id="e9f3b-174">No -- use **IMAPISupport:: CompareEntryIDs**</span></span> <br/> |<span data-ttu-id="e9f3b-175">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-175">Yes</span></span>  <br/> |<span data-ttu-id="e9f3b-176">是</span><span class="sxs-lookup"><span data-stu-id="e9f3b-176">Yes</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e9f3b-177">相关资源</span><span class="sxs-lookup"><span data-stu-id="e9f3b-177">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e9f3b-178">协议规范</span><span class="sxs-lookup"><span data-stu-id="e9f3b-178">Protocol specifications</span></span>

<span data-ttu-id="e9f3b-179">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9f3b-179">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e9f3b-180">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-180">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e9f3b-181">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9f3b-181">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e9f3b-182">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-182">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="e9f3b-183">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9f3b-183">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e9f3b-184">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-184">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e9f3b-185">头文件</span><span class="sxs-lookup"><span data-stu-id="e9f3b-185">Header files</span></span>

<span data-ttu-id="e9f3b-186">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e9f3b-186">Mapidefs.h</span></span>
  
> <span data-ttu-id="e9f3b-187">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-187">Provides data type definitions.</span></span>
    
<span data-ttu-id="e9f3b-188">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e9f3b-188">Mapitags.h</span></span>
  
> <span data-ttu-id="e9f3b-189">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e9f3b-189">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e9f3b-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9f3b-190">See also</span></span>



[<span data-ttu-id="e9f3b-191">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e9f3b-191">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e9f3b-192">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9f3b-192">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e9f3b-193">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e9f3b-193">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e9f3b-194">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e9f3b-194">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

