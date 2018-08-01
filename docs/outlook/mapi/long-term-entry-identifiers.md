---
title: 长期条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a514275e-40c2-48db-8072-1dfc392a7ac6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 589420db48edb348a22f34ce72b948f4d8207ae9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776158"
---
# <a name="long-term-entry-identifiers"></a>长期条目标识符

  
  
**适用于**： Outlook 
  
对象需要与长寿命标识符时，将服务提供程序为对象分配的长期的项标识符。 长期条目标识符周或月始终是有效，可以在其他工作站，具体取决于提供程序上有效。 创建自定义的收件人的地址簿提供程序的长期标识符是通用有效。 
  
长期条目标识符已分配给消息存储库、 文件夹、 邮件、 通讯簿容器、 邮件用户和通讯组列表。 当客户端应用程序调用这些对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法时，始终是返回的长期条目标识符。 
  
长期条目标识符必须唯一活动配置文件; 中的所有邮件存储因此，当邮件或文件夹从一个消息存储到另一个复制，必须将它分配新的项标识符。 当移动消息存储对象时，实现移动的消息存储提供程序将确定是否原始条目标识符将一直保持有效。 某些服务提供商向移动对象; 分配新的项标识符有些则没有。 如果发生更改时，将得到的移动通知时传递给客户端的信息中包括的新的项标识符。 
  
通常情况下，消息存储提供程序时将文件夹移实现以下行为：
  
- 当文件夹从一个消息存储库移至另一个不同类型的存储时，条目标识符保证更改。
    
- 当文件夹从一个消息存储库移至另一个相同类型的存储时，始终更改的项标识符。
    
- 当文件夹移至的相同的消息存储中的另一个位置时，条目标识符可能或可能未更改，具体取决于消息存储提供程序。
    
重命名文件夹，而不更改其父文件夹通常不会导致要更改的项标识符。 
  
## <a name="see-also"></a>另请参阅



[MAPI 条目标识符](mapi-entry-identifiers.md)

