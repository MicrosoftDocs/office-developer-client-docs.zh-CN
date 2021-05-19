---
title: 排序和分类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 853c48e4-ef5b-49da-b281-f72784c598ce
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: 8a5a07cdeb7f000c9a7da24dbea1a42a6f9fc185
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418482"
---
# <a name="sorting-and-categorization"></a><span data-ttu-id="40460-103">排序和分类</span><span class="sxs-lookup"><span data-stu-id="40460-103">Sorting and Categorization</span></span>

 
  
<span data-ttu-id="40460-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="40460-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="40460-105">对表进行排序会按对查看者有意义的顺序对行进行排序。</span><span class="sxs-lookup"><span data-stu-id="40460-105">Sorting a table places rows in an order that makes sense for its viewer.</span></span> <span data-ttu-id="40460-106">例如，一个查看者可能更希望查看按邮件主题排序的文件夹的内容表，以便对话的所有线程在一起，而另一个查看者可能希望邮件按发件人姓名排序。</span><span class="sxs-lookup"><span data-stu-id="40460-106">For example, one viewer might prefer to see the contents table of a folder sorted by message subject so that all the threads of a conversation are together while another viewer might want the messages sorted by the name of the sender.</span></span> <span data-ttu-id="40460-107">新实例化表不一定按任何特定顺序排序。</span><span class="sxs-lookup"><span data-stu-id="40460-107">A newly instantiated table is not necessarily sorted in any particular order.</span></span> 
  
<span data-ttu-id="40460-108">有两种类型的排序：</span><span class="sxs-lookup"><span data-stu-id="40460-108">There are two types of sorting:</span></span>
  
- <span data-ttu-id="40460-109">标准排序</span><span class="sxs-lookup"><span data-stu-id="40460-109">Standard sorting</span></span>
    
- <span data-ttu-id="40460-110">分类排序</span><span class="sxs-lookup"><span data-stu-id="40460-110">Categorized sorting</span></span> 
    
<span data-ttu-id="40460-111">使用标准排序，所有行都显示在一个简单列表一个或多个列作为排序键。</span><span class="sxs-lookup"><span data-stu-id="40460-111">With standard sorting, all of the rows are displayed in a flat list using one or more columns as a sort key.</span></span> <span data-ttu-id="40460-112">使用分类排序，这些行按层次结构显示，一列或多列作为排序键。</span><span class="sxs-lookup"><span data-stu-id="40460-112">With categorized sorting, the rows are displayed hierarchically with one or more columns as the sort key.</span></span> <span data-ttu-id="40460-113">在每个类别中，都有一个包含以下列的特殊标题行。</span><span class="sxs-lookup"><span data-stu-id="40460-113">Within each category, there is a special heading row that contains the following columns.</span></span>
  
- <span data-ttu-id="40460-114">组成排序键的列</span><span class="sxs-lookup"><span data-stu-id="40460-114">The column or columns that make up the sort key</span></span>
    
