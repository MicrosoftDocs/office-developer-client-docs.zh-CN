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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344434"
---
# <a name="sproptagarray"></a>SPropTagArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个属性标记数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CbNewSPropTagArray](cbnewsproptagarray.md)、 [CbSPropTagArray](cbsproptagarray.md)、 [SizedSPropTagArray](sizedsproptagarray.md) <br/> |
   
```cpp
typedef struct _SPropTagArray
{
  ULONG cValues;
  ULONG aulPropTag[MAPI_DIM];
} SPropTagArray, FAR *LPSPropTagArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**aulPropTag**成员指示的数组中的属性标记的计数。 
    
 **aulPropTag**
  
> 属性标记数组。
    
## <a name="remarks"></a>注解

属性标记是一个32位无符号整数, 由两部分组成: 
  
- 高顺序16位中的标识符。
    
- 一个低序位16位的类型。
    
标识符是特定区域中的一个数值。 MAPI 为标识符定义范围, 以描述该属性的用途, 以及负责维护该属性的参与者。 MAPI 为在 Mapitags 头文件中支持的每个属性标记定义约束。
  
类型指示属性值的格式。 MAPI 为它在 mapidefs.h 头文件中支持的每个属性类型定义常量。 
  
有关属性标记及其组件的详细信息, 请参阅下列主题之一: 
  
[MAPI 属性标记](mapi-property-tags.md)
  
[MAPI 属性标识符概述](mapi-property-identifier-overview.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)
  
有关单值和多值属性类型的完整列表, 请参阅附录、[属性标识符和类型](property-identifiers-and-types.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

