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
  
描述比较属性限制，该限制使用关系运算符测试两个属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 用于比较这两个属性的关系运算符。 可能的值如下所示：
    
  - RELOP_GE：比较基于大于或等于第一个值。
      
  - RELOP_GT：比较基于较大的第一个值。
      
  - RELOP_LE：比较基于小于或等于第一个值。
      
  - RELOP_LT：比较基于第一个值较小。
      
  - RELOP_NE：基于数值进行比较。
      
  - RELOP_RE：比较基于 LIKE (正则表达式) 值。
      
  - RELOP_EQ：基于相等的值进行比较。
    
**ulPropTag1**
  
> 要比较的第一个属性的属性标记。 
    
**ulPropTag2**
  
> 要比较的第二个属性的属性标记。
    
## <a name="remarks"></a>备注

比较顺序为属性 ( _标记 1，)  (关系运算符)  (标记 2)_。 要比较的属性必须相同类型。 尝试比较不同类型的属性会导致 MAPI 或服务提供商从作为参数MAPI_E_TOO_COMPLEX [IMAPITable](imapitableiunknown.md) 方法返回错误值。 
  
比较属性值限制的结果在一个或两个属性不存在时未定义。 当客户端需要针对此类限制进行明确定义的行为，并且不确定属性是否存在时（例如 (不是表) 的必需列）时，它应创建 **AND** 限制以将比较属性限制与存在限制联接。 使用 [SExistRestriction](sexistrestriction.md) 结构定义存在限制，使用 [SAndRestriction](sandrestriction.md) 结构定义 **AND** 限制。 
  
如果服务提供商支持 **，则 ulPropTag1** 和 **ulPropTag2** 成员中指定的属性可以是多值属性。 
  
有关 **SComparePropsRestriction** 结构和限制的一般详细信息，请参阅关于 [限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅

- [SBitMaskRestriction](sbitmaskrestriction.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

