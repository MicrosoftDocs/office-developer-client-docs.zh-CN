---
title: PidLidSharingProviderName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingProviderName
api_type:
- COM
ms.assetid: 67e6497c-e053-4b2d-a81c-c6cf6017f8bd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 53dd5b0a808ca818a6086c09a9e59220a6d6d654
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593457"
---
# <a name="pidlidsharingprovidername-canonical-property"></a>PidLidSharingProviderName 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定由**dispidSharingProviderGuid** ([PidLidSharingProviderGuid](pidlidsharingproviderguid-canonical-property.md)) 标识的共享服务提供商的用户可显示名称。 这是邮件的共享的属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSharingProviderName  <br/> |
|属性进行设置：  <br/> |PSETID_Sharing  <br/> |
|长 ID （盖）：  <br/> |0x00008A02  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |共享  <br/> |
   
## <a name="remarks"></a>注解

应忽略此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)
  
> 共享客户端之间的邮箱文件夹。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

