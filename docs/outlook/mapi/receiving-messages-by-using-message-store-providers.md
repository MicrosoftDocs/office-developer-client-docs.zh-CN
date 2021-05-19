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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418727"
---
# <a name="receiving-messages-by-using-message-store-providers"></a>使用邮件存储提供程序接收邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序不需要支持传入邮件提交 (也就是说，支持传输提供程序和 MAPI 后台处理程序将邮件存储提供程序用作邮件传输) 。 但是，如果邮件存储提供程序不支持传入邮件提交，则不能用作默认邮件存储。
  
若要支持传入邮件提交，邮件存储提供程序必须执行以下操作：
  
- 支持 [IMsgStore：：GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) 和 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 方法，以便客户端应用程序可以找到传入的邮件。 
    
- 支持 [IMsgStore：：NotifyNewMail](imsgstore-notifynewmail.md) 方法，以便 MAPI 后台处理程序可以通知邮件存储提供程序新邮件已到达。 
    
- 实现通知，以便客户端可以注册新邮件通知。 通知是可选的，但提供程序应实现它们。
    
传入邮件传递到邮件存储时发生的方法调用顺序如下：
  
1. MAPI 后台处理程序使用收件箱[EntryID](entryid.md)调用[IMsgStore：：OpenEntry，](imsgstore-openentry.md)获取[IMAPIFolder](imapifolderimapicontainer.md)接口。 
    
2. MAPI 后台处理程序调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 获取新的邮件对象。 
    
3. MAPI 后台处理程序将邮件对象传递给传输提供程序。
    
4. 传输提供程序使用来自基础邮件系统的数据填充邮件的属性，并调用邮件对象的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。 
    
5. 邮件存储提供程序使用其通知方法通知注册的客户端新邮件已到达。
    
6. MAPI 后台处理程序调用邮件存储的 [IMsgStore：：NotifyNewMail](imsgstore-notifynewmail.md) 方法。 
    
## <a name="see-also"></a>另请参阅



[邮件存储功能](message-store-features.md)

