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
ms.openlocfilehash: cdb1ef3cf6db2a1b63b68a105867aa6624b80c2c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588893"
---
# <a name="resending-an-undelivered-message"></a>重新发送未送达的邮件
  
**适用于**： Outlook 2013 |Outlook 2016 
  
传输提供程序时它无法成功传递一条消息，您已提交发送未送达报告 (NDR)。 由客户端用户可以尝试重新发送这些未送达的消息。 如果您支持重新发送消息，您可以使用 MAPI 提供窗体或实现您自己。 MAPI 表单如果可能，显示失败的收件人和传递失败的原因的名称，并包括一个按钮，选中时，允许用户重新发送的邮件。
  
当收到重发的消息时，它应类似于完全原始邮件。 收件人应无法进行区分已在其第一次传输尝试或后续尝试发送一条消息。 就好像邮件已被发送成功第一次，此邮件上的回复应该会正常工作。
  
### <a name="to-resend-an-undelivered-message"></a>重新发送未送达的邮件
  
1. 调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)创建新邮件。 
    
2. 从原始邮件中，复制的所有属性不包括 * * PR_MESSAGE_RECIPIENTS * * ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性，以及**PR_SENDER**和**PR_SENT_REPRESENTING**属性。 进行以下属性修改： 
    
   - 将**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 设置为报表的 * * PR_ORIG_MESSAGE_CLASS * * ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) 属性。
    
   - **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_RESEND 标志。
    
   - 将**PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 设置为原始消息的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
   - 对于每个收件人， **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性中设置 MAPI_SUBMITTED。 
    
   - 重复的每个失败的收件人。 更改为 MAPI_P1 重复收件人**PR_RECIPIENT_TYPE**属性。 因此，每个失败收件人现在有两个条目收件人表中： 与**PR_RECIPIENT_TYPE**设置为其原始值，另一种具有**PR_RECIPIENT_TYPE**设置为 MAPI_P1。 
    
3. 调用[ScCreateConversationIndex](sccreateconversationindex.md)设置跟踪如果需要的对话。 
    
4. 调用新邮件的[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法更新的收件人列表。 
    
5. 调用[IMessage::SubmitMessage](imessage-submitmessage.md)以保存并发送新邮件。 
    

