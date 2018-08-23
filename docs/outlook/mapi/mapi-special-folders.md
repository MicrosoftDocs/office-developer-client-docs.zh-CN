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
ms.openlocfilehash: 396a6c01d0b9cd867706a7dd4997bd6ddd7fd147
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578288"
---
# <a name="mapi-special-folders"></a><span data-ttu-id="60c94-103">MAPI 特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-103">MAPI Special Folders</span></span>

  
  
<span data-ttu-id="60c94-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="60c94-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="60c94-105">MAPI 定义几个是特殊的因为它们提供作为默认文件夹的预定义的角色的某些类型的邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-105">MAPI defines a few folders that are special because they serve predefined roles as default folders for certain types of messages.</span></span> <span data-ttu-id="60c94-106">通常不能删除这些特殊文件夹，并且其特殊的项标识符的属性。</span><span class="sxs-lookup"><span data-stu-id="60c94-106">These special folders typically cannot be deleted, and they have special entry identifier properties.</span></span>
  
<span data-ttu-id="60c94-107">有八个特殊文件夹的一部分的人际邮件 (IPM) 子树。</span><span class="sxs-lookup"><span data-stu-id="60c94-107">There are eight special folders, some that are part of the interpersonal message (IPM) subtree.</span></span> <span data-ttu-id="60c94-108">MAPI 客户端获得访问其消息存储库，其后客户端可能导致无法删除文件夹，如有必要之前创建这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-108">MAPI creates these folders before a client receives access to its message store, after which the client might be able to delete the folders, if necessary.</span></span> <span data-ttu-id="60c94-109">某些消息存储提供程序允许删除，而有些则没有。</span><span class="sxs-lookup"><span data-stu-id="60c94-109">Some message store providers allow deletion, while others do not.</span></span> <span data-ttu-id="60c94-110">下表介绍这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-110">The following table describes these folders.</span></span>
  
<span data-ttu-id="60c94-111">**MAPI 文件夹**</span><span class="sxs-lookup"><span data-stu-id="60c94-111">**MAPI Folders**</span></span>

|<span data-ttu-id="60c94-112">**Folder**</span><span class="sxs-lookup"><span data-stu-id="60c94-112">**Folder**</span></span>|<span data-ttu-id="60c94-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="60c94-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60c94-114">发件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-114">Outbox folder</span></span>  <br/> |<span data-ttu-id="60c94-115">包含传出 IPM 消息。</span><span class="sxs-lookup"><span data-stu-id="60c94-115">Contains outgoing IPM messages.</span></span>  <br/> |
|<span data-ttu-id="60c94-116">已删除的项目文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-116">Deleted Items folder</span></span>  <br/> |<span data-ttu-id="60c94-117">包含 IPM 邮件标记为删除。</span><span class="sxs-lookup"><span data-stu-id="60c94-117">Contains IPM messages that are marked for deletion.</span></span>  <br/> |
|<span data-ttu-id="60c94-118">发送的项目文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-118">Sent Items folder</span></span>  <br/> |<span data-ttu-id="60c94-119">包含 IPM 已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="60c94-119">Contains IPM messages that have been sent.</span></span>  <br/> |
|<span data-ttu-id="60c94-120">IPM 根文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-120">IPM root folder</span></span>  <br/> |<span data-ttu-id="60c94-121">包含用于管理 IPM 邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-121">Contains folders for managing IPM messages.</span></span>  <br/> |
|<span data-ttu-id="60c94-122">接收文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-122">Receive folder</span></span>  <br/> |<span data-ttu-id="60c94-123">包含为特定邮件类的传入消息。</span><span class="sxs-lookup"><span data-stu-id="60c94-123">Contains incoming messages for a particular message class.</span></span>  <br/> |
|<span data-ttu-id="60c94-124">搜索结果的根文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-124">Search-results root folder</span></span>  <br/> |<span data-ttu-id="60c94-125">包含用于管理搜索结果的文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-125">Contains folders for managing search results.</span></span>  <br/> |
|<span data-ttu-id="60c94-126">常见视图的根文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-126">Common-views root folder</span></span>  <br/> |<span data-ttu-id="60c94-127">包含用于管理消息存储库视图的文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-127">Contains folders for managing views for the message store.</span></span>  <br/> |
|<span data-ttu-id="60c94-128">个人视图的根文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-128">Personal-views root folder</span></span>  <br/> |<span data-ttu-id="60c94-129">包含用于管理特定用户的视图的文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-129">Contains folders for managing views for a particular user.</span></span>  <br/> |
   
