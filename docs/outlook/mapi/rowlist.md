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
ms.openlocfilehash: 4cbaf08c58a98be45ad33aebb8f230fb53c234f3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577658"
---
# <a name="rowlist"></a>ROWLIST

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个表示行和通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)界面表格中的行上执行的操作的[ROWENTRY](rowentry.md)结构数组。 
  
```cpp
typedef struct
{
  ULONG     cEntries;
  ROWENTRY  aEntries[MAPI_DIM];
}  ROWLIST, FAR * LPROWLIST;

```

## <a name="members"></a>Members

 **cEntries**
  
> 指定由**aEntries**成员的数组中的条目的计数。 
    
 **aEntries [MAPI_DIM]**
  
> **ROWENTRY**结构数组，其中包含的行和表中的行上执行的操作。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|RulesDlg.cpp  <br/> |CRulesDlg::GetSelectedItems  <br/> |用于生成的后续**ModifyTable**操作选定的规则列表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ROWENTRY](rowentry.md)
  
[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MAPI 结构](mapi-structures.md)

