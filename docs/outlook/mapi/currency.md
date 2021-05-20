---
title: CURRENCY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CURRENCY
api_type:
- COM
ms.assetid: cffc05a0-95e4-4b9f-bf8f-c4272a75afa8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dccb6b19af72d0f748a3a513b7f3d78904ebc789
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431118"
---
# <a name="currency"></a>CURRENCY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个代表货币值的有符号 64 位整数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct tagCY
{
  unsigned long Lo;
  long Hi;
} CURRENCY;

```

## <a name="members"></a>Members

 **Lo**
  
> 货币值的低顺序 32 位。 
    
 **你好**
  
> 货币值的 32 位高顺序值。
    
## <a name="remarks"></a>备注

**CURRENCY** 结构是小数位数的缩放整数表示形式，小数点右边有四位数字。 例如，存储值 327500 应解释为表示货币值 32.7500。 
  
**CURRENCY** 结构用于描述类型为 PT_CURRENCY。 有关属性类型的信息，请参阅 [MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

