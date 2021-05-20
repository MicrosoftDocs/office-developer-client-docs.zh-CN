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
  
描述用于测试属性值大小的大小限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 大小比较中使用的关系运算符。 可能的值如下所示： 
    
RELOP_GE 
  
> 比较基于大于或等于第一个值。
    
RELOP_GT 
  
> 比较基于较大的第一个值。
    
RELOP_LE 
  
> 比较基于小于或等于第一个值。
    
RELOP_LT 
  
> 比较基于第一个值较小。
    
RELOP_NE 
  
> 比较基于值。
    
RELOP_RE 
  
> 比较基于 LIKE (正则表达式) 值。
    
RELOP_EQ 
  
> 比较基于相等的值。
    
 **ulPropTag**
  
> 标识要测试的属性的属性标记。
    
 **cb**
  
> 属性值中的字节数。
    
## <a name="remarks"></a>备注

有关限制如何工作的一般讨论，请参阅关于 [限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

