---
title: 打开通讯簿容器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89383b27-618c-4ccb-9e16-f66235c98bfe
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 28f60154524065bd2c818e2e4b7db37ca33276b4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776559"
---
# <a name="opening-an-address-book-container"></a><span data-ttu-id="03bc5-103">打开通讯簿容器</span><span class="sxs-lookup"><span data-stu-id="03bc5-103">Opening an address book container</span></span>

<span data-ttu-id="03bc5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="03bc5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="03bc5-105">打开 MAPI 集成通讯簿后，打开要访问其中的收件人的一个或多个地址簿容器。</span><span class="sxs-lookup"><span data-stu-id="03bc5-105">After opening the MAPI integrated address book, open one or more address book containers to access the recipients within them.</span></span>
  
<span data-ttu-id="03bc5-106">若要打开通讯簿的顶级容器，调用[IAddrBook::OpenEntry](iaddrbook-openentry.md) NULL 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="03bc5-106">To open the top-level container of the address book, call [IAddrBook::OpenEntry](iaddrbook-openentry.md) with a NULL entry identifier.</span></span> 
  
<span data-ttu-id="03bc5-107">通讯簿容器可在只读实施或读/写访问。</span><span class="sxs-lookup"><span data-stu-id="03bc5-107">Address book containers can be implemented with read-only or read/write access.</span></span> <span data-ttu-id="03bc5-108">只读容器仅用于浏览。</span><span class="sxs-lookup"><span data-stu-id="03bc5-108">Read-only containers are used only for browsing.</span></span> <span data-ttu-id="03bc5-109">读/写容器可以进行修改，允许客户端以创建新条目并删除和修改现有的条目。</span><span class="sxs-lookup"><span data-stu-id="03bc5-109">Read/write containers can be modified, allowing clients to create new entries and delete and modify existing entries.</span></span> <span data-ttu-id="03bc5-110">所有个人通讯簿 (PAB) 的容器实现为读/写容器。</span><span class="sxs-lookup"><span data-stu-id="03bc5-110">All personal address book (PAB) containers are implemented as read/write containers.</span></span> 
  
<span data-ttu-id="03bc5-111">若要打开任何较低级别的容器，调用**OpenEntry** ，并指定要在打开的容器的项标识符。</span><span class="sxs-lookup"><span data-stu-id="03bc5-111">To open any lower level container, call **OpenEntry** and specify the entry identifier of the container to be opened.</span></span> 
  
## <a name="open-the-container-designated-as-the-pab"></a><span data-ttu-id="03bc5-112">打开指定为 PAB 容器</span><span class="sxs-lookup"><span data-stu-id="03bc5-112">Open the container designated as the PAB</span></span>
  
1. <span data-ttu-id="03bc5-113">调用[IAddrBook::GetPAB](iaddrbook-getpab.md)检索 PAB 的项标识符。</span><span class="sxs-lookup"><span data-stu-id="03bc5-113">Call [IAddrBook::GetPAB](iaddrbook-getpab.md) to retrieve the PAB's entry identifier.</span></span> 
    
