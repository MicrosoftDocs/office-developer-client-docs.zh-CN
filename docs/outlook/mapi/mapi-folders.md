---
title: MAPI 文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8fac3c92-d2f5-479e-a368-ca82bddd8e30
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c00dce9ec489ca2b886f3e51551ba57e9eeea33
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421842"
---
# <a name="mapi-folders"></a><span data-ttu-id="6986a-103">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="6986a-103">MAPI Folders</span></span>

  
  
<span data-ttu-id="6986a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6986a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6986a-105">文件夹是用作邮件的基本组织单位的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="6986a-105">Folders are MAPI objects that serve as the basic unit of organization for messages.</span></span> <span data-ttu-id="6986a-106">层次结构排列, 文件夹可以包含邮件和其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-106">Arranged hierarchically, folders can contain messages and other folders.</span></span> <span data-ttu-id="6986a-107">文件夹使查找和处理邮件变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="6986a-107">Folders make it easier to locate and work with messages.</span></span>
  
<span data-ttu-id="6986a-108">文件夹实现[IMAPIFolder](imapifolderimapicontainer.md)接口, 该接口间接继承自通过[IMAPIContainer](imapicontainerimapiprop.md)和[IMAPIProp](imapipropiunknown.md)接口的**IUnknown**接口。</span><span class="sxs-lookup"><span data-stu-id="6986a-108">Folders implement the [IMAPIFolder](imapifolderimapicontainer.md) interface, which indirectly inherits from the **IUnknown** interface through the [IMAPIContainer](imapicontainerimapiprop.md) and [IMAPIProp](imapipropiunknown.md) interfaces.</span></span> <span data-ttu-id="6986a-109">客户端使用**IMAPIFolder**创建、复制和删除邮件和文件夹、检索和设置邮件状态以及设置或清除邮件的阅读标志。</span><span class="sxs-lookup"><span data-stu-id="6986a-109">Clients use **IMAPIFolder** to create, copy, and delete messages and folders, to retrieve and set message status, and to set or clear the read flag for a message.</span></span> <span data-ttu-id="6986a-110">尽管支持邮件存储提供程序以支持**IMAPIFolder**中的所有方法, 但某些方法会导致邮件存储提供程序可能想要避免的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="6986a-110">Although message store providers are required to support all the methods in **IMAPIFolder**, some methods introduce a level of complexity that message store providers might want to avoid.</span></span> <span data-ttu-id="6986a-111">MAPI 通过在[IMAPISupport](imapisupportiunknown.md)接口中实施一些更复杂的文件夹功能来保存邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="6986a-111">MAPI saves message store providers some work by implementing some of the more complex folder functionality in the [IMAPISupport](imapisupportiunknown.md) interface.</span></span> <span data-ttu-id="6986a-112">例如, 邮件存储提供程序可以调用支持对象中的 copy 方法并获得相同的结果, 而不是实现自己的 copy 方法。</span><span class="sxs-lookup"><span data-stu-id="6986a-112">Rather than implementing their own copy methods, for example, message store providers can call the copy methods in the support object and get the same results.</span></span> 
  
<span data-ttu-id="6986a-113">有三种类型的文件夹:</span><span class="sxs-lookup"><span data-stu-id="6986a-113">There are three kinds of folders:</span></span>
  
- <span data-ttu-id="6986a-114">根文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-114">Root folders.</span></span>
    
- <span data-ttu-id="6986a-115">通用文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-115">Generic folders.</span></span>
    
- <span data-ttu-id="6986a-116">搜索文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-116">Search folders.</span></span>
    
<span data-ttu-id="6986a-117">每个邮件存储至少具有一个根文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-117">Every message store has at least a root folder.</span></span> <span data-ttu-id="6986a-118">根文件夹显示在层次结构的顶部, 包含邮件和其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-118">The root folder appears at the top of the hierarchy and contains messages and other folders.</span></span> <span data-ttu-id="6986a-119">无法移动、复制、重命名或删除根文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-119">Root folders cannot be moved, copied, renamed, or deleted.</span></span> <span data-ttu-id="6986a-120">每个邮件存储区只有一个根文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-120">There is only one root folder for each message store.</span></span>
  
<span data-ttu-id="6986a-121">大多数其他文件夹是常规文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-121">Most other folders are generic folders.</span></span> <span data-ttu-id="6986a-122">与根文件夹一样, 通用文件夹包含邮件和其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-122">Like root folders, generic folders contain messages and other folders.</span></span> <span data-ttu-id="6986a-123">与根文件夹不同, 可以对它们进行移动、复制、重命名和删除。</span><span class="sxs-lookup"><span data-stu-id="6986a-123">Unlike root folders, they can be moved, copied, renamed, and deleted.</span></span> <span data-ttu-id="6986a-124">可以在根文件夹或其他通用文件夹中创建通用文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-124">Generic folders can be created in the root folder or other generic folders.</span></span> <span data-ttu-id="6986a-125">当客户端在另一个文件夹中创建通用文件夹时, 新的文件夹称为子文件夹或子文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-125">When a client creates a generic folder in another folder, the new folder is called a subfolder, or child folder.</span></span> <span data-ttu-id="6986a-126">将在其中放置新文件夹的文件夹称为新文件夹的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-126">The folder in which the new folder is placed is referred to as the parent folder of the new folder.</span></span> <span data-ttu-id="6986a-127">具有相同父文件夹的通用文件夹称为 "同辈文件夹"。</span><span class="sxs-lookup"><span data-stu-id="6986a-127">Generic folders that have the same parent folder are called sibling folders.</span></span> <span data-ttu-id="6986a-128">同辈和非同辈文件夹都可能具有唯一的名称, 具体取决于邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="6986a-128">Both sibling and non-sibling folders may or may not have unique names, depending on the message store provider.</span></span> <span data-ttu-id="6986a-129">如果客户端尝试在同一父文件夹中创建两个名称相同的文件夹, 则需要同级文件夹具有唯一名称的邮件存储提供程序将返回错误值 MAPI_E_COLLISION。</span><span class="sxs-lookup"><span data-stu-id="6986a-129">Message store providers that require sibling folders to have unique names return the error value MAPI_E_COLLISION when a client attempts to create two folders with the same name in the same parent.</span></span> 
  
