---
title: PidLidTimeZoneStruct 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTimeZoneStruct
api_type:
- COM
ms.assetid: 2acf0036-2f3e-4f90-8614-7aa667860f74
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a1a96cdb3aed03b9621097f1ef858a09391c0693
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777115"
---
# <a name="pidlidtimezonestruct-canonical-property"></a>PidLidTimeZoneStruct 规范属性

  
  
**适用于**： Outlook 
  
包含映射到[TZREG](http://msdn.microsoft.com/en-us/library/bb820983%28v=office.12%29.aspx)结构，其中介绍了用于定期约会或会议请求的开始和结束时间的时区的持久化格式的流。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTimeZoneStruct  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008233  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>说明

Microsoft Office Outlook 2003，早期版本的 Outlook 和应用程序上协作数据对象 (CDO) 1.21 基于其用户还未运行 Outlook 或 Exchange Server 提供的日历更新工具存储的开始时间和结束时间定期约会或会议请求为相对的时间，并将存储其中**dispidTimeZoneStruct**中创建约会或会议请求的时区。 但是，将忽略此方案，随时间推移，时区规则可以更改，导致某些约会和会议安排规则更改，并在不正确的时间之前该用户。 用户和用户未运行 Windows Vista 或那些没有开启自动更新的管理员应使用定位提供 Outlook 或 Exchange Server 调整此类约会和会议请求的时间的工具的日历。 有关这些日历调整工具和重定日历基值的 Api 的详细信息，请参阅[关于编程方式为夏时制调整日历](http://msdn.microsoft.com/library/38b342d9-ab10-04b6-5490-9a45f847a60f%28Office.15%29.aspx)
  
使用以下-little-endian 格式时分析流持久化到流**TZREG**结构时所获得从**dispidTimeZoneStruct**，或提交到**dispidTimeZoneStruct**二进制属性。 
  
```cpp
long        lBias;           // offset from GMT
long        lStandardBias;   // offset from bias during standard time
long        lDaylightBias;   // offset from bias during daylight time
WORD        wStandardYear;      // matches the stStandardDate's wYear member
SYSTEMTIME  stStandardDate;  // time to switch to standard time
WORD        wDaylightYear;      // matches the stDaylightDate's wYear field
SYSTEMTIME  stDaylightDate;  // time to switch to daylight time
```

此属性设置为定期系列上指定时区信息，并指定如何转换本地时间与协调世界时 (UTC) 之间的时间字段。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
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

