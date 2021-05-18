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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407625"
---
# <a name="handling-an-outgoing-message"></a>处理待发邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
传出邮件是一种可以跨一个或多个邮件系统发送给一个或多个收件人或发送到邮件存储中的文件夹的邮件。
  
## <a name="create-and-send-an-outgoing-message"></a>创建和发送传出邮件
  
1. 打开默认邮件存储。 有关详细信息，请参阅打开[邮件存储和](opening-a-message-store.md)[打开默认邮件存储](opening-the-default-message-store.md)。
    
2. 打开发件箱文件夹。 有关详细信息，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用发件箱文件夹的 **IMAPIFolder：：CreateMessage** 方法来创建新邮件。 有关详细信息，请参阅 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md)、
    
4. 创建包含一个或多个已解析收件人的收件人列表。 有关详细信息，请参阅创建 [收件人列表](creating-a-recipient-list.md)。
    
5. （可选）添加主题。 有关详细信息，请参阅 [创建邮件主题](creating-a-message-subject.md)。
    
6. 添加邮件文本。 有关详细信息，请参阅创建 [消息文本](creating-message-text.md)。
    
7. 如果邮件文本已设置格式，请添加呈现信息。 有关详细信息，请参阅向 [格式化文本添加呈现信息](adding-rendering-information-to-formatted-text.md)。
    
8. （可选）添加一个或多个附件。 有关详细信息，请参阅创建 [邮件附件](creating-a-message-attachment.md)。
    
9. 设置其他邮件属性，然后通过调用 **IMessage：：SubmitMessage 保存并发送邮件**。 有关详细信息，请参阅 [IMessage：：SubmitMessage](imessage-submitmessage.md)。
    
10. 如果 **PR \_ DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性设置为 TRUE 或将其移动到 **由 PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性标识的文件夹，则删除已发送的邮件。 有关详细信息，请参阅处理 [已发送的邮件](processing-a-sent-message.md)。
    
如果要在发送邮件之前进行互操作保存，请调用邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。 有关详细信息，请参阅保存 [邮件](saving-a-message.md) 或 [发送邮件](sending-a-message.md)。 
  
## <a name="in-this-section"></a>本节内容

- [创建收件人列表](creating-a-recipient-list.md)：介绍如何创建收件人列表。
    
- [创建邮件主题](creating-a-message-subject.md)：介绍如何为邮件创建可选主题。
    
- [创建消息文本](creating-message-text.md)：介绍如何创建邮件文本。
    
- [向格式化文本添加呈现信息](adding-rendering-information-to-formatted-text.md)：描述附件在格式化文本中的呈现位置。
    
- [创建邮件附件](creating-a-message-attachment.md)：介绍如何创建附件。
    
- [保存邮件](saving-a-message.md)：描述客户端如何保存邮件。
    
- [发送邮件 ：](sending-a-message.md)介绍如何发送邮件。
    
- [处理已发送的邮件](processing-a-sent-message.md)：介绍如何处理已发送的邮件。
    

