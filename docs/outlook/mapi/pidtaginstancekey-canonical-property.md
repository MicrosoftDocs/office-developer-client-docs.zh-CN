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
ms.openlocfilehash: bc16e88035f091a4f42a03342a70e7e3a1da5e0c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777730"
---
# <a name="pidtaginstancekey-canonical-property"></a><span data-ttu-id="7162a-103">PidTagInstanceKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="7162a-103">PidTagInstanceKey Canonical Property</span></span>

  
  
<span data-ttu-id="7162a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7162a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7162a-105">包含唯一标识表中的行的值。</span><span class="sxs-lookup"><span data-stu-id="7162a-105">Contains a value that uniquely identifies a row in a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7162a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7162a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7162a-107">PR_INSTANCE_KEY</span><span class="sxs-lookup"><span data-stu-id="7162a-107">PR_INSTANCE_KEY</span></span>  <br/> |
|<span data-ttu-id="7162a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="7162a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7162a-109">0x0FF6</span><span class="sxs-lookup"><span data-stu-id="7162a-109">0x0FF6</span></span>  <br/> |
|<span data-ttu-id="7162a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7162a-110">Data type:</span></span>  <br/> |<span data-ttu-id="7162a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="7162a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="7162a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7162a-112">Area:</span></span>  <br/> |<span data-ttu-id="7162a-113">Table</span><span class="sxs-lookup"><span data-stu-id="7162a-113">Table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7162a-114">说明</span><span class="sxs-lookup"><span data-stu-id="7162a-114">Remarks</span></span>

<span data-ttu-id="7162a-115">此属性是唯一标识表视图中的行的二进制值。</span><span class="sxs-lookup"><span data-stu-id="7162a-115">This property is a binary value that uniquely identifies a row in a table view.</span></span> <span data-ttu-id="7162a-116">它是大多数表中所需的列。</span><span class="sxs-lookup"><span data-stu-id="7162a-116">It is a required column in most tables.</span></span> <span data-ttu-id="7162a-117">如果行包括在两个视图中，有两个不同的实例键。</span><span class="sxs-lookup"><span data-stu-id="7162a-117">If a row is included in two views, there are two different instance keys.</span></span> <span data-ttu-id="7162a-118">行的实例项可能不同每次打开表时，但打开表时均保持不变。</span><span class="sxs-lookup"><span data-stu-id="7162a-118">The instance key of a row may differ each time the table is opened, but remains constant while the table is open.</span></span> <span data-ttu-id="7162a-119">行添加在使用表时不要重新使用以前使用的实例键。</span><span class="sxs-lookup"><span data-stu-id="7162a-119">Rows added while a table is in use do not reuse an instance key that was previously used.</span></span> 
  
<span data-ttu-id="7162a-120">使用**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性用于关联的扩展的所有行。</span><span class="sxs-lookup"><span data-stu-id="7162a-120">Use the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) or **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) properties to correlate all the rows of an expansion.</span></span> <span data-ttu-id="7162a-121">使用**PR_INSTANCE_KEY**找到扩展中的特定实例。</span><span class="sxs-lookup"><span data-stu-id="7162a-121">Use **PR_INSTANCE_KEY** to locate a particular instance within the expansion.</span></span> 
  
<span data-ttu-id="7162a-122">表格中展开一个多值的属性时, 创建行的扩展，每个实例，即为该属性的每个值。</span><span class="sxs-lookup"><span data-stu-id="7162a-122">When a multivalued property is expanded in a table, a row is created for each instance of the expansion, that is, for each value of that property.</span></span> <span data-ttu-id="7162a-123">每行时的其他所有列都保留整个扩展其原始值都为**PR_INSTANCE_KEY**属性的唯一值。</span><span class="sxs-lookup"><span data-stu-id="7162a-123">Each row has a unique value for the **PR_INSTANCE_KEY** property, while all the other columns retain their original values throughout the expansion.</span></span> 
  
<span data-ttu-id="7162a-124">在表的分类排序，可以为排序的结果添加不对应于实际数据的行。</span><span class="sxs-lookup"><span data-stu-id="7162a-124">In a categorized sort of a table, rows not corresponding to actual data can be added to the result of the sort.</span></span> <span data-ttu-id="7162a-125">每个这样的行，如所有表中的所有行都有其自己的唯一实例密钥。</span><span class="sxs-lookup"><span data-stu-id="7162a-125">Each such row, like all rows in all tables, has its own unique instance key.</span></span> 
  
 <span data-ttu-id="7162a-126">**PR_INSTANCE_KEY**也可用于在表事件通知。</span><span class="sxs-lookup"><span data-stu-id="7162a-126">**PR_INSTANCE_KEY** is also used in table event notifications.</span></span> <span data-ttu-id="7162a-127">[TABLE_NOTIFICATION](table_notification.md)结构的**propIndex**和**propPrior**成员是[SPropValue](spropvalue.md)结构按住**PR_INSTANCE_KEY**值。</span><span class="sxs-lookup"><span data-stu-id="7162a-127">The **propIndex** and **propPrior** members of the [TABLE_NOTIFICATION](table_notification.md) structure are [SPropValue](spropvalue.md) structures holding **PR_INSTANCE_KEY** values.</span></span> <span data-ttu-id="7162a-128">**PropIndex**成员指示已添加或更改的行。</span><span class="sxs-lookup"><span data-stu-id="7162a-128">The **propIndex** member indicates the row that was added or changed.</span></span> <span data-ttu-id="7162a-129">**PropPrior**成员指示之前 （**PR_NULL**表示对第一行的更改） 的添加或更改行的行。</span><span class="sxs-lookup"><span data-stu-id="7162a-129">The **propPrior** member indicates the row before the added or changed row (**PR_NULL** indicates a change to the first row).</span></span> 
  
<span data-ttu-id="7162a-130">显示表的一部分不复制此值。</span><span class="sxs-lookup"><span data-stu-id="7162a-130">This value is not copied as part of the display table.</span></span> 
  
 <span data-ttu-id="7162a-131">**PR_INSTANCE_KEY**是一个[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="7162a-131">**PR_INSTANCE_KEY** is a [MAPIUID](mapiuid.md) structure.</span></span> <span data-ttu-id="7162a-132">可以直接将所有实例键都比较作为二进制值。</span><span class="sxs-lookup"><span data-stu-id="7162a-132">All instance keys can be directly compared as binary values.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7162a-133">相关资源</span><span class="sxs-lookup"><span data-stu-id="7162a-133">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7162a-134">协议规范</span><span class="sxs-lookup"><span data-stu-id="7162a-134">Protocol specifications</span></span>

<span data-ttu-id="7162a-135">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7162a-135">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7162a-136">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="7162a-136">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7162a-137">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7162a-137">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7162a-138">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="7162a-138">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7162a-139">头文件</span><span class="sxs-lookup"><span data-stu-id="7162a-139">Header files</span></span>

<span data-ttu-id="7162a-140">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7162a-140">Mapidefs.h</span></span>
  
> <span data-ttu-id="7162a-141">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7162a-141">Provides data type definitions.</span></span>
    
<span data-ttu-id="7162a-142">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7162a-142">Mapitags.h</span></span>
  
> <span data-ttu-id="7162a-143">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7162a-143">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7162a-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7162a-144">See also</span></span>



[<span data-ttu-id="7162a-145">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7162a-145">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7162a-146">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7162a-146">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7162a-147">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7162a-147">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7162a-148">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7162a-148">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

