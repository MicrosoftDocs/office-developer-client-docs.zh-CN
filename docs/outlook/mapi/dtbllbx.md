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
  
描述将在从显示表构建的对话框中使用的列表。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 用于从列表中消除水平或垂直滚动条的标志的位掩码。 可以设置以下标志：
    
MAPI_NO_HBAR 
  
> 列表上不应显示水平滚动条。
    
MAPI_NO_VBAR 
  
> 不应在列表中显示垂直滚动条。
    
 **ulPRSetProperty**
  
> 任何类型的属性的属性标记。 此属性是由 **ulPRTableTable** 成员标识的表中的列之一。 
    
 **ulPRTableName**
  
> 表类型属性的属性标记PT_OBJECT **OpenProperty** 调用打开的表属性。 表格应包含的列数取决于列表是单选列表还是多选列表。 如果 **ulPRSetProperty** 成员设置为PR_NULL ([PidTagNull](pidtagnull-canonical-property.md)) ，则列表允许多重选择。
    
## <a name="remarks"></a>备注

**DTBLLBX** 结构描述列表一个控件，该控件用于显示多个项目，并允许用户选择一个或多个项目。 
  
**ulPRSetProperty** 成员和 **ulPRTableName** 成员协同工作;当从表中选择一个值时，当对话框关闭时，它会写回 **ulPRSetProperty。** 
  
flags 值指示水平滚动条还是垂直滚动条应该与列表一起显示。 默认设置是显示滚动条类型（如果需要）。 服务提供商可以设置MAPI_NO_HBAR以禁止显示水平滚动条，MAPI_NO_VBAR禁止垂直滚动条。 
  
这两个属性标记成员协同工作，以显示列表中的值，并设置相应的属性（当选择列表中的项目时）。 当 MAPI 首次显示列表时，它将调用 **IMAPIProp** 实现 **OpenProperty** 方法来检索 **ulPRTableName** 成员中标识的表。 表中的列数取决于 **ulPRSetProperty** 成员的值。 如果 **ulPRSetProperty** 设置为 **PR_NULL，** 则列表是基于包含收件人的对象（如通讯簿容器、邮件的收件人表或通讯组列表内容表）的多个选择列表。 
  
多选列表的表格必须包含以下列：
  
 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
  
 **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 
  
 **PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 
  
 **PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 以及最多五个其他多值字符串属性也可以与三个必需列一起显示。 
  
如果 **ulPRSetProperty** 成员未设置为 **PR_NULL，则** 列表为单个选择列表。 **ulPRSetProperty 的初始** 值确定第一个选定的行。 当用户选择其中一行时 **，ulPRSetProperty** 成员将设置为所选值，并且此值通过调用 [IMAPIProp：：SetProps](imapiprop-setprops.md)写回属性接口实现。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

