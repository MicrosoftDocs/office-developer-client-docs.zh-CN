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
ms.openlocfilehash: 34177aee48adad7eecb40836a247705fc22d2a32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778709"
---
# <a name="scontentrestriction"></a>SContentRestriction
 
**适用于**： Outlook 
  
介绍内容限制，用来限制为仅这些内容匹配搜索字符串中包含的列的行表视图。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 定义的内容的限制时用于匹配验证应同时实施的 preciseness 级别选项设置。
    
   **低 16 位**的**ulFuzzyLevel**成员 PT_BINARY 和 PT_STRING8 应用于类型的属性，并且必须设置为下列值之一： 
    
   - FL_FULLSTRING： 若要匹配， **lpProp**搜索字符串必须包含在由**ulPropTag**标识的属性。
        
   - FL_PREFIX： 若要匹配， **lpProp**搜索字符串必须显示由**ulPropTag**标识属性的开头。 应仅最由**lpProp**搜索字符串的长度比较两个字符串。 
        
   - FL_SUBSTRING： 若要匹配， **lpProp**搜索字符串必须包含无处不在由**ulPropTag**标识的属性。 
        
   **UlFuzzyLevel**成员**高 16 位**的类型 PT_STRING8 属性仅应用于，并可以设置为下列值的任意组合： 
        
   - FL_IGNORECASE： 无需考虑用例，应进行比较。 
        
   - FL_IGNORENONSPACE： 比较结果应忽略如音符 Unicode 定义不占位字符。 
        
   - FL_LOOSE： 比较结果应为您提供忽略大小写和不占位字符匹配尽可能。 
    
**ulPropTag**
  
> 标识要检查的搜索字符串匹配项的字符串属性的属性标记。 
    
**lpProp**
  
> 指针指向包含要用作搜索字符串的字符串值的属性值结构。
    
## <a name="remarks"></a>说明

**SContentRestriction**结构中有两个属性标记： **ulPropTag**成员和在**SPropValue**结构的**ulPropTag**成员另一个指向**lpProp**。 在这两个标记，MAPI 需要属性的类型字段，并忽略属性标识符字段。 但是，必须匹配的两个属性类型，否则 MAPI_E_TOO_COMPLEX 在调用[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)使用限制时则返回的错误值。 
  
值 FL_FULLSTRING、 FL_PREFIX 和 FL_SUBSTRING 相互排斥。 可以设置仅有一种，且两者之一必须设置。 及其含义固定的并提供程序必须完全按照定义方式实现它们。 如果无法支持这些值时，提供程序应返回 MAPI_E_TOO_COMPLEX。 
  
值 FL_IGNORECASE、 FL_IGNORENONSPACE 和 FL_LOOSE 无关。 任意位置从零到所有这三个它们可以设置。 作为指导仅提供及其定义和提供程序是免费实现的每个标志自己特定含义。 如果还没有指定的标志的实现，提供程序不应该返回任何错误的含义。 
  
属性不存在时未定义的属性对施加内容限制结果。 当客户端定义完善的行为的需要这样的限制而不是确保是否属性存在，例如，它不是必需的表格列它应创建加入带存在限制内容的限制**和**限制。 使用[SExistRestriction](sexistrestriction.md)结构以定义存在限制和[SAndRestriction](sandrestriction.md)结构，用于定义**和**限制。 
  
有关**SContentRestriction**结构和限制的详细信息，请参阅[有关限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅

- [SPropValue](spropvalue.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

