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
ms.openlocfilehash: 463d81a6692b6071cada0ad22e7343020563e41c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350888"
---
# <a name="idistlist--imapicontainer"></a><span data-ttu-id="68d6a-103">IDistList : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="68d6a-103">IDistList : IMAPIContainer</span></span>

  
  
<span data-ttu-id="68d6a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="68d6a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="68d6a-105">提供对可修改通讯簿容器中的通讯组列表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="68d6a-105">Provides access to distribution lists in modifiable address book containers.</span></span> <span data-ttu-id="68d6a-106">除了执行名称解析之外, **IDistList**还可以创建、复制和删除通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="68d6a-106">**IDistList** can create, copy, and delete distribution lists, in addition to performing name resolution.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="68d6a-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="68d6a-107">Header file:</span></span>  <br/> |<span data-ttu-id="68d6a-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="68d6a-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="68d6a-109">公开者:</span><span class="sxs-lookup"><span data-stu-id="68d6a-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="68d6a-110">通讯组列表对象</span><span class="sxs-lookup"><span data-stu-id="68d6a-110">Distribution list objects</span></span>  <br/> |
|<span data-ttu-id="68d6a-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="68d6a-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="68d6a-112">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="68d6a-112">Address book providers</span></span>  <br/> |
|<span data-ttu-id="68d6a-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="68d6a-113">Called by:</span></span>  <br/> |<span data-ttu-id="68d6a-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="68d6a-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="68d6a-115">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="68d6a-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="68d6a-116">IID_IDistList</span><span class="sxs-lookup"><span data-stu-id="68d6a-116">IID_IDistList</span></span>  <br/> |
|<span data-ttu-id="68d6a-117">指针类型:</span><span class="sxs-lookup"><span data-stu-id="68d6a-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="68d6a-118">LPDISTLIST</span><span class="sxs-lookup"><span data-stu-id="68d6a-118">LPDISTLIST</span></span>  <br/> |
|<span data-ttu-id="68d6a-119">事务模型:</span><span class="sxs-lookup"><span data-stu-id="68d6a-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="68d6a-120">事务</span><span class="sxs-lookup"><span data-stu-id="68d6a-120">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="68d6a-121">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="68d6a-121">Vtable order</span></span>

<span data-ttu-id="68d6a-122">此接口没有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="68d6a-122">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="68d6a-123">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="68d6a-123">**Required properties**</span></span>|<span data-ttu-id="68d6a-124">**Access**</span><span class="sxs-lookup"><span data-stu-id="68d6a-124">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="68d6a-125">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="68d6a-125">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="68d6a-126">读/写</span><span class="sxs-lookup"><span data-stu-id="68d6a-126">Read/write</span></span>  <br/> |
|<span data-ttu-id="68d6a-127">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="68d6a-127">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="68d6a-128">读/写</span><span class="sxs-lookup"><span data-stu-id="68d6a-128">Read/write</span></span>  <br/> |
|<span data-ttu-id="68d6a-129">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="68d6a-129">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="68d6a-130">只读</span><span class="sxs-lookup"><span data-stu-id="68d6a-130">Read-only</span></span>  <br/> |
|<span data-ttu-id="68d6a-131">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="68d6a-131">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="68d6a-132">只读</span><span class="sxs-lookup"><span data-stu-id="68d6a-132">Read-only</span></span>  <br/> |
|<span data-ttu-id="68d6a-133">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="68d6a-133">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="68d6a-134">只读</span><span class="sxs-lookup"><span data-stu-id="68d6a-134">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="68d6a-135">注解</span><span class="sxs-lookup"><span data-stu-id="68d6a-135">Remarks</span></span>

<span data-ttu-id="68d6a-136">**IDistList**接口继承自[IMAPIContainer](imapicontainerimapiprop.md) , 并包含与通讯簿容器相同的方法。</span><span class="sxs-lookup"><span data-stu-id="68d6a-136">The **IDistList** interface inherits from [IMAPIContainer](imapicontainerimapiprop.md) and includes the same methods as address book containers.</span></span> <span data-ttu-id="68d6a-137">因此, 由于**IDistList**接口的方法与[IABContainer](iabcontainerimapicontainer.md)接口的方法相同, 因此不会在此处复制它们。</span><span class="sxs-lookup"><span data-stu-id="68d6a-137">Therefore, because the methods of the **IDistList** interface are identical to those of the [IABContainer](iabcontainerimapicontainer.md) interface, they are not duplicated here.</span></span> 
  
