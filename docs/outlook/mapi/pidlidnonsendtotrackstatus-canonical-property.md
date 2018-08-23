---
title: PidLidNonSendToTrackStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNonSendToTrackStatus
api_type:
- COM
ms.assetid: 50fec332-e7df-4bc6-8c50-59b9ca545f89
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cf9d11b7a53ee0b9911e32cb3c3e2a0a490e4729
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592785"
---
# <a name="pidlidnonsendtotrackstatus-canonical-property"></a>PidLidNonSendToTrackStatus 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的每个与会者的**dispidNonSendableTo** ([PidLidNonSendableTo](pidlidnonsendableto-canonical-property.md)) 属性中列出的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidNonSendToTrackStatus  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x00008543  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

仅当**dispidNonSendableTo**属性设置时，此属性是必需的。 此属性中的值的数目必须等于**dispidNonSendableTo**中值的数目。 此属性中的每个 PT_LONG 值对应于**dispidNonSendableTo**属性在同一索引中的与会者。 
  
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

