---
title: SGuidArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SGuidArray
api_type:
- COM
ms.assetid: 2091e5fc-75c8-4ea4-87e9-a9bf508e9c58
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 553ec17e9caf9bf93278ff139eb94e02e6b48554
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19778774"
---
# <a name="sguidarray"></a>SGuidArray

  
  
**适用于**： Outlook 
  
包含用于描述 PT_MV_CLSID 类型的属性的[GUID](guid.md)结构的数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SGuidArray
{
  ULONG cValues;
  GUID FAR *lpguid;
} SGuidArray;

```

## <a name="members"></a>成员

 **cValues**
  
> 由**lpguid**成员指向数组中的值的数目。 
    
 **lpguid**
  
> 指针指向包含的类标识符值的**GUID**结构数组。 
    
## <a name="remarks"></a>备注

有关 PT_MV_CLSID 的详细信息，请参阅[列表的属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

