---
title: PidLidTimeZone 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTimeZone
api_type:
- COM
ms.assetid: ffbab371-1a1d-4aa4-ad31-17549a74513c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 90dc35e72fc863ab12d9d6df9c54def7af788efd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568887"
---
# <a name="pidlidtimezone-canonical-property"></a>PidLidTimeZone 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定定期会议的信息所在的时区。
  
|||
|:-----|:-----|
|相关属性：  <br/> |LID_TIME_ZONE  <br/> |
|属性进行设置：  <br/> |PSETID_Meeting  <br/> |
|长 ID （盖）：  <br/> |0x0000000C  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

如果未设置**dispidApptRecur** ([PidLidAppointmentRecur](pidlidappointmentrecur-canonical-property.md)) 属性，但如果**LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) 属性为 TRUE，则**LID_IS_EXCEPTION** ([仅读取此属性PidLidIsException](pidlidisexception-canonical-property.md)) 属性为 FALSE。 较低的字指定表中包含的信息所在的时区的索引。 从右上单词，读取仅最高的位。 如果设置此位，然后所在的时区引用将不遵循将遵循夏令时 (DST)，否则为 DST 日期[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中详细介绍。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

