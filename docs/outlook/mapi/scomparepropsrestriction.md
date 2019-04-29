---
title: SComparePropsRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SComparePropsRestriction
api_type:
- COM
ms.assetid: 3231a91a-1ef2-4dd8-9f3e-79ca56d2eae9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 513ec0db4e99e687d8aeb9e1d6acdef73df4d158
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33440001"
---
# <a name="scomparepropsrestriction"></a>SComparePropsRestriction

**适用于**：Outlook 2013 | Outlook 2016 
  
介绍 compare 属性限制, 该限制使用关系运算符测试两个属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SComparePropsRestriction
{
  ULONG relop;
  ULONG ulPropTag1;
  ULONG ulPropTag2;
} SComparePropsRestriction;

```

## <a name="members"></a>Members

**relop**
  
> 用于比较这两个属性的关系运算符。 可能的值如下所示:
    
  - RELOP_GE: 根据一个大于或等于的第一个值进行比较。
      
  - RELOP_GT: 根据更大的第一个值进行比较。
      
  - RELOP_LE: 基于一个小于或等于的第一个值进行比较。
      
  - RELOP_LT: 基于较小的第一个值进行比较。
      
  - RELOP_NE: 根据不相等的值进行比较。
      
  - RELOP_RE: 根据 LIKE (正则表达式) 值进行比较。
      
  - RELOP_EQ: 根据相等的值进行比较。
    
**ulPropTag1**
  
> 要比较的第一个属性的属性标记。 
    
**ulPropTag2**
  
> 要比较的第二个属性的属性标记。
    
## <a name="remarks"></a>说明

比较顺序为 _(属性标记 1) (关系运算符) (属性标记 2)_。 要进行比较的属性必须具有相同的类型。 尝试比较不同类型的属性会导致 MAPI 或服务提供程序返回错误值 MAPI_E_TOO_COMPLEX 从将结构作为参数传递到的[IMAPITable](imapitableiunknown.md)方法。 
  
如果一个或两个属性不存在, 则 compare 属性值限制的结果将未定义。 当客户端需要此类限制的定义良好的行为且不确定该属性是否存在时 (例如, 它不是表中的必需列), 应创建**和**限制以将 compare 属性限制加入存在限制. 使用[SExistRestriction](sexistrestriction.md)结构定义存在限制和[SAndRestriction](sandrestriction.md)结构以定义**和**限制。 
  
如果服务提供程序支持, 在**ulPropTag1**和**ulPropTag2**成员中指定的属性可以是多值的。 
  
有关**SComparePropsRestriction**结构和限制的详细信息, 请参阅[关于限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅

- [SBitMaskRestriction](sbitmaskrestriction.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

