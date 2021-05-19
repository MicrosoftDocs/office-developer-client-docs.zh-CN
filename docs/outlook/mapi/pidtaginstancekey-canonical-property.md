---
title: PidTagInstanceKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInstanceKey
api_type:
- HeaderDef
ms.assetid: 14fc5571-acc0-4d75-8598-964aee5ba01c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c237149c305a80012d1f06ea4373b892d25daec1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358509"
---
# <a name="pidtaginstancekey-canonical-property"></a><span data-ttu-id="309e8-103">PidTagInstanceKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="309e8-103">PidTagInstanceKey Canonical Property</span></span>

  
  
<span data-ttu-id="309e8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="309e8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="309e8-105">包含一个值，该值唯一标识表格中的行。</span><span class="sxs-lookup"><span data-stu-id="309e8-105">Contains a value that uniquely identifies a row in a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="309e8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="309e8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="309e8-107">PR_INSTANCE_KEY</span><span class="sxs-lookup"><span data-stu-id="309e8-107">PR_INSTANCE_KEY</span></span>  <br/> |
|<span data-ttu-id="309e8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="309e8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="309e8-109">0x0FF6</span><span class="sxs-lookup"><span data-stu-id="309e8-109">0x0FF6</span></span>  <br/> |
|<span data-ttu-id="309e8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="309e8-110">Data type:</span></span>  <br/> |<span data-ttu-id="309e8-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="309e8-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="309e8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="309e8-112">Area:</span></span>  <br/> |<span data-ttu-id="309e8-113">表格</span><span class="sxs-lookup"><span data-stu-id="309e8-113">Table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="309e8-114">备注</span><span class="sxs-lookup"><span data-stu-id="309e8-114">Remarks</span></span>

<span data-ttu-id="309e8-115">此属性是一个二进制值，用于唯一标识表视图中的行。</span><span class="sxs-lookup"><span data-stu-id="309e8-115">This property is a binary value that uniquely identifies a row in a table view.</span></span> <span data-ttu-id="309e8-116">在大多数表中，它是必填列。</span><span class="sxs-lookup"><span data-stu-id="309e8-116">It is a required column in most tables.</span></span> <span data-ttu-id="309e8-117">如果一行包含在两个视图中，则有两个不同的实例键。</span><span class="sxs-lookup"><span data-stu-id="309e8-117">If a row is included in two views, there are two different instance keys.</span></span> <span data-ttu-id="309e8-118">每次打开表时，行的实例键可能有所不同，但在表打开时仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="309e8-118">The instance key of a row may differ each time the table is opened, but remains constant while the table is open.</span></span> <span data-ttu-id="309e8-119">使用表格时添加的行不会重复使用之前使用的实例键。</span><span class="sxs-lookup"><span data-stu-id="309e8-119">Rows added while a table is in use do not reuse an instance key that was previously used.</span></span> 
  
<span data-ttu-id="309e8-120">使用 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性可关联扩展的所有行。</span><span class="sxs-lookup"><span data-stu-id="309e8-120">Use the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) or **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) properties to correlate all the rows of an expansion.</span></span> <span data-ttu-id="309e8-121">使用 **PR_INSTANCE_KEY** 在扩展中查找特定实例。</span><span class="sxs-lookup"><span data-stu-id="309e8-121">Use **PR_INSTANCE_KEY** to locate a particular instance within the expansion.</span></span> 
  
<span data-ttu-id="309e8-122">在表中展开多值属性时，将针对每个扩展实例（即，针对该属性的每个值）创建一行。</span><span class="sxs-lookup"><span data-stu-id="309e8-122">When a multivalued property is expanded in a table, a row is created for each instance of the expansion, that is, for each value of that property.</span></span> <span data-ttu-id="309e8-123">每行对 **PR_INSTANCE_KEY** 具有唯一值，而所有其他列在整个扩展过程中保留其原始值。</span><span class="sxs-lookup"><span data-stu-id="309e8-123">Each row has a unique value for the **PR_INSTANCE_KEY** property, while all the other columns retain their original values throughout the expansion.</span></span> 
  
