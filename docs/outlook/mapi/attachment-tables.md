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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318135"
---
# <a name="attachment-tables"></a>附件表

**适用于**：Outlook 2013 | Outlook 2016 
  
附件表包含与提交的邮件或撰写中的邮件相关联的所有附件对象的相关信息。 
  
只有通过对邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法的调用保存的附件才包含在表中。 附件表由邮件存储提供程序实现, 并由客户端应用程序和传输提供程序使用。 
  
可以通过调用以下任一方法来访问附件表:
  
- [IMessage::GetAttachmentTable](imessage-getattachmenttable.md)
    
- [IMAPIProp:: OpenProperty](imapiprop-openproperty.md), 请求**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。
    
附件表是动态的。
  
邮件存储提供程序不需要支持对其附件表进行排序。 如果不支持排序, 则必须按呈现位置的顺序 ( **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性) 显示表。
  
邮件存储提供程序也不需要支持对其附件表的限制。 不支持限制的提供程序将从其[IMAPITable:: Restrict](imapitable-restrict.md)和[IMAPITable:: FindRow](imapitable-findrow.md)的实现中返回 MAPI_E_NO_SUPPORT。
  
附件表可能很小;在必需的列集中只有四列:
  
- **PR_ATTACH_NUM**([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 
    
- **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 
    
- **PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 
    
- **PR_RENDERING_POSITION**
    
 **PR_ATTACH_NUM**为 nontransmittable, 并且包含一个用于唯一标识邮件中的附件的值。 此属性通常用作表中的行的索引。 **PR_ATTACH_NUM**的生命周期较短;仅当包含附件的邮件处于打开状态时, 此方法才有效。 只要附件表打开, 它的值就会保持不变。 
  
 **PR_INSTANCE_KEY**在几乎每个表中都是必需的。 它用于唯一标识特定行。 
  
 **PR_RECORD_KEY**通常用于唯一标识用于比较目的的对象。 与**PR_ATTACH_NUM**不同, **PR_RECORD_KEY**的作用域与长期条目标识符的作用域相同;即使在关闭并重新打开邮件之后, 它仍然可用且有效。 有关 mapi 中使用记录密钥的详细信息, 请参阅[mapi 记录和搜索关键字](mapi-record-and-search-keys.md)。
  
 **PR_RENDERING_POSITION**指示附件在 rtf 邮件中的显示方式。 它可以设置为以字符为单位的偏移量, 邮件内容的第一个字符存储在**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中, 而不是偏移量为 0, 或为-1 (0xffffffff), 指示不应在邮件中呈现附件文本。 不设置**PR_RENDERING_POSITION**也是一个选项。 
  
当按呈现位置对附件表进行排序时, 邮件存储提供程序会将其视为有符号值 (PT_LONG)。 因此, 呈现位置为-1 的附件在显示反映有效偏移量的呈现位置的附件之前进行排序。 
  
有关在纯文本邮件中呈现附件的详细信息, 请参阅[以纯文本格式呈现附件](rendering-an-attachment-in-plain-text.md)。 
  
有关使用格式化文本 (如 rtf 格式) 呈现附件的信息, 请参阅[在 rtf 文本中呈现附件](rendering-an-attachment-in-rtf-text.md)。
  
某些属性邮件存储提供程序通常包含在附件表中, 因为它们易于计算或检索:
  
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

