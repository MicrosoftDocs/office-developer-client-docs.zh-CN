---
title: 限制的类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0d3bd58b-7100-4117-91ac-27139715c85b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85cf254c9ea23ecbd6f311ba012d2e048a0b2a6b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572443"
---
# <a name="types-of-restrictions"></a>限制的类型

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
有许多类型的限制，一些该焦点特定的列。 所有表实现都需要支持当前列集合中的列上的限制。 但是，要添加值，表实施者还可以支持基于当前未在表视图中的对象属性限制。
  
可以使用限制的执行逻辑**AND**，**或者**，或**不**运算组合一些限制。 例如，必须使用加入限制的大多数属性都存在使用**和**限制的限制。 有一些例外，如使用属性限制中的属性时**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性时，或者在它是表中所需的列。 构建限制的客户端限制其视图应使用存在其属性限制的限制因为 MAPI 不指定如何服务提供商应评估属性限制当属性不存在。 很合理，建议使用的服务提供商失败此限制，但没有要求。 
  
使用[SRestriction](srestriction.md)数据结构，其中包含的更多专用限制结构联合和联合中包含的结构的类型的指示符定义限制。 
  
每个合并区域中的专用的限制结构表示不同类型的限制。 限制和其关联的数据结构的类型包括：
  
|**类型的限制**|**关联的数据结构**|**说明**|
|:-----|:-----|:-----|
|比较属性  <br/> |[SComparePropsRestriction](scomparepropsrestriction.md) <br/> |比较两个相同类型的属性。  <br/> |
|**AND** <br/> |[SAndRestriction](sandrestriction.md) <br/> |执行两个或多个限制的逻辑**和**操作。  <br/> |
|**或** <br/> |[SOrRestriction](sorrestriction.md) <br/> |执行两个或多个限制逻辑**或**运算。  <br/> |
|**NOT** <br/> |[SNotRestriction](snotrestriction.md) <br/> |执行两个或多个限制逻辑**NOT**操作。  <br/> |
|Content  <br/> |[SContentRestriction](scontentrestriction.md) <br/> |查找指定的数据。  <br/> |
|属性  <br/> |[SPropertyRestriction](spropertyrestriction.md) <br/> |指定特定属性值为匹配条件。 可用于，例如，搜索特定类型的附件。  <br/> |
|Bitmask  <br/> |[SBitMaskRestriction](sbitmaskrestriction.md) <br/> |应用于一个位掩码 PT_LONG 属性，通常以确定是否设置特定的标志。  <br/> |
|Size  <br/> |[SSizeRestriction](ssizerestriction.md) <br/> |测试使用标准关系运算符属性的大小。  <br/> |
|存在  <br/> |[SExistRestriction](sexistrestriction.md) <br/> |测试是否拥有的对象的属性的值。  <br/> |
|子对象  <br/> |[SSubRestriction](ssubrestriction.md) <br/> |用于搜索通过子对象或无法访问与条目标识符，如收件人和附件的对象。 可用，例如，若要查找特定的收件人的邮件。  <br/> |
|Comment  <br/> |[SCommentRestriction](scommentrestriction.md) <br/> |将对象与一组命名属性。  <br/> |
   
一些限制使用正则表达式，并 MAPI 支持有限的窗体使用的多个文本应用程序中的样式表示法的正则表达式。
  
若要保留限制特定于应用程序的信息的磁盘保存限制的客户端使用注释限制。 例如，保存在属性限制中使用的命名属性的名称的客户端可以这样做了一条注释限制。 保存该名称不能在属性限制;[SPropertyRestriction](spropertyrestriction.md)数据结构包含仅属性标记。 注释限制将忽略[IMAPITable::Restrict](imapitable-restrict.md) ，拥有[IMAPITable::QueryRows](imapitable-queryrows.md) **Restrict**呼叫后返回的行没有影响。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

