---
title: 转发邮件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0027fd5a-f30a-4025-b670-c21869b3a480
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d1df84c37cc2a24806c35ae0c90e4bf2a5e438d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433176"
---
# <a name="forwarding-a-message"></a>转发邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
转发邮件涉及许多与发送原始邮件相同的任务。 首先，必须打开默认邮件存储和指定用于保留传出邮件的文件夹（通常为发件箱）并调用此文件夹的 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法以创建要转发的邮件。 还必须打开保存原始邮件的文件夹，通常为"收件箱"。 有关打开不同文件夹的信息，请参阅 [打开邮件存储文件夹](opening-a-message-store-folder.md)。
  
创建要转发的邮件和创建原始邮件之间的主要区别在于，对于转发的邮件，大多数属性都是基于原始邮件的属性或直接从原始邮件的属性复制的。 
  
**转发邮件**
  
1. 打开默认邮件存储。 有关详细信息，请参阅 [打开默认邮件存储](opening-the-default-message-store.md)。
    
2. 打开发件箱文件夹。 有关详细信息，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用发件箱的 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法以创建新的转发邮件。 
    
4. 调用原始邮件的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法将以下属性复制到转发的邮件： 
    
   - **PR \_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 、PR **\_ HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 或 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) ，具体取决于您是否支持格式文本格式、纯文本或 HTML。
    
   - **PR \_NORMALIZED_SUBJECT (** [PidTagNormalizedSubject)](pidtagnormalizedsubject-canonical-property.md) 
    
5. 通过调用原始邮件的 **IMAPIProp：：CopyTo** 方法来复制 **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性，或者调用要复制的每个附件的以下三个步骤过程，从原始邮件复制邮件附件：
    
   1. 调用新转发邮件的 [IMessage：：CreateAttach](imessage-createattach.md) 方法以创建新的附件。 
      
   2. 调用原始邮件的 [IMessage：：OpenAttach](imessage-openattach.md) 方法打开要复制的附件。 
      
   3. 调用原始邮件的 **IMAPIProp：：CopyTo** 方法，将旧附件的所有附件属性复制到新附件。 
    
6. 请勿在 **IMAPIProp：：CopyTo 调用中包括以下属性**： 
    
|||
|:-----|:-----|
|**PR_CLIENT_SUBMIT_TIME (** [PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))   <br/> |**PR_MESSAGE_DELIVERY_TIME (** [PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))   <br/> |
|**PR_MESSAGE_DOWNLOAD_TIME (** [PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))   <br/> |**PR_MESSAGE_FLAGS (** [PidTagMessageFlags](pidtagmessageflags-canonical-property.md))   <br/> |
|**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED (** [PidTagOriginatorDeliveryReportRequested)](pidtagoriginatordeliveryreportrequested-canonical-property.md)  <br/> |**PR_RCVD_REPRESENTING** 属性  <br/> |
|**PR_READ_RECEIPT_ENTRYID (** [PidTagReadReceiptEntryId)](pidtagreadreceiptentryid-canonical-property.md)  <br/> |**PR_READ_RECEIPT_REQUESTED (** [PidTagReadReceiptRequested)](pidtagreadreceiptrequested-canonical-property.md)  <br/> |
|**PR_RECEIVED_BY** 属性  <br/> |**PR_REPLY_RECIPIENT** 属性  <br/> |
|**PR_REPORT_ENTRYID (** [PidTagReportEntryId)](pidtagreportentryid-canonical-property.md)  <br/> |**PR_SENDER** 属性  <br/> |
|**PR_SENT_REPRESENTING** 属性  <br/> |**PR_SENTMAIL_ENTRYID (** [PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))   <br/> |
|**PR_SUBJECT_PREFIX (** [PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))   <br/> | <br/> |
   
1. 通过添加缩进和包含原始发件人、传输日期、主题和收件人列表的头段落来设置邮件文本的格式。 请勿在内容中包括 Internet 样式的前缀字符。
    
2. 调用 [ScCreateConversationIndex](sccreateconversationindex.md)，将原始邮件的 **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 值。
    
3. 为转发的邮件设置前缀。 如果使用标准"FW："，请连接这些字符到 PR_NORMALIZED_SUBJECT 开头 **，PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 此新字符串。  请勿将 PR_SUBJECT_PREFIX **(** [PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 。 如果使用非标准前缀（如长度超过三个字符的字符串），请存储在 **PR_SUBJECT_PREFIX。** 
    
4. 将 **PR_SENT_REPRESENTING** 属性设置为活动属性 **中的PR_RCVD_REPRESENTING值** 。 
    
5. 创建收件人列表。 有关详细信息，请参阅创建 [收件人列表](creating-a-recipient-list.md)。
    
6. 调用转发的邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存它，或者 [调用 IMessage：：SubmitMessage](imessage-submitmessage.md) 保存并发送它。 
    
## <a name="see-also"></a>另请参阅

- [PidTagMessageAttachments 规范属性](pidtagmessageattachments-canonical-property.md)

