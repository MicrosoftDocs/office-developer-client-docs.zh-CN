---
title: PidTagExceptionReplaceTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExceptionReplaceTime
api_type:
- HeaderDef
ms.assetid: bd4d1311-15e4-4275-a967-c6d11d2e48d2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 20893f7c3d64698f70ae26c09c2d7ddc64ce3f9d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569930"
---
# <a name="pidtagexceptionreplacetime-canonical-property"></a>PidTagExceptionReplaceTime 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示原始日期和时间，如果未异常时应出现定期模式中的实例。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EXCEPTION_REPLACETIME  <br/> |
|标识符：  <br/> |0x7FF9  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |类定义消息非可传送  <br/> |
   
## <a name="remarks"></a>注解

以协调世界时 (UTC)，必须指定此值。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
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

