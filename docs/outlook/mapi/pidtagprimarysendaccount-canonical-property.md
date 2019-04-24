---
title: PidTagPrimarySendAccount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPrimarySendAccount
api_type:
- COM
ms.assetid: 2f268b3b-2e4c-4aea-8879-bdd0ac1df35c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2c32cc61fea63cd38215c30e04e8a467d4901cc9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339373"
---
# <a name="pidtagprimarysendaccount-canonical-property"></a>PidTagPrimarySendAccount 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含命名用于发送邮件的第一台服务器的字符串。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PRIMARY_SEND_ACCOUNT  <br/> |
|标识符:  <br/> |0x0E28  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |帐户  <br/> |
   
## <a name="remarks"></a>注解

指定客户端用于发送邮件的第一台服务器。 这些属性的格式是依赖于实现的。 客户端可以使用这些属性来确定要将邮件定向到哪个服务器, 但这是可选的, 并且值对服务器没有任何意义。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

