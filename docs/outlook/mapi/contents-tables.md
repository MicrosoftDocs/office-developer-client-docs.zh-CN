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
ms.openlocfilehash: 491381c771cae65e682acc8033b6558523847d3d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435584"
---
# <a name="contents-tables"></a>内容表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
内容表包含有关 MAPI 容器中的对象的信息。 通讯簿提供程序实现每个容器的内容表, 邮件存储和远程传输提供程序实现其文件夹的内容表。 通讯簿容器的 "内容" 表列出了有关其邮件用户和通讯组列表对象的信息, 而文件夹的 "内容" 表中列出了有关其邮件的信息。 内容表主要由客户端应用程序使用。 
  
"文件夹内容" 表格有以下两种类型:
  
- 标准内容表包含标准邮件, 即可以传输并对用户可见的邮件。 
    
- 关联的内容表包含客户端出于特定目的而创建的隐藏、非传输信息, 例如, 用于存储标准邮件的替代表示形式。 相关信息是通过将 MAPI_ASSOCIATED 标志传递给[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)调用而创建的。 
    
大多数通讯簿容器和多个文件夹的内容表格不支持分类排序。 
  
可以通过调用来访问内容表:
  
- [IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)。
    
    - 和
    
- [IMAPIProp:: OpenProperty](imapiprop-openproperty.md) with **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 或**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) (仅限文件夹) 指定为属性标记和 IID_IMAPITable 作为接口标识符。
    
邮件存储和通讯簿提供程序必须支持这两种方法来检索表属性。 提供程序不可接受仅支持一种访问这些表的方法, 因为客户端希望能够进行选择。 
  
 **GetContentsTable**接受输入多个指定首选项的标志。 设置时, MAPI_ASSOCIATED 标志将检索关联的内容表。 由于某些文件夹不支持关联的内容, 并且客户端无法提前确定这种情况, 因此在请求关联的内容表时, **GetContentsTable**有时会返回错误 MAPI_E_NO_SUPPORT。 
  
MAPI_DEFERRED_ERRORS 标志向表的实施者表明, 在此之前, 不需要报告在呼叫过程中遇到的任何错误。 
  
对**IMAPIProp:: OpenProperty**的调用涉及到访问内容表, 方法是打开其相应的属性、 **PR_CONTAINER_CONTENTS**用于通讯簿内容表和标准文件夹内容表以及**PR_FOLDER_ASSOCIATED_** 关联的内容表的内容。 尽管不能通过文件夹或容器的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法检索这些属性, 但它们包含在由[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法返回的属性标记数组中。 
  
 **PR_CONTAINER_CONTENTS**还可用于在复制操作中包含或排除内容表。 如果客户端在*lpExcludeProps*参数中为**IMAPIProp:: CopyTo**在复制操作中指定了**PR_CONTAINER_CONTENTS** , 则新的文件夹或容器将不支持原始文件夹或容器的内容表。 
  
通讯簿容器和文件夹内容表包含所需列的冗长列表, 客户端在从**GetContentsTable**或**OpenProperty**检索表后, 这些列将可供使用。 如果必要, 提供程序可以向此必需的集合中添加, 并且通过**SetColumns**方法, 客户端也可以请求修改。 
  
每种类型的内容表的必需列为:
  
|**必需列**|**内容类型表**|
|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_DISPLAY_CC**([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
|**PR_DISPLAY_TO**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |所有内容表  <br/> |
|**PR_HASATTACH**([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |所有内容表  <br/> |
|**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
|**PR_MAPPING_SIGNATURE**([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
|**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))  <br/> |远程传输文件夹表  <br/> |
|**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_MSG_STATUS**([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |所有内容表  <br/> |
|**PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |通讯簿容器和邮件存储文件夹表  <br/> |
|**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))  <br/> |远程传输文件夹表  <br/> |
|**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
|**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
   
每行可用的条目标识符可以是短期或长期条目标识符, 具体取决于表实现。 短期条目标识符通常在性能问题的情况下使用。 可以使用任一类型的条目标识符来访问相应的对象。 
  
内容表还具有一组可选列, 这些列是可选的, 但通常由服务提供程序在其实现中包括。 这些可选列为:
  
|**可选列**|**内容类型表**|
|:-----|:-----|
|**PR_CLIENT_SUBMIT_TIME**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
|**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))  <br/> |标准文件夹内容表  <br/> |
|**PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))  <br/> |标准文件夹内容表  <br/> |
|**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
|**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_NORMALIZED_SUBJECT**([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_SEND_RICH_INFO**([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
|**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |所有文件夹内容表  <br/> |
|**PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))  <br/> |通讯簿容器表  <br/> |
   
邮件存储提供程序还必须包括**PR_PARENT_DISPLAY** ([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md)) 仅用于搜索结果文件夹内容表。
  
只有当文件夹中的所有邮件具有相同的映射签名 (即, 属性名称与属性标识符的映射) 时, 才能将命名属性添加到 "文件夹内容" 表的列集中。 如果用户支持在该文件夹中创建任意邮件, 则文件夹内容表格应支持向列集添加特定于邮件类别的属性。
  
客户端可以通过调用[IMAPIFolder:: SaveContentsSort](imapifolder-savecontentssort.md)方法来保存文件夹内容表的默认排序顺序。 如果在呼叫中指定了 RECURSIVE_SORT 标志, 则可以对该文件夹中的所有子文件夹应用排序次序。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

