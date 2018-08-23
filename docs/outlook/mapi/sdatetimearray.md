---
title: SDateTimeArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SDateTimeArray
api_type:
- COM
ms.assetid: 6a0dff65-1055-487c-9d15-4cfe336f2ad7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dc90f15835de35354a271d87a736366a4caf8dd9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578778"
---
# <a name="sdatetimearray"></a>SDateTimeArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含用于描述 PT_MV_SYSTIME 类型的属性的时间值的数组。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SDateTimeArray
{
  ULONG cValues;
  FILETIME FAR *lpft;
} SDateTimeArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpft**成员指向数组中的值的数目。 
    
 **lpft**
  
> 指向一个[FILETIME](filetime.md)结构包含时间值的数组。 
    
## <a name="remarks"></a>注解

有关 PT_MV_SYSTIME 的详细信息，请参阅[列表的属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[FILETIME](filetime.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

