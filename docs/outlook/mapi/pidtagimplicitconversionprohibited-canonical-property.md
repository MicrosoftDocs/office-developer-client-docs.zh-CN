---
title: PidTagImplicitConversionProhibited 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagImplicitConversionProhibited
api_type:
- HeaderDef
ms.assetid: c6cb5a86-0105-4743-9f8e-b832e898da52
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dcfaf9f4e71a13a8697da0cac98f7ea9cc3d8708
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777724"
---
# <a name="pidtagimplicitconversionprohibited-canonical-property"></a>PidTagImplicitConversionProhibited 规范属性

  
  
**适用于**： Outlook 
  
如果邮件传输代理 (MTA) 禁止发出隐式消息文本转换，包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IMPLICIT_CONVERSION_PROHIBITED  <br/> |
|标识符：  <br/> |0x0016  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Server  <br/> |
   
## <a name="remarks"></a>说明

如果此属性为 TRUE，则在邮件系统必须不执行任何内容转换对邮件除非明确请求**PR_EXPLICIT_CONVERSION** ([PidTagExplicitConversion](pidtagexplicitconversion-canonical-property.md)) 属性分别为每个收件人。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

