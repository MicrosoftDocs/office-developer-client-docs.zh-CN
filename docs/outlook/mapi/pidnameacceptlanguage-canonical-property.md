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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 855610c43cfaa64fa69e6987743b137b188d84a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360940"
---
# <a name="pidnameacceptlanguage-canonical-property"></a>PidNameAcceptLanguage 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 [RFC3282] 接受语言标头字段值。
  
|||
|:-----|:-----|
|友好名称:  <br/> |AcceptLanguage  <br/> |
|属性集:  <br/> |PS_INTERNET_HEADERS  <br/> |
|属性名称:  <br/> |Accept-Language  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

若要设置此属性的值, 多用途 Internet 邮件扩展 (MIME) 客户端应使用所需的值来编写接受语言标头字段。 MIME 客户端可以改为写入 X-接受语言的标头字段。 MIME 阅读器应将任一头字段的值复制到该属性的值。 如果同时存在这两个标头字段, 则 MIME 阅读器应使用 Accept a Language 标头字段。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

