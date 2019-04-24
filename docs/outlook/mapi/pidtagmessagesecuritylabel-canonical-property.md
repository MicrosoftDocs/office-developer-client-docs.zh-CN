---
title: PidTagMessageSecurityLabel 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageSecurityLabel
api_type:
- HeaderDef
ms.assetid: aae41f1b-19bb-40c7-8564-0c87a5a4e47c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b6900cbacc2bea6c5519efdc4281ca98629b23bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355676"
---
# <a name="pidtagmessagesecuritylabel-canonical-property"></a>PidTagMessageSecurityLabel 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件的安全标签。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_SECURITY_LABEL  <br/> |
|标识符:  <br/> |0x001E  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |服务器  <br/> |
   
## <a name="remarks"></a>注解

此属性提供**PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) 属性保护邮件的基础。 令牌会保证它与邮件内容的关联。
  
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