2. <span data-ttu-id="03bc5-114">传递给[IAddrBook::OpenEntry](iaddrbook-openentry.md)此条目标识符。</span><span class="sxs-lookup"><span data-stu-id="03bc5-114">Pass this entry identifier to [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span>
    
## <a name="open-a-container-that-is-not-the-pab"></a><span data-ttu-id="03bc5-115">打开不是 PAB 容器</span><span class="sxs-lookup"><span data-stu-id="03bc5-115">Open a container that is not the PAB</span></span>
  
1. <span data-ttu-id="03bc5-116">要打开通讯簿的根容器 NULL 条目标识符调用[IAddrBook::OpenEntry](iaddrbook-openentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="03bc5-116">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md) with a NULL entry identifier to open the address book's root container.</span></span> 
    
2. <span data-ttu-id="03bc5-117">调用根容器[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法来检索其层次结构表 — 所有通讯簿中的顶级容器的列表。</span><span class="sxs-lookup"><span data-stu-id="03bc5-117">Call the root container's [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method to retrieve its hierarchy table — a list of all of the top-level containers in the address book.</span></span> 
    
3. <span data-ttu-id="03bc5-118">如果容器来打开特定类型的：</span><span class="sxs-lookup"><span data-stu-id="03bc5-118">If the container to be opened is of a specific type:</span></span>
    
   - <span data-ttu-id="03bc5-119">属性标记、 对该属性值，容器的类型和关系 RELOP_EQ 使用**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 创建**SPropertyRestriction**结构。</span><span class="sxs-lookup"><span data-stu-id="03bc5-119">Create an **SPropertyRestriction** structure with **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) for the property tag, the container's type for the property value, and RELOP_EQ for the relation.</span></span> <span data-ttu-id="03bc5-120">**PR_DISPLAY_TYPE**可以将多个值，它们之间设置：</span><span class="sxs-lookup"><span data-stu-id="03bc5-120">**PR_DISPLAY_TYPE** can be set to many values, among them:</span></span> 
    
   - <span data-ttu-id="03bc5-121">DT_GLOBAL 来限制在全局地址列表所属的容器层次结构表。</span><span class="sxs-lookup"><span data-stu-id="03bc5-121">DT_GLOBAL to limit the hierarchy table to containers that belong in the global address list.</span></span>
    
   - <span data-ttu-id="03bc5-122">DT_LOCAL 限制属于本地通讯簿容器表。</span><span class="sxs-lookup"><span data-stu-id="03bc5-122">DT_LOCAL to limit the table to containers belonging to a local address book.</span></span>
    
   - <span data-ttu-id="03bc5-123">DT_MODIFIABLE 以限制可以修改的容器的表。</span><span class="sxs-lookup"><span data-stu-id="03bc5-123">DT_MODIFIABLE to limit the table to containers that can be modified.</span></span>
    
   - <span data-ttu-id="03bc5-124">创建包含**PR_ENTRYID**、 **PR_DISPLAY_TYPE**和感兴趣的任何其他列[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="03bc5-124">Create an [SPropTagArray](sproptagarray.md) structure that includes **PR_ENTRYID**, **PR_DISPLAY_TYPE**, and any other columns of interest.</span></span> 
    
   - <span data-ttu-id="03bc5-125">调用[HrQueryAllRows](hrqueryallrows.md)，传递在属性限制和属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="03bc5-125">Call [HrQueryAllRows](hrqueryallrows.md), passing your property restriction and property tag array.</span></span> <span data-ttu-id="03bc5-126">**HrQueryAllRows**将返回零个或多行，对每个容器属于指定类型的一行。</span><span class="sxs-lookup"><span data-stu-id="03bc5-126">**HrQueryAllRows** will return zero or more rows, one row for every container that belongs to the specified type.</span></span> <span data-ttu-id="03bc5-127">准备处理返回的任意数量的行。</span><span class="sxs-lookup"><span data-stu-id="03bc5-127">Be prepared to handle the return of any number of rows.</span></span> 
    
   - <span data-ttu-id="03bc5-128">调用**IAddrBook::OpenEntry**表示感兴趣的容器的行的**PR_ENTRYID**列中的项标识符。</span><span class="sxs-lookup"><span data-stu-id="03bc5-128">Call **IAddrBook::OpenEntry** with the entry identifier from the **PR_ENTRYID** column of the row that represents the container of interest.</span></span> 
    
4. <span data-ttu-id="03bc5-129">如果要在打开的容器属于特定地址簿提供程序：</span><span class="sxs-lookup"><span data-stu-id="03bc5-129">If the container to be opened belongs to a specific address book provider:</span></span>
    
   - <span data-ttu-id="03bc5-130">为属性标记，属性值，提供程序特定值 RELOP_EQ 关系与**PR_AB_PROVIDERS** ([PidTagAbProviders](pidtagabproviders-canonical-property.md)) 创建[SPropertyRestriction](spropertyrestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="03bc5-130">Create an [SPropertyRestriction](spropertyrestriction.md) structure with **PR_AB_PROVIDERS** ([PidTagAbProviders](pidtagabproviders-canonical-property.md)) for the property tag, a provider-specific value for the property value, and RELOP_EQ for the relation.</span></span> <span data-ttu-id="03bc5-131">通常的特定于提供程序的值为的全局唯一标识符或 GUID。</span><span class="sxs-lookup"><span data-stu-id="03bc5-131">Typically the provider-specific value is a globally unique identifier or GUID.</span></span> <span data-ttu-id="03bc5-132">您可以找到该值发布在某个通讯簿提供程序的标头文件。</span><span class="sxs-lookup"><span data-stu-id="03bc5-132">You will find this value published in one of the address book provider's header files.</span></span> 
    
   - <span data-ttu-id="03bc5-133">创建包含**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_AB_PROVIDERS**和感兴趣的任何其他列[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="03bc5-133">Create an [SPropTagArray](sproptagarray.md) structure that includes **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_AB_PROVIDERS**, and any other columns of interest.</span></span> 
    
   - <span data-ttu-id="03bc5-134">调用[HrQueryAllRows](hrqueryallrows.md)，传递在属性限制和属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="03bc5-134">Call [HrQueryAllRows](hrqueryallrows.md), passing your property restriction and property tag array.</span></span> <span data-ttu-id="03bc5-135">如果指定的地址簿提供程序不是配置文件中， **HrQueryAllRows**将返回零行。</span><span class="sxs-lookup"><span data-stu-id="03bc5-135">**HrQueryAllRows** will return zero rows if the specified address book provider is not in the profile.</span></span> <span data-ttu-id="03bc5-136">它可以返回一个或多个行的提供程序的顶级容器，具体取决于提供程序的组织方式。</span><span class="sxs-lookup"><span data-stu-id="03bc5-136">It can return one or more rows for the provider's top-level containers, depending on how the provider is organized.</span></span> 
    
   - <span data-ttu-id="03bc5-137">调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)表示感兴趣的容器的行的**PR_ENTRYID**列中的项标识符。</span><span class="sxs-lookup"><span data-stu-id="03bc5-137">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md) with the entry identifier from the **PR_ENTRYID** column of the row that represents the container of interest.</span></span> <span data-ttu-id="03bc5-138">如果您感兴趣的容器不是顶级容器，查找的顶级容器和遍历层次结构。</span><span class="sxs-lookup"><span data-stu-id="03bc5-138">If the container that you are interested in is not a top-level container, find the top-level container and traverse the hierarchy.</span></span> 
    