- <span data-ttu-id="40460-115">**PR_CONTENT_COUNT (** [PidTagContentCount](pidtagcontentcount-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="40460-115">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="40460-116">**PR_CONTENT_UNREAD (** [PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="40460-116">**PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="40460-117">**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="40460-117">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>
    
- <span data-ttu-id="40460-118">**PR_DEPTH (** [PidTagDepth](pidtagdepth-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="40460-118">**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md))</span></span>
    
- <span data-ttu-id="40460-119">**PR_ROW_TYPE (** [PidTagRowType](pidtagrowtype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="40460-119">**PR_ROW_TYPE** ([PidTagRowType](pidtagrowtype-canonical-property.md))</span></span> 
    
<span data-ttu-id="40460-120">标题行下缩进是表中所有包含与排序键匹配的值的列的行。</span><span class="sxs-lookup"><span data-stu-id="40460-120">Indented under the heading row are all the rows from the table that contain columns with values that match the sort key.</span></span> <span data-ttu-id="40460-121">这些行称为叶行。</span><span class="sxs-lookup"><span data-stu-id="40460-121">These rows are called the leaf rows.</span></span> <span data-ttu-id="40460-122">叶行包含列集的所有列减去排序键列。</span><span class="sxs-lookup"><span data-stu-id="40460-122">Leaf rows contain all the columns in the column set minus the sort key columns.</span></span> 
  
<span data-ttu-id="40460-123">文件夹的内容表通常除了支持标准排序之外，还支持分类排序。</span><span class="sxs-lookup"><span data-stu-id="40460-123">The contents tables of folders often support categorized sorting in addition to standard sorting.</span></span> <span data-ttu-id="40460-124">通讯簿容器的内容表通常仅支持标准排序。</span><span class="sxs-lookup"><span data-stu-id="40460-124">The contents tables of address book containers typically support only standard sorting.</span></span> 
  
<span data-ttu-id="40460-125">类别可以有两种状态：折叠和展开。</span><span class="sxs-lookup"><span data-stu-id="40460-125">A category can have two states: collapsed and expanded.</span></span> <span data-ttu-id="40460-126">当类别为折叠状态时，仅从 [IMAPITable：：QueryRows 返回标题行](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="40460-126">When a category is in the collapsed state, only the heading row is returned from [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="40460-127">当类别为展开状态时，将返回与类别相关的所有行。</span><span class="sxs-lookup"><span data-stu-id="40460-127">When a category is in the expanded state, all of the rows related to the category are returned.</span></span> <span data-ttu-id="40460-128">这包括标题行和叶行。</span><span class="sxs-lookup"><span data-stu-id="40460-128">This includes the heading row and the leaf rows.</span></span> 
  
<span data-ttu-id="40460-129">表视图中的每个类别都可以独立展开或折叠。</span><span class="sxs-lookup"><span data-stu-id="40460-129">Each category in a table view can be expanded or collapsed independently.</span></span> <span data-ttu-id="40460-130">也就是说，并非所有类别必须同时处于同一状态;某些类别可以折叠，而其他类别可以展开。</span><span class="sxs-lookup"><span data-stu-id="40460-130">That is, not all categories must be in the same state at the same time; some categories can be collapsed while others are expanded.</span></span> 
  
<span data-ttu-id="40460-131">已分类表的用户决定其显示方式。</span><span class="sxs-lookup"><span data-stu-id="40460-131">The user of a categorized table decides how it is displayed.</span></span> <span data-ttu-id="40460-132">一个常见选项是使用 Windows SDK 中提供的控件，称为树视图控件。</span><span class="sxs-lookup"><span data-stu-id="40460-132">One common option is to use a control provided in the Windows SDK called the treeview control.</span></span> <span data-ttu-id="40460-133">树视图控件是支持树状结构中的信息的列表框。</span><span class="sxs-lookup"><span data-stu-id="40460-133">Treeview controls are list boxes that support information in a tree-like structure.</span></span> <span data-ttu-id="40460-134">展开状态中类别的标题行标有减号，折叠状态中类别的标题行标有加号。</span><span class="sxs-lookup"><span data-stu-id="40460-134">Heading rows for categories in the expanded state are marked with a minus sign while heading rows for categories in the collapsed state are marked with a plus sign.</span></span> <span data-ttu-id="40460-135">展开的类别显示在标题行下缩进的叶行。</span><span class="sxs-lookup"><span data-stu-id="40460-135">Expanded categories are displayed with the leaf rows indented under the heading rows.</span></span> 
  
<span data-ttu-id="40460-136">为了折叠和展开类别，客户端应用程序或服务提供商使用下列 [IMAPITable ： IUnknown](imapitableiunknown.md) 方法：</span><span class="sxs-lookup"><span data-stu-id="40460-136">To collapse and expand a category, a client application or service provider uses the following [IMAPITable : IUnknown](imapitableiunknown.md) methods:</span></span> 
  
- [<span data-ttu-id="40460-137">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="40460-137">IMAPITable::GetCollapseState</span></span>](imapitable-getcollapsestate.md)
    
- [<span data-ttu-id="40460-138">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="40460-138">IMAPITable::SetCollapseState</span></span>](imapitable-setcollapsestate.md)
    
- [<span data-ttu-id="40460-139">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="40460-139">IMAPITable::ExpandRow</span></span>](imapitable-expandrow.md)
    
- [<span data-ttu-id="40460-140">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="40460-140">IMAPITable::CollapseRow</span></span>](imapitable-collapserow.md)
    
<span data-ttu-id="40460-141">有关对对话线程进行排序的信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="40460-141">For more information about sorting the threads of a conversation see the following topics:</span></span>
  
- [<span data-ttu-id="40460-142">SSortOrder</span><span class="sxs-lookup"><span data-stu-id="40460-142">SSortOrder</span></span>](ssortorder.md)
    
- [<span data-ttu-id="40460-143">PidTagSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="40460-143">PidTagSubject Canonical Property</span></span>](pidtagsubject-canonical-property.md)
    
- [<span data-ttu-id="40460-144">PidTagSubjectPrefix 规范属性</span><span class="sxs-lookup"><span data-stu-id="40460-144">PidTagSubjectPrefix Canonical Property</span></span>](pidtagsubjectprefix-canonical-property.md)
    
- [<span data-ttu-id="40460-145">PidTagNormalizedSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="40460-145">PidTagNormalizedSubject Canonical Property</span></span>](pidtagnormalizedsubject-canonical-property.md)
    
- [<span data-ttu-id="40460-146">PidTagConversationTopic 规范属性</span><span class="sxs-lookup"><span data-stu-id="40460-146">PidTagConversationTopic Canonical Property</span></span>](pidtagconversationtopic-canonical-property.md)
    
- [<span data-ttu-id="40460-147">PidTagConversationIndex 规范属性</span><span class="sxs-lookup"><span data-stu-id="40460-147">PidTagConversationIndex Canonical Property</span></span>](pidtagconversationindex-canonical-property.md)
    
- [<span data-ttu-id="40460-148">ScCreateConversationIndex</span><span class="sxs-lookup"><span data-stu-id="40460-148">ScCreateConversationIndex</span></span>](sccreateconversationindex.md)
    
- [<span data-ttu-id="40460-149">设置列和限制后对表进行排序</span><span class="sxs-lookup"><span data-stu-id="40460-149">Sorting Tables After Setting Columns and Restrictions</span></span>](sorting-tables-after-setting-columns-and-restrictions.md)
    
## <a name="see-also"></a><span data-ttu-id="40460-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40460-150">See also</span></span>



[<span data-ttu-id="40460-151">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="40460-151">MAPI Tables</span></span>](mapi-tables.md)

