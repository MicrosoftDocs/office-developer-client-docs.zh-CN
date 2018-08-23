---
title: SPropertyRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropertyRestriction
api_type:
- COM
ms.assetid: 2bbf13e9-05b3-4498-8e08-d9e07505190d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d588380ccc84f51fe58bb0f092d5287b12b4270
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586534"
---
# <a name="spropertyrestriction"></a>SPropertyRestriction

**适用于**： Outlook 2013 |Outlook 2016 
  
介绍用于匹配属性的值的常量属性限制。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SPropertyRestriction
{
  ULONG relop;
  ULONG ulPropTag;
  LPSPropValue lpProp;
} SPropertyRestriction;

```

## <a name="members"></a>Members

**relop**
  
> 将在搜索中使用的关系运算符。 可能值如下所示：
    
  - RELOP_GE： 比较结果是根据大于或等于的第一个值。
        
  - RELOP_GT： 比较结果是根据更高版本的第一个值。
        
  - RELOP_LE： 进行比较基于上第一个值小于或等于。
        
  - RELOP_LT： 比较结果是根据为较小的第一个值。
        
  - RELOP_NE： 进行比较基于上不相等的值。
        
  - RELOP_RE： 进行比较基于类似 （正则表达式） 值。
        
  - RELOP_EQ： 比较结果是根据相等的值。
    
**ulPropTag**
  
> 属性标记标识要进行比较的属性。 
    
**lpProp**
  
> 指向[SPropValue](spropvalue.md)结构，其中包含将在比较中使用的常量值的指针。 
    
## <a name="remarks"></a>注解

**SPropertyRestriction**结构中有两个属性标记。 一个在**ulPropTag**成员中声明，另一个是在所指的**lpProp** **SPropValue**结构的**ulPropTag**成员。 MAPI 要求属性标识符字段和属性类型字段。 在**SPropertyRestriction** **ulPropTag**是要匹配的属性和**SPropertyRestriction**到**ulPropTag**的类型的**SPropValue** **lpProp**指针指示如何的成员值解释**lpProp**联合。 必须匹配的两个属性类型，否则 MAPI_E_TOO_COMPLEX 在调用[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)使用限制时则返回的错误值。 
  
比较顺序是 _（属性值） （关系运算符） （常量值）_。
  
属性限制传递给**IMAPITable::Restrict**或**IMAPITable::FindRow**和目标属性不存在，当该限制的结果是未定义。 通过创建加入带**存在**限制在属性限制**和**限制，呼叫者可以保证准确的结果。 使用[SExistRestriction](sexistrestriction.md)结构以定义**存在**限制和[SAndRestriction](sandrestriction.md)结构，用于定义**和**限制。 
  
可以在属性限制中使用多值的属性标记，如果服务提供商实现表支持。 如果受支持，多值的属性标记可无处不在可以使用单值属性标记。 
  
多值的属性标记可以采用以下方法：
  
- [IMAPIProp::SetProps](imapiprop-setprops.md)
    
- [IMAPIProp::GetProps](imapiprop-getprops.md)
    
- [IMAPITable::SetColumns](imapitable-setcolumns.md)
    
- [IMAPITable::SortTable](imapitable-sorttable.md)
    
- [IMAPITable::Restrict](imapitable-restrict.md)
    
> [!IMPORTANT]
> 对多值属性限制时值得注意的情况时两个属性标记不匹配。 在此情况下必须满足以下条件。 > 如果**SPropertyRestriction** **ulPropTag**的属性类型包含多值属性类型的位标志 MV_FLAG (0x1000)， **SPropValue** **ulPropTag**的属性类型应匹配减去 MV_ 前者标志位标志，即，其反函数。 > 例如，若要限制使用属性标记属性 0x8012101f，即 PROP_TAG 一个多值自定义字符串属性，如类别 (MV_FLAG | PT_UNICODE，0x8012))，相应**SPropertyRestriction**将显示为如下所示。 >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";`> 请注意，如果**SPropValue** **ulPropTag**的属性类型包含 MV_FLAG 位标志，可能返回 MAPI_E_TOO_COMPLEX。 
  
有关**SPropertyRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅

- [SExistRestriction](sexistrestriction.md)
- [SAndRestriction](sandrestriction.md)
- [SPropValue](spropvalue.md)
- [SRestriction](srestriction.md)
- [IMAPITable::FindRow](imapitable-findrow.md)
- [IMAPITable::Restrict](imapitable-restrict.md)
- [MAPI 结构](mapi-structures.md)

