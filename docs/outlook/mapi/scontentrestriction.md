---
title: SContentRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SContentRestriction
api_type:
- COM
ms.assetid: 784c8a5a-493e-48e6-8784-ba8122c76e3d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87be6df27a3e6729cb514118438521d76a66b30c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423662"
---
# <a name="scontentrestriction"></a>SContentRestriction
 
**适用于**：Outlook 2013 | Outlook 2016 
  
描述内容限制，该限制用于将表视图限制为仅包含内容与搜索字符串匹配的列的行。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SContentRestriction
{
  ULONG        ulFuzzyLevel;
  ULONG        ulPropTag;
  LPSPropValue lpProp;
} SContentRestriction;

```

## <a name="members"></a>Members

**ulFuzzyLevel**
  
> 选项设置，用于定义验证匹配项时内容限制应强制实施的精度级别。
    
   **ulFuzzyLevel** 成员较低的 **16** 位适用于 PT_BINARY 和 PT_STRING8 类型的属性，并且必须设置为下列值之一： 
    
   - FL_FULLSTRING：若要匹配 **，lpProp** 搜索字符串必须包含在 **ulPropTag 标识的属性中**。
        
   - FL_PREFIX：若要匹配 **，lpProp** 搜索字符串必须出现在 **ulPropTag 标识的属性的开头**。 这两个字符串应仅与 **lpProp** 指示的搜索字符串的长度进行比较。 
        
   - FL_SUBSTRING：若要匹配 **，lpProp** 搜索字符串必须包含在 **ulPropTag** 标识的属性中的任何位置。 
        
   **ulFuzzyLevel** 成员上面的 **16** 位仅适用于 PT_STRING8 类型的属性，可以任意组合设置为以下值： 
        
   - FL_IGNORECASE：应在不考虑大小写的情况下进行比较。 
        
   - FL_IGNORENONSPACE：比较应忽略 Unicode 定义的非空格字符，如音调符号。 
        
   - FL_LOOSE：比较应尽可能为您提供匹配，忽略大小写字符和非空格字符。 
    
**ulPropTag**
  
> 属性标记，用于标识要检查搜索字符串是否出现的字符串属性。 
    
**lpProp**
  
> 指向包含要用作搜索字符串的字符串值的属性值结构的指针。
    
## <a name="remarks"></a>备注

**SContentRestriction** 结构中有两个属性标记：一个在 **ulPropTag** 成员中，另一个在 **lpProp** 指向 **的 SPropValue 结构的 ulPropTag** 成员中。  在这两个标记中，MAPI 仅需要属性类型字段并忽略属性标识符字段。 但是，这两个属性类型必须匹配，否则在调用 [IMAPITable：：Restrict](imapitable-restrict.md) 或 [IMAPITable：：FindRow](imapitable-findrow.md)时，将返回错误值 MAPI_E_TOO_COMPLEX。 
  
值FL_FULLSTRING、FL_PREFIX和FL_SUBSTRING是互斥的。 只能设置其中一个，并且必须设置其中一个。 它们的含义是固定的，提供程序必须完全按照定义实现它们。 如果提供程序无法MAPI_E_TOO_COMPLEX这些值，则提供程序应返回值。 
  
值FL_IGNORECASE、FL_IGNORENONSPACE和FL_LOOSE是独立的。 Anywhere from zero to all three them can be set. 它们的定义仅作为指南提供，并且提供程序可以自由实现每个标志自己的特定含义。 如果提供程序没有实现指定标志，则不应返回任何错误指示。 
  
当属性不存在时，未定义对属性施加的内容限制的结果。 当客户端需要针对此类限制进行明确定义的行为，并且不确定属性是否存在（例如，该属性不是表的必需列）时，它应创建 **AND** 限制以使用存在限制加入内容限制。 使用 [SExistRestriction](sexistrestriction.md) 结构定义存在限制，使用 [SAndRestriction](sandrestriction.md) 结构定义 **AND** 限制。 
  
有关 **SContentRestriction** 结构和限制的一般详细信息，请参阅关于 [限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅

- [SPropValue](spropvalue.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

