---
title: MAPI 文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8fac3c92-d2f5-479e-a368-ca82bddd8e30
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 21b738424b27d3d89d8de84c8c9ff2ff86dd945b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564085"
---
# <a name="mapi-folders"></a><span data-ttu-id="01aca-103">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="01aca-103">MAPI Folders</span></span>

  
  
<span data-ttu-id="01aca-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="01aca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="01aca-105">文件夹是充当组织的邮件的基本单位的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="01aca-105">Folders are MAPI objects that serve as the basic unit of organization for messages.</span></span> <span data-ttu-id="01aca-106">按层次结构排列，文件夹可以包含邮件和其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-106">Arranged hierarchically, folders can contain messages and other folders.</span></span> <span data-ttu-id="01aca-107">文件夹更加轻松地查找和处理邮件。</span><span class="sxs-lookup"><span data-stu-id="01aca-107">Folders make it easier to locate and work with messages.</span></span>
  
<span data-ttu-id="01aca-108">文件夹实现[IMAPIFolder](imapifolderimapicontainer.md)接口，间接继承的**IUnknown**接口，通过[IMAPIContainer](imapicontainerimapiprop.md)和[IMAPIProp](imapipropiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="01aca-108">Folders implement the [IMAPIFolder](imapifolderimapicontainer.md) interface, which indirectly inherits from the **IUnknown** interface through the [IMAPIContainer](imapicontainerimapiprop.md) and [IMAPIProp](imapipropiunknown.md) interfaces.</span></span> <span data-ttu-id="01aca-109">客户端使用**IMAPIFolder**若要创建、 复制和删除邮件和文件夹，用于检索和设置邮件状态和设置或清除邮件阅读的标志。</span><span class="sxs-lookup"><span data-stu-id="01aca-109">Clients use **IMAPIFolder** to create, copy, and delete messages and folders, to retrieve and set message status, and to set or clear the read flag for a message.</span></span> <span data-ttu-id="01aca-110">尽管在**IMAPIFolder**支持所有方法所需消息存储提供程序，但某些方法引入消息存储提供程序可能希望避免的复杂级别。</span><span class="sxs-lookup"><span data-stu-id="01aca-110">Although message store providers are required to support all the methods in **IMAPIFolder**, some methods introduce a level of complexity that message store providers might want to avoid.</span></span> <span data-ttu-id="01aca-111">MAPI 将消息存储提供程序一些工作保存由[IMAPISupport](imapisupportiunknown.md)接口中实现的某些更复杂的文件夹功能。</span><span class="sxs-lookup"><span data-stu-id="01aca-111">MAPI saves message store providers some work by implementing some of the more complex folder functionality in the [IMAPISupport](imapisupportiunknown.md) interface.</span></span> <span data-ttu-id="01aca-112">而不是实现自己的复制方法，例如，消息存储提供程序可以呼叫中的支持对象的复制方法并获取相同的结果。</span><span class="sxs-lookup"><span data-stu-id="01aca-112">Rather than implementing their own copy methods, for example, message store providers can call the copy methods in the support object and get the same results.</span></span> 
  
<span data-ttu-id="01aca-113">有三种类型的文件夹：</span><span class="sxs-lookup"><span data-stu-id="01aca-113">There are three kinds of folders:</span></span>
  
- <span data-ttu-id="01aca-114">根文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-114">Root folders.</span></span>
    
- <span data-ttu-id="01aca-115">泛型文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-115">Generic folders.</span></span>
    
- <span data-ttu-id="01aca-116">搜索文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-116">Search folders.</span></span>
    
<span data-ttu-id="01aca-117">每个消息存储库具有至少一个根文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-117">Every message store has at least a root folder.</span></span> <span data-ttu-id="01aca-118">根文件夹层次结构的顶端显示和包含邮件和其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-118">The root folder appears at the top of the hierarchy and contains messages and other folders.</span></span> <span data-ttu-id="01aca-119">不能移动、 复制、 重命名或删除根文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-119">Root folders cannot be moved, copied, renamed, or deleted.</span></span> <span data-ttu-id="01aca-120">没有为每个消息存储库的只有一个根文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-120">There is only one root folder for each message store.</span></span>
  
<span data-ttu-id="01aca-121">大多数其他文件夹是通用的文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-121">Most other folders are generic folders.</span></span> <span data-ttu-id="01aca-122">根文件夹，如泛型文件夹包含邮件和其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-122">Like root folders, generic folders contain messages and other folders.</span></span> <span data-ttu-id="01aca-123">与不同的根文件夹，他们可以移动、 复制、 重命名，并删除。</span><span class="sxs-lookup"><span data-stu-id="01aca-123">Unlike root folders, they can be moved, copied, renamed, and deleted.</span></span> <span data-ttu-id="01aca-124">可以在根文件夹或其他泛型文件夹中创建通用的文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-124">Generic folders can be created in the root folder or other generic folders.</span></span> <span data-ttu-id="01aca-125">当客户端在另一个文件夹中创建通用文件夹时，新文件夹称为子文件夹或子文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-125">When a client creates a generic folder in another folder, the new folder is called a subfolder, or child folder.</span></span> <span data-ttu-id="01aca-126">在其中放置新文件夹的文件夹称为新文件夹的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-126">The folder in which the new folder is placed is referred to as the parent folder of the new folder.</span></span> <span data-ttu-id="01aca-127">具有相同的父文件夹的通用文件夹称为同级文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-127">Generic folders that have the same parent folder are called sibling folders.</span></span> <span data-ttu-id="01aca-128">同级和非同级文件夹可能或可能不具有唯一的名称，具体取决于消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="01aca-128">Both sibling and non-sibling folders may or may not have unique names, depending on the message store provider.</span></span> <span data-ttu-id="01aca-129">邮件需要具有唯一的名称时客户端尝试使用同一个父中具有相同名称创建两个文件夹返回错误值 MAPI_E_COLLISION 同级文件夹的存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="01aca-129">Message store providers that require sibling folders to have unique names return the error value MAPI_E_COLLISION when a client attempts to create two folders with the same name in the same parent.</span></span> 
  
<span data-ttu-id="01aca-130">搜索文件夹包含指向与一组预定义的条件匹配的邮件。</span><span class="sxs-lookup"><span data-stu-id="01aca-130">A search folder contains links to messages that match a set of predefined criteria.</span></span> <span data-ttu-id="01aca-131">搜索文件夹包含的链接，而不是实际的邮件，因为它们是实际上是只读的。</span><span class="sxs-lookup"><span data-stu-id="01aca-131">Because search folders contain links rather than actual messages, they are in effect read-only.</span></span> <span data-ttu-id="01aca-132">不能包含其他文件夹或具有邮件或文件夹移动或复制到它们。</span><span class="sxs-lookup"><span data-stu-id="01aca-132">They cannot contain other folders or have messages or folders moved or copied into them.</span></span> <span data-ttu-id="01aca-133">不能具有中; 创建的新消息和它们本身不能移动、 复制或重命名。</span><span class="sxs-lookup"><span data-stu-id="01aca-133">They cannot have new messages created in them; and they themselves cannot be moved, copied, or renamed.</span></span> <span data-ttu-id="01aca-134">搜索文件夹中删除一条消息后，它是实际删除从包含邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-134">When a message is deleted from a search folder, it is actually deleted from the folder that contains the message.</span></span>
  
<span data-ttu-id="01aca-135">文件夹类型存储在**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="01aca-135">Folder type is stored in the **PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md)) property.</span></span> <span data-ttu-id="01aca-136">每个文件夹包含此属性设置为 FOLDER_GENERIC、 FOLDER_ROOT 或 FOLDER_SEARCH，具体取决于其类型。</span><span class="sxs-lookup"><span data-stu-id="01aca-136">Every folder has this property set to either FOLDER_GENERIC, FOLDER_ROOT, or FOLDER_SEARCH, depending on its type.</span></span>
  
