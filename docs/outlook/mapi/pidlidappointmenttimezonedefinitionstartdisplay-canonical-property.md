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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345015"
---
# <a name="pidlidappointmenttimezonedefinitionstartdisplay-canonical-property"></a>PidLidAppointmentTimeZoneDefinitionStartDisplay 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含映射到 [TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx) 结构的持久格式的流，该流存储选择单实例约会或会议请求的开始时间时所使用的时区的说明。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptTZDefStartDisplay  <br/> |
|属性集：  <br/> |PSETID_Appointment  <br/> |
|LONG ID (的一) ：  <br/> |0x0000825E  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>备注

Microsoft Office Outlook 2003 或更早版本，以及基于协作数据对象 (CDO) 1.2.1 且尚未运行 Outlook 或 Microsoft Exchange Server 的日历更新工具的解决方案，将单实例约会和会议请求的开始时间和结束时间存储为协调世界时 (UTC) 。 这些客户端不存储创建约会或会议请求的时区的任何信息。
  
Outlook 2007 Microsoft Office Outlook 及基于 CDO 1.2.1 且已运行 Outlook 或 Exchange Server 日历更新工具的解决方案使用此属性存储开始时间的时区。 **dispidApptTZDefStartDisplay** 属性显示已安排在原始时区的约会或会议。 它确定是否应在时区规则更改时调整开始时间。 如果缺少此属性，则假定为当前本地时区。 此属性仅用于显示目的，不用于定期扩展。 
  
分析程序在读取从此属性获取的流时，或将 **TZDEFINITION** 持久化到流以承诺使用二进制属性（如 **dispidApptTZDefStartDisplay）** 时必须小心。 有关详细信息，请参阅关于 [将 TZDEFINITION 持久化到流以提交到二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。
  
此属性指定 **dispidApptStartWhole** 属性的时区 ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 信息。 **dispidApptTZDefStartDisplay** 的值用于将起始日期和时间从 UTC 转换为本地时区，以便进行显示。 对于此属性 **指定的每个 TZRULE，TZRULE_FLAG_RECUR_CURRENT_TZREG** 设置该标志。 例如，如果 **TZRULE** 是有效规则，则字段值 **TZRULE** 必须为"0x0002";否则，它必须是"0x0000"。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议Exchange Server的引用。
    
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

