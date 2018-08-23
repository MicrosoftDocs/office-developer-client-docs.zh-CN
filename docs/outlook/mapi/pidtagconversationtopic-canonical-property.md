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
ms.openlocfilehash: ce9d13b6ecd560798cee4f79d8d62b966dc427f1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586471"
---
# <a name="pidtagconversationtopic-canonical-property"></a>PidTagConversationTopic 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含会话线索中的第一个邮件的主题。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONVERSATION_TOPIC，PR_CONVERSATION_TOPIC_A，PR_CONVERSATION_TOPIC_W  <br/> |
|标识符：  <br/> |0x0070  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

会话线索表示一系列邮件和答复。 设置这些属性是线程，通常为**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性中的第一条消息。 后续的消息的线程中应使用同一主题不做任何修改。 
  
**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性指示后续的消息和回复的顺序关系。 即使设置这些属性，其用途是可选的。 
  
消息存储提供程序具有这些属性始终对传入或传出邮件设置的选项的保证。 如果已设置这些属性应不会更改它们。 如果没有，它们可以设置为**PR_NORMALIZED_SUBJECT**。 调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)之前，应执行任何操作。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
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

