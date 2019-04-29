---
title: 搜索通讯簿
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 20ff2b63-e4a3-4ba9-bad0-2c1873fb69b5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d40419291f4b09c5880a769ce231015511e8f269
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424369"
---
# <a name="searching-the-address-book"></a><span data-ttu-id="7549d-103">搜索通讯簿</span><span class="sxs-lookup"><span data-stu-id="7549d-103">Searching the address book</span></span>

<span data-ttu-id="7549d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7549d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7549d-105">MAPI 允许通讯簿提供程序实现两个级别的搜索功能:</span><span class="sxs-lookup"><span data-stu-id="7549d-105">MAPI enables address book providers to implement two levels of search functionality:</span></span>
  
- <span data-ttu-id="7549d-106">与通讯簿条目的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性相匹配的指定名称的基本级别。</span><span class="sxs-lookup"><span data-stu-id="7549d-106">A basic level that matches a specified name with the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of address book entries.</span></span> <span data-ttu-id="7549d-107">例如, 使用此级别, 用户可以查看名称从西北开始的通讯组列表, 或查找姓氏为褐色的单个邮件用户。</span><span class="sxs-lookup"><span data-stu-id="7549d-107">This level allows users, for example, to view distribution lists with names beginning with Northwest or locate individual messaging users whose last name is Brown.</span></span>
    
- <span data-ttu-id="7549d-108">与**PR_DISPLAY_NAME**之外的属性匹配的高级级别。</span><span class="sxs-lookup"><span data-stu-id="7549d-108">An advanced level that matches on properties other than **PR_DISPLAY_NAME**.</span></span> <span data-ttu-id="7549d-109">例如, 此级别允许用户进一步缩小搜索范围, 并使用特定地址类型查找名为棕色的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="7549d-109">This level allows users, for example, to further narrow their searches and find messaging users named Brown with a particular address type.</span></span>
    
