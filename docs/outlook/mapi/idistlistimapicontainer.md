---
title: IDistList IMAPIContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IDistList
api_type:
- COM
ms.assetid: bd8e1ddb-3027-428b-8964-81614f80282d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7fee3c84d6a4d4a94397f5197f45637b0c7dd2be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775302"
---
# <a name="idistlist--imapicontainer"></a><span data-ttu-id="e6f50-103">IDistList : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="e6f50-103">IDistList : IMAPIContainer</span></span>

  
  
<span data-ttu-id="e6f50-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e6f50-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e6f50-105">提供对通讯组列表，在地址可修改访问簿容器。</span><span class="sxs-lookup"><span data-stu-id="e6f50-105">Provides access to distribution lists in modifiable address book containers.</span></span> <span data-ttu-id="e6f50-106">**IDistList**可以创建、 复制和删除通讯组列表，除了执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="e6f50-106">**IDistList** can create, copy, and delete distribution lists, in addition to performing name resolution.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6f50-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="e6f50-107">Header file:</span></span>  <br/> |<span data-ttu-id="e6f50-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e6f50-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="e6f50-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="e6f50-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="e6f50-110">通讯组列表对象</span><span class="sxs-lookup"><span data-stu-id="e6f50-110">Distribution list objects</span></span>  <br/> |
|<span data-ttu-id="e6f50-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="e6f50-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="e6f50-112">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="e6f50-112">Address book providers</span></span>  <br/> |
|<span data-ttu-id="e6f50-113">调用：</span><span class="sxs-lookup"><span data-stu-id="e6f50-113">Called by:</span></span>  <br/> |<span data-ttu-id="e6f50-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="e6f50-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="e6f50-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="e6f50-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="e6f50-116">IID_IDistList</span><span class="sxs-lookup"><span data-stu-id="e6f50-116">IID_IDistList</span></span>  <br/> |
|<span data-ttu-id="e6f50-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="e6f50-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="e6f50-118">LPDISTLIST</span><span class="sxs-lookup"><span data-stu-id="e6f50-118">LPDISTLIST</span></span>  <br/> |
|<span data-ttu-id="e6f50-119">事务模型：</span><span class="sxs-lookup"><span data-stu-id="e6f50-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="e6f50-120">事务处理</span><span class="sxs-lookup"><span data-stu-id="e6f50-120">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="e6f50-121">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="e6f50-121">Vtable order</span></span>

<span data-ttu-id="e6f50-122">此接口不具有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="e6f50-122">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="e6f50-123">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="e6f50-123">**Required properties**</span></span>|<span data-ttu-id="e6f50-124">**Access**</span><span class="sxs-lookup"><span data-stu-id="e6f50-124">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6f50-125">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e6f50-125">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6f50-126">读/写</span><span class="sxs-lookup"><span data-stu-id="e6f50-126">Read/write</span></span>  <br/> |
|<span data-ttu-id="e6f50-127">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e6f50-127">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6f50-128">读/写</span><span class="sxs-lookup"><span data-stu-id="e6f50-128">Read/write</span></span>  <br/> |
|<span data-ttu-id="e6f50-129">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e6f50-129">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6f50-130">只读</span><span class="sxs-lookup"><span data-stu-id="e6f50-130">Read-only</span></span>  <br/> |
|<span data-ttu-id="e6f50-131">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e6f50-131">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6f50-132">只读</span><span class="sxs-lookup"><span data-stu-id="e6f50-132">Read-only</span></span>  <br/> |
|<span data-ttu-id="e6f50-133">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e6f50-133">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6f50-134">只读</span><span class="sxs-lookup"><span data-stu-id="e6f50-134">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6f50-135">说明</span><span class="sxs-lookup"><span data-stu-id="e6f50-135">Remarks</span></span>

