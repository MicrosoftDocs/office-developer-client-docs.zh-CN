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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410922"
---
# <a name="mapi-special-folders"></a><span data-ttu-id="19e75-103">MAPI 特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-103">MAPI Special Folders</span></span>

  
  
<span data-ttu-id="19e75-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="19e75-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="19e75-105">MAPI 定义了一些特殊文件夹，因为它们将预定义角色用作某些类型的邮件的默认文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-105">MAPI defines a few folders that are special because they serve predefined roles as default folders for certain types of messages.</span></span> <span data-ttu-id="19e75-106">通常无法删除这些特殊文件夹，它们具有特殊的条目标识符属性。</span><span class="sxs-lookup"><span data-stu-id="19e75-106">These special folders typically cannot be deleted, and they have special entry identifier properties.</span></span>
  
<span data-ttu-id="19e75-107">有八个特殊文件夹，其中一些是 IPM 子树中 (邮件) 部分。</span><span class="sxs-lookup"><span data-stu-id="19e75-107">There are eight special folders, some that are part of the interpersonal message (IPM) subtree.</span></span> <span data-ttu-id="19e75-108">MAPI 在客户端接收对邮件存储的访问权限之前创建这些文件夹，之后，客户端可能会在必要时删除这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-108">MAPI creates these folders before a client receives access to its message store, after which the client might be able to delete the folders, if necessary.</span></span> <span data-ttu-id="19e75-109">某些邮件存储提供程序允许删除，而其他邮件存储提供程序不允许删除。</span><span class="sxs-lookup"><span data-stu-id="19e75-109">Some message store providers allow deletion, while others do not.</span></span> <span data-ttu-id="19e75-110">下表介绍了这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-110">The following table describes these folders.</span></span>
  
<span data-ttu-id="19e75-111">**MAPI 文件夹**</span><span class="sxs-lookup"><span data-stu-id="19e75-111">**MAPI Folders**</span></span>

|<span data-ttu-id="19e75-112">**Folder**</span><span class="sxs-lookup"><span data-stu-id="19e75-112">**Folder**</span></span>|<span data-ttu-id="19e75-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="19e75-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="19e75-114">发件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-114">Outbox folder</span></span>  <br/> |<span data-ttu-id="19e75-115">包含传出 IPM 邮件。</span><span class="sxs-lookup"><span data-stu-id="19e75-115">Contains outgoing IPM messages.</span></span>  <br/> |
|<span data-ttu-id="19e75-116">“已删除邮件”文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-116">Deleted Items folder</span></span>  <br/> |<span data-ttu-id="19e75-117">包含标记为删除的 IPM 邮件。</span><span class="sxs-lookup"><span data-stu-id="19e75-117">Contains IPM messages that are marked for deletion.</span></span>  <br/> |
|<span data-ttu-id="19e75-118">"已发送项目"文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-118">Sent Items folder</span></span>  <br/> |<span data-ttu-id="19e75-119">包含已发送的 IPM 邮件。</span><span class="sxs-lookup"><span data-stu-id="19e75-119">Contains IPM messages that have been sent.</span></span>  <br/> |
|<span data-ttu-id="19e75-120">IPM 根文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-120">IPM root folder</span></span>  <br/> |<span data-ttu-id="19e75-121">包含用于管理 IPM 邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-121">Contains folders for managing IPM messages.</span></span>  <br/> |
|<span data-ttu-id="19e75-122">接收文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-122">Receive folder</span></span>  <br/> |<span data-ttu-id="19e75-123">包含特定邮件类的传入邮件。</span><span class="sxs-lookup"><span data-stu-id="19e75-123">Contains incoming messages for a particular message class.</span></span>  <br/> |
|<span data-ttu-id="19e75-124">搜索结果根文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-124">Search-results root folder</span></span>  <br/> |<span data-ttu-id="19e75-125">包含用于管理搜索结果的文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-125">Contains folders for managing search results.</span></span>  <br/> |
|<span data-ttu-id="19e75-126">通用视图根文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-126">Common-views root folder</span></span>  <br/> |<span data-ttu-id="19e75-127">包含用于管理邮件存储视图的文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-127">Contains folders for managing views for the message store.</span></span>  <br/> |
|<span data-ttu-id="19e75-128">个人视图根文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-128">Personal-views root folder</span></span>  <br/> |<span data-ttu-id="19e75-129">包含用于管理特定用户的视图的文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-129">Contains folders for managing views for a particular user.</span></span>  <br/> |
   
