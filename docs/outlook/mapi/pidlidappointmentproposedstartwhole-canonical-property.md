---
title: PidLidAppointmentProposedStartWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentProposedStartWhole
api_type:
- COM
ms.assetid: acc96b0a-bffb-46ef-8c46-b831d165a346
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bdf810ee71f5b79435bb706f8f60f5d4054c7f75
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591694"
---
# <a name="pidlidappointmentproposedstartwhole-canonical-property"></a>PidLidAppointmentProposedStartWhole 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定为**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 计数器建议的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptProposedStartWhole  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008250  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

以协调世界时 (UTC)，必须指定此值。
  
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

