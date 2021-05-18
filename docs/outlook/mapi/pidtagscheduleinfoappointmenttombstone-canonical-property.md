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
  
包含表示已拒绝的会议的数据块列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_APPT_TOMBSTONE  <br/> |
|标识符:  <br/> |0x686A  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>备注

数据块以 32 位值的标题开头，定义为：
  
|**值**|**说明**|
|:-----|:-----|
|标示符  <br/> |此字段的值必须是0xBEDEAFCD。  <br/> |
|HeaderSize  <br/> |此字段的值必须0x00000014。  <br/> |
|版本  <br/> |此字段的值必须为 3。  <br/> |
|RecordsCount  <br/> |后续记录计数。  <br/> |
|RecordsSize  <br/> |此字段的值必须0x00000014。  <br/> |
   
标头后跟定义如下的 32 位值的 **RecordsCount** 条目： 
  
|**值**|**说明**|
|:-----|:-----|
|StartTime  <br/> |自 UTC 时间 1601 年 1 月 1 日午夜起，会议对象的开始时间（以分钟数表示）。  <br/> |
|EndTime  <br/> |自 UTC 时间 1601 年 1 月 1 日午夜起，会议对象的结束时间（分钟）。  <br/> |
|GlobalObjectIdSize  <br/> |GlobalObjectId 字段的大小（以字节为单位）。  <br/> |
|GlobalObjectId  <br/> |此记录所代表的LID_GLOBAL_OBJID ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 属性的值。   <br/> |
|UserName  <br/> |前两个字节是字符串PT_STRING8的长度。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