<span data-ttu-id="19e75-130">前四个文件夹与 IPM 子树相关，该树是 MAPI 在初始化邮件存储时创建的文件夹树。</span><span class="sxs-lookup"><span data-stu-id="19e75-130">The first four folders relate to the IPM subtree, a tree of folders that MAPI creates when a message store is initialized.</span></span> <span data-ttu-id="19e75-131">交互式邮件客户端的默认邮件存储始终包括 IPM 文件夹子树及其文件夹层次结构中的其他特殊文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-131">Default message stores for interactive messaging clients always include the IPM folder subtree and the other special folders in their folder hierarchy.</span></span> <span data-ttu-id="19e75-132">非默认邮件存储仅支持搜索结果根文件夹、IPM 子树根文件夹、"已删除邮件"文件夹和接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-132">Non-default message stores are required only to support the search-results root folder, the IPM subtree root folder, the Deleted Items folder, and the receive folder.</span></span> <span data-ttu-id="19e75-133">为了确保 IPM 子树文件夹存在且有效，客户端可以调用 [HrValidateIPMSubtree](hrvalidateipmsubtree.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="19e75-133">To ensure that the IPM subtree folders exist and are valid, clients can call the [HrValidateIPMSubtree](hrvalidateipmsubtree.md) function.</span></span> <span data-ttu-id="19e75-134">**HrValidateIPMSubtree** 检查文件夹，如果出现问题，请重新创建它们。</span><span class="sxs-lookup"><span data-stu-id="19e75-134">**HrValidateIPMSubtree** checks the folders and recreates them if there is a problem.</span></span> 
  
<span data-ttu-id="19e75-135">搜索结果、常见视图和个人视图的根文件夹不是 IPM 子树的一部分;这些文件夹是在邮件存储的根文件夹中创建的。</span><span class="sxs-lookup"><span data-stu-id="19e75-135">The root folders for search results, common views, and personal views are not part of the IPM subtree; these folders are created in the root folder for the message store.</span></span> <span data-ttu-id="19e75-136">搜索结果根文件夹包含支持包含满足一组搜索条件的邮件的内容表的文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-136">The search-results root folder contains folders that support contents tables with messages that satisfy a set of search criteria.</span></span> <span data-ttu-id="19e75-137">尽管允许客户端在任何文件夹中创建搜索结果文件夹，但大多数客户端将单个根文件夹指定为会话期间创建的所有搜索结果文件夹的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="19e75-137">Although clients are allowed to create search-results folders in any folder, most clients designate a single root folder to be the parent of all the search-results folders created during the session.</span></span> 
  
<span data-ttu-id="19e75-138">常见视图和个人视图根文件夹包含描述视图或显示邮件和文件夹数据的首选方法的邮件。</span><span class="sxs-lookup"><span data-stu-id="19e75-138">The common-views and personal-views root folders contain messages that describe views, or preferred ways of presenting message and folder data.</span></span> <span data-ttu-id="19e75-139">通用视图根文件夹包含客户端可用于邮件存储中任何文件夹的视图;personal-views 文件夹包含特定用户为特定文件夹定义的视图。</span><span class="sxs-lookup"><span data-stu-id="19e75-139">The common-views root folder contains views that clients can use with any folder in the message store; the personal-views folder contains views that have been defined by a particular user for a particular folder or folders.</span></span>
  
<span data-ttu-id="19e75-140">使用 IPM 邮件的客户端应在 IPM 子树根文件夹（而不是邮件存储的根文件夹）下创建所有文件夹和邮件。</span><span class="sxs-lookup"><span data-stu-id="19e75-140">Clients that work with IPM messages should create all folders and messages under the IPM subtree root folder, rather than the root folder of the message store.</span></span> <span data-ttu-id="19e75-141">这为非 IPM 客户端（处理计算机之间或人与计算机之间交换的消息的客户端）提供了一种向 IPM 客户端隐藏其消息的简便方法。</span><span class="sxs-lookup"><span data-stu-id="19e75-141">This gives non-IPM clients — the clients that deal with messages exchanged between computers or between humans and computers — an easy way to hide their messages from IPM clients.</span></span> 
  
<span data-ttu-id="19e75-142">MAPI 为这些特殊文件夹分配特殊条目标识符属性。</span><span class="sxs-lookup"><span data-stu-id="19e75-142">MAPI assigns special entry identifier properties for these special folders.</span></span> <span data-ttu-id="19e75-143">有关特殊文件夹条目标识符的列表，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="19e75-143">For a list of the special folder entry identifiers, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
  
### <a name="outlook-special-folders"></a><span data-ttu-id="19e75-144">Outlook特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-144">Outlook Special Folders</span></span>

<span data-ttu-id="19e75-145">Outlook特殊文件夹由存储在"收件箱"文件夹和邮件存储的根文件夹中的条目标识。</span><span class="sxs-lookup"><span data-stu-id="19e75-145">Outlook special folders are identified by their entry IDs that are stored in the Inbox folder and the root folder for the message store.</span></span>
  
|<span data-ttu-id="19e75-146">**Folder**</span><span class="sxs-lookup"><span data-stu-id="19e75-146">**Folder**</span></span>|<span data-ttu-id="19e75-147">**要设置的属性**</span><span class="sxs-lookup"><span data-stu-id="19e75-147">**The property to set**</span></span>|
|:-----|:-----|
|<span data-ttu-id="19e75-148">日历</span><span class="sxs-lookup"><span data-stu-id="19e75-148">Calendar</span></span>  <br/> |<span data-ttu-id="19e75-149">**PR_IPM_APPOINTMENT_ENTRYID (** [PidTagIpmAppointmentEntryId)](pidtagipmappointmententryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="19e75-149">**PR_IPM_APPOINTMENT_ENTRYID** ([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="19e75-150">联系人</span><span class="sxs-lookup"><span data-stu-id="19e75-150">Contacts</span></span>  <br/> |<span data-ttu-id="19e75-151">**PR_IPM_CONTACT_ENTRYID (** [PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="19e75-151">**PR_IPM_CONTACT_ENTRYID** ([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="19e75-152">日志</span><span class="sxs-lookup"><span data-stu-id="19e75-152">Journal</span></span>  <br/> |<span data-ttu-id="19e75-153">**PR_IPM_JOURNAL_ENTRYID (** [PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="19e75-153">**PR_IPM_JOURNAL_ENTRYID** ([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="19e75-154">备注</span><span class="sxs-lookup"><span data-stu-id="19e75-154">Notes</span></span>  <br/> |<span data-ttu-id="19e75-155">**PR_IPM_NOTE_ENTRYID (** [PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="19e75-155">**PR_IPM_NOTE_ENTRYID** ([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="19e75-156">任务</span><span class="sxs-lookup"><span data-stu-id="19e75-156">Tasks</span></span>  <br/> |<span data-ttu-id="19e75-157">**PR_IPM_TASK_ENTRYID (** [PidTagIpmTaskEntryId)](pidtagipmtaskentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="19e75-157">**PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="19e75-158">草稿</span><span class="sxs-lookup"><span data-stu-id="19e75-158">Drafts</span></span>  <br/> |<span data-ttu-id="19e75-159">**PR_IPM_DRAFTS_ENTRYID (** [PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="19e75-159">**PR_IPM_DRAFTS_ENTRYID** ([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="19e75-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19e75-160">See also</span></span>



[<span data-ttu-id="19e75-161">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="19e75-161">MAPI Folders</span></span>](mapi-folders.md)