<span data-ttu-id="01aca-137">每个文件夹都有一个条目标识符和一个记录密钥。</span><span class="sxs-lookup"><span data-stu-id="01aca-137">Every folder has one entry identifier and one record key.</span></span> <span data-ttu-id="01aca-138">客户端和服务提供商使用的项标识符， **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))，以打开文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-138">The entry identifier, **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), is used by clients and service providers to open the folder.</span></span> <span data-ttu-id="01aca-139">记录项， **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 是用于比较与其他文件夹的文件夹的二进制值。</span><span class="sxs-lookup"><span data-stu-id="01aca-139">The record key, **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)), is a binary value that is used to compare the folder with other folders.</span></span> 
  
<span data-ttu-id="01aca-140">文件夹具有其他属性标识相关的文件夹和消息存储库。</span><span class="sxs-lookup"><span data-stu-id="01aca-140">A folder has other properties to identify related folders and the message store.</span></span> <span data-ttu-id="01aca-141">需要以下属性：</span><span class="sxs-lookup"><span data-stu-id="01aca-141">The following properties are required:</span></span>
  
- <span data-ttu-id="01aca-142">**PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="01aca-142">**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="01aca-143">**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="01aca-143">**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="01aca-144">**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="01aca-144">**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span></span>
    
<span data-ttu-id="01aca-145">有些文件夹支持**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性，其中介绍了用户可以执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="01aca-145">Some folders support the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property which describes the type of operations a user can perform.</span></span> <span data-ttu-id="01aca-146">例如， **PR_ACCESS**的有效设置之一是 MAPI_ACCESS_DELETE，指示可以删除该文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-146">For example, one of the valid settings for **PR_ACCESS** is MAPI_ACCESS_DELETE, which indicates that the folder can be removed.</span></span> <span data-ttu-id="01aca-147">其他设置，MAPI_ACCESS_MODIFY，指示应可修改的文件夹。</span><span class="sxs-lookup"><span data-stu-id="01aca-147">Another setting, MAPI_ACCESS_MODIFY, indicates that the folder should be modifiable.</span></span> 
  
<span data-ttu-id="01aca-148">需要的文件夹属性的完整列表，请参阅[IMAPIFolder](imapifolderimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="01aca-148">For a complete list of required folder properties, see the [IMAPIFolder](imapifolderimapicontainer.md) interface.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="01aca-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01aca-149">See also</span></span>



[<span data-ttu-id="01aca-150">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="01aca-150">MAPI Application Development</span></span>](mapi-application-development.md)

