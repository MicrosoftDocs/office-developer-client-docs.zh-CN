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
  
描述用于将常量与属性值相匹配的属性限制。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 将在搜索中使用的关系运算符。 可能的值如下所示：
    
  - RELOP_GE：比较基于大于或等于第一个值。
        
  - RELOP_GT：比较基于较大的第一个值。
        
  - RELOP_LE：比较基于小于或等于第一个值。
        
  - RELOP_LT：比较基于第一个值较小。
        
  - RELOP_NE：基于数值进行比较。
        
  - RELOP_RE：比较基于 LIKE (正则表达式) 值。
        
  - RELOP_EQ：基于相等的值进行比较。
    
**ulPropTag**
  
> 标识要比较的属性的属性标记。 
    
**lpProp**
  
> 指向包含将在比较中使用的常量值的 [SPropValue](spropvalue.md) 结构的指针。 
    
## <a name="remarks"></a>备注

**SPropertyRestriction 结构中有两个属性** 标记。 一个位于 **ulPropTag** 成员中，另一个位于 **lpProp** 指向的 **SPropValue** 结构的 **ulPropTag** 成员中。 MAPI 需要属性标识符字段和属性类型字段。 **SPropertyRestriction** 中的 **ulPropTag** 是要匹配的属性 **，SPropertyRestriction** 到 **ulPropTag** 的 **SPropValue** 类型的 **lpProp** 指针指示如何解释 **lpProp** 联合的成员值。 这两个属性类型必须匹配，否则在调用 [IMAPITable：：Restrict](imapitable-restrict.md) 或 [IMAPITable：：FindRow](imapitable-findrow.md)MAPI_E_TOO_COMPLEX将返回错误值 。 
  
比较顺序是 (_运算符)  (运算符)  (常量) 。_
  
当属性限制传递到 **IMAPITable：：Restrict** 或 **IMAPITable：：FindRow** 并且目标属性不存在时，限制的结果将不确定。 通过创建 **将属性** 限制与 **EXIST** 限制联接在一起的 AND 限制，可以保证调用方得到准确的结果。 使用 [SExistRestriction](sexistrestriction.md) 结构定义 **EXIST** 限制，使用 [SAndRestriction](sandrestriction.md) 结构定义 **AND** 限制。 
  
如果实现表的服务提供商支持多值属性标记，可以在属性限制中使用它们。 如果支持，可在可以使用单值属性标记的任何位置使用多值属性标记。 
  
多值属性标记可用于以下方法：
  
- [IMAPIProp::SetProps](imapiprop-setprops.md)
    
- [IMAPIProp::GetProps](imapiprop-getprops.md)
    
- [IMAPITable::SetColumns](imapitable-setcolumns.md)
    
- [IMAPITable::SortTable](imapitable-sorttable.md)
    
- [IMAPITable::Restrict](imapitable-restrict.md)
    
> [!IMPORTANT]
> 两个属性标记不匹配的一个值得注意的情况是限制多值属性。 在这种情况下，必须为 true。 > 如果 **SPropertyRestriction** 的 **ulPropTag** 的属性类型包含多值属性类型位标志 MV_FLAG (0x1000) ，**则 SPropValue** 的 **ulPropTag** 的属性类型应匹配前者减去 MV_FLAG 位标志，即其反函数。 >例如，若要限制使用多值自定义字符串属性，例如属性 0x8012101f（即 PROP_TAG (MV_FLAG|PT_UNICODE、0x8012) ) ）具有属性标记的类别，对应的 **SPropertyRestriction** 将显示如下。 >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";`>请注意，如果 **SPropValue** **的 ulPropTag** 的属性类型包含 MV_FLAG 位标志，则可能会返回 MAPI_E_TOO_COMPLEX。 
  
有关 **SPropertyRestriction** 结构详细信息，请参阅关于 [限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅

- [SExistRestriction](sexistrestriction.md)
- [SAndRestriction](sandrestriction.md)
- [SPropValue](spropvalue.md)
- [SRestriction](srestriction.md)
- [IMAPITable::FindRow](imapitable-findrow.md)
- [IMAPITable::Restrict](imapitable-restrict.md)
- [MAPI 结构](mapi-structures.md)

