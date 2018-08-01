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
ms.openlocfilehash: 37a6d101f6ee9c04236253e143aff3a51a9208d3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778329"
---
# <a name="pidtagscheduleinfoappointmenttombstone-canonical-property"></a>PidTagScheduleInfoAppointmentTombstone 规范属性

  
  
**适用于**： Outlook 
  
包含表示已拒绝的会议数据块的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_APPT_TOMBSTONE  <br/> |
|标识符：  <br/> |0x686A  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>说明

数据块开始使用定义为 32 位值的标头：
  
|**值**|**说明**|
|:-----|:-----|
|标示符  <br/> |此字段必须 0xBEDEAFCD 的值。  <br/> |
|HeaderSize  <br/> |此字段必须具有值 0x00000014。  <br/> |
|版本  <br/> |此字段必须具有值 3。  <br/> |
|RecordsCount  <br/> |按照的记录数。  <br/> |
|RecordsSize  <br/> |此字段必须具有值 0x00000014。  <br/> |
   
标头是后跟的 32 位值定义为**RecordsCount**条目： 
  
|**值**|**说明**|
|:-----|:-----|
|StartTime  <br/> |以分钟为单位，自午夜，1601 年 1 月 1 日，UTC 会议对象的开始时间。  <br/> |
|EndTime  <br/> |以分钟为单位，自午夜，1601 年 1 月 1 日，UTC 会议对象的结束时间。  <br/> |
|GlobalObjectIdSize  <br/> |以字节为单位 GlobalObjectId 字段的大小。  <br/> |
|GlobalObjectId  <br/> |这记录会议的**LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 属性的值表示。  <br/> |
|UserName  <br/> |前两个字节是遵循 PT_STRING8 字符串的长度。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

