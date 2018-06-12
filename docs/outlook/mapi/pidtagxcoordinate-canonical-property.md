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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 3b5a4a337d8f92a3142aeb43eec9f2e9f0578a8a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778568"
---
# <a name="pidtagxcoordinate-canonical-property"></a>PidTagXCoordinate 规范属性

  
  
**适用于**： Outlook 
  
包含的起始位置 （左上角） 对话框控件，以标准 Windows 对话框单位表示的 x 坐标。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_XPOS  <br/> |
|标识符:  <br/> |0x3F05  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>备注

此属性、 **PR_YPOS** ([PidTagYCoordinate](pidtagycoordinate-canonical-property.md))、 **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)) 和**PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) 属性定位并调整大小对话框控件。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

