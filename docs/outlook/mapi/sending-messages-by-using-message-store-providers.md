---
title: 使用邮件存储提供程序发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7632d784-00d8-48fd-a73b-73778efbef7f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b34714a230adb44417624d149d34ed6a14a2dfa5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437607"
---
# <a name="sending-messages-by-using-message-store-providers"></a><span data-ttu-id="c7c6a-103">使用邮件存储提供程序发送邮件</span><span class="sxs-lookup"><span data-stu-id="c7c6a-103">Sending messages by using message store providers</span></span>

<span data-ttu-id="c7c6a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7c6a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7c6a-105">邮件存储提供程序不需要支持传出邮件 (，即客户端应用程序能够使用邮件存储提供程序将邮件) 。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-105">Message store providers are not required to support outgoing message submissions (that is, the ability for client applications to use the message store provider to send messages).</span></span> <span data-ttu-id="c7c6a-106">客户端应用程序在发送邮件时必须使用邮件存储，因为邮件数据必须存储在用户完成撰写邮件到 MAPI 后台处理程序将邮件提交给传输提供程序以提交到基础邮件系统之间的某位置。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-106">Client applications need to use a message store while sending messages, because the message's data must be stored somewhere between the time that the user is finished composing it and the time that the MAPI spooler gives the message to a transport provider for submission to the underlying messaging system.</span></span> <span data-ttu-id="c7c6a-107">如果邮件存储提供程序不支持传出邮件提交，则不能用作默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-107">If your message store provider does not support outgoing message submissions, it cannot be used as the default message store.</span></span>
  
<span data-ttu-id="c7c6a-108">若要支持发送邮件，邮件存储提供程序必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-108">To support sending messages, your message store provider must do the following:</span></span>
  
- <span data-ttu-id="c7c6a-109">实现传出邮件队列。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-109">Implement an outgoing message queue.</span></span>
    
- <span data-ttu-id="c7c6a-110">对在 [邮件存储中创建的邮件对象支持 IMessage：：SubmitMessage](imessage-submitmessage.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-110">Support the [IMessage::SubmitMessage](imessage-submitmessage.md) method on message objects created in the message store.</span></span> 
    
- <span data-ttu-id="c7c6a-111">支持特定于 MAPI 后台处理程序的 **IMsgStore** 方法：IMsgStore：：FinishedMsg、IMsgStore：：GetOutgoingQueue、IMsgStore：：NotifyNewMail 和 [IMsgStore：：SetLockState](imsgstore-setlockstate.md)。 [](imsgstore-finishedmsg.md) [](imsgstore-getoutgoingqueue.md) [](imsgstore-notifynewmail.md)</span><span class="sxs-lookup"><span data-stu-id="c7c6a-111">Support the **IMsgStore** methods that are specific to the MAPI spooler: [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md), [IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md), [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md), and [IMsgStore::SetLockState](imsgstore-setlockstate.md).</span></span>
    
<span data-ttu-id="c7c6a-112">**SetLockState** 方法对于 MAPI 后台处理程序和客户端之间的正确互操作非常重要。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-112">The **SetLockState** method is important for proper interoperation between the MAPI spooler and clients.</span></span> <span data-ttu-id="c7c6a-113">当 MAPI 后台处理程序对传出邮件调用 **SetLockState** 时，邮件存储提供程序不得允许客户端打开该邮件。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-113">When the MAPI spooler calls **SetLockState** on an outgoing message, the message store provider must not let clients open the message.</span></span> <span data-ttu-id="c7c6a-114">如果客户端确实尝试打开 MAPI 后台处理程序锁定的邮件，则邮件存储提供程序应返回MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-114">If a client does try to open a message that is locked by the MAPI spooler, the message store provider should return MAPI_E_NO_ACCESS.</span></span> <span data-ttu-id="c7c6a-115">当 MAPI 后台处理程序锁定邮件时，如果存储关闭，则邮件的锁定状态无需是永久性的。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-115">The locked state of a message does not have to be persistent in case the store is shut down while the message is locked by the MAPI spooler.</span></span> 
  
<span data-ttu-id="c7c6a-116">无论 MAPI 后台处理程序是否已锁定传出邮件，邮件存储提供程序都不应允许打开传出邮件队列中的邮件进行写入。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-116">Regardless of whether the MAPI spooler has locked an outgoing message, the message store provider should not allow a message in the outgoing message queue to be opened for writing.</span></span> <span data-ttu-id="c7c6a-117">如果客户端对具有 MAPI_MODIFY 标志的传出邮件调用 [IMSgStore：：OpenEntry](imsgstore-openentry.md) 方法，则调用应失败并返回MAPI_E_SUBMITTED。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-117">If a client calls the [IMSgStore::OpenEntry](imsgstore-openentry.md) method on an outgoing message with the MAPI_MODIFY flag, the call should fail and return MAPI_E_SUBMITTED.</span></span> <span data-ttu-id="c7c6a-118">如果客户端应用程序对具有 MAPI_BEST_ACCESS 标志的传出邮件调用 **OpenEntry，** 则邮件存储提供程序应允许对邮件进行只读访问。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-118">If a client application calls **OpenEntry** on an outgoing message with the MAPI_BEST_ACCESS flag, the message store provider should allow read-only access to the message.</span></span> 
  
<span data-ttu-id="c7c6a-119">当 MAPI 后台处理程序处理邮件时，邮件存储提供程序将邮件的 **PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) 属性SUBMITFLAG_LOCKED。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-119">When a message is to be handled by the MAPI spooler, the message store provider sets the message's **PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) property to SUBMITFLAG_LOCKED.</span></span> <span data-ttu-id="c7c6a-120">the SUBMITFLAG_LOCKED value indicates that the MAPI spooler has locked the message for its exclusive use.</span><span class="sxs-lookup"><span data-stu-id="c7c6a-120">The SUBMITFLAG_LOCKED value indicates that the MAPI spooler has locked the message for its exclusive use.</span></span> <span data-ttu-id="c7c6a-121">当邮件需要由 **传输** PR_SUBMIT_FLAGS注册的一个或多个预处理器函数进行预处理时，将设置 PR_SUBMIT_FLAGS 的另一个值（即 SUBMITFLAG_PREPROCESS）。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-121">The other value for **PR_SUBMIT_FLAGS**, SUBMITFLAG_PREPROCESS, is set when the message requires preprocessing by one or more preprocessor functions registered by a transport provider.</span></span>
  
