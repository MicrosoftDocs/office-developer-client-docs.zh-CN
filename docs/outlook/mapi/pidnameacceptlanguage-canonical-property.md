---
title: PidNameAcceptLanguage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameAcceptLanguage
api_type:
- COM
ms.assetid: 4b202bc1-f718-446a-950f-634ffee47baf
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d2c2fb31b722e76034b08077632c817d6adde802
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777170"
---
# <a name="pidnameacceptlanguage-canonical-property"></a>PidNameAcceptLanguage 规范属性

  
  
**适用于**： Outlook 
  
包含 [RFC3282] 接受语言标头字段值。
  
|||
|:-----|:-----|
|友好名称：  <br/> |AcceptLanguage  <br/> |
|属性进行设置：  <br/> |PS_INTERNET_HEADERS  <br/> |
|属性名称：  <br/> |接受语言  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Email  <br/> |
   
## <a name="remarks"></a>备注

若要设置此属性的值，多用途 Internet 邮件扩展 (MIME) 客户端应编写将接受语言标头字段与所需的值。 MIME 客户端可能会改为编写 X 接受语言标头字段。 MIME 读者应将任一标头字段的值复制到此属性的值。 如果存在两个标头字段时，MIME 读者应使用接受语言标头字段。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

