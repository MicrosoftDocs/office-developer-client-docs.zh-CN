---
title: SPropTagArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropTagArray
api_type:
- COM
ms.assetid: 4a9e1579-bebe-4a51-8ced-6dba9c3bcb63
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9a5be98298ab1f9333ac1c223a6ef594e60dd86a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430698"
---
# <a name="sproptagarray"></a>SPropTagArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含属性标记的数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[](cbnewsproptagarray.md)CbNewSPropTagArray、CbSPropTagArray、SizedSPropTagArray [](cbsproptagarray.md) [](sizedsproptagarray.md) <br/> |
   
```cpp
typedef struct _SPropTagArray
{
  ULONG cValues;
  ULONG aulPropTag[MAPI_DIM];
} SPropTagArray, FAR *LPSPropTagArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由 **aulPropTag** 成员指示的数组中的属性标记计数。 
    
 **aulPropTag**
  
> 属性标记数组。
    
## <a name="remarks"></a>备注

属性标记是一个 32 位无符号整数，由两部分组成： 
  
- 高顺序 16 位中的标识符。
    
- 低顺序 16 位中的类型。
    
标识符是特定范围中的数值。 MAPI 为标识符定义范围，以描述属性用于什么以及谁负责维护它。 MAPI 为 Mapitags.h 头文件中支持的每个属性标记定义约束。
  
类型指示属性值的格式。 MAPI 为 Mapidefs.h 头文件中支持的每个属性类型定义常量。 
  
有关属性标记及其组件的信息，请参阅下列主题之一： 
  
[MAPI 属性标记](mapi-property-tags.md)
  
[MAPI 属性标识符概述](mapi-property-identifier-overview.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)
  
有关单值和多值属性类型的完整列表，请参阅附录属性 [标识符和类型](property-identifiers-and-types.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

