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
# <a name="resending-an-undelivered-message"></a>重新发送未送达的邮件
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传输提供程序在无法成功传递已提交的邮件时发送未送达报告 (NDR)。 无论用户是否可以尝试重新发送未送达的邮件, 都由客户端决定。 如果您支持重新发送邮件, 则可以使用 MAPI 提供的表单或实现自己的表单。 MAPI 表单显示失败收件人的姓名和传递失败的原因 (如有可能), 并包含一个按钮, 当选择该按钮时, 用户可以重新发送邮件。
  
收到重发的邮件时, 它应与原始邮件完全一样。 收件人应该无法区分在第一次传输时传递的邮件, 也不能区分后续尝试。 对此邮件的回复应完全按照第一次成功发送邮件的方式运行。
  
### <a name="to-resend-an-undelivered-message"></a>重新发送未送达的邮件
  
1. 调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)以创建新邮件。 
    
2. 从原始邮件中复制所有属性, 但不包括 * * PR_MESSAGE_RECIPIENTS * * ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性以及**PR_SENDER**和**PR_SENT_REPRESENTING**属性。 对以下属性进行修改: 
    
   - 将**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 设置为报表的 * * PR_ORIG_MESSAGE_CLASS * * ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md)) 属性。
    
   - 在**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_RESEND 标志。
    
   - 将**PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 设置为原始邮件的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
   - 对于每个收件人, 请在**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性中设置 MAPI_SUBMITTED。 
    
   - 复制每个失败的收件人。 将复制的收件人的**PR_RECIPIENT_TYPE**属性更改为 MAPI_P1。 因此, 对于每个失败的收件人, 收件人表中现在有两个条目: 一个将**PR_RECIPIENT_TYPE**设置为其原始值, 另一个使用**PR_RECIPIENT_TYPE**设置为 MAPI_P1。 
    
3. 如果需要, 请调用[ScCreateConversationIndex](sccreateconversationindex.md)以设置会话跟踪。 
    
4. 调用新邮件的[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法以更新收件人列表。 
    
5. 调用[IMessage:: SubmitMessage](imessage-submitmessage.md)以保存并发送新邮件。 
    

