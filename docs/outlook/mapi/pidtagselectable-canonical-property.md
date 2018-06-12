---
title: PidTagSelectable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSelectable
api_type:
- COM
ms.assetid: eeecd957-dd50-4849-9698-8bc7106301e9
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 225c435107ba79183c737ddb8e09cda1ffbd83f4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778365"
---
# <a name="pidtagselectable-canonical-property"></a><span data-ttu-id="6ebdf-103">PidTagSelectable 规范属性</span><span class="sxs-lookup"><span data-stu-id="6ebdf-103">PidTagSelectable Canonical Property</span></span>

  
  
<span data-ttu-id="6ebdf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6ebdf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6ebdf-105">包含 TRUE，则可以选择一次性表中的条目。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-105">Contains TRUE if the entry in the one-off table can be selected.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6ebdf-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="6ebdf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6ebdf-107">PR_SELECTABLE</span><span class="sxs-lookup"><span data-stu-id="6ebdf-107">PR_SELECTABLE</span></span>  <br/> |
|<span data-ttu-id="6ebdf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6ebdf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6ebdf-109">0x3609</span><span class="sxs-lookup"><span data-stu-id="6ebdf-109">0x3609</span></span>  <br/> |
|<span data-ttu-id="6ebdf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6ebdf-110">Data type:</span></span>  <br/> |<span data-ttu-id="6ebdf-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6ebdf-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="6ebdf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6ebdf-112">Area:</span></span>  <br/> |<span data-ttu-id="6ebdf-113">通讯簿容器</span><span class="sxs-lookup"><span data-stu-id="6ebdf-113">Address book container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6ebdf-114">备注</span><span class="sxs-lookup"><span data-stu-id="6ebdf-114">Remarks</span></span>

<span data-ttu-id="6ebdf-115">此属性主要用于可视一次性表的格式设置。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-115">This property is used primarily for visual formatting of a one-off table.</span></span> <span data-ttu-id="6ebdf-116">模板可以通过创建指示组标题条目进行分组。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-116">Templates can be grouped by creating an entry that indicates the heading for the group.</span></span> <span data-ttu-id="6ebdf-117">此属性设置为 FALSE 的标题，则确保用户可以组和不此标题条目的选择实际的模板。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-117">Setting this property to FALSE for the heading ensures that the user can select only the actual templates in the group and not this heading entry.</span></span> 
  
<span data-ttu-id="6ebdf-118">此属性仅适用于一次性表，不适用于通讯簿层次结构表。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-118">This property applies only to a one-off table, not to an address book hierarchy table.</span></span> 
  
<span data-ttu-id="6ebdf-119">MAPI 允许直观地通过两种方法对项目进行分组的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-119">MAPI allows an address book provider to group items visually by two means.</span></span> <span data-ttu-id="6ebdf-120">首先，某些行可以充当标题的不可选择。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-120">First, certain rows can function as headings by being unselectable.</span></span> <span data-ttu-id="6ebdf-121">其次，可以使用**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性相对于其标题缩可选项目。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-121">Second, the selectable items can be indented relative to their headings by using the **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) property.</span></span> <span data-ttu-id="6ebdf-122">此属性在此类分组中用于指示此项目可选择列表中创建一个一次性地址。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-122">This property is used in such grouping to indicate whether or not this item can be selected from a list to create a one-off address.</span></span> <span data-ttu-id="6ebdf-123">例如，如果客户端有几个模板构建传真地址，它可以如下所示显示这些：</span><span class="sxs-lookup"><span data-stu-id="6ebdf-123">For example, if a client has several templates for building fax addresses, it can display them as follows:</span></span> 
  
<span data-ttu-id="6ebdf-124">传真模板 （深度 0，不可选）</span><span class="sxs-lookup"><span data-stu-id="6ebdf-124">FAX templates (depth 0, not selectable)</span></span>
  
 <span data-ttu-id="6ebdf-125">本地 （深度 1，可选）</span><span class="sxs-lookup"><span data-stu-id="6ebdf-125">Local (depth 1, selectable)</span></span> 
  
 <span data-ttu-id="6ebdf-126">长途 （深度 1，可选）</span><span class="sxs-lookup"><span data-stu-id="6ebdf-126">Long-distance (depth 1, selectable)</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6ebdf-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="6ebdf-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6ebdf-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="6ebdf-128">Protocol specifications</span></span>

<span data-ttu-id="6ebdf-129">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6ebdf-129">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6ebdf-130">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-130">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6ebdf-131">[[MS OXOABKT]](http://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6ebdf-131">[[MS-OXOABKT]](http://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6ebdf-132">指定的属性和操作所允许的地址簿模板。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-132">Specifies the properties and operations that are permissible for address book templates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6ebdf-133">头文件</span><span class="sxs-lookup"><span data-stu-id="6ebdf-133">Header files</span></span>

<span data-ttu-id="6ebdf-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6ebdf-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="6ebdf-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="6ebdf-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6ebdf-136">Mapitags.h</span></span>
  
> <span data-ttu-id="6ebdf-137">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6ebdf-137">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6ebdf-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ebdf-138">See also</span></span>



[<span data-ttu-id="6ebdf-139">IABLogon::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="6ebdf-139">IABLogon::GetOneOffTable</span></span>](iablogon-getoneofftable.md)
  
[<span data-ttu-id="6ebdf-140">PidTagFolderType 规范属性</span><span class="sxs-lookup"><span data-stu-id="6ebdf-140">PidTagFolderType Canonical Property</span></span>](pidtagfoldertype-canonical-property.md)


[<span data-ttu-id="6ebdf-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6ebdf-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6ebdf-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6ebdf-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6ebdf-143">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6ebdf-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6ebdf-144">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6ebdf-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

