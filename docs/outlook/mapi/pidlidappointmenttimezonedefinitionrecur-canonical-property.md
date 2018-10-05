---
title: PidLidAppointmentTimeZoneDefinitionRecur 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentTimeZoneDefinitionRecur
api_type:
- COM
ms.assetid: 52fd57a0-9e34-4452-9ecd-2acb454446c9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5e9b06178a1517fc1c8652b0d667faf1afc77cc
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389300"
---
# <a name="pidlidappointmenttimezonedefinitionrecur-canonical-property"></a>PidLidAppointmentTimeZoneDefinitionRecur 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含映射到的存储的说明创建定期约会或会议请求时使用的时区[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构持久化格式的流。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptTZDefRecur  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008260  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>说明

自 Microsoft Office Outlook 2007 和基于上协作数据对象 (CDO) 1.2.1 （英文) 的解决方案的 Microsoft Outlook 的运行 Outlook 或 Exchange Server 日历版本更新工具使用**dispidApptTZDefRecur**和**dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) 属性以确定是否应调整定期会议，是否更改时区的规则。 这些属性必须保持同步，因为旧客户端可能仍然操作**dispidTimeZoneStruct**属性。 若要检测是否同步两个属性，规则相匹配**dispidTimeZoneStruct** **wFlags**成员应具有的 TZRULE_FLAG_RECUR_CURRENT_TZREG 标记设置。 如果未设置此标志，或将其设置**dispidTimeZoneStruct**属性中的规则与标记的规则不匹配时，应丢弃**dispidApptTZDefRecur**属性，并应改用**dispidTimeZoneStruct** 。 
  
当您编写的**dispidApptTZDefRecur**和**dispidTimeZoneStruct**属性到新的定期会议，或时使任意选择使用**dispidTimeZoneStruct**属性，所在的时区 （的当前定义应使用根据 Windows 注册表中）。 
  
分析程序必须注意，它读取从**dispidApptTZDefRecur**，获得一个流或时它所**TZDEFINITION**持久化到承诺如**dispidApptTZDefRecur**二进制属性的流。 有关详细信息，请参阅[关于保留 TZDEFINITION 到流提交到二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。
  
 **dispidApptTZDefRecur**指定介绍如何将收件人和与协调世界时 (UTC) 转换会议日期和时间定期系列的时区信息。 如果设置此属性，但它具有与由**dispidTimeZoneStruct**代表的数据不一致的数据，客户端必须使用**dispidTimeZoneStruct** ，而不是**dispidApptTZDefRecur**。 如果未设置**dispidApptTZDefRecur** ，将使用**PidLidTimeZoneStruct**属性。 此 BLOB 中的字段顺序-little-endian 字节编码。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

