---
title: PidTagConversationTopic 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagConversationTopic
api_type:
- HeaderDef
ms.assetid: db852b99-ce04-49bf-a714-7549571502e2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dfd437fac3a784212807c495f6e8f1adbe759cb0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334683"
---
# <a name="pidtagconversationtopic-canonical-property"></a>PidTagConversationTopic 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对话线程中第一封邮件的主题。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONVERSATION_TOPIC、PR_CONVERSATION_TOPIC_A、PR_CONVERSATION_TOPIC_W  <br/> |
|标识符:  <br/> |0x0070  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

对话线程表示一系列消息和回复。 这些属性设置为线程中第一条消息，通常设置为[PidTagNormalizedSubject PR_NORMALIZED_SUBJECT (PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性。  线程中的后续消息应使用相同的主题，无需进行修改。 
  
The **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) property indicates the order relationship between subsequent messages and replies. 它的使用是可选的，即使这些属性已设置。 
  
邮件存储提供程序可以选择确保始终对传入或传出邮件设置这些属性。 如果这些属性已经设置，则不应更改它们。 如果没有，可以设置为 **"PR_NORMALIZED_SUBJECT"。** 在调用 [IMAPIProp：：SaveChanges 之前，应执行任何](imapiprop-savechanges.md) 操作。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许对电子邮件对象执行的属性和操作。
    
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

