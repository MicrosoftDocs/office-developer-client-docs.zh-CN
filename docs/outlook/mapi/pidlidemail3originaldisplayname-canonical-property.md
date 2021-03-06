---
title: PidLidEmail3OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail3OriginalDisplayName
api_type:
- COM
ms.assetid: f3fa392a-c3b1-46dd-bf9b-5ce310719542
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e69bcde35bcfec7746893ee18423aca3a24a6c4a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338071"
---
# <a name="pidlidemail3originaldisplayname-canonical-property"></a>PidLidEmail3OriginalDisplayName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定对应于显示名称电子邮件地址的第三个联系人。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidEmail3OriginalDisplayName  <br/> |
|属性集：  <br/> |PSETID_Address  <br/> |
|LONG ID (的一) ：  <br/> |0x000080A4  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>备注

如果 **dispidEmail3AddrType** ([PidLidEmail3AddressType](pidlidemail3addresstype-canonical-property.md)) 属性的值为"SMTP"，则各个 **dispidEmail3OriginalDisplayName** 属性的值应等于各自 **dispidEmail3EmailAddress** ([PidLidEmail3EmailAddress](pidlidemail3emailaddress-canonical-property.md)) 的值。 此属性的目的是显示与 **dispidEmail3EmailAddress** 中的用户友好地址等效的替代用户友好地址。
  
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

