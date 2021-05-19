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
  
多值列包含多值属性的数据，多值属性是一个包含基类型的值的数组而不是单个值的属性。 因为任何表的默认列集都没有多值属性，所以只有当表的用户请求表时，多值属性才包含在表中。 
  
多值列可以显示在表中：
  
- 在单行中，所有属性值都显示在单个列实例中。 这是默认选项。
    
    - 或 -
    
- 在一系列行中，每个属性值各有一行。 每个唯一值都显示在列内自己的行中，行数与多值属性中的值数一样。 每行具有[PidTagInstanceKey](pidtaginstancekey-canonical-property.md) PR_INSTANCE_KEY (的唯一) ，但其他列的值相同。  如果一行包含多个具有多个值的列，例如，两列分别具有  _M_ 和  _N_ 值，则  _行的 M \* N_ 实例将显示在表中。 
    
表用户通过调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 方法请求非默认类型的显示，该方法具有在多值列的属性类型中设置的 MVI_FLAG 标志。 the MVI_FLAG flag is a constant defined as the result of combining the MV_FLAG and MV_INSTANCE flags with a logical **OR** operation. 除了在 **SetColumns** 中使用之外，MVI_FLAG 还可以传递到 _lpSortCriteria_ 参数中的 [IMAPITable：：SortTable](imapitable-sorttable.md)和 _lpRestriction_ 参数的 **ulPropTag** 成员中的 [IMAPITable：：Restrict。](imapitable-restrict.md) 在传递MVI_FLAG时 **，SortTable** 的执行方式与 **SetColumns** 类似，即为多值列的每个值添加一行，并按实例中的单个值进行排序。 每一个值添加一行。 
  
 **但是**，Restrict 不会将多值列展开到其他计算行中。 具有值集的多值MVI_FLAG指示服务提供商在限制表时使用该列。 如果限制中具有属性值，则它必须是一个值属性标记，该标记与 [IMAPITable：：QueryRows](imapitable-queryrows.md) 为列返回的值属性标记相同。 
  
表实现器只需要支持默认的显示类型，并且当调用方请求其他备选MAPI_E_TOO_COMPLEX可以返回值。 对于实现文件夹内容表的邮件存储提供程序来说，支持这两种显示类型的能力非常重要。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

