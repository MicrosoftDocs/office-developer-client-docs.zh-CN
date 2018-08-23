---
title: PidLidRemoteTransport 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidRemoteTransport
api_type:
- COM
ms.assetid: b3b30d6a-05cd-4dd1-a162-20768f12e680
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 124a0d8f23fcff9d1bca9d5debe4a9aa6fb6146c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587115"
---
# <a name="pidlidremotetransport-canonical-property"></a>PidLidRemoteTransport 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
标识哪个帐户的标头项相关联，主要是为了实现 POP 保留在服务器功能。 
  
|||
|:-----|:-----|
|相关的属性  <br/> |dispidRemoteXP  <br/> |
|属性进行设置：  <br/> |PSETID_Remote  <br/> |
|长 ID （盖）：  <br/> |0x00008F03  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |远程邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性是仅对具有邮件类 IPM 的邮件。远程。 Microsoft Outlook 保持在文件夹关联的信息 （从故障） 邮件中，为给定的存储到下载的各种帐户的映射，但它无法在注册表中保留此信息。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

