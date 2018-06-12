---
title: 排序和分类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 853c48e4-ef5b-49da-b281-f72784c598ce
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 5e63d276d25a26f937e9b4f44575fea1030f52d0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778832"
---
# <a name="sorting-and-categorization"></a>排序和分类

 
  
**适用于**： Outlook 
  
对表进行排序顺序为其查看器有意义放置行。 例如，一个查看器可能更愿意按邮件主题，以便的对话的所有线程都在一起时另一个查看器可能希望在按发件人名称的消息的文件夹的内容表，请参阅。 新实例化的表一定不按任何特定的顺序。 
  
有两种类型的排序：
  
- 标准排序
    
- 分类排序 
    
使用标准排序的所有行使用一个或多个列作为排序关键字一个平面列表中显示。 与已分类排序，将行显示按层次结构与一个或多个列作为排序关键字。 在每个类别中，没有包含以下列特殊的标题行。
  
- 构成排序关键字的列
    
- **PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))
    
- **PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))
    
- **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))
    
- **PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))
    
- **PR_ROW_TYPE**([PidTagRowType](pidtagrowtype-canonical-property.md)) 
    
标题行下缩进的表中包含值与相匹配的排序关键字列的所有行。 这些行称为叶行。 叶行包含设置减去排序键列列中的所有列。 
  
文件夹的内容表通常支持除了标准排序分类排序。 通讯簿容器的内容表通常支持仅标准排序。 
  
某个类别可有两种状态： 折叠和展开。 折叠状态类别时，从[IMAPITable::QueryRows](imapitable-queryrows.md)返回仅标题行。 展开状态类别时，将返回所有与类别相关的行。 这包括标题行和叶行。 
  
可展开或折叠独立表视图中的每个类别。 即，并非所有类别都必须位于相同的状态在同一时间;某些类别可以折叠时其他人扩展。 
  
分类表的用户决定显示方式。 一个常见选项是使用 Windows SDK 调用 treeview 控件中提供的控件。 Treeview 控件是在树状结构中支持信息的列表框。 处于展开状态的类别的标题行标记有减号时处于折叠状态的类别的标题行标记带加号。 扩展的类别显示带有标题行下缩进的叶行。 
  
若要折叠和展开类别，客户端应用程序或服务提供商使用以下[IMAPITable: IUnknown](imapitableiunknown.md)方法： 
  
- [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
    
- [IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)
    
- [IMAPITable::ExpandRow](imapitable-expandrow.md)
    
- [IMAPITable::CollapseRow](imapitable-collapserow.md)
    
有关排序的详细信息的对话线程，请参阅以下主题：
  
- [SSortOrder](ssortorder.md)
    
- [PidTagSubject 规范属性](pidtagsubject-canonical-property.md)
    
- [PidTagSubjectPrefix 规范属性](pidtagsubjectprefix-canonical-property.md)
    
- [PidTagNormalizedSubject 规范属性](pidtagnormalizedsubject-canonical-property.md)
    
- [PidTagConversationTopic 规范属性](pidtagconversationtopic-canonical-property.md)
    
- [PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)
    
- [ScCreateConversationIndex](sccreateconversationindex.md)
    
- [设置列和限制后排序表](sorting-tables-after-setting-columns-and-restrictions.md)
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

