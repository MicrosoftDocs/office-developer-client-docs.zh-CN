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
ms.openlocfilehash: 61176ec6f9ff00fa5a38a2b385cb5281fa40961e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777412"
---
# <a name="pidtagconflictitems-canonical-property"></a><span data-ttu-id="700be-103">PidTagConflictItems 规范属性</span><span class="sxs-lookup"><span data-stu-id="700be-103">PidTagConflictItems Canonical Property</span></span>

  
  
<span data-ttu-id="700be-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="700be-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="700be-105">包含一个或多个条目都已参与自动冲突解决中的项的 Id。</span><span class="sxs-lookup"><span data-stu-id="700be-105">Contains one or more entry IDs of items that have been involved in an automatic conflict resolution.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="700be-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="700be-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="700be-107">PR_CONFLICT_ITEMS</span><span class="sxs-lookup"><span data-stu-id="700be-107">PR_CONFLICT_ITEMS</span></span>  <br/> |
|<span data-ttu-id="700be-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="700be-108">Identifier:</span></span>  <br/> |<span data-ttu-id="700be-109">0x1098</span><span class="sxs-lookup"><span data-stu-id="700be-109">0x1098</span></span>  <br/> |
|<span data-ttu-id="700be-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="700be-110">Property type:</span></span>  <br/> |<span data-ttu-id="700be-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="700be-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="700be-112">区域：</span><span class="sxs-lookup"><span data-stu-id="700be-112">Area:</span></span>  <br/> |<span data-ttu-id="700be-113">ICS</span><span class="sxs-lookup"><span data-stu-id="700be-113">ICS</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="700be-114">说明</span><span class="sxs-lookup"><span data-stu-id="700be-114">Remarks</span></span>

<span data-ttu-id="700be-115">标准支持自动冲突解决的 Microsoft Outlook 项目的类型包括以下类型的标准项： 约会项目、 联系人项目、 日记项目、 邮件项目、 会议项目、 粘滞便笺项目和任务项。</span><span class="sxs-lookup"><span data-stu-id="700be-115">The types of standard Microsoft Outlook items that support automatic conflict resolution include the following standard item types: appointment items, contact items, journal items, mail items, meeting items, sticky note items, and task items.</span></span> <span data-ttu-id="700be-116">项目属于邮件类派生的其中一种标准的项目类型还支持自动冲突解决。</span><span class="sxs-lookup"><span data-stu-id="700be-116">An item belonging to a message class that derives from one of these standard item types also supports automatic conflict resolution.</span></span> <span data-ttu-id="700be-117">在 Microsoft Outlook 2003 和 Microsoft Office Outlook 2007 中，当 Outlook 同步项目，并考虑存在可能产生的副本可能不包含所有的基本数据，Outlook 存储**冲突**的冲突副本**同步问题**文件夹下的文件夹。</span><span class="sxs-lookup"><span data-stu-id="700be-117">In Microsoft Outlook 2003 and Microsoft Office Outlook 2007, when Outlook synchronizes items and considers that there is a possibility that the resultant copy may not contain all essential data, Outlook stores the conflicting copies in the **Conflicts** folder, under the **Sync Issues** folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="700be-118">**同步问题**及其子文件夹处于隐藏状态的直到您单击**转到**菜单上的**文件夹列表**。</span><span class="sxs-lookup"><span data-stu-id="700be-118">**Sync Issues** and its subfolders are hidden until you click **Folder List** on the **Go** menu.</span></span> 
  
<span data-ttu-id="700be-119">项目公开**PR_CONFLICT_ITEMS**属性，如果它是支持自动冲突解决项类型之一，赢得解决冲突，或者被由于冲突解决放在**冲突**文件夹。</span><span class="sxs-lookup"><span data-stu-id="700be-119">An item exposes the **PR_CONFLICT_ITEMS** property if it is one of the item types that support automatic conflict resolution, has won in a conflict resolution, or was placed in the **Conflicts** folder because of a conflict resolution.</span></span> <span data-ttu-id="700be-120">在其中放置项目的文件夹确定**PR_CONFLICT_ITEMS**的内容。</span><span class="sxs-lookup"><span data-stu-id="700be-120">The folder in which the item is placed determines the content of **PR_CONFLICT_ITEMS**.</span></span> <span data-ttu-id="700be-121">如果项目位于之外**冲突**文件夹中，某些文件夹和项目公开**PR_CONFLICT_ITEMS**属性，项必须具有赢冲突解决，和**PR_CONFLICT_ITEMS**将包含的一个或多个条目 Id指定在冲突解决中丢失的那些项目。</span><span class="sxs-lookup"><span data-stu-id="700be-121">If the item is located in some folder other than the **Conflicts** folder, and the item exposes the **PR_CONFLICT_ITEMS** property, the item must have won the conflict resolution, and **PR_CONFLICT_ITEMS** would contain one or more entry IDs of those items that lost in the conflict resolution.</span></span> <span data-ttu-id="700be-122">如果项目位于**冲突**文件夹和项目公开**PR_CONFLICT_ITEMS**属性，此项必须丢失冲突解决中，并且**PR_CONFLICT_ITEMS**会包含赢得冲突中的项目的条目 ID解决方法。</span><span class="sxs-lookup"><span data-stu-id="700be-122">If the item is located in the **Conflicts** folder and the item exposes the **PR_CONFLICT_ITEMS** property, this item must have lost the conflict resolution, and **PR_CONFLICT_ITEMS** would contain the entry ID of the item that won in the conflict resolution.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="700be-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="700be-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="700be-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="700be-124">Protocol specifications</span></span>

<span data-ttu-id="700be-125">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="700be-125">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="700be-126">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="700be-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="700be-127">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="700be-127">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="700be-128">同步服务器和客户端之间的消息对象数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="700be-128">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="700be-129">头文件</span><span class="sxs-lookup"><span data-stu-id="700be-129">Header files</span></span>

<span data-ttu-id="700be-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="700be-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="700be-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="700be-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="700be-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="700be-132">Mapitags.h</span></span>
  
> <span data-ttu-id="700be-133">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="700be-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="700be-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="700be-134">See also</span></span>



[<span data-ttu-id="700be-135">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="700be-135">About MAPI Additions</span></span>](about-mapi-additions.md)
  
[<span data-ttu-id="700be-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="700be-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="700be-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="700be-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="700be-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="700be-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="700be-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="700be-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

