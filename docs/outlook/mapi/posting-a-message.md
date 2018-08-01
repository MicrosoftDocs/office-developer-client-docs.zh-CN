---
title: 发布一条消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc3e1546-e58b-413f-82d7-4efeb86b0000
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 33bf6780979ee25739abf93d89744e1517363c63
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778561"
---
# <a name="posting-a-message"></a>发布一条消息

**适用于**： Outlook 
  
发送一条消息是类似于发送一条消息。 主要区别是目标。 而不是正在跨一个或多个邮件系统定向到一个或多个收件人，已发布的消息仍保留在当前消息存储的文件夹中。
  
### <a name="to-post-a-message"></a>若要发布消息
  
1. 通过调用[IMsgStore::OpenEntry](imsgstore-openentry.md)打开目标文件夹。 如果目标文件夹收件箱，找到要传递给**OpenEntry**通过调用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)的项标识符。 
    
2. 调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)创建邮件。 
    
3. 呼叫消息的[IMAPIProp::SetProps](imapiprop-setprops.md)方法，以便设置： 
    
   - **PidTagMessageFlags** ( [PR_MESSAGE_FLAGS](pidtagmessageflags-canonical-property.md)) 属性中 MSGFLAG_READ 标志。
    
   - **PR_SENDER**属性。 
    
   - **PR_SENT_REPRESENTING**属性。 
    
   - **PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) 属性中。
    
   - **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。
    
   - **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性中。
    
   - **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性中。
    
   - 所需的邮件类的任何属性。
    
4. 调用消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以保存邮件。 
    
5. 如有必要，创建附件，设置其属性，并将其保存。 有关将附件添加到邮件的详细信息，请参阅[创建邮件附件](creating-a-message-attachment.md)。
    
6. 调用**IMessage::SaveChanges**保存邮件。 此时将显示在内容中的目标文件夹。 
    
请注意，未创建收件人列表。 相反，您可以设置通常设置为已发送的邮件传输提供程序的多个属性。 
  
如果您想要让其出现在内容表中的可见文件夹之前间歇性保存一条消息，而是在隐藏的文件夹，如 IPM 子树的根文件夹中创建它，并将其移动到目标文件夹。 
  

