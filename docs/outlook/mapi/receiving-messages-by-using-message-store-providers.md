---
title: 使用邮件存储提供程序接收邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4763951e-ccfd-453e-b99c-5c7d5efb90c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c93a4b56489c2bfb458e2e1cd872073e64d9998a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328446"
---
# <a name="receiving-messages-by-using-message-store-providers"></a>使用邮件存储提供程序接收邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序无需支持传入邮件提交 (即, 支持传输提供程序和 MAPI 后台处理程序将邮件存储提供程序用作邮件的传递点) 的功能。 但是, 如果您的邮件存储提供程序不支持传入邮件提交, 则不能将其用作默认邮件存储。
  
若要支持传入邮件提交, 您的邮件存储提供程序必须执行以下操作:
  
- 支持[IMsgStore:: GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)和[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)方法, 以便客户端应用程序可以找到传入的邮件。 
    
- 支持[IMsgStore:: NotifyNewMail](imsgstore-notifynewmail.md)方法, 以便 MAPI 后台处理程序可以通知邮件存储提供程序是否已到达新邮件。 
    
- 实施通知, 以便客户端可以注册新的邮件通知。 通知是可选的, 但您的提供程序应实施这些通知。
    
传入邮件传递到邮件存储区时的方法调用序列如下所示:
  
1. MAPI 后台处理程序调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)和收件箱[EntryID](entryid.md)以获取[IMAPIFolder](imapifolderimapicontainer.md)接口。 
    
2. MAPI 后台处理程序调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)获取新的 message 对象。 
    
3. MAPI 后台处理程序将 message 对象传递给传输提供程序。
    
4. 传输提供程序使用基础邮件系统中的数据填充邮件的属性, 并调用 message 对象的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。 
    
5. 邮件存储提供程序使用其通知方法来通知已注册的客户端新邮件已到达。
    
6. MAPI 后台处理程序调用邮件存储区的[IMsgStore:: NotifyNewMail](imsgstore-notifynewmail.md)方法。 
    
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

