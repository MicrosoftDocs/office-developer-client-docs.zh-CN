---
title: PidTagConversationIndex 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagConversationIndex
api_type:
- HeaderDef
ms.assetid: c65cdda7-9515-4da9-be75-43ebf45a02df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 77fee834108a603c1cd10e8e47776cc34fd75a2b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584162"
---
# <a name="pidtagconversationindex-canonical-property"></a>PidTagConversationIndex 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个二进制值，指示此消息在对话线程中的相对位置。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONVERSATION_INDEX  <br/> |
|标识符：  <br/> |0x0071  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

会话线索表示一系列邮件和答复。 此属性通常使用连接的时间戳值来实现。 即使设置**PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))，其用途是可选的。 
  
MAPI 提供了用于创建或更新的对话索引的[ScCreateConversationIndex](sccreateconversationindex.md)函数。 该函数将作为计数的字节数组的当前索引值，并返回具有在结尾处连接时间戳的索引值。 表示对其他邮件的答复邮件应使用**ScCreateConversationIndex**更新此属性。 
  
消息存储提供程序具有**PR_CONVERSATION_INDEX**始终对传入或传出邮件设置的选项的保证。 它可以通过调用**ScCreateConversationIndex**，如果此属性设置的现有值或空如果不是执行此操作。 调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)之前，应执行此操作。 
  
可以在此属性以显示邮件的分层关系排序**PR_CONVERSATION_TOPIC**具有相同的值的所有邮件。 
  
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

