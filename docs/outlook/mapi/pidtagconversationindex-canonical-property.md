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
ms.openlocfilehash: c6fa0d8f1323e8562a78080f50dbf448b8019ec2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334718"
---
# <a name="pidtagconversationindex-canonical-property"></a>PidTagConversationIndex 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指示此消息在对话线程中的相对位置的二进制值。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONVERSATION_INDEX  <br/> |
|标识符:  <br/> |0x0071  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

对话线程表示一系列消息和回复。 通常使用连接时间戳值实现此属性。 即使设置了[PidTagConversationTopic PR_CONVERSATION_TOPIC (PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)) 也是可选的。  
  
MAPI 提供 [ScCreateConversationIndex](sccreateconversationindex.md) 函数来创建或更新对话索引。 该函数将当前索引值作为计数型字节数组，并返回最后连接有时间戳的索引值。 表示对另一封邮件的答复的邮件应该使用 **ScCreateConversationIndex** 更新此属性。 
  
邮件存储提供程序可以选择确保始终PR_CONVERSATION_INDEX传入或传出邮件上设置邮件。 它可以通过调用 **ScCreateConversationIndex** 来实现此操作，如果此属性已设置，则使用现有值;如果未设置，则使用 NULL。 应在调用 [IMAPIProp：：SaveChanges 之前](imapiprop-savechanges.md) 执行此操作。 
  
可以基于此属性对PR_CONVERSATION_TOPIC相同值的所有邮件进行排序，以显示邮件的层次结构关系。 
  
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

