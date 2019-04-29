---
title: 打开通讯簿容器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89383b27-618c-4ccb-9e16-f66235c98bfe
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 97fa9f9750174c112c431c62f6171f674856fa86
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436739"
---
# <a name="opening-an-address-book-container"></a><span data-ttu-id="e7c9e-103">打开通讯簿容器</span><span class="sxs-lookup"><span data-stu-id="e7c9e-103">Opening an address book container</span></span>

<span data-ttu-id="e7c9e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e7c9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e7c9e-105">打开 MAPI 集成通讯簿后, 打开一个或多个通讯簿容器以访问其中的收件人。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-105">After opening the MAPI integrated address book, open one or more address book containers to access the recipients within them.</span></span>
  
<span data-ttu-id="e7c9e-106">若要打开通讯簿的顶级容器, 请使用 NULL 条目标识符调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-106">To open the top-level container of the address book, call [IAddrBook::OpenEntry](iaddrbook-openentry.md) with a NULL entry identifier.</span></span> 
  
<span data-ttu-id="e7c9e-107">可以使用只读或读/写访问权限来实现通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-107">Address book containers can be implemented with read-only or read/write access.</span></span> <span data-ttu-id="e7c9e-108">只读容器仅用于浏览。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-108">Read-only containers are used only for browsing.</span></span> <span data-ttu-id="e7c9e-109">可以修改读/写容器, 允许客户端创建新的条目, 并删除和修改现有条目。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-109">Read/write containers can be modified, allowing clients to create new entries and delete and modify existing entries.</span></span> <span data-ttu-id="e7c9e-110">所有个人通讯簿 (PAB) 容器都实现为读/写容器。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-110">All personal address book (PAB) containers are implemented as read/write containers.</span></span> 
  
<span data-ttu-id="e7c9e-111">若要打开任何较低级别的容器, 请调用**OpenEntry**并指定要打开的容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-111">To open any lower level container, call **OpenEntry** and specify the entry identifier of the container to be opened.</span></span> 
  
## <a name="open-the-container-designated-as-the-pab"></a><span data-ttu-id="e7c9e-112">打开指定为 PAB 的容器</span><span class="sxs-lookup"><span data-stu-id="e7c9e-112">Open the container designated as the PAB</span></span>
  
1. <span data-ttu-id="e7c9e-113">调用[IAddrBook:: GetPAB](iaddrbook-getpab.md)以检索 PAB 的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-113">Call [IAddrBook::GetPAB](iaddrbook-getpab.md) to retrieve the PAB's entry identifier.</span></span> 
    
2. <span data-ttu-id="e7c9e-114">将此项标识符传递给[IAddrBook:: OpenEntry](iaddrbook-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-114">Pass this entry identifier to [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span>
    
## <a name="open-a-container-that-is-not-the-pab"></a><span data-ttu-id="e7c9e-115">打开不是 PAB 的容器</span><span class="sxs-lookup"><span data-stu-id="e7c9e-115">Open a container that is not the PAB</span></span>
  
1. <span data-ttu-id="e7c9e-116">使用 NULL 条目标识符调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md) , 以打开通讯簿的根容器。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-116">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md) with a NULL entry identifier to open the address book's root container.</span></span> 
    
