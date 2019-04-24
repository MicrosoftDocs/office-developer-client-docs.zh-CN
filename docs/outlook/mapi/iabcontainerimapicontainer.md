---
title: IABContainer IMAPIContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer
api_type:
- COM
ms.assetid: 1f5ce6e0-b79a-4da2-b014-8c00cd72912e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0905fbe2ba584aef49c50152aaf448267d477c10
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348956"
---
# <a name="iabcontainer--imapicontainer"></a><span data-ttu-id="9872d-103">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="9872d-103">IABContainer : IMAPIContainer</span></span>

<span data-ttu-id="9872d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9872d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9872d-105">提供对通讯簿容器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9872d-105">Provides access to address book containers.</span></span> <span data-ttu-id="9872d-106">MAPI 和客户端应用程序调用**IABContainer**方法来执行名称解析以及创建、复制和删除收件人。</span><span class="sxs-lookup"><span data-stu-id="9872d-106">MAPI and client applications call the methods of **IABContainer** to perform name resolution and to create, copy, and delete recipients.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9872d-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="9872d-107">Header file:</span></span>  <br/> |<span data-ttu-id="9872d-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9872d-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="9872d-109">公开者:</span><span class="sxs-lookup"><span data-stu-id="9872d-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="9872d-110">通讯簿容器对象</span><span class="sxs-lookup"><span data-stu-id="9872d-110">Address book container objects</span></span>  <br/> |
|<span data-ttu-id="9872d-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="9872d-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="9872d-112">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="9872d-112">Address book providers</span></span>  <br/> |
|<span data-ttu-id="9872d-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="9872d-113">Called by:</span></span>  <br/> |<span data-ttu-id="9872d-114">MAPI 和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="9872d-114">MAPI and client applications</span></span>  <br/> |
|<span data-ttu-id="9872d-115">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="9872d-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="9872d-116">IID_IABContainer</span><span class="sxs-lookup"><span data-stu-id="9872d-116">IID_IABContainer</span></span>  <br/> |
|<span data-ttu-id="9872d-117">指针类型:</span><span class="sxs-lookup"><span data-stu-id="9872d-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="9872d-118">LPABCONT</span><span class="sxs-lookup"><span data-stu-id="9872d-118">LPABCONT</span></span>  <br/> |
|<span data-ttu-id="9872d-119">事务模型:</span><span class="sxs-lookup"><span data-stu-id="9872d-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="9872d-120">事务</span><span class="sxs-lookup"><span data-stu-id="9872d-120">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="9872d-121">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="9872d-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="9872d-122">CreateEntry</span><span class="sxs-lookup"><span data-stu-id="9872d-122">CreateEntry</span></span>](iabcontainer-createentry.md) <br/> |<span data-ttu-id="9872d-123">创建一个新的条目, 该条目可以是邮件用户、通讯组列表或其他容器。</span><span class="sxs-lookup"><span data-stu-id="9872d-123">Creates a new entry, which can be a messaging user, a distribution list, or another container.</span></span>  <br/> |
|[<span data-ttu-id="9872d-124">CopyEntries</span><span class="sxs-lookup"><span data-stu-id="9872d-124">CopyEntries</span></span>](iabcontainer-copyentries.md) <br/> |<span data-ttu-id="9872d-125">复制一个或多个条目, 通常是邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="9872d-125">Copies one or more entries, typically messaging users or distribution lists.</span></span>  <br/> |
|[<span data-ttu-id="9872d-126">DeleteEntries</span><span class="sxs-lookup"><span data-stu-id="9872d-126">DeleteEntries</span></span>](iabcontainer-deleteentries.md) <br/> |<span data-ttu-id="9872d-127">删除一个或多个条目, 通常是邮件用户、通讯组列表或其他容器。</span><span class="sxs-lookup"><span data-stu-id="9872d-127">Removes one or more entries, typically messaging users, distribution lists, or other containers.</span></span>  <br/> |
|[<span data-ttu-id="9872d-128">ResolveNames</span><span class="sxs-lookup"><span data-stu-id="9872d-128">ResolveNames</span></span>](iabcontainer-resolvenames.md) <br/> |<span data-ttu-id="9872d-129">为一个或多个收件人条目执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="9872d-129">Performs name resolution for one or more recipient entries.</span></span>  <br/> |
   
