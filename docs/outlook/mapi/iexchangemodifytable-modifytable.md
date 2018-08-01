---
title: IExchangeModifyTableModifyTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IExchangeModifyTable.ModifyTable
api_type:
- COM
ms.assetid: b9a745cc-260d-4a1c-896e-6a038ab3cfb9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e7f24fb4b444f63b6277d1844a7948f5ab0c590
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775299"
---
# <a name="iexchangemodifytablemodifytable"></a>IExchangeModifyTable::ModifyTable

  
  
**适用于**： Outlook 
  
更新 MAPI table 对象。
  
```cpp
HRESULT ModifyTable( 
  ULONG ulFlags, 
  LPROWLIST lpMods 
); 

```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]使用下列值之一： 
    
0（零）
  
> 使用[ROWENTRY](rowentry.md)结构的**ulRowFlags**成员的值。 
    
ACLTABLE_FREEBUSY
  
> 设置新的权限。
    
frightsFreeBusyDetailed
  
> 当 ACLTABLE_FREEBUSY 传递时，提供了详细的显示新的忙/闲信息的权限。
    
frightsFreeBusySimple
  
> 当 ACLTABLE_FREEBUSY 传递时，提供新忙/闲信息的权限的简单的显示。
    
ROWLIST_REPLACE
  
> 将表中的所有行。
    
 _lpMods_
  
> [in]指向包含 table 对象的属性的[ROWLIST](rowlist.md)结构。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|RulesDlg.cpp  <br/> |CRulesDlg::OnModifySelectedItem  <br/> |MFCMAPI 使用**IExchangeModifyTable::ModifyTable**方法修改的规则写回表中的规则。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)
  
[ROWENTRY](rowentry.md)
  
[ROWLIST](rowlist.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

