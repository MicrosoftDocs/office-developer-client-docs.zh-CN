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
ms.openlocfilehash: 29d392eba530126e06a672c10044c5b4df0618c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406085"
---
# <a name="spropertyrestriction"></a>SPropertyRestriction

**适用于**：Outlook 2013 | Outlook 2016 
  
介绍用于将常量与属性值相匹配的属性限制。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 将在搜索中使用的关系运算符。 可能的值如下所示:
    
  - RELOP_GE: 根据一个大于或等于的第一个值进行比较。
        
  - RELOP_GT: 根据更大的第一个值进行比较。
        
  - RELOP_LE: 基于一个小于或等于的第一个值进行比较。
        
  - RELOP_LT: 基于较小的第一个值进行比较。
        
  - RELOP_NE: 根据不相等的值进行比较。
        
  - RELOP_RE: 根据 LIKE (正则表达式) 值进行比较。
        
  - RELOP_EQ: 根据相等的值进行比较。
    
**ulPropTag**
  
> 标识要比较的属性的属性标记。 
    
**lpProp**
  
> 指向包含将在比较中使用的常量值的[SPropValue](spropvalue.md)结构的指针。 
    
## <a name="remarks"></a>说明

**SPropertyRestriction**结构中有两个属性标记。 一个位于**ulPropTag**成员中, 另一个位于**lpProp**指向的**SPropValue**结构的**ulPropTag**成员中。 MAPI 同时需要 "属性标识符" 字段和 "属性类型" 字段。 **SPropertyRestriction**中的**ulPropTag**是要匹配的属性, 而**SPropertyRestriction**的**lpProp**指针指示 ulPropTag 的 SPropValue 类型**** 的**** 的成员值解释**lpProp**联合。 这两个属性类型必须匹配, 否则在对[IMAPITable:: Restrict](imapitable-restrict.md)或[IMAPITable:: FindRow](imapitable-findrow.md)的调用中使用限制时, 将返回错误值 MAPI_E_TOO_COMPLEX。 
  
比较顺序为 _(属性值) (关系运算符) (常量值_)。
  
如果将属性限制传递给**IMAPITable:: Restrict**或**IMAPITable:: FindRow** , 且目标属性不存在, 则限制的结果将是不确定的。 通过创建**和**限制将属性限制与**存在**的限制联接在一起, 可以保证正确结果的调用者。 使用[SExistRestriction](sexistrestriction.md)结构定义**存在**限制和[SAndRestriction](sandrestriction.md)结构以定义**和**限制。 
  
如果实现表的服务提供程序支持, 多值属性标记可在属性限制中使用。 如果支持, 多值属性标记可用于任何可使用单值属性标记的地方。 
  
可以在以下方法中使用多值属性标记:
  
- [IMAPIProp::SetProps](imapiprop-setprops.md)
    
- [IMAPIProp::GetProps](imapiprop-getprops.md)
    
- [IMAPITable::SetColumns](imapitable-setcolumns.md)
    
- [IMAPITable::SortTable](imapitable-sorttable.md)
    
- [IMAPITable::Restrict](imapitable-restrict.md)
    
> [!IMPORTANT]
> 这两个属性标记不匹配的一个显著情况是, 如果对多值属性进行限制。 在这种情况下, 以下情况必须为 true。 > 如果**SPropertyRestriction**的**ulPropTag**的属性类型包含多值属性类型位标志 MV_FLAG (0x1000), 则**ulPropTag**的**SPropValue**的属性类型应与前减去 MV_ 的属性类型相匹配。标志位标志, 即它的反函数。 > 例如, 若要限制使用多值自定义字符串属性 (如具有属性标记的属性0x8012101f 的类别) (即 PROP_TAG (MV_FLAG | PT_UNICODE、0x8012)), 相应的**SPropertyRestriction**将显示为沿用. >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";`> 请注意, 如果**SPropValue**的**ulPropTag**的属性类型包含 MV_FLAG 位标志, 则可能返回的是 MAPI_E_TOO_COMPLEX。 
  
有关**SPropertyRestriction**结构的详细信息, 请参阅[关于限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅

- [SExistRestriction](sexistrestriction.md)
- [SAndRestriction](sandrestriction.md)
- [SPropValue](spropvalue.md)
- [SRestriction](srestriction.md)
- [IMAPITable::FindRow](imapitable-findrow.md)
- [IMAPITable::Restrict](imapitable-restrict.md)
- [MAPI 结构](mapi-structures.md)

