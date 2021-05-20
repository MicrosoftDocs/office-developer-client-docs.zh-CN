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
ms.openlocfilehash: 099f08876eadc83ebb66b9e4226eeeee6277bf01
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430880"
---
# <a name="pidtagcontrolflags-canonical-property"></a>PidTagControlFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于控制控件行为的标志位掩码，该控件在基于显示表构建的对话框中使用。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTROL_FLAGS  <br/> |
|标识符:  <br/> |0x3F00  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>备注

可以为此属性设置以下一个或多个标志：
  
DT_ACCEPT_DBCS 
  
> 该控件可以Double-Byte DBCS (字符) 字符集。 此标志与编辑控件一起使用。 它允许多字节字符集。
    
DT_EDITABLE 
  
> 可以编辑控件;可更改与控件关联的值。 未设置此标志时，控件为只读。 在标签、分组框、标准推送按钮、多值下拉列表框和列表框控件上忽略此值。
    
DT_MULTILINE 
  
> 编辑控件可以包含多个行。 这意味着可以在控件中输入返回字符。 此标志仅对编辑控件有效。
    
DT_PASSWORD_EDIT 
  
> 适用于编辑控件。 编辑控件被视为密码。 该值使用星号显示，而不是返回输入的实际字符。
    
DT_REQUIRED 
  
> 如果控件允许更改 (DT_EDITABLE) ，则必须在调用 [IMAPIProp：：SaveChanges 之前](imapiprop-savechanges.md) 具有值。 
    
DT_SET_IMMEDIATE 
  
> 启用值的即时设置;控件中的值更改后，MAPI 就会为与该控件关联的属性调用 **SetProps** 方法。 未设置此标志时，在对话框关闭时设置值。 
    
DT_SET_SELECTION 
  
> 在列表框中进行选择时，该列表框的索引列设置为属性。 始终与DT_SET_IMMEDIATE。
    
此属性存储在控件的 [DTCTL](dtctl.md) 结构的 ulCtlFlags 成员中。 大多数控件标志适用于允许用户输入的所有控件;一些仅适用于编辑控件。 不允许用户输入的控件（如按钮或标签）会为控件标志设置 0。 
  
许多标志值都一目了然。 例如，当DT_REQUIRED控件时，控件必须包含一个值，然后才能允许对话框关闭。 服务提供商可以通过 **IMAPIProp** 实现提供值，或者用户可以输入值。 DT_EDITABLE指示可以修改控件的值。 DT_MULTILINE允许编辑控件的值跨越多行。 
  
某些控件标志的含义并不明显。 当控件设置DT_SET_IMMEDIATE标志时，只要用户移动到新控件，其值的任何更改都会生效。 MAPI 对控件属性的属性的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法进行单个调用。 这不同于默认行为，即推迟更改控件值生效，直到用户选择"确定"按钮或关闭对话框。  DT_SET_IMMEDIATE标志通常与显示表通知结合使用。 
  
下表列出了控件的类型以及可以针对每种类型设置的所有标志值。
  
|**Control**|**此属性的有效值**|
|:-----|:-----|
|按钮  <br/> |必须为零  <br/> |
|复选框  <br/> |DT_EDITABLE、DT_SET_IMMEDIATE  <br/> |
|组合框  <br/> |DT_EDITABLE、DT_REQUIRED、DT_SET_IMMEDIATE  <br/> |
|下拉列表框  <br/> |DT_EDITABLE、DT_SET_IMMEDIATE  <br/> |
|编辑  <br/> |DT_ACCEPT_DBCS、DT_MULTILINE、DT_EDITABLE、DT_PASSWORD_EDIT、DT_REQUIRED、DT_SET_IMMEDIATE  <br/> |
|分组框  <br/> |必须为零  <br/> |
|标签  <br/> |必须为零  <br/> |
|列表框  <br/> |必须为零  <br/> |
|多值下拉列表框  <br/> |必须为零  <br/> |
|多值列表框  <br/> |必须为零  <br/> |
|选项卡式页面  <br/> |必须为零  <br/> |
|单选按钮  <br/> |必须为零  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

