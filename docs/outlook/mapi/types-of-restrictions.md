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
  
存在许多类型的限制，其中一些限制侧重于特定列。 所有表实现应支持对当前列集内列的限制。 但是，若要添加值，表实施者还可以支持基于当前不在表视图中的对象属性的限制。
  
可以使用执行逻辑 **AND、OR** 或 **NOT** 操作的限制来组合某些限制。 例如，必须使用 AND 限制将大多数属性限制与 **存在限制联接** 。 有一些例外情况，例如当属性限制中使用的属性是 **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性时，或者当该属性是表格中的必需列时。 用于限制其视图的客户端构建限制应该使用具有属性限制的已存在限制，因为 MAPI 不指定当属性不存在时，服务提供商如何评估属性限制。 建议服务提供商不满足限制，但没有任何要求，这是合理的。 
  
限制是使用 [SRestriction 数据结构定义的，SRestriction](srestriction.md) 数据结构包含一组更专门的限制结构和联合中包含的结构类型的指示器。 
  
联合中的每个专用限制结构表示不同类型的限制。 限制类型及其关联的数据结构包括：
  
|**限制类型**|**关联的数据结构**|**说明**|
|:-----|:-----|:-----|
|Compare 属性  <br/> |[SComparePropsRestriction](scomparepropsrestriction.md) <br/> |比较同一类型的两个属性。  <br/> |
|AND <br/> |[SAndRestriction](sandrestriction.md) <br/> |对两个或多个限制执行逻辑 **AND** 操作。  <br/> |
|**OR** <br/> |[SOrRestriction](sorrestriction.md) <br/> |对两个或多个限制执行逻辑 **OR** 操作。  <br/> |
|**NOT** <br/> |[SNotRestriction](snotrestriction.md) <br/> |对两个或多个限制执行逻辑 **NOT** 操作。  <br/> |
|Content  <br/> |[SContentRestriction](scontentrestriction.md) <br/> |查找指定数据。  <br/> |
|属性  <br/> |[SPropertyRestriction](spropertyrestriction.md) <br/> |指定特定属性值作为匹配条件。 例如，可用于搜索特定类型的附件。  <br/> |
|Bitmask  <br/> |[SBitMaskRestriction](sbitmaskrestriction.md) <br/> |将位掩码应用于PT_LONG，通常用于确定是否设置了特定标志。  <br/> |
|Size  <br/> |[SSizeRestriction](ssizerestriction.md) <br/> |使用标准关系运算符测试属性的大小。  <br/> |
|存在  <br/> |[SExistRestriction](sexistrestriction.md) <br/> |测试对象是否具有属性的值。  <br/> |
|子对象  <br/> |[SSubRestriction](ssubrestriction.md) <br/> |用于搜索子对象，或无法使用条目标识符访问的对象，例如收件人和附件。 例如，可用于查找特定收件人的邮件。  <br/> |
|评论  <br/> |[SCommentRestriction](scommentrestriction.md) <br/> |将对象与一组命名属性关联。  <br/> |
   
某些限制使用正则表达式，MAPI 支持采用许多文本应用程序的样式中的有限形式的正则表达式表示法。
  
注释限制由在磁盘上保存限制的客户端使用，以保留具有限制的应用程序特定信息。 例如，保存属性限制中使用的命名属性的名称的客户端可以使用注释限制来这样做。 在属性限制中无法保存名称; [SPropertyRestriction](spropertyrestriction.md) 数据结构仅保留属性标记。 [IMAPITable：：Restrict](imapitable-restrict.md)将忽略注释限制，因为它们在执行 **Restrict** 调用后对 [IMAPITable：：QueryRows](imapitable-queryrows.md)返回的行没有影响。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

