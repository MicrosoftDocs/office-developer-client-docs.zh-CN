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
# <a name="resending-an-undelivered-message"></a>重新发送未送达的邮件
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果传输提供程序无法成功传递已提交 (，) NDR 发送未送达报告。 用户能否尝试重新发送这些未送达的邮件取决于客户端。 如果支持重新发送邮件，可以使用 MAPI 提供的窗体，也可以实现自己的窗体。 MAPI 窗体显示失败收件人的姓名以及传递失败的原因（如果可能）并包括一个按钮，选中该按钮后，用户可以重新发送邮件。
  
收到重新发送的邮件时，看起来应该与原始邮件完全相同。 收件人应无法区分第一次尝试传输时传递的邮件还是后续尝试传递的邮件。 对此消息的答复应该与邮件第一次成功发送一样。
  
### <a name="to-resend-an-undelivered-message"></a>重新发送未送达邮件
  
1. 调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 以创建新邮件。 
    
2. 从原始邮件复制所有属性，不包括 ** PR_MESSAGE_RECIPIENTS ** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性以及 **PR_SENDER** 和 **PR_SENT_REPRESENTING** 属性。 进行以下属性修改： 
    
   - 将 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 设置为报表的 **PR_ORIG_MESSAGE_CLASS ** ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) 属性。
    
   - 设置 MSGFLAG_RESEND [PidTagMessageFlags](pidtagmessageflags-canonical-property.md) PR_MESSAGE_FLAGS (标记) 标记。 
    
   - 将 **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 设置为原始邮件的 PR_ENTRYID **(** [PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
   - 对于每个收件人，在 MAPI_SUBMITTED [PidTagRecipientType](pidtagrecipienttype-canonical-property.md) **PR_RECIPIENT_TYPE (** 设置) 属性。 
    
   - 复制每个失败的收件人。 将 **PR_RECIPIENT_TYPE** 收件人的收件人属性更改为MAPI_P1。 因此，对于每个失败的收件人，收件人表中现在存在两个条目：一个PR_RECIPIENT_TYPE设置为其原始值，另一个条目的 PR_RECIPIENT_TYPE **设置为** MAPI_P1。 
    
3. 如果需要 [，请调用 ScCreateConversationIndex](sccreateconversationindex.md) 设置对话跟踪。 
    
4. 调用新邮件的 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法来更新收件人列表。 
    
5. 调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 以保存和发送新邮件。 
    

