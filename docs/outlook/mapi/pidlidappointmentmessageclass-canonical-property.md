---
title: PidLidAppointmentMessageClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentMessageClass
api_type:
- COM
ms.assetid: 8b8c8484-0cb4-4842-8b11-de42d97e0140
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7149ba5a4a0378951942df790003b6d09c1155f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358098"
---
# <a name="pidlidappointmentmessageclass-canonical-property"></a>PidLidAppointmentMessageClass 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示 **PR_MESSAGE_CLASS (** 会议请求生成的) [PidTagMessageClass 的 PidTagMessageClass](pidtagmessageclass-canonical-property.md) 属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptMessageClass  <br/> |
|属性集：  <br/> |PSETID_Meeting  <br/> |
|LONG ID (的一) ：  <br/> |0x00000024  <br/> |
|数据类型：  <br/> |PT_TSTRING  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>备注

此属性的值必须为"IPM"。Appointment"或前缀为"IPM"。Appointment."。 此属性不是必需的。
  
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

