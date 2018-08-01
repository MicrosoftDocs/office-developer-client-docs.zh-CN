---
title: PidTagFreeBusyRangeTimestamp 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFreeBusyRangeTimestamp
api_type:
- HeaderDef
ms.assetid: 142d955f-f92d-485a-80c9-9c72e82af0f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 20bb23690a0d0833960ba3d1f104585c857c825b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777661"
---
# <a name="pidtagfreebusyrangetimestamp-canonical-property"></a>PidTagFreeBusyRangeTimestamp 规范属性

  
  
**适用于**： Outlook 
  
包含的数据时已发布的时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FREEBUSY_RANGE_TIMESTAMP  <br/> |
|标识符：  <br/> |0x6868  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>说明

此属性是自午夜开始，采用协调世界时 (UTC) 1601 年 1 月 1 日的分钟数。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> 发布的用户或资源的可用性。
    
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

