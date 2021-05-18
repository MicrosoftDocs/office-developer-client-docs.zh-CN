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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d909a121bdc528a04d0f400555a6f98f29da8f0c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406050"
---
# <a name="pidtagrelatedmessageids-canonical-property"></a>PidTagRelatedMessageIds 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含与邮件相关的邮件的标识符列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RELATED_IPMS  <br/> |
|标识符:  <br/> |0x002D  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

标识符使用与用于[PidTagSearchKey](pidtagsearchkey-canonical-property.md)属性PR_SEARCH_KEY (相同) 规则。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

