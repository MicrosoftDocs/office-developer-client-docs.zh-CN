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
ms.openlocfilehash: 987020bd6fd49fcba9453075cd502bd5cea4c3a3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435906"
---
# <a name="slpstrarray"></a>SLPSTRArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个字符串值数组，用于描述类型为 PT_MV_STRING8。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SLPSTRArray
{
  ULONG cValues;
  LPSTR FAR *lppszA;
} SLPSTRArray;

```

## <a name="members"></a>Members

 **cValues**
  
> **lppszA** 成员指向的数组中的值计数。 
    
 **lppszA**
  
> 指向以 null 结束的 8 位字符字符串数组的指针。
    
## <a name="remarks"></a>备注

有关属性类型PT_MV_STRING8，请参阅 [属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

