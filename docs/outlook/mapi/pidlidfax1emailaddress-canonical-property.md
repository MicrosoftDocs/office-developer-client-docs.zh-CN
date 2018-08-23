---
title: PidLidFax1EmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFax1EmailAddress
api_type:
- COM
ms.assetid: 416c2d27-cf85-45a9-86e8-0b042e327c19
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 69d107043ed3144823ad5aa0db6dfd6c7d16b0ee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577217"
---
# <a name="pidlidfax1emailaddress-canonical-property"></a>PidLidFax1EmailAddress 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定联系人的商务传真的电子邮件地址。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFax1EmailAddress  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x000080B3  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>注解

此属性，如果存在此参数，应会包含一个用户可读的显示名称后, 跟"@"字符后, 跟传真号码。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

