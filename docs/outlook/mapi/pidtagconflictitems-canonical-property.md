---
title: PidTagConflictItems 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagConflictItems
api_type:
- HeaderDef
ms.assetid: 0d147827-f0e2-dcc1-4427-c4a2f48ca801
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 83940d9239bc172d5fab76232f6644f0e89033b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338015"
---
# <a name="pidtagconflictitems-canonical-property"></a><span data-ttu-id="7bb1f-103">PidTagConflictItems 规范属性</span><span class="sxs-lookup"><span data-stu-id="7bb1f-103">PidTagConflictItems Canonical Property</span></span>

  
  
<span data-ttu-id="7bb1f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7bb1f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7bb1f-105">包含自动冲突解决中涉及的项目的一个或多个条目 id。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-105">Contains one or more entry IDs of items that have been involved in an automatic conflict resolution.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="7bb1f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7bb1f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7bb1f-107">PR_CONFLICT_ITEMS</span><span class="sxs-lookup"><span data-stu-id="7bb1f-107">PR_CONFLICT_ITEMS</span></span>  <br/> |
|<span data-ttu-id="7bb1f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7bb1f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7bb1f-109">0x1098</span><span class="sxs-lookup"><span data-stu-id="7bb1f-109">0x1098</span></span>  <br/> |
|<span data-ttu-id="7bb1f-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="7bb1f-110">Property type:</span></span>  <br/> |<span data-ttu-id="7bb1f-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="7bb1f-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="7bb1f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7bb1f-112">Area:</span></span>  <br/> |<span data-ttu-id="7bb1f-113">用作</span><span class="sxs-lookup"><span data-stu-id="7bb1f-113">ICS</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7bb1f-114">注解</span><span class="sxs-lookup"><span data-stu-id="7bb1f-114">Remarks</span></span>

<span data-ttu-id="7bb1f-115">支持自动冲突解决的标准 Microsoft Outlook 项目的类型包括以下标准项类型: 约会项、联系人项、日记项、邮件项、会议项、便笺项和任务项。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-115">The types of standard Microsoft Outlook items that support automatic conflict resolution include the following standard item types: appointment items, contact items, journal items, mail items, meeting items, sticky note items, and task items.</span></span> <span data-ttu-id="7bb1f-116">属于从这些标准项目类型之一派生的邮件类的项目也支持自动冲突解决。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-116">An item belonging to a message class that derives from one of these standard item types also supports automatic conflict resolution.</span></span> <span data-ttu-id="7bb1f-117">在 microsoft Outlook 2003 和 microsoft Office outlook 2007 中, 当 Outlook 同步项目并认为生成的副本可能不包含所有重要数据时, outlook 会将冲突副本存储在**冲突**中文件夹中的 "**同步问题**" 文件夹下。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-117">In Microsoft Outlook 2003 and Microsoft Office Outlook 2007, when Outlook synchronizes items and considers that there is a possibility that the resultant copy may not contain all essential data, Outlook stores the conflicting copies in the **Conflicts** folder, under the **Sync Issues** folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7bb1f-118">除非您单击 "**转到**" 菜单上的 "**文件夹列表**", 否则**同步问题**及其子文件夹将被隐藏。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-118">**Sync Issues** and its subfolders are hidden until you click **Folder List** on the **Go** menu.</span></span> 
  
<span data-ttu-id="7bb1f-119">如果项目类型是支持自动冲突解决的项目类型之一, 已赢得冲突解决, 或者由于冲突解决而被置于**冲突**文件夹中, 则该项目会公开**PR_CONFLICT_ITEMS**属性。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-119">An item exposes the **PR_CONFLICT_ITEMS** property if it is one of the item types that support automatic conflict resolution, has won in a conflict resolution, or was placed in the **Conflicts** folder because of a conflict resolution.</span></span> <span data-ttu-id="7bb1f-120">放置项的文件夹将决定**PR_CONFLICT_ITEMS**的内容。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-120">The folder in which the item is placed determines the content of **PR_CONFLICT_ITEMS**.</span></span> <span data-ttu-id="7bb1f-121">如果项位于 "**冲突**" 文件夹之外的某个文件夹中, 并且该项公开了**PR_CONFLICT_ITEMS**属性, 则该项目必须赢得冲突解决, 并且**PR_CONFLICT_ITEMS**将包含一个或多个条目 id冲突解决中丢失的那些项目。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-121">If the item is located in some folder other than the **Conflicts** folder, and the item exposes the **PR_CONFLICT_ITEMS** property, the item must have won the conflict resolution, and **PR_CONFLICT_ITEMS** would contain one or more entry IDs of those items that lost in the conflict resolution.</span></span> <span data-ttu-id="7bb1f-122">如果项位于 "**冲突**" 文件夹中, 并且该项公开了**PR_CONFLICT_ITEMS**属性, 则此项必须已丢失冲突解决, 并且**PR_CONFLICT_ITEMS**将包含冲突中赢得的项的条目 ID。办法.</span><span class="sxs-lookup"><span data-stu-id="7bb1f-122">If the item is located in the **Conflicts** folder and the item exposes the **PR_CONFLICT_ITEMS** property, this item must have lost the conflict resolution, and **PR_CONFLICT_ITEMS** would contain the entry ID of the item that won in the conflict resolution.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7bb1f-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="7bb1f-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7bb1f-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="7bb1f-124">Protocol specifications</span></span>

<span data-ttu-id="7bb1f-125">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7bb1f-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7bb1f-126">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7bb1f-127">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7bb1f-127">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7bb1f-128">处理服务器和客户端之间的同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-128">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7bb1f-129">头文件</span><span class="sxs-lookup"><span data-stu-id="7bb1f-129">Header files</span></span>

<span data-ttu-id="7bb1f-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7bb1f-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="7bb1f-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="7bb1f-132">Mapitags</span><span class="sxs-lookup"><span data-stu-id="7bb1f-132">Mapitags.h</span></span>
  
> <span data-ttu-id="7bb1f-133">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7bb1f-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7bb1f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bb1f-134">See also</span></span>



[<span data-ttu-id="7bb1f-135">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="7bb1f-135">About MAPI Additions</span></span>](about-mapi-additions.md)
  
[<span data-ttu-id="7bb1f-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7bb1f-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7bb1f-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7bb1f-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7bb1f-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7bb1f-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7bb1f-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7bb1f-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

