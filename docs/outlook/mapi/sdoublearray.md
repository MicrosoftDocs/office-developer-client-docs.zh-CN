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
ms.openlocfilehash: 91440d619c8ad8a64b2bac7463a26d9c196a3c0f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439266"
---
# <a name="sdoublearray"></a>SDoubleArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个双精度数组，用于描述类型为 PT_MV_DOUBLE。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SDoubleArray
{
  ULONG cValues;
  double FAR *lpdbl;
} SDoubleArray;

```

## <a name="members"></a>Members

 **cValues**
  
> **lpdbl** 成员指向的数组中的值计数。 
    
 **lpdbl**
  
> 指向双值数组的指针。
    
## <a name="remarks"></a>备注

有关属性类型PT_MV_DOUBLE，请参阅 [属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

