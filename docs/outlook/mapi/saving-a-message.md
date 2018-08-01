---
title: 保存邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 97bff16b-dc7c-4eed-8834-d0c076d83ca3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e61a72691309b2ac632b764c0607f5b1e36b291b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778669"
---
# <a name="saving-a-message"></a>保存邮件

  
  
**适用于**： Outlook 
  
保存一条消息之前，客户端通常呼叫消息的[IMAPIProp::SetProps](imapiprop-setprops.md)方法，以便设置除了消息文本属性、 附件属性、 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))，和属性的几个属性收件人列表相关联。
  
设置为字符的字符串，如 IPM **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。请注意，介绍传出消息的类。 尽管客户端应该对所有传出邮件设置**PR_MESSAGE_CLASS** ，但如果未设置消息存储提供程序提供默认值。 待发邮件的默认邮件类 IPM。 
  
**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_UNSENT 标志。 如果需要，还要设置 MSGFLAG_READ 和 MSGFLAG_UNMODIFIED 标志。 设置 MSGFLAG_UNMODIFIED 允许在组合下的一条消息以模拟邮件已送达。 之前已首次保存一条消息，则仅可以通过客户端设置 MSGFLAG_UNMODIFIED。 
  
当您准备好使永久未发送的邮件的副本时，邮件和附件的所有呼叫[IMAPIProp::SaveChanges](imapiprop-savechanges.md) 。 如果要立即发送消息，您不需要调用**SaveChanges**。 调用**SubmitMessage**内部将邮件作为其处理的一部分。 
  
调用**SaveChanges**时, 最好指定 KEEP_OPEN_READWRITE 标志，从而要修改在以后的消息。 其他可设置标志包括 FORCE_SAVE，指示提交更改后，应关闭消息或附件、 KEEP_OPEN_READONLY，指示将进行任何进一步的更改，和标志若要允许到的消息存储提供程序批处理客户端请求，MAPI_DEFERRED_ERRORS。
  
呼叫**SaveChanges**邮件中的每个附件的邮件的呼叫**SaveChanges**之前至关重要。 如果您不能将附件保存，附件将不可包含在邮件时，它发送并不会出现在邮件的附件表。 如果您不能保存邮件的所有附件保存后，邮件及其附件将丢失。 
  
当调用**SaveChanges**时，消息存储提供程序将更新以下属性： 
  
- **仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 列出了所有主收件人。
    
- **仅包含显示名称**列出所有抄送副本收件人。 
    
- **PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 列出了所有密件抄送副本收件人。
    
- **操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))
    
- **PR_MESSAGE_FLAGS**设置 MSGFLAG_HASATTACH，如果一个或多个附件已保存，并清除 MSGFLAG_UNMODIFIED 显示消息已经更改。 
    
- **PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 包含邮件的最新的大小。
    
- **PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 提供对附件表访问。
    
- **PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 提供对收件人表访问。
    
创建一条消息时，某些消息属性通常由客户端或服务提供程序中提供。 如果客户端在将它们设置，则由**SaveChanges**称为次更新它们的消息存储提供程序。 例如，如果设置了一条消息**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性创建邮件时，他们无需修改在节省时间。 但是，忽略这些设置创建消息的消息存储提供程序必须将它们设置第一次调用**SaveChanges** 。 
  
如果**SaveChanges**返回 MAPI_E_CORRUPT_DATA，假定正在保存的数据现在丢失。 丢失网络连接时或服务器未运行时，其实现中使用客户端-服务器模型的消息存储提供程序可能会返回此值。 向用户返回错误之前, 尝试写入并通过调用**SetProps**跟**SaveChanges**到另一个呼叫到第二次保存的数据。 如果数据缓存在本地，这不应出现问题。 但是，如果没有本地高速缓存或第二个**SaveChanges**呼叫失败，则显示错误警告的问题的用户。 
  

