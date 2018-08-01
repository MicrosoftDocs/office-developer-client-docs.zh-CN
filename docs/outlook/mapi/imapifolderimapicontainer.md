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
ms.openlocfilehash: 64a64029c3507d9ac4b520076a44e23170dd9bd4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775377"
---
# <a name="imapifolder--imapicontainer"></a><span data-ttu-id="e861a-103">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="e861a-103">IMAPIFolder : IMAPIContainer</span></span>

  
  
<span data-ttu-id="e861a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e861a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e861a-105">在文件夹中执行操作的消息和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e861a-105">Performs operations on the messages and subfolders in a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e861a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e861a-106">Header file:</span></span>  <br/> |<span data-ttu-id="e861a-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e861a-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="e861a-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="e861a-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="e861a-109">文件夹对象</span><span class="sxs-lookup"><span data-stu-id="e861a-109">Folder objects</span></span>  <br/> |
|<span data-ttu-id="e861a-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="e861a-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="e861a-111">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e861a-111">Message store providers</span></span>  <br/> |
|<span data-ttu-id="e861a-112">调用：</span><span class="sxs-lookup"><span data-stu-id="e861a-112">Called by:</span></span>  <br/> |<span data-ttu-id="e861a-113">客户端应用程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="e861a-113">Client applications and MAPI</span></span>  <br/> |
|<span data-ttu-id="e861a-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="e861a-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="e861a-115">IID_IMAPIFolder</span><span class="sxs-lookup"><span data-stu-id="e861a-115">IID_IMAPIFolder</span></span>  <br/> |
|<span data-ttu-id="e861a-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="e861a-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="e861a-117">LPMAPIFOLDER</span><span class="sxs-lookup"><span data-stu-id="e861a-117">LPMAPIFOLDER</span></span>  <br/> |
|<span data-ttu-id="e861a-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="e861a-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="e861a-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="e861a-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="e861a-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="e861a-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="e861a-121">CreateMessage</span><span class="sxs-lookup"><span data-stu-id="e861a-121">CreateMessage</span></span>](imapifolder-createmessage.md) <br/> |<span data-ttu-id="e861a-122">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="e861a-122">Creates a new message.</span></span>  <br/> |
|[<span data-ttu-id="e861a-123">CopyMessages</span><span class="sxs-lookup"><span data-stu-id="e861a-123">CopyMessages</span></span>](imapifolder-copymessages.md) <br/> |<span data-ttu-id="e861a-124">复制或移动一个或多条消息。</span><span class="sxs-lookup"><span data-stu-id="e861a-124">Copies or moves one or more messages.</span></span>  <br/> |
|[<span data-ttu-id="e861a-125">DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="e861a-125">DeleteMessages</span></span>](imapifolder-deletemessages.md) <br/> |<span data-ttu-id="e861a-126">删除一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="e861a-126">Deletes one or more messages.</span></span>  <br/> |
|[<span data-ttu-id="e861a-127">CreateFolder</span><span class="sxs-lookup"><span data-stu-id="e861a-127">CreateFolder</span></span>](imapifolder-createfolder.md) <br/> |<span data-ttu-id="e861a-128">创建新的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e861a-128">Creates a new subfolder.</span></span>  <br/> |
|[<span data-ttu-id="e861a-129">CopyFolder</span><span class="sxs-lookup"><span data-stu-id="e861a-129">CopyFolder</span></span>](imapifolder-copyfolder.md) <br/> |<span data-ttu-id="e861a-130">复制或移动的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e861a-130">Copies or moves a subfolder.</span></span>  <br/> |
|[<span data-ttu-id="e861a-131">DeleteFolder</span><span class="sxs-lookup"><span data-stu-id="e861a-131">DeleteFolder</span></span>](imapifolder-deletefolder.md) <br/> |<span data-ttu-id="e861a-132">删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e861a-132">Deletes a subfolder.</span></span>  <br/> |
|[<span data-ttu-id="e861a-133">SetReadFlags</span><span class="sxs-lookup"><span data-stu-id="e861a-133">SetReadFlags</span></span>](imapifolder-setreadflags.md) <br/> |<span data-ttu-id="e861a-134">设置或清除 MSGFLAG_READ 标志中的一个或多个文件夹的邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性并管理阅读报告的发送。</span><span class="sxs-lookup"><span data-stu-id="e861a-134">Sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of one or more of the folder's messages, and manages the sending of read reports.</span></span>  <br/> |
|[<span data-ttu-id="e861a-135">GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="e861a-135">GetMessageStatus</span></span>](imapifolder-getmessagestatus.md) <br/> |<span data-ttu-id="e861a-136">获取与特定文件夹中的邮件关联的状态。</span><span class="sxs-lookup"><span data-stu-id="e861a-136">Obtains the status associated with a message in a particular folder.</span></span>  <br/> |
|[<span data-ttu-id="e861a-137">SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="e861a-137">SetMessageStatus</span></span>](imapifolder-setmessagestatus.md) <br/> |<span data-ttu-id="e861a-138">设置与消息关联的状态。</span><span class="sxs-lookup"><span data-stu-id="e861a-138">Sets the status associated with a message.</span></span>  <br/> |
|[<span data-ttu-id="e861a-139">SaveContentsSort</span><span class="sxs-lookup"><span data-stu-id="e861a-139">SaveContentsSort</span></span>](imapifolder-savecontentssort.md) <br/> |<span data-ttu-id="e861a-140">设置某个文件夹的内容表的默认排序次序。</span><span class="sxs-lookup"><span data-stu-id="e861a-140">Sets the default sort order for a folder's contents table.</span></span>  <br/> |
|[<span data-ttu-id="e861a-141">EmptyFolder</span><span class="sxs-lookup"><span data-stu-id="e861a-141">EmptyFolder</span></span>](imapifolder-emptyfolder.md) <br/> |<span data-ttu-id="e861a-142">删除所有消息和子文件夹从文件夹而不删除该文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="e861a-142">Deletes all messages and subfolders from a folder without deleting the folder itself.</span></span>  <br/> |
   
