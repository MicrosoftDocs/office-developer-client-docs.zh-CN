---
title: 处理传入的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d45d5ed9-41cd-4aaf-91d2-1e4a27bb16d4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f3fbe34793e3520b26b984f4bd6b14fbcab7a951
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438979"
---
# <a name="handling-an-incoming-message"></a>处理传入的邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
传入邮件是跨一个或多个邮件系统发送的邮件。 它可能只发送给您或发送给许多其他收件人。 传入邮件放置在指定用于保存特定类的邮件的接收文件夹中。 您可以为处理的每个邮件类设置不同的接收文件夹，或者在所有类中都使用一个文件夹。
  
如果已在邮件存储中注册新邮件通知，则每当邮件放入接收文件夹中时，都会收到通知。 如果尚未注册新邮件通知，则必须定期打开相应的接收文件夹，以手动检查新邮件的到达时间。
  
客户端通过按如下方式将参数设置为 [IMsgStore：：Advise](imsgstore-advise.md) 来注册新邮件通知： 
  
- 将  _cbEntryID 设置为_ 0。 
    
- 将  _lpEntryID 设置为_ NULL。 
    
- 将  _ulEventMask 设置为_ fnevNewMail。 
    
对 **IMAPIAdviseSink：：OnNotify** 方法的调用中的 _lpNotifications_ 参数指向一个 **NEWMAIL \_ NOTIFICATION** 结构，其中包含有关传入邮件的信息，例如其邮件类、其条目标识符、其父文件夹的条目标识符及其 PR_MESSAGE_FLAGS 属性 **的内容**。 有关注册和处理通知的信息，请参阅[IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) [、NEWMAIL_NOTIFICATION、PR_MESSAGE_FLAGS](newmail_notification.md) ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和[Handling Notifications。](handling-notifications.md)  
  
在向用户显示传入邮件之前，请确定其邮件类是否是你的客户端支持的类。 如果没有，则忽略该消息。 如果该类是支持类，可以使用适用于邮件的邮件类的窗体打开和显示邮件。 窗体的选择基于邮件类。 属于 IPM 类的邮件使用 MAPI 实现的默认窗体。 属于客户端定义的自定义类的邮件可以使用客户端定义的专用窗体或 MAPI 默认窗体。
  
## <a name="open-and-display-an-incoming-message"></a>打开并显示传入消息
  
1. 调用 **IMsgStore：：GetReceiveFolder** 检索邮件类的接收文件夹的条目标识符，并传递此条目标识符到 **IMsgStore：：OpenEntry** 以打开该文件夹。 有关详细信息，请参阅[IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) [、IMsgStore：：OpenEntry](imsgstore-openentry.md)和[Opening a Message Store Folder。](opening-a-message-store-folder.md)
    
2. 调用接收文件夹的 **IMAPIContainer：：GetContentsTable** 方法以检索其内容表。 有关详细信息，请参阅 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md)。 调用表的 **IMAPITable：：QueryRows** 方法来检索表中的所有行。 有关详细信息，请参阅[IMAPITable：：QueryRows](imapitable-queryrows.md)和[Contents Tables。](contents-tables.md) 有关显示内容表的信息，请参阅 [显示文件夹内容表](displaying-a-folder-contents-table.md)。
    
3. 如果您的客户端是交互式的，则允许用户从表中选择一条消息并确定用于显示该消息的表单。 客户端可以使用 MAPI 提供的默认窗体或自定义窗体。 有关详细信息，请参阅处理 [MAPI 窗体](handling-mapi-forms.md)。
    
4. 调用 **IMsgStore：：OpenEntry** 打开邮件。 有关详细信息，请参阅 [打开邮件](opening-a-message.md)。
    
5. 处理消息文本。 有关详细信息，请参阅打开 [邮件文本](opening-message-text.md)。
    
6. 呈现每个邮件附件。 有关详细信息，请参阅以纯文本呈现附件 [或在](rendering-an-attachment-in-plain-text.md) [RTF 文本中呈现附件](rendering-an-attachment-in-rtf-text.md)。
    
7. 如果需要，请打开附件。 有关详细信息，请参阅 [打开附件](opening-an-attachment.md)。
    
## <a name="in-this-section"></a>本节内容

- [打开邮件文本](opening-message-text.md)：介绍如何打开邮件文本。
    
- [以纯文本呈现附件](rendering-an-attachment-in-plain-text.md)：介绍如何以纯文本呈现附件。
    
- [以 RTF 文本呈现](rendering-an-attachment-in-rtf-text.md)附件 ：介绍如何以格式化文本呈现附件。
    
- [打开附件](opening-an-attachment.md)：介绍如何打开附件。
    