|<span data-ttu-id="9872d-130">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="9872d-130">**Required properties**</span></span>|<span data-ttu-id="9872d-131">**Access**</span><span class="sxs-lookup"><span data-stu-id="9872d-131">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9872d-132">**PR_CONTAINER_FLAGS**([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-132">**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-133">读/写</span><span class="sxs-lookup"><span data-stu-id="9872d-133">Read/write</span></span>  <br/> |
|<span data-ttu-id="9872d-134">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-134">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-135">读/写</span><span class="sxs-lookup"><span data-stu-id="9872d-135">Read/write</span></span>  <br/> |
|<span data-ttu-id="9872d-136">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-136">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-137">只读</span><span class="sxs-lookup"><span data-stu-id="9872d-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="9872d-138">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-138">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-139">只读</span><span class="sxs-lookup"><span data-stu-id="9872d-139">Read-only</span></span>  <br/> |
|<span data-ttu-id="9872d-140">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-140">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-141">只读</span><span class="sxs-lookup"><span data-stu-id="9872d-141">Read-only</span></span>  <br/> |
   
|<span data-ttu-id="9872d-142">**可选属性**</span><span class="sxs-lookup"><span data-stu-id="9872d-142">**Optional properties**</span></span>|<span data-ttu-id="9872d-143">**Access**</span><span class="sxs-lookup"><span data-stu-id="9872d-143">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9872d-144">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-144">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-145">只读</span><span class="sxs-lookup"><span data-stu-id="9872d-145">Read-only</span></span>  <br/> |
|<span data-ttu-id="9872d-146">**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-146">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-147">只读</span><span class="sxs-lookup"><span data-stu-id="9872d-147">Read-only</span></span>  <br/> |
|<span data-ttu-id="9872d-148">**PR_DEF_CREATE_DL**([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-148">**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-149">只读</span><span class="sxs-lookup"><span data-stu-id="9872d-149">Read-only</span></span>  <br/> |
|<span data-ttu-id="9872d-150">**PR_DEF_CREATE_MAILUSER**([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-150">**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-151">只读</span><span class="sxs-lookup"><span data-stu-id="9872d-151">Read-only</span></span>  <br/> |
|<span data-ttu-id="9872d-152">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9872d-152">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9872d-153">只读</span><span class="sxs-lookup"><span data-stu-id="9872d-153">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9872d-154">注解</span><span class="sxs-lookup"><span data-stu-id="9872d-154">Remarks</span></span>

<span data-ttu-id="9872d-155">**IABContainer**接口通过[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)和[IMAPIProp: IUnknown](imapipropiunknown.md)接口间接继承自[IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="9872d-155">The **IABContainer** interface inherits indirectly from the [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) interface through the [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md) and [IMAPIProp : IUnknown](imapipropiunknown.md) interfaces.</span></span> <span data-ttu-id="9872d-156">通讯簿提供程序实现**IABContainer**接口。</span><span class="sxs-lookup"><span data-stu-id="9872d-156">Address book providers implement the **IABContainer** interface.</span></span> 
  
<span data-ttu-id="9872d-157">通讯簿容器中可以存在任意数量的邮件用户对象、通讯组列表和其他通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="9872d-157">Any number of messaging user objects, distribution lists, and other address book containers can exist in an address book container.</span></span> <span data-ttu-id="9872d-158">与任何容器一样, 客户端或服务提供程序可以使用通讯簿容器打开其中一个条目或检索层次结构表或内容表。</span><span class="sxs-lookup"><span data-stu-id="9872d-158">As with any container, clients or service providers can use an address book container to open one of its entries or to retrieve a hierarchy table or contents table.</span></span> <span data-ttu-id="9872d-159">通讯簿容器还提供名称解析, 具体取决于提供程序、添加、删除或修改条目的功能。</span><span class="sxs-lookup"><span data-stu-id="9872d-159">Address book containers also provide name resolution and, depending on the provider, the ability to add, remove, or modify entries.</span></span>
  
<span data-ttu-id="9872d-160">MAPI 定义了一个名为 "个人通讯簿 (PAB)" 的特殊通讯簿容器, 该容器保留从其他容器复制的条目。</span><span class="sxs-lookup"><span data-stu-id="9872d-160">MAPI defines a special address book container called the personal address book (PAB) that holds entries copied from other containers.</span></span> <span data-ttu-id="9872d-161">PAB 始终是可修改的。</span><span class="sxs-lookup"><span data-stu-id="9872d-161">A PAB is always modifiable.</span></span> <span data-ttu-id="9872d-162">用户通常用其自己的 PAB 填充其 PAB, 以指定他们最常与之通信的收件人。</span><span class="sxs-lookup"><span data-stu-id="9872d-162">Users typically populate their PAB with entries designating the recipients with which they most frequently communicate.</span></span> <span data-ttu-id="9872d-163">PAB 也可以保留一次性地址和新的收件人, 而不是任何通讯簿容器的一部分。</span><span class="sxs-lookup"><span data-stu-id="9872d-163">A PAB can also hold one-off addresses and new recipients not yet a part of any address book container.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9872d-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9872d-164">See also</span></span>

- [<span data-ttu-id="9872d-165">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="9872d-165">MAPI Interfaces</span></span>](mapi-interfaces.md)

