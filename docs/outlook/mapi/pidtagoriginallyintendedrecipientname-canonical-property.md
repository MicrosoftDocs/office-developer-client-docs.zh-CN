---
title: PidTagOriginallyIntendedRecipientName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginallyIntendedRecipientName
api_type:
- COM
ms.assetid: 56c406fb-8778-4f85-bbdc-4cabfa140248
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8637ef8036ccec79b82bcfff4a9f6d21fd5c2e11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419840"
---
# <a name="pidtagoriginallyintendedrecipientname-canonical-property"></a>PidTagOriginallyIntendedRecipientName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含自动前向邮件最初预期收件人的编码名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINALLY_INTENDED_RECIPIENT_NAME  <br/> |
|标识符:  <br/> |0x0020  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |服务器  <br/> |
   
## <a name="remarks"></a>备注

the **PR_ORIGINALLY_INTENDED_RECIPIENT_NAME** property must be set by the automatic agent that has forwarded the message. 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

