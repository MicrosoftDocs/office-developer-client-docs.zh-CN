---
title: 发送答复
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 90dafeae-6b61-40e3-8341-d6a11799d0f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f47741369b1091c0dd24358e063de8f4675000fa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437446"
---
# <a name="sending-a-reply"></a>发送答复

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序通常支持两种类型的答复：一种仅发送给原始邮件的发件人，另一种发送给原始邮件的收件人列表中包括的所有其他收件人以及发件人。 此第二种类型的答复通常称为"全部答复"邮件。
  
若要发送任一类型的答复，您可以实现发送原始邮件时执行某些相同的任务。 例如，打开默认邮件存储和传出邮件文件夹（通常为发件箱）并调用传出文件夹的 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法创建回复。 此外，打开保存原始邮件的文件夹，通常为"收件箱"。 有关打开不同文件夹的信息，请参阅 [打开邮件存储文件夹](opening-a-message-store-folder.md)。
  
创建答复和创建原始邮件之间的主要区别在于，使用答复时，大多数属性要么基于原始邮件的属性，要么直接从原始邮件的属性中复制。 附件（邮件的 **PR_MESSAGE_ATTACHMENTS (** [PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性）被明确排除。 回复所有邮件的收件人列表都是从原始邮件的列表中创建的，收件人由 PR_RECEIVED_BY_SEARCH_KEY ([PidTagReceivedBySearchKey](pidtagreceivedbysearchkey-canonical-property.md) **)** 属性表示，并且已删除所有盲信副本收件人。 the **PR_RECEIVED_BY_SEARCH_KEY** property represents the current user. 
  
### <a name="to-send-a-reply"></a>发送答复
  
1. 打开默认邮件存储。 有关详细信息，请参阅 [打开默认邮件存储](opening-the-default-message-store.md)。
    
2. 打开发件箱文件夹。 有关详细信息，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用发件箱的 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法来创建回复。 
    
4. 调用原始邮件的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法将以下属性复制到回复邮件： 
    
   - **PR \_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) ，具体取决于你是否支持格式文本格式。
    
   - **PR \_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) ，如果答复将转到整个收件人列表。
    
   - **PR \_NORMALIZED_SUBJECT (** [PidTagNormalizedSubject) 。](pidtagnormalizedsubject-canonical-property.md)
    
5. 请勿在 **IMAPIProp：：CopyTo 调用中包括以下属性**：
    
    |||
    |:-----|:-----|
    |**PR \_ 客户端 \_ 提交 \_ 时间** <br/> |**PR \_ 邮件 \_ 传递 \_ 时间** <br/> |
    |**PR \_ 邮件 \_ 下载 \_ 时间** <br/> |**PR \_ 邮件 \_ 标志** <br/> |
    |**PR \_ ORIGINATOR \_ DELIVERY \_ REPORT\REQUESTED** <br/> |**PR \_RCVD \_ 表示** 属性  <br/> |
    |**PR \_ 已 \_ 读回 \_ 执 ENTRYID** <br/> |**请求的 PR \_ \_ \_ 已读回执** <br/> |
    |**PR \_RECEIVED \_ BY** 属性  <br/> |**PR \_REPLY \_ RECIPIENT** 属性  <br/> |
    |**PR \_ REPORT \_ ENTRYID** <br/> |**PR \_SENDER** 属性  <br/> |
    |**PR \_已 \_ 发送表示** 属性  <br/> |**PR \_ SENTMAIL \_ ENTRYID** <br/> |
    |**PR \_ 主题 \_ 前缀** <br/> | <br/> |
   
6. 将分隔符文本添加到您支持的任何邮件正文属性 — **PR_BODY** **、PR_HTM** L 或 **PR_RTF_COMPRESSED**。
    
7. 调用 [ScCreateConversationIndex](sccreateconversationindex.md)，将原始邮件的 **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 值。
    
8. 设置答复的前缀。 如果使用的是标准"RE："，请连接这些字符到 PR_NORMALIZED_SUBJECT 开头 **，PR_SUBJECT (**  [PidTagSubject](pidtagsubject-canonical-property.md)) 设置为此新字符串。 请勿将 PR_SUBJECT_PREFIX **(** [PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 。 如果使用非标准前缀（如长度超过三个字符的字符串），请存储在 **PR_SUBJECT_PREFIX。** 
    
9. 将 **PR_SENT_REPRESENTING** 属性设置为活动属性 **中的PR_RCVD_REPRESENTING值** 。 
    
10. 将 **PR \_ REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和 **PR_REPLY \_ RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) 中的每个条目设置为主要收件人（其类型为 MAPI_TO 的收件人）的条目标识符和 显示名称。 保持这些属性同步。 也就是说 **，PR_REPLY_RECIPIENT \_ 条目** 和 **PR_REPLY_RECIPIENT_NAMES** 必须包含相同数量的条目，并且其中一个属性中位于特定位置的条目必须对应于另一个属性中位于同一位置的条目。 
    
11. 如果答复仅发送给原始邮件的发件人，请创建一个条目收件人列表，该收件人由原始邮件的 **PR_SENT_REPRESENTING** 属性表示。 有关创建收件人列表的信息，请参阅 [创建收件人列表](creating-a-recipient-list.md)。
    
12. 如果答复全部答复，请创建收件人列表，如下所示：
    
    1. 调用原始邮件的 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 方法以访问其收件人表。 
        
    2. 调用 [HrQueryAllRows](hrqueryallrows.md) 以检索表中的所有行。 确定每一行是代表主要收件人还是抄稿收件人，并且应保留在列表中，或者是否代表"抄用副本"收件人或用户，并且应从列表中删除。 
        
    3. 通过查看[PidTagRecipientType](pidtagrecipienttype-canonical-property.md) PR_RECIPIENT_TYPE (列来区分) 类型。  此列将设置为MAPI_TO收件人、MAPI_CC的收件人和MAPI_BCC收件人的收件人。 
        
    4. 比较 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 列与原始邮件的 **PR_RECEIVED_BY_SEARCH_KEY** 属性以确定该行是否表示用户。 
        
    5. 通过调用 [MAPIFreeBuffer](mapifreebuffer.md) 释放与收件人表 [的 SRowSet](srowset.md) 结构中的相应条目关联的内存，从收件人列表中删除不需要的行。 将属性值数组中所有值设置为零，将 **所有 cValues** 成员设置为零，将 **SRowSet** 中每个 [SRow](srow.md)结构的所有 **lpProps** 成员设置为 NULL。 
        
    6. 将发件人添加到收件人列表中，如原始邮件的 **PR \_ SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)) 和 **PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) 属性表示。 检查发件人在列表中是否重复。
        
    7. 调用回复邮件 [的 IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法，将  _ulFlags_ 参数设置为零，以基于原始邮件中的列表为答复或转发的邮件创建新的收件人列表。 
    
13. 调用回复的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存消息，或调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 保存并发送邮件。 
    
> [!NOTE]
> 在调用 **IMessage：：ModifyRecipients** 以将更改存储在收件人列表中之前，您可以允许用户通过邮件窗体进行修改。 用户可以添加到列表或删除特定成员。 允许用户对收件人列表进行更改是一项可选的客户端功能。 
  

