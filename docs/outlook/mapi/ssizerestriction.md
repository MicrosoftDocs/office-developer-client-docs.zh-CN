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
ms.openlocfilehash: 24ceb7b5358447de3a240756227b86224d2c354c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439084"
---
# <a name="ssizerestriction"></a>SSizeRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍用于测试属性值大小的大小限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 大小比较中使用的关系运算符。 可能的值如下所示: 
    
RELOP_GE 
  
> 根据大于或等于的第一个值进行比较。
    
RELOP_GT 
  
> 根据更大的第一个值进行比较。
    
RELOP_LE 
  
> 根据值小于或等于的第一个值进行比较。
    
RELOP_LT 
  
> 根据较小的第一个值进行比较。
    
RELOP_NE 
  
> 根据不相等的值进行比较。
    
RELOP_RE 
  
> 根据 LIKE (正则表达式) 值进行比较。
    
RELOP_EQ 
  
> 根据相等的值进行比较。
    
 **ulPropTag**
  
> 标识要测试的属性的属性标记。
    
 **cb**
  
> 属性值中的字节数。
    
## <a name="remarks"></a>说明

有关限制的工作原理的一般讨论, 请参阅[关于限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

