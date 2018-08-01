---
title: 使用邮件存储区提供程序接收邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4763951e-ccfd-453e-b99c-5c7d5efb90c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 94ea0fe7fba4e49c1f646d889f3727cf5ef4739d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778592"
---
# <a name="receiving-messages-by-using-message-store-providers"></a>使用邮件存储区提供程序接收邮件

  
  
**适用于**： Outlook 
  
消息存储提供程序无需支持传入的邮件提交 （即，为支持的功能的传输提供商和 MAPI 后台处理程序使用消息存储提供程序的邮件的传递点）。 但是，如果您的消息存储提供程序不支持传入的邮件提交，它不能用作默认邮件存储区。
  
若要支持传入的邮件提交，消息存储提供程序必须执行以下操作：
  
- 支持的[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)和[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)方法，以便客户端应用程序可以找到传入消息。 
    
- 支持的[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)方法，以便 MAPI 后台处理程序可通知新消息已到达的消息存储提供程序。 
    
- 实现通知，以便客户端可以注册新邮件通知。 通知是可选的但您的提供商应实现它们。
    
传入消息传递到的消息存储时，发生此事件的方法调用顺序如下所示：
  
1. MAPI 后台处理程序调用[IMsgStore::OpenEntry](imsgstore-openentry.md)与收件箱[EntryID](entryid.md)获取[IMAPIFolder](imapifolderimapicontainer.md)接口。 
    
2. MAPI 后台处理程序调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)获取新消息对象。 
    
3. MAPI 后台处理程序将 message 对象传递到传输提供程序。
    
4. 传输提供程序填入基础邮件系统中的数据消息的属性，并调用 message 对象的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 
    
5. 消息存储提供程序使用其通知方法通知注册的客户端，已到达一个新的邮件。
    
6. MAPI 后台处理程序调用的消息存储[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)方法。 
    
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

