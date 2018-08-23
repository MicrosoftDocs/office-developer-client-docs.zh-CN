---
title: SDoubleArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SDoubleArray
api_type:
- COM
ms.assetid: b63b26de-faf9-453c-ab8b-fb703ed09ae8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6986ed7c9ab9932c5d95fcfb7f74f80088f21971
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580367"
---
# <a name="sdoublearray"></a>SDoubleArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含数组的双精度数用来描述 PT_MV_DOUBLE 类型的属性。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SDoubleArray
{
  ULONG cValues;
  double FAR *lpdbl;
} SDoubleArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpdbl**成员指向数组中的值的数目。 
    
 **lpdbl**
  
> 指向双精度值的数组。
    
## <a name="remarks"></a>注解

有关 PT_MV_DOUBLE 的详细信息，请参阅[列表的属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

