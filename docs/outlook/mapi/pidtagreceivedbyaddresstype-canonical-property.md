---
title: PidTagReceivedByAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedByAddressType
api_type:
- COM
ms.assetid: 0eef299d-6923-4dae-9a18-91ea82ea0f3e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 00c07069ed174fe55556dfe48398d65b4e64100e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359225"
---
# <a name="pidtagreceivedbyaddresstype-canonical-property"></a>PidTagReceivedByAddressType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含实际接收邮件的邮件用户的电子邮件地址类型 (如 SMTP)。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECEIVED_BY_ADDRTYPE、PR_RECEIVED_BY_ADDRTYPE_A、PR_RECEIVED_BY_ADDRTYPE_W  <br/> |
|标识符:  <br/> |0x0075  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>注解

这些属性是实际接收邮件的邮件用户的地址属性的示例。 它们必须由传入传输提供程序设置。
  
地址类型字符串只能包含大写字母字符 A 到 Z 以及从0到9的数字。 这些属性通过指定地址类型 (如 SMTP) 来限定**PR_RECEIVED_BY_EMAIL_ADDRESS** ([PidTagReceivedByEmailAddress](pidtagreceivedbyemailaddress-canonical-property.md)) 属性, 从而指示应如何构造地址。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定在电子邮件中允许的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

