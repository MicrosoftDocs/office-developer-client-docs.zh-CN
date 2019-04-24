---
title: ROWENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ROWENTRY
api_type:
- COM
ms.assetid: bd6c0d8e-68cc-4d60-9029-13ed81c816cd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 243ab1e926171ee66b95cfd8e969cd77e2b31faf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279599"
---
# <a name="rowentry"></a>ROWENTRY

**适用于**：Outlook 2013 | Outlook 2016 
  
包含通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口在表的行上执行的行和操作。 
  
```cpp
typedef struct
{
  ULONG         ulRowFlags;
  ULONG         cValues;
  LPSPropValue  rgPropVals;
}  ROWENTRY, FAR * LPROWENTRY;
```

## <a name="members"></a>Members

**ulRowFlags**
  
> 要对数据执行以下操作之一: 
    
  - ROW_ADD: 将数据作为新行添加到表中。
      
  - ROW_MODIFY: 修改表中的此行。
      
  - ROW_REMOVE: 从表中删除此行。
      
  - ROW_EMPTY: 不要将行数据添加到表中。 (行是空的。)
    
**cValues**
  
> **rgPropvals**中的属性值的数目。
    
**rgPropVals**
  
> [SPropValue](spropvalue.md)结构的数组, 这些结构表示要插入到表中的列的值。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|RulesDlg  <br/> |CRulesDlg:: GetSelectedItems  <br/> |用于为后续**ModifyTable**操作生成选定规则的列表。  <br/> |
   
## <a name="see-also"></a>另请参阅
  
- [IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)
- [MAPI 结构](mapi-structures.md)

