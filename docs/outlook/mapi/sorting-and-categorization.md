---
title: 排序和分类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 853c48e4-ef5b-49da-b281-f72784c598ce
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 5e63d276d25a26f937e9b4f44575fea1030f52d0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778832"
---
# <a name="sorting-and-categorization"></a><span data-ttu-id="3f33b-103">排序和分类</span><span class="sxs-lookup"><span data-stu-id="3f33b-103">Sorting and Categorization</span></span>

 
  
<span data-ttu-id="3f33b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3f33b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3f33b-105">对表进行排序顺序为其查看器有意义放置行。</span><span class="sxs-lookup"><span data-stu-id="3f33b-105">Sorting a table places rows in an order that makes sense for its viewer.</span></span> <span data-ttu-id="3f33b-106">例如，一个查看器可能更愿意按邮件主题，以便的对话的所有线程都在一起时另一个查看器可能希望在按发件人名称的消息的文件夹的内容表，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3f33b-106">For example, one viewer might prefer to see the contents table of a folder sorted by message subject so that all the threads of a conversation are together while another viewer might want the messages sorted by the name of the sender.</span></span> <span data-ttu-id="3f33b-107">新实例化的表一定不按任何特定的顺序。</span><span class="sxs-lookup"><span data-stu-id="3f33b-107">A newly instantiated table is not necessarily sorted in any particular order.</span></span> 
  
<span data-ttu-id="3f33b-108">有两种类型的排序：</span><span class="sxs-lookup"><span data-stu-id="3f33b-108">There are two types of sorting:</span></span>
  
- <span data-ttu-id="3f33b-109">标准排序</span><span class="sxs-lookup"><span data-stu-id="3f33b-109">Standard sorting</span></span>
    
- <span data-ttu-id="3f33b-110">分类排序</span><span class="sxs-lookup"><span data-stu-id="3f33b-110">Categorized sorting</span></span> 
    
<span data-ttu-id="3f33b-111">使用标准排序的所有行使用一个或多个列作为排序关键字一个平面列表中显示。</span><span class="sxs-lookup"><span data-stu-id="3f33b-111">With standard sorting, all of the rows are displayed in a flat list using one or more columns as a sort key.</span></span> <span data-ttu-id="3f33b-112">与已分类排序，将行显示按层次结构与一个或多个列作为排序关键字。</span><span class="sxs-lookup"><span data-stu-id="3f33b-112">With categorized sorting, the rows are displayed hierarchically with one or more columns as the sort key.</span></span> <span data-ttu-id="3f33b-113">在每个类别中，没有包含以下列特殊的标题行。</span><span class="sxs-lookup"><span data-stu-id="3f33b-113">Within each category, there is a special heading row that contains the following columns.</span></span>
  
- <span data-ttu-id="3f33b-114">构成排序关键字的列</span><span class="sxs-lookup"><span data-stu-id="3f33b-114">The column or columns that make up the sort key</span></span>
    
- <span data-ttu-id="3f33b-115">**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3f33b-115">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="3f33b-116">**PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3f33b-116">**PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="3f33b-117">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3f33b-117">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>
    
- <span data-ttu-id="3f33b-118">**PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3f33b-118">**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md))</span></span>
    