<span data-ttu-id="6986a-130">"搜索文件夹" 包含与一组预定义条件相匹配的邮件的链接。</span><span class="sxs-lookup"><span data-stu-id="6986a-130">A search folder contains links to messages that match a set of predefined criteria.</span></span> <span data-ttu-id="6986a-131">由于搜索文件夹包含链接而不是实际邮件, 因此它们实际上是只读的。</span><span class="sxs-lookup"><span data-stu-id="6986a-131">Because search folders contain links rather than actual messages, they are in effect read-only.</span></span> <span data-ttu-id="6986a-132">用户不能包含其他文件夹, 也不能将邮件或文件夹移动或复制到其中。</span><span class="sxs-lookup"><span data-stu-id="6986a-132">They cannot contain other folders or have messages or folders moved or copied into them.</span></span> <span data-ttu-id="6986a-133">他们不能在其中创建新邮件;它们本身不能被移动、复制或重命名。</span><span class="sxs-lookup"><span data-stu-id="6986a-133">They cannot have new messages created in them; and they themselves cannot be moved, copied, or renamed.</span></span> <span data-ttu-id="6986a-134">从搜索文件夹中删除邮件时, 该邮件实际上从包含该邮件的文件夹中删除。</span><span class="sxs-lookup"><span data-stu-id="6986a-134">When a message is deleted from a search folder, it is actually deleted from the folder that contains the message.</span></span>
  
<span data-ttu-id="6986a-135">文件夹类型存储在**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="6986a-135">Folder type is stored in the **PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md)) property.</span></span> <span data-ttu-id="6986a-136">每个文件夹均将此属性设置为 FOLDER_GENERIC、FOLDER_ROOT 或 FOLDER_SEARCH, 具体取决于其类型。</span><span class="sxs-lookup"><span data-stu-id="6986a-136">Every folder has this property set to either FOLDER_GENERIC, FOLDER_ROOT, or FOLDER_SEARCH, depending on its type.</span></span>
  
<span data-ttu-id="6986a-137">每个文件夹都有一个条目标识符和一个记录键。</span><span class="sxs-lookup"><span data-stu-id="6986a-137">Every folder has one entry identifier and one record key.</span></span> <span data-ttu-id="6986a-138">条目标识符 ( **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))) 由客户端和服务提供商用于打开文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-138">The entry identifier, **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), is used by clients and service providers to open the folder.</span></span> <span data-ttu-id="6986a-139">record 关键字**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 是一个二进制值, 用于将文件夹与其他文件夹进行比较。</span><span class="sxs-lookup"><span data-stu-id="6986a-139">The record key, **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)), is a binary value that is used to compare the folder with other folders.</span></span> 
  
<span data-ttu-id="6986a-140">文件夹具有用于标识相关文件夹和邮件存储区的其他属性。</span><span class="sxs-lookup"><span data-stu-id="6986a-140">A folder has other properties to identify related folders and the message store.</span></span> <span data-ttu-id="6986a-141">以下属性是必需的:</span><span class="sxs-lookup"><span data-stu-id="6986a-141">The following properties are required:</span></span>
  
- <span data-ttu-id="6986a-142">**PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6986a-142">**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="6986a-143">**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6986a-143">**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="6986a-144">**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6986a-144">**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span></span>
    
<span data-ttu-id="6986a-145">某些文件夹支持**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性, 该属性描述了用户可以执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="6986a-145">Some folders support the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property which describes the type of operations a user can perform.</span></span> <span data-ttu-id="6986a-146">例如, **PR_ACCESS**的有效设置之一是 MAPI_ACCESS_DELETE, 这表示可以删除该文件夹。</span><span class="sxs-lookup"><span data-stu-id="6986a-146">For example, one of the valid settings for **PR_ACCESS** is MAPI_ACCESS_DELETE, which indicates that the folder can be removed.</span></span> <span data-ttu-id="6986a-147">另一个设置 MAPI_ACCESS_MODIFY, 指示文件夹应可修改。</span><span class="sxs-lookup"><span data-stu-id="6986a-147">Another setting, MAPI_ACCESS_MODIFY, indicates that the folder should be modifiable.</span></span> 
  
<span data-ttu-id="6986a-148">有关所需的文件夹属性的完整列表, 请参阅[IMAPIFolder](imapifolderimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="6986a-148">For a complete list of required folder properties, see the [IMAPIFolder](imapifolderimapicontainer.md) interface.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6986a-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6986a-149">See also</span></span>



[<span data-ttu-id="6986a-150">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="6986a-150">MAPI Application Development</span></span>](mapi-application-development.md)

