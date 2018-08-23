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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ccad74a9f2553bf29af124821c6d6a87dcde3303
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572870"
---
# <a name="slpstrarray"></a>SLPSTRArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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

## <a name="members"></a>Members

 **cValues**
  
> 由**lppszA**成员指向数组中的值的数目。 
    
 **lppszA**
  
> 指向一个 null 结束 8 位字符的字符串数组。
    
## <a name="remarks"></a>注解

有关 PT_MV_STRING8 的详细信息，请参阅[列表的属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

