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
# <a name="pidtagconflictitems-canonical-property"></a><span data-ttu-id="aa539-103">PidTagConflictItems 规范属性</span><span class="sxs-lookup"><span data-stu-id="aa539-103">PidTagConflictItems Canonical Property</span></span>

  
  
<span data-ttu-id="aa539-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa539-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa539-105">包含自动冲突解决中涉及的项目的一个或多个条目 ID。</span><span class="sxs-lookup"><span data-stu-id="aa539-105">Contains one or more entry IDs of items that have been involved in an automatic conflict resolution.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="aa539-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="aa539-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="aa539-107">PR_CONFLICT_ITEMS</span><span class="sxs-lookup"><span data-stu-id="aa539-107">PR_CONFLICT_ITEMS</span></span>  <br/> |
|<span data-ttu-id="aa539-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="aa539-108">Identifier:</span></span>  <br/> |<span data-ttu-id="aa539-109">0x1098</span><span class="sxs-lookup"><span data-stu-id="aa539-109">0x1098</span></span>  <br/> |
|<span data-ttu-id="aa539-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="aa539-110">Property type:</span></span>  <br/> |<span data-ttu-id="aa539-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="aa539-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="aa539-112">区域：</span><span class="sxs-lookup"><span data-stu-id="aa539-112">Area:</span></span>  <br/> |<span data-ttu-id="aa539-113">ICS</span><span class="sxs-lookup"><span data-stu-id="aa539-113">ICS</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="aa539-114">备注</span><span class="sxs-lookup"><span data-stu-id="aa539-114">Remarks</span></span>

<span data-ttu-id="aa539-115">支持自动冲突解决的标准 Microsoft Outlook项目类型包括以下标准项目类型：约会项目、联系人项目、日记项目、邮件项目、会议项目、便笺项目和任务项目。</span><span class="sxs-lookup"><span data-stu-id="aa539-115">The types of standard Microsoft Outlook items that support automatic conflict resolution include the following standard item types: appointment items, contact items, journal items, mail items, meeting items, sticky note items, and task items.</span></span> <span data-ttu-id="aa539-116">属于派生自其中一个标准项目类型的邮件类的项目还支持自动冲突解决。</span><span class="sxs-lookup"><span data-stu-id="aa539-116">An item belonging to a message class that derives from one of these standard item types also supports automatic conflict resolution.</span></span> <span data-ttu-id="aa539-117">在 Microsoft Outlook 2003 和 Microsoft Office Outlook 2007 中，当 Outlook 同步项目并考虑结果副本可能不包含所有必需数据时，Outlook 将冲突副本存储在"同步问题"文件夹下的 **"冲突**"文件夹中。 </span><span class="sxs-lookup"><span data-stu-id="aa539-117">In Microsoft Outlook 2003 and Microsoft Office Outlook 2007, when Outlook synchronizes items and considers that there is a possibility that the resultant copy may not contain all essential data, Outlook stores the conflicting copies in the **Conflicts** folder, under the **Sync Issues** folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="aa539-118">**在单击"** 开始"菜单上的"文件夹列表"之前，将隐藏"同步问题 **"\*\*\*\*及其子文件夹**。</span><span class="sxs-lookup"><span data-stu-id="aa539-118">**Sync Issues** and its subfolders are hidden until you click **Folder List** on the **Go** menu.</span></span> 
  
<span data-ttu-id="aa539-119">如果项目 **是支持自动冲突解决的项目** 类型之一、在冲突解决中获胜或由于冲突解决而放置在"冲突"文件夹中，则该项目将公开 PR_CONFLICT_ITEMS 属性。</span><span class="sxs-lookup"><span data-stu-id="aa539-119">An item exposes the **PR_CONFLICT_ITEMS** property if it is one of the item types that support automatic conflict resolution, has won in a conflict resolution, or was placed in the **Conflicts** folder because of a conflict resolution.</span></span> <span data-ttu-id="aa539-120">项目放置在其中的文件夹决定了项目 **PR_CONFLICT_ITEMS。**</span><span class="sxs-lookup"><span data-stu-id="aa539-120">The folder in which the item is placed determines the content of **PR_CONFLICT_ITEMS**.</span></span> <span data-ttu-id="aa539-121">如果项目位于"冲突"文件夹外的其他文件夹中，并且该项目公开 **了 PR_CONFLICT_ITEMS** 属性，则该项目必须获得冲突解决 **，PR_CONFLICT_ITEMS** 将包含冲突解决中丢失的项目的一个或多个条目 ID。</span><span class="sxs-lookup"><span data-stu-id="aa539-121">If the item is located in some folder other than the **Conflicts** folder, and the item exposes the **PR_CONFLICT_ITEMS** property, the item must have won the conflict resolution, and **PR_CONFLICT_ITEMS** would contain one or more entry IDs of those items that lost in the conflict resolution.</span></span> <span data-ttu-id="aa539-122">如果项目位于"冲突"文件夹中，并且该项目公开 **了 PR_CONFLICT_ITEMS** 属性，则此项目必须已失去冲突解决 **，PR_CONFLICT_ITEMS** 将包含在冲突解决中赢得的项目的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="aa539-122">If the item is located in the **Conflicts** folder and the item exposes the **PR_CONFLICT_ITEMS** property, this item must have lost the conflict resolution, and **PR_CONFLICT_ITEMS** would contain the entry ID of the item that won in the conflict resolution.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="aa539-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="aa539-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="aa539-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="aa539-124">Protocol specifications</span></span>

<span data-ttu-id="aa539-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aa539-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="aa539-126">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="aa539-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="aa539-127">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aa539-127">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="aa539-128">处理在服务器和客户端之间同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="aa539-128">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="aa539-129">头文件</span><span class="sxs-lookup"><span data-stu-id="aa539-129">Header files</span></span>

<span data-ttu-id="aa539-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="aa539-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="aa539-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="aa539-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="aa539-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="aa539-132">Mapitags.h</span></span>
  
> <span data-ttu-id="aa539-133">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="aa539-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="aa539-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa539-134">See also</span></span>



[<span data-ttu-id="aa539-135">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="aa539-135">About MAPI Additions</span></span>](about-mapi-additions.md)
  
[<span data-ttu-id="aa539-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="aa539-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="aa539-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="aa539-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="aa539-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="aa539-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="aa539-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="aa539-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

