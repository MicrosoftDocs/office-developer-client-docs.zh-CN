---
title: PidLidEmail2OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail2OriginalDisplayName
api_type:
- COM
ms.assetid: 0b648ef6-86ed-40ee-b068-8fcde7e0fe75
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7fb7e5afa6a1c050a5d91274bc4f82439fb98640
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337959"
---
# <a name="pidlidemail2originaldisplayname-canonical-property"></a>PidLidEmail2OriginalDisplayName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定对应于显示名称电子邮件地址的第二个联系人。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidEmail2OriginalDisplayName  <br/> |
|属性集：  <br/> |PSETID_Address  <br/> |
|LONG ID (的一) ：  <br/> |0x00008094  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>备注

如果 **dispidEmail2AddrType** ([PidLidEmail2AddressType](pidlidemail2addresstype-canonical-property.md)) 属性的值为"SMTP"，则各个 **PidLidEmail2OriginalDisplayName** 属性的值应等于各自的 **dispidEmail2EmailAddress** ([PidLidEmail2EmailAddress](pidlidemail2emailaddress-canonical-property.md)) 属性的值。 此属性的目的是显示与 **dispidEmail2EmailAddress** 中的用户友好地址等效的替代用户友好地址。
  
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

