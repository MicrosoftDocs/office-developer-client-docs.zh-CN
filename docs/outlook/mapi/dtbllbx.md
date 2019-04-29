---
title: DTBLLBX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLLBX
api_type:
- COM
ms.assetid: 971b4837-6823-4f28-9803-3c22b2ec091f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2bff20af2b3e9ea4e203e38ae38a8bc19074a727
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438566"
---
# <a name="dtbllbx"></a>DTBLLBX

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍将在从显示表生成的对话框中使用的列表。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _DTBLLBX
{
  ULONG ulFlags;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLLBX, FAR *LPDTBLLBX

```

## <a name="members"></a>成员

 **ulFlags**
  
> 用于从列表中消除水平或垂直滚动条的标志位掩码。 可以设置以下标志:
    
MAPI_NO_HBAR 
  
> 不应在列表中显示任何水平滚动条。
    
MAPI_NO_VBAR 
  
> 不应在列表中显示垂直滚动条。
    
 **ulPRSetProperty**
  
> 任何类型的属性的属性标记。 此属性是由**ulPRTableTable**成员标识的表中的一列。 
    
 **ulPRTableName**
  
> 可以使用**OpenProperty**调用打开的 PT_OBJECT 类型的 table 属性的属性标记。 表应包含的列数取决于列表是单个还是多个选择列表。 如果将**ulPRSetProperty**成员设置为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)), 则此列表允许多项选择。
    
## <a name="remarks"></a>说明

**DTBLLBX**结构描述用于显示多个项目的控件的列表, 并允许用户选择一个或多个项目。 
  
**ulPRSetProperty**成员和**ulPRTableName**成员一起工作;当从表中选择一个值时, 它会在对话框关闭时写回到**ulPRSetProperty** 。 
  
flags 值指示是否在列表中显示水平和垂直滚动条。 默认值为如果需要, 则显示滚动条的类型。 服务提供程序可以将 MAPI_NO_HBAR 设置为禁止水平滚动条和 MAPI_NO_VBAR, 以禁止显示垂直滚动条。 
  
当选择列表中的项目时, 这两个属性标记成员将一起显示列表中的值并设置相应的属性。 当 MAPI 第一次显示列表时, 它会调用**IMAPIProp**实现的**OpenProperty**方法, 以检索**ulPRTableName**成员中标识的表。 表中的列数取决于**ulPRSetProperty**成员的值。 如果将**ulPRSetProperty**设置为**PR_NULL**, 则列表是基于包含收件人的对象的多选列表, 如通讯簿容器、邮件的收件人表或通讯组列表内容表。 
  
多选列表的表格必须包含以下列:
  
 **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
  
 **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
  
 **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))
  
 **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)), 并且最多有五个其他多值字符串属性也可以显示三个必需的列。 
  
如果**ulPRSetProperty**成员未设置为**PR_NULL**, 则该列表为单个选择列表。 **ulPRSetProperty**的初始值决定了第一个选定的行。 当用户选择其中一个行时, **ulPRSetProperty**成员将设置为选定值, 并将此值写回到属性接口实现中, 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)。 
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

