---
title: 内容表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7b8efb4e-b5be-41b8-81bb-9aa1da421433
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0dd79d9630837b5ec8a709d386ccc0db987dfb5b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774681"
---
# <a name="contents-tables"></a>内容表

  
  
**适用于**： Outlook 
  
内容表包含有关 MAPI 容器中的对象的信息。 通讯簿提供程序实现的其容器，每个内容表和消息存储和远程传输提供程序实现其文件夹的内容表。 文件夹的内容表列出了其邮件的信息时的通讯簿容器内容表列出了有关其邮件用户和通讯组列表对象的信息。 内容表主要使用客户端应用程序。 
  
有两种类型的文件夹内容表：
  
- 标准内容表包含标准消息 — 可以传输和向用户显示的消息。 
    
- 关联的内容表包含隐藏、 非可传送创建客户端的特定用途，如存储标准消息备用表示的信息。 通过将 MAPI_ASSOCIATED 标志传递给[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)呼叫创建的相关的信息。 
    
大多数地址簿容器和多个文件夹的表不支持的内容进行分类排序。 
  
可以通过调用访问内容表：
  
- [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)。
    
    - 或者-
    
- 与**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 或**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) （仅文件夹） 指定为属性标记和 IID [IMAPIProp::OpenProperty](imapiprop-openproperty.md)接口标识 _IMAPITable。
    
消息存储和地址簿提供程序必须支持这两种方法，用于检索表属性。 它是无法接受的提供程序可以访问这些表，因为客户端期望有选择支持只有一个办法。 
  
 **GetContentsTable**接受指定首选项的几个标志作为输入。 设置时，MAPI_ASSOCIATED 标志检索关联的内容表。 由于某些文件夹不支持关联的内容，并且没有为客户端提早制定确定此方法， **GetContentsTable**有时返回错误 MAPI_E_NO_SUPPORT 请求相关联的内容表时。 
  
向呼叫过程中遇到的任何错误不需要之前一些更高版本的时间报告的表的实施指示 MAPI_DEFERRED_ERRORS 标志。 
  
调用**IMAPIProp::OpenProperty**涉及通过打开及其对应的属性，对通讯簿内容表和标准文件夹内容表**PR_FOLDER_ASSOCIATED_ **PR_CONTAINER_CONTENTS**访问内容表内容**的相关内容表。 尽管都不或可以通过文件夹或容器的[IMAPIProp::GetProps](imapiprop-getprops.md)方法检索这些属性，它们包括在由[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的属性标记数组。 
  
 **PR_CONTAINER_CONTENTS**还可以用于中包括或排除内容表复制操作。 如果客户端**PR_CONTAINER_CONTENTS** *lpExcludeProps*参数中指定的**IMAPIProp::CopyTo**复制操作中的新文件夹或容器不支持的原始文件夹或容器的内容表。 
  
通讯簿容器和文件夹内容表具有冗长所需的列的列表，客户端可以预期将之后从**GetContentsTable**或**OpenProperty**检索表可用的列。 如果需要与客户端，通过**SetColumns**方法，还可以请求进行修改，可以向此组添加提供程序。 
  
所需的列的每种类型的内容表是：
  
|**所需的列**|**内容表的类型**|
|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_DISPLAY_CC**([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))  <br/> |邮件存储区文件夹表  <br/> |
|**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |所有内容表  <br/> |
|**PR_HASATTACH**([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |所有内容表  <br/> |
|**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))  <br/> |邮件存储区文件夹表  <br/> |
|**PR_MAPPING_SIGNATURE**([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md))  <br/> |邮件存储区文件夹表  <br/> |
|**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))  <br/> |远程传输文件夹表  <br/> |
|**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_MSG_STATUS**([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |所有内容表  <br/> |
|**PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))  <br/> |邮件存储区文件夹表  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |通讯簿容器和消息存储库文件夹表  <br/> |
|**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))  <br/> |远程传输文件夹表  <br/> |
|**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))  <br/> |邮件存储区文件夹表  <br/> |
|**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))  <br/> |邮件存储区文件夹表  <br/> |
   
具有每行的项标识符可以是一个短期或长期条目标识符，具体取决于表实现。 短期条目标识符通常在的情况下性能问题。 任一类型的项标识符可用于访问相应的对象。 
  
内容表还有一组是可选的但通常由服务提供商提供在其实现中包括的列。 这些可选列有：
  
|**可选的列**|**内容表的类型**|
|:-----|:-----|
|**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))  <br/> |邮件存储区文件夹表  <br/> |
|**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))  <br/> |标准文件夹内容表  <br/> |
|**PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))  <br/> |标准文件夹内容表  <br/> |
|**PR_CONVERSATION_INDEX**([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))  <br/> |邮件存储区文件夹表  <br/> |
|**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_NORMALIZED_SUBJECT**([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_SEND_RICH_INFO**([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |文件夹内容的所有表  <br/> |
|**PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
   
消息存储提供程序还必须包括**PR_PARENT_DISPLAY** ([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md)) 搜索结果文件夹内容仅用于表。
  
命名的属性可能会添加到文件夹内容表的列集，仅当文件夹中的所有邮件都具有相同映射的签名，即到属性标识符的属性名称的相同的映射。 文件夹内容表应支持设置特定属性设置为列中，添加邮件类，它们是否支持的任意邮件创建的文件夹中。
  
客户端可以通过调用其[IMAPIFolder::SaveContentsSort](imapifolder-savecontentssort.md)方法保存文件夹内容表的默认排序次序。 如果在调用指定 RECURSIVE_SORT 标志，则可以进行的排序次序要应用于所有文件夹中的子文件夹。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

