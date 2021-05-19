---
title: 重新发送未送达的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 71768db3-a107-47c6-8e6b-775e8d40ac36
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ddd0c1419531b0822bb98df51f47e12e63dcf242
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432665"
---
# <a name="resending-an-undelivered-message"></a><span data-ttu-id="3dc48-103">重新发送未送达的邮件</span><span class="sxs-lookup"><span data-stu-id="3dc48-103">Resending an undelivered message</span></span>
  
<span data-ttu-id="3dc48-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3dc48-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3dc48-105">如果传输提供程序无法成功传递已提交 (，) NDR 发送未送达报告。</span><span class="sxs-lookup"><span data-stu-id="3dc48-105">A transport provider sends a non-delivery report (NDR) when it cannot successfully deliver a message that you have submitted.</span></span> <span data-ttu-id="3dc48-106">用户能否尝试重新发送这些未送达的邮件取决于客户端。</span><span class="sxs-lookup"><span data-stu-id="3dc48-106">It is up to the client whether or not users can attempt to resend these undelivered messages.</span></span> <span data-ttu-id="3dc48-107">如果支持重新发送邮件，可以使用 MAPI 提供的窗体，也可以实现自己的窗体。</span><span class="sxs-lookup"><span data-stu-id="3dc48-107">If you support resending messages, you can either use a form provided by MAPI or implement your own.</span></span> <span data-ttu-id="3dc48-108">MAPI 窗体显示失败收件人的姓名以及传递失败的原因（如果可能）并包括一个按钮，选中该按钮后，用户可以重新发送邮件。</span><span class="sxs-lookup"><span data-stu-id="3dc48-108">The MAPI form displays the names of the failed recipients and the reason for the delivery failure, if possible, and includes a button that, when selected, allows a user to resend the message.</span></span>
  
<span data-ttu-id="3dc48-109">收到重新发送的邮件时，看起来应该与原始邮件完全相同。</span><span class="sxs-lookup"><span data-stu-id="3dc48-109">When a resent message is received, it should look exactly like the original message.</span></span> <span data-ttu-id="3dc48-110">收件人应无法区分第一次尝试传输时传递的邮件还是后续尝试传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="3dc48-110">The recipient should be unable to differentiate between a message that was delivered on its first attempt at transmission or a subsequent attempt.</span></span> <span data-ttu-id="3dc48-111">对此消息的答复应该与邮件第一次成功发送一样。</span><span class="sxs-lookup"><span data-stu-id="3dc48-111">Replies on this message should work exactly as if the message had been sent successfully the first time.</span></span>
  
### <a name="to-resend-an-undelivered-message"></a><span data-ttu-id="3dc48-112">重新发送未送达邮件</span><span class="sxs-lookup"><span data-stu-id="3dc48-112">To resend an undelivered message</span></span>
  
1. <span data-ttu-id="3dc48-113">调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 以创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="3dc48-113">Call [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) to create a new message.</span></span> 
    
2. <span data-ttu-id="3dc48-114">从原始邮件复制所有属性，不包括 \*\* PR_MESSAGE_RECIPIENTS \*\* ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性以及 **PR_SENDER** 和 **PR_SENT_REPRESENTING** 属性。</span><span class="sxs-lookup"><span data-stu-id="3dc48-114">Copy all of the properties from the original message, excluding the \*\* PR_MESSAGE_RECIPIENTS \*\* ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property, and the **PR_SENDER** and **PR_SENT_REPRESENTING** properties.</span></span> <span data-ttu-id="3dc48-115">进行以下属性修改：</span><span class="sxs-lookup"><span data-stu-id="3dc48-115">Make the following property modifications:</span></span> 
    
   - <span data-ttu-id="3dc48-116">将 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 设置为报表的 \*\*PR_ORIG_MESSAGE_CLASS \*\* ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3dc48-116">Set **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) to the report's \*\*PR_ORIG_MESSAGE_CLASS \*\* ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="3dc48-117">设置 MSGFLAG_RESEND [PidTagMessageFlags](pidtagmessageflags-canonical-property.md) PR_MESSAGE_FLAGS (标记) 标记。 </span><span class="sxs-lookup"><span data-stu-id="3dc48-117">Set the MSGFLAG_RESEND flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="3dc48-118">将 **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 设置为原始邮件的 PR_ENTRYID **(** [PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3dc48-118">Set **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) to the original message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="3dc48-119">对于每个收件人，在 MAPI_SUBMITTED [PidTagRecipientType](pidtagrecipienttype-canonical-property.md) **PR_RECIPIENT_TYPE (** 设置) 属性。</span><span class="sxs-lookup"><span data-stu-id="3dc48-119">For each recipient, set MAPI_SUBMITTED in the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property.</span></span> 
    
   - <span data-ttu-id="3dc48-120">复制每个失败的收件人。</span><span class="sxs-lookup"><span data-stu-id="3dc48-120">Duplicate each failed recipient.</span></span> <span data-ttu-id="3dc48-121">将 **PR_RECIPIENT_TYPE** 收件人的收件人属性更改为MAPI_P1。</span><span class="sxs-lookup"><span data-stu-id="3dc48-121">Change the **PR_RECIPIENT_TYPE** property for the duplicated recipient to MAPI_P1.</span></span> <span data-ttu-id="3dc48-122">因此，对于每个失败的收件人，收件人表中现在存在两个条目：一个PR_RECIPIENT_TYPE设置为其原始值，另一个条目的 PR_RECIPIENT_TYPE **设置为** MAPI_P1。</span><span class="sxs-lookup"><span data-stu-id="3dc48-122">Therefore, for each failed recipient there are now two entries in the recipient table: one with **PR_RECIPIENT_TYPE** set to its original value and the other with **PR_RECIPIENT_TYPE** set to MAPI_P1.</span></span> 
    
3. <span data-ttu-id="3dc48-123">如果需要 [，请调用 ScCreateConversationIndex](sccreateconversationindex.md) 设置对话跟踪。</span><span class="sxs-lookup"><span data-stu-id="3dc48-123">Call [ScCreateConversationIndex](sccreateconversationindex.md) to set up conversation tracking if desired.</span></span> 
    
4. <span data-ttu-id="3dc48-124">调用新邮件的 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法来更新收件人列表。</span><span class="sxs-lookup"><span data-stu-id="3dc48-124">Call the new message's [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method to update the recipient list.</span></span> 
    
5. <span data-ttu-id="3dc48-125">调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 以保存和发送新邮件。</span><span class="sxs-lookup"><span data-stu-id="3dc48-125">Call [IMessage::SubmitMessage](imessage-submitmessage.md) to save and send the new message.</span></span> 
    

