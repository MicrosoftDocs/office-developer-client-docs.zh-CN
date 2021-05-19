---
title: PidTagDeltaX 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeltaX
api_type:
- HeaderDef
ms.assetid: 9bbe996b-1cfc-46d7-bb0a-291c760500ef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efaca709b666458b0cd2f2de2124fa900d2a75b4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420519"
---
# <a name="pidtagdeltax-canonical-property"></a>PidTagDeltaX 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含以标准对话框单位表示的对话框Windows的宽度。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DELTAX  <br/> |
|标识符:  <br/> |0x3F03  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>备注

PR_XPOS  ([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md) **) 、PR_YPOS** ([PidTagYCoordinate](pidtagycoordinate-canonical-property.md) **) 、PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) 属性，此属性控制对话框控件的位置和大小。 
  
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

