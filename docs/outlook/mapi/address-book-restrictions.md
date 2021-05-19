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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432798"
---
# <a name="address-book-restrictions"></a>通讯簿限制

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序需要支持对容器的内容表的三种类型的限制：
  
- 不明确的名称属性限制
    
- 实例键属性限制
    
- 前缀显示名称内容限制
    
不明确的名称限制是使用 PR_ANR ( [PidTagAnr](pidtaganr-canonical-property.md)) 属性将收件人姓名与通讯簿容器中的条目相匹配的属性限制。 PR_ANR **属性** 限制是一种"最佳猜测"类型的搜索，通过该搜索，通讯簿提供程序可以选择最适合其容器的匹配属性。 例如，一个通讯簿提供商可能通过针对每个容器 **条目** 的 **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) 属性匹配收件人姓名来实现 PR_ANR 限制，而另一个提供商可能使用 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 。
  
MAPI 建议实现该 **PR_ANR在足够的** 性能和用户满意度之间取得平衡。 当通讯簿提供程序实现限制时，发现匹配数过少或匹配过多，可能会损害用户满意度。 某些通讯簿提供程序支持所谓的可分辨名称或常用名称，该名称在对话框中无法显示，但可以匹配不明确的名称限制。 
  
典型的实现可能是将收件人的显示名称解析为单词，与包含所有单词的任何条目匹配。 注意详细信息，例如对单词位置的敏感性、是否匹配非安全单词以及分隔符的选择可能会有所不同。 例如，如果要解析的名称为"Bill L"，则典型的 **PR_ANR限制会** 选择以下条目作为匹配项： 
  
- Billy Larson
    
- Bill Lee
    
- Bill Logan Jr. 
    
- Sam Bill Lee
    
实例键限制PR_INSTANCE_KEY ( [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性限制）用于实现用于查看 MAPI 表的客户端应用程序的列表框。 某些列表框实现允许用户进行多重选择、向上或向下滚动，并返回到选择的第一个项目。 为了实现此行为，客户端调用 [IMAPITable：：FindRow，](imapitable-findrow.md)将 PR_INSTANCE_KEY **属性的属性** 限制传递给 方法。 通讯簿提供程序需要支持此限制。 
  
用于表查看的列表框的另一个功能是基于一组前缀字符定位光标的功能。 在用户开始键入前缀字符时，客户端会将光标移到以这些字符开头的第一个项目。 客户端通过基于 PR_DISPLAY_NAME **属性和** 模糊级别的内容FL_PREFIX此功能。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

