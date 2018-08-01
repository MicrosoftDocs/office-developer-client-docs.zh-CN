---
title: 搜索通讯簿
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 20ff2b63-e4a3-4ba9-bad0-2c1873fb69b5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6673e1d51a7c030a35a7c5c3cbc955341afba299
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778725"
---
# <a name="searching-the-address-book"></a><span data-ttu-id="b476b-103">搜索通讯簿</span><span class="sxs-lookup"><span data-stu-id="b476b-103">Searching the address book</span></span>

<span data-ttu-id="b476b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b476b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b476b-105">MAPI 启用通讯簿提供程序实现两个级别的搜索功能：</span><span class="sxs-lookup"><span data-stu-id="b476b-105">MAPI enables address book providers to implement two levels of search functionality:</span></span>
  
- <span data-ttu-id="b476b-106">基本级别与通讯簿条目的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性指定的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="b476b-106">A basic level that matches a specified name with the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of address book entries.</span></span> <span data-ttu-id="b476b-107">此级别允许用户，例如，可以使用名称开头西北查看通讯组列表或找到其 last name 是褐色的单个消息用户。</span><span class="sxs-lookup"><span data-stu-id="b476b-107">This level allows users, for example, to view distribution lists with names beginning with Northwest or locate individual messaging users whose last name is Brown.</span></span>
    
- <span data-ttu-id="b476b-108">匹配属性之外**PR_DISPLAY_NAME**高级级别。</span><span class="sxs-lookup"><span data-stu-id="b476b-108">An advanced level that matches on properties other than **PR_DISPLAY_NAME**.</span></span> <span data-ttu-id="b476b-109">此级别允许用户，例如，若要进一步缩小其搜索和查找消息名褐色为与特定地址类型的用户。</span><span class="sxs-lookup"><span data-stu-id="b476b-109">This level allows users, for example, to further narrow their searches and find messaging users named Brown with a particular address type.</span></span>
    
