---
title: PidTagOriginatorRequestedAlternateRecipient 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatorRequestedAlternateRecipient
api_type:
- COM
ms.assetid: c85b7862-18bc-4e17-94db-9097e0ac4a02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c7abd0ae93c5b38c756ec0915dda6a4cdfcebaa5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777993"
---
# <a name="pidtagoriginatorrequestedalternaterecipient-canonical-property"></a>PidTagOriginatorRequestedAlternateRecipient 规范属性

  
  
**适用于**： Outlook 
  
包含的发件人指定一个备用收件人的项标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINATOR_REQUESTED_ALTERNATE_RECIPIENT  <br/> |
|标识符：  <br/> |0x0C09  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MIME  <br/> |
   
## <a name="remarks"></a>说明

自动转发邮件中使用此属性。 如果不允许自动转接，或者如果已不指定任何备用收件人，应生成原件报告。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

