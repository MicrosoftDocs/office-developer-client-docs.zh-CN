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
  
传入邮件是已在一个或多个邮件系统中发送的邮件。 它可能已仅发送给您或其他许多收件人。 传入邮件放在接收文件夹中, 指定用于保存特定类的邮件。 您可以为每个要处理的邮件类别设置不同的接收文件夹, 或为所有类使用一个文件夹。
  
如果已使用邮件存储区注册了新邮件通知, 则每当邮件放在接收文件夹中时, 都会收到通知。 如果尚未注册新邮件通知, 则必须定期打开相应的接收文件夹, 以手动检查是否到达新邮件。
  
客户端通过将参数设置为[IMsgStore:: 建议](imsgstore-advise.md)来注册新邮件通知, 如下所示: 
  
- 将_cbEntryID_设置为0。 
    
- 将_lpEntryID_设置为 NULL。 
    
- 将_ulEventMask_设置为 fnevNewMail。 
    
对**IMAPIAdviseSink:: OnNotify**方法的调用中的_lpNotifications_参数指向一个**\_NEWMAIL 通知**结构, 其中包含有关传入邮件的信息, 例如其邮件类别、其条目标识符、其父文件夹的条目标识符以及它的**PR_MESSAGE_FLAGS**属性的内容。 有关注册和处理通知的详细信息, 请参阅[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)、 [NEWMAIL_NOTIFICATION](newmail_notification.md)、 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和[处理通知](handling-notifications.md)。 
  
在向用户显示传入邮件之前, 请确定其邮件类别是否为您的客户端支持的类。 如果不是, 则忽略该消息。 如果类是您支持的类, 则可以使用适合于邮件的邮件类的窗体打开和显示邮件。 窗体的选择基于邮件类。 属于 IPM 类的邮件使用由 MAPI 实现的默认表单。 属于由客户端定义的自定义类的邮件可以使用客户端定义的专用表单或 MAPI 默认表单。
  
## <a name="open-and-display-an-incoming-message"></a>打开并显示传入的邮件
  
1. 调用**IMsgStore:: GetReceiveFolder**以检索邮件的邮件类的接收文件夹的条目标识符, 并将此条目标识符传递到**IMsgStore:: OpenEntry**以打开该文件夹。 有关详细信息, 请参阅[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md), [IMsgStore:: OpenEntry](imsgstore-openentry.md), 并[打开邮件存储文件夹](opening-a-message-store-folder.md)。
    
2. 调用接收文件夹的**IMAPIContainer:: GetContentsTable**方法以检索其内容表。 有关详细信息, 请参阅[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)。 调用表的**IMAPITable:: QueryRows**方法以检索表中的所有行。 有关详细信息, 请参阅[IMAPITable:: QueryRows](imapitable-queryrows.md)和[内容表](contents-tables.md)。 有关显示内容表的详细信息, 请参阅[显示文件夹内容表](displaying-a-folder-contents-table.md)。
    
3. 如果您的客户端是交互式的, 则允许用户从表中选择一封邮件, 并确定要用于显示该邮件的窗体。 客户端可以使用 MAPI 或自定义窗体提供的默认窗体。 有关详细信息, 请参阅[处理 MAPI 表单](handling-mapi-forms.md)。
    
4. 调用**IMsgStore:: OpenEntry**以打开邮件。 有关详细信息, 请参阅[打开邮件](opening-a-message.md)。
    
5. 处理消息文本。 有关详细信息, 请参阅[打开消息文本](opening-message-text.md)。
    
6. 呈现每个邮件附件。 有关详细信息, 请参阅[以纯文本呈现附件](rendering-an-attachment-in-plain-text.md)或[在 RTF 文本中呈现附件](rendering-an-attachment-in-rtf-text.md)。
    
7. 如果需要, 打开一个附件。 有关详细信息, 请参阅[打开附件](opening-an-attachment.md)。
    
## <a name="in-this-section"></a>本节内容

- [打开消息文本](opening-message-text.md): 介绍如何打开消息文本。
    
- [以纯文本格式呈现附件](rendering-an-attachment-in-plain-text.md): 介绍如何以纯文本形式呈现附件。
    
- [在 RTF 文本中呈现附件](rendering-an-attachment-in-rtf-text.md): 介绍如何在格式化文本中呈现附件。
    
- [打开附件](opening-an-attachment.md): 介绍如何打开附件。
    

