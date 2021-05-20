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
ms.openlocfilehash: ddedc2ca0785be2fe4850ec3cfdf979d1e5f2798
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439441"
---
# <a name="pidlidremotetransport-canonical-property"></a>PidLidRemoteTransport 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
标识与标头项关联的帐户，主要用于实现"在服务器上保留 POP"功能。 
  
|||
|:-----|:-----|
|关联的属性  <br/> |dispidRemoteXP  <br/> |
|属性集：  <br/> |PSETID_Remote  <br/> |
|LONG ID (的一) ：  <br/> |0x00008F03  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |远程邮件  <br/> |
   
## <a name="remarks"></a>备注

此属性仅与具有 IPM 邮件类的邮件相关。远程。 Microsoft Outlook将下载到给定存储的各种帐户的映射保存在文件夹关联信息 (FAI) 邮件中，但它也可以将此信息保存在注册表中。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

