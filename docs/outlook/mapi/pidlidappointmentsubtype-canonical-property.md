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
ms.openlocfilehash: 921d7d8defbdae66bc48072d757f4f58b7d656f0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345414"
---
# <a name="pidlidappointmentsubtype-canonical-property"></a>PidLidAppointmentSubType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定事件是否全天发生。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptSubType  <br/> |
|属性集：  <br/> |PSETID_Appointment  <br/> |
|LONG ID (的一) ：  <br/> |0x00008215  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>备注

此属性指定事件是否是由用户指定的全天事件。 TRUE 值表示事件是全天事件，在这种情况下，开始时间和结束时间必须为午夜，以便持续时间为 24 小时，并且至少为 24 小时。 FALSE 值或缺少此属性指示事件不是全天事件。 当用户恰好创建 24 小时的事件时，客户端或服务器不得将该值推断为 TRUE，即使该事件在午夜开始和结束也是如此。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

