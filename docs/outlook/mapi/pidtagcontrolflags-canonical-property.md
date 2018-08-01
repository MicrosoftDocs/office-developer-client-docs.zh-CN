---
title: PidTagControlFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagControlFlags
api_type:
- HeaderDef
ms.assetid: b97a9e72-fbb7-49ab-a19d-5e9bd1b8a80d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f6947efe1aa6866efb7a5a3d96262d021c68013f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777507"
---
# <a name="pidtagcontrolflags-canonical-property"></a>PidTagControlFlags 规范属性

  
  
**适用于**： Outlook 
  
包含调控显示表中生成的对话框中使用控件的行为的标志位的掩码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTROL_FLAGS  <br/> |
|标识符：  <br/> |0x3F00  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>说明

此属性，可以设置一个或多个以下标志：
  
DT_ACCEPT_DBCS 
  
> 该控件可在其中包含双字节字符集 (DBCS) 字符。 此标志用于编辑控件。 允许多个字节字符集。
    
DT_EDITABLE 
  
> 可以编辑控件;可以更改与控件关联的值。 当未设置此标志时，控件是只读的。 此值，则忽略上标签、 组框、 标准下压按钮、 多值的下拉列表框和列表框控件。
    
DT_MULTILINE 
  
> 编辑控件可以包含多个行。 这意味着回车符可以输入的控件内。 此标志是有效的编辑控件仅。
    
DT_PASSWORD_EDIT 
  
> 适用于编辑控件。 编辑控件被视为一个密码。 而不回声输入的实际字符使用星号来显示值。
    
DT_REQUIRED 
  
> 如果该控件允许更改 (DT_EDITABLE)，它必须具有一个值，调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)之前。 
    
DT_SET_IMMEDIATE 
  
> 启用即时设置的值;只要在控件中的值更改，MAPI 调用与该控件关联的属性的**SetProps**方法。 当未设置此标志时，当消除对话框中设置的值。 
    
DT_SET_SELECTION 
  
> 当列表框中进行选择时，该列表框的索引列被设置为属性。 始终与 DT_SET_IMMEDIATE 一起使用。
    
此属性存储在控件的[DTCTL](dtctl.md)结构的 ulCtlFlags 成员。 大部分控制标志适用于所有控件，允许用户输入;一些仅适用于编辑控件。 不允许用户输入按钮或标签，如的控制设置其控制标志为 0。 
  
许多标志值是显而易见的。 例如，当 DT_REQUIRED 设置控件时，它必须包含一个值，对话框允许解除之前。 服务提供商可以提供通过**IMAPIProp**实现其值，或者用户可以输入一个。 DT_EDITABLE 指示可以修改该控件的值。 DT_MULTILINE 允许编辑控件以跨多个行的值。 
  
一些控制标志不那么明显中及其含义。 当控件集 DT_SET_IMMEDIATE 标志时、 其值要采取的任何更改将影响只要用户移动到一个新的控件。 MAPI 单个调用属性接口的[IMAPIProp::SetProps](imapiprop-setprops.md)方法，用于控件的属性。 这一点不同于默认行为，即延迟具有对控件值的更改在用户选择**确定**按钮或消除对话框后会生效。 DT_SET_IMMEDIATE 标志常用与显示表通知结合使用。 
  
下表列出的控件的类型和所有可以为每种类型的标志值。
  
|**控件**|**此属性的有效值**|
|:-----|:-----|
|按钮  <br/> |必须为零  <br/> |
|复选框  <br/> |DT_EDITABLE DT_SET_IMMEDIATE  <br/> |
|组合框  <br/> |DT_EDITABLE，DT_REQUIRED，DT_SET_IMMEDIATE  <br/> |
|下拉列表框  <br/> |DT_EDITABLE DT_SET_IMMEDIATE  <br/> |
|编辑  <br/> |DT_ACCEPT_DBCS、 DT_MULTILINE、 DT_EDITABLE、 DT_PASSWORD_EDIT、 DT_REQUIRED、 DT_SET_IMMEDIATE  <br/> |
|分组框  <br/> |必须为零  <br/> |
|标签  <br/> |必须为零  <br/> |
|列表框  <br/> |必须为零  <br/> |
|多值下拉列表框  <br/> |必须为零  <br/> |
|多值列表框  <br/> |必须为零  <br/> |
|选项卡式的页面  <br/> |必须为零  <br/> |
|单选按钮  <br/> |必须为零  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

