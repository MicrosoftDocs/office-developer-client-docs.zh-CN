---
title: 编写层次结构查看器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4c939a8c-8148-4add-b181-5a12e6d32309
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5f6ebd20afc3b8d029fa7c632c55982862664055
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421128"
---
# <a name="writing-a-hierarchy-viewer"></a><span data-ttu-id="6db1d-103">编写层次结构查看器</span><span class="sxs-lookup"><span data-stu-id="6db1d-103">Writing a Hierarchy Viewer</span></span>

  
  
<span data-ttu-id="6db1d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6db1d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6db1d-105">层次结构查看器是一个用户界面组件, 用于显示文件夹和通讯簿容器层次结构表。</span><span class="sxs-lookup"><span data-stu-id="6db1d-105">A hierarchy viewer is a user interface component that is used for displaying folder and address book container hierarchy tables.</span></span> <span data-ttu-id="6db1d-106">层次结构查看者可以显示不同级别的层次结构成员, 根据需要展开和收缩每个级别。</span><span class="sxs-lookup"><span data-stu-id="6db1d-106">Hierarchy viewers can display members of the hierarchy at different levels, expanding and contracting each level on demand.</span></span>
  
<span data-ttu-id="6db1d-107">container 属性**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 控制层次结构成员的显示级别。</span><span class="sxs-lookup"><span data-stu-id="6db1d-107">The container property, **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)), controls the level at which a hierarchy member is displayed.</span></span> <span data-ttu-id="6db1d-108">表示顶级通讯簿容器或文件夹的条目将其**PR_DEPTH**属性设置为零。</span><span class="sxs-lookup"><span data-stu-id="6db1d-108">Entries that represent top-level address book containers or folders have their **PR_DEPTH** property set to zero.</span></span> <span data-ttu-id="6db1d-109">对于连续级别中的条目, 此属性的值按顺序递增。</span><span class="sxs-lookup"><span data-stu-id="6db1d-109">The value of this property is incremented sequentially for entries in sequential levels.</span></span> <span data-ttu-id="6db1d-110">也就是说, 当用户选择要展开的顶级容器时, 将显示 " **PR_DEPTH** " 设置为1的所有容器。</span><span class="sxs-lookup"><span data-stu-id="6db1d-110">That is, when a user selects a top-level container to expand, display all containers with **PR_DEPTH** set to 1.</span></span> <span data-ttu-id="6db1d-111">当用户展开这些子容器之一时, 将显示 " **PR_DEPTH** " 设置为2的容器, 依此类推。</span><span class="sxs-lookup"><span data-stu-id="6db1d-111">When a user expands one of these subcontainers, display the containers with **PR_DEPTH** set to 2, and so on.</span></span> 
  
<span data-ttu-id="6db1d-112">层次结构查看器支持不同的深度范围。</span><span class="sxs-lookup"><span data-stu-id="6db1d-112">Hierarchy viewers support a different range of depths.</span></span> <span data-ttu-id="6db1d-113">您可以将查看器限制为仅有一个或两个级别, 如果显示范围较广的层次结构, 则可以支持多个级别。</span><span class="sxs-lookup"><span data-stu-id="6db1d-113">You can limit your viewer to only one or two levels or you can support multiple levels, if displaying an expansive hierarchy is a priority.</span></span> 
  
<span data-ttu-id="6db1d-114">通讯簿为通讯簿中的顶级容器提供了层次结构查看器。</span><span class="sxs-lookup"><span data-stu-id="6db1d-114">The address book provides a hierarchy viewer for the top-level containers in the address book.</span></span> 
  
 <span data-ttu-id="6db1d-115">**访问通讯簿层次结构表**</span><span class="sxs-lookup"><span data-stu-id="6db1d-115">**To access the address book hierarchy table**</span></span>
  
1. <span data-ttu-id="6db1d-116">调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md), 传递一个 null 条目标识符, 以打开通讯簿的根容器。</span><span class="sxs-lookup"><span data-stu-id="6db1d-116">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md), passing a null entry identifier, to open the address book's root container.</span></span>
    
2. <span data-ttu-id="6db1d-117">调用根容器的[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以访问 MAPI 通讯簿的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="6db1d-117">Call the root container's [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method to access the hierarchy table of the MAPI address book.</span></span> 
    
 <span data-ttu-id="6db1d-118">**访问默认邮件存储的层次结构表**</span><span class="sxs-lookup"><span data-stu-id="6db1d-118">**To access the default message store's hierarchy table**</span></span>
  
1. <span data-ttu-id="6db1d-119">调用[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)以访问邮件存储库表。</span><span class="sxs-lookup"><span data-stu-id="6db1d-119">Call [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) to access the message store table.</span></span> 
    
2. <span data-ttu-id="6db1d-120">使用[SPropertyRestriction](spropertyrestriction.md)结构生成限制, 将表限定为**PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 属性设置为 TRUE 的那些行。</span><span class="sxs-lookup"><span data-stu-id="6db1d-120">Build a restriction using the [SPropertyRestriction](spropertyrestriction.md) structure to limit the table to only those rows that have a **PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) property set to TRUE.</span></span> 
    
3. <span data-ttu-id="6db1d-121">调用[IMAPITable:: FindRow](imapitable-findrow.md), 并将其传递给**SPropertyRestriction**, 以定位表示默认邮件存储的行。</span><span class="sxs-lookup"><span data-stu-id="6db1d-121">Call [IMAPITable::FindRow](imapitable-findrow.md), passing it the **SPropertyRestriction**, to locate the row representing the default message store.</span></span> 
    
4. <span data-ttu-id="6db1d-122">调用[IMAPISession:: OpenEntry](imapisession-openentry.md), 从邮件存储库表中的默认邮件存储行传入**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="6db1d-122">Call [IMAPISession::OpenEntry](imapisession-openentry.md), passing in the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property from the default message store's row in the message store table.</span></span>
    
5. <span data-ttu-id="6db1d-123">调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="6db1d-123">Call the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) property.</span></span>
    
6. <span data-ttu-id="6db1d-124">调用邮件存储区的[IMsgStore:: OpenEntry](imsgstore-openentry.md)方法, 并传递**PR_IPM_SUBTREE_ENTRYID**属性, 以打开邮件存储的 IPM 子树的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="6db1d-124">Call the message store's [IMsgStore::OpenEntry](imsgstore-openentry.md) method, passing the **PR_IPM_SUBTREE_ENTRYID** property, to open the root folder of the message store's IPM subtree.</span></span> 
    
7. <span data-ttu-id="6db1d-125">调用 IPM 根文件夹的[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以访问其层次结构表。</span><span class="sxs-lookup"><span data-stu-id="6db1d-125">Call the IPM root folder's [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method to access its hierarchy table.</span></span> 
    

