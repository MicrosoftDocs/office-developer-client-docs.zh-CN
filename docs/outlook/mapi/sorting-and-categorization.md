---
title: 排序和分类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 853c48e4-ef5b-49da-b281-f72784c598ce
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 8a5a07cdeb7f000c9a7da24dbea1a42a6f9fc185
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344504"
---
# <a name="sorting-and-categorization"></a><span data-ttu-id="e72a6-103">排序和分类</span><span class="sxs-lookup"><span data-stu-id="e72a6-103">Sorting and Categorization</span></span>

 
  
<span data-ttu-id="e72a6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e72a6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e72a6-105">对表进行排序时, 会按对其查看器有意义的顺序放置行。</span><span class="sxs-lookup"><span data-stu-id="e72a6-105">Sorting a table places rows in an order that makes sense for its viewer.</span></span> <span data-ttu-id="e72a6-106">例如, 一个查看者可能更愿意查看按邮件主题排序的文件夹的内容表, 以便会话的所有线程都在一起, 而另一个查看器可能希望邮件按发件人的姓名进行排序。</span><span class="sxs-lookup"><span data-stu-id="e72a6-106">For example, one viewer might prefer to see the contents table of a folder sorted by message subject so that all the threads of a conversation are together while another viewer might want the messages sorted by the name of the sender.</span></span> <span data-ttu-id="e72a6-107">新实例化的表不一定以任何特定的顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="e72a6-107">A newly instantiated table is not necessarily sorted in any particular order.</span></span> 
  
<span data-ttu-id="e72a6-108">有两种类型的排序:</span><span class="sxs-lookup"><span data-stu-id="e72a6-108">There are two types of sorting:</span></span>
  
- <span data-ttu-id="e72a6-109">标准排序</span><span class="sxs-lookup"><span data-stu-id="e72a6-109">Standard sorting</span></span>
    
- <span data-ttu-id="e72a6-110">分类排序</span><span class="sxs-lookup"><span data-stu-id="e72a6-110">Categorized sorting</span></span> 
    
<span data-ttu-id="e72a6-111">使用标准排序, 所有行都显示在简单列表中, 使用一个或多个列作为排序关键字。</span><span class="sxs-lookup"><span data-stu-id="e72a6-111">With standard sorting, all of the rows are displayed in a flat list using one or more columns as a sort key.</span></span> <span data-ttu-id="e72a6-112">通过分类排序, 行以分层方式显示, 并显示一个或多个列作为排序关键字。</span><span class="sxs-lookup"><span data-stu-id="e72a6-112">With categorized sorting, the rows are displayed hierarchically with one or more columns as the sort key.</span></span> <span data-ttu-id="e72a6-113">在每个类别中, 都有一个特殊的标题行, 其中包含以下列。</span><span class="sxs-lookup"><span data-stu-id="e72a6-113">Within each category, there is a special heading row that contains the following columns.</span></span>
  
- <span data-ttu-id="e72a6-114">组成排序关键字的一个或多个列</span><span class="sxs-lookup"><span data-stu-id="e72a6-114">The column or columns that make up the sort key</span></span>
    
- <span data-ttu-id="e72a6-115">**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e72a6-115">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="e72a6-116">**PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e72a6-116">**PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="e72a6-117">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e72a6-117">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>
    
- <span data-ttu-id="e72a6-118">**PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e72a6-118">**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md))</span></span>
    
