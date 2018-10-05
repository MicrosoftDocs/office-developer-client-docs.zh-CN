---
title: PidLidEmail1OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail1OriginalDisplayName
api_type:
- COM
ms.assetid: 991c2969-0180-4c7d-95ee-e62fd24d67ef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a20ae8e3f19073bfb88d58db516a0e5f93d91445
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399863"
---
# <a name="pidlidemail1originaldisplayname-canonical-property"></a>PidLidEmail1OriginalDisplayName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定对应于指定为该联系人的电子邮件地址的第一个显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidEmail1OriginalDisplayName  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008084  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

如果**dispidEmail1AddrType** ([PidLidEmail1AddressType](pidlidemail1addresstype-canonical-property.md)) 属性的值为"SMTP"，各自**dispidEmail1OriginalDisplayName**属性的值应等于各自**的值dispidEmail1EmailAddress** ([PidLidEmail1EmailAddress](pidlidemail1emailaddress-canonical-property.md)) 属性。 此属性显示替代的用户友好地址，它等效于**dispidEmail1EmailAddress**属性中。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

