---
title: 附件表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 92a07f7b-d34c-4085-ab11-eadcd918fa1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 27e489447b501b6e0d3bb7d668cecc3750be443e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564120"
---
# <a name="attachment-tables"></a>附件表

**适用于**： Outlook 2013 |Outlook 2016 
  
附件表包含有关与已提交的邮件或在组合下的一条消息相关联的 attachment 对象的所有信息。 
  
通过调用消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法已保存的附件包含在表中。 附件表由消息存储提供程序实现并使用客户端应用程序和传输提供程序。 
  
附件表可通过调用以下任一项：
  
- [IMessage::GetAttachmentTable](imessage-getattachmenttable.md)
    
- [IMAPIProp::OpenProperty](imapiprop-openproperty.md)，请求**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。
    
附件表是动态的。
  
消息存储提供程序不需要支持对其附件表排序。 如果不支持进行排序，必须按呈现位置顺序显示表 — **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性。
  
消息存储提供程序不还需要支持其附件表上的限制。 不支持限制的提供程序返回的[IMAPITable::Restrict](imapitable-restrict.md)和[IMAPITable::FindRow](imapitable-findrow.md)其实现 MAPI_E_NO_SUPPORT。
  
附件表可以小型;所需的列设置中有仅四列：
  
- **PR_ATTACH_NUM**([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 
    
- **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 
    
- **PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 
    
- **PR_RENDERING_POSITION**
    
 **PR_ATTACH_NUM** nontransmittable 并包含用于唯一地标识邮件中的附件的值。 此属性通常用作索引到 table 的行。 **PR_ATTACH_NUM**具有短寿命;打开包含附件的邮件时才有效。 其值保证保持不变，只要附件表处于打开状态。 
  
 几乎在每个表中需要**PR_INSTANCE_KEY** 。 它用于唯一标识的特定行。 
  
 **PR_RECORD_KEY**通常用于唯一标识为了进行比较的对象。 与**PR_ATTACH_NUM**，不同**PR_RECORD_KEY**具有相同的范围的长期的项标识符;尚待可用且有效，即使关闭并重新打开该邮件。 有关使用 MAPI 中的记录项的详细信息，请参阅[MAPI 记录和搜索键](mapi-record-and-search-keys.md)。
  
 **PR_RENDERING_POSITION**指示附件格式文本消息中的显示方式。 它可以设为字符，如要偏移 0， **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中存储的消息内容的第一个字符中的偏移量或为-1 (0xFFFFFFFF)，指示附件应不呈现在邮件内部在所有的文本。 不设置**PR_RENDERING_POSITION**也是一个选项。 
  
附件表进行排序的呈现位置时, 的消息存储提供程序会将其视为有符号值 (PT_LONG)。 因此，具有呈现位置为-1 附件进行排序之前具有反映有效偏移量的呈现位置的附件。 
  
关于呈现纯文本邮件的附件的详细信息，请参阅[呈现纯文本中的附件](rendering-an-attachment-in-plain-text.md)。 
  
关于呈现附件格式化文本如富文本格式 (RTF) 中的信息，请参阅[呈现 RTF 文本中的附件](rendering-an-attachment-in-rtf-text.md)。
  
下面是一些消息存储提供程序通常包括附件表格中因为它们是易于计算或检索的属性：
  
|||
|:-----|:-----|
|**PR_ATTACH_ENCODING**([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md))  <br/> |**PR_ATTACH_EXTENSION**([PidTagAttachExtension](pidtagattachextension-canonical-property.md))  <br/> |
|**PR_ATTACH_FILENAME**([PidTagAttachFilename](pidtagattachfilename-canonical-property.md))  <br/> |**PR_ATTACH_LONG_FILENAME**([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md))  <br/> |
|**PR_ATTACH_PATHNAME**([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))  <br/> |**PR_ATTACH_LONG_PATHNAME**([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md))  <br/> |
|**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))  <br/> |**PR_ATTACH_TAG**([PidTagAttachTag](pidtagattachtag-canonical-property.md))  <br/> |
|**PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))  <br/> |**PR_ATTACH_TRANSPORT_NAME**([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))  <br/> |
   
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

