---
title: 跟踪对话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
api_type:
- COM
ms.assetid: 0500dee8-a39d-45ce-87b1-c515e92e083d
description: 上次修改时间：2011 年 7 月 23 日
localization_priority: Priority
ms.openlocfilehash: 3a59a7a15b4647832634adc4757544876b8841b1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349544"
---
# <a name="tracking-conversations"></a>跟踪对话

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对话跟踪收集邮件响应。 客户应设置以下两个属性，以辅助跟踪对话：
  
- **PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))
    
    **PR_CONVERSATION_TOPIC** 是邮件的标准化主题，该主题没有前缀字符串。 将此属性设为邮件的 **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性值。 
    
- **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))
    
    **PR_CONVERSATION_INDEX** 指示邮件在特定对话中的位置。 客户有责任为每个传出邮件设置 **PR_CONVERSATION_INDEX**，无论它是新邮件、转发邮件还是回复邮件。 客户可以手动设置此属性或调用 MAPI 提供的实用程序函数 [ScCreateConversationIndex](sccreateconversationindex.md)。 
    
 **ScCreateConversationIndex** 将为任何传出邮件生成对话索引值。 **ScCreateConversationIndex** 将索引用作页眉构建基块，该基块长度为 22 字节，后跟 0 个或多个长度为 5 字节的子基块。 
  
页眉构建基块由 22 字节组成，分成三个部分：
  
- 一个保留字节。 其值为 1。
    
- 5 字节用于当前系统时间，该时间转换为 [FILETIME](filetime.md) 结构格式。 
    
- 16 个字节用于保留 [GUID](guid.md)，或全局唯一标识符。
    
每个子基块由 5 字节组成，分成以下部分：
  
- 1 位包含表示当前时间与页眉构建基块中存储的时间之间的差异的代码。 如果差异小于 0.02 秒且大于 2 年，则此位为 0，如果差异小于 1 秒且大于 56 年，则为 1。
    
- 31 位包含当前时间和页眉构建基块中的时间（以 **FILETIME** 单位表示）之间的差异。子基块的这个部分是通过两种战略之一生成，具体取决于第一位的值。 如果此位为 0，则 **ScCreateConversationIndex** 将丢弃高 15 位和低 18 位。 如果此位为 1，则函数将丢弃高 10 位和低 23 位。 
    
- 4 位包含调用 Win32 函数 [GetTickCount](https://msdn.microsoft.com/library/ms724408%28VS.85%29.aspx) 所生成的随机数字。
    
- 4 位包含取自随机数字的序列计数。
    
如果选择手动设置邮件索引，请考虑以下建议：
  
1. 保持回复者的时区差异透明；使用 UTC 时间而不是本地时间。
    
2. 将每个对话组缩进相同的量。
    
3. 对属于相同邮件日期的回复进行排序。
    
4. 将共用相同主题且从不同时间开始的线程分开。 
    
5. 若要通过按类别排序以便按主题对邮件进行分许，请依次按 **PR_CONVERSATION_TOPIC** 和 **PR_CONVERSATION_INDEX** 进行排序。 若要展现排序结果，请将对话索引长度为 22 字节的邮件的 **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性设为 0。 若要实现每次 5 字节的长度增量，请将 **PR_DEPTH** 属性的值增加 1。 
    
PR_ORIGINAL 属性组也可用于对话跟踪。 设置这些属性可将回复邮件或转发邮件链接至原始邮件。 所有 PR_ORIGINAL 属性均为可选项。 例如，如未显式设置 **PR_ORIGINAL_AUTHOR_ENTRYID** ([PidTagOriginalAuthorEntryId](pidtagoriginalauthorentryid-canonical-property.md))，则邮件存储提供程序可使用默认值，或 **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 属性的值。 同样，如未设置 **PR_ORIGINAL_AUTHOR_NAME** 或 **PR_ORIGINAL_SUBMIT_TIME** ([PidTagOriginalSubmitTime](pidtagoriginalsubmittime-canonical-property.md))，则这些可默认分别采用 **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和 **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性的值。 
  

