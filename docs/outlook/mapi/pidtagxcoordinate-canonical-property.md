---
title: PidTagXCoordinate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagXCoordinate
api_type:
- COM
ms.assetid: 030d5c21-ab02-4047-bf2d-9a402a1e9102
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87df676dccdb067302d62da2bd1fda6b634ed4f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350657"
---
# <a name="pidtagxcoordinate-canonical-property"></a>PidTagXCoordinate 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对话框控件的起始位置 (左上角) 的 x 坐标 (以标准 Windows 对话框的单位表示)。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_XPOS  <br/> |
|标识符:  <br/> |0x3F05  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>注解

此属性、 **PR_YPOS** ([PidTagYCoordinate](pidtagycoordinate-canonical-property.md))、 **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)) 和**PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) 属性定位并调整对话框控件的大小。
  
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

