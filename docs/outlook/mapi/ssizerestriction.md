---
title: SSizeRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SSizeRestriction
api_type:
- COM
ms.assetid: 4e7340d1-3cb9-4276-b83f-1c8f94acb909
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 134eb844ef7b72d396c300b27a87a3a7ae320cf1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778881"
---
# <a name="ssizerestriction"></a>SSizeRestriction

  
  
**适用于**： Outlook 
  
介绍了用于测试的属性值的大小的大小限制。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SSizeRestriction
{
  ULONG relop;
  ULONG ulPropTag;
  ULONG cb;
} SSizeRestriction;

```

## <a name="members"></a>Members

 **relop**
  
> 是用于大小比较关系运算符。 可能值如下所示： 
    
RELOP_GE 
  
> 基于大于或等于的第一个值进行比较。
    
RELOP_GT 
  
> 基于更高版本的第一个值进行比较。
    
RELOP_LE 
  
> 基于小于或等于的第一个值进行比较。
    
RELOP_LT 
  
> 在较小的第一个值进行比较。
    
RELOP_NE 
  
> 基于不相等的值进行比较。
    
RELOP_RE 
  
> 基于类似 （正则表达式） 值进行比较。
    
RELOP_EQ 
  
> 基于相等的值进行比较。
    
 **ulPropTag**
  
> 属性标记标识要测试的属性。
    
 **cb**
  
> 属性值中的字节数。
    
## <a name="remarks"></a>说明

有关限制的工作方式的一般讨论，请参阅[有关限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

