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
  
介绍将在从显示表生成的对话框中使用的下拉列表控件。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 保留, 必须为零。 
    
 **ulPRDisplayProperty**
  
> 类型为 PT_TSTRING 的属性的属性标记。 此属性是由**ulPRTableName**成员标识的表中的一列。 此属性的值将显示在列表中。 
    
 **ulPRSetProperty**
  
> 任何类型的属性的属性标记。 此属性是由**ulPRTableName**成员标识的表中的一列。 当列表的用户从**ulPRTableName**成员所标识的表的行中选择**ulPRDisplayProperty**成员的属性值时, 将设置相应的**ulPRSetProperty**成员。 
    
 **ulPRTableName**
  
> 可以使用**OpenProperty**调用打开的 PT_OBJECT 类型的 table 属性的属性标记。 该表应具有两列: **ulPRDisplayProperty**和**ulPRSetProperty**。 表中的行应与列表中的项相对应。
    
## <a name="remarks"></a>说明

**DTBLDDLBX**结构描述了一个下拉列表控件, 该控件显示为单个项目, 直到用户将其展开。 
  
由属性标记标识的三个属性一起使用, 以显示列表中的信息并设置一个相关的属性。 **ulPRTableName**成员是通过调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)访问的 table 对象。 表包含两列: 由**ulPRDisplayProperty**成员标识的属性的一个列, 另一个为**ulPRSetProperty**成员标识的属性的列。 
  
**ulPRDisplayProperty**属性驱动列表显示。 当用户从显示中选择一个值时, MAPI 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)以设置**ulPRSetProperty**成员标识的相应属性。 这意味着与选定的显示属性位于同一行中的属性。 **ulPRSetProperty**成员不能设置为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))。
  
如果 MAPI 已通过调用[IMAPIProp:: GetProps](imapiprop-getprops.md)检索**ulPRSetProperty**成员代表的属性, 并在表中找到包含**ulPRSetProperty**成员值的行, 则会在列表中显示一个初始值。 最初显示的值是**ulPRDisplayProperty**列中与该结构的**ulPRDisplayProperty**成员中的属性相匹配的内容。 由**ulPRDisplayProperty**成员标识的属性的**GetProps**返回的值成为首次显示列表时显示的初始值。 
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。 有关属性类型的信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)


[MAPI 结构](mapi-structures.md)
  
[显示表实现](display-table-implementation.md)
  
[显示表](display-tables.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)

