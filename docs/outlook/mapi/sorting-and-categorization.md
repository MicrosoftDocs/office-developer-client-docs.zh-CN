---
title: 排序和分类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 853c48e4-ef5b-49da-b281-f72784c598ce
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: 8a5a07cdeb7f000c9a7da24dbea1a42a6f9fc185
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418482"
---
# <a name="sorting-and-categorization"></a>排序和分类

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对表进行排序会按对查看者有意义的顺序对行进行排序。 例如，一个查看者可能更希望查看按邮件主题排序的文件夹的内容表，以便对话的所有线程在一起，而另一个查看者可能希望邮件按发件人姓名排序。 新实例化表不一定按任何特定顺序排序。 
  
有两种类型的排序：
  
- 标准排序
    
- 分类排序 
    
使用标准排序，所有行都显示在一个简单列表一个或多个列作为排序键。 使用分类排序，这些行按层次结构显示，一列或多列作为排序键。 在每个类别中，都有一个包含以下列的特殊标题行。
  
- 组成排序键的列
    
- **PR_CONTENT_COUNT (** [PidTagContentCount](pidtagcontentcount-canonical-property.md)) 
    
- **PR_CONTENT_UNREAD (** [PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md)) 
    
- **PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 
    
- **PR_DEPTH (** [PidTagDepth](pidtagdepth-canonical-property.md)) 
    
- **PR_ROW_TYPE (** [PidTagRowType](pidtagrowtype-canonical-property.md))  
    
标题行下缩进是表中所有包含与排序键匹配的值的列的行。 这些行称为叶行。 叶行包含列集的所有列减去排序键列。 
  
文件夹的内容表通常除了支持标准排序之外，还支持分类排序。 通讯簿容器的内容表通常仅支持标准排序。 
  
类别可以有两种状态：折叠和展开。 当类别为折叠状态时，仅从 [IMAPITable：：QueryRows 返回标题行](imapitable-queryrows.md)。 当类别为展开状态时，将返回与类别相关的所有行。 这包括标题行和叶行。 
  
表视图中的每个类别都可以独立展开或折叠。 也就是说，并非所有类别必须同时处于同一状态;某些类别可以折叠，而其他类别可以展开。 
  
已分类表的用户决定其显示方式。 一个常见选项是使用 Windows SDK 中提供的控件，称为树视图控件。 树视图控件是支持树状结构中的信息的列表框。 展开状态中类别的标题行标有减号，折叠状态中类别的标题行标有加号。 展开的类别显示在标题行下缩进的叶行。 
  
为了折叠和展开类别，客户端应用程序或服务提供商使用下列 [IMAPITable ： IUnknown](imapitableiunknown.md) 方法： 
  
- [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
    
- [IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)
    
- [IMAPITable::ExpandRow](imapitable-expandrow.md)
    
- [IMAPITable::CollapseRow](imapitable-collapserow.md)
    
有关对对话线程进行排序的信息，请参阅下列主题：
  
- [SSortOrder](ssortorder.md)
    
- [PidTagSubject 规范属性](pidtagsubject-canonical-property.md)
    
- [PidTagSubjectPrefix 规范属性](pidtagsubjectprefix-canonical-property.md)
    
- [PidTagNormalizedSubject 规范属性](pidtagnormalizedsubject-canonical-property.md)
    
- [PidTagConversationTopic 规范属性](pidtagconversationtopic-canonical-property.md)
    
- [PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)
    
- [ScCreateConversationIndex](sccreateconversationindex.md)
    
- [设置列和限制后对表进行排序](sorting-tables-after-setting-columns-and-restrictions.md)
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

