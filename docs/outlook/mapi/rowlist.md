---
title: ROWLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ROWLIST
api_type:
- COM
ms.assetid: ce0be0d5-4962-4d53-828f-c93d1c5aae32
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c13b741b1e0ddfd964b9325d736a26dac4bff2af
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419182"
---
# <a name="rowlist"></a>ROWLIST

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含[ROWENTRY](rowentry.md)结构的数组, 这些结构表示通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口对表中的这些行执行的行和操作。 
  
```cpp
typedef struct
{
  ULONG     cEntries;
  ROWENTRY  aEntries[MAPI_DIM];
}  ROWLIST, FAR * LPROWLIST;

```

## <a name="members"></a>Members

 **cEntries**
  
> 由**aEntries**成员指定的数组中的条目数。 
    
 **aEntries [MAPI_DIM]**
  
> **ROWENTRY**结构的数组, 其中包含在表中对这些行执行的行和操作。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|RulesDlg  <br/> |CRulesDlg:: GetSelectedItems  <br/> |用于为后续**ModifyTable**操作生成选定规则的列表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ROWENTRY](rowentry.md)
  
[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MAPI 结构](mapi-structures.md)

