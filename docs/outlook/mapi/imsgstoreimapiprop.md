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
ms.openlocfilehash: 4ed17fd7f826432da9460fe01e5aa76802726bad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584630"
---
# <a name="imsgstore--imapiprop"></a><span data-ttu-id="0e512-103">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="0e512-103">IMsgStore : IMAPIProp</span></span>

  
  
<span data-ttu-id="0e512-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0e512-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0e512-105">提供对邮件存储信息和邮件和文件夹访问。</span><span class="sxs-lookup"><span data-stu-id="0e512-105">Provides access to message store information and to messages and folders.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0e512-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="0e512-106">Header file:</span></span>  <br/> |<span data-ttu-id="0e512-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0e512-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="0e512-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="0e512-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="0e512-109">消息存储对象</span><span class="sxs-lookup"><span data-stu-id="0e512-109">Message store object</span></span>  <br/> |
|<span data-ttu-id="0e512-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="0e512-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="0e512-111">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="0e512-111">Message store providers</span></span>  <br/> |
|<span data-ttu-id="0e512-112">调用：</span><span class="sxs-lookup"><span data-stu-id="0e512-112">Called by:</span></span>  <br/> |<span data-ttu-id="0e512-113">客户端应用程序、 MAPI 后台处理程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="0e512-113">Client applications, the MAPI spooler, and MAPI</span></span>  <br/> |
|<span data-ttu-id="0e512-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="0e512-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="0e512-115">IID_IMsgStore</span><span class="sxs-lookup"><span data-stu-id="0e512-115">IID_IMsgStore</span></span>  <br/> |
|<span data-ttu-id="0e512-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="0e512-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="0e512-117">LPMDB</span><span class="sxs-lookup"><span data-stu-id="0e512-117">LPMDB</span></span>  <br/> |
|<span data-ttu-id="0e512-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="0e512-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="0e512-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="0e512-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="0e512-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="0e512-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="0e512-121">建议</span><span class="sxs-lookup"><span data-stu-id="0e512-121">Advise</span></span>](imsgstore-advise.md) <br/> |<span data-ttu-id="0e512-122">注册接收影响消息存储库的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="0e512-122">Registers to receive notification of specified events that affect the message store.</span></span>  <br/> |
|[<span data-ttu-id="0e512-123">取消通知</span><span class="sxs-lookup"><span data-stu-id="0e512-123">Unadvise</span></span>](imsgstore-unadvise.md) <br/> |<span data-ttu-id="0e512-124">取消发送通知之前设置与对**IMsgStore::Advise**方法的调用。</span><span class="sxs-lookup"><span data-stu-id="0e512-124">Cancels the sending of notifications previously set up with a call to the **IMsgStore::Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="0e512-125">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="0e512-125">CompareEntryIDs</span></span>](imsgstore-compareentryids.md) <br/> |<span data-ttu-id="0e512-126">比较两个条目标识符来确定它们是否引用中的消息存储的同一个条目。</span><span class="sxs-lookup"><span data-stu-id="0e512-126">Compares two entry identifiers to determine whether they refer to the same entry in a message store.</span></span>  <br/> |
|[<span data-ttu-id="0e512-127">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="0e512-127">OpenEntry</span></span>](imsgstore-openentry.md) <br/> |<span data-ttu-id="0e512-128">打开文件夹或消息并返回进一步访问的接口指针。</span><span class="sxs-lookup"><span data-stu-id="0e512-128">Opens a folder or message and returns an interface pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="0e512-129">SetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="0e512-129">SetReceiveFolder</span></span>](imsgstore-setreceivefolder.md) <br/> |<span data-ttu-id="0e512-130">为特定邮件类别的传入消息的目标建立一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e512-130">Establishes a folder as the destination for incoming messages of a particular message class.</span></span>  <br/> |
|[<span data-ttu-id="0e512-131">GetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="0e512-131">GetReceiveFolder</span></span>](imsgstore-getreceivefolder.md) <br/> |<span data-ttu-id="0e512-132">获取时，传入邮件指定的邮件类的或为默认的目标接收的消息存储库文件夹建立的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e512-132">Obtains the folder that was established as the destination for incoming messages of a specified message class or as the default receive folder for the message store.</span></span>  <br/> |
|[<span data-ttu-id="0e512-133">GetReceiveFolderTable</span><span class="sxs-lookup"><span data-stu-id="0e512-133">GetReceiveFolderTable</span></span>](imsgstore-getreceivefoldertable.md) <br/> |<span data-ttu-id="0e512-134">提供对接收文件夹表中，所有的接收文件夹的邮件存储的信息与表格的访问。</span><span class="sxs-lookup"><span data-stu-id="0e512-134">Provides access to the receive folder table, a table with information about all of the receive folders for the message store.</span></span>  <br/> |
|[<span data-ttu-id="0e512-135">StoreLogoff</span><span class="sxs-lookup"><span data-stu-id="0e512-135">StoreLogoff</span></span>](imsgstore-storelogoff.md) <br/> |<span data-ttu-id="0e512-136">允许的邮件存储的有序注销。</span><span class="sxs-lookup"><span data-stu-id="0e512-136">Enables the orderly logoff of the message store.</span></span>  <br/> |
|[<span data-ttu-id="0e512-137">AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="0e512-137">AbortSubmit</span></span>](imsgstore-abortsubmit.md) <br/> |<span data-ttu-id="0e512-138">尝试从传出队列中删除一条消息。</span><span class="sxs-lookup"><span data-stu-id="0e512-138">Attempts to remove a message from the outgoing queue.</span></span>  <br/> |
|[<span data-ttu-id="0e512-139">GetOutgoingQueue</span><span class="sxs-lookup"><span data-stu-id="0e512-139">GetOutgoingQueue</span></span>](imsgstore-getoutgoingqueue.md) <br/> |<span data-ttu-id="0e512-140">提供对传出队列表，具有信息的所有邮件的邮件存储传出队列中的表的访问。</span><span class="sxs-lookup"><span data-stu-id="0e512-140">Provides access to the outgoing queue table, a table that has information about all of the messages in the message store's outgoing queue.</span></span>  <br/> |
|[<span data-ttu-id="0e512-141">SetLockState</span><span class="sxs-lookup"><span data-stu-id="0e512-141">SetLockState</span></span>](imsgstore-setlockstate.md) <br/> |<span data-ttu-id="0e512-142">锁定或解除锁定一条消息。</span><span class="sxs-lookup"><span data-stu-id="0e512-142">Locks or unlocks a message.</span></span>  <br/> |
|[<span data-ttu-id="0e512-143">FinishedMsg</span><span class="sxs-lookup"><span data-stu-id="0e512-143">FinishedMsg</span></span>](imsgstore-finishedmsg.md) <br/> |<span data-ttu-id="0e512-144">启用对已发送的邮件执行处理的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="0e512-144">Enables the message store provider to perform processing on a sent message.</span></span>  <br/> |
|[<span data-ttu-id="0e512-145">NotifyNewMail</span><span class="sxs-lookup"><span data-stu-id="0e512-145">NotifyNewMail</span></span>](imsgstore-notifynewmail.md) <br/> |<span data-ttu-id="0e512-146">通知新消息已到达的消息存储。</span><span class="sxs-lookup"><span data-stu-id="0e512-146">Informs the message store that a new message has arrived.</span></span>  <br/> |
   
