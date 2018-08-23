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
ms.openlocfilehash: 35e19a4281c46ae7c2b5cbd76c1ecea35bf87665
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569762"
---
# <a name="dtbllbx"></a>DTBLLBX

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
描述将显示表中生成的对话框中使用的列表。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _DTBLLBX
{
  ULONG ulFlags;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLLBX, FAR *LPDTBLLBX

```

## <a name="members"></a>Members

 **ulFlags**
  
> 用于消除从列表中的水平或垂直滚动条的标志位掩码。 可以设置以下标志：
    
MAPI_NO_HBAR 
  
> 不水平滚动条应与列表所示。
    
MAPI_NO_VBAR 
  
> 不垂直滚动条应与列表所示。
    
 **ulPRSetProperty**
  
> 属性标记任何类型的属性。 此属性是一个由**ulPRTableTable**成员标识表中的列。 
    
 **ulPRTableName**
  
> 调用属性表属性类型可以打开使用**OpenProperty** PT_OBJECT 的标记。 该表应具有的列数取决于列表是否是单个或多个所选内容列表。 如果**ulPRSetProperty**成员设置为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))，允许多重选择列表。
    
## <a name="remarks"></a>注解

**DTBLLBX**结构介绍用于显示多个项目，并使用户可以选择一个或多个项目的控件的列表。 
  
**UlPRSetProperty**成员和**ulPRTableName**成员协同; 工作当从表中选择一个值时，它是写回**ulPRSetProperty**时消除对话框。 
  
Flags 值指示是否应与列表中显示水平或垂直滚动条。 默认值是不显示的滚动条如果需要的类型。 服务提供商可以设置 MAPI_NO_HBAR 禁止在水平滚动条和 MAPI_NO_VBAR 禁止在垂直滚动条。 
  
两个属性标记成员协同工作来在列表中显示值和选择列表中的项目时设置相应的属性。 当 MAPI 首次显示列表时，它会调用**IMAPIProp**实现**OpenProperty**方法来检索标识**ulPRTableName**成员中的表。 表中的列数取决于**ulPRSetProperty**成员的值。 如果**ulPRSetProperty**设置为**PR_NULL**，列表是一个包含收件人，如通讯簿容器、 邮件收件人表或通讯组列表内容表对象所基于的多个所选内容列表。 
  
多选列表表必须包括以下各列：
  
 **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
  
 **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
  
 **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))
  
 **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 和最多五个其他多值的字符串属性也可以显示与所需的三个列。 
  
如果未设置为**PR_NULL** **ulPRSetProperty**成员，列表是单项选择列表。 **UlPRSetProperty**的初始值确定所选的第一行。 当用户选择行之一时， **ulPRSetProperty**成员设置为所选的值，该值写回[IMAPIProp::SetProps](imapiprop-setprops.md)调用与该属性接口实现。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

