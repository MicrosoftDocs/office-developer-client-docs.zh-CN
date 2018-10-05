---
title: PidLidAppointmentTimeZoneDefinitionEndDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentTimeZoneDefinitionEndDisplay
api_type:
- COM
ms.assetid: 7b6193cb-612b-408e-b9bc-285df313e2cc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 24ccd25a1d799f3146bd230e5156be0051104f47
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382748"
---
# <a name="pidlidappointmenttimezonedefinitionenddisplay-canonical-property"></a>PidLidAppointmentTimeZoneDefinitionEndDisplay 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含映射到的存储选择单实例约会或会议请求的结束时间时使用的时区的说明[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构持久化格式的流。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptTZDefEndDisplay  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x0000825F  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>说明

Microsoft Office Outlook 2003 或更早版本和解决方案的基于上协作数据对象 (CDO) 1.2.1 （英文) 和 Outlook 或 Microsoft Exchange Server 已不运行日历更新工具存储的开始时间和结束时间的单实例约会和会议请求以协调世界时 (UTC)。 这些客户端不存储在其中创建约会或会议请求的时区的任何信息。
  
自 Microsoft Office Outlook 2007，并基于 CDO 1.2.1 （英文) 的解决方案的 Microsoft Outlook 的运行 Outlook 或 Exchange Server 日历版本更新工具使用**dispidApptTZDefEndDisplay**存储的结束时间的时区。 **dispidApptTZDefEndDisplay**显示该约会或会议中原始时区，它已安排，并确定是否更改时区的规则是否应调整的结束时间。 如果该属性不存在，则使用**dispidApptTZDefStartDisplay** ([PidLidAppointmentTimeZoneDefinitionStartDisplay](pidlidappointmenttimezonedefinitionstartdisplay-canonical-property.md)) 属性指定的时区。 如果**dispidApptTZDefStartDisplay**缺失或无效，则假定当前的本地时区。 **dispidApptTZDefEndDisplay**用于仅显示目的，并且不使用定期扩展中。 
  
分析程序必须注意，它读取从**dispidApptTZDefEndDisplay**，获得一个流或时它所**TZDEFINITION**持久化到承诺如**dispidApptTZDefEndDisplay**二进制属性的流。 有关详细信息，请参阅[关于保留 TZDEFINITION 到流提交到二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。
  
 **dispidApptTZDefEndDisplay**指定时区属性的信息的**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md))。 格式、 约束和计算**dispidApptTZDefEndDisplay**是**dispidApptTZDefStartDisplay**属性中指定相同的。 
  
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

