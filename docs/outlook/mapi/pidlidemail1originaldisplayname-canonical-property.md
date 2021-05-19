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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335040"
---
# <a name="pidlidemail1originaldisplayname-canonical-property"></a>PidLidEmail1OriginalDisplayName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定第一显示名称对应于为联系人指定的电子邮件地址。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidEmail1OriginalDisplayName  <br/> |
|属性集：  <br/> |PSETID_Address  <br/> |
|LONG ID (的一) ：  <br/> |0x00008084  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>备注

如果 **dispidEmail1AddrType** ([PidLidEmail1AddressType](pidlidemail1addresstype-canonical-property.md)) 属性的值为"SMTP"，则各个 **dispidEmail1OriginalDisplayName** 属性的值应等于各自的 **dispidEmail1EmailAddress** ([PidLidEmail1EmailAddress](pidlidemail1emailaddress-canonical-property.md)) 属性的值。 此属性显示与 **dispidEmail1EmailAddress** 属性中的用户友好地址等效的备用用户友好地址。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

