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
ms.openlocfilehash: 5237a5c2767920bdb604bfe86603cea4fca56b84
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572772"
---
# <a name="sproptagarray"></a>SPropTagArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含数组属性标记。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbNewSPropTagArray](cbnewsproptagarray.md)， [CbSPropTagArray](cbsproptagarray.md)， [SizedSPropTagArray](sizedsproptagarray.md) <br/> |
   
```cpp
typedef struct _SPropTagArray
{
  ULONG cValues;
  ULONG aulPropTag[MAPI_DIM];
} SPropTagArray, FAR *LPSPropTagArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 属性数组由**aulPropTag**成员中的标记的计数。 
    
 **aulPropTag**
  
> 属性标记的数组。
    
## <a name="remarks"></a>注解

属性标记是一个 32 位无符号的整数，由两部分组成： 
  
- 中高阶 16 位的标识符。
    
- 低序位 16 位中的类型。
    
标识符是一个数值在特定范围内。 MAPI 定义标识符来描述属性用于和谁负责维护它的区域。 MAPI 属性标记它 Mapitags.h 头文件中所支持的每个定义的约束。
  
该类型指示该属性的值的格式。 MAPI 的属性类型，它支持 Mapidefs.h 头文件中的每个定义的常数。 
  
有关属性标记及其组件的详细信息，请参阅以下主题之一： 
  
[MAPI 属性标记](mapi-property-tags.md)
  
[MAPI 属性标识符概述](mapi-property-identifier-overview.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)
  
单值和多值属性类型的完整列表，请参阅附录[属性标识符和类型](property-identifiers-and-types.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

