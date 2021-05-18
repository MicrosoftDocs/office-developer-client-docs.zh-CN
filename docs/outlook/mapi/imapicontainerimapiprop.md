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
ms.openlocfilehash: 8be3b1857d539f81e42d2ac3e5813afa73513a16
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406120"
---
# <a name="imapicontainer--imapiprop"></a><span data-ttu-id="749ce-103">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="749ce-103">IMAPIContainer : IMAPIProp</span></span>

  
  
<span data-ttu-id="749ce-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="749ce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="749ce-105">管理对容器对象（如通讯簿、通讯组列表和文件夹）的高级别操作。</span><span class="sxs-lookup"><span data-stu-id="749ce-105">Manages high-level operations on container objects such as address books, distribution lists, and folders.</span></span> <span data-ttu-id="749ce-106">[IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)， [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)， and [IDistList ： IMAPIContainer](idistlistimapicontainer.md) interfaces are derived from **IMAPIContainer**.</span><span class="sxs-lookup"><span data-stu-id="749ce-106">The [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md), [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md), and [IDistList : IMAPIContainer](idistlistimapicontainer.md) interfaces are derived from **IMAPIContainer**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="749ce-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="749ce-107">Header file:</span></span>  <br/> |<span data-ttu-id="749ce-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="749ce-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="749ce-109">公开者：</span><span class="sxs-lookup"><span data-stu-id="749ce-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="749ce-110">文件夹、通讯簿容器和通讯组列表对象</span><span class="sxs-lookup"><span data-stu-id="749ce-110">Folder, address book container, and distribution list objects</span></span>  <br/> |
|<span data-ttu-id="749ce-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="749ce-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="749ce-112">邮件存储、通讯簿和远程传输提供程序</span><span class="sxs-lookup"><span data-stu-id="749ce-112">Message store, address book, and remote transport providers</span></span>  <br/> |
|<span data-ttu-id="749ce-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="749ce-113">Called by:</span></span>  <br/> |<span data-ttu-id="749ce-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="749ce-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="749ce-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="749ce-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="749ce-116">IID_IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="749ce-116">IID_IMAPIContainer</span></span>  <br/> |
|<span data-ttu-id="749ce-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="749ce-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="749ce-118">LPMAPICONTAINER</span><span class="sxs-lookup"><span data-stu-id="749ce-118">LPMAPICONTAINER</span></span>  <br/> |
|<span data-ttu-id="749ce-119">事务模型：</span><span class="sxs-lookup"><span data-stu-id="749ce-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="749ce-120">抽象类，从未实现</span><span class="sxs-lookup"><span data-stu-id="749ce-120">Abstract class, never implemented</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="749ce-121">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="749ce-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="749ce-122">GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="749ce-122">GetContentsTable</span></span>](imapicontainer-getcontentstable.md) <br/> |<span data-ttu-id="749ce-123">返回一个指向容器内容表的指针。</span><span class="sxs-lookup"><span data-stu-id="749ce-123">Returns a pointer to the container's contents table.</span></span>  <br/> |
|[<span data-ttu-id="749ce-124">GetHierarchyTable</span><span class="sxs-lookup"><span data-stu-id="749ce-124">GetHierarchyTable</span></span>](imapicontainer-gethierarchytable.md) <br/> |<span data-ttu-id="749ce-125">返回一个指向容器层次结构表的指针。</span><span class="sxs-lookup"><span data-stu-id="749ce-125">Returns a pointer to the container's hierarchy table.</span></span>  <br/> |
|[<span data-ttu-id="749ce-126">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="749ce-126">OpenEntry</span></span>](imapicontainer-openentry.md) <br/> |<span data-ttu-id="749ce-127">打开容器中的对象，返回接口指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="749ce-127">Opens an object in the container, returning an interface pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="749ce-128">SetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="749ce-128">SetSearchCriteria</span></span>](imapicontainer-setsearchcriteria.md) <br/> |<span data-ttu-id="749ce-129">为容器建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="749ce-129">Establishes search criteria for the container.</span></span>  <br/> |
|[<span data-ttu-id="749ce-130">GetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="749ce-130">GetSearchCriteria</span></span>](imapicontainer-getsearchcriteria.md) <br/> |<span data-ttu-id="749ce-131">获取容器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="749ce-131">Obtains the search criteria for the container.</span></span>  <br/> |
   
|<span data-ttu-id="749ce-132">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="749ce-132">**Required properties**</span></span>|<span data-ttu-id="749ce-133">**Access**</span><span class="sxs-lookup"><span data-stu-id="749ce-133">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="749ce-134">**PR_CONTAINER_HIERARCHY (** [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="749ce-134">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="749ce-135">只读</span><span class="sxs-lookup"><span data-stu-id="749ce-135">Read-only</span></span>  <br/> |
|<span data-ttu-id="749ce-136">**PR_CONTAINER_CONTENTS (** [PidTagContainerContents)](pidtagcontainercontents-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="749ce-136">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="749ce-137">只读</span><span class="sxs-lookup"><span data-stu-id="749ce-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="749ce-138">**PR_CONTAINER_FLAGS (** [PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="749ce-138">**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="749ce-139">读/写</span><span class="sxs-lookup"><span data-stu-id="749ce-139">Read/write</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="749ce-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="749ce-140">See also</span></span>



[<span data-ttu-id="749ce-141">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="749ce-141">MAPI Interfaces</span></span>](mapi-interfaces.md)