|<span data-ttu-id="e861a-143">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="e861a-143">**Required properties**</span></span>|<span data-ttu-id="e861a-144">**Access**</span><span class="sxs-lookup"><span data-stu-id="e861a-144">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e861a-145">**PR_DISPLAY_NAME**([PidTagDisplayNamePrefix](pidtagdisplaynameprefix-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e861a-145">**PR_DISPLAY_NAME** ([PidTagDisplayNamePrefix](pidtagdisplaynameprefix-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e861a-146">读/写</span><span class="sxs-lookup"><span data-stu-id="e861a-146">Read/write</span></span>  <br/> |
|<span data-ttu-id="e861a-147">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e861a-147">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e861a-148">只读</span><span class="sxs-lookup"><span data-stu-id="e861a-148">Read-only</span></span>  <br/> |
|<span data-ttu-id="e861a-149">**PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e861a-149">**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e861a-150">读/写</span><span class="sxs-lookup"><span data-stu-id="e861a-150">Read/write</span></span>  <br/> |
|<span data-ttu-id="e861a-151">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e861a-151">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e861a-152">只读</span><span class="sxs-lookup"><span data-stu-id="e861a-152">Read-only</span></span>  <br/> |
|<span data-ttu-id="e861a-153">**PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e861a-153">**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e861a-154">只读</span><span class="sxs-lookup"><span data-stu-id="e861a-154">Read-only</span></span>  <br/> |
|<span data-ttu-id="e861a-155">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e861a-155">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e861a-156">只读</span><span class="sxs-lookup"><span data-stu-id="e861a-156">Read-only</span></span>  <br/> |
|<span data-ttu-id="e861a-157">**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e861a-157">**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e861a-158">只读</span><span class="sxs-lookup"><span data-stu-id="e861a-158">Read-only</span></span>  <br/> |
|<span data-ttu-id="e861a-159">**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e861a-159">**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e861a-160">只读</span><span class="sxs-lookup"><span data-stu-id="e861a-160">Read-only</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e861a-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e861a-161">See also</span></span>



[<span data-ttu-id="e861a-162">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="e861a-162">MAPI Interfaces</span></span>](mapi-interfaces.md)

