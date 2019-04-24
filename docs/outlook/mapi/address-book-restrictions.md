---
title: 通讯簿限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ace8c03-45a7-484b-8c12-516ac0e40dc2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7419c174c1f68653794c2dbd836577e8dd3e596e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328075"
---
# <a name="address-book-restrictions"></a>通讯簿限制

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序在其容器的内容表上支持三种类型的限制是必需的:
  
- 不明确的名称属性限制
    
- 实例键属性限制
    
- 带前缀的显示名称内容限制
    
不明确的名称限制是使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性将收件人姓名与通讯簿容器中的条目相匹配的属性限制。 **PR_ANR**属性限制是一种 "最佳推测" 类型的搜索, 使用通讯簿提供程序可以选择最适合其容器的匹配属性。 例如, 一个通讯簿提供程序可以通过针对每个容器条目的**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) 属性匹配收件人名称来实现**PR_ANR**限制, 而另一个提供程序可能会使用**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。
  
MAPI 建议**PR_ANR**限制的实现在充分的性能和用户满意度之间达到平衡。 当通讯簿提供程序以这样的方式实施限制时, 可能会危及用户满意度, 因为找到的匹配项过少或过多。 某些通讯簿提供程序支持称为可分辨或公用的名称, 该名称在对话框中不可显示, 但可以匹配不明确的名称限制。 
  
典型的实现可能是将收件人的显示名称解析为词, 并匹配包含所有单词的任何条目。 注意对 word 位置的敏感性、不连续单词是否匹配以及分隔符字符的选择可能不同的详细信息。 例如, 如果要解析的名称为 "Bill L", 则典型的**PR_ANR**限制将选择以下条目作为匹配: 
  
- Billy Larson
    
- 帐单先生
    
- 付款人 Logan 先生。 
    
- Sam 帐单先生/
    
在用于查看 MAPI 表的客户端应用程序中使用列表框的实现中使用实例密钥限制或**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性限制。 某些列表框实现允许用户进行多项选择, 向上或向下滚动, 然后返回到选定的第一个项目。 若要实现此行为, 客户端调用[IMAPITable:: FindRow](imapitable-findrow.md), 并将**PR_INSTANCE_KEY**属性上的属性限制传递给方法。 需要通讯簿提供程序来支持此限制。 
  
用于表格查看的列表框的另一项功能是能够根据一组前缀字符定位光标。 当用户开始键入前缀字符时, 客户端会将光标移动到第一个以这些字符开头的项。 客户端通过基于**PR_DISPLAY_NAME**属性和 FL_PREFIX 模糊级别的内容限制来实现此功能。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

