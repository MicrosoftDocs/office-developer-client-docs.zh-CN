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
ms.openlocfilehash: 4aa800b504e7ffb07d94ace6d8dc30c1463ed637
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427441"
---
# <a name="attachment-tables"></a>附件表

**适用于**：Outlook 2013 | Outlook 2016 
  
附件表包含有关与提交的邮件或组合下的邮件关联的所有附件对象的信息。 
  
表中仅包含通过调用邮件 [的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法保存的附件。 附件表由邮件存储提供程序实现，由客户端应用程序和传输提供程序使用。 
  
可以通过调用以下任一方法访问附件表：
  
- [IMessage::GetAttachmentTable](imessage-getattachmenttable.md)
    
- [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)，请求PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。
    
附件表是动态的。
  
邮件存储提供程序不需要支持对附件表进行排序。 如果不支持排序，则表必须按呈现位置（PR_RENDERING_POSITION ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 显示。 
  
邮件存储提供程序也不需要支持对附件表的限制。 不支持限制的提供程序将MAPI_E_NO_SUPPORT [IMAPITable：：Restrict](imapitable-restrict.md) 和 [IMAPITable：：FindRow](imapitable-findrow.md)的实现返回值。
  
附件表可以较小;所需的列集只有四列：
  
- **PR_ATTACH_NUM (** [PidTagAttachNumber](pidtagattachnumber-canonical-property.md))  
    
- **PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  
    
- **PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md) 
    
- **PR_RENDERING_POSITION**
    
 **PR_ATTACH_NUM** 不可传递，并且包含用于唯一标识邮件中的附件的值。 此属性通常用作表行的索引。 **PR_ATTACH_NUM** 生存期短;仅在包含附件的邮件打开时有效。 只要附件表处于打开状态，它的值就保证保持恒定。 
  
 **PR_INSTANCE_KEY** 表都需要此配置。 它用于唯一标识特定行。 
  
 **PR_RECORD_KEY** 用于唯一地标识对象，以便进行比较。 与 **PR_ATTACH_NUM** 不同 **，PR_RECORD_KEY** 具有与长期条目标识符相同的作用域;即使关闭并重新打开邮件，它仍然可用且有效。 有关在 MAPI 中使用记录键的信息，请参阅[MAPI Record and Search Keys。](mapi-record-and-search-keys.md)
  
 **PR_RENDERING_POSITION** 指示附件在格式文本邮件中的显示方式。 它可以设置为字符的偏移，其中 **存储在 PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中的邮件内容的第一个字符偏移量为 0，或设置为 -1 (0xFFFFFFFF) ，指示完全不应在邮件文本中呈现附件。 不设置 **PR_RENDERING_POSITION** 也是一个选项。 
  
当附件表按呈现位置排序时，邮件存储提供程序会视其为已签名 (PT_LONG) 。 因此，呈现位置为 -1 的附件在呈现位置反映有效偏移的附件之前进行排序。 
  
有关在纯文本邮件中呈现附件的信息，请参阅以纯文本 [呈现附件](rendering-an-attachment-in-plain-text.md)。 
  
有关以 RTF 格式格式等格式文本呈现附件 (RTF) ，请参阅在 [RTF](rendering-an-attachment-in-rtf-text.md)文本中呈现附件。
  
附件表中通常包括邮件存储提供程序的一些属性，因为它们易于计算或检索：
  
|||
|:-----|:-----|
|**PR_ATTACH_ENCODING (** [PidTagAttachEncoding](pidtagattachencoding-canonical-property.md))   <br/> |**PR_ATTACH_EXTENSION (** [PidTagAttachExtension)](pidtagattachextension-canonical-property.md)  <br/> |
|**PR_ATTACH_FILENAME (** [PidTagAttachFilename)](pidtagattachfilename-canonical-property.md)  <br/> |**PR_ATTACH_LONG_FILENAME (** [PidTagAttachLongFilename)](pidtagattachlongfilename-canonical-property.md)  <br/> |
|**PR_ATTACH_PATHNAME (** [PidTagAttachPathname)](pidtagattachpathname-canonical-property.md)  <br/> |**PR_ATTACH_LONG_PATHNAME (** [PidTagAttachLongPathname)](pidtagattachlongpathname-canonical-property.md)  <br/> |
|**PR_ATTACH_METHOD (** [PidTagAttachMethod)](pidtagattachmethod-canonical-property.md)  <br/> |**PR_ATTACH_TAG (** [PidTagAttachTag](pidtagattachtag-canonical-property.md))   <br/> |
|**PR_CREATION_TIME (** [PidTagCreationTime](pidtagcreationtime-canonical-property.md))   <br/> |**PR_ATTACH_TRANSPORT_NAME (** [PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))   <br/> |
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |**PR_LAST_MODIFICATION_TIME (** [PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))   <br/> |
   
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

