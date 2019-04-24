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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350664"
---
# <a name="pidtagycoordinate-canonical-property"></a>PidTagYCoordinate 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对话框控件的起始位置 (左上角) 的 y 坐标 (采用标准 Windows 对话框的单位)。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_YPOS  <br/> |
|标识符:  <br/> |0x3F06  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>注解

**PR_XPOS** ([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md))、此属性、 **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)) 和**PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) 属性定位并调整控件的大小。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

