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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328061"
---
# <a name="forwarding-a-message"></a>转发邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
转发邮件涉及发送原始邮件的许多相同的任务。 首先, 必须打开默认邮件存储和指定用于保存传出邮件的文件夹 (通常为 "发件箱"), 并调用此文件夹的[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法来创建要转发的邮件。 您还必须打开保存原始邮件的文件夹 (通常为 "收件箱")。 有关打开不同文件夹的信息, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
  
创建要转发的邮件和创建原始邮件的主要区别在于, 在转发邮件时, 大部分属性是基于原始邮件的属性, 还是直接从原始邮件的属性复制。 
  
**转发邮件**
  
1. 打开默认邮件存储。 有关详细信息, 请参阅[打开默认邮件存储](opening-the-default-message-store.md)。
    
2. 打开 "发件箱" 文件夹。 有关详细信息, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
    
3. 调用发件箱的[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法以创建新的转发邮件。 
    
4. 调用原始邮件的[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将以下属性复制到转发的邮件: 
    
   - **pr\_正文**([PidTagBody](pidtagbody-canonical-property.md))、 **pr\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)), 具体取决于您是否支持 rtf 格式、纯文本或 HTML。
    
   - **PR\_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 
    
5. 通过调用原始邮件的**IMAPIProp:: CopyTo**方法复制**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性或调用以下命令, 从原始邮件复制邮件附件:对于要复制的每个附件, 三个步骤的过程:
    
   1. 调用新的转发邮件的[IMessage:: CreateAttach](imessage-createattach.md)方法以创建新的附件。 
      
   2. 调用原始邮件的[IMessage:: OpenAttach](imessage-openattach.md)方法以打开要复制的附件。 
      
   3. 调用原始邮件的**IMAPIProp:: CopyTo**方法将所有附件属性从旧附件复制到新附件。 
    
6. 请勿在调用**IMAPIProp:: CopyTo**中包含以下属性: 
    
|||
|:-----|:-----|
|**PR_CLIENT_SUBMIT_TIME**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))  <br/> |**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |
|**PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))  <br/> |**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |
|**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))  <br/> |**PR_RCVD_REPRESENTING**属性  <br/> |
|**PR_READ_RECEIPT_ENTRYID**([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md))  <br/> |**PR_READ_RECEIPT_REQUESTED**([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))  <br/> |
|**PR_RECEIVED_BY**属性  <br/> |**PR_REPLY_RECIPIENT**属性  <br/> |
|**PR_REPORT_ENTRYID**([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))  <br/> |**PR_SENDER**属性  <br/> |
|**PR_SENT_REPRESENTING**属性  <br/> |**PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))  <br/> |
|**PR_SUBJECT_PREFIX**([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))  <br/> | <br/> |
   
1. 通过添加缩进和包含原始发件人、"传输日期"、"主题" 和 "收件人" 列表的标题段落来设置邮件文本的格式。 不要将 Internet 样式前缀字符包含在内容中。
    
2. 调用[ScCreateConversationIndex](sccreateconversationindex.md), 并传入原始邮件的**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性的值。
    
3. 为转发的邮件设置前缀。 如果使用的是标准 "FW:", 请将这些字符连接到**PR_NORMALIZED_SUBJECT**的开头, 并将**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 连接到此新字符串。 请勿设置**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))。 如果您使用非标准前缀 (例如字符串超过三个字符的字符串), 则将其存储在**PR_SUBJECT_PREFIX**中。 
    
4. 将**PR_SENT_REPRESENTING**属性设置为**PR_RCVD_REPRESENTING**属性中对应的值。 
    
5. 创建收件人列表。 有关详细信息, 请参阅[创建收件人列表](creating-a-recipient-list.md)。
    
6. 调用转发邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存它或[IMessage:: SubmitMessage](imessage-submitmessage.md)保存并发送它。 
    
## <a name="see-also"></a>另请参阅

- [PidTagMessageAttachments 规范属性](pidtagmessageattachments-canonical-property.md)

