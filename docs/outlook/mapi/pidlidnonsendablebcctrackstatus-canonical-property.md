---
title: PidLidNonSendableBccTrackStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNonSendableBccTrackStatus
api_type:
- COM
ms.assetid: daad8735-a3da-4a0b-9329-6eb253c281fd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da2bd4e87c7076872ccff708983cfbe631b27122
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776917"
---
# <a name="pidlidnonsendablebcctrackstatus-canonical-property"></a>PidLidNonSendableBccTrackStatus 规范属性

  
  
**适用于**： Outlook 
  
包含的每个与会者**dispidNonSendableBCC** ([PidLidNonSendableBcc](pidlidnonsendablebcc-canonical-property.md)) 属性中列出的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidNonSendBccTrackStatus  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x00008545  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

仅当**dispidNonSendableBCC**属性设置时，此属性是必需的。 此属性中的值的数目必须等于**dispidNonSendableBCC**中值的数目。 此属性中的每个值对应于在同一索引的**dispidNonSendableBCC**属性中的参与者。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