<span data-ttu-id="68d6a-138">实现**IDistList**的通讯组列表或对象是邮件用户对象或单个收件人的集合。</span><span class="sxs-lookup"><span data-stu-id="68d6a-138">A distribution list or object that implements **IDistList** is a collection of messaging user objects, or individual recipients.</span></span> <span data-ttu-id="68d6a-139">通讯组列表可以包含所有邮件用户对象, 或某些邮件用户和一些通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="68d6a-139">A distribution list can consist of all messaging user objects, or some messaging user and some distribution lists.</span></span> 
  
<span data-ttu-id="68d6a-140">通讯组列表通常有两种类型:</span><span class="sxs-lookup"><span data-stu-id="68d6a-140">There are typically two types of distribution lists:</span></span>
  
- <span data-ttu-id="68d6a-141">由基础邮件系统展开的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="68d6a-141">Distribution lists that are expanded by the underlying messaging system.</span></span> <span data-ttu-id="68d6a-142">此类型的列表具有一个地址, **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), 其处理方式与单个收件人相同。</span><span class="sxs-lookup"><span data-stu-id="68d6a-142">This type of list has an address, **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), and is treated the same as if it were an individual recipient.</span></span> 
    
- <span data-ttu-id="68d6a-143">存在于本地容器中并由客户端应用程序扩展的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="68d6a-143">Distribution lists that exist in a local container and are expanded by the client application.</span></span>
    
<span data-ttu-id="68d6a-144">可选的通讯组列表属性包括以下各项:</span><span class="sxs-lookup"><span data-stu-id="68d6a-144">Optional distribution list properties include the following:</span></span>
  
- <span data-ttu-id="68d6a-145">**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="68d6a-145">**PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="68d6a-146">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="68d6a-146">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span> 
    
- <span data-ttu-id="68d6a-147">**PR_DETAILS_TABLE**([PidTagDetailsTable](pidtagdetailstable-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="68d6a-147">**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md))</span></span> 
    
<span data-ttu-id="68d6a-148">请注意, **PR_ADDRTYPE**是必需的, 但**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 不是必需的。</span><span class="sxs-lookup"><span data-stu-id="68d6a-148">Notice that **PR_ADDRTYPE** is required, but **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) is not.</span></span> <span data-ttu-id="68d6a-149">这是因为没有电子邮件地址的通讯组列表仍可以接收邮件, 但必须展开其成员列表。</span><span class="sxs-lookup"><span data-stu-id="68d6a-149">That is because a distribution list without an email address can still receive messages, but its member list must be expanded.</span></span> <span data-ttu-id="68d6a-150">如果将**PR_ADDRTYPE**属性设置为 MAPIPDL, MAPI 将执行扩展。</span><span class="sxs-lookup"><span data-stu-id="68d6a-150">If the **PR_ADDRTYPE** property is set to MAPIPDL, MAPI performs the expansion.</span></span> <span data-ttu-id="68d6a-151">如果**PR_ADDRTYPE**是 MAPIPDL 之外的值, 则传输提供程序将执行扩展。</span><span class="sxs-lookup"><span data-stu-id="68d6a-151">If **PR_ADDRTYPE** is a value other than MAPIPDL, the transport provider performs the expansion.</span></span> 
  
<span data-ttu-id="68d6a-152">有关如何使用**IDistList**方法的其他信息, 请参阅**IABContainer**的并行方法的引用条目。</span><span class="sxs-lookup"><span data-stu-id="68d6a-152">For additional information about how to use the **IDistList** methods, see the reference entries for the parallel methods of **IABContainer**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="68d6a-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68d6a-153">See also</span></span>



[<span data-ttu-id="68d6a-154">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="68d6a-154">MAPI Interfaces</span></span>](mapi-interfaces.md)

