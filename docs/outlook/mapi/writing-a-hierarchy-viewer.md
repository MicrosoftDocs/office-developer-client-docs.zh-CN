---
title: 编写层次结构查看器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4c939a8c-8148-4add-b181-5a12e6d32309
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6ff394c95dfa3166d39dcba4b0c577dcfac7b8d8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581592"
---
# <a name="writing-a-hierarchy-viewer"></a><span data-ttu-id="85aca-103">编写层次结构查看器</span><span class="sxs-lookup"><span data-stu-id="85aca-103">Writing a Hierarchy Viewer</span></span>

  
  
<span data-ttu-id="85aca-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85aca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="85aca-105">层次结构查看器是用于显示文件夹和通讯簿容器层次结构表的用户界面组件。</span><span class="sxs-lookup"><span data-stu-id="85aca-105">A hierarchy viewer is a user interface component that is used for displaying folder and address book container hierarchy tables.</span></span> <span data-ttu-id="85aca-106">层次结构查看者可以在不同级别，展开和折叠按需型每个级别显示的层次结构的成员。</span><span class="sxs-lookup"><span data-stu-id="85aca-106">Hierarchy viewers can display members of the hierarchy at different levels, expanding and contracting each level on demand.</span></span>
  
<span data-ttu-id="85aca-107">Container 属性， **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md))，控件的层次结构成员将显示的级别。</span><span class="sxs-lookup"><span data-stu-id="85aca-107">The container property, **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)), controls the level at which a hierarchy member is displayed.</span></span> <span data-ttu-id="85aca-108">表示顶级通讯簿容器或文件夹项具有其**PR_DEPTH**属性设置为零。</span><span class="sxs-lookup"><span data-stu-id="85aca-108">Entries that represent top-level address book containers or folders have their **PR_DEPTH** property set to zero.</span></span> <span data-ttu-id="85aca-109">此属性的值将按顺序递增顺序级别的条目。</span><span class="sxs-lookup"><span data-stu-id="85aca-109">The value of this property is incremented sequentially for entries in sequential levels.</span></span> <span data-ttu-id="85aca-110">即，当用户选择的顶级容器展开，显示所有容器都与**PR_DEPTH**都设置为 1。</span><span class="sxs-lookup"><span data-stu-id="85aca-110">That is, when a user selects a top-level container to expand, display all containers with **PR_DEPTH** set to 1.</span></span> <span data-ttu-id="85aca-111">当用户展开这些子容器之一时，2，向显示**PR_DEPTH**设置的容器，依此类推。</span><span class="sxs-lookup"><span data-stu-id="85aca-111">When a user expands one of these subcontainers, display the containers with **PR_DEPTH** set to 2, and so on.</span></span> 
  
<span data-ttu-id="85aca-112">层次结构查看器支持不同范围的深度。</span><span class="sxs-lookup"><span data-stu-id="85aca-112">Hierarchy viewers support a different range of depths.</span></span> <span data-ttu-id="85aca-113">您可以限制为仅一个或两个级别您查看器或显示大规模层次结构是否优先级，您可以支持多个级别。</span><span class="sxs-lookup"><span data-stu-id="85aca-113">You can limit your viewer to only one or two levels or you can support multiple levels, if displaying an expansive hierarchy is a priority.</span></span> 
  
<span data-ttu-id="85aca-114">通讯簿提供用于在通讯簿中的顶级容器层次结构查看器。</span><span class="sxs-lookup"><span data-stu-id="85aca-114">The address book provides a hierarchy viewer for the top-level containers in the address book.</span></span> 
  
 <span data-ttu-id="85aca-115">**若要访问通讯簿层次结构表**</span><span class="sxs-lookup"><span data-stu-id="85aca-115">**To access the address book hierarchy table**</span></span>
  
1. <span data-ttu-id="85aca-116">调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)，传递 null 条目标识符，打开在通讯簿根容器。</span><span class="sxs-lookup"><span data-stu-id="85aca-116">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md), passing a null entry identifier, to open the address book's root container.</span></span>
    
2. <span data-ttu-id="85aca-117">调用根容器[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法来访问的 MAPI 通讯簿层次结构表。</span><span class="sxs-lookup"><span data-stu-id="85aca-117">Call the root container's [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method to access the hierarchy table of the MAPI address book.</span></span> 
    
 <span data-ttu-id="85aca-118">**若要访问的默认邮件存储层次结构表**</span><span class="sxs-lookup"><span data-stu-id="85aca-118">**To access the default message store's hierarchy table**</span></span>
  
1. <span data-ttu-id="85aca-119">调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)消息存储表的访问。</span><span class="sxs-lookup"><span data-stu-id="85aca-119">Call [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) to access the message store table.</span></span> 
    
2. <span data-ttu-id="85aca-120">构建使用[SPropertyRestriction](spropertyrestriction.md)结构限制表格**PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 属性设置为 TRUE 的行限制。</span><span class="sxs-lookup"><span data-stu-id="85aca-120">Build a restriction using the [SPropertyRestriction](spropertyrestriction.md) structure to limit the table to only those rows that have a **PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) property set to TRUE.</span></span> 
    
3. <span data-ttu-id="85aca-121">调用[IMAPITable::FindRow](imapitable-findrow.md)，将其传递**SPropertyRestriction**，以找到表示默认的邮件存储的行。</span><span class="sxs-lookup"><span data-stu-id="85aca-121">Call [IMAPITable::FindRow](imapitable-findrow.md), passing it the **SPropertyRestriction**, to locate the row representing the default message store.</span></span> 
    
4. <span data-ttu-id="85aca-122">调用[IMAPISession::OpenEntry](imapisession-openentry.md)，从默认的邮件存储的消息存储表中行传递**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="85aca-122">Call [IMAPISession::OpenEntry](imapisession-openentry.md), passing in the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property from the default message store's row in the message store table.</span></span>
    
5. <span data-ttu-id="85aca-123">调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="85aca-123">Call the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) property.</span></span>
    
6. <span data-ttu-id="85aca-124">调用的消息存储[IMsgStore::OpenEntry](imsgstore-openentry.md)方法，传递**PR_IPM_SUBTREE_ENTRYID**属性，以打开的消息存储 IPM 子树的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="85aca-124">Call the message store's [IMsgStore::OpenEntry](imsgstore-openentry.md) method, passing the **PR_IPM_SUBTREE_ENTRYID** property, to open the root folder of the message store's IPM subtree.</span></span> 
    
7. <span data-ttu-id="85aca-125">调用 IPM 根文件夹[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法，以访问其层次结构表。</span><span class="sxs-lookup"><span data-stu-id="85aca-125">Call the IPM root folder's [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method to access its hierarchy table.</span></span> 
    

