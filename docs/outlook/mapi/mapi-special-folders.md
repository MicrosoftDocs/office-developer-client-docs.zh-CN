---
title: MAPI 特殊文件夹
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f2aa2376-b293-4d05-9104-218cc1fe1758
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fa221510a5f6a8c8be24b4869960d1770cef5882
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357356"
---
# <a name="mapi-special-folders"></a><span data-ttu-id="1f7fd-103">MAPI 特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-103">MAPI Special Folders</span></span>

  
  
<span data-ttu-id="1f7fd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f7fd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f7fd-105">MAPI 定义了一些特殊的文件夹, 因为它们为特定类型的邮件提供了预定义角色作为默认文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-105">MAPI defines a few folders that are special because they serve predefined roles as default folders for certain types of messages.</span></span> <span data-ttu-id="1f7fd-106">这些特殊文件夹通常不能删除, 并且它们具有特殊的条目标识符属性。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-106">These special folders typically cannot be deleted, and they have special entry identifier properties.</span></span>
  
<span data-ttu-id="1f7fd-107">有八个特殊文件夹, 一些是人际邮件 (IPM) 子树的一部分。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-107">There are eight special folders, some that are part of the interpersonal message (IPM) subtree.</span></span> <span data-ttu-id="1f7fd-108">MAPI 会在客户端访问其邮件存储区之前创建这些文件夹, 如果需要, 客户端可能能够删除这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-108">MAPI creates these folders before a client receives access to its message store, after which the client might be able to delete the folders, if necessary.</span></span> <span data-ttu-id="1f7fd-109">某些邮件存储提供程序允许删除, 而其他则不是。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-109">Some message store providers allow deletion, while others do not.</span></span> <span data-ttu-id="1f7fd-110">下表介绍了这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-110">The following table describes these folders.</span></span>
  
<span data-ttu-id="1f7fd-111">**MAPI 文件夹**</span><span class="sxs-lookup"><span data-stu-id="1f7fd-111">**MAPI Folders**</span></span>

|<span data-ttu-id="1f7fd-112">**Folder**</span><span class="sxs-lookup"><span data-stu-id="1f7fd-112">**Folder**</span></span>|<span data-ttu-id="1f7fd-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="1f7fd-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f7fd-114">发件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-114">Outbox folder</span></span>  <br/> |<span data-ttu-id="1f7fd-115">包含传出的 IPM 邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-115">Contains outgoing IPM messages.</span></span>  <br/> |
|<span data-ttu-id="1f7fd-116">“已删除邮件”文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-116">Deleted Items folder</span></span>  <br/> |<span data-ttu-id="1f7fd-117">包含标记为要删除的 IPM 邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-117">Contains IPM messages that are marked for deletion.</span></span>  <br/> |
|<span data-ttu-id="1f7fd-118">"已发送邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-118">Sent Items folder</span></span>  <br/> |<span data-ttu-id="1f7fd-119">包含已发送的 IPM 邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-119">Contains IPM messages that have been sent.</span></span>  <br/> |
|<span data-ttu-id="1f7fd-120">IPM 根文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-120">IPM root folder</span></span>  <br/> |<span data-ttu-id="1f7fd-121">包含用于管理 IPM 邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-121">Contains folders for managing IPM messages.</span></span>  <br/> |
|<span data-ttu-id="1f7fd-122">接收文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-122">Receive folder</span></span>  <br/> |<span data-ttu-id="1f7fd-123">包含特定邮件类别的传入邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-123">Contains incoming messages for a particular message class.</span></span>  <br/> |
|<span data-ttu-id="1f7fd-124">搜索结果根文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-124">Search-results root folder</span></span>  <br/> |<span data-ttu-id="1f7fd-125">包含用于管理搜索结果的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-125">Contains folders for managing search results.</span></span>  <br/> |
|<span data-ttu-id="1f7fd-126">常见的视图根文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-126">Common-views root folder</span></span>  <br/> |<span data-ttu-id="1f7fd-127">包含用于管理邮件存储的视图的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-127">Contains folders for managing views for the message store.</span></span>  <br/> |
|<span data-ttu-id="1f7fd-128">个人-视图根文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-128">Personal-views root folder</span></span>  <br/> |<span data-ttu-id="1f7fd-129">包含用于管理特定用户的视图的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-129">Contains folders for managing views for a particular user.</span></span>  <br/> |
   
<span data-ttu-id="1f7fd-130">前四个文件夹与 IPM 子树相关, 在初始化邮件存储时 MAPI 创建的文件夹树。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-130">The first four folders relate to the IPM subtree, a tree of folders that MAPI creates when a message store is initialized.</span></span> <span data-ttu-id="1f7fd-131">交互邮件客户端的默认邮件存储总是在其文件夹层次结构中包含 IPM 文件夹子树和其他特殊文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-131">Default message stores for interactive messaging clients always include the IPM folder subtree and the other special folders in their folder hierarchy.</span></span> <span data-ttu-id="1f7fd-132">仅支持搜索结果根文件夹、IPM 子树根文件夹、"已删除邮件" 文件夹和 "接收" 文件夹时, 才需要非默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-132">Non-default message stores are required only to support the search-results root folder, the IPM subtree root folder, the Deleted Items folder, and the receive folder.</span></span> <span data-ttu-id="1f7fd-133">若要确保 IPM 子树文件夹存在且有效, 客户端可以调用[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-133">To ensure that the IPM subtree folders exist and are valid, clients can call the [HrValidateIPMSubtree](hrvalidateipmsubtree.md) function.</span></span> <span data-ttu-id="1f7fd-134">**HrValidateIPMSubtree**检查文件夹并在出现问题时重新创建它们。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-134">**HrValidateIPMSubtree** checks the folders and recreates them if there is a problem.</span></span> 
  
