---
title: SRealArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SRealArray
api_type:
- COM
ms.assetid: 95be07bf-5732-4775-9e0f-fec47e99d9b7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8439d6609ebece75699a1150a9d0c1a41277fd52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429871"
---
# <a name="srealarray"></a>SRealArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一组浮点值，用于描述类型为 PT_MV_R4。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SRealArray
{
  ULONG cValues;
  float FAR *lpflt;
} SRealArray;

```

## <a name="members"></a>Members

 **cValues**
  
> **lpflt** 成员指向的数组中的值计数。 
    
 **lpflt**
  
> 指向浮点值的数组的指针。
    
## <a name="remarks"></a>备注

有关属性类型PT_MV_R4，请参阅属性 [类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

