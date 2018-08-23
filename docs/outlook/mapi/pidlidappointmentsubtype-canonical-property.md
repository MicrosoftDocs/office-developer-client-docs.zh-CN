---
title: PidLidAppointmentSubType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentSubType
api_type:
- COM
ms.assetid: e2e00af3-1fb3-4314-936a-f480674d3d83
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 78749a61bcbac64ded2c4791d9e239a12c38ce81
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579044"
---
# <a name="pidlidappointmentsubtype-canonical-property"></a>PidLidAppointmentSubType 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定的事件是全天。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptSubType  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008215  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

此属性指定的事件是全天事件，指定的用户。 值为 TRUE 指示事件是全天事件，在这种情况下的开始时间和结束时间必须午夜以便持续时间为 24 小时的倍数，并为至少 24 个小时。 值为 FALSE 或不存在此属性指示该事件不是全天事件。 在客户端或服务器必须时用户碰巧创建 24 小时的事件，即使事件开始和结束午夜推断的值为 TRUE。
  
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

