---
title: PidLidLogDuration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogDocumentSaved
api_type:
- COM
ms.assetid: 012a3f6e-fd16-4dc9-845d-2bf4cebeaa42
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: cc2d52ec183cc336bf126b1fda9a85d41f704f7d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776906"
---
# <a name="pidlidlogduration-canonical-property"></a>PidLidLogDuration 规范属性

  
  
**适用于**： Outlook 
  
表示的工期，以分钟为单位的日记邮件。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |dispidLogDuration  <br/> |
|属性进行设置：  <br/> |PSETID_Log  <br/> |
|长 ID （盖）：  <br/> |0x00008707  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |日记  <br/> |
   
## <a name="remarks"></a>备注

持续时间，以分钟为单位的值必须为**dispidLogEnd** ([PidLidLogEnd](pidlidlogend-canonical-property.md)) 和**dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) 属性之间的差异的活动。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的日志。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

