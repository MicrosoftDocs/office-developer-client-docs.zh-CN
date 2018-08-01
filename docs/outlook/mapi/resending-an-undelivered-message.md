---
title: 重新发送未送达的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 71768db3-a107-47c6-8e6b-775e8d40ac36
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4fd0bf5a542e006ec743dbb7fe03d3331875c6d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778623"
---
# <a name="resending-an-undelivered-message"></a><span data-ttu-id="1b197-103">重新发送未送达的邮件</span><span class="sxs-lookup"><span data-stu-id="1b197-103">Resending an undelivered message</span></span>
  
<span data-ttu-id="1b197-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1b197-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1b197-105">传输提供程序时它无法成功传递一条消息，您已提交发送未送达报告 (NDR)。</span><span class="sxs-lookup"><span data-stu-id="1b197-105">A transport provider sends a non-delivery report (NDR) when it cannot successfully deliver a message that you have submitted.</span></span> <span data-ttu-id="1b197-106">由客户端用户可以尝试重新发送这些未送达的消息。</span><span class="sxs-lookup"><span data-stu-id="1b197-106">It is up to the client whether or not users can attempt to resend these undelivered messages.</span></span> <span data-ttu-id="1b197-107">如果您支持重新发送消息，您可以使用 MAPI 提供窗体或实现您自己。</span><span class="sxs-lookup"><span data-stu-id="1b197-107">If you support resending messages, you can either use a form provided by MAPI or implement your own.</span></span> <span data-ttu-id="1b197-108">MAPI 表单如果可能，显示失败的收件人和传递失败的原因的名称，并包括一个按钮，选中时，允许用户重新发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="1b197-108">The MAPI form displays the names of the failed recipients and the reason for the delivery failure, if possible, and includes a button that, when selected, allows a user to resend the message.</span></span>
  
<span data-ttu-id="1b197-109">当收到重发的消息时，它应类似于完全原始邮件。</span><span class="sxs-lookup"><span data-stu-id="1b197-109">When a resent message is received, it should look exactly like the original message.</span></span> <span data-ttu-id="1b197-110">收件人应无法进行区分已在其第一次传输尝试或后续尝试发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="1b197-110">The recipient should be unable to differentiate between a message that was delivered on its first attempt at transmission or a subsequent attempt.</span></span> <span data-ttu-id="1b197-111">就好像邮件已被发送成功第一次，此邮件上的回复应该会正常工作。</span><span class="sxs-lookup"><span data-stu-id="1b197-111">Replies on this message should work exactly as if the message had been sent successfully the first time.</span></span>
  
### <a name="to-resend-an-undelivered-message"></a><span data-ttu-id="1b197-112">重新发送未送达的邮件</span><span class="sxs-lookup"><span data-stu-id="1b197-112">To resend an undelivered message</span></span>
  
1. <span data-ttu-id="1b197-113">调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="1b197-113">Call [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) to create a new message.</span></span> 
    
2. <span data-ttu-id="1b197-114">从原始邮件中，复制的所有属性不包括 * * PR_MESSAGE_RECIPIENTS * * ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性，以及**PR_SENDER**和**PR_SENT_REPRESENTING**属性。</span><span class="sxs-lookup"><span data-stu-id="1b197-114">Copy all of the properties from the original message, excluding the ** PR_MESSAGE_RECIPIENTS ** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property, and the **PR_SENDER** and **PR_SENT_REPRESENTING** properties.</span></span> <span data-ttu-id="1b197-115">进行以下属性修改：</span><span class="sxs-lookup"><span data-stu-id="1b197-115">Make the following property modifications:</span></span> 
    
   - <span data-ttu-id="1b197-116">将**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 设置为报表的 * * PR_ORIG_MESSAGE_CLASS * * ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1b197-116">Set **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) to the report's **PR_ORIG_MESSAGE_CLASS ** ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="1b197-117">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_RESEND 标志。</span><span class="sxs-lookup"><span data-stu-id="1b197-117">Set the MSGFLAG_RESEND flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="1b197-118">将**PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 设置为原始消息的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1b197-118">Set **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) to the original message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="1b197-119">对于每个收件人， **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性中设置 MAPI_SUBMITTED。</span><span class="sxs-lookup"><span data-stu-id="1b197-119">For each recipient, set MAPI_SUBMITTED in the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property.</span></span> 
    
   - <span data-ttu-id="1b197-120">重复的每个失败的收件人。</span><span class="sxs-lookup"><span data-stu-id="1b197-120">Duplicate each failed recipient.</span></span> <span data-ttu-id="1b197-121">更改为 MAPI_P1 重复收件人**PR_RECIPIENT_TYPE**属性。</span><span class="sxs-lookup"><span data-stu-id="1b197-121">Change the **PR_RECIPIENT_TYPE** property for the duplicated recipient to MAPI_P1.</span></span> <span data-ttu-id="1b197-122">因此，每个失败收件人现在有两个条目收件人表中： 与**PR_RECIPIENT_TYPE**设置为其原始值，另一种具有**PR_RECIPIENT_TYPE**设置为 MAPI_P1。</span><span class="sxs-lookup"><span data-stu-id="1b197-122">Therefore, for each failed recipient there are now two entries in the recipient table: one with **PR_RECIPIENT_TYPE** set to its original value and the other with **PR_RECIPIENT_TYPE** set to MAPI_P1.</span></span> 
    
3. <span data-ttu-id="1b197-123">调用[ScCreateConversationIndex](sccreateconversationindex.md)设置跟踪如果需要的对话。</span><span class="sxs-lookup"><span data-stu-id="1b197-123">Call [ScCreateConversationIndex](sccreateconversationindex.md) to set up conversation tracking if desired.</span></span> 
    
4. <span data-ttu-id="1b197-124">调用新邮件的[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法更新的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="1b197-124">Call the new message's [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method to update the recipient list.</span></span> 
    
5. <span data-ttu-id="1b197-125">调用[IMessage::SubmitMessage](imessage-submitmessage.md)以保存并发送新邮件。</span><span class="sxs-lookup"><span data-stu-id="1b197-125">Call [IMessage::SubmitMessage](imessage-submitmessage.md) to save and send the new message.</span></span> 
    

