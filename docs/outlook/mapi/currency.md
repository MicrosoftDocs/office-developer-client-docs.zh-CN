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
ms.openlocfilehash: 0789b566eb814fe984ae78670d22ad2937b0c3a5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774745"
---
# <a name="currency"></a>CURRENCY

  
  
**适用于**： Outlook 
  
包含表示货币值有符号的 64 位整数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct tagCY
{
  unsigned long Lo;
  long Hi;
} CURRENCY;

```

## <a name="members"></a>Members

 **Lo**
  
> 低序位 32 位的货币值。 
    
 **你好**
  
> 货币值的高顺序 32 位。
    
## <a name="remarks"></a>说明

**货币**结构是十进制数与小数点右边的四位数字的依比例调整的整数表示形式。 例如，存储的值是 32.7500 的 327500 是 32.7500 的解释为表示货币值。 
  
**货币**结构用于描述 PT_CURRENCY 类型的属性。 属性类型有关的信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

