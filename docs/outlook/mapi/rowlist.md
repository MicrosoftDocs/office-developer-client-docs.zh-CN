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
ms.openlocfilehash: d0427e36d07d1cdc4f88e471f9ca006e737b73f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778656"
---
# <a name="rowlist"></a>ROWLIST

  
  
**适用于**： Outlook 
  
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