<span data-ttu-id="1f7fd-135">搜索结果、常见视图和个人视图的根文件夹不是 IPM 子树的一部分;这些文件夹是在邮件存储区的根文件夹中创建的。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-135">The root folders for search results, common views, and personal views are not part of the IPM subtree; these folders are created in the root folder for the message store.</span></span> <span data-ttu-id="1f7fd-136">搜索结果根文件夹包含的文件夹支持具有符合一组搜索条件的邮件的内容表格。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-136">The search-results root folder contains folders that support contents tables with messages that satisfy a set of search criteria.</span></span> <span data-ttu-id="1f7fd-137">尽管允许客户端在任何文件夹中创建搜索结果文件夹, 但大多数客户端都将单个根文件夹指定为在会话期间创建的所有搜索结果文件夹的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-137">Although clients are allowed to create search-results folders in any folder, most clients designate a single root folder to be the parent of all the search-results folders created during the session.</span></span> 
  
<span data-ttu-id="1f7fd-138">常见视图和个人视图根文件夹包含描述视图的消息, 或用于显示邮件和文件夹数据的首选方法。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-138">The common-views and personal-views root folders contain messages that describe views, or preferred ways of presenting message and folder data.</span></span> <span data-ttu-id="1f7fd-139">常见视图根文件夹包含客户端可用于邮件存储区中的任何文件夹的视图。"个人视图" 文件夹包含已由特定用户为特定文件夹或文件夹定义的视图。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-139">The common-views root folder contains views that clients can use with any folder in the message store; the personal-views folder contains views that have been defined by a particular user for a particular folder or folders.</span></span>
  
<span data-ttu-id="1f7fd-140">使用 ipm 邮件的客户端应在 IPM 子树根文件夹下创建所有文件夹和邮件, 而不是邮件存储区的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-140">Clients that work with IPM messages should create all folders and messages under the IPM subtree root folder, rather than the root folder of the message store.</span></span> <span data-ttu-id="1f7fd-141">这将为非 ipm 客户端—处理在计算机之间或在人类和计算机之间交换的邮件的客户端, 这是一种从 IPM 客户端隐藏邮件的简单方法。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-141">This gives non-IPM clients — the clients that deal with messages exchanged between computers or between humans and computers — an easy way to hide their messages from IPM clients.</span></span> 
  
<span data-ttu-id="1f7fd-142">MAPI 为这些特殊文件夹分配特殊的条目标识符属性。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-142">MAPI assigns special entry identifier properties for these special folders.</span></span> <span data-ttu-id="1f7fd-143">有关特殊文件夹项标识符的列表, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-143">For a list of the special folder entry identifiers, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
  
### <a name="outlook-special-folders"></a><span data-ttu-id="1f7fd-144">Outlook 特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-144">Outlook Special Folders</span></span>

<span data-ttu-id="1f7fd-145">Outlook 特殊文件夹由其在 "收件箱" 文件夹和邮件存储区的根文件夹中存储的条目 id 标识。</span><span class="sxs-lookup"><span data-stu-id="1f7fd-145">Outlook special folders are identified by their entry IDs that are stored in the Inbox folder and the root folder for the message store.</span></span>
  
|<span data-ttu-id="1f7fd-146">**Folder**</span><span class="sxs-lookup"><span data-stu-id="1f7fd-146">**Folder**</span></span>|<span data-ttu-id="1f7fd-147">**要设置的属性**</span><span class="sxs-lookup"><span data-stu-id="1f7fd-147">**The property to set**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f7fd-148">日历</span><span class="sxs-lookup"><span data-stu-id="1f7fd-148">Calendar</span></span>  <br/> |<span data-ttu-id="1f7fd-149">**PR_IPM_APPOINTMENT_ENTRYID**([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1f7fd-149">**PR_IPM_APPOINTMENT_ENTRYID** ([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="1f7fd-150">联系人</span><span class="sxs-lookup"><span data-stu-id="1f7fd-150">Contacts</span></span>  <br/> |<span data-ttu-id="1f7fd-151">**PR_IPM_CONTACT_ENTRYID**([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1f7fd-151">**PR_IPM_CONTACT_ENTRYID** ([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="1f7fd-152">分类账</span><span class="sxs-lookup"><span data-stu-id="1f7fd-152">Journal</span></span>  <br/> |<span data-ttu-id="1f7fd-153">**PR_IPM_JOURNAL_ENTRYID**([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1f7fd-153">**PR_IPM_JOURNAL_ENTRYID** ([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="1f7fd-154">备注</span><span class="sxs-lookup"><span data-stu-id="1f7fd-154">Notes</span></span>  <br/> |<span data-ttu-id="1f7fd-155">**PR_IPM_NOTE_ENTRYID**([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1f7fd-155">**PR_IPM_NOTE_ENTRYID** ([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="1f7fd-156">任务</span><span class="sxs-lookup"><span data-stu-id="1f7fd-156">Tasks</span></span>  <br/> |<span data-ttu-id="1f7fd-157">**PR_IPM_TASK_ENTRYID**([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1f7fd-157">**PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="1f7fd-158">草稿</span><span class="sxs-lookup"><span data-stu-id="1f7fd-158">Drafts</span></span>  <br/> |<span data-ttu-id="1f7fd-159">**PR_IPM_DRAFTS_ENTRYID**([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1f7fd-159">**PR_IPM_DRAFTS_ENTRYID** ([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1f7fd-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f7fd-160">See also</span></span>



[<span data-ttu-id="1f7fd-161">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="1f7fd-161">MAPI Folders</span></span>](mapi-folders.md)

