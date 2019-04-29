---
title: 限制类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0d3bd58b-7100-4117-91ac-27139715c85b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28159dfb947b4fb0ea54680627588b7c10bee3b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416284"
---
# <a name="types-of-restrictions"></a>限制类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有多种类型的限制, 有些是重点关注特定的列。 所有表实现都应支持对当前列集中的列的限制。 但是, 若要添加值, 表实施者还可以基于当前不在表视图中的对象属性支持限制。
  
可以使用执行逻辑**AND**、 **or**或**NOT**运算的限制组合一些限制。 例如, 大多数属性限制必须使用**和**限制加入存在的限制。 有一些例外情况, 例如, 在属性限制中使用的属性是**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性或表中的必需列。 客户端生成限制以限制其视图应使用存在的限制及其属性限制, 因为 MAPI 不指定当属性不存在时服务提供程序应如何评估属性限制。 合理且建议服务提供商失败限制, 但没有任何要求。 
  
限制是使用[SRestriction](srestriction.md)数据结构定义的, 其中包含更多专用限制结构的联合以及联合中包含的结构类型的指示器。 
  
union 中的每个专用限制结构都代表不同类型的限制。 限制的类型及其关联的数据结构为:
  
|**限制的类型**|**关联的数据结构**|**说明**|
|:-----|:-----|:-----|
|Compare 属性  <br/> |[SComparePropsRestriction](scomparepropsrestriction.md) <br/> |比较同一类型的两个属性。  <br/> |
|**AND** <br/> |[SAndRestriction](sandrestriction.md) <br/> |对两个或更多个限制执行逻辑**AND**运算。  <br/> |
|**或** <br/> |[SOrRestriction](sorrestriction.md) <br/> |对两个或更多个限制执行逻辑**OR**运算。  <br/> |
|**NOT** <br/> |[SNotRestriction](snotrestriction.md) <br/> |对两个或更多个限制执行逻辑**非**运算。  <br/> |
|内容  <br/> |[SContentRestriction](scontentrestriction.md) <br/> |查找指定数据。  <br/> |
|属性  <br/> |[SPropertyRestriction](spropertyrestriction.md) <br/> |将特定的属性值指定为匹配的条件。 例如, 可用于搜索特定类型的附件。  <br/> |
|Bitmask  <br/> |[SBitMaskRestriction](sbitmaskrestriction.md) <br/> |将位掩码应用于 PT_LONG 属性, 通常用于确定是否设置了特定的标志。  <br/> |
|大小  <br/> |[SSizeRestriction](ssizerestriction.md) <br/> |使用标准关系运算符测试属性的大小。  <br/> |
|尚  <br/> |[SExistRestriction](sexistrestriction.md) <br/> |测试对象是否具有属性的值。  <br/> |
|子  <br/> |[SSubRestriction](ssubrestriction.md) <br/> |用于搜索子对象, 或使用条目标识符无法访问的对象, 例如收件人和附件。 例如, 可用于查找特定收件人的邮件。  <br/> |
|注释  <br/> |[SCommentRestriction](scommentrestriction.md) <br/> |将对象与一组命名属性相关联。  <br/> |
   
某些限制使用正则表达式, 而 MAPI 在使用许多文本应用程序的样式中支持有限形式的正则表达式表示法。
  
在磁盘上保存限制的客户端使用注释限制, 以保留特定于应用程序的信息和限制。 例如, 在属性限制中保存所使用的命名属性的名称的客户端可以使用注释限制执行此操作。 在属性限制中不能保存名称;[SPropertyRestriction](spropertyrestriction.md)数据结构仅保存属性标记。 [IMAPITable:: restrict](imapitable-restrict.md)将忽略注释限制, 使其对[imapitable:: QueryRows](imapitable-queryrows.md)返回的行不起作用。在进行**限制**调用之后。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

