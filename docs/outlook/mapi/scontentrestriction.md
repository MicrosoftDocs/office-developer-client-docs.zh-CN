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
  
介绍内容限制, 用于将表视图限制为仅包含内容与搜索字符串匹配的列的那些行。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 定义在验证匹配项时内容限制应强制实施的 preciseness 级别的选项设置。
    
   **ulFuzzyLevel**成员的**低16位**应用于 PT_BINARY 和 PT_STRING8 类型的属性, 并且必须设置为以下值之一: 
    
   - FL_FULLSTRING: 若要匹配, **lpProp**搜索字符串必须包含在由**ulPropTag**标识的属性中。
        
   - FL_PREFIX: 若要匹配, **lpProp**搜索字符串必须出现在由**ulPropTag**标识的属性的开头。 这两个字符串只应与**lpProp**所指示的搜索字符串的长度进行比较。 
        
   - FL_SUBSTRING: 若要匹配, **lpProp**搜索字符串必须包含在**ulPropTag**标识的属性中的任何位置。 
        
   **ulFuzzyLevel**成员的**高16位**仅适用于 PT_STRING8 类型的属性, 并且可以通过任意组合设置为以下值: 
        
   - FL_IGNORECASE: 应进行比较, 而不考虑大小写。 
        
   - FL_IGNORENONSPACE: 比较操作应忽略 Unicode 定义的非空格字符, 如变音标记。 
        
   - FL_LOOSE: 比较时应尽可能为您提供匹配项, 忽略大小写和非空格字符。 
    
**ulPropTag**
  
> 用于标识要检查搜索字符串的匹配项的字符串属性的属性标记。 
    
**lpProp**
  
> 指向属性值结构的指针, 该结构包含要用作搜索字符串的字符串值。
    
## <a name="remarks"></a>说明

**SContentRestriction**结构中有两个属性标记: 一个在**ulPropTag**成员中, 另一个位于**lpProp**指向的**SPropValue**结构的**ulPropTag**成员中。 在这两个标记中, MAPI 仅需要属性类型字段, 并且忽略属性标识符字段。 但是, 这两个属性类型必须匹配, 否则在对[IMAPITable:: Restrict](imapitable-restrict.md)或[imapitable:: FindRow](imapitable-findrow.md)的调用中使用限制时, 将返回错误值 MAPI_E_TOO_COMPLEX。 
  
值 FL_FULLSTRING、FL_PREFIX 和 FL_SUBSTRING 是相互排斥的。 只能设置其中一个, 并且必须设置其中一个。 它们的含义是固定的, 并且提供程序必须完全按照定义实现。 如果提供程序无法支持这些值, 则该提供程序应返回 MAPI_E_TOO_COMPLEX。 
  
值 FL_IGNORECASE、FL_IGNORENONSPACE 和 FL_LOOSE 是独立的。 可以设置从零到所有三项之间的任意位置。 它们的定义仅作为指导提供, 提供程序可自由实现每个标志的特定含义。 如果提供程序不能实现指定的标志, 则该提供程序不应返回任何错误指示。 
  
如果属性不存在, 则针对属性施加的内容限制的结果将未定义。 如果客户端需要此类限制的明确定义行为, 并且不确定该属性是否存在, 则它不是表的必需列。它应创建**并**限制, 以使用存在的限制加入内容限制。 使用[SExistRestriction](sexistrestriction.md)结构定义存在限制和[SAndRestriction](sandrestriction.md)结构以定义**和**限制。 
  
有关**SContentRestriction**结构和限制的详细信息, 请参阅[关于限制](about-restrictions.md)。
  
## <a name="see-also"></a>另请参阅

- [SPropValue](spropvalue.md)
- [SRestriction](srestriction.md)
- [MAPI 结构](mapi-structures.md)

