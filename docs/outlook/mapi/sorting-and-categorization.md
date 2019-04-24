---
title: 排序和分类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 853c48e4-ef5b-49da-b281-f72784c598ce
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 8a5a07cdeb7f000c9a7da24dbea1a42a6f9fc185
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344504"
---
# <a name="sorting-and-categorization"></a>排序和分类

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对表进行排序时, 会按对其查看器有意义的顺序放置行。 例如, 一个查看者可能更愿意查看按邮件主题排序的文件夹的内容表, 以便会话的所有线程都在一起, 而另一个查看器可能希望邮件按发件人的姓名进行排序。 新实例化的表不一定以任何特定的顺序进行排序。 
  
有两种类型的排序:
  
- 标准排序
    
- 分类排序 
    
使用标准排序, 所有行都显示在简单列表中, 使用一个或多个列作为排序关键字。 通过分类排序, 行以分层方式显示, 并显示一个或多个列作为排序关键字。 在每个类别中, 都有一个特殊的标题行, 其中包含以下列。
  
- 组成排序关键字的一个或多个列
    
- **PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))
    
- **PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))
    
- **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))
    
- **PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))
    
- **PR_ROW_TYPE**([PidTagRowType](pidtagrowtype-canonical-property.md)) 
    
在标题行下缩进是表中的所有行, 其中包含值与排序关键字相匹配的列。 这些行称为叶行。 叶行包含列集中的所有列减去排序关键字列。 
  
除了标准排序之外, 文件夹的内容表通常支持分类排序。 通讯簿容器的内容表通常只支持标准排序。 
  
一个类别可以有两种状态: 折叠和展开。 当类别处于折叠状态时, 仅从[IMAPITable:: QueryRows](imapitable-queryrows.md)返回标题行。 当类别处于展开状态时, 将返回与该类别相关的所有行。 这包括标题行和叶行。 
  
表视图中的每个类别都可以单独展开或折叠。 也就是说, 并非所有类别都必须处于相同的状态。某些类别可以折叠, 而其他类别则展开。 
  
已分类的表格的用户决定它的显示方式。 一个常见的选项是使用 Windows SDK 中提供的一个名为 treeview 控件的控件。 Treeview 控件是支持树状结构中的信息的列表框。 展开状态中的类别的标题行标记为负号, 而折叠状态中的类别的标题行标有加号。 展开的类别将显示在标题行下缩进的叶行。 
  
若要折叠和展开类别, 客户端应用程序或服务提供程序使用以下[IMAPITable: IUnknown](imapitableiunknown.md)方法: 
  
- [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
    
- [IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)
    
- [IMAPITable::ExpandRow](imapitable-expandrow.md)
    
- [IMAPITable::CollapseRow](imapitable-collapserow.md)
    
有关对对话的线程进行排序的详细信息, 请参阅下列主题:
  
- [SSortOrder](ssortorder.md)
    
- [PidTagSubject 规范属性](pidtagsubject-canonical-property.md)
    
- [PidTagSubjectPrefix 规范属性](pidtagsubjectprefix-canonical-property.md)
    
- [PidTagNormalizedSubject 规范属性](pidtagnormalizedsubject-canonical-property.md)
    
- [PidTagConversationTopic 规范属性](pidtagconversationtopic-canonical-property.md)
    
- [PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)
    
- [ScCreateConversationIndex](sccreateconversationindex.md)
    
- [设置列和限制后对表排序](sorting-tables-after-setting-columns-and-restrictions.md)
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

