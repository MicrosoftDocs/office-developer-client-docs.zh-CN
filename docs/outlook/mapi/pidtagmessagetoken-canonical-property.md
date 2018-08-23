---
title: PidTagMessageToken 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageToken
api_type:
- HeaderDef
ms.assetid: fcb93346-db92-44b5-a447-59fd95f98f45
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6b5def94096f7664169935a062d3b28171fb2919
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578428"
---
# <a name="pidtagmessagetoken-canonical-property"></a>PidTagMessageToken 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含邮件 ASN.1 安全令牌。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_TOKEN  <br/> |
|标识符：  <br/> |0x0C03  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |安全邮件属性  <br/> |
   
## <a name="remarks"></a>注解

此属性传达受保护与安全相关信息从其原始发件人向其收件人。 与**PR_MESSAGE_SECURITY_LABEL** ([PidTagMessageSecurityLabel](pidtagmessagesecuritylabel-canonical-property.md)) 属性一起使用，则保证与邮件内容的标签的关联。 在与**PR_CONTENT_INTEGRITY_CHECK** ([PidTagContentIntegrityCheck](pidtagcontentintegritycheck-canonical-property.md)) 属性一起使用，它验证的消息内容未更改。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

