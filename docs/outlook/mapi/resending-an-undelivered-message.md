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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328677"
---
# <a name="resending-an-undelivered-message"></a><span data-ttu-id="c627b-103">重新发送未送达的邮件</span><span class="sxs-lookup"><span data-stu-id="c627b-103">Resending an undelivered message</span></span>
  
<span data-ttu-id="c627b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c627b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c627b-105">传输提供程序在无法成功传递已提交的邮件时发送未送达报告 (NDR)。</span><span class="sxs-lookup"><span data-stu-id="c627b-105">A transport provider sends a non-delivery report (NDR) when it cannot successfully deliver a message that you have submitted.</span></span> <span data-ttu-id="c627b-106">无论用户是否可以尝试重新发送未送达的邮件, 都由客户端决定。</span><span class="sxs-lookup"><span data-stu-id="c627b-106">It is up to the client whether or not users can attempt to resend these undelivered messages.</span></span> <span data-ttu-id="c627b-107">如果您支持重新发送邮件, 则可以使用 MAPI 提供的表单或实现自己的表单。</span><span class="sxs-lookup"><span data-stu-id="c627b-107">If you support resending messages, you can either use a form provided by MAPI or implement your own.</span></span> <span data-ttu-id="c627b-108">MAPI 表单显示失败收件人的姓名和传递失败的原因 (如有可能), 并包含一个按钮, 当选择该按钮时, 用户可以重新发送邮件。</span><span class="sxs-lookup"><span data-stu-id="c627b-108">The MAPI form displays the names of the failed recipients and the reason for the delivery failure, if possible, and includes a button that, when selected, allows a user to resend the message.</span></span>
  
<span data-ttu-id="c627b-109">收到重发的邮件时, 它应与原始邮件完全一样。</span><span class="sxs-lookup"><span data-stu-id="c627b-109">When a resent message is received, it should look exactly like the original message.</span></span> <span data-ttu-id="c627b-110">收件人应该无法区分在第一次传输时传递的邮件, 也不能区分后续尝试。</span><span class="sxs-lookup"><span data-stu-id="c627b-110">The recipient should be unable to differentiate between a message that was delivered on its first attempt at transmission or a subsequent attempt.</span></span> <span data-ttu-id="c627b-111">对此邮件的回复应完全按照第一次成功发送邮件的方式运行。</span><span class="sxs-lookup"><span data-stu-id="c627b-111">Replies on this message should work exactly as if the message had been sent successfully the first time.</span></span>
  
### <a name="to-resend-an-undelivered-message"></a><span data-ttu-id="c627b-112">重新发送未送达的邮件</span><span class="sxs-lookup"><span data-stu-id="c627b-112">To resend an undelivered message</span></span>
  
1. <span data-ttu-id="c627b-113">调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)以创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="c627b-113">Call [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) to create a new message.</span></span> 
    
2. <span data-ttu-id="c627b-114">从原始邮件中复制所有属性, 但不包括 \* \* PR_MESSAGE_RECIPIENTS \* \* ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性以及**PR_SENDER**和**PR_SENT_REPRESENTING**属性。</span><span class="sxs-lookup"><span data-stu-id="c627b-114">Copy all of the properties from the original message, excluding the \*\* PR_MESSAGE_RECIPIENTS \*\* ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property, and the **PR_SENDER** and **PR_SENT_REPRESENTING** properties.</span></span> <span data-ttu-id="c627b-115">对以下属性进行修改:</span><span class="sxs-lookup"><span data-stu-id="c627b-115">Make the following property modifications:</span></span> 
    
   - <span data-ttu-id="c627b-116">将**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 设置为报表的 \* \* PR_ORIG_MESSAGE_CLASS \* \* ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="c627b-116">Set **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) to the report's \*\*PR_ORIG_MESSAGE_CLASS \*\* ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="c627b-117">在**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_RESEND 标志。</span><span class="sxs-lookup"><span data-stu-id="c627b-117">Set the MSGFLAG_RESEND flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="c627b-118">将**PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 设置为原始邮件的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="c627b-118">Set **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) to the original message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="c627b-119">对于每个收件人, 请在**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性中设置 MAPI_SUBMITTED。</span><span class="sxs-lookup"><span data-stu-id="c627b-119">For each recipient, set MAPI_SUBMITTED in the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property.</span></span> 
    
   - <span data-ttu-id="c627b-120">复制每个失败的收件人。</span><span class="sxs-lookup"><span data-stu-id="c627b-120">Duplicate each failed recipient.</span></span> <span data-ttu-id="c627b-121">将复制的收件人的**PR_RECIPIENT_TYPE**属性更改为 MAPI_P1。</span><span class="sxs-lookup"><span data-stu-id="c627b-121">Change the **PR_RECIPIENT_TYPE** property for the duplicated recipient to MAPI_P1.</span></span> <span data-ttu-id="c627b-122">因此, 对于每个失败的收件人, 收件人表中现在有两个条目: 一个将**PR_RECIPIENT_TYPE**设置为其原始值, 另一个使用**PR_RECIPIENT_TYPE**设置为 MAPI_P1。</span><span class="sxs-lookup"><span data-stu-id="c627b-122">Therefore, for each failed recipient there are now two entries in the recipient table: one with **PR_RECIPIENT_TYPE** set to its original value and the other with **PR_RECIPIENT_TYPE** set to MAPI_P1.</span></span> 
    
3. <span data-ttu-id="c627b-123">如果需要, 请调用[ScCreateConversationIndex](sccreateconversationindex.md)以设置会话跟踪。</span><span class="sxs-lookup"><span data-stu-id="c627b-123">Call [ScCreateConversationIndex](sccreateconversationindex.md) to set up conversation tracking if desired.</span></span> 
    
4. <span data-ttu-id="c627b-124">调用新邮件的[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法以更新收件人列表。</span><span class="sxs-lookup"><span data-stu-id="c627b-124">Call the new message's [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method to update the recipient list.</span></span> 
    
5. <span data-ttu-id="c627b-125">调用[IMessage:: SubmitMessage](imessage-submitmessage.md)以保存并发送新邮件。</span><span class="sxs-lookup"><span data-stu-id="c627b-125">Call [IMessage::SubmitMessage](imessage-submitmessage.md) to save and send the new message.</span></span> 
    

