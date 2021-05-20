---
title: 支持对邮件存储中邮件的多个客户端访问
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 31885c64-edb2-4a87-8730-09f163dedd40
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 40bed9ccbe8073c8e9ea5176c9d4be8fe642b52d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439861"
---
# <a name="supporting-multiple-client-access-to-messages-in-message-stores"></a>支持对邮件存储中邮件的多个客户端访问

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
多个客户端应用程序可以同时打开给定消息。 邮件存储提供程序不需要遵循管理此类访问的任何特定规则。 但是，如果客户端应用程序修改邮件并保存其更改，则存储提供程序应遵守以下规则：
  
- 允许第一次调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法，就像它是打开消息的唯一客户端一样。 
    
- 在其他客户端 **的后续 SaveChanges** 调用中，邮件存储提供程序应忽略更改并返回MAPI_E_OBJECT_CHANGED。 
    
- 允许客户端应用程序使用 MAPI_E_OBJECT_CHANGED 标志再次调用 **SaveChanges** 来响应FORCE_SAVE代码。 如果客户端应用程序这样做，邮件存储提供程序应该将以前的更改替换为新更改。 
    
或者，邮件存储提供程序可以检测冲突并呈现一个界面，使用户可以选择是保留原始邮件，还是使用新更改覆盖原始邮件，还是将新更改保存到其他位置。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储中的邮件](implementing-messages-in-message-stores.md)

