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
ms.openlocfilehash: 146c8b4d711982118fd9da185a5b095a1bae6b2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774982"
---
# <a name="forwarding-a-message"></a>转发邮件

**适用于**： Outlook 
  
转发邮件涉及多个与发送原始邮件相同的任务。 首先，必须打开默认的邮件存储和指定用于保存传出消息，通常箱文件夹，并调用此文件夹[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法来创建邮件转发。 您还必须打开包含原始邮件，通常收件箱文件夹。 有关打开不同的文件夹的信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
  
创建要转接的消息和创建原始的主要区别是，转发邮件、 大部分属性是基于或复制直接从原始邮件的属性。 
  
**转发邮件**
  
1. 打开默认邮件存储区。 有关详细信息，请参阅[打开默认邮件存储区](opening-the-default-message-store.md)。
    
2. 打开发件箱文件夹。 有关详细信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用发件箱的[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法，以创建新的转发的邮件。 
    
4. 调用原始消息的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法复制到转发邮件的以下属性： 
    
   - **PR\_正文**([PidTagBody](pidtagbody-canonical-property.md))， **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))，具体取决于您是否支持富文本格式、 纯文本或 HTML。
    
   - **PR\_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 
    
5. 通过调用原始消息的**IMAPIProp::CopyTo**方法复制的**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性或通过调用下列从原始邮件复制邮件附件每个附件要复制的三个步骤过程：
    
   1. 调用新的转发邮件的[IMessage::CreateAttach](imessage-createattach.md)方法创建一个新附件。 
      
   2. 调用原始消息的[IMessage::OpenAttach](imessage-openattach.md)方法以打开要复制的附件。 
      
   3. 调用原始消息的**IMAPIProp::CopyTo**方法复制的所有附件属性到新的旧附件。 
    
6. **IMAPIProp::CopyTo**到呼叫中不包括以下属性： 
    
|||
|:-----|:-----|
|**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))  <br/> |**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |
|**PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))  <br/> |**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |
|**邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))  <br/> |**PR_RCVD_REPRESENTING**属性  <br/> |
|**PR_READ_RECEIPT_ENTRYID**([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md))  <br/> |**PR_READ_RECEIPT_REQUESTED**([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))  <br/> |
|**PR_RECEIVED_BY**属性  <br/> |**PR_REPLY_RECIPIENT**属性  <br/> |
|**PR_REPORT_ENTRYID**([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))  <br/> |**PR_SENDER**属性  <br/> |
|**PR_SENT_REPRESENTING**属性  <br/> |**PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))  <br/> |
|**PR_SUBJECT_PREFIX**([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))  <br/> | <br/> |
   
1. 通过添加缩进和包含原始发件人，标头段落格式的消息文本的传输、 主题和收件人列表的日期。 不包含内容的 Internet 风格前缀字符。
    
2. 调用[ScCreateConversationIndex](sccreateconversationindex.md)，传递中原始消息的**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性的值。
    
3. 设置转发邮件的前缀。 如果您使用的是标准"FW:"连接到的**PR_NORMALIZED_SUBJECT**开头这些字符和将**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 设置为此新字符串。 未设置**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))。 如果您使用非标准前缀，例如 string 超过三个字符，则将其存储在**PR_SUBJECT_PREFIX**。 
    
4. 设置为**PR_RCVD_REPRESENTING**属性中的相应值的**PR_SENT_REPRESENTING**属性。 
    
5. 创建收件人列表。 有关详细信息，请参阅[创建收件人列表](creating-a-recipient-list.md)。
    
6. 调用转发的邮件[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以保存它或者[IMessage::SubmitMessage](imessage-submitmessage.md)以保存并发送它。 
    
## <a name="see-also"></a>另请参阅

- [PidTagMessageAttachments 规范属性](pidtagmessageattachments-canonical-property.md)