<span data-ttu-id="b476b-110">因为通讯簿提供程序可以支持在基本级别，这两个级别，其容器的每个搜索或选择不在所有支持，不需要搜索作为标准功能实现。</span><span class="sxs-lookup"><span data-stu-id="b476b-110">Because address book providers can support searching for each of their containers at the basic level, at both levels, or choose not to support it at all, do not expect searching to be implemented as a standard feature.</span></span> <span data-ttu-id="b476b-111">若要确定某个特定的容器是否支持搜索，尝试建立对其[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法的调用中的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="b476b-111">To determine if a particular container supports searches, attempt to establish search criteria in a call to its [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method.</span></span> <span data-ttu-id="b476b-112">如果**SetSearchCriteria**返回 MAPI_E_NO_SUPPORT，容器不支持搜索。</span><span class="sxs-lookup"><span data-stu-id="b476b-112">If **SetSearchCriteria** returns MAPI_E_NO_SUPPORT, the container does not support searches.</span></span> 
  
<span data-ttu-id="b476b-113">在支持搜索的容器，通过调用[IMAPIContainer::GetSearchCriteria](imapicontainer-getsearchcriteria.md)中检索已建立的条件。</span><span class="sxs-lookup"><span data-stu-id="b476b-113">In a container that supports searches, retrieve established criteria by calling [IMAPIContainer::GetSearchCriteria](imapicontainer-getsearchcriteria.md).</span></span> <span data-ttu-id="b476b-114">您还可以请求，将提示用户输入搜索条件显示容器内容表之前。</span><span class="sxs-lookup"><span data-stu-id="b476b-114">You can also request that the user be prompted for search criteria before a container's contents table is displayed.</span></span> <span data-ttu-id="b476b-115">若要选择此选项，设置的容器的**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性 AB_FIND_ON_OPEN 标志。</span><span class="sxs-lookup"><span data-stu-id="b476b-115">To choose this option, set the AB_FIND_ON_OPEN flag of the container's **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property.</span></span> <span data-ttu-id="b476b-116">用户输入条件后，它是存储为限制，并传递给**SetSearchCriteria**方法。</span><span class="sxs-lookup"><span data-stu-id="b476b-116">After the user enters the criteria, it is stored as a restriction and passed to the **SetSearchCriteria** method.</span></span> <span data-ttu-id="b476b-117">设置 AB_FIND_ON_OPEN 是特别有用，如果您使用联机服务或具有慢速链接到其数据的任何通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="b476b-117">Setting AB_FIND_ON_OPEN is particularly useful if you are using an online service or any address book provider that has a slow link to its data.</span></span> 
  
### <a name="to-perform-a-basic-search-in-an-address-book-container"></a><span data-ttu-id="b476b-118">若要执行的通讯簿容器中的基本搜索</span><span class="sxs-lookup"><span data-stu-id="b476b-118">To perform a basic search in an address book container</span></span>
  
1. <span data-ttu-id="b476b-119">调用容器的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法以打开其内容的表格。</span><span class="sxs-lookup"><span data-stu-id="b476b-119">Call the container's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to open its contents table.</span></span> 
    
2. <span data-ttu-id="b476b-120">选择满足您需求的搜索技术。</span><span class="sxs-lookup"><span data-stu-id="b476b-120">Choose a search technique that meets your needs.</span></span> <span data-ttu-id="b476b-121">选项包括：</span><span class="sxs-lookup"><span data-stu-id="b476b-121">The choices include:</span></span>
    
   - <span data-ttu-id="b476b-122">[IMAPITable::FindRow](imapitable-findrow.md) ，以便在表中查找特定行。</span><span class="sxs-lookup"><span data-stu-id="b476b-122">[IMAPITable::FindRow](imapitable-findrow.md) to locate a specific row in the table.</span></span> 
    
   - <span data-ttu-id="b476b-123">对表中的行进行排序[IMAPITable::SortTable](imapitable-sorttable.md) 。</span><span class="sxs-lookup"><span data-stu-id="b476b-123">[IMAPITable::SortTable](imapitable-sorttable.md) to order rows in the table.</span></span> 
    
   - <span data-ttu-id="b476b-124">[IMAPITable::Restrict](imapitable-restrict.md)限制表视图。</span><span class="sxs-lookup"><span data-stu-id="b476b-124">[IMAPITable::Restrict](imapitable-restrict.md) to limit the table view.</span></span> 
    
   - <span data-ttu-id="b476b-125">属性限制的模糊名称解析使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b476b-125">Property restriction using the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property for resolving ambiguous names.</span></span> <span data-ttu-id="b476b-126">调用**IMAPITable::Restrict**要实施此限制。</span><span class="sxs-lookup"><span data-stu-id="b476b-126">Call **IMAPITable::Restrict** to impose this restriction.</span></span> 
    
   - <span data-ttu-id="b476b-127">[IABContainer::ResolveNames](iabcontainer-resolvenames.md) ，若要解决不明确的名称。</span><span class="sxs-lookup"><span data-stu-id="b476b-127">[IABContainer::ResolveNames](iabcontainer-resolvenames.md) to resolve ambiguous names.</span></span> 
    
3. <span data-ttu-id="b476b-128">调用[IMAPITable::QueryRows](imapitable-queryrows.md)检索符合应用的搜索条件的任何行。</span><span class="sxs-lookup"><span data-stu-id="b476b-128">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve any rows that meet your applied search criteria.</span></span> <span data-ttu-id="b476b-129">**QueryRows**可以返回零个或多个匹配的行。</span><span class="sxs-lookup"><span data-stu-id="b476b-129">**QueryRows** can return zero or more matching rows.</span></span> 
    
<span data-ttu-id="b476b-130">**FindRow**、 **SortTable**和**Restrict**方法是可用于任何可以创建，通过客户端或服务提供商的表的表方法。</span><span class="sxs-lookup"><span data-stu-id="b476b-130">The **FindRow**, **SortTable**, and **Restrict** methods are table methods that are available for any table that can be created, either by a client or a service provider.</span></span> <span data-ttu-id="b476b-131">**PR\_ANR**属性限制**IABContainer::ResolveNames**方法特定于通讯簿提供程序和用于解析不明确的名称。</span><span class="sxs-lookup"><span data-stu-id="b476b-131">The **PR\_ANR** property restriction and **IABContainer::ResolveNames** method are specific to address book providers and are used for resolving ambiguous names.</span></span> <span data-ttu-id="b476b-132">不明确的名称是在收件人列表中的条目，没有与其关联的**PR_ENTRYID**属性。</span><span class="sxs-lookup"><span data-stu-id="b476b-132">Ambiguous names are entries in a recipient list that do not have a **PR_ENTRYID** property associated with them.</span></span> 
  
<span data-ttu-id="b476b-133">**PR\_ANR**限制调用算法，单词到分隔的字符串匹配这些单词与使用前缀匹配在通讯簿中的信息。</span><span class="sxs-lookup"><span data-stu-id="b476b-133">The **PR\_ANR** restriction invokes an algorithm that separates a character string into words and matches those words with information in the address book using prefix-matching.</span></span> <span data-ttu-id="b476b-134">用于匹配的信息取决于通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="b476b-134">The information used for the matching depends on the address book provider.</span></span> <span data-ttu-id="b476b-135">所有通讯簿提供程序都需要支持其通讯簿容器**PR_ANR**限制。</span><span class="sxs-lookup"><span data-stu-id="b476b-135">All address book providers are required to support the **PR_ANR** restriction for their address book containers.</span></span> <span data-ttu-id="b476b-136">有关详细信息，请参阅[实现名称解析](implementing-name-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="b476b-136">For more information, see [Implementing Name Resolution](implementing-name-resolution.md).</span></span>
  
<span data-ttu-id="b476b-137">**IABContainer::ResolveNames**执行**PR_ANR**限制而无需容器的内容表，才能开放的处理多个名称。</span><span class="sxs-lookup"><span data-stu-id="b476b-137">**IABContainer::ResolveNames** performs **PR_ANR** restriction processing on multiple names without requiring the container's contents table to be open.</span></span> <span data-ttu-id="b476b-138">调用**ResolveNames**一次将多个名称解析可以速度大于调用**PR\_ANR**限制多次。</span><span class="sxs-lookup"><span data-stu-id="b476b-138">Calling **ResolveNames** once to resolve multiple names can be much faster than invoking a **PR\_ANR** restriction multiple times.</span></span> <span data-ttu-id="b476b-139">但是，无需通讯簿提供程序支持**ResolveNames**。</span><span class="sxs-lookup"><span data-stu-id="b476b-139">However, address book providers are not required to support **ResolveNames**.</span></span>
  

