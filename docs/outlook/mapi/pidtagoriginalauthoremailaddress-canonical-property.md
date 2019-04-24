---
title: PidTagOriginalAuthorEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorEmailAddress
api_type:
- COM
ms.assetid: 67cda756-ba71-4f29-a601-55359e44d93b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7918c5d5b585ffb199bfbc140edfb8286b499b40
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329237"
---
# <a name="pidtagoriginalauthoremailaddress-canonical-property"></a>PidTagOriginalAuthorEmailAddress 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件第一版的作者的电子邮件地址, 即邮件转发或答复前的邮件地址。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS、PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_A、PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_W  <br/> |
|标识符:  <br/> |0x007A  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |服务器  <br/> |
   
## <a name="remarks"></a>注解

这些属性是邮件作者地址属性的示例。 首次提交邮件时, 客户端应用程序应将这些属性设置为**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) 属性的值。 转发或答复邮件时, 它永远不会更改。
  
原始作者属性允许保留本地邮件域外部的信息。 当邮件到达其他邮件域 (例如从 Internet) 时, 这些属性提供了一种确保原始信息不会丢失的方法。
  
## <a name="related-resources"></a>相关资源

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

