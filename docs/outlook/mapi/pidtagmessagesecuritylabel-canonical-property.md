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
ms.openlocfilehash: a6caa322e1d266be1fe56aecd89736e757067758
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594367"
---
# <a name="pidtagmessagesecuritylabel-canonical-property"></a>PidTagMessageSecurityLabel 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含邮件安全标签。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_SECURITY_LABEL  <br/> |
|标识符：  <br/> |0x001E  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Server  <br/> |
   
## <a name="remarks"></a>注解

此属性提供在其**PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) 属性保护邮件的基础。 由令牌保证其与邮件内容的关联。
  
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