<span data-ttu-id="60c94-130">与 IPM 子树，MAPI 创建初始化的消息存储时的文件夹的树相关的前四个文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-130">The first four folders relate to the IPM subtree, a tree of folders that MAPI creates when a message store is initialized.</span></span> <span data-ttu-id="60c94-131">交互式消息客户端的默认邮件存储始终包括 IPM 文件夹子树和其他特殊文件夹，其文件夹层次结构中。</span><span class="sxs-lookup"><span data-stu-id="60c94-131">Default message stores for interactive messaging clients always include the IPM folder subtree and the other special folders in their folder hierarchy.</span></span> <span data-ttu-id="60c94-132">非默认的消息存储仅需要支持的搜索结果的根文件夹、 IPM 子树的根文件夹、 已删除邮件文件夹中和接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-132">Non-default message stores are required only to support the search-results root folder, the IPM subtree root folder, the Deleted Items folder, and the receive folder.</span></span> <span data-ttu-id="60c94-133">若要确保 IPM 子树文件夹存在和有效，客户端可以调用[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数。</span><span class="sxs-lookup"><span data-stu-id="60c94-133">To ensure that the IPM subtree folders exist and are valid, clients can call the [HrValidateIPMSubtree](hrvalidateipmsubtree.md) function.</span></span> <span data-ttu-id="60c94-134">**HrValidateIPMSubtree**检查文件夹，并重新创建这些问题时。</span><span class="sxs-lookup"><span data-stu-id="60c94-134">**HrValidateIPMSubtree** checks the folders and recreates them if there is a problem.</span></span> 
  
<span data-ttu-id="60c94-135">不属于 IPM 子树; 搜索结果、 公共视图和个人视图的根文件夹。消息存储库的根文件夹中创建这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-135">The root folders for search results, common views, and personal views are not part of the IPM subtree; these folders are created in the root folder for the message store.</span></span> <span data-ttu-id="60c94-136">搜索结果的根文件夹包含支持内容表包含符合搜索条件的一组的邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-136">The search-results root folder contains folders that support contents tables with messages that satisfy a set of search criteria.</span></span> <span data-ttu-id="60c94-137">允许的客户端在任何文件夹中创建搜索结果文件夹，尽管大多数客户端指定要将所有搜索结果的父对象的单个根文件夹在会话过程中创建的文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-137">Although clients are allowed to create search-results folders in any folder, most clients designate a single root folder to be the parent of all the search-results folders created during the session.</span></span> 
  
<span data-ttu-id="60c94-138">公共视图和个人视图的根文件夹包含描述视图或来显示邮件和文件夹的数据的首选的方法的消息。</span><span class="sxs-lookup"><span data-stu-id="60c94-138">The common-views and personal-views root folders contain messages that describe views, or preferred ways of presenting message and folder data.</span></span> <span data-ttu-id="60c94-139">常见视图根文件夹中包含的客户端可以使用任何文件夹中的消息存储; 视图个人视图文件夹包含由特定用户的特定文件夹或文件夹已定义的视图。</span><span class="sxs-lookup"><span data-stu-id="60c94-139">The common-views root folder contains views that clients can use with any folder in the message store; the personal-views folder contains views that have been defined by a particular user for a particular folder or folders.</span></span>
  
<span data-ttu-id="60c94-140">处理 IPM 邮件的客户端应创建的所有文件夹和 IPM 子树的根文件夹，而不是邮件存储区的根文件夹下的邮件。</span><span class="sxs-lookup"><span data-stu-id="60c94-140">Clients that work with IPM messages should create all folders and messages under the IPM subtree root folder, rather than the root folder of the message store.</span></span> <span data-ttu-id="60c94-141">这种非 IPM 客户端 — 客户端计算机之间人和计算机或之间交换消息处理 — 用于隐藏 IPM 客户端从其邮件简便方法。</span><span class="sxs-lookup"><span data-stu-id="60c94-141">This gives non-IPM clients — the clients that deal with messages exchanged between computers or between humans and computers — an easy way to hide their messages from IPM clients.</span></span> 
  
<span data-ttu-id="60c94-142">MAPI 将这些特殊文件夹的标识符属性分配特殊的条目。</span><span class="sxs-lookup"><span data-stu-id="60c94-142">MAPI assigns special entry identifier properties for these special folders.</span></span> <span data-ttu-id="60c94-143">特殊文件夹项标识符的列表，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="60c94-143">For a list of the special folder entry identifiers, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
  
### <a name="outlook-special-folders"></a><span data-ttu-id="60c94-144">Outlook 特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-144">Outlook Special Folders</span></span>

<span data-ttu-id="60c94-145">由其条目存储在收件箱文件夹和消息存储库的根文件夹中的 Id 标识 outlook 特殊文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c94-145">Outlook special folders are identified by their entry IDs that are stored in the Inbox folder and the root folder for the message store.</span></span>
  
|<span data-ttu-id="60c94-146">**Folder**</span><span class="sxs-lookup"><span data-stu-id="60c94-146">**Folder**</span></span>|<span data-ttu-id="60c94-147">**要设置的属性**</span><span class="sxs-lookup"><span data-stu-id="60c94-147">**The property to set**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60c94-148">日历</span><span class="sxs-lookup"><span data-stu-id="60c94-148">Calendar</span></span>  <br/> |<span data-ttu-id="60c94-149">**PR_IPM_APPOINTMENT_ENTRYID**([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c94-149">**PR_IPM_APPOINTMENT_ENTRYID** ([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="60c94-150">联系人</span><span class="sxs-lookup"><span data-stu-id="60c94-150">Contacts</span></span>  <br/> |<span data-ttu-id="60c94-151">**PR_IPM_CONTACT_ENTRYID**([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c94-151">**PR_IPM_CONTACT_ENTRYID** ([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="60c94-152">日记</span><span class="sxs-lookup"><span data-stu-id="60c94-152">Journal</span></span>  <br/> |<span data-ttu-id="60c94-153">**PR_IPM_JOURNAL_ENTRYID**([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c94-153">**PR_IPM_JOURNAL_ENTRYID** ([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="60c94-154">笔记</span><span class="sxs-lookup"><span data-stu-id="60c94-154">Notes</span></span>  <br/> |<span data-ttu-id="60c94-155">**PR_IPM_NOTE_ENTRYID**([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c94-155">**PR_IPM_NOTE_ENTRYID** ([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="60c94-156">任务</span><span class="sxs-lookup"><span data-stu-id="60c94-156">Tasks</span></span>  <br/> |<span data-ttu-id="60c94-157">**PR_IPM_TASK_ENTRYID**([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c94-157">**PR_IPM_TASK_ENTRYID** ([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="60c94-158">草稿</span><span class="sxs-lookup"><span data-stu-id="60c94-158">Drafts</span></span>  <br/> |<span data-ttu-id="60c94-159">**PR_IPM_DRAFTS_ENTRYID**([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c94-159">**PR_IPM_DRAFTS_ENTRYID** ([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="60c94-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60c94-160">See also</span></span>



[<span data-ttu-id="60c94-161">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="60c94-161">MAPI Folders</span></span>](mapi-folders.md)

