---
title: 处理传入消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d45d5ed9-41cd-4aaf-91d2-1e4a27bb16d4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5705af6c8efaf42ae27d1b39bb28d162971ebf9b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775044"
---
# <a name="handling-an-incoming-message"></a>处理传入消息

**适用于**： Outlook 
  
对传入邮件是已跨一个或多个邮件系统发送的消息。 它可能已发送只对您或其他很多个收件人。 传入消息被置于指定用于保存的特定类的邮件的接收文件夹。 您可以设置另一个接收您处理，或使用的所有类的一个文件夹每个邮件类的文件夹。
  
如果您已注册的与邮件存储的新邮件通知，将一条消息置于接收文件夹时通知您。 如果您未注册新邮件通知，则必须打开相应接收定期来手动检查新邮件的到达的文件夹。
  
客户端注册新邮件通知通过将参数设置为[IMsgStore::Advise](imsgstore-advise.md) ，如下所示： 
  
- 设置为 0 _cbEntryID_ 。 
    
- _LpEntryID_设置为 NULL。 
    
- 设置为 fnevNewMail _ulEventMask_ 。 
    
对**IMAPIAdviseSink::OnNotify**方法的调用中的_lpNotifications_参数指向**NEWMAIL\_通知**结构，其中包含有关传入邮件，例如其邮件类别，它的项的信息标识符，其父文件夹的项标识符和其**PR_MESSAGE_FLAGS**属性的内容。 有关注册和处理通知的详细信息，请参阅[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)、 [NEWMAIL_NOTIFICATION](newmail_notification.md)、 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和[处理通知](handling-notifications.md)。 
  
向用户显示传入消息之前, 确定其邮件类别是您的客户端支持的类。 如果没有，则忽略该消息。 如果您支持的一个类，您可以打开并显示适用于邮件的邮件类的窗体的邮件。 邮件类基于表单的选择。 属于 IPM 类的邮件使用由 MAPI 实现默认窗体。 属于自定义类定义由客户端的消息可以使用客户端定义专用窗体或 MAPI 默认窗体。
  
## <a name="open-and-display-an-incoming-message"></a>打开并显示传入消息
  
1. 调用**IMsgStore::GetReceiveFolder**检索的接收文件夹的邮件的邮件类的项标识符，并将此条目标识符传递到**IMsgStore::OpenEntry**打开文件夹。 有关详细信息，请参阅[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)、 [IMsgStore::OpenEntry](imsgstore-openentry.md)，和[打开邮件存储文件夹](opening-a-message-store-folder.md)。
    
2. 呼叫的接收文件夹**IMAPIContainer::GetContentsTable**方法来检索其内容表。 有关详细信息，请参阅[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)。 调用表的**IMAPITable::QueryRows**方法来检索表中的所有行。 有关详细信息，请参阅[IMAPITable::QueryRows](imapitable-queryrows.md)和[内容的表格](contents-tables.md)。 有关显示内容表的详细信息，请参阅[显示文件夹内容表](displaying-a-folder-contents-table.md)。
    
3. 如果您的客户端交互，允许用户从表中选择一条消息，并确定要用于显示该邮件的表单。 客户端可以使用 MAPI 或自定义窗体提供的默认窗体。 有关详细信息，请参阅[处理 MAPI 表单](handling-mapi-forms.md)。
    
4. 调用**IMsgStore::OpenEntry**以打开该邮件。 有关详细信息，请参阅[打开一条消息](opening-a-message.md)。
    
5. 处理的消息文本。 有关详细信息，请参阅[打开消息文本](opening-message-text.md)。
    
6. 呈现每个邮件附件。 有关详细信息，请参阅[呈现纯文本中的附件](rendering-an-attachment-in-plain-text.md)或[呈现 RTF 文本中的附件](rendering-an-attachment-in-rtf-text.md)。
    
7. 如果需要，请打开的附件。 有关详细信息，请参阅[打开附件](opening-an-attachment.md)。
    
## <a name="in-this-section"></a>本节内容

- [打开消息文本](opening-message-text.md)： 介绍如何打开的消息文本。
    
- [呈现以纯文本附件](rendering-an-attachment-in-plain-text.md)： 介绍如何呈现纯文本中的附件。
    
- [呈现 RTF 文本中的附件](rendering-an-attachment-in-rtf-text.md)： 介绍如何呈现附件中带格式的文本。
    
- [打开附件](opening-an-attachment.md)： 介绍如何打开的附件。
    