|<span data-ttu-id="0e512-147">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="0e512-147">**Required properties**</span></span>|<span data-ttu-id="0e512-148">**访问级别**</span><span class="sxs-lookup"><span data-stu-id="0e512-148">**Access level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e512-149">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-149">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e512-150">读/写</span><span class="sxs-lookup"><span data-stu-id="0e512-150">Read/write</span></span>  <br/> |
|<span data-ttu-id="0e512-151">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-151">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e512-152">只读</span><span class="sxs-lookup"><span data-stu-id="0e512-152">Read-only</span></span>  <br/> |
|<span data-ttu-id="0e512-153">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-153">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e512-154">只读</span><span class="sxs-lookup"><span data-stu-id="0e512-154">Read-only</span></span>  <br/> |
|<span data-ttu-id="0e512-155">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-155">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e512-156">只读</span><span class="sxs-lookup"><span data-stu-id="0e512-156">Read-only</span></span>  <br/> |
|<span data-ttu-id="0e512-157">**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-157">**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e512-158">只读</span><span class="sxs-lookup"><span data-stu-id="0e512-158">Read-only</span></span>  <br/> |
|<span data-ttu-id="0e512-159">**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-159">**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e512-160">只读</span><span class="sxs-lookup"><span data-stu-id="0e512-160">Read-only</span></span>  <br/> |
|<span data-ttu-id="0e512-161">**PR_MDB_PROVIDER**([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-161">**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e512-162">只读</span><span class="sxs-lookup"><span data-stu-id="0e512-162">Read-only</span></span>  <br/> |
|<span data-ttu-id="0e512-163">**PR_STORE_SUPPORT_MASK**([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-163">**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e512-164">只读</span><span class="sxs-lookup"><span data-stu-id="0e512-164">Read-only</span></span>  <br/> |
   
<span data-ttu-id="0e512-165">人际邮件 (IPM) 消息存储库的以下属性：</span><span class="sxs-lookup"><span data-stu-id="0e512-165">The following properties are for interpersonal message (IPM) message stores:</span></span>
  
- <span data-ttu-id="0e512-166">**PR_IPM_OUTBOX_ENTRYID**([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-166">**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="0e512-167">**PR_IPM_SENTMAIL_ENTRYID**([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-167">**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="0e512-168">**PR_IPM_SUBTREE_ENTRYID**([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-168">**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="0e512-169">**PR_IPM_WASTEBASKET_ENTRYID**([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e512-169">**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="0e512-170">**PR_MDB_PROVIDER**</span><span class="sxs-lookup"><span data-stu-id="0e512-170">**PR_MDB_PROVIDER**</span></span>
    
- <span data-ttu-id="0e512-171">**PR_STORE_SUPPORT_MASK**</span><span class="sxs-lookup"><span data-stu-id="0e512-171">**PR_STORE_SUPPORT_MASK**</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0e512-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e512-172">See also</span></span>



[<span data-ttu-id="0e512-173">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0e512-173">MAPI Properties</span></span>](mapi-properties.md)

