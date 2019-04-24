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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345351"
---
# <a name="pidlidappointmenttimezonedefinitionrecur-canonical-property"></a>PidLidAppointmentTimeZoneDefinitionRecur 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含映射到[TZDEFINITION](https://msdn.microsoft.com/library/0ae21571-2299-6407-807c-428668bb6798%28Office.15%29.aspx)结构的保留格式的流, 该格式存储在创建定期约会或会议请求时所使用的时区的说明。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptTZDefRecur  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x00008260  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

microsoft Office outlook 2007 版本的 microsoft Outlook 和基于协作数据对象 (CDO) 1.2.1 的解决方案 (已运行 Outlook 或 Exchange Server 日历更新工具) 使用**dispidApptTZDefRecur**和**dispidTimeZoneStruct** ([PidLidTimeZoneStruct](pidlidtimezonestruct-canonical-property.md)) 属性, 以确定是否应在时区的规则更改时调整定期会议。 这些属性必须是同步的, 因为旧版客户端仍可能会对**dispidTimeZoneStruct**属性进行操作。 若要检测这两个属性是否同步, 匹配**dispidTimeZoneStruct**的规则的**wFlags**成员应设置 TZRULE_FLAG_RECUR_CURRENT_TZREG 标志。 如果未设置此标志, 或者设置了此标志, 并且**dispidTimeZoneStruct**属性中的规则与标记的规则不匹配, 则应丢弃**dispidApptTZDefRecur**属性, 而应改用**dispidTimeZoneStruct** 。 
  
当您将**dispidApptTZDefRecur**和**dispidTimeZoneStruct**属性同时写入新的定期会议时, 或者当您使用**dispidTimeZoneStruct**属性进行任意选择时, 时区的当前定义 (应使用 Windows 注册表)。 
  
分析器在读取从**dispidApptTZDefRecur**获取的流时, 或者在它保持**TZDEFINITION**为对二进制属性 (如**dispidApptTZDefRecur**) 承诺的流时, 必须小心。 有关详细信息, 请参阅[关于将 TZDEFINITION 保留给 stream 以提交给二进制属性](https://msdn.microsoft.com/library/0dec535d-d48f-39a5-97d5-0bd109134b3b%28Office.15%29.aspx)。
  
 **dispidApptTZDefRecur**指定了描述如何将定期系列上的会议日期和时间转换为协调世界时 (UTC) 的时区信息。 如果设置了此属性, 但它包含的数据与**dispidTimeZoneStruct**所表示的数据不一致, 则客户端必须使用**dispidTimeZoneStruct**而不是**dispidApptTZDefRecur**。 如果未设置**dispidApptTZDefRecur** , 则改为使用**PidLidTimeZoneStruct**属性。 此 BLOB 中的字段以小字节序字节顺序进行编码。 
  
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

