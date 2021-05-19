---
title: PidLidToAttendeesString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToAttendeesString
api_type:
- COM
ms.assetid: ca1eedba-c617-4403-8490-315ab75f2edb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea0cd256b025ae519272f32522bebbe6e9e17b5e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339809"
---
# <a name="pidlidtoattendeesstring-canonical-property"></a>PidLidToAttendeesString 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含同时需要与会者的所有可发送与会者的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidToAttendeesString  <br/> |
|属性集：  <br/> |PSETID_Appointment  <br/> |
|LONG ID (的一) ：  <br/> |0x0000823B  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>备注

每个与会者的值为与会者通讯簿PR_DISPLAY_NAME ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的默认值。  单独的条目必须以分号分隔，后跟空格。 此属性不是必需的。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
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

