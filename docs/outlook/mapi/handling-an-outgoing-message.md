---
title: 处理的传出邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f40c2e0b-1a35-4901-868f-af6c191c921e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3f3330c132abdf35d0e4f67775c03f7d2e9fcc76
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563987"
---
# <a name="handling-an-outgoing-message"></a>处理的传出邮件

**适用于**： Outlook 2013 |Outlook 2016 
  
传出 message 是一条消息，可以跨一个或多个邮件系统发送到一个或多个收件人或发送到的文件夹中的消息存储。
  
## <a name="create-and-send-an-outgoing-message"></a>创建并发送传出邮件
  
1. 打开默认邮件存储区。 有关详细信息，请参阅[打开消息存储](opening-a-message-store.md)并[打开默认的邮件存储](opening-the-default-message-store.md)。
    
2. 打开发件箱文件夹。 有关详细信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用发件箱文件夹的**IMAPIFolder::CreateMessage**方法，以创建新的邮件。 有关详细信息，请参阅[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)，
    
4. 创建具有一个或多个解析的收件人的收件人列表。 有关详细信息，请参阅[创建收件人列表](creating-a-recipient-list.md)。
    
5. （可选） 添加主题。 有关详细信息，请参阅[创建邮件主题](creating-a-message-subject.md)。
    
6. 添加的消息文本。 有关详细信息，请参阅[创建消息文本](creating-message-text.md)。
    
7. 如果消息文本的格式，添加呈现的信息。 有关详细信息，请参阅[为格式文本添加呈现信息](adding-rendering-information-to-formatted-text.md)。
    
8. （可选） 中添加一个或多个附件。 有关详细信息，请参阅[创建邮件附件](creating-a-message-attachment.md)。
    
9. 将其他邮件属性设置为所需然后保存并通过调用**IMessage::SubmitMessage**发送消息。 有关详细信息，请参阅[IMessage::SubmitMessage](imessage-submitmessage.md)。
    
10. 删除已发送的邮件如果**PR\_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性设置为 TRUE 或移动到文件夹它标识**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。 有关详细信息，请参阅[处理发送消息](processing-a-sent-message.md)。
    
如果您希望 intermittantly 发送之前保存邮件、 呼叫消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 有关详细信息，请参阅，[保存邮件](saving-a-message.md)或[发送一条消息](sending-a-message.md)。 
  
## <a name="in-this-section"></a>本节内容

- [创建收件人列表](creating-a-recipient-list.md)： 介绍如何创建收件人列表。
    
- [创建邮件主题](creating-a-message-subject.md)： 介绍如何创建一条消息，可选主题。
    
- [创建消息文本](creating-message-text.md)： 介绍如何创建消息文本。
    
- [为格式文本添加呈现信息](adding-rendering-information-to-formatted-text.md)： 介绍在带格式的文本附件与要在其中呈现。
    
- [创建邮件附件](creating-a-message-attachment.md)： 介绍如何创建附件。
    
- [保存消息](saving-a-message.md)： 介绍了客户端如何保存邮件。
    
- [发送一条消息](sending-a-message.md)： 介绍如何发送一条消息。
    
- [发送邮件的处理](processing-a-sent-message.md)： 介绍如何发送可以处理邮件。
    

