---
title: PidLidOldWhenEndWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOldWhenEndWhole
api_type:
- COM
ms.assetid: 788227e9-9bcf-465c-886c-746dbc665230
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b84de421b73fd328467dab8ea1f5888b9a37ecf1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776948"
---
# <a name="pidlidoldwhenendwhole-canonical-property"></a>PidLidOldWhenEndWhole 规范属性

  
  
**适用于**： Outlook 
  
指示会议更新之前的**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的原始值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidOldWhenEndWhole  <br/> |
|属性进行设置：  <br/> |PSETID_Meeting  <br/> |
|长 ID （盖）：  <br/> |0x0000002A  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>说明

此属性不是必需的。
  
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