<span data-ttu-id="7549d-110">由于通讯簿提供程序可以支持在基本级别搜索每个容器, 在这两个级别上, 或者选择根本不支持它, 因此不希望将搜索作为标准功能实现。</span><span class="sxs-lookup"><span data-stu-id="7549d-110">Because address book providers can support searching for each of their containers at the basic level, at both levels, or choose not to support it at all, do not expect searching to be implemented as a standard feature.</span></span> <span data-ttu-id="7549d-111">若要确定特定容器是否支持搜索, 请尝试在对其[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法的调用中建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="7549d-111">To determine if a particular container supports searches, attempt to establish search criteria in a call to its [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method.</span></span> <span data-ttu-id="7549d-112">如果**SetSearchCriteria**返回 MAPI_E_NO_SUPPORT, 则该容器不支持搜索。</span><span class="sxs-lookup"><span data-stu-id="7549d-112">If **SetSearchCriteria** returns MAPI_E_NO_SUPPORT, the container does not support searches.</span></span> 
  
<span data-ttu-id="7549d-113">在支持搜索的容器中, 通过调用[IMAPIContainer:: GetSearchCriteria](imapicontainer-getsearchcriteria.md)检索已建立的条件。</span><span class="sxs-lookup"><span data-stu-id="7549d-113">In a container that supports searches, retrieve established criteria by calling [IMAPIContainer::GetSearchCriteria](imapicontainer-getsearchcriteria.md).</span></span> <span data-ttu-id="7549d-114">您还可以请求在显示容器的内容表之前, 提示用户输入搜索条件。</span><span class="sxs-lookup"><span data-stu-id="7549d-114">You can also request that the user be prompted for search criteria before a container's contents table is displayed.</span></span> <span data-ttu-id="7549d-115">若要选择此选项, 请设置容器的**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性的 AB_FIND_ON_OPEN 标志。</span><span class="sxs-lookup"><span data-stu-id="7549d-115">To choose this option, set the AB_FIND_ON_OPEN flag of the container's **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property.</span></span> <span data-ttu-id="7549d-116">用户输入条件后, 它将存储为限制并传递给**SetSearchCriteria**方法。</span><span class="sxs-lookup"><span data-stu-id="7549d-116">After the user enters the criteria, it is stored as a restriction and passed to the **SetSearchCriteria** method.</span></span> <span data-ttu-id="7549d-117">如果使用的是联机服务或任何具有指向其数据的慢速链接的通讯簿提供程序, 则设置 AB_FIND_ON_OPEN 尤其有用。</span><span class="sxs-lookup"><span data-stu-id="7549d-117">Setting AB_FIND_ON_OPEN is particularly useful if you are using an online service or any address book provider that has a slow link to its data.</span></span> 
  
### <a name="to-perform-a-basic-search-in-an-address-book-container"></a><span data-ttu-id="7549d-118">在通讯簿容器中执行基本搜索</span><span class="sxs-lookup"><span data-stu-id="7549d-118">To perform a basic search in an address book container</span></span>
  
1. <span data-ttu-id="7549d-119">调用容器的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法以打开其内容表。</span><span class="sxs-lookup"><span data-stu-id="7549d-119">Call the container's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to open its contents table.</span></span> 
    
2. <span data-ttu-id="7549d-120">选择符合你的需求的搜索技术。</span><span class="sxs-lookup"><span data-stu-id="7549d-120">Choose a search technique that meets your needs.</span></span> <span data-ttu-id="7549d-121">选项包括:</span><span class="sxs-lookup"><span data-stu-id="7549d-121">The choices include:</span></span>
    
   - <span data-ttu-id="7549d-122">[IMAPITable:: FindRow](imapitable-findrow.md) , 用于查找表中的特定行。</span><span class="sxs-lookup"><span data-stu-id="7549d-122">[IMAPITable::FindRow](imapitable-findrow.md) to locate a specific row in the table.</span></span> 
    
   - <span data-ttu-id="7549d-123">[IMAPITable:: SortTable](imapitable-sorttable.md)对表中的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="7549d-123">[IMAPITable::SortTable](imapitable-sorttable.md) to order rows in the table.</span></span> 
    
   - <span data-ttu-id="7549d-124">[IMAPITable:: Restrict](imapitable-restrict.md)限制表格视图。</span><span class="sxs-lookup"><span data-stu-id="7549d-124">[IMAPITable::Restrict](imapitable-restrict.md) to limit the table view.</span></span> 
    
   - <span data-ttu-id="7549d-125">使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性解析不明确的名称的属性限制。</span><span class="sxs-lookup"><span data-stu-id="7549d-125">Property restriction using the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property for resolving ambiguous names.</span></span> <span data-ttu-id="7549d-126">调用**IMAPITable:: Restrict**以施加此限制。</span><span class="sxs-lookup"><span data-stu-id="7549d-126">Call **IMAPITable::Restrict** to impose this restriction.</span></span> 
    
   - <span data-ttu-id="7549d-127">[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)解析不明确的名称。</span><span class="sxs-lookup"><span data-stu-id="7549d-127">[IABContainer::ResolveNames](iabcontainer-resolvenames.md) to resolve ambiguous names.</span></span> 
    
3. <span data-ttu-id="7549d-128">调用[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索符合应用的搜索条件的任何行。</span><span class="sxs-lookup"><span data-stu-id="7549d-128">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve any rows that meet your applied search criteria.</span></span> <span data-ttu-id="7549d-129">**QueryRows**可以返回零个或多个匹配行。</span><span class="sxs-lookup"><span data-stu-id="7549d-129">**QueryRows** can return zero or more matching rows.</span></span> 
    
<span data-ttu-id="7549d-130">**FindRow**、 **SortTable**和**Restrict**方法是可用于可由客户端或服务提供商创建的任何表的表方法。</span><span class="sxs-lookup"><span data-stu-id="7549d-130">The **FindRow**, **SortTable**, and **Restrict** methods are table methods that are available for any table that can be created, either by a client or a service provider.</span></span> <span data-ttu-id="7549d-131">**\_PR ANR**属性限制和**IABContainer:: ResolveNames**方法特定于通讯簿提供程序, 用于解析不明确的名称。</span><span class="sxs-lookup"><span data-stu-id="7549d-131">The **PR\_ANR** property restriction and **IABContainer::ResolveNames** method are specific to address book providers and are used for resolving ambiguous names.</span></span> <span data-ttu-id="7549d-132">不明确的名称是收件人列表中没有与之关联的**PR_ENTRYID**属性的条目。</span><span class="sxs-lookup"><span data-stu-id="7549d-132">Ambiguous names are entries in a recipient list that do not have a **PR_ENTRYID** property associated with them.</span></span> 
  
<span data-ttu-id="7549d-133">**PR\_ANR**限制调用将字符串分隔为单词的算法, 并将这些单词与使用前缀匹配的通讯簿中的信息相匹配。</span><span class="sxs-lookup"><span data-stu-id="7549d-133">The **PR\_ANR** restriction invokes an algorithm that separates a character string into words and matches those words with information in the address book using prefix-matching.</span></span> <span data-ttu-id="7549d-134">用于匹配的信息取决于通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="7549d-134">The information used for the matching depends on the address book provider.</span></span> <span data-ttu-id="7549d-135">所有通讯簿提供程序都需要支持其通讯簿容器的**PR_ANR**限制。</span><span class="sxs-lookup"><span data-stu-id="7549d-135">All address book providers are required to support the **PR_ANR** restriction for their address book containers.</span></span> <span data-ttu-id="7549d-136">有关详细信息, 请参阅[实现名称解析](implementing-name-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="7549d-136">For more information, see [Implementing Name Resolution](implementing-name-resolution.md).</span></span>
  
<span data-ttu-id="7549d-137">**IABContainer:: ResolveNames**对多个名称执行**PR_ANR**限制处理, 而无需打开容器的内容表。</span><span class="sxs-lookup"><span data-stu-id="7549d-137">**IABContainer::ResolveNames** performs **PR_ANR** restriction processing on multiple names without requiring the container's contents table to be open.</span></span> <span data-ttu-id="7549d-138">调用**ResolveNames**一次以解析多个名称比多次调用**PR\_ANR**限制的速度要快得多。</span><span class="sxs-lookup"><span data-stu-id="7549d-138">Calling **ResolveNames** once to resolve multiple names can be much faster than invoking a **PR\_ANR** restriction multiple times.</span></span> <span data-ttu-id="7549d-139">但是, 通讯簿提供程序不需要支持**ResolveNames**。</span><span class="sxs-lookup"><span data-stu-id="7549d-139">However, address book providers are not required to support **ResolveNames**.</span></span>
  

