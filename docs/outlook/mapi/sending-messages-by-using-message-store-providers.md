---
title: 使用邮件的发送消息存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7632d784-00d8-48fd-a73b-73778efbef7f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: aaba816ca7efab6cee939087a18332561f31b81b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778734"
---
# <a name="sending-messages-by-using-message-store-providers"></a><span data-ttu-id="a1fa8-103">使用邮件的发送消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="a1fa8-103">Sending messages by using message store providers</span></span>

<span data-ttu-id="a1fa8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a1fa8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a1fa8-105">消息存储提供程序不需要支持传出邮件提交 （即，客户端应用程序使用的消息存储提供程序来发送邮件的功能）。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-105">Message store providers are not required to support outgoing message submissions (that is, the ability for client applications to use the message store provider to send messages).</span></span> <span data-ttu-id="a1fa8-106">客户端应用程序需要使用的消息存储时发送邮件，因为必须消息的数据存储这二者之间用户已完成的时间撰写及其 MAPI 后台处理程序提供邮件到传输提供程序的时间提交到基础邮件系统。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-106">Client applications need to use a message store while sending messages, because the message's data must be stored somewhere between the time that the user is finished composing it and the time that the MAPI spooler gives the message to a transport provider for submission to the underlying messaging system.</span></span> <span data-ttu-id="a1fa8-107">如果您的消息存储提供程序不支持传出邮件提交，它不能用作默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-107">If your message store provider does not support outgoing message submissions, it cannot be used as the default message store.</span></span>
  
<span data-ttu-id="a1fa8-108">若要支持发送消息，消息存储提供程序必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-108">To support sending messages, your message store provider must do the following:</span></span>
  
- <span data-ttu-id="a1fa8-109">实现传出消息队列。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-109">Implement an outgoing message queue.</span></span>
    
