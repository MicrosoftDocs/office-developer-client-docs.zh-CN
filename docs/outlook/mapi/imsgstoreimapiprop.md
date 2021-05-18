---
title: IMsgStore IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore
api_type:
- COM
ms.assetid: 20090114-b183-4767-8971-a304a9aa47e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: af4bf73b58f7723066bb8fad7c087ba0238ceec2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422325"
---
# <a name="imsgstore--imapiprop"></a><span data-ttu-id="58fb1-103">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="58fb1-103">IMsgStore : IMAPIProp</span></span>

  
  
<span data-ttu-id="58fb1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58fb1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58fb1-105">提供对邮件存储信息以及邮件和文件夹的访问权限。</span><span class="sxs-lookup"><span data-stu-id="58fb1-105">Provides access to message store information and to messages and folders.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="58fb1-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="58fb1-106">Header file:</span></span>  <br/> |<span data-ttu-id="58fb1-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="58fb1-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="58fb1-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="58fb1-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="58fb1-109">邮件存储对象</span><span class="sxs-lookup"><span data-stu-id="58fb1-109">Message store object</span></span>  <br/> |
|<span data-ttu-id="58fb1-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="58fb1-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="58fb1-111">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="58fb1-111">Message store providers</span></span>  <br/> |
|<span data-ttu-id="58fb1-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="58fb1-112">Called by:</span></span>  <br/> |<span data-ttu-id="58fb1-113">客户端应用程序、MAPI 后台处理程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="58fb1-113">Client applications, the MAPI spooler, and MAPI</span></span>  <br/> |
|<span data-ttu-id="58fb1-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="58fb1-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="58fb1-115">IID_IMsgStore</span><span class="sxs-lookup"><span data-stu-id="58fb1-115">IID_IMsgStore</span></span>  <br/> |
|<span data-ttu-id="58fb1-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="58fb1-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="58fb1-117">LPMDB</span><span class="sxs-lookup"><span data-stu-id="58fb1-117">LPMDB</span></span>  <br/> |
|<span data-ttu-id="58fb1-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="58fb1-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="58fb1-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="58fb1-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="58fb1-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="58fb1-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="58fb1-121">建议</span><span class="sxs-lookup"><span data-stu-id="58fb1-121">Advise</span></span>](imsgstore-advise.md) <br/> |<span data-ttu-id="58fb1-122">注册以接收影响邮件存储的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="58fb1-122">Registers to receive notification of specified events that affect the message store.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-123">非企业</span><span class="sxs-lookup"><span data-stu-id="58fb1-123">Unadvise</span></span>](imsgstore-unadvise.md) <br/> |<span data-ttu-id="58fb1-124">取消发送以前通过调用 **IMsgStore：：Advise** 方法设置的通知。</span><span class="sxs-lookup"><span data-stu-id="58fb1-124">Cancels the sending of notifications previously set up with a call to the **IMsgStore::Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-125">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="58fb1-125">CompareEntryIDs</span></span>](imsgstore-compareentryids.md) <br/> |<span data-ttu-id="58fb1-126">比较两个条目标识符以确定它们是否引用邮件存储中的同一条目。</span><span class="sxs-lookup"><span data-stu-id="58fb1-126">Compares two entry identifiers to determine whether they refer to the same entry in a message store.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-127">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="58fb1-127">OpenEntry</span></span>](imsgstore-openentry.md) <br/> |<span data-ttu-id="58fb1-128">打开文件夹或邮件并返回接口指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="58fb1-128">Opens a folder or message and returns an interface pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-129">SetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="58fb1-129">SetReceiveFolder</span></span>](imsgstore-setreceivefolder.md) <br/> |<span data-ttu-id="58fb1-130">建立一个文件夹作为特定邮件类的传入邮件的目标。</span><span class="sxs-lookup"><span data-stu-id="58fb1-130">Establishes a folder as the destination for incoming messages of a particular message class.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-131">GetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="58fb1-131">GetReceiveFolder</span></span>](imsgstore-getreceivefolder.md) <br/> |<span data-ttu-id="58fb1-132">获取已建立为指定邮件类的传入邮件的目标或作为邮件存储的默认接收文件夹的文件夹。</span><span class="sxs-lookup"><span data-stu-id="58fb1-132">Obtains the folder that was established as the destination for incoming messages of a specified message class or as the default receive folder for the message store.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-133">GetReceiveFolderTable</span><span class="sxs-lookup"><span data-stu-id="58fb1-133">GetReceiveFolderTable</span></span>](imsgstore-getreceivefoldertable.md) <br/> |<span data-ttu-id="58fb1-134">提供对接收文件夹表的访问权限，该表包含有关邮件存储的所有接收文件夹的信息。</span><span class="sxs-lookup"><span data-stu-id="58fb1-134">Provides access to the receive folder table, a table with information about all of the receive folders for the message store.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-135">StoreLogoff</span><span class="sxs-lookup"><span data-stu-id="58fb1-135">StoreLogoff</span></span>](imsgstore-storelogoff.md) <br/> |<span data-ttu-id="58fb1-136">启用邮件存储的有序注销。</span><span class="sxs-lookup"><span data-stu-id="58fb1-136">Enables the orderly logoff of the message store.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-137">AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="58fb1-137">AbortSubmit</span></span>](imsgstore-abortsubmit.md) <br/> |<span data-ttu-id="58fb1-138">尝试从传出队列中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="58fb1-138">Attempts to remove a message from the outgoing queue.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-139">GetOutgoingQueue</span><span class="sxs-lookup"><span data-stu-id="58fb1-139">GetOutgoingQueue</span></span>](imsgstore-getoutgoingqueue.md) <br/> |<span data-ttu-id="58fb1-140">提供对传出队列表的访问，该表包含有关邮件存储的传出队列中所有邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="58fb1-140">Provides access to the outgoing queue table, a table that has information about all of the messages in the message store's outgoing queue.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-141">SetLockState</span><span class="sxs-lookup"><span data-stu-id="58fb1-141">SetLockState</span></span>](imsgstore-setlockstate.md) <br/> |<span data-ttu-id="58fb1-142">锁定或解锁邮件。</span><span class="sxs-lookup"><span data-stu-id="58fb1-142">Locks or unlocks a message.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-143">FinishedMsg</span><span class="sxs-lookup"><span data-stu-id="58fb1-143">FinishedMsg</span></span>](imsgstore-finishedmsg.md) <br/> |<span data-ttu-id="58fb1-144">使邮件存储提供程序能够对已发送的邮件执行处理。</span><span class="sxs-lookup"><span data-stu-id="58fb1-144">Enables the message store provider to perform processing on a sent message.</span></span>  <br/> |
|[<span data-ttu-id="58fb1-145">NotifyNewMail</span><span class="sxs-lookup"><span data-stu-id="58fb1-145">NotifyNewMail</span></span>](imsgstore-notifynewmail.md) <br/> |<span data-ttu-id="58fb1-146">通知邮件存储新邮件已到达。</span><span class="sxs-lookup"><span data-stu-id="58fb1-146">Informs the message store that a new message has arrived.</span></span>  <br/> |
   
