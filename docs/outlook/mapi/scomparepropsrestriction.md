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
ms.openlocfilehash: 7177b2f0f709939b7580fa7abb87490073bb00c4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588809"
---
# <a name="scomparepropsrestriction"></a>SComparePropsRestriction

**适用于**： Outlook 2013 |Outlook 2016 
  
介绍比较属性限制，测试使用关系运算符的两个属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 要用于比较两个属性的关系运算符。 可能值如下所示：
    
  - RELOP_GE： 比较结果是根据大于或等于的第一个值。
      
  - RELOP_GT： 比较结果是根据更高版本的第一个值。
      
  - RELOP_LE： 进行比较基于上第一个值小于或等于。
      
  - RELOP_LT： 比较结果是根据为较小的第一个值。
      
  - RELOP_NE： 进行比较基于上不相等的值。
      
  - RELOP_RE： 进行比较基于类似 （正则表达式） 值。
      
  - RELOP_EQ： 比较结果是根据相等的值。
    
**ulPropTag1**
  
> 要比较的第一个属性的属性标记。 
    
**ulPropTag2**
  
> 要进行比较的第二个属性的属性标记。
    
## <a name="remarks"></a>注解

比较顺序是 _(1） （关系运算符） 中的属性标记 （属性标记 2）_。 要比较的属性必须属于同一字段类型。 试图比较不同类型的属性将导致从作为参数传递结构是指[IMAPITable](imapitableiunknown.md)方法返回错误值 MAPI_E_TOO_COMPLEX MAPI 或服务提供商。 
  
一个或两个属性不存在时未定义的比较属性值限制结果。 当客户端需要这样的限制定义完善的行为，并且不确保属性是否存在，（例如，不是必需的表格列） 它应创建加入存在比较属性限制**和**限制限制。 使用[SExistRestriction](sexistrestriction.md)结构以定义存在限制和[SAndRestriction](sandrestriction.md)结构，用于定义**和**限制。 
  
如果服务提供商支持，可以是多值的**ulPropTag1**和**ulPropTag2**成员中指定的属性。 
  
有关**SComparePropsRestriction**结构和限制的详细信息，请参阅[有关限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅

- [SBitMaskRestriction](sbitmaskrestriction.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

