---
title: PidTagExpiryUnits 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExpiryUnits
api_type:
- HeaderDef
ms.assetid: f6a1ca22-cf4c-4e59-8846-6bd937fa8f6e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8e8deb67990ce25b10a3b0fc1d373f635f958013
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316406"
---
# <a name="pidtagexpiryunits-canonical-property"></a>PidTagExpiryUnits 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述[PidTagExpiryNumber](pidtagexpirynumber-canonical-property.md) PR_EXPIRY_NUMBER (属性) 的时间单位。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EXPIRY_UNITS  <br/> |
|标识符:  <br/> |0x3FEE  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>备注

此属性（如果设置）必须是下列值之一：
  
|||
|:-----|:-----|
|PidTagExpiryUnits  <br/> |Description (TimeOf)   <br/> |
|0x00000000  <br/> |分钟，例如 60 秒  <br/> |
|0x00000001  <br/> |小时，例如 60x60 秒  <br/> |
|0x00000002  <br/> |天，例如 24x60x60 秒  <br/> |
|0x00000003  <br/> |周，例如 7x24x60x60 秒  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
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

