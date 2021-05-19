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
  
使用 [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中指定的定期模式和范围之一指定定期系列的发生日期和时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptRecur  <br/> |
|属性集：  <br/> |PSETID_Appointment  <br/> |
|LONG ID (的一) ：  <br/> |0x00008216  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>备注

此属性通过使用 [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中详述的定期模式和范围之一来指定发生定期系列的日期和时间。 此属性的值还包含有关修改和删除的异常的信息;信息，例如日期、主题、位置和例外的其他几个属性。 此属性中定期日历项目的二进制数据存储为 **AppointmentRecurrencePattern** 结构。 此属性不能存在于单个实例日历项目上。 
  
定期存在一些限制：
  
- 多个实例不得在同一天启动。
    
- 事件不得重叠。 具体而言，修改定期系列中实例的开始日期的异常必须在上一实例结束之后和定期系列中下一个实例的开始日期发生。 如果定期系列中的上一个实例或下一个实例为例外，则同样如此。
    
定期系列的日程安排由定期系列的定期模式范围。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定电子邮件和其他对象提醒的属性和交互模型。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

