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
ms.openlocfilehash: 3307bb252ca4436999a541f85657fed9878c798a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579394"
---
# <a name="dtblddlbx"></a>DTBLDDLBX

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
描述将显示表中生成的对话框中使用的下拉列表控件。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _DTBLDDLBX
{
  ULONG ulFlags;
  ULONG ulPRDisplayProperty;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLDDLBX, FAR *LPDTBLDDLBX;

```

## <a name="members"></a>Members

 **ulFlags**
  
> 保留，必须为零。 
    
 **ulPRDisplayProperty**
  
> 属性标记类型 PT_TSTRING 的属性。 此属性是一个由**ulPRTableName**成员标识表中的列。 此属性的值显示在列表中。 
    
 **ulPRSetProperty**
  
> 属性标记任何类型的属性。 此属性是一个由**ulPRTableName**成员标识表中的列。 当列表的用户从由**ulPRTableName**成员标识表的行**ulPRDisplayProperty**成员的选择的属性值时，设置相应的**ulPRSetProperty**成员。 
    
 **ulPRTableName**
  
> 调用属性表属性类型可以打开使用**OpenProperty** PT_OBJECT 的标记。 表应具有两个列： **ulPRDisplayProperty**和**ulPRSetProperty**。 Table 的行应对应于列表中的项。
    
## <a name="remarks"></a>注解

**DTBLDDLBX**结构描述用户选择将其展开之前将显示为单个项目的下拉列表控件。 
  
由属性标记标识的三个属性一起在列表中显示的信息和设置相关的属性。 **UlPRTableName**成员是 table 对象，通过调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)访问。 表中的两个列： 属性由**ulPRDisplayProperty**成员和另一个用于标识由**ulPRSetProperty**成员属性标识的一列。 
  
**UlPRDisplayProperty**属性驱动器的列表显示。 当用户从显示中选择一个值时，MAPI 调用[IMAPIProp::SetProps](imapiprop-setprops.md)由**ulPRSetProperty**成员标识设置的相应属性。 这意味着，选定的显示属性与位于同一行中的属性。 **UlPRSetProperty**成员不能设置为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))。
  
如果 MAPI 已检索**ulPRSetProperty**成员[IMAPIProp::GetProps](imapiprop-getprops.md)呼叫通过所表示的属性和值表中的行位于**ulPRSetProperty**成员的列表中显示初始值。 显示的初始值是结构的**ulPRDisplayProperty**列中**ulPRDisplayProperty**成员属性相匹配的行中的内容。 返回**GetProps**标识**ulPRDisplayProperty**成员属性的值将成为首次显示列表时显示的初始值。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。 属性类型有关的信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)


[MAPI 结构](mapi-structures.md)
  
[显示表实现](display-table-implementation.md)
  
[显示表](display-tables.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)

