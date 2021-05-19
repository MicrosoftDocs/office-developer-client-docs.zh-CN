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
ms.openlocfilehash: 46bb9b2cc1a4d54807d6929b4e1439b58fb3a531
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418174"
---
# <a name="iexchangemodifytablemodifytable"></a>IExchangeModifyTable::ModifyTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
更新 MAPI 表对象。
  
```cpp
HRESULT ModifyTable( 
  ULONG ulFlags, 
  LPROWLIST lpMods 
); 

```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]使用以下值之一： 
    
0（零）
  
> 使用 [ROWENTRY](rowentry.md)结构的 **ulRowFlags** 成员的值。 
    
ACLTABLE_FREEBUSY
  
> 设置新权限。
    
frightsFreeBusyDetailed
  
> 传递ACLTABLE_FREEBUSY时，提供新的忙/闲权限的详细显示。
    
frightsFreeBusySimple
  
> 传递ACLTABLE_FREEBUSY时，提供新的忙/闲权限的简单显示。
    
ROWLIST_REPLACE
  
> 替换表中的所有行。
    
 _lpMods_
  
> [in]指向包含 table 对象属性的 [ROWLIST](rowlist.md) 结构。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|RulesDlg.cpp  <br/> |CRulesDlg：：OnModifySelectedItem  <br/> |MFCMAPI 使用 **IExchangeModifyTable：：ModifyTable** 方法将修改后的规则写回规则表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)
  
[ROWENTRY](rowentry.md)
  
[ROWLIST](rowlist.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

