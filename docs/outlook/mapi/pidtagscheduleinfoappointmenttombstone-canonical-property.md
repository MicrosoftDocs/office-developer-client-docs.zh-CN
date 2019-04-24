---
title: PidTagScheduleInfoAppointmentTombstone 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoAppointmentTombstone
api_type:
- COM
ms.assetid: 6b82e2ee-992f-4cbe-bdcb-e7465e556640
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7a7134a037aa4845ae22ab18899d27f1e50d6b7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321320"
---
# <a name="pidtagscheduleinfoappointmenttombstone-canonical-property"></a>PidTagScheduleInfoAppointmentTombstone 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含表示已被谢绝的会议的数据块的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_APPT_TOMBSTONE  <br/> |
|标识符:  <br/> |0x686A  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |闲/忙  <br/> |
   
## <a name="remarks"></a>注解

数据块开头的标头为32位值, 其定义为:
  
|**Value**|**说明**|
|:-----|:-----|
|标示符  <br/> |此字段必须为0xBEDEAFCD 值。  <br/> |
|HeaderSize  <br/> |此字段的值必须为0x00000014。  <br/> |
|Version  <br/> |此字段的值必须为3。  <br/> |
|RecordsCount  <br/> |追随的记录数。  <br/> |
|RecordsSize  <br/> |此字段的值必须为0x00000014。  <br/> |
   
头的后面是32位值的**RecordsCount**项定义为: 
  
|**Value**|**说明**|
|:-----|:-----|
|StartTime  <br/> |自午夜年1月1日 (UTC) 起, 会议对象的开始时间 (以分钟为单位)。  <br/> |
|EndTime  <br/> |自午夜、1601年1月1日午夜起, 会议对象的结束时间 (以分钟为单位)。  <br/> |
|GlobalObjectIdSize  <br/> |GlobalObjectId 字段的大小 (以字节为单位)。  <br/> |
|GlobalObjectId  <br/> |此记录表示的会议的**LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 属性的值。  <br/> |
|UserName  <br/> |前两个字节是 PT_STRING8 字符串的长度, 如下所示。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

