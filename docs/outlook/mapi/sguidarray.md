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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bc0ae6d69db6077c17d2efa66d04a5366f2395a0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585568"
---
# <a name="sguidarray"></a>SGuidArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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

## <a name="members"></a>Members

 **cValues**
  
> 由**lpguid**成员指向数组中的值的数目。 
    
 **lpguid**
  
> 指针指向包含的类标识符值的**GUID**结构数组。 
    
## <a name="remarks"></a>注解

有关 PT_MV_CLSID 的详细信息，请参阅[列表的属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

