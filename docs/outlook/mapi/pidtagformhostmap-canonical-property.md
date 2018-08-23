---
title: PidTagFormHostMap 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormHostMap
api_type:
- HeaderDef
ms.assetid: 92742747-cce0-4c54-9ece-1fcf652ac498
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8c024f71279fac5dbb3d771442d9fbfb8a50e0f5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578869"
---
# <a name="pidtagformhostmap-canonical-property"></a>PidTagFormHostMap 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含主机地图的可用窗体。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FORM_HOST_MAP  <br/> |
|标识符：  <br/> |0x3306  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |常见的 MAPI  <br/> |
   
## <a name="remarks"></a>注解

更改**IMAPIFormProp**接口的基础结构时，客户端应用程序应更新以及**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性，此属性。 
  
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

