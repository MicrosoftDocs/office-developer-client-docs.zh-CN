---
title: PidNameCrossReference 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameCrossReference
api_type:
- COM
ms.assetid: d16e1adf-c911-427e-9c98-678a303e6791
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5daf8c1ee249cfc7fb1bc1ffb6dfc68b400fe953
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571127"
---
# <a name="pidnamecrossreference-canonical-property"></a>PidNameCrossReference 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含 [RFC3282] Xref 标头字段值。
  
|||
|:-----|:-----|
|友好名称：  <br/> |无  <br/> |
|属性进行设置：  <br/> |PS_INTERNET_HEADERS  <br/> |
|属性名称：  <br/> |Xref  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

若要设置此属性的值，多用途 Internet 邮件扩展 (MIME) 客户端必须所需的值都写入到 XRef 标头字段中。 MIME 读者必须将 XRef 标头字段的值复制到此属性的值。
  
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
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

