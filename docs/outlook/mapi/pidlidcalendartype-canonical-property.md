---
title: PidLidCalendarType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCalendarType
api_type:
- COM
ms.assetid: 06e066f1-2b7d-4a6b-b88c-85a9bfa83bd3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6a33559a3e047890153f6a8e0ab40e49c2bf80cb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396517"
---
# <a name="pidlidcalendartype-canonical-property"></a>PidLidCalendarType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定**dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 属性中的日历类型字段的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |LID_CALENDAR_TYPE  <br/> |
|属性进行设置：  <br/> |PSETID_Meeting  <br/> |
|长 ID （盖）：  <br/> |0x0000001C  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>说明

当会议请求表示定期系列或异常时，这是**dispidApptRecur**属性中的日历类型字段的值。 否则为不设置此属性，将其假定为 0。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

