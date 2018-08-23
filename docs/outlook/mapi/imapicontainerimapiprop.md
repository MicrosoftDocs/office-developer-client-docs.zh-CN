---
title: IMAPIContainer IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer
api_type:
- COM
ms.assetid: d83fdd83-3e86-43c8-a73f-8e9e01b53371
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 38094895fed03884b138b02d4aa1ed87bcc6ea9c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575698"
---
# <a name="imapicontainer--imapiprop"></a><span data-ttu-id="1673a-103">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="1673a-103">IMAPIContainer : IMAPIProp</span></span>

  
  
<span data-ttu-id="1673a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1673a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1673a-105">管理高级操作，如通讯簿、 通讯组列表和文件夹的容器对象。</span><span class="sxs-lookup"><span data-stu-id="1673a-105">Manages high-level operations on container objects such as address books, distribution lists, and folders.</span></span> <span data-ttu-id="1673a-106">[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)， [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)，和[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口派生**IMAPIContainer**。</span><span class="sxs-lookup"><span data-stu-id="1673a-106">The [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md), [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md), and [IDistList : IMAPIContainer](idistlistimapicontainer.md) interfaces are derived from **IMAPIContainer**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1673a-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="1673a-107">Header file:</span></span>  <br/> |<span data-ttu-id="1673a-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1673a-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="1673a-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="1673a-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="1673a-110">文件夹、 通讯簿容器和通讯组列表对象</span><span class="sxs-lookup"><span data-stu-id="1673a-110">Folder, address book container, and distribution list objects</span></span>  <br/> |
|<span data-ttu-id="1673a-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="1673a-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="1673a-112">消息存储、 通讯簿和远程传输提供程序</span><span class="sxs-lookup"><span data-stu-id="1673a-112">Message store, address book, and remote transport providers</span></span>  <br/> |
|<span data-ttu-id="1673a-113">调用：</span><span class="sxs-lookup"><span data-stu-id="1673a-113">Called by:</span></span>  <br/> |<span data-ttu-id="1673a-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1673a-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="1673a-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="1673a-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="1673a-116">IID_IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="1673a-116">IID_IMAPIContainer</span></span>  <br/> |
|<span data-ttu-id="1673a-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="1673a-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="1673a-118">LPMAPICONTAINER</span><span class="sxs-lookup"><span data-stu-id="1673a-118">LPMAPICONTAINER</span></span>  <br/> |
|<span data-ttu-id="1673a-119">事务模型：</span><span class="sxs-lookup"><span data-stu-id="1673a-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="1673a-120">从不实现抽象类</span><span class="sxs-lookup"><span data-stu-id="1673a-120">Abstract class, never implemented</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="1673a-121">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="1673a-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="1673a-122">GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="1673a-122">GetContentsTable</span></span>](imapicontainer-getcontentstable.md) <br/> |<span data-ttu-id="1673a-123">返回到容器的内容表的指针。</span><span class="sxs-lookup"><span data-stu-id="1673a-123">Returns a pointer to the container's contents table.</span></span>  <br/> |
|[<span data-ttu-id="1673a-124">通讯</span><span class="sxs-lookup"><span data-stu-id="1673a-124">GetHierarchyTable</span></span>](imapicontainer-gethierarchytable.md) <br/> |<span data-ttu-id="1673a-125">返回到容器的层次结构表的指针。</span><span class="sxs-lookup"><span data-stu-id="1673a-125">Returns a pointer to the container's hierarchy table.</span></span>  <br/> |
|[<span data-ttu-id="1673a-126">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="1673a-126">OpenEntry</span></span>](imapicontainer-openentry.md) <br/> |<span data-ttu-id="1673a-127">在该容器，返回进一步访问的接口指针中打开一个对象。</span><span class="sxs-lookup"><span data-stu-id="1673a-127">Opens an object in the container, returning an interface pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="1673a-128">SetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="1673a-128">SetSearchCriteria</span></span>](imapicontainer-setsearchcriteria.md) <br/> |<span data-ttu-id="1673a-129">建立容器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="1673a-129">Establishes search criteria for the container.</span></span>  <br/> |
|[<span data-ttu-id="1673a-130">GetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="1673a-130">GetSearchCriteria</span></span>](imapicontainer-getsearchcriteria.md) <br/> |<span data-ttu-id="1673a-131">获取容器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="1673a-131">Obtains the search criteria for the container.</span></span>  <br/> |
   
|<span data-ttu-id="1673a-132">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="1673a-132">**Required properties**</span></span>|<span data-ttu-id="1673a-133">**Access**</span><span class="sxs-lookup"><span data-stu-id="1673a-133">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1673a-134">**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1673a-134">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1673a-135">只读</span><span class="sxs-lookup"><span data-stu-id="1673a-135">Read-only</span></span>  <br/> |
|<span data-ttu-id="1673a-136">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1673a-136">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1673a-137">只读</span><span class="sxs-lookup"><span data-stu-id="1673a-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="1673a-138">**PR_CONTAINER_FLAGS**([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1673a-138">**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1673a-139">读/写</span><span class="sxs-lookup"><span data-stu-id="1673a-139">Read/write</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1673a-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1673a-140">See also</span></span>



[<span data-ttu-id="1673a-141">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="1673a-141">MAPI Interfaces</span></span>](mapi-interfaces.md)

