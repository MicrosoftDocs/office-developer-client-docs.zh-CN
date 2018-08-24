---
title: 发送答复 （英文）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 90dafeae-6b61-40e3-8341-d6a11799d0f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4d8c995f5fbca322fca44cdcbb0de224af6b2fbf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590286"
---
# <a name="sending-a-reply"></a>发送答复 （英文）

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序通常支持两种类型的答复： 一个仅发送给原始邮件和一个发送给所有发件人除了原始邮件的收件人列表中包含其他收件人的发件人。 通常，此第二个类型的答复称为所有邮件的答复。
  
若要发送的答复任一类型，您实现一些即可发送原始邮件时的相同任务。 例如，您打开默认的邮件存储和传出邮件文件夹，通常是发件箱，并调用传出文件夹的[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法创建答复。 此外，您打开保留原始邮件，通常收件箱文件夹。 有关打开不同的文件夹的信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
  
创建答复并创建原始邮件的主要区别是，使用答复大部分属性是基于或复制直接从原始邮件的属性。 附件 — 一条消息**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性 — 明确排除。 所有邮件从原始消息的列表都创建由**PR_RECEIVED_BY_SEARCH_KEY** ([PidTagReceivedBySearchKey](pidtagreceivedbysearchkey-canonical-property.md)) 属性收件人和删除所有密件抄送副本收件人的答复收件人列表。 **PR_RECEIVED_BY_SEARCH_KEY**属性表示当前用户。 
  
### <a name="to-send-a-reply"></a>发送答复
  
1. 打开默认邮件存储区。 有关详细信息，请参阅[打开默认邮件存储区](opening-the-default-message-store.md)。
    
2. 打开发件箱文件夹。 有关详细信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用发件箱的[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法创建答复。 
    
4. 调用原始消息的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法，将以下属性复制到答复消息： 
    
   - **PR\_正文**([PidTagBody](pidtagbody-canonical-property.md)) 或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))，具体取决于是否支持富文本格式。
    
   - **PR\_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))，如果答复将转到整个收件人列表。
    
   - **PR\_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))。
    
5. **IMAPIProp::CopyTo**到呼叫中不包括以下属性：
    
    |||
    |:-----|:-----|
    |**PR\_客户端\_提交\_时间** <br/> |**PR\_消息\_传递\_时间** <br/> |
    |**PR\_消息\_下载\_时间** <br/> |**PR\_消息\_标志** <br/> |
    |**PR\_原始发件人\_传递\_REPORT\REQUESTED** <br/> |**PR\_接收的\_REPRESENTING**属性  <br/> |
    |**PR\_读取\_回执\_ENTRYID** <br/> |**PR\_读取\_回执\_申请** <br/> |
    |**PR\_RECEIVED\_BY**属性  <br/> |**PR\_答复\_收件人**属性  <br/> |
    |**PR\_报告\_ENTRYID** <br/> |**PR\_发件人**属性  <br/> |
    |**PR\_发送\_REPRESENTING**属性  <br/> |**PR\_SENTMAIL\_ENTRYID** <br/> |
    |**PR\_主题\_前缀** <br/> | <br/> |
   
6. 将分隔符文本添加到您支持无论消息正文属性 — **PR_BODY**、 **PR_HTM**L、 或**PR_RTF_COMPRESSED**。
    
7. 调用[ScCreateConversationIndex](sccreateconversationindex.md)，传递中原始消息的**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性的值。
    
8. 设置回复前缀。 如果您使用的是标准"RE:"连接到的**PR_NORMALIZED_SUBJECT**开头这些字符和将**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 设置为此新字符串。 未设置**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))。 如果您使用非标准前缀，例如 string 超过三个字符，则将其存储在**PR_SUBJECT_PREFIX**。 
    
9. 设置为**PR_RCVD_REPRESENTING**属性中的相应值的**PR_SENT_REPRESENTING**属性。 
    
10. 设置中的条目的每个**PR\_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和**PR_REPLY\_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) 的项标识符和显示名称主收件人 — 其类型是 MAPI_TO 收件人。 保持同步这些属性。 即**PR_REPLY_RECIPIENT\_条目**和**PR_REPLY_RECIPIENT_NAMES**必须包含相同数量的条目，条目中的属性之一的特定位置必须对应的条目中其他的相同位置属性。 
    
11. 如果仅对原始邮件的发件人发送答复，与原始消息的**PR_SENT_REPRESENTING**属性表示收件人创建单输入收件人列表。 有关创建收件人列表的详细信息，请参阅[创建收件人列表](creating-a-recipient-list.md)。
    
12. 如果答复，所有答复创建收件人列表，如下所示：
    
    1. 调用原始消息的[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法，以访问其收件人的表。 
        
    2. 调用[HrQueryAllRows](hrqueryallrows.md)检索所有表中的行。 确定每个行表示主索引器还是抄送收件人，并应保持在列表中还是如果它表示密件抄送副本收件人或用户，并应从列表中删除。 
        
    3. 区分通过查看**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 列的收件人类型。 此列将设置为 MAPI_TO 主收件人、 MAPI_CC 抄送副本收件人和 MAPI_BCC 的密件抄送副本收件人。 
        
    4. 将原始邮件以确定该行是否代表用户的**PR_RECEIVED_BY_SEARCH_KEY**属性的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 列进行比较。 
        
    5. 通过调用[MAPIFreeBuffer](mapifreebuffer.md)以释放与收件人表[SRowSet](srowset.md)结构中的相应条目关联的内存，从收件人列表中删除不必要的行。 将所有为零，所有**cValues**成员为零，属性值数组中的值和**SRowSet**中每个[SRow](srow.md)结构中的**lpProps**成员的所有设置为 NULL。 
        
    6. 将发件人添加到的收件人列表中，由原始消息的**PR\_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)) 和**PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))属性。 检查发件人不会重复列表中。
        
    7. 呼叫答复邮件[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法，将_ulFlags_参数设置为零，创建新的收件人列表的答复或转发的基于从原始邮件列表的邮件。 
    
13. 呼叫答复[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法保存[IMessage::SubmitMessage](imessage-submitmessage.md)保存，并将其发送的消息。 
    
> [!NOTE]
> 调用之前**IMessage::ModifyRecipients**存储的收件人列表中的更改，您可以允许用户通过邮件窗体的修改。 用户可以向列表中添加或删除特定的成员。 允许用户对收件人列表进行更改是一个可选的客户端功能。 
  

