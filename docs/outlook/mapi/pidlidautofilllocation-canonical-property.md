---
title: PidLidAutoFillLocation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAutoFillLocation
api_type:
- COM
ms.assetid: e4db6cae-4730-45d0-8b8a-9bd484c8bd3f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 31cabf50602f9e0f7a70118ddc794387990862ad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591266"
---
# <a name="pidlidautofilllocation-canonical-property"></a>PidLidAutoFillLocation 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示从表示的资源 RecipientRow **dispidLocation** ([PidLidLocation](pidlidlocation-canonical-property.md)) 属性的值设置为**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidAutoFillLocation  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x0000823A  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

RecipientRow 的详细信息，请参阅[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)中指定的邮件和附件对象协议。
  
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