|<span data-ttu-id="58fb1-147">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="58fb1-147">**Required properties**</span></span>|<span data-ttu-id="58fb1-148">**访问级别**</span><span class="sxs-lookup"><span data-stu-id="58fb1-148">**Access level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58fb1-149">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="58fb1-149">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="58fb1-150">读/写</span><span class="sxs-lookup"><span data-stu-id="58fb1-150">Read/write</span></span>  <br/> |
|<span data-ttu-id="58fb1-151">**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="58fb1-151">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="58fb1-152">只读</span><span class="sxs-lookup"><span data-stu-id="58fb1-152">Read-only</span></span>  <br/> |
|<span data-ttu-id="58fb1-153">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="58fb1-153">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="58fb1-154">只读</span><span class="sxs-lookup"><span data-stu-id="58fb1-154">Read-only</span></span>  <br/> |
|<span data-ttu-id="58fb1-155">**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="58fb1-155">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="58fb1-156">只读</span><span class="sxs-lookup"><span data-stu-id="58fb1-156">Read-only</span></span>  <br/> |
|<span data-ttu-id="58fb1-157">**PR_STORE_ENTRYID (** [PidTagStoreEntryId)](pidtagstoreentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="58fb1-157">**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="58fb1-158">只读</span><span class="sxs-lookup"><span data-stu-id="58fb1-158">Read-only</span></span>  <br/> |
|<span data-ttu-id="58fb1-159">**PR_STORE_RECORD_KEY (** [PidTagStoreRecordKey)](pidtagstorerecordkey-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="58fb1-159">**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="58fb1-160">只读</span><span class="sxs-lookup"><span data-stu-id="58fb1-160">Read-only</span></span>  <br/> |
|<span data-ttu-id="58fb1-161">**PR_MDB_PROVIDER (** [PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="58fb1-161">**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="58fb1-162">只读</span><span class="sxs-lookup"><span data-stu-id="58fb1-162">Read-only</span></span>  <br/> |
|<span data-ttu-id="58fb1-163">**PR_STORE_SUPPORT_MASK (** [PidTagStoreSupportMask)](pidtagstoresupportmask-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="58fb1-163">**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="58fb1-164">只读</span><span class="sxs-lookup"><span data-stu-id="58fb1-164">Read-only</span></span>  <br/> |
   
<span data-ttu-id="58fb1-165">以下属性用于 IPM (邮件) 邮件：</span><span class="sxs-lookup"><span data-stu-id="58fb1-165">The following properties are for interpersonal message (IPM) message stores:</span></span>
  
- <span data-ttu-id="58fb1-166">**PR_IPM_OUTBOX_ENTRYID (** [PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="58fb1-166">**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="58fb1-167">**PR_IPM_SENTMAIL_ENTRYID (** [PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="58fb1-167">**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="58fb1-168">**PR_IPM_SUBTREE_ENTRYID (** [PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="58fb1-168">**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="58fb1-169">**PR_IPM_WASTEBASKET_ENTRYID (** [PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="58fb1-169">**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="58fb1-170">**PR_MDB_PROVIDER**</span><span class="sxs-lookup"><span data-stu-id="58fb1-170">**PR_MDB_PROVIDER**</span></span>
    
- <span data-ttu-id="58fb1-171">**PR_STORE_SUPPORT_MASK**</span><span class="sxs-lookup"><span data-stu-id="58fb1-171">**PR_STORE_SUPPORT_MASK**</span></span>
    
## <a name="see-also"></a><span data-ttu-id="58fb1-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58fb1-172">See also</span></span>



[<span data-ttu-id="58fb1-173">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="58fb1-173">MAPI Properties</span></span>](mapi-properties.md)

