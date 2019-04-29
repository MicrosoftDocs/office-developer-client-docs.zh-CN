---
title: DTBLCHECKBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLCHECKBOX
api_type:
- COM
ms.assetid: 0dd12990-5431-4768-9d64-27d4ef6b7b20
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ed0bbe986f374648e2ee85f3a0d2dfe7bc392e0f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436830"
---
# <a name="dtblcheckbox"></a>DTBLCHECKBOX

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关将在从显示表生成的对话框中使用的复选框的信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[SizedDtblCheckBox](sizeddtblcheckbox.md) <br/> |
   
```cpp
typedef struct _DTBLCHECKBOX
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulPRPropertyName;
} DTBLCHECKBOX, FAR *LPDTBLCHECKBOX;

```

## <a name="members"></a>Members

 **ulbLpszLabel**
  
> 使用复选框显示的字符字符串在内存中的位置。 
    
 **ulFlags**
  
> 用于指定复选框标签格式的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。
    
 **ulPRPropertyName**
  
> 类型为 PT_BOOLEAN 的属性的属性标记。 此属性的值受复选框状态的影响。
    
## <a name="remarks"></a>说明

**DTBLCHECKBOX**结构描述了一个复选框, 该控件反映两个状态之一: 已启用 (复选框) 或已禁用 (空框)。 
  
**ulPRPropertyName**成员描述了一个布尔属性, 该属性的值通过更改复选框的状态进行操作。 当该复选框第一次显示时, MAPI 将调用与显示表相关联的**IMAPIProp**实现的**GetProps**方法, 以检索一组默认属性。 如果其中一个属性映射到**DTBLCHECKBOX**结构中的属性标记, 则该属性的值将显示为复选框的初始值。 
  
可以修改复选框控件。 这样一来, 用户可以更改其状态。 可修改的复选框在其[DTCTL](dtctl.md)结构的**ulCtlFlags**成员及其**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性中设置 DT_EDITABLE 标志。 复选框更改其状态时, MAPI 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)将在**DTBLCHECKBOX**结构的 property 标记成员中标识的属性设置为新状态。 
  
例如, 通讯簿提供程序可能在其配置对话框中包含一个可修改的复选框控件, 以调整收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性的设置。 当用户选中此复选框时, MAPI 会将此属性设置为 TRUE。 如果未选中此复选框, 则会将该属性设置为 FALSE。
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。 有关属性类型的信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[PidTagControlType 规范属性](pidtagcontroltype-canonical-property.md)


[MAPI 结构](mapi-structures.md)

