---
title: PidTagFormDesignerGuid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormDesignerGuid
api_type:
- HeaderDef
ms.assetid: 8d7f5789-610c-47f6-a109-5513d677ef60
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b0e0847a3a9e21f080a852738ec8afbc98a2263f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412238"
---
# <a name="pidtagformdesignerguid-canonical-property"></a>PidTagFormDesignerGuid 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于设计窗体的对象的唯一标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FORM_DESIGNER_GUID  <br/> |
|标识符:  <br/> |0x3309  <br/> |
|数据类型：  <br/> |PT_GUID  <br/> |
|区域：  <br/> |MAPI common  <br/> |
   
## <a name="remarks"></a>备注

此属性通常包含用于创建表单的设计 (GUID) 的全局唯一标识符。 此属性可以为空。 
  
[MAPIUID](mapiuid.md)结构包含唯一标识符的定义。 
  
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

