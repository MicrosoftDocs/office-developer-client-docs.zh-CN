---
title: IMAPIFolder IMAPIContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder
api_type:
- COM
ms.assetid: bc2e8d17-7687-43c2-8f01-b677703f7288
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e31896354141999e02f2cba117ef9739340be61
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424236"
---
# <a name="imapifolder--imapicontainer"></a><span data-ttu-id="0bf33-103">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="0bf33-103">IMAPIFolder : IMAPIContainer</span></span>

  
  
<span data-ttu-id="0bf33-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0bf33-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0bf33-105">对文件夹中的邮件和子文件夹执行操作。</span><span class="sxs-lookup"><span data-stu-id="0bf33-105">Performs operations on the messages and subfolders in a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0bf33-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0bf33-106">Header file:</span></span>  <br/> |<span data-ttu-id="0bf33-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0bf33-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="0bf33-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="0bf33-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="0bf33-109">Folder 对象</span><span class="sxs-lookup"><span data-stu-id="0bf33-109">Folder objects</span></span>  <br/> |
|<span data-ttu-id="0bf33-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="0bf33-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="0bf33-111">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="0bf33-111">Message store providers</span></span>  <br/> |
|<span data-ttu-id="0bf33-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="0bf33-112">Called by:</span></span>  <br/> |<span data-ttu-id="0bf33-113">客户端应用程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="0bf33-113">Client applications and MAPI</span></span>  <br/> |
|<span data-ttu-id="0bf33-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="0bf33-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="0bf33-115">IID_IMAPIFolder</span><span class="sxs-lookup"><span data-stu-id="0bf33-115">IID_IMAPIFolder</span></span>  <br/> |
|<span data-ttu-id="0bf33-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="0bf33-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="0bf33-117">LPMAPIFOLDER</span><span class="sxs-lookup"><span data-stu-id="0bf33-117">LPMAPIFOLDER</span></span>  <br/> |
|<span data-ttu-id="0bf33-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="0bf33-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="0bf33-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="0bf33-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="0bf33-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="0bf33-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="0bf33-121">CreateMessage</span><span class="sxs-lookup"><span data-stu-id="0bf33-121">CreateMessage</span></span>](imapifolder-createmessage.md) <br/> |<span data-ttu-id="0bf33-122">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="0bf33-122">Creates a new message.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-123">CopyMessages</span><span class="sxs-lookup"><span data-stu-id="0bf33-123">CopyMessages</span></span>](imapifolder-copymessages.md) <br/> |<span data-ttu-id="0bf33-124">复制或移动一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="0bf33-124">Copies or moves one or more messages.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-125">DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="0bf33-125">DeleteMessages</span></span>](imapifolder-deletemessages.md) <br/> |<span data-ttu-id="0bf33-126">删除一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="0bf33-126">Deletes one or more messages.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-127">CreateFolder</span><span class="sxs-lookup"><span data-stu-id="0bf33-127">CreateFolder</span></span>](imapifolder-createfolder.md) <br/> |<span data-ttu-id="0bf33-128">创建新的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bf33-128">Creates a new subfolder.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-129">CopyFolder</span><span class="sxs-lookup"><span data-stu-id="0bf33-129">CopyFolder</span></span>](imapifolder-copyfolder.md) <br/> |<span data-ttu-id="0bf33-130">复制或移动子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bf33-130">Copies or moves a subfolder.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-131">DeleteFolder</span><span class="sxs-lookup"><span data-stu-id="0bf33-131">DeleteFolder</span></span>](imapifolder-deletefolder.md) <br/> |<span data-ttu-id="0bf33-132">删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bf33-132">Deletes a subfolder.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-133">SetReadFlags</span><span class="sxs-lookup"><span data-stu-id="0bf33-133">SetReadFlags</span></span>](imapifolder-setreadflags.md) <br/> |<span data-ttu-id="0bf33-134">设置或清除文件夹的一个或多个邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标志，并管理读取报表的发送。</span><span class="sxs-lookup"><span data-stu-id="0bf33-134">Sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of one or more of the folder's messages, and manages the sending of read reports.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-135">GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="0bf33-135">GetMessageStatus</span></span>](imapifolder-getmessagestatus.md) <br/> |<span data-ttu-id="0bf33-136">获取与特定文件夹中的邮件相关联的状态。</span><span class="sxs-lookup"><span data-stu-id="0bf33-136">Obtains the status associated with a message in a particular folder.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-137">SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="0bf33-137">SetMessageStatus</span></span>](imapifolder-setmessagestatus.md) <br/> |<span data-ttu-id="0bf33-138">设置与邮件关联的状态。</span><span class="sxs-lookup"><span data-stu-id="0bf33-138">Sets the status associated with a message.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-139">SaveContentsSort</span><span class="sxs-lookup"><span data-stu-id="0bf33-139">SaveContentsSort</span></span>](imapifolder-savecontentssort.md) <br/> |<span data-ttu-id="0bf33-140">设置文件夹的内容表的默认排序顺序。</span><span class="sxs-lookup"><span data-stu-id="0bf33-140">Sets the default sort order for a folder's contents table.</span></span>  <br/> |
|[<span data-ttu-id="0bf33-141">EmptyFolder</span><span class="sxs-lookup"><span data-stu-id="0bf33-141">EmptyFolder</span></span>](imapifolder-emptyfolder.md) <br/> |<span data-ttu-id="0bf33-142">从文件夹中删除所有邮件和子文件夹，而不删除文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="0bf33-142">Deletes all messages and subfolders from a folder without deleting the folder itself.</span></span>  <br/> |
   
