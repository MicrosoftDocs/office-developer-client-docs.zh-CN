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
ms.openlocfilehash: c6726b852176fa31bf879b5a32b63c35ce2be514
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774833"
---
# <a name="dtblcheckbox"></a>DTBLCHECKBOX

  
  
**适用于**： Outlook 
  
包含有关复选框将显示表中生成的对话框中使用的信息。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[SizedDtblCheckBox](sizeddtblcheckbox.md) <br/> |
   
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
  
> 在复选框中显示的字符字符串的内存中的位置。 
    
 **ulFlags**
  
> 用于指定的复选框标签格式的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 标签为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。
    
 **ulPRPropertyName**
  
> 属性标记类型 PT_BOOLEAN 的属性。 此属性的值会影响状态的复选框。
    
## <a name="remarks"></a>说明

**DTBLCHECKBOX**结构介绍复选框控件，反映了两种状态之一： 启用 （复选的框） 或禁用 （空框）。 
  
**UlPRPropertyName**成员描述其值操作通过更改复选框的状态的布尔属性。 当第一次显示复选框时，MAPI 调用与要检索的一组默认属性的显示表相关联的**IMAPIProp**实现的**GetProps**方法。 如果属性之一映射到**DTBLCHECKBOX**结构中的属性标记，该属性的值显示为复选框的初始值。 
  
复选框控件可以进行修改。 这允许用户更改其状态。 在其[DTCTL](dtctl.md)结构的**ulCtlFlags**成员和中其**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性，可修改复选框设置 DT_EDITABLE 标志。 当一个复选框更改其状态时，MAPI 调用[IMAPIProp::SetProps](imapiprop-setprops.md)设置为新状态的**DTBLCHECKBOX**结构属性标记成员中标识的属性。 
  
例如，通讯簿提供程序可能会在其配置对话框中，若要调整收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性的设置包括可修改复选框控件。 当用户选择复选框时，MAPI 将此属性设置为 TRUE。 时未选中该复选框，则将该属性设置为 FALSE。
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。 属性类型有关的信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[PidTagControlType 规范属性](pidtagcontroltype-canonical-property.md)


[MAPI 结构](mapi-structures.md)

