---
title: PidTagYCoordinate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagYCoordinate
api_type:
- COM
ms.assetid: f176308d-efb9-460c-8379-8a12d4f8e017
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ab90b05f8bd92f4cfd90f84078691a293ae159b7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436851"
---
# <a name="pidtagycoordinate-canonical-property"></a>PidTagYCoordinate 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对话框控件左上角 (的 y 坐标) ，以标准对话框Windows表示。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_YPOS  <br/> |
|标识符:  <br/> |0x3F06  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>备注

The **PR_XPOS** ([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md)) ， this property， **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)) ， and **PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) properties position and size the control.
  
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

