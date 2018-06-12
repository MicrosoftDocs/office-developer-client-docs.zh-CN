---
title: SLPSTRArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SLPSTRArray
api_type:
- COM
ms.assetid: 5f570d9b-eb3d-4fc7-bcbe-348a0b8fe9e9
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6d2bb6bdb934e0b02831b813b1246a3df4193e0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778818"
---
# <a name="slpstrarray"></a>SLPSTRArray

  
  
**适用于**： Outlook 
  
包含用于描述 PT_MV_STRING8 类型的属性的字符串值的数组。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SLPSTRArray
{
  ULONG cValues;
  LPSTR FAR *lppszA;
} SLPSTRArray;

```

## <a name="members"></a>成员

 **cValues**
  
> 由**lppszA**成员指向数组中的值的数目。 
    
 **lppszA**
  
> 指向一个 null 结束 8 位字符的字符串数组。
    
## <a name="remarks"></a>备注

有关 PT_MV_STRING8 的详细信息，请参阅[列表的属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