<span data-ttu-id="e6f50-136">**IDistList**接口继承[IMAPIContainer](imapicontainerimapiprop.md) ，并包括作为通讯簿容器相同的方法。</span><span class="sxs-lookup"><span data-stu-id="e6f50-136">The **IDistList** interface inherits from [IMAPIContainer](imapicontainerimapiprop.md) and includes the same methods as address book containers.</span></span> <span data-ttu-id="e6f50-137">因此，因为**IDistList**接口的方法是那些[IABContainer](iabcontainerimapicontainer.md)接口的完全相同，它们不会复制此处。</span><span class="sxs-lookup"><span data-stu-id="e6f50-137">Therefore, because the methods of the **IDistList** interface are identical to those of the [IABContainer](iabcontainerimapicontainer.md) interface, they are not duplicated here.</span></span> 
  
<span data-ttu-id="e6f50-138">通讯组列表或实现**IDistList**对象的消息的用户对象或单个收件人集合。</span><span class="sxs-lookup"><span data-stu-id="e6f50-138">A distribution list or object that implements **IDistList** is a collection of messaging user objects, or individual recipients.</span></span> <span data-ttu-id="e6f50-139">通讯组列表可以包含所有邮件用户对象，或某些消息的用户和一些通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6f50-139">A distribution list can consist of all messaging user objects, or some messaging user and some distribution lists.</span></span> 
  
<span data-ttu-id="e6f50-140">通常有两种类型的通讯组列表：</span><span class="sxs-lookup"><span data-stu-id="e6f50-140">There are typically two types of distribution lists:</span></span>
  
- <span data-ttu-id="e6f50-141">扩展基础消息系统的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6f50-141">Distribution lists that are expanded by the underlying messaging system.</span></span> <span data-ttu-id="e6f50-142">此类型的列表具有地址， **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))，并且视为相同好像它是单独的收件人。</span><span class="sxs-lookup"><span data-stu-id="e6f50-142">This type of list has an address, **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), and is treated the same as if it were an individual recipient.</span></span> 
    
- <span data-ttu-id="e6f50-143">本地容器中存在的且由客户端应用程序扩展的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6f50-143">Distribution lists that exist in a local container and are expanded by the client application.</span></span>
    
<span data-ttu-id="e6f50-144">可选的通讯组列表属性包括：</span><span class="sxs-lookup"><span data-stu-id="e6f50-144">Optional distribution list properties include the following:</span></span>
  
- <span data-ttu-id="e6f50-145">**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e6f50-145">**PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="e6f50-146">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e6f50-146">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span> 
    
- <span data-ttu-id="e6f50-147">**PR_DETAILS_TABLE**([PidTagDetailsTable](pidtagdetailstable-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e6f50-147">**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md))</span></span> 
    
<span data-ttu-id="e6f50-148">注意**PR_ADDRTYPE**是必需的而不是**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="e6f50-148">Notice that **PR_ADDRTYPE** is required, but **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) is not.</span></span> <span data-ttu-id="e6f50-149">这是因为通讯组列表的电子邮件地址不仍可以接收邮件，但必须扩展其成员列表。</span><span class="sxs-lookup"><span data-stu-id="e6f50-149">That is because a distribution list without an email address can still receive messages, but its member list must be expanded.</span></span> <span data-ttu-id="e6f50-150">如果**PR_ADDRTYPE**属性设置为 MAPIPDL，MAPI 执行扩展。</span><span class="sxs-lookup"><span data-stu-id="e6f50-150">If the **PR_ADDRTYPE** property is set to MAPIPDL, MAPI performs the expansion.</span></span> <span data-ttu-id="e6f50-151">**PR_ADDRTYPE**是 MAPIPDL 之外的一个值，则传输提供程序执行扩展。</span><span class="sxs-lookup"><span data-stu-id="e6f50-151">If **PR_ADDRTYPE** is a value other than MAPIPDL, the transport provider performs the expansion.</span></span> 
  
<span data-ttu-id="e6f50-152">有关如何使用**IDistList**方法的其他信息，请参阅**IABContainer**的并行方法的引用条目。</span><span class="sxs-lookup"><span data-stu-id="e6f50-152">For additional information about how to use the **IDistList** methods, see the reference entries for the parallel methods of **IABContainer**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e6f50-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6f50-153">See also</span></span>



[<span data-ttu-id="e6f50-154">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="e6f50-154">MAPI Interfaces</span></span>](mapi-interfaces.md)

