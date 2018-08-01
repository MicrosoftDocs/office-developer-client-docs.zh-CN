---
title: PidTagContentReturnRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentReturnRequested
api_type:
- HeaderDef
ms.assetid: f86f7c59-42ab-4ac0-80fe-c985103e6bd6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b4aaf05cdd8c85736215bd0d0f3a8c5c9dafecf0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777488"
---
# <a name="pidtagcontentreturnrequested-canonical-property"></a>PidTagContentReturnRequested 规范属性

  
  
**适用于**： Outlook 
  
包含 TRUE，则应与原件报告返回一条消息。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTENT_RETURN_REQUESTED  <br/> |
|标识符：  <br/> |0x000A  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Report  <br/> |
   
## <a name="remarks"></a>注解

如果未设置此属性，MAPI 会将其视为 TRUE 值。 
  
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

