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
ms.openlocfilehash: 9d9fd04776742383f40c6989bcf588b24b33d84b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406778"
---
# <a name="sdatetimearray"></a>SDateTimeArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于描述类型为 PT_MV_SYSTIME 的属性的时间值数组。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SDateTimeArray
{
  ULONG cValues;
  FILETIME FAR *lpft;
} SDateTimeArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpft**成员指向的数组中的值的计数。 
    
 **lpft**
  
> 指向包含时间值的[FILETIME](filetime.md)结构数组的指针。 
    
## <a name="remarks"></a>说明

有关 PT_MV_SYSTIME 的详细信息, 请参阅[属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[FILETIME](filetime.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

