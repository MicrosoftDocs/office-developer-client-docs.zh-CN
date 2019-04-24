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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350839"
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
  
> 实时使用下列值之一: 
    
0（零）
  
> 使用[ROWENTRY](rowentry.md)结构的**ulRowFlags**成员的值。 
    
ACLTABLE_FREEBUSY
  
> 设置新权限。
    
frightsFreeBusyDetailed
  
> 当传递 ACLTABLE_FREEBUSY 时, 提供新的忙/闲权限的详细显示。
    
frightsFreeBusySimple
  
> 当传递 ACLTABLE_FREEBUSY 时, 将提供新的忙/闲权限的简单显示。
    
ROWLIST_REPLACE
  
> 替换表中的所有行。
    
 _lpMods_
  
> 实时指向一个[ROWLIST](rowlist.md)结构, 其中包含 table 对象的属性。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|RulesDlg  <br/> |CRulesDlg:: OnModifySelectedItem  <br/> |MFCMAPI 使用**IExchangeModifyTable:: ModifyTable**方法将修改的规则写回到规则表中。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)
  
[ROWENTRY](rowentry.md)
  
[ROWLIST](rowlist.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

