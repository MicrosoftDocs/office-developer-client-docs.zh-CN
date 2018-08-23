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
ms.openlocfilehash: d28ce67c6b45f3d0b04d645946ea3f4b3a263c48
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578988"
---
# <a name="iexchangemodifytablegettable"></a>IExchangeModifyTable::GetTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回一个 MAPI table 对象的接口的指针。
  
```cpp
HRESULT GetTable( 
  ULONG ulFlags, 
  LPMAPITABLE FAR * lppTable 
); 

```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为 0 （零）。
    
ACLTABLE_FREEBUSY
  
> 设置新的权限。
    
frightsFreeBusyDetailed
  
> 当 ACLTABLE_FREEBUSY 传递时，提供了详细的显示新的忙/闲信息的权限。
    
frightsFreeBusySimple
  
> 当 ACLTABLE_FREEBUSY 传递时，提供新忙/闲信息的权限的简单的显示。
    
 _lppTable_
  
> [输出]指向[IMAPITable: IUnknown](imapitableiunknown.md)接口包含 table 对象。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|RulesDlg.cpp  <br/> |CRulesDlg::OnRefreshView  <br/> |MFCMAPI 使用**IExchangeModifyTable::GetTable**方法以获取 table 的规则。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

