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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345379"
---
# <a name="pidlidappointmenttimezonedefinitionenddisplay-canonical-property"></a>PidLidAppointmentTimeZoneDefinitionEndDisplay 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含映射到[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构的保留格式的流, 该格式存储在选择单实例约会或会议请求的结束时间时使用的时区的说明。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptTZDefEndDisplay  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x0000825F  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

Microsoft Office Outlook 2003 或更低版本, 基于协作数据对象 (CDO) 1.2.1 的解决方案以及未运行 Outlook 或 Microsoft Exchange Server 的日历更新工具的解决方案, 存储单实例的开始时间和结束时间协调世界时 (UTC) 的约会和会议请求。 这些客户端不会存储创建约会或会议请求的时区的任何信息。
  
由于 microsoft Office Outlook 2007 以及基于 CDO 1.2.1 的解决方案 (已运行 Outlook 或 Exchange Server 日历更新工具), microsoft Outlook 的版本将使用**dispidApptTZDefEndDisplay**存储结束时间的时区。 **dispidApptTZDefEndDisplay**在原始时区中显示约会或会议计划的时间, 并确定是否应在时区的规则更改时调整结束时间。 如果缺少此属性, 则使用由**dispidApptTZDefStartDisplay** ([PidLidAppointmentTimeZoneDefinitionStartDisplay](pidlidappointmenttimezonedefinitionstartdisplay-canonical-property.md)) 属性指定的时区。 如果**dispidApptTZDefStartDisplay**缺失或无效, 则假定为当前本地时区。 **dispidApptTZDefEndDisplay**仅用于显示目的, 在定期扩展中不使用。 
  
分析器在读取从**dispidApptTZDefEndDisplay**获取的流时, 或者在它保持**TZDEFINITION**为对二进制属性 (如**dispidApptTZDefEndDisplay**) 承诺的流时, 必须小心。 有关详细信息, 请参阅[关于将 TZDEFINITION 保留给 stream 以提交给二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。
  
 **dispidApptTZDefEndDisplay**指定**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的时区信息。 **dispidApptTZDefEndDisplay**的格式、约束和计算与在**dispidApptTZDefStartDisplay**属性中指定的格式、约束和计算相同。 
  
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

