---
title: PidLidAppointmentEndWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentEndWhole
api_type:
- COM
ms.assetid: f6fd33d6-04fb-4801-a004-fb80a14ca79d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eaff90de919c1bdc04983bce32a2aa808ae56013
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358896"
---
# <a name="pidlidappointmentendwhole-canonical-property"></a>PidLidAppointmentEndWhole 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示约会结束的日期和时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptEndWhole  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x0000820E  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

此属性对应于 Microsoft Office Outlook 对象模型中的约会的**dispidApptEndWhole**属性。 
  
这将指定事件的结束日期和时间;它必须采用协调通用时间 (UTC), 并且必须大于**dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 属性的值。 对于定期系列, **dispidApptEndWhole**属性是第一个实例根据定期模式的结束日期和时间。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

