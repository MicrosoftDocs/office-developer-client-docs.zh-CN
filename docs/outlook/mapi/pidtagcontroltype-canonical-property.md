---
title: PidTagControlType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagControlType
api_type:
- HeaderDef
ms.assetid: 7728fa2f-4a59-4e86-90f1-4384824598aa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fba82fef7c5330f538521d8d5fbdbcecc061ee27
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777509"
---
# <a name="pidtagcontroltype-canonical-property"></a>PidTagControlType 规范属性

  
  
**适用于**： Outlook 
  
包含一个值，该值在对话框中使用的控件的控件类型。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTROL_TYPE  <br/> |
|标识符：  <br/> |0x3F02  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>说明

此属性可以具有完全下列值之一：
  
DTCT_BUTTON 
  
> 对话框按钮控件。
    
DTCT_CHECKBOX 
  
> 对话框复选框。
    
DTCT_COMBOBOX 
  
> 对话框组合框。
    
DTCT_DDLBX 
  
> 对话框下拉列表。
    
DTCT_EDIT 
  
> 编辑文本对话框。
    
DTCT_GROUPBOX 
  
> 对话框组。
    
DTCT_LABEL 
  
> 对话框标签。
    
DTCT_LBX 
  
> 对话框列表。
    
DTCT_LISTBOX 
  
> 对话框列表。
    
DTCT_MVDDLBX 
  
> 多值的列表框填充的多值字符串类型的属性。
    
DTCT_PAGE 
  
> 对话框选项卡式的页面。
    
DTCT_RADIOBUTTON 
  
> 对话框单选按钮。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

