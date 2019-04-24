---
title: 处理待发邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f40c2e0b-1a35-4901-868f-af6c191c921e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 07785ac82c41108b4333b3c370e3d2f5bfd1426a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342803"
---
# <a name="handling-an-outgoing-message"></a>处理待发邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
传出邮件是一封邮件, 可发送给一个或多个邮件系统中的一个或多个收件人, 或投递到邮件存储区中的文件夹。
  
## <a name="create-and-send-an-outgoing-message"></a>创建和发送传出邮件
  
1. 打开默认邮件存储。 有关详细信息, 请参阅[打开邮件存储](opening-a-message-store.md)和[打开默认邮件存储](opening-the-default-message-store.md)。
    
2. 打开 "发件箱" 文件夹。 有关详细信息, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用 "发件箱" 文件夹的**IMAPIFolder:: CreateMessage**方法以创建新邮件。 有关详细信息, 请参阅[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md),
    
4. 创建包含一个或多个解析的收件人的收件人列表。 有关详细信息, 请参阅[创建收件人列表](creating-a-recipient-list.md)。
    
5. (可选) 添加主题。 有关详细信息, 请参阅[创建邮件主题](creating-a-message-subject.md)。
    
6. 添加消息文本。 有关详细信息, 请参阅[创建邮件文本](creating-message-text.md)。
    
7. 如果邮件文本的格式设置, 请添加呈现信息。 有关详细信息, 请参阅[将呈现信息添加到格式化文本](adding-rendering-information-to-formatted-text.md)。
    
8. (可选) 添加一个或多个附件。 有关详细信息, 请参阅[创建邮件附件](creating-a-message-attachment.md)。
    
9. 根据需要设置其他邮件属性, 然后通过调用**IMessage:: SubmitMessage**来保存和发送邮件。 有关详细信息, 请参阅[IMessage:: SubmitMessage](imessage-submitmessage.md)。
    
10. 如果**PR\_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性设置为 TRUE 或将其移动到由**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性标识的文件夹中, 则删除已发送的邮件。 有关详细信息, 请参阅[处理已发送的邮件](processing-a-sent-message.md)。
    
如果要在发送邮件之前 intermittantly 保存邮件, 请调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。 有关详细信息, 请参阅[保存邮件](saving-a-message.md)或[发送邮件](sending-a-message.md)。 
  
## <a name="in-this-section"></a>本节内容

- [创建收件人列表](creating-a-recipient-list.md): 介绍如何创建收件人列表。
    
- [创建邮件主题](creating-a-message-subject.md): 介绍如何为邮件创建可选主题。
    
- [创建邮件文本](creating-message-text.md): 介绍如何创建邮件文本。
    
- [将呈现信息添加到格式化文本](adding-rendering-information-to-formatted-text.md): 说明格式化文本中要呈现附件的位置。
    
- [创建邮件附件](creating-a-message-attachment.md): 介绍如何创建附件。
    
- [保存邮件](saving-a-message.md): 介绍了客户端保存邮件的方式。
    
- [发送邮件](sending-a-message.md): 介绍如何发送邮件。
    
- [处理已发送的邮件](processing-a-sent-message.md): 介绍如何处理已发送的邮件。
    

