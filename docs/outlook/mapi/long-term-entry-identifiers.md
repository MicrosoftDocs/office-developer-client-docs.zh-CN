---
title: Long-Term条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a514275e-40c2-48db-8072-1dfc392a7ac6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b65656992681618aa8a1c53217bdd7101bc2502b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409221"
---
# <a name="long-term-entry-identifiers"></a>Long-Term条目标识符

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当对象需要生存期较长的标识符时，服务提供商将长期条目标识符分配给对象。 长期条目标识符对于周或月始终有效，并且在其他工作站上也有效，具体取决于提供程序。 由通讯簿提供程序为自定义收件人创建的长期标识符通常有效。 
  
长期条目标识符分配给邮件存储、文件夹、邮件、通讯簿容器、邮件用户和通讯组列表。 当客户端应用程序调用这些对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法时，它始终是返回的长期条目标识符。 
  
长期条目标识符在活动配置文件中所有邮件存储中必须是唯一的;因此，将邮件或文件夹从一个邮件存储复制到另一个邮件存储时，必须为其分配一个新的条目标识符。 移动邮件存储对象时，实现移动的邮件存储提供程序将确定原始条目标识符是否将保持有效。 某些服务提供商向移动的对象分配新的条目标识符;其他则不允许。 如果更改，当客户端收到移动通知时，新条目标识符将包含在传递给客户端的信息中。 
  
通常，邮件存储提供程序在移动文件夹时会实现以下行为：
  
- 将文件夹从一个邮件存储移动到另一个不同类型的存储时，保证条目标识符会更改。
    
- 将文件夹从一个邮件存储移动到同一类型的另一个存储时，条目标识符几乎总是会更改。
    
- 当文件夹移动到同一邮件存储中的另一个位置时，条目标识符可能会更改，也可能不变，具体取决于邮件存储提供程序。
    
重命名文件夹而不更改其父文件夹通常不会导致条目标识符更改。 
  
## <a name="see-also"></a>另请参阅



[MAPI 条目标识符](mapi-entry-identifiers.md)

