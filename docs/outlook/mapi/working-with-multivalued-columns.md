---
title: 使用多值列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 911a41c3-c10f-4473-8853-fafb56b721ba
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 34f19e279c86e0c0856d242cf2aa13d744d46f13
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420183"
---
# <a name="working-with-multivalued-columns"></a>使用多值列

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
多值列包含多值属性的数据, 这是一个具有基类型的值数组而不是单个值的属性。 由于没有表在其默认列集中包含多值属性, 只有当表的用户请求多值属性时, 才会将这些属性包含在表中。 
  
多值列可在表中显示:
  
- 在单个行中, 所有属性值显示在单个列实例中。 此为默认选项。
    
    - 和
    
- 在一系列行中, 每个属性值占一行。 每个唯一值显示在其自己的行中的列中, 其中的行数与多值属性中的值相同。 每行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性的值都是唯一的, 但其他列的值相同。 如果某行包含多个值的多个列 (例如, 分别具有_M_和_N_个值的两个列), 则在表中显示该行的_M\*N_个实例。 
    
通过调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法并在多值列的属性类型中设置 MVI_FLAG 标志, 表用户将请求显示非默认类型的显示。 MVI_FLAG 标志是一个常量, 定义为将 MV_FLAG 和 MV_INSTANCE 标志与逻辑**OR**运算结合使用的结果。 除了在**SetColumns**中使用之外, 还可以将 MVI_FLAG 传递到_lpSortCriteria_参数中的[imapitable:: SortTable](imapitable-sorttable.md)和[imapitable:: Restrict](imapitable-restrict.md) in _ulPropTag_的**lpRestriction**成员参数. 传递 MVI_FLAG 时, **SortTable**的执行方式类似于**SetColumns**, 为多值列中的每个值添加一行, 并对实例中的单个值进行排序。 为每个值添加一个行。 
  
 但是,**限制**不会将多值列展开为其他计算行。 带有 MVI_FLAG 集的多值列指示服务提供程序在限制表时使用该列。 如果限制中有属性值, 则它必须是与将由[IMAPITable:: QueryRows](imapitable-queryrows.md)为列返回的值相同的单个值属性标记。 
  
表实施者只需支持默认类型的显示, 并且可以在呼叫者请求其他替代项时返回 MAPI_E_TOO_COMPLEX 值。 支持这两种类型的显示对实现文件夹内容表的邮件存储提供程序最重要。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