|<span data-ttu-id="0bf33-143">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="0bf33-143">**Required properties**</span></span>|<span data-ttu-id="0bf33-144">**Access**</span><span class="sxs-lookup"><span data-stu-id="0bf33-144">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0bf33-145">**PR_DISPLAY_NAME (** [PidTagDisplayNamePrefix](pidtagdisplaynameprefix-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="0bf33-145">**PR_DISPLAY_NAME** ([PidTagDisplayNamePrefix](pidtagdisplaynameprefix-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0bf33-146">读/写</span><span class="sxs-lookup"><span data-stu-id="0bf33-146">Read/write</span></span>  <br/> |
|<span data-ttu-id="0bf33-147">**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="0bf33-147">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0bf33-148">只读</span><span class="sxs-lookup"><span data-stu-id="0bf33-148">Read-only</span></span>  <br/> |
|<span data-ttu-id="0bf33-149">**PR_FOLDER_TYPE (** [PidTagFolderType)](pidtagfoldertype-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="0bf33-149">**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0bf33-150">读/写</span><span class="sxs-lookup"><span data-stu-id="0bf33-150">Read/write</span></span>  <br/> |
|<span data-ttu-id="0bf33-151">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="0bf33-151">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0bf33-152">只读</span><span class="sxs-lookup"><span data-stu-id="0bf33-152">Read-only</span></span>  <br/> |
|<span data-ttu-id="0bf33-153">**PR_PARENT_ENTRYID (** [PidTagParentEntryId](pidtagparententryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="0bf33-153">**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0bf33-154">只读</span><span class="sxs-lookup"><span data-stu-id="0bf33-154">Read-only</span></span>  <br/> |
|<span data-ttu-id="0bf33-155">**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="0bf33-155">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0bf33-156">只读</span><span class="sxs-lookup"><span data-stu-id="0bf33-156">Read-only</span></span>  <br/> |
|<span data-ttu-id="0bf33-157">**PR_STORE_ENTRYID (** [PidTagStoreEntryId)](pidtagstoreentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="0bf33-157">**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0bf33-158">只读</span><span class="sxs-lookup"><span data-stu-id="0bf33-158">Read-only</span></span>  <br/> |
|<span data-ttu-id="0bf33-159">**PR_STORE_RECORD_KEY (** [PidTagStoreRecordKey)](pidtagstorerecordkey-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="0bf33-159">**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0bf33-160">只读</span><span class="sxs-lookup"><span data-stu-id="0bf33-160">Read-only</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0bf33-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf33-161">See also</span></span>



[<span data-ttu-id="0bf33-162">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="0bf33-162">MAPI Interfaces</span></span>](mapi-interfaces.md)

