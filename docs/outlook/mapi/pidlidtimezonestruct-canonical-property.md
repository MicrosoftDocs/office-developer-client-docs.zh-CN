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
ms.openlocfilehash: b9c2a1bbf519379c1735c489c2dcd3fcfb395a60
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346373"
---
# <a name="pidlidtimezonestruct-canonical-property"></a>PidLidTimeZoneStruct 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含映射到[TZREG](https://msdn.microsoft.com/library/bb820983%28v=office.12%29.aspx)结构的保留格式的流, 该格式描述要用于定期约会或会议请求的开始和结束时间的时区。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTimeZoneStruct  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x00008233  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

Microsoft Office Outlook 2003, 早期版本的 Outlook, 以及基于协作数据对象 (CDO) 1.21 的应用程序, 其用户未运行 Outlook 或 Exchange Server 存储提供的日历更新工具的开始时间和结束时间相对于相对时间的定期约会或会议请求, 并存储在**dispidTimeZoneStruct**中创建约会或会议请求的时区。 但是, 这种方案将忽略这一段时间, 时区规则可能会更改, 从而导致在规则发生更改并在不正确的时间发生之前计划用户的一些约会和会议。 未运行 Windows Vista 或未启用自动更新的用户和管理员应使用 Outlook 或 Exchange Server 提供的日历重定工具来调整此类约会和会议请求的时间。 有关可变基日历的这些日历重定工具和 api 的详细信息, 请参阅 "[关于以编程方式重定日历" 以实现夏时制](https://msdn.microsoft.com/library/38b342d9-ab10-04b6-5490-9a45f847a60f%28Office.15%29.aspx)
  
在分析从**dispidTimeZoneStruct**获取的流时, 或者在将**TZREG**结构保留为要提交到**dispidTimeZoneStruct**二进制属性的流时, 使用以下小字节格式的格式。 
  
```cpp
long        lBias;           // offset from GMT
long        lStandardBias;   // offset from bias during standard time
long        lDaylightBias;   // offset from bias during daylight time
WORD        wStandardYear;      // matches the stStandardDate's wYear member
SYSTEMTIME  stStandardDate;  // time to switch to standard time
WORD        wDaylightYear;      // matches the stDaylightDate's wYear field
SYSTEMTIME  stDaylightDate;  // time to switch to daylight time
```

此属性在定期系列上设置, 以指定时区信息, 并指定如何在本地时间与协调通用时间 (UTC) 之间转换时间字段。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
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

