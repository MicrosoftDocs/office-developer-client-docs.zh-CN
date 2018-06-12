---
title: PidTagRelatedMessageIds 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRelatedMessageIds
api_type:
- COM
ms.assetid: 51f0eb8a-0a16-4b45-9380-28caddecf955
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 1a865b571de9e471bcc1942ab54b02f658b4c158
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778184"
---
# <a name="pidtagrelatedmessageids-canonical-property"></a>PidTagRelatedMessageIds 规范属性

  
  
**适用于**： Outlook 
  
包含与邮件相关的消息的标识符的列表。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RELATED_IPMS  <br/> |
|标识符:  <br/> |0x002D  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

标识符使用相同的特定构造规则，如用于**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

