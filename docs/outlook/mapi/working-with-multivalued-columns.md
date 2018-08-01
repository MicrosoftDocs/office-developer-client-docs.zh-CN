---
title: 处理多值列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 911a41c3-c10f-4473-8853-fafb56b721ba
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ee3307836e8b167efbc2cdc870e698257526ef97
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779112"
---
# <a name="working-with-multivalued-columns"></a>处理多值列

  
  
**适用于**： Outlook 
  
多值的列包含的数据的多值属性，这是该属性的值而不是单个值的基类型的数组。 无表在其默认列集合中包含多值的属性，因为多值的属性包含表格中的表的用户请求时，才。 
  
可以在表中显示多值的列：
  
- 在单独一行，与所有显示在单列实例的属性值。 这是默认按钮。
    
    - 或者-
    
- 在一系列的行，通过为每个属性值的一行。 每个唯一值出现在其自己与以下行中的列是因为存在多个行是多值属性中的值。 每个行具有的唯一值**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性，但其他列的相同值。 如果某一行包含多个列与多个值，例如，两个列中的包含_M_ 、 _N_值分别，然后_M\*N_表中显示的行的实例。 
    
表用户请求中的多值列的属性类型设置 MVI_FLAG 标志与调用[IMAPITable::SetColumns](imapitable-setcolumns.md)方法来显示的非默认类型。 MVI_FLAG 标志是定义为 MV_FLAG 和 MV_INSTANCE 标志组合与逻辑**OR**运算的结果的常量。 除了中正使用的**SetColumns**，MVI_FLAG 还可传递给[IMAPITable::SortTable](imapitable-sorttable.md) _lpSortCriteria_参数和[IMAPITable::Restrict](imapitable-restrict.md)中_lpRestriction_的**ulPropTag**成员参数。 当传递 MVI_FLAG，则**SortTable**同样执行到**SetColumns**，在多值列中添加的每个值的一行和实例中的单个值排序。 对于每个值添加了一个行。 
  
 **限制**，但是，不展开多值的列到其他计算行。 使用 MVI_FLAG 集的多值的列指示的服务提供程序，用于限制表中的列。 如果限制中没有属性值，它必须是相同的列[IMAPITable::QueryRows](imapitable-queryrows.md)将返回一个单值属性标记。 
  
表实施只需支持显示的默认类型和呼叫者请求其他替代项时，可以返回 MAPI_E_TOO_COMPLEX 值。 支持两种类型的能力是显示的最重要的消息存储提供程序实现文件夹内容表。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

