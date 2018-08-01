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
ms.openlocfilehash: 0eb6d62b64595474957415e94275d0ac52cc2b6b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775200"
---
# <a name="iabcontainer--imapicontainer"></a><span data-ttu-id="41de5-103">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="41de5-103">IABContainer : IMAPIContainer</span></span>

<span data-ttu-id="41de5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="41de5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="41de5-105">提供对通讯簿容器的访问。</span><span class="sxs-lookup"><span data-stu-id="41de5-105">Provides access to address book containers.</span></span> <span data-ttu-id="41de5-106">MAPI 和客户端应用程序调用**IABContainer**执行名称解析和创建、 复制方法，并删除收件人。</span><span class="sxs-lookup"><span data-stu-id="41de5-106">MAPI and client applications call the methods of **IABContainer** to perform name resolution and to create, copy, and delete recipients.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="41de5-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="41de5-107">Header file:</span></span>  <br/> |<span data-ttu-id="41de5-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="41de5-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="41de5-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="41de5-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="41de5-110">通讯簿容器对象</span><span class="sxs-lookup"><span data-stu-id="41de5-110">Address book container objects</span></span>  <br/> |
|<span data-ttu-id="41de5-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="41de5-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="41de5-112">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="41de5-112">Address book providers</span></span>  <br/> |
|<span data-ttu-id="41de5-113">调用：</span><span class="sxs-lookup"><span data-stu-id="41de5-113">Called by:</span></span>  <br/> |<span data-ttu-id="41de5-114">MAPI 和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="41de5-114">MAPI and client applications</span></span>  <br/> |
|<span data-ttu-id="41de5-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="41de5-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="41de5-116">IID_IABContainer</span><span class="sxs-lookup"><span data-stu-id="41de5-116">IID_IABContainer</span></span>  <br/> |
|<span data-ttu-id="41de5-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="41de5-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="41de5-118">LPABCONT</span><span class="sxs-lookup"><span data-stu-id="41de5-118">LPABCONT</span></span>  <br/> |
|<span data-ttu-id="41de5-119">事务模型：</span><span class="sxs-lookup"><span data-stu-id="41de5-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="41de5-120">事务处理</span><span class="sxs-lookup"><span data-stu-id="41de5-120">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="41de5-121">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="41de5-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="41de5-122">CreateEntry</span><span class="sxs-lookup"><span data-stu-id="41de5-122">CreateEntry</span></span>](iabcontainer-createentry.md) <br/> |<span data-ttu-id="41de5-123">创建一个新项，可以是邮件用户、 通讯组列表或其他容器。</span><span class="sxs-lookup"><span data-stu-id="41de5-123">Creates a new entry, which can be a messaging user, a distribution list, or another container.</span></span>  <br/> |
|[<span data-ttu-id="41de5-124">CopyEntries</span><span class="sxs-lookup"><span data-stu-id="41de5-124">CopyEntries</span></span>](iabcontainer-copyentries.md) <br/> |<span data-ttu-id="41de5-125">复制一个或多个条目，通常消息的用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="41de5-125">Copies one or more entries, typically messaging users or distribution lists.</span></span>  <br/> |
|[<span data-ttu-id="41de5-126">DeleteEntries</span><span class="sxs-lookup"><span data-stu-id="41de5-126">DeleteEntries</span></span>](iabcontainer-deleteentries.md) <br/> |<span data-ttu-id="41de5-127">删除一个或多个条目，通常消息的用户、 通讯组列表或其他容器。</span><span class="sxs-lookup"><span data-stu-id="41de5-127">Removes one or more entries, typically messaging users, distribution lists, or other containers.</span></span>  <br/> |
|[<span data-ttu-id="41de5-128">ResolveNames</span><span class="sxs-lookup"><span data-stu-id="41de5-128">ResolveNames</span></span>](iabcontainer-resolvenames.md) <br/> |<span data-ttu-id="41de5-129">执行一个或多个收件人的条目的名称解析。</span><span class="sxs-lookup"><span data-stu-id="41de5-129">Performs name resolution for one or more recipient entries.</span></span>  <br/> |
   
