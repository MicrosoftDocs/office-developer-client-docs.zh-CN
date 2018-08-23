---
title: 跟踪对话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0500dee8-a39d-45ce-87b1-c515e92e083d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ae8b5a474675c0afd771f4e8dfd060d0b379c8f4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572219"
---
# <a name="tracking-conversations"></a>跟踪对话

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
对话跟踪正在收集 エ ・ 复 ハ 一条消息。 客户端应在跟踪对话设置帮助的两个属性：
  
- **PR_CONVERSATION_TOPIC**([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))
    
    **PR_CONVERSATION_TOPIC**是规范化的邮件的主题，没有前缀字符串主题。 将此属性设置为消息的**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性的值。 
    
- **PR_CONVERSATION_INDEX**([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))
    
    **PR_CONVERSATION_INDEX**指示特定的对话中的邮件的位置。 新的邮件、 转发的邮件或回复是否是客户端的 reponsibility **PR_CONVERSATION_INDEX**设置为每个传出消息。 客户端可以手动设置此属性，或者调用[ScCreateConversationIndex](sccreateconversationindex.md)，MAPI 提供的实用工具函数。 
    
 **ScCreateConversationIndex**生成任何传出消息的对话索引的值。 **ScCreateConversationIndex**实现索引作为标头块的 22 字节的长度后, 跟零个或更多的子阻止在长度每 5 个字节。 
  
标头块组成 22 字节，分为三个部分：
  
- 一个保留的字节。 其值为 1。
    
- 五个字节用于当前系统时间转换为[FILETIME](filetime.md)结构格式。 
    
- 16 个字节保留的[GUID](guid.md)或全局唯一标识符。
    
每个子块组成 5 个字节，划分，如下所示：
  
- 包含表示当前时间和存储在标头块的时间之间的差异的代码的一位。 如果差不超过.02 第二个和大于两年和 1 如果差小于一秒 56 年以上，则此位将为 0。
    
- 包含以**FILETIME**单位表示的标头块中的当前时间与完成时间之间的区别三十一位。子块的这一部分将生成使用两种策略，具体取决于第一位的值之一。 如果此位为零， **ScCreateConversationIndex**放弃高 15 位和低 18 位。 如果此位是一个，该函数将丢弃高 10 位和低 23 位。 
    
- 包含通过调用 Win32 函数[GetTickCount](http://msdn.microsoft.com/en-us/library/ms724408%28VS.85%29.aspx)生成一个随机数字的四位。
    
- 包含一系列的四位计数的取自随机数字的一部分。
    
如果您选择手动设置消息的对话索引，请考虑以下建议：
  
1. 保留透明; 响应者时区的差异使用 UTC 时间，而不是本地时间。
    
2. 通过了相同时间缩进每个对话组。
    
3. 排序 エ ・ 复 ハ 相同的消息日期。
    
4. 在发生共享相同的主题的不同时间开始的单独的线程。 
    
5. 若要实现分类的排序，以便按主题分组消息，排序按**PR_CONVERSATION_TOPIC**第一个，然后按**PR_CONVERSATION_INDEX**。 显示排序的结果，设置为 0 邮件是在长度 22 字节的对话索引**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性。 然后，在长度每 5 字节增量，增加**PR_DEPTH**属性的值 1。 
    
PR_ORIGINAL 组属性还可用于跟踪的对话。 设置这些属性以链接到原始邮件的答复或转发的邮件。 所有 PR_ORIGINAL 属性是可选的。 如果您未显式设置，例如， **PR_ORIGINAL_AUTHOR_ENTRYID** ([PidTagOriginalAuthorEntryId](pidtagoriginalauthorentryid-canonical-property.md)) 的消息存储提供程序可以使用默认值或**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 的值属性。 同样，如果未设置**PR_ORIGINAL_AUTHOR_NAME**或**PR_ORIGINAL_SUBMIT_TIME** ([PidTagOriginalSubmitTime](pidtagoriginalsubmittime-canonical-property.md))，这些属性可以使用默认**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和**PR_ 的值CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性，分别。 
  

