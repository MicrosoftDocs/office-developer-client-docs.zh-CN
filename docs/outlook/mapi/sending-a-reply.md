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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339779"
---
# <a name="sending-a-reply"></a>发送答复

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序通常支持两种类型的答复: 一个只发送给原始邮件的发件人, 另一个发送给原始邮件的收件人列表中包含的其他所有收件人以及发件人。 第二种类型的回复通常称为 "答复所有邮件"。
  
若要发送这两种类型的答复, 您需要执行一些与发送原始邮件时相同的任务。 例如, 打开默认邮件存储和 "传出邮件" 文件夹 (通常为 "发件箱"), 并调用传出文件夹的[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法来创建答复。 此外, 还可以打开保存原始邮件的文件夹 (通常为 "收件箱")。 有关打开不同文件夹的信息, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
  
创建答复和创建原始邮件的主要区别在于, 使用答复时, 大部分属性是基于原始邮件的属性, 还是直接从原始邮件的属性复制。 附件—特别排除的是邮件的**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 答复全部邮件的收件人列表是从原始邮件的列表中创建的, 收件人由**PR_RECEIVED_BY_SEARCH_KEY** ([PidTagReceivedBySearchKey](pidtagreceivedbysearchkey-canonical-property.md)) 属性和删除的所有密件抄送收件人。 **PR_RECEIVED_BY_SEARCH_KEY**属性表示当前用户。 
  
### <a name="to-send-a-reply"></a>发送答复
  
1. 打开默认邮件存储。 有关详细信息, 请参阅[打开默认邮件存储](opening-the-default-message-store.md)。
    
2. 打开 "发件箱" 文件夹。 有关详细信息, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用发件箱的[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法以创建答复。 
    
4. 调用原始邮件的[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将以下属性复制到答复邮件: 
    
   - **PR\_主体**([PidTagBody](pidtagbody-canonical-property.md)) 或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)), 具体取决于是否支持 rtf 格式。
    
   - **PR\_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) (如果答复将转到整个收件人列表)。
    
   - **PR\_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))。
    
5. 请勿在调用**IMAPIProp:: CopyTo**中包含以下属性:
    
    |||
    |:-----|:-----|
    |**PR\_客户\_端\_提交时间** <br/> |**PR\_邮件\_传递\_时间** <br/> |
    |**PR\_邮件\_下载\_时间** <br/> |**PR\_邮件\_标志** <br/> |
    |**PR\_发起\_人\_传递 REPORT\REQUESTED** <br/> |**PR\_RCVD\_表示**属性  <br/> |
    |**PR\_阅读\_回执\_条目 ID** <br/> |**请求\_PR\_已\_读回执** <br/> |
    |**通过\_属性\_接收的 PR**  <br/> |**"\_PR\_答复收件人**" 属性  <br/> |
    |**PR\_报告\_条目 ID** <br/> |**PR\_发件人**属性  <br/> |
    |**PR\_发送\_表示**属性  <br/> |**PR\_SENTMAIL\_ENTRYID** <br/> |
    |**PR\_主题\_前缀** <br/> | <br/> |
   
6. 向您支持的任何邮件正文属性添加分隔符文本, 即**PR_BODY**、 **PR_HTM**L 或**PR_RTF_COMPRESSED**。
    
7. 调用[ScCreateConversationIndex](sccreateconversationindex.md), 并传入原始邮件的**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性的值。
    
8. 为答复设置前缀。 如果您使用的是标准的 "RE:", 请将这些字符连接到**PR_NORMALIZED_SUBJECT**的开头, 并将**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 设置为此新字符串。 请勿设置**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))。 如果您使用非标准前缀 (例如字符串超过三个字符的字符串), 则将其存储在**PR_SUBJECT_PREFIX**中。 
    
9. 将**PR_SENT_REPRESENTING**属性设置为**PR_RCVD_REPRESENTING**属性中对应的值。 
    
10. 将 " **PR\_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md))" 和 " **\_PR_REPLY RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))" 中的每个条目设置为 "条目标识符" 和 "显示名称"主要收件人—类型为 "MAPI_TO" 的收件人。 保持这些属性同步。 也就是说, **PR_REPLY_RECIPIENT\_** entry 和**PR_REPLY_RECIPIENT_NAMES**必须包含相同的条目数, 并且其中一个属性中的特定位置的条目必须与其他项目中的同一位置的条目相对应财产. 
    
11. 如果答复仅发送给原始邮件的发件人, 请使用原始邮件的**PR_SENT_REPRESENTING**属性的收件人创建单个条目收件人列表。 有关创建收件人列表的详细信息, 请参阅[创建收件人列表](creating-a-recipient-list.md)。
    
12. 如果答复是 "全部答复", 请按如下所示创建收件人列表:
    
    1. 调用原始邮件的[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法以访问其收件人表。 
        
    2. 调用[HrQueryAllRows](hrqueryallrows.md)以检索表中的所有行。 确定每行是否表示主收件人或抄送收件人, 并且应保留在列表中, 或者如果它表示密件抄送收件人或用户, 应将其从列表中删除。 
        
    3. 通过查看**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 列来区分收件人类型。 对于主要收件人, MAPI_CC 将设置为 MAPI_TO, 对于抄送收件人, 此列将设置为 MAPI_BCC, 对于密件抄送收件人, 此列将设置为。 
        
    4. 将**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 列与原始邮件的**PR_RECEIVED_BY_SEARCH_KEY**属性进行比较, 以确定该行是否代表用户。 
        
    5. 通过调用[MAPIFreeBuffer](mapifreebuffer.md) , 从收件人列表中删除不需要的行, 以释放与收件人表的[SRowSet](srowset.md)结构中的相应条目相关联的内存。 将属性值数组中的所有值都设置为零, 将所有**cValues**成员设置为零, 并将**SRowSet**中的每个[SRow](srow.md)结构中的所有**lpProps**成员设置为 NULL。 
        
    6. 将发件人添加到收件人列表, 由原始邮件的**PR\_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)) 和**PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) 表示属性. 检查列表中的发件人是否不重复。
        
    7. 调用答复邮件的[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法, 将_ulFlags_参数设置为零, 以根据原始邮件中的列表创建答复邮件或转发邮件的新收件人列表。 
    
13. 调用答复的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存消息或[IMessage:: SubmitMessage](imessage-submitmessage.md)以保存并发送它。 
    
> [!NOTE]
> 在调用**IMessage:: ModifyRecipients**以将更改存储在收件人列表中之前, 您可以允许用户通过邮件窗体进行修改。 用户可以向列表中添加或删除特定成员。 允许用户对收件人列表进行更改是可选的客户端功能。 
  