<span data-ttu-id="c7c6a-122">以下过程介绍邮件存储、传输和 MAPI 后台处理程序如何交互以将邮件从客户端发送到一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-122">The following procedures describe how the message store, transport, and MAPI spooler interact to send a message from a client to one or more recipients.</span></span> 
  
<span data-ttu-id="c7c6a-123">客户端应用程序调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-123">The client application calls the [IMessage::SubmitMessage](imessage-submitmessage.md) method.</span></span> <span data-ttu-id="c7c6a-124">在 **SubmitMessage** 中，邮件存储提供程序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-124">In **SubmitMessage**, the message store provider does the following:</span></span>
  
1. <span data-ttu-id="c7c6a-125">调用 [IMAPISupport：:P repareSubmit](imapisupport-preparesubmit.md)。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-125">Calls [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md).</span></span> <span data-ttu-id="c7c6a-126">如果 MAPI 返回错误，邮件存储提供程序会向客户端返回该错误。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-126">If MAPI returns an error, the message store provider returns that error to the client.</span></span>
    
2. <span data-ttu-id="c7c6a-127">设置MSGFLAG_SUBMIT [PidTagMessageFlags PR_MESSAGE_FLAGS (PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 中的位。 </span><span class="sxs-lookup"><span data-stu-id="c7c6a-127">Sets the MSGFLAG_SUBMIT bit in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message.</span></span>
    
3. <span data-ttu-id="c7c6a-128">确保收件人表中存在 **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性的列，并设置此属性为 FALSE 以指示尚未对传输邮件承担任何传输责任。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-128">Ensures that there is a column for the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property in the recipient table and sets it to FALSE to indicate that no transport has yet assumed responsibility for transmitting the message.</span></span>
    
4. <span data-ttu-id="c7c6a-129">使用[PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md) PR_CLIENT_SUBMIT_TIME (设置原始) 日期和时间。 </span><span class="sxs-lookup"><span data-stu-id="c7c6a-129">Sets the date and time of origination in the **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) property.</span></span>
    
5. <span data-ttu-id="c7c6a-130">调用 [IMAPISupport：：ExpandRecips](imapisupport-expandrecips.md) 以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-130">Calls [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md) to do the following:</span></span> 
    
    1. <span data-ttu-id="c7c6a-131">展开所有个人通讯组列表和自定义收件人，将所有更改的显示名称替换为其原始名称。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-131">Expand all personal distribution lists and custom recipients and replace all changed display names with their original names.</span></span>
        
    2. <span data-ttu-id="c7c6a-132">删除重复的名称。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-132">Remove duplicate names.</span></span>
        
    3. <span data-ttu-id="c7c6a-133">检查所需的任何预处理，如果需要预处理，请设置 NEEDS_PREPROCESSING 标志和 **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性（为 MAPI 保留）。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-133">Check for any required preprocessing and, if preprocessing is required, set the NEEDS_PREPROCESSING flag and the **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) property, which is reserved for MAPI.</span></span> 
        
    4. <span data-ttu-id="c7c6a-134">如果NEEDS_SPOOLER与传输紧密结合，并且无法处理所有收件人，则设置此标记。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-134">Set the NEEDS_SPOOLER flag if the message store is tightly coupled with a transport and it cannot handle all of the recipients.</span></span> 
    
6. <span data-ttu-id="c7c6a-135">如果设置了邮件NEEDS_PREPROCESSING，则执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-135">Performs the following tasks if the NEEDS_PREPROCESSING message flag is set:</span></span>
    
    1. <span data-ttu-id="c7c6a-136">将邮件放在传出队列中，SUBMITFLAG_PREPROCESS设置 PR_SUBMIT_FLAGS **位。**</span><span class="sxs-lookup"><span data-stu-id="c7c6a-136">Puts the message in the outgoing queue with the SUBMITFLAG_PREPROCESS bit set in the **PR_SUBMIT_FLAGS** property.</span></span> 
        
    2. <span data-ttu-id="c7c6a-137">通知 MAPI 后台处理程序队列已更改。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-137">Notifies the MAPI spooler that the queue has changed.</span></span>
        
    3. <span data-ttu-id="c7c6a-138">将控制权返回给客户端，消息流将继续在 MAPI 后台处理程序中运行。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-138">Returns control to the client, and message flow continues in the MAPI spooler.</span></span> <span data-ttu-id="c7c6a-139">MAPI 后台处理程序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-139">The MAPI spooler performs the following tasks:</span></span> 
    
       1. <span data-ttu-id="c7c6a-140">通过调用 [IMsgStore：：SetLockState 锁定邮件](imsgstore-setlockstate.md)。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-140">Locks the message by calling [IMsgStore::SetLockState](imsgstore-setlockstate.md).</span></span>
            
       2. <span data-ttu-id="c7c6a-141">按注册顺序调用所有预处理函数，执行所需的预处理。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-141">Performs the needed preprocessing by calling all of the preprocessing functions in the order of registration.</span></span> <span data-ttu-id="c7c6a-142">传输提供程序调用 [IMAPISupport：：RegisterPreprocessor](imapisupport-registerpreprocessor.md) 以注册预处理函数。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-142">Transport providers call [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) to register preprocessing functions.</span></span> 
            
       3. <span data-ttu-id="c7c6a-143">对 [打开的邮件调用 IMessage：：SubmitMessage](imessage-submitmessage.md) 以向邮件存储指示预处理已完成。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-143">Calls [IMessage::SubmitMessage](imessage-submitmessage.md) on the open message to indicate to the message store that preprocessing is complete.</span></span> 
    
<span data-ttu-id="c7c6a-144">如果没有预处理，或者存在预处理和名为 **SubmitMessage** 的 MAPI 后台处理程序，邮件存储提供程序将在客户端进程中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-144">If there was no preprocessing, or there was preprocessing and the MAPI spooler called **SubmitMessage**, the message store provider does the following in the client process:</span></span> 
  
- <span data-ttu-id="c7c6a-145">如果邮件存储与传输紧密耦合，并且从 [IMAPISupport：：ExpandRecips](imapisupport-expandrecips.md)返回 NEEDS_SPOOLER，则执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-145">Performs the following tasks if the message store is tightly coupled to a transport and the NEEDS_SPOOLER flag was returned from [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md):</span></span>
    
   - <span data-ttu-id="c7c6a-146">处理它可以处理的任何收件人。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-146">Handles any recipients that it can handle.</span></span>
    
   - <span data-ttu-id="c7c6a-147">将 **PR_RESPONSIBILITY** 处理的任何收件人的属性都为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-147">Sets the **PR_RESPONSIBILITY** property to TRUE for any recipients that it handles.</span></span> 
    
   - <span data-ttu-id="c7c6a-148">如果已知此紧密耦合存储和传输的所有收件人，则执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-148">Performs the following tasks if all recipients are known to this tightly coupled store and transport:</span></span> 
    
     - <span data-ttu-id="c7c6a-149">如果邮件已预处理或邮件存储提供程序希望 MAPI 后台处理程序完成消息处理，则调用[IMAPISupport：：CompleteMsg。](imapisupport-completemsg.md)</span><span class="sxs-lookup"><span data-stu-id="c7c6a-149">Calls [IMAPISupport::CompleteMsg](imapisupport-completemsg.md) if the message was preprocessed or the message store provider wants the MAPI spooler to complete message processing.</span></span> <span data-ttu-id="c7c6a-150">邮件流将继续使用 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-150">Message flow continues with the MAPI spooler.</span></span> 
    
     - <span data-ttu-id="c7c6a-151">如果未预处理邮件或邮件存储提供程序不希望 MAPI 后台处理程序完成邮件处理，则执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-151">Performs the following tasks if the message was not preprocessed or the message store provider does not want the MAPI spooler to complete message processing:</span></span>
    
       1. <span data-ttu-id="c7c6a-152">将邮件复制到[PidTagSentMailEntryId PR_SENTMAIL_ENTRYID (PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 标识的文件夹（如果已设置）。 </span><span class="sxs-lookup"><span data-stu-id="c7c6a-152">Copies the message to the folder identified by the entry identifier in the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property, if set.</span></span>
            
       2. <span data-ttu-id="c7c6a-153">如果[PidTagDeleteAfterSubmit PR_DELETE_AFTER_SUBMIT (PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)属性) 设置为 TRUE，则删除邮件。 </span><span class="sxs-lookup"><span data-stu-id="c7c6a-153">Deletes the message if the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property has been set to TRUE.</span></span>
            
       3. <span data-ttu-id="c7c6a-154">如果邮件被锁定，则解锁邮件。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-154">Unlocks the message if it is locked.</span></span>
            
       4. <span data-ttu-id="c7c6a-155">返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-155">Returns to the client.</span></span> <span data-ttu-id="c7c6a-156">邮件流已完成。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-156">Message flow is complete.</span></span>
    
  - <span data-ttu-id="c7c6a-157">如果邮件已预处理或提供程序希望 MAPI 后台处理程序完成邮件处理，则执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-157">Performs the following tasks if the message was preprocessed or the provider wants the MAPI spooler to complete message processing:</span></span>
    
    1. <span data-ttu-id="c7c6a-158">调用 [IMAPISupport：：CompleteMsg](imapisupport-completemsg.md)。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-158">Calls [IMAPISupport::CompleteMsg](imapisupport-completemsg.md).</span></span> 
          
    2. <span data-ttu-id="c7c6a-159">使用 MAPI 后台处理程序继续消息流。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-159">Continues message flow with the MAPI spooler.</span></span> <span data-ttu-id="c7c6a-160">有关详细信息，请参阅发送邮件 [：MAPI 后台处理程序任务](sending-messages-mapi-spooler-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-160">For more information, see [Sending Messages: MAPI Spooler Tasks](sending-messages-mapi-spooler-tasks.md).</span></span>
    
  - <span data-ttu-id="c7c6a-161">如果未预处理邮件或提供程序不希望后台处理程序完成邮件处理，则执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-161">Performs the following tasks if the message was not preprocessed or the provider does not want the spooler to complete message processing:</span></span>
    
    1. <span data-ttu-id="c7c6a-162">将邮件复制到由 PR_SENTMAIL_ENTRYID 属性中的条目 **标识符标识** 的文件夹（如果已设置）。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-162">Copies the message to the folder identified by the entry identifier in the **PR_SENTMAIL_ENTRYID** property, if set.</span></span> 
        
    2. <span data-ttu-id="c7c6a-163">如果邮件的 PR_DELETE_AFTER_SUBMIT **属性已** 设置为 TRUE，则删除该邮件。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-163">Deletes the message if the **PR_DELETE_AFTER_SUBMIT** property has been set to TRUE.</span></span> 
        
    3. <span data-ttu-id="c7c6a-164">如果邮件被锁定，则解锁邮件。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-164">Unlocks the message if it is locked.</span></span> 
        
    4. <span data-ttu-id="c7c6a-165">返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-165">Returns to the caller.</span></span> <span data-ttu-id="c7c6a-166">邮件流已完成。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-166">Message flow is complete.</span></span>
    
- <span data-ttu-id="c7c6a-167">如果邮件存储未紧密耦合到传输中，并非所有收件人都已知邮件存储，或已设置 NEEDS_SPOOLER 标志，则执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c7c6a-167">Performs the following tasks if the message store is not tightly coupled to a transport, not all of the recipients were known to the message store, or the NEEDS_SPOOLER flag is set:</span></span>
    
  1. <span data-ttu-id="c7c6a-168">将邮件置于传出队列中，而不在 SUBMITFLAG_PREPROCESS 属性中设置 **PR_SUBMIT_FLAGS** 位。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-168">Puts the message in the outgoing queue without setting the SUBMITFLAG_PREPROCESS bit in the **PR_SUBMIT_FLAGS** property.</span></span> 
    
  2. <span data-ttu-id="c7c6a-169">通过生成表通知通知 MAPI 后台处理程序，通知传出队列已更改。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-169">Notifies the MAPI spooler that the outgoing queue has changed by generating a table notification.</span></span> 
    
  3. <span data-ttu-id="c7c6a-170">返回到客户端，邮件流将继续由 MAPI 后台处理程序执行一组任务。</span><span class="sxs-lookup"><span data-stu-id="c7c6a-170">Returns to the client, and message flow continues with a set of tasks performed by the MAPI spooler.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c7c6a-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7c6a-171">See also</span></span>

- [<span data-ttu-id="c7c6a-172">邮件存储功能</span><span class="sxs-lookup"><span data-stu-id="c7c6a-172">Message Store Features</span></span>](message-store-features.md)

