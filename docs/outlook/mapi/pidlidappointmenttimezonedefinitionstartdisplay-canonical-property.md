---
title: PidLidAppointmentTimeZoneDefinitionStartDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentTimeZoneDefinitionStartDispl
api_type:
- COM
ms.assetid: 08239670-3211-420c-99d7-0056ed967cb8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 504dc4b1cecb9798590e4a15968acc3aa98fe4a6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399898"
---
# <a name="pidlidappointmenttimezonedefinitionstartdisplay-canonical-property"></a>PidLidAppointmentTimeZoneDefinitionStartDisplay 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含映射到的存储选择单实例约会或会议请求的开始时间时使用的时区的说明[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构持久化格式的流。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptTZDefStartDisplay  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x0000825E  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>说明

Microsoft Office Outlook 2003 或更早版本和解决方案的基于上协作数据对象 (CDO) 1.2.1 （英文) 和 Outlook 或 Microsoft Exchange Server 已不运行日历更新工具存储的开始时间和结束时间的单实例约会和会议请求以协调世界时 (UTC)。 这些客户端不存储在其中创建约会或会议请求的时区的任何信息。
  
版本的 Microsoft Office Outlook 2007 和基于 CDO 1.2.1 （英文) 的解决方案运行 Outlook 或 Exchange Server 日历更新工具相 Outlook 使用此属性存储的开始时间的时区。 **DispidApptTZDefStartDisplay**属性显示该约会或会议中原始时区安排了它。 如果更改时区的规则是否应调整的开始时间，它确定。 如果该属性不存在，则假定当前的本地时区。 此属性用于显示仅并不用于定期扩展。 
  
分析程序必须注意，它读取此属性，从获取流或时它所**TZDEFINITION**持久化到承诺如**dispidApptTZDefStartDisplay**二进制属性的流。 有关详细信息，请参阅[关于保留 TZDEFINITION 到流提交到二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。
  
此属性指定时区属性的信息的**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md))。 **DispidApptTZDefStartDisplay**的值用于将开始日期和时间从 UTC 转换为用于显示本地时区。 为此属性指定每个**TZRULE** ，不得设置 TZRULE_FLAG_RECUR_CURRENT_TZREG 标志。 例如，如果**TZRULE**是有效的规则，字段， **TZRULE**的值必须是"0x0002";否则，它必须是"0x0000"。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和引用相关的 Exchange Server 协议规范正在
    
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