- <span data-ttu-id="e72a6-119">**PR_ROW_TYPE**([PidTagRowType](pidtagrowtype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e72a6-119">**PR_ROW_TYPE** ([PidTagRowType](pidtagrowtype-canonical-property.md))</span></span> 
    
<span data-ttu-id="e72a6-120">在标题行下缩进是表中的所有行, 其中包含值与排序关键字相匹配的列。</span><span class="sxs-lookup"><span data-stu-id="e72a6-120">Indented under the heading row are all the rows from the table that contain columns with values that match the sort key.</span></span> <span data-ttu-id="e72a6-121">这些行称为叶行。</span><span class="sxs-lookup"><span data-stu-id="e72a6-121">These rows are called the leaf rows.</span></span> <span data-ttu-id="e72a6-122">叶行包含列集中的所有列减去排序关键字列。</span><span class="sxs-lookup"><span data-stu-id="e72a6-122">Leaf rows contain all the columns in the column set minus the sort key columns.</span></span> 
  
<span data-ttu-id="e72a6-123">除了标准排序之外, 文件夹的内容表通常支持分类排序。</span><span class="sxs-lookup"><span data-stu-id="e72a6-123">The contents tables of folders often support categorized sorting in addition to standard sorting.</span></span> <span data-ttu-id="e72a6-124">通讯簿容器的内容表通常只支持标准排序。</span><span class="sxs-lookup"><span data-stu-id="e72a6-124">The contents tables of address book containers typically support only standard sorting.</span></span> 
  
<span data-ttu-id="e72a6-125">一个类别可以有两种状态: 折叠和展开。</span><span class="sxs-lookup"><span data-stu-id="e72a6-125">A category can have two states: collapsed and expanded.</span></span> <span data-ttu-id="e72a6-126">当类别处于折叠状态时, 仅从[IMAPITable:: QueryRows](imapitable-queryrows.md)返回标题行。</span><span class="sxs-lookup"><span data-stu-id="e72a6-126">When a category is in the collapsed state, only the heading row is returned from [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="e72a6-127">当类别处于展开状态时, 将返回与该类别相关的所有行。</span><span class="sxs-lookup"><span data-stu-id="e72a6-127">When a category is in the expanded state, all of the rows related to the category are returned.</span></span> <span data-ttu-id="e72a6-128">这包括标题行和叶行。</span><span class="sxs-lookup"><span data-stu-id="e72a6-128">This includes the heading row and the leaf rows.</span></span> 
  
<span data-ttu-id="e72a6-129">表视图中的每个类别都可以单独展开或折叠。</span><span class="sxs-lookup"><span data-stu-id="e72a6-129">Each category in a table view can be expanded or collapsed independently.</span></span> <span data-ttu-id="e72a6-130">也就是说, 并非所有类别都必须处于相同的状态。某些类别可以折叠, 而其他类别则展开。</span><span class="sxs-lookup"><span data-stu-id="e72a6-130">That is, not all categories must be in the same state at the same time; some categories can be collapsed while others are expanded.</span></span> 
  
<span data-ttu-id="e72a6-131">已分类的表格的用户决定它的显示方式。</span><span class="sxs-lookup"><span data-stu-id="e72a6-131">The user of a categorized table decides how it is displayed.</span></span> <span data-ttu-id="e72a6-132">一个常见的选项是使用 Windows SDK 中提供的一个名为 treeview 控件的控件。</span><span class="sxs-lookup"><span data-stu-id="e72a6-132">One common option is to use a control provided in the Windows SDK called the treeview control.</span></span> <span data-ttu-id="e72a6-133">Treeview 控件是支持树状结构中的信息的列表框。</span><span class="sxs-lookup"><span data-stu-id="e72a6-133">Treeview controls are list boxes that support information in a tree-like structure.</span></span> <span data-ttu-id="e72a6-134">展开状态中的类别的标题行标记为负号, 而折叠状态中的类别的标题行标有加号。</span><span class="sxs-lookup"><span data-stu-id="e72a6-134">Heading rows for categories in the expanded state are marked with a minus sign while heading rows for categories in the collapsed state are marked with a plus sign.</span></span> <span data-ttu-id="e72a6-135">展开的类别将显示在标题行下缩进的叶行。</span><span class="sxs-lookup"><span data-stu-id="e72a6-135">Expanded categories are displayed with the leaf rows indented under the heading rows.</span></span> 
  
<span data-ttu-id="e72a6-136">若要折叠和展开类别, 客户端应用程序或服务提供程序使用以下[IMAPITable: IUnknown](imapitableiunknown.md)方法:</span><span class="sxs-lookup"><span data-stu-id="e72a6-136">To collapse and expand a category, a client application or service provider uses the following [IMAPITable : IUnknown](imapitableiunknown.md) methods:</span></span> 
  
- [<span data-ttu-id="e72a6-137">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="e72a6-137">IMAPITable::GetCollapseState</span></span>](imapitable-getcollapsestate.md)
    
- [<span data-ttu-id="e72a6-138">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="e72a6-138">IMAPITable::SetCollapseState</span></span>](imapitable-setcollapsestate.md)
    
- [<span data-ttu-id="e72a6-139">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="e72a6-139">IMAPITable::ExpandRow</span></span>](imapitable-expandrow.md)
    
- [<span data-ttu-id="e72a6-140">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="e72a6-140">IMAPITable::CollapseRow</span></span>](imapitable-collapserow.md)
    
<span data-ttu-id="e72a6-141">有关对对话的线程进行排序的详细信息, 请参阅下列主题:</span><span class="sxs-lookup"><span data-stu-id="e72a6-141">For more information about sorting the threads of a conversation see the following topics:</span></span>
  
- [<span data-ttu-id="e72a6-142">SSortOrder</span><span class="sxs-lookup"><span data-stu-id="e72a6-142">SSortOrder</span></span>](ssortorder.md)
    
- [<span data-ttu-id="e72a6-143">PidTagSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="e72a6-143">PidTagSubject Canonical Property</span></span>](pidtagsubject-canonical-property.md)
    
- [<span data-ttu-id="e72a6-144">PidTagSubjectPrefix 规范属性</span><span class="sxs-lookup"><span data-stu-id="e72a6-144">PidTagSubjectPrefix Canonical Property</span></span>](pidtagsubjectprefix-canonical-property.md)
    
- [<span data-ttu-id="e72a6-145">PidTagNormalizedSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="e72a6-145">PidTagNormalizedSubject Canonical Property</span></span>](pidtagnormalizedsubject-canonical-property.md)
    
- [<span data-ttu-id="e72a6-146">PidTagConversationTopic 规范属性</span><span class="sxs-lookup"><span data-stu-id="e72a6-146">PidTagConversationTopic Canonical Property</span></span>](pidtagconversationtopic-canonical-property.md)
    
- [<span data-ttu-id="e72a6-147">PidTagConversationIndex 规范属性</span><span class="sxs-lookup"><span data-stu-id="e72a6-147">PidTagConversationIndex Canonical Property</span></span>](pidtagconversationindex-canonical-property.md)
    
- [<span data-ttu-id="e72a6-148">ScCreateConversationIndex</span><span class="sxs-lookup"><span data-stu-id="e72a6-148">ScCreateConversationIndex</span></span>](sccreateconversationindex.md)
    
- [<span data-ttu-id="e72a6-149">设置列和限制后对表排序</span><span class="sxs-lookup"><span data-stu-id="e72a6-149">Sorting Tables After Setting Columns and Restrictions</span></span>](sorting-tables-after-setting-columns-and-restrictions.md)
    
## <a name="see-also"></a><span data-ttu-id="e72a6-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e72a6-150">See also</span></span>



[<span data-ttu-id="e72a6-151">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="e72a6-151">MAPI Tables</span></span>](mapi-tables.md)