- <span data-ttu-id="a1fa8-110">消息存储中创建的消息对象支持[IMessage::SubmitMessage](imessage-submitmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-110">Support the [IMessage::SubmitMessage](imessage-submitmessage.md) method on message objects created in the message store.</span></span> 
    
- <span data-ttu-id="a1fa8-111">支持特定于 MAPI 后台处理程序的**IMsgStore**方法： [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)、 [IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)、 [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)和[IMsgStore::SetLockState](imsgstore-setlockstate.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-111">Support the **IMsgStore** methods that are specific to the MAPI spooler: [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md), [IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md), [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md), and [IMsgStore::SetLockState](imsgstore-setlockstate.md).</span></span>
    
<span data-ttu-id="a1fa8-112">**SetLockState**方法很重要的 MAPI 后台处理程序和客户端之间的正确进行互操作。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-112">The **SetLockState** method is important for proper interoperation between the MAPI spooler and clients.</span></span> <span data-ttu-id="a1fa8-113">当 MAPI 后台处理程序调用**SetLockState**传出邮件时，消息存储提供程序必须不允许客户端打开该邮件。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-113">When the MAPI spooler calls **SetLockState** on an outgoing message, the message store provider must not let clients open the message.</span></span> <span data-ttu-id="a1fa8-114">如果客户端执行尝试打开一条消息，MAPI 后台处理程序被锁定，消息存储提供程序应返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-114">If a client does try to open a message that is locked by the MAPI spooler, the message store provider should return MAPI_E_NO_ACCESS.</span></span> <span data-ttu-id="a1fa8-115">不必是永久性的邮件锁定 MAPI 后台打印程序时存储已关闭的情况下一条消息的锁定的状态。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-115">The locked state of a message does not have to be persistent in case the store is shut down while the message is locked by the MAPI spooler.</span></span> 
  
<span data-ttu-id="a1fa8-116">无论是否 MAPI 后台处理程序已锁定的传出邮件，消息存储提供程序不应在传出的消息队列，要打开以进行编写允许一条消息。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-116">Regardless of whether the MAPI spooler has locked an outgoing message, the message store provider should not allow a message in the outgoing message queue to be opened for writing.</span></span> <span data-ttu-id="a1fa8-117">如果客户端在带 MAPI_MODIFY 标志的传出邮件上调用[IMSgStore::OpenEntry](imsgstore-openentry.md)方法，呼叫应失败并返回 MAPI_E_SUBMITTED。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-117">If a client calls the [IMSgStore::OpenEntry](imsgstore-openentry.md) method on an outgoing message with the MAPI_MODIFY flag, the call should fail and return MAPI_E_SUBMITTED.</span></span> <span data-ttu-id="a1fa8-118">如果客户端应用程序调用带 MAPI_BEST_ACCESS 标志的传出邮件上**OpenEntry** ，消息存储提供程序应允许到邮件的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-118">If a client application calls **OpenEntry** on an outgoing message with the MAPI_BEST_ACCESS flag, the message store provider should allow read-only access to the message.</span></span> 
  
<span data-ttu-id="a1fa8-119">当一条消息是由 MAPI 后台处理程序时，消息存储提供程序将消息的**PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) 属性设置 SUBMITFLAG_LOCKED。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-119">When a message is to be handled by the MAPI spooler, the message store provider sets the message's **PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) property to SUBMITFLAG_LOCKED.</span></span> <span data-ttu-id="a1fa8-120">SUBMITFLAG_LOCKED 值指示 MAPI 后台处理程序已锁定以供其专用的消息。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-120">The SUBMITFLAG_LOCKED value indicates that the MAPI spooler has locked the message for its exclusive use.</span></span> <span data-ttu-id="a1fa8-121">当邮件需要预处理由传输提供程序注册的一个或多个预处理器函数设置**PR_SUBMIT_FLAGS**，SUBMITFLAG_PREPROCESS 的其他值。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-121">The other value for **PR_SUBMIT_FLAGS**, SUBMITFLAG_PREPROCESS, is set when the message requires preprocessing by one or more preprocessor functions registered by a transport provider.</span></span>
  
<span data-ttu-id="a1fa8-122">下面的过程介绍如何消息存储、 传输和 MAPI 后台处理程序交互作用以便从客户端向一个或多个收件人发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-122">The following procedures describe how the message store, transport, and MAPI spooler interact to send a message from a client to one or more recipients.</span></span> 
  
<span data-ttu-id="a1fa8-123">客户端应用程序调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-123">The client application calls the [IMessage::SubmitMessage](imessage-submitmessage.md) method.</span></span> <span data-ttu-id="a1fa8-124">在**SubmitMessage**，消息存储提供程序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-124">In **SubmitMessage**, the message store provider does the following:</span></span>
  
1. <span data-ttu-id="a1fa8-125">调用[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-125">Calls [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md).</span></span> <span data-ttu-id="a1fa8-126">如果 MAPI 返回一个错误，消息存储提供程序将返回到客户端的错误。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-126">If MAPI returns an error, the message store provider returns that error to the client.</span></span>
    
2. <span data-ttu-id="a1fa8-127">设置消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中位 MSGFLAG_SUBMIT。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-127">Sets the MSGFLAG_SUBMIT bit in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message.</span></span>
    
3. <span data-ttu-id="a1fa8-128">确保有是**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性收件人表中的列，并将其设置为 FALSE 以指示的任何传输尚未假定负责传输消息。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-128">Ensures that there is a column for the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property in the recipient table and sets it to FALSE to indicate that no transport has yet assumed responsibility for transmitting the message.</span></span>
    
4. <span data-ttu-id="a1fa8-129">设置日期和时间发起的**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-129">Sets the date and time of origination in the **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) property.</span></span>
    
5. <span data-ttu-id="a1fa8-130">调用[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-130">Calls [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md) to do the following:</span></span> 
    
    1. <span data-ttu-id="a1fa8-131">展开所有个人通讯组列表和自定义收件人并将所有更改的显示名称替换其原始名称。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-131">Expand all personal distribution lists and custom recipients and replace all changed display names with their original names.</span></span>
        
    2. <span data-ttu-id="a1fa8-132">删除重复的名称。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-132">Remove duplicate names.</span></span>
        
    3. <span data-ttu-id="a1fa8-133">检查任何所需预处理，然后，如果预处理是必需的设置 NEEDS_PREPROCESSING 标志和供 MAPI 的**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-133">Check for any required preprocessing and, if preprocessing is required, set the NEEDS_PREPROCESSING flag and the **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) property, which is reserved for MAPI.</span></span> 
        
    4. <span data-ttu-id="a1fa8-134">如果与传输紧密耦合的消息存储，它无法处理的所有收件人，则设置 NEEDS_SPOOLER 标志。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-134">Set the NEEDS_SPOOLER flag if the message store is tightly coupled with a transport and it cannot handle all of the recipients.</span></span> 
    
6. <span data-ttu-id="a1fa8-135">如果设置了 NEEDS_PREPROCESSING 邮件标志，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-135">Performs the following tasks if the NEEDS_PREPROCESSING message flag is set:</span></span>
    
    1. <span data-ttu-id="a1fa8-136">与**PR_SUBMIT_FLAGS**属性中设置的 SUBMITFLAG_PREPROCESS 位置于传出队列消息。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-136">Puts the message in the outgoing queue with the SUBMITFLAG_PREPROCESS bit set in the **PR_SUBMIT_FLAGS** property.</span></span> 
        
    2. <span data-ttu-id="a1fa8-137">通知队列已更改 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-137">Notifies the MAPI spooler that the queue has changed.</span></span>
        
    3. <span data-ttu-id="a1fa8-138">返回控件添加到客户端，并在 MAPI 后台处理程序的邮件流继续。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-138">Returns control to the client, and message flow continues in the MAPI spooler.</span></span> <span data-ttu-id="a1fa8-139">MAPI 后台处理程序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-139">The MAPI spooler performs the following tasks:</span></span> 
    
       1. <span data-ttu-id="a1fa8-140">通过调用[IMsgStore::SetLockState](imsgstore-setlockstate.md)锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-140">Locks the message by calling [IMsgStore::SetLockState](imsgstore-setlockstate.md).</span></span>
            
       2. <span data-ttu-id="a1fa8-141">执行所需的预处理通过调用的所有注册的顺序预处理函数。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-141">Performs the needed preprocessing by calling all of the preprocessing functions in the order of registration.</span></span> <span data-ttu-id="a1fa8-142">传输提供程序调用[IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md)注册预处理函数。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-142">Transport providers call [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) to register preprocessing functions.</span></span> 
            
       3. <span data-ttu-id="a1fa8-143">在打开的邮件，以指示邮件[IMessage::SubmitMessage](imessage-submitmessage.md)存储该预处理的呼叫即告完成。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-143">Calls [IMessage::SubmitMessage](imessage-submitmessage.md) on the open message to indicate to the message store that preprocessing is complete.</span></span> 
    
<span data-ttu-id="a1fa8-144">如果没有任何预处理，或出现预处理和 MAPI 后台处理程序调用**SubmitMessage**，消息存储提供程序执行以下客户端过程中：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-144">If there was no preprocessing, or there was preprocessing and the MAPI spooler called **SubmitMessage**, the message store provider does the following in the client process:</span></span> 
  
- <span data-ttu-id="a1fa8-145">如果消息存储紧密耦合到传输和从[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)返回 NEEDS_SPOOLER 标志，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-145">Performs the following tasks if the message store is tightly coupled to a transport and the NEEDS_SPOOLER flag was returned from [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md):</span></span>
    
   - <span data-ttu-id="a1fa8-146">处理它可以处理任何收件人。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-146">Handles any recipients that it can handle.</span></span>
    
   - <span data-ttu-id="a1fa8-147">为它处理任何收件人将**PR_RESPONSIBILITY**属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-147">Sets the **PR_RESPONSIBILITY** property to TRUE for any recipients that it handles.</span></span> 
    
   - <span data-ttu-id="a1fa8-148">如果此紧密耦合的存储和传输到已知所有收件人，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-148">Performs the following tasks if all recipients are known to this tightly coupled store and transport:</span></span> 
    
     - <span data-ttu-id="a1fa8-149">如果已预处理邮件或消息存储提供程序希望进行完整的消息处理 MAPI 后台处理程序，调用[IMAPISupport::CompleteMsg](imapisupport-completemsg.md) 。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-149">Calls [IMAPISupport::CompleteMsg](imapisupport-completemsg.md) if the message was preprocessed or the message store provider wants the MAPI spooler to complete message processing.</span></span> <span data-ttu-id="a1fa8-150">邮件流继续 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-150">Message flow continues with the MAPI spooler.</span></span> 
    
     - <span data-ttu-id="a1fa8-151">如果已不预处理邮件或消息存储提供程序不需要 MAPI 后台处理程序完成消息处理，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-151">Performs the following tasks if the message was not preprocessed or the message store provider does not want the MAPI spooler to complete message processing:</span></span>
    
       1. <span data-ttu-id="a1fa8-152">如果**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性中的项标识符标识的文件夹的邮件的副本设置。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-152">Copies the message to the folder identified by the entry identifier in the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property, if set.</span></span>
            
       2. <span data-ttu-id="a1fa8-153">如果**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性已设置为 TRUE，则删除邮件。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-153">Deletes the message if the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property has been set to TRUE.</span></span>
            
       3. <span data-ttu-id="a1fa8-154">如果它已被锁定，解除锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-154">Unlocks the message if it is locked.</span></span>
            
       4. <span data-ttu-id="a1fa8-155">返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-155">Returns to the client.</span></span> <span data-ttu-id="a1fa8-156">邮件流已完成。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-156">Message flow is complete.</span></span>
    
  - <span data-ttu-id="a1fa8-157">如果邮件已预处理或提供程序希望 MAPI 后台处理程序完成消息处理，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-157">Performs the following tasks if the message was preprocessed or the provider wants the MAPI spooler to complete message processing:</span></span>
    
    1. <span data-ttu-id="a1fa8-158">调用[IMAPISupport::CompleteMsg](imapisupport-completemsg.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-158">Calls [IMAPISupport::CompleteMsg](imapisupport-completemsg.md).</span></span> 
          
    2. <span data-ttu-id="a1fa8-159">继续使用 MAPI 后台处理程序的邮件流。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-159">Continues message flow with the MAPI spooler.</span></span> <span data-ttu-id="a1fa8-160">有关详细信息，请参阅[发送的邮件： MAPI 后台处理程序任务](sending-messages-mapi-spooler-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-160">For more information, see [Sending Messages: MAPI Spooler Tasks](sending-messages-mapi-spooler-tasks.md).</span></span>
    
  - <span data-ttu-id="a1fa8-161">如果邮件已不预处理或提供程序不需要完成消息处理后台处理程序，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-161">Performs the following tasks if the message was not preprocessed or the provider does not want the spooler to complete message processing:</span></span>
    
    1. <span data-ttu-id="a1fa8-162">如果由**PR_SENTMAIL_ENTRYID**属性中的项标识符标识的文件夹的邮件设置的副本。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-162">Copies the message to the folder identified by the entry identifier in the **PR_SENTMAIL_ENTRYID** property, if set.</span></span> 
        
    2. <span data-ttu-id="a1fa8-163">如果**PR_DELETE_AFTER_SUBMIT**属性已设置为 TRUE，则删除邮件。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-163">Deletes the message if the **PR_DELETE_AFTER_SUBMIT** property has been set to TRUE.</span></span> 
        
    3. <span data-ttu-id="a1fa8-164">如果它已被锁定，解除锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-164">Unlocks the message if it is locked.</span></span> 
        
    4. <span data-ttu-id="a1fa8-165">返回到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-165">Returns to the caller.</span></span> <span data-ttu-id="a1fa8-166">邮件流已完成。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-166">Message flow is complete.</span></span>
    
- <span data-ttu-id="a1fa8-167">如果传输不紧密耦合的消息存储，并非所有收件人已已知的消息存储库，或者 NEEDS_SPOOLER 标志设置，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a1fa8-167">Performs the following tasks if the message store is not tightly coupled to a transport, not all of the recipients were known to the message store, or the NEEDS_SPOOLER flag is set:</span></span>
    
  1. <span data-ttu-id="a1fa8-168">邮件未**PR_SUBMIT_FLAGS**属性中设置 SUBMITFLAG_PREPROCESS 位置于传出队列中。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-168">Puts the message in the outgoing queue without setting the SUBMITFLAG_PREPROCESS bit in the **PR_SUBMIT_FLAGS** property.</span></span> 
    
  2. <span data-ttu-id="a1fa8-169">通知传出队列已更改的生成表通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-169">Notifies the MAPI spooler that the outgoing queue has changed by generating a table notification.</span></span> 
    
  3. <span data-ttu-id="a1fa8-170">返回到客户端和邮件流继续执行一组由 MAPI 后台处理程序执行的任务。</span><span class="sxs-lookup"><span data-stu-id="a1fa8-170">Returns to the client, and message flow continues with a set of tasks performed by the MAPI spooler.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a1fa8-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1fa8-171">See also</span></span>

- [<span data-ttu-id="a1fa8-172">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="a1fa8-172">Message Store Features</span></span>](message-store-features.md)

