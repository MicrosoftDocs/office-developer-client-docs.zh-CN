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
ms.openlocfilehash: de50616664048af6b931a09df7c65461e9ee3399
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331778"
---
# <a name="pidlidappointmentrecur-canonical-property"></a>PidLidAppointmentRecur 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过使用[[OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中指定的定期模式和范围之一, 指定定期系列发生的日期和时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptRecur  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x00008216  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

此属性指定定期系列使用[[OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中详细说明的一种定期模式和范围时发生的日期和时间。 此属性的值还包含有关已修改和已删除异常的信息;诸如日期、主题、位置和其他几个异常属性的信息。 定期日历项目的此属性中的二进制数据存储为**AppointmentRecurrencePattern**结构。 此属性不能在单个实例日历项目中存在。 
  
重复发生有一些限制:
  
- 多个实例不能在同一天开始。
    
- 事件不能重叠。 具体而言, 修改定期系列中实例的开始日期的异常必须在上一实例结束后的某个日期开始, 且在定期系列中的下一个实例开始时。 如果定期系列中的前一个或下一个实例是例外情况, 也是如此。
    
定期系列的日程安排由其定期模式和范围决定。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
[[毫秒-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定用于电子邮件和其他对象提醒的属性和交互模型。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

