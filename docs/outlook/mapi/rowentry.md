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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: f8ac73b1977886208290285fec2d1bd0de1b4f92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778658"
---
# <a name="rowentry"></a>ROWENTRY

**适用于**： Outlook 
  
包含的行和通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)界面表中的行执行的操作。 
  
```cpp
typedef struct
{
  ULONG         ulRowFlags;
  ULONG         cValues;
  LPSPropValue  rgPropVals;
}  ROWENTRY, FAR * LPROWENTRY;
```

## <a name="members"></a>成员

**ulRowFlags**
  
> 对数据执行以下操作之一： 
    
  - ROW_ADD： 将数据添加到表作为新行。
      
  - ROW_MODIFY： 修改此表中的行。
      
  - ROW_REMOVE： 从表中删除此行。
      
  - ROW_EMPTY： 不要向表中添加行数据。 （行为空。）
    
**cValues**
  
> **RgPropvals**中的属性值的数目。
    
**rgPropVals**
  
> [SPropValue](spropvalue.md)结构表示要插入到表的列值的数组。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|RulesDlg.cpp  <br/> |CRulesDlg::GetSelectedItems  <br/> |用于生成的后续**ModifyTable**操作选定的规则列表。  <br/> |
   
## <a name="see-also"></a>另请参阅
  
- [IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)
- [MAPI 结构](mapi-structures.md)

