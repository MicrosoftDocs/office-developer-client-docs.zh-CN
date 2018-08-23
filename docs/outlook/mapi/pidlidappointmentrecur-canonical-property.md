---
title: PidLidAppointmentRecur 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentRecur
api_type:
- COM
ms.assetid: 56d6240f-d07b-48d1-aef0-bf57078ea6c3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da38c8f04c0ffe6b4b26551cb23e84275900fcb4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563056"
---
# <a name="pidlidappointmentrecur-canonical-property"></a>PidLidAppointmentRecur 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定定期系列时使用的定期模式和[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中指定的区域之一发生的日期和时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptRecur  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008216  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

此属性指定定期系列时使用的定期模式之一，发生此事件和区域中的详细说明[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)的日期和时间。 此属性的值还包含有关修改和删除例外; 信息如日期、 主题、 位置和其他几个属性的异常的信息。 此属性的定期日历项目中的二进制数据存储为**AppointmentRecurrencePattern**结构。 此属性必须存在在单个实例日历项目。 
  
有一些限制到定期事件：
  
- 在同一天必须启动多个实例。
    
- 匹配项必须不重叠。 具体而言，之后将前一个实例的末尾和定期系列中的下一个实例的开始日期必须发生异常修改实例定期系列中的开始日期。 True 如果定期系列中的前一个或下一个实例异常相同。
    
定期系列的计划取决于其定期模式和范围。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定属性和电子邮件和其他对象提醒的交互模型。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