<span data-ttu-id="309e8-124">在表的分类排序中，可以将与实际数据不对应的行添加到排序结果中。</span><span class="sxs-lookup"><span data-stu-id="309e8-124">In a categorized sort of a table, rows not corresponding to actual data can be added to the result of the sort.</span></span> <span data-ttu-id="309e8-125">每个这样的行（如所有表中的所有行）都有其自己的唯一实例键。</span><span class="sxs-lookup"><span data-stu-id="309e8-125">Each such row, like all rows in all tables, has its own unique instance key.</span></span> 
  
 <span data-ttu-id="309e8-126">**PR_INSTANCE_KEY** 表事件通知中也使用。</span><span class="sxs-lookup"><span data-stu-id="309e8-126">**PR_INSTANCE_KEY** is also used in table event notifications.</span></span> <span data-ttu-id="309e8-127">TABLE_NOTIFICATION结构的 **propIndex** 和 **propPrior** 成员是 [SPropValue](spropvalue.md)结构，它们 **PR_INSTANCE_KEY值。** [](table_notification.md)</span><span class="sxs-lookup"><span data-stu-id="309e8-127">The **propIndex** and **propPrior** members of the [TABLE_NOTIFICATION](table_notification.md) structure are [SPropValue](spropvalue.md) structures holding **PR_INSTANCE_KEY** values.</span></span> <span data-ttu-id="309e8-128">**propIndex** 成员指示已添加或已更改的行。</span><span class="sxs-lookup"><span data-stu-id="309e8-128">The **propIndex** member indicates the row that was added or changed.</span></span> <span data-ttu-id="309e8-129">**propPrior** 成员指示行之前添加或更改的行 (PR_NULL表示第一行行) 。</span><span class="sxs-lookup"><span data-stu-id="309e8-129">The **propPrior** member indicates the row before the added or changed row (**PR_NULL** indicates a change to the first row).</span></span> 
  
<span data-ttu-id="309e8-130">此值不会作为显示表的一部分进行复制。</span><span class="sxs-lookup"><span data-stu-id="309e8-130">This value is not copied as part of the display table.</span></span> 
  
 <span data-ttu-id="309e8-131">**PR_INSTANCE_KEY** 是 [MAPIUID](mapiuid.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="309e8-131">**PR_INSTANCE_KEY** is a [MAPIUID](mapiuid.md) structure.</span></span> <span data-ttu-id="309e8-132">可以将所有实例键直接比较为二进制值。</span><span class="sxs-lookup"><span data-stu-id="309e8-132">All instance keys can be directly compared as binary values.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="309e8-133">相关资源</span><span class="sxs-lookup"><span data-stu-id="309e8-133">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="309e8-134">协议规范</span><span class="sxs-lookup"><span data-stu-id="309e8-134">Protocol specifications</span></span>

<span data-ttu-id="309e8-135">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="309e8-135">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="309e8-136">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="309e8-136">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="309e8-137">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="309e8-137">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="309e8-138">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="309e8-138">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="309e8-139">头文件</span><span class="sxs-lookup"><span data-stu-id="309e8-139">Header files</span></span>

<span data-ttu-id="309e8-140">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="309e8-140">Mapidefs.h</span></span>
  
> <span data-ttu-id="309e8-141">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="309e8-141">Provides data type definitions.</span></span>
    
<span data-ttu-id="309e8-142">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="309e8-142">Mapitags.h</span></span>
  
> <span data-ttu-id="309e8-143">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="309e8-143">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="309e8-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="309e8-144">See also</span></span>



[<span data-ttu-id="309e8-145">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="309e8-145">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="309e8-146">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="309e8-146">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="309e8-147">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="309e8-147">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="309e8-148">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="309e8-148">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