- <span data-ttu-id="3f33b-119">**PR_ROW_TYPE**([PidTagRowType](pidtagrowtype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3f33b-119">**PR_ROW_TYPE** ([PidTagRowType](pidtagrowtype-canonical-property.md))</span></span> 
    
<span data-ttu-id="3f33b-120">标题行下缩进的表中包含值与相匹配的排序关键字列的所有行。</span><span class="sxs-lookup"><span data-stu-id="3f33b-120">Indented under the heading row are all the rows from the table that contain columns with values that match the sort key.</span></span> <span data-ttu-id="3f33b-121">这些行称为叶行。</span><span class="sxs-lookup"><span data-stu-id="3f33b-121">These rows are called the leaf rows.</span></span> <span data-ttu-id="3f33b-122">叶行包含设置减去排序键列列中的所有列。</span><span class="sxs-lookup"><span data-stu-id="3f33b-122">Leaf rows contain all the columns in the column set minus the sort key columns.</span></span> 
  
<span data-ttu-id="3f33b-123">文件夹的内容表通常支持除了标准排序分类排序。</span><span class="sxs-lookup"><span data-stu-id="3f33b-123">The contents tables of folders often support categorized sorting in addition to standard sorting.</span></span> <span data-ttu-id="3f33b-124">通讯簿容器的内容表通常支持仅标准排序。</span><span class="sxs-lookup"><span data-stu-id="3f33b-124">The contents tables of address book containers typically support only standard sorting.</span></span> 
  
<span data-ttu-id="3f33b-125">某个类别可有两种状态： 折叠和展开。</span><span class="sxs-lookup"><span data-stu-id="3f33b-125">A category can have two states: collapsed and expanded.</span></span> <span data-ttu-id="3f33b-126">折叠状态类别时，从[IMAPITable::QueryRows](imapitable-queryrows.md)返回仅标题行。</span><span class="sxs-lookup"><span data-stu-id="3f33b-126">When a category is in the collapsed state, only the heading row is returned from [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="3f33b-127">展开状态类别时，将返回所有与类别相关的行。</span><span class="sxs-lookup"><span data-stu-id="3f33b-127">When a category is in the expanded state, all of the rows related to the category are returned.</span></span> <span data-ttu-id="3f33b-128">这包括标题行和叶行。</span><span class="sxs-lookup"><span data-stu-id="3f33b-128">This includes the heading row and the leaf rows.</span></span> 
  
<span data-ttu-id="3f33b-129">可展开或折叠独立表视图中的每个类别。</span><span class="sxs-lookup"><span data-stu-id="3f33b-129">Each category in a table view can be expanded or collapsed independently.</span></span> <span data-ttu-id="3f33b-130">即，并非所有类别都必须位于相同的状态在同一时间;某些类别可以折叠时其他人扩展。</span><span class="sxs-lookup"><span data-stu-id="3f33b-130">That is, not all categories must be in the same state at the same time; some categories can be collapsed while others are expanded.</span></span> 
  
<span data-ttu-id="3f33b-131">分类表的用户决定显示方式。</span><span class="sxs-lookup"><span data-stu-id="3f33b-131">The user of a categorized table decides how it is displayed.</span></span> <span data-ttu-id="3f33b-132">一个常见选项是使用 Windows SDK 调用 treeview 控件中提供的控件。</span><span class="sxs-lookup"><span data-stu-id="3f33b-132">One common option is to use a control provided in the Windows SDK called the treeview control.</span></span> <span data-ttu-id="3f33b-133">Treeview 控件是在树状结构中支持信息的列表框。</span><span class="sxs-lookup"><span data-stu-id="3f33b-133">Treeview controls are list boxes that support information in a tree-like structure.</span></span> <span data-ttu-id="3f33b-134">处于展开状态的类别的标题行标记有减号时处于折叠状态的类别的标题行标记带加号。</span><span class="sxs-lookup"><span data-stu-id="3f33b-134">Heading rows for categories in the expanded state are marked with a minus sign while heading rows for categories in the collapsed state are marked with a plus sign.</span></span> <span data-ttu-id="3f33b-135">扩展的类别显示带有标题行下缩进的叶行。</span><span class="sxs-lookup"><span data-stu-id="3f33b-135">Expanded categories are displayed with the leaf rows indented under the heading rows.</span></span> 
  
<span data-ttu-id="3f33b-136">若要折叠和展开类别，客户端应用程序或服务提供商使用以下[IMAPITable: IUnknown](imapitableiunknown.md)方法：</span><span class="sxs-lookup"><span data-stu-id="3f33b-136">To collapse and expand a category, a client application or service provider uses the following [IMAPITable : IUnknown](imapitableiunknown.md) methods:</span></span> 
  
- [<span data-ttu-id="3f33b-137">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="3f33b-137">IMAPITable::GetCollapseState</span></span>](imapitable-getcollapsestate.md)
    
- [<span data-ttu-id="3f33b-138">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="3f33b-138">IMAPITable::SetCollapseState</span></span>](imapitable-setcollapsestate.md)
    
- [<span data-ttu-id="3f33b-139">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="3f33b-139">IMAPITable::ExpandRow</span></span>](imapitable-expandrow.md)
    
- [<span data-ttu-id="3f33b-140">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="3f33b-140">IMAPITable::CollapseRow</span></span>](imapitable-collapserow.md)
    
<span data-ttu-id="3f33b-141">有关排序的详细信息的对话线程，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="3f33b-141">For more information about sorting the threads of a conversation see the following topics:</span></span>
  
- [<span data-ttu-id="3f33b-142">SSortOrder</span><span class="sxs-lookup"><span data-stu-id="3f33b-142">SSortOrder</span></span>](ssortorder.md)
    
- [<span data-ttu-id="3f33b-143">PidTagSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f33b-143">PidTagSubject Canonical Property</span></span>](pidtagsubject-canonical-property.md)
    
- [<span data-ttu-id="3f33b-144">PidTagSubjectPrefix 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f33b-144">PidTagSubjectPrefix Canonical Property</span></span>](pidtagsubjectprefix-canonical-property.md)
    
- [<span data-ttu-id="3f33b-145">PidTagNormalizedSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f33b-145">PidTagNormalizedSubject Canonical Property</span></span>](pidtagnormalizedsubject-canonical-property.md)
    
- [<span data-ttu-id="3f33b-146">PidTagConversationTopic 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f33b-146">PidTagConversationTopic Canonical Property</span></span>](pidtagconversationtopic-canonical-property.md)
    
- [<span data-ttu-id="3f33b-147">PidTagConversationIndex 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f33b-147">PidTagConversationIndex Canonical Property</span></span>](pidtagconversationindex-canonical-property.md)
    
- [<span data-ttu-id="3f33b-148">ScCreateConversationIndex</span><span class="sxs-lookup"><span data-stu-id="3f33b-148">ScCreateConversationIndex</span></span>](sccreateconversationindex.md)
    
- [<span data-ttu-id="3f33b-149">设置列和限制后对表排序</span><span class="sxs-lookup"><span data-stu-id="3f33b-149">Sorting Tables After Setting Columns and Restrictions</span></span>](sorting-tables-after-setting-columns-and-restrictions.md)
    
## <a name="see-also"></a><span data-ttu-id="3f33b-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f33b-150">See also</span></span>



[<span data-ttu-id="3f33b-151">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="3f33b-151">MAPI Tables</span></span>](mapi-tables.md)

