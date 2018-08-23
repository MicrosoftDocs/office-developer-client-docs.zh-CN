---
title: 通讯簿限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ace8c03-45a7-484b-8c12-516ac0e40dc2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 54cd90cac6c00e8cf274e0b78a1bfec32401bb8d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576510"
---
# <a name="address-book-restrictions"></a>通讯簿限制

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
要在其容器的内容表支持三种类型的限制，通讯簿提供程序被必需:
  
- 模糊名称属性限制
    
- 实例 key 属性限制
    
- 前缀的显示名称内容限制
    
模糊名称限制是属性限制使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性来匹配地址簿容器中条目的收件人姓名。 **PR_ANR**属性限制是"最佳猜测"搜索通讯簿提供程序，从而使得可以选择最适合其容器的匹配属性的类型。 例如，一个通讯簿提供程序可能通过匹配的收件人姓名，针对每个容器条目的**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) 属性来实现**PR_ANR**限制，而其他提供程序可能使用**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。
  
MAPI 建议的**PR_ANR**限制实现 strike 足够性能和用户满意度之间的平衡。 通讯簿提供程序实现如限制时，可能会破坏用户满意度找到太少或太多的匹配项的方式。 某些通讯簿提供程序支持称为不可显示在对话框中，但可以匹配模糊名称限制的可分辨，或常见，名称。 
  
典型的实现可能为单词、 匹配任何项，其中包含的所有单词解析收件人的显示名称。 注意详细信息，如敏感度 word 位置、 是否匹配不连续的单词，和选择分隔符可能不同。 例如，如果解析名称为"Bill L"，典型的**PR_ANR**限制将视为匹配选择以下项： 
  
- Billy Larson
    
- Bill 李
    
- Bill 日志职位需求。 
    
- Sam Bill 李
    
实例键限制或**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性限制的客户端应用程序中使用查看 MAPI 表的列表框实现中使用。 某些列表框实现允许用户进行多个选择，向上滚动或向下，并返回到第一项选择。 若要实现此行为，客户端调用[IMAPITable::FindRow](imapitable-findrow.md)，将属性限制**PR_INSTANCE_KEY**属性传递给方法。 通讯簿提供程序需要支持此限制。 
  
用于查看表的列表框的另一个功能是能够将光标基于一的前缀字符。 在用户启动键入前缀字符时，客户端将光标移到这些字符开头的第一项。 客户端与基于**PR_DISPLAY_NAME**属性和 FL_PREFIX 模糊级别内容限制实现此功能。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

