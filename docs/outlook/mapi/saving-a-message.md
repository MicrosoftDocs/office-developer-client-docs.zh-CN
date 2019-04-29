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
  
在保存邮件之前, 客户端通常会调用邮件的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法, 以设置除邮件文本属性、附件属性、 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 和属性之外的一些属性。与收件人列表相关联。
  
将**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性设置为字符串 (如 IPM.)。请注意, 说明传出邮件的类。 虽然客户端应在所有传出邮件上设置**PR_MESSAGE_CLASS** , 但如果您不设置它, 则邮件存储提供程序将提供默认值。 待发邮件的默认邮件类为 IPM。 
  
在**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_UNSENT 标志。 如果需要, 还可以设置 MSGFLAG_READ 和 MSGFLAG_UNMODIFIED 标志。 设置 MSGFLAG_UNMODIFIED 允许撰写一封邮件, 以模拟已传递的邮件。 仅在首次保存邮件之前, 客户端才能设置 MSGFLAG_UNMODIFIED。 
  
当您准备好为未发送的邮件创建永久副本时, 请在邮件及其所有附件上调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md) 。 如果要立即发送邮件, 则无需调用**SaveChanges**。 对**SubmitMessage**的调用会在其处理过程中保存邮件。 
  
调用**SaveChanges**时, 最好指定 KEEP_OPEN_READWRITE 标志, 这将允许在以后修改该邮件。 其他可设置的标志包括 FORCE_SAVE, 这表示在提交更改后应关闭邮件或附件, KEEP_OPEN_READONLY (指示不会进行进一步的更改) 以及允许邮件存储提供程序的标志批处理客户端请求, MAPI_DEFERRED_ERRORS。
  
在调用消息的**savechanges**之前, 对邮件中的每个附件调用**savechanges**是非常重要的。 如果无法保存附件, 则邮件在发送时不会包含在邮件中, 并且不会显示在邮件的附件表中。 如果保存所有附件后无法保存邮件, 则邮件和附件都将丢失。 
  
调用**SaveChanges**时, 邮件存储提供程序将更新以下属性: 
  
- **PR_DISPLAY_TO**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 列出所有主要收件人。
    
- **PR_DISPLAY_TO**列出所有抄送收件人。 
    
- **PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 列出所有密件抄送收件人。
    
- **操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))
    
- 如果保存了一个或多个附件并清除 MSGFLAG_UNMODIFIED 以显示邮件已更改, 则**PR_MESSAGE_FLAGS**将设置 MSGFLAG_HASATTACH。 
    
- **PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 包含最新的邮件大小。
    
- **PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 提供对附件表的访问权限。
    
- **PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 提供对收件人表的访问权限。
    
某些邮件属性通常由客户端或服务提供商在创建邮件时提供。 如果客户端在对其进行设置, 则在调用**SaveChanges**时, 将由邮件存储提供程序对其进行更新。 例如, 如果在创建邮件时设置了邮件的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性, 则无需在保存时对其进行修改。 但是, 在邮件创建过程中忘记设置它们的邮件存储提供程序必须在第一次调用**SaveChanges**时设置它们。 
  
如果**SaveChanges**返回 MAPI_E_CORRUPT_DATA, 则假定要保存的数据现在已丢失。 将客户端-服务器模型用于实施的邮件存储提供程序可能会在网络连接丢失或服务器未运行时返回此值。 在向用户返回错误之前, 请先调用**SetProps**并再次调用**SaveChanges**, 以再次写入并保存数据。 如果数据在本地缓存, 则不会出现问题。 但是, 如果没有本地缓存或第二个**SaveChanges**调用失败, 则显示一个错误, 提醒用户出现该问题。 
  

