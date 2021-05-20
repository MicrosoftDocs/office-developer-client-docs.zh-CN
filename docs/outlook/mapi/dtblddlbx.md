---
title: DTBLDDLBX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLDDLBX
api_type:
- COM
ms.assetid: cf60584c-4357-44c7-9d51-f30f7e510c0c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 244aaea4902d6be8eda4cdca176436af9b002ba7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438846"
---
# <a name="dtblddlbx"></a>DTBLDDLBX

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将在从显示表构建的对话框中使用的下拉列表控件。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _DTBLDDLBX
{
  ULONG ulFlags;
  ULONG ulPRDisplayProperty;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLDDLBX, FAR *LPDTBLDDLBX;

```

## <a name="members"></a>成员

 **ulFlags**
  
> 保留，必须为零。 
    
 **ulPRDisplayProperty**
  
> 类型为 PT_TSTRING 的属性PT_TSTRING。 此属性是由 **ulPRTableName** 成员标识的表中的列之一。 此属性的值显示在列表中。 
    
 **ulPRSetProperty**
  
> 任何类型的属性的属性标记。 此属性是由 **ulPRTableName** 成员标识的表中的列之一。 当列表的用户从 **ulPRTableName** 成员标识的表中选择 **ulPRDisplayProperty** 成员属性值时，将设置相应的 **ulPRSetProperty** 成员。 
    
 **ulPRTableName**
  
> 表类型属性的属性标记PT_OBJECT **OpenProperty** 调用打开的表属性。 该表应包含两列 **：ulPRDisplayProperty 和** **ulPRSetProperty**。 表格的行应与列表中的项相对应。
    
## <a name="remarks"></a>备注

**DTBLDDLBX** 结构描述作为单个项目显示的下拉列表控件，直到用户选择展开它。 
  
属性标记标识的三个属性协同工作，以显示列表中的信息并设置相关属性。 **ulPRTableName** 成员是通过调用 [IMAPIProp：：OpenProperty 来访问的表对象](imapiprop-openproperty.md)。 该表包含两列：一列用于 **ulPRDisplayProperty** 成员标识的属性，另一列用于 **ulPRSetProperty** 成员标识的属性。 
  
**ulPRDisplayProperty** 属性驱动列表显示。 当用户从显示器中选择一个值时，MAPI 将调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 以设置 **由 ulPRSetProperty** 成员标识的相应属性。 这意味着属性与所选显示属性在同一行中。 不能 **将 ulPRSetProperty** 成员设置为PR_NULL ([PidTagNull](pidtagnull-canonical-property.md)) 。
  
如果 MAPI 已通过调用 [IMAPIProp：：GetProps](imapiprop-getprops.md)检索 **了 ulPRSetProperty** 成员所代表的属性，并且找到表中具有 **ulPRSetProperty** 成员值的行，则列表中将显示初始值。 初始显示的值是该行中 **ulPRDisplayProperty** 列的内容，该列与结构的 **ulPRDisplayProperty** 成员中的属性匹配。 **GetProps** 为 **ulPRDisplayProperty** 成员标识的属性返回的值将成为首次显示列表时显示的初始值。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。 有关属性类型的信息，请参阅 [MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)


[MAPI 结构](mapi-structures.md)
  
[显示表实现](display-table-implementation.md)
  
[显示表](display-tables.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)