|<span data-ttu-id="41de5-130">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="41de5-130">**Required properties**</span></span>|<span data-ttu-id="41de5-131">**Access**</span><span class="sxs-lookup"><span data-stu-id="41de5-131">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41de5-132">**PR_CONTAINER_FLAGS**([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-132">**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-133">读/写</span><span class="sxs-lookup"><span data-stu-id="41de5-133">Read/write</span></span>  <br/> |
|<span data-ttu-id="41de5-134">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-134">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-135">读/写</span><span class="sxs-lookup"><span data-stu-id="41de5-135">Read/write</span></span>  <br/> |
|<span data-ttu-id="41de5-136">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-136">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-137">只读</span><span class="sxs-lookup"><span data-stu-id="41de5-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="41de5-138">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-138">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-139">只读</span><span class="sxs-lookup"><span data-stu-id="41de5-139">Read-only</span></span>  <br/> |
|<span data-ttu-id="41de5-140">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-140">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-141">只读</span><span class="sxs-lookup"><span data-stu-id="41de5-141">Read-only</span></span>  <br/> |
   
|<span data-ttu-id="41de5-142">**可选属性**</span><span class="sxs-lookup"><span data-stu-id="41de5-142">**Optional properties**</span></span>|<span data-ttu-id="41de5-143">**Access**</span><span class="sxs-lookup"><span data-stu-id="41de5-143">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41de5-144">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-144">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-145">只读</span><span class="sxs-lookup"><span data-stu-id="41de5-145">Read-only</span></span>  <br/> |
|<span data-ttu-id="41de5-146">**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-146">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-147">只读</span><span class="sxs-lookup"><span data-stu-id="41de5-147">Read-only</span></span>  <br/> |
|<span data-ttu-id="41de5-148">**PR_DEF_CREATE_DL**([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-148">**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-149">只读</span><span class="sxs-lookup"><span data-stu-id="41de5-149">Read-only</span></span>  <br/> |
|<span data-ttu-id="41de5-150">**PR_DEF_CREATE_MAILUSER**([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-150">**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-151">只读</span><span class="sxs-lookup"><span data-stu-id="41de5-151">Read-only</span></span>  <br/> |
|<span data-ttu-id="41de5-152">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="41de5-152">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="41de5-153">只读</span><span class="sxs-lookup"><span data-stu-id="41de5-153">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="41de5-154">说明</span><span class="sxs-lookup"><span data-stu-id="41de5-154">Remarks</span></span>

<span data-ttu-id="41de5-155">**IABContainer**接口从[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx)接口通过间接继承[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)和[IMAPIProp: IUnknown](imapipropiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="41de5-155">The **IABContainer** interface inherits indirectly from the [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx) interface through the [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md) and [IMAPIProp : IUnknown](imapipropiunknown.md) interfaces.</span></span> <span data-ttu-id="41de5-156">通讯簿提供程序实现**IABContainer**接口。</span><span class="sxs-lookup"><span data-stu-id="41de5-156">Address book providers implement the **IABContainer** interface.</span></span> 
  
<span data-ttu-id="41de5-157">通讯簿容器中存在可以任意数量的消息的用户对象、 通讯组列表和其他通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="41de5-157">Any number of messaging user objects, distribution lists, and other address book containers can exist in an address book container.</span></span> <span data-ttu-id="41de5-158">与任何容器，客户端或服务提供商可以使用通讯簿容器来打开其项之一或检索层次结构表或内容表。</span><span class="sxs-lookup"><span data-stu-id="41de5-158">As with any container, clients or service providers can use an address book container to open one of its entries or to retrieve a hierarchy table or contents table.</span></span> <span data-ttu-id="41de5-159">通讯的簿容器还提供名称解析，取决于提供程序，可以添加、 删除或修改条目。</span><span class="sxs-lookup"><span data-stu-id="41de5-159">Address book containers also provide name resolution and, depending on the provider, the ability to add, remove, or modify entries.</span></span>
  
<span data-ttu-id="41de5-160">MAPI 定义名为容纳从其他容器复制的项的个人通讯簿 (PAB) 特殊通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="41de5-160">MAPI defines a special address book container called the personal address book (PAB) that holds entries copied from other containers.</span></span> <span data-ttu-id="41de5-161">PAB 始终是修改的。</span><span class="sxs-lookup"><span data-stu-id="41de5-161">A PAB is always modifiable.</span></span> <span data-ttu-id="41de5-162">用户通常填充其 PAB 指定与他们通常通信的收件人的条目。</span><span class="sxs-lookup"><span data-stu-id="41de5-162">Users typically populate their PAB with entries designating the recipients with which they most frequently communicate.</span></span> <span data-ttu-id="41de5-163">PAB 也可以容纳一次性地址和新的收件人尚未任何通讯簿容器的一部分。</span><span class="sxs-lookup"><span data-stu-id="41de5-163">A PAB can also hold one-off addresses and new recipients not yet a part of any address book container.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41de5-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41de5-164">See also</span></span>

- [<span data-ttu-id="41de5-165">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="41de5-165">MAPI Interfaces</span></span>](mapi-interfaces.md)

