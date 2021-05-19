---
title: 保存邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 97bff16b-dc7c-4eed-8834-d0c076d83ca3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d5ceeb46bded101700aec696a17d690bde80ce6d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420928"
---
# <a name="saving-a-message"></a>保存邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在保存邮件之前，客户端通常调用邮件的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来设置邮件文本属性、附件属性 **、PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 以及与收件人列表关联的属性。
  
将 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性设置为字符串（如 IPM）。请注意，描述传出邮件的类。 尽管客户端应 **PR_MESSAGE_CLASS** 所有传出邮件设置默认值，但是如果未设置，则由邮件存储提供程序提供默认值。 传出邮件的默认邮件类别为 IPM。 
  
设置 MSGFLAG_UNSENT [PidTagMessageFlags](pidtagmessageflags-canonical-property.md) PR_MESSAGE_FLAGS (标记) 标记。  如果需要，还要设置MSGFLAG_READ和MSGFLAG_UNMODIFIED标志。 设置MSGFLAG_UNMODIFIED允许组合下的邮件模拟传递的邮件。 MSGFLAG_UNMODIFIED第一次保存邮件之前，客户端才能设置该设置。 
  
准备好制作未发送邮件的永久副本时，请对邮件及其所有附件调用[IMAPIProp：：SaveChanges。](imapiprop-savechanges.md) 如果打算立即发送邮件，则无需调用 **SaveChanges**。 调用 **SubmitMessage** 会将邮件保存为邮件处理的一部分。 
  
调用 **SaveChanges** 时，建议指定 KEEP_OPEN_READWRITE 标记，以允许在以后修改邮件。 其他可设置的标志包括 FORCE_SAVE（指示提交更改后应关闭邮件或附件）和 KEEP_OPEN_READONLY（指示不会进行进一步更改）和用于允许邮件存储提供程序批处理客户端请求的标志 MAPI_DEFERRED_ERRORS。
  
为邮件调用 **SaveChanges** 之前，必须针对邮件中每个附件调用 **SaveChanges。** 如果无法保存附件，则邮件发送时不会包含附件，并且附件不会显示在邮件的附件表中。 如果在保存所有附件后无法保存邮件，邮件和附件都将丢失。 
  
调用 **SaveChanges** 时，邮件存储提供程序将更新以下属性： 
  
- **PR_DISPLAY_TO (** [PidTagDisplayTo)](pidtagdisplayto-canonical-property.md) 列出所有主收件人。
    
- **PR_DISPLAY_TO** 列出所有抄稿收件人。 
    
- **PR_DISPLAY_BCC (** [PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 列出所有抄送收件人。
    
- **PR_LAST_MODIFICATION_TIME (** [PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md)) 
    
- **PR_MESSAGE_FLAGS** 设置MSGFLAG_HASATTACH一个或多个附件，并清除MSGFLAG_UNMODIFIED显示邮件已更改的附件。 
    
- **PR_MESSAGE_SIZE (** [PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 包含邮件的当前大小。
    
- **PR_MESSAGE_ATTACHMENTS (** [PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 提供对附件表的访问。
    
- **PR_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 提供对收件人表的访问。
    
一些邮件属性通常由客户端或服务提供商在邮件创建时提供。 如果客户端没有设置它们，则由消息存储提供程序在调用 **SaveChanges** 时更新它们。 例如，如果在创建邮件时设置了邮件的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性，则无需在保存时修改这些属性。 但是，在邮件创建时忽略设置它们的邮件存储提供程序必须在首次调用 **SaveChanges 时** 设置它们。 
  
如果 **SaveChanges** 返回MAPI_E_CORRUPT_DATA，则假定正在保存的数据现已丢失。 当网络连接丢失或服务器未运行时，使用客户端-服务器模型实现的消息存储提供程序可能会返回此值。 在向用户返回错误之前，尝试再次写入并保存数据，方法为调用 **SetProps，** 然后再次调用 **SaveChanges**。 如果在本地缓存数据，这应该不会是问题。 但是，如果没有本地缓存或第二个 **SaveChanges** 调用失败，则显示一个错误以提醒用户该问题。 
  

