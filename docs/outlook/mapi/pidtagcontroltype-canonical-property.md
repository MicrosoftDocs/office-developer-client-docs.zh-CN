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
ms.openlocfilehash: 7bdb02f72ba14a36c8a4c218cd5f0631e7145e6a
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734201"
---
# <a name="pidtagcontroltype-canonical-property"></a>PidTagControlType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个值，该值指示对话框中使用的控件的控件类型。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTROL_TYPE  <br/> |
|标识符:  <br/> |0x3F02  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>说明

此属性可以正好具有以下值之一：
    
DTCT_LABEL (0x0000000000) 
  
> 对话框标签。
   
DTCT_EDIT (0x000000001) 
  
> 对话框编辑文本框。

DTCT_LBX (0x000000002) 
  
> 对话框列表框。
    
DTCT_COMBOBOX (0x000000003) 
  
> 对话框组合框。

DTCT_DDLBX (0x000000004) 
  
> 对话框下拉列表框。

DTCT_CHECKBOX (0x00000005) 
  
> 对话框复选框。

DTCT_GROUPBOX (0x000000006) 
  
> 对话框组框。
  
DTCT_BUTTON (0x000000007) 
  
> 对话框按钮控件。
    
DTCT_PAGE (0x00000008) 
  
> 对话框选项卡式页面。
    
DTCT_RADIOBUTTON (0x00000009) 
  
> 对话框单选按钮。
    
DTCT_MVLISTBOX (0x00000000B) 
  
> 由字符串类型的多值属性填充的多值列表框。
    
DTCT_MVDDLBX (0x0000000C) 
  
> 由字符串类型的多值属性填充的多值下拉列表框。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

