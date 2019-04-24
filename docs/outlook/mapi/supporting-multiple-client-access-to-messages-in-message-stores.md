---
title: 支持对邮件存储区中的邮件进行多个客户端访问
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 31885c64-edb2-4a87-8730-09f163dedd40
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 40bed9ccbe8073c8e9ea5176c9d4be8fe642b52d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350601"
---
# <a name="supporting-multiple-client-access-to-messages-in-message-stores"></a>支持对邮件存储区中的邮件进行多个客户端访问

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
多个客户端应用程序可以同时打开给定的邮件。 邮件存储提供程序不必遵循用于控制此类访问的任何特定规则。 但是, 如果客户端应用程序修改邮件并保存其更改, 则存储提供程序应遵循以下规则:
  
- 允许对[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法进行的第一次调用, 就像它是打开邮件的唯一客户端一样。 
    
- 在其他客户端的后续**SaveChanges**调用中, 邮件存储提供程序应忽略所做的更改, 然后返回 MAPI_E_OBJECT_CHANGED。 
    
- 允许客户端应用程序通过使用 FORCE_SAVE 标志再次调用**SaveChanges**来响应 MAPI_E_OBJECT_CHANGED 返回代码。 如果客户端应用程序这样做, 则邮件存储提供程序应将以前的更改替换为新的更改。 
    
或者, 邮件存储提供程序可以检测到冲突并提供一个接口, 使用户能够选择是保留原始邮件、使用新更改覆盖原始邮件, 还是将新更改保存到另一个位置。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储中的邮件](implementing-messages-in-message-stores.md)

