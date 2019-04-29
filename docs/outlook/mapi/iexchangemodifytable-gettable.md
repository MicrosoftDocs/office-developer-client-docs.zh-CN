---
title: IExchangeModifyTableGetTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IExchangeModifyTable.GetTable
api_type:
- COM
ms.assetid: 97df32c4-07c6-41f1-84e7-c6e87d396e34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87c60f424e08eea011bb643041196ca9445a3aa1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436242"
---
# <a name="iexchangemodifytablegettable"></a>IExchangeModifyTable::GetTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回指向 MAPI 表对象的接口的指针。
  
```cpp
HRESULT GetTable( 
  ULONG ulFlags, 
  LPMAPITABLE FAR * lppTable 
); 

```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为 0 (零)。
    
ACLTABLE_FREEBUSY
  
> 设置新权限。
    
frightsFreeBusyDetailed
  
> 当传递 ACLTABLE_FREEBUSY 时, 提供新的忙/闲权限的详细显示。
    
frightsFreeBusySimple
  
> 当传递 ACLTABLE_FREEBUSY 时, 将提供新的忙/闲权限的简单显示。
    
 _lppTable_
  
> 排除指向包含 table 对象的[IMAPITable: IUnknown](imapitableiunknown.md)接口。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|RulesDlg  <br/> |CRulesDlg:: OnRefreshView  <br/> |MFCMAPI 使用**IExchangeModifyTable:: GetTable**方法获取规则表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

