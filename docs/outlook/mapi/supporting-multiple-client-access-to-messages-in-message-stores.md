---
title: 支持多个客户端访问邮件存储区中的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 31885c64-edb2-4a87-8730-09f163dedd40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b13fbb9f2807c9814fed5ba3bcca8fe73aaa7b01
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564218"
---
# <a name="supporting-multiple-client-access-to-messages-in-message-stores"></a>支持多个客户端访问邮件存储区中的邮件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
很可能为多个客户端应用程序同时打开给定的消息。 消息存储提供程序没有关注调控此类访问权限的任何特定规则。 但是，如果客户端应用程序修改邮件，并保存其更改，存储提供程序都应符合以下规则：
  
- 允许对[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法的第一个调用，以继续好像它是已打开的消息的唯一客户端。 
    
- 在其他客户端的**SaveChanges**后续呼叫，消息存储提供程序应忽略所做的更改并返回 MAPI_E_OBJECT_CHANGED。 
    
- 允许客户端应用程序以应对 MAPI_E_OBJECT_CHANGED 返回代码通过调用**SaveChanges**再次使用 FORCE_SAVE 标志。 如果客户端应用程序这，消息存储提供程序应当用新的替换以前的更改。 
    
此外，消息存储提供程序可以检测到冲突，并演示使用户可以选择是否保留原始邮件，使用新的更改，覆盖原始邮件或将新的更改保存到另一个位置的接口。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储区中的邮件](implementing-messages-in-message-stores.md)