2. <span data-ttu-id="e7c9e-117">调用根容器的[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以检索其层次结构表—通讯簿中所有顶级容器的列表。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-117">Call the root container's [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method to retrieve its hierarchy table — a list of all of the top-level containers in the address book.</span></span> 
    
3. <span data-ttu-id="e7c9e-118">如果要打开的容器为特定类型:</span><span class="sxs-lookup"><span data-stu-id="e7c9e-118">If the container to be opened is of a specific type:</span></span>
    
   - <span data-ttu-id="e7c9e-119">使用**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 为属性标记创建**SPropertyRestriction**结构, 为属性值创建容器的类型, 并为该关系创建 RELOP_EQ。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-119">Create an **SPropertyRestriction** structure with **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) for the property tag, the container's type for the property value, and RELOP_EQ for the relation.</span></span> <span data-ttu-id="e7c9e-120">**PR_DISPLAY_TYPE**可设置为多个值, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="e7c9e-120">**PR_DISPLAY_TYPE** can be set to many values, among them:</span></span> 
    
   - <span data-ttu-id="e7c9e-121">DT_GLOBAL 将层次结构表限制为属于全局地址列表的容器。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-121">DT_GLOBAL to limit the hierarchy table to containers that belong in the global address list.</span></span>
    
   - <span data-ttu-id="e7c9e-122">DT_LOCAL 将表限制为属于本地通讯簿的容器。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-122">DT_LOCAL to limit the table to containers belonging to a local address book.</span></span>
    
   - <span data-ttu-id="e7c9e-123">DT_MODIFIABLE 将表限制为可修改的容器。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-123">DT_MODIFIABLE to limit the table to containers that can be modified.</span></span>
    
   - <span data-ttu-id="e7c9e-124">创建一个[SPropTagArray](sproptagarray.md)结构, 其中包括**PR_ENTRYID**、 **PR_DISPLAY_TYPE**和其他感兴趣的列。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-124">Create an [SPropTagArray](sproptagarray.md) structure that includes **PR_ENTRYID**, **PR_DISPLAY_TYPE**, and any other columns of interest.</span></span> 
    
   - <span data-ttu-id="e7c9e-125">调用[HrQueryAllRows](hrqueryallrows.md), 并传递属性限制和属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-125">Call [HrQueryAllRows](hrqueryallrows.md), passing your property restriction and property tag array.</span></span> <span data-ttu-id="e7c9e-126">**HrQueryAllRows**将返回零个或多个行, 属于指定类型的每个容器一行。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-126">**HrQueryAllRows** will return zero or more rows, one row for every container that belongs to the specified type.</span></span> <span data-ttu-id="e7c9e-127">准备好处理任意数量的行的返回。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-127">Be prepared to handle the return of any number of rows.</span></span> 
    
   - <span data-ttu-id="e7c9e-128">使用表示感兴趣的容器的行的**PR_ENTRYID**列中的条目标识符调用**IAddrBook:: OpenEntry** 。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-128">Call **IAddrBook::OpenEntry** with the entry identifier from the **PR_ENTRYID** column of the row that represents the container of interest.</span></span> 
    
4. <span data-ttu-id="e7c9e-129">如果要打开的容器属于特定的通讯簿提供程序:</span><span class="sxs-lookup"><span data-stu-id="e7c9e-129">If the container to be opened belongs to a specific address book provider:</span></span>
    
   - <span data-ttu-id="e7c9e-130">创建一个[SPropertyRestriction](spropertyrestriction.md)结构, 其中包含**PR_AB_PROVIDERS** ([PidTagAbProviders](pidtagabproviders-canonical-property.md)) 的属性标记、特定于提供程序的属性值值和 RELOP_EQ 的关系。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-130">Create an [SPropertyRestriction](spropertyrestriction.md) structure with **PR_AB_PROVIDERS** ([PidTagAbProviders](pidtagabproviders-canonical-property.md)) for the property tag, a provider-specific value for the property value, and RELOP_EQ for the relation.</span></span> <span data-ttu-id="e7c9e-131">通常, 提供程序特定的值是全局唯一的标识符或 GUID。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-131">Typically the provider-specific value is a globally unique identifier or GUID.</span></span> <span data-ttu-id="e7c9e-132">您将在某个通讯簿提供程序的头文件中找到发布的此值。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-132">You will find this value published in one of the address book provider's header files.</span></span> 
    
   - <span data-ttu-id="e7c9e-133">创建一个包含**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_AB_PROVIDERS**和任何其他感兴趣的列的[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-133">Create an [SPropTagArray](sproptagarray.md) structure that includes **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_AB_PROVIDERS**, and any other columns of interest.</span></span> 
    
   - <span data-ttu-id="e7c9e-134">调用[HrQueryAllRows](hrqueryallrows.md), 并传递属性限制和属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-134">Call [HrQueryAllRows](hrqueryallrows.md), passing your property restriction and property tag array.</span></span> <span data-ttu-id="e7c9e-135">如果指定的通讯簿提供程序不在配置文件中, **HrQueryAllRows**将返回零行。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-135">**HrQueryAllRows** will return zero rows if the specified address book provider is not in the profile.</span></span> <span data-ttu-id="e7c9e-136">它可以返回提供程序的顶级容器的一个或多个行, 具体取决于提供程序的组织方式。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-136">It can return one or more rows for the provider's top-level containers, depending on how the provider is organized.</span></span> 
    
   - <span data-ttu-id="e7c9e-137">使用表示感兴趣的容器的行的**PR_ENTRYID**列中的条目标识符调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-137">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md) with the entry identifier from the **PR_ENTRYID** column of the row that represents the container of interest.</span></span> <span data-ttu-id="e7c9e-138">如果您感兴趣的容器不是顶级容器, 请查找顶级容器并遍历层次结构。</span><span class="sxs-lookup"><span data-stu-id="e7c9e-138">If the container that you are interested in is not a top-level container, find the top-level container and traverse the hierarchy.</span></span> 
    

