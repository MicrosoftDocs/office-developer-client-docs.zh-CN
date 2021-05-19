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
  
内容表包含有关 MAPI 容器中的对象的信息。 通讯簿提供程序针对每个容器实现内容表，邮件存储和远程传输提供程序为文件夹实现内容表。 通讯簿容器的内容表列出了有关其邮件用户和通讯组列表对象的信息，而文件夹的内容表列出了有关其邮件的信息。 内容表主要由客户端应用程序使用。 
  
有两种类型的文件夹内容表：
  
- 标准内容表包含标准消息 - 可以传输和向用户显示的邮件。 
    
- 关联的内容表包含客户端为特定目的（例如存储标准邮件的备用表示形式）创建的隐藏、不可传输的信息。 通过向 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 调用传递 MAPI_ASSOCIATED 标志来创建相关信息。 
    
大多数通讯簿容器和许多文件夹的内容表不支持分类排序。 
  
可以通过调用访问内容表：
  
- [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md)。
    
    - 或 -
    
- [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 具有 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 或 **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))  (文件夹) 指定为属性标记，IID_IMAPITable 指定为接口标识符。
    
邮件存储和通讯簿提供程序必须支持检索表属性这两种技术。 提供程序仅支持一种访问这些表的方法是无法接受的，因为客户端希望有选择。 
  
 **GetContentsTable** 接受指定首选项的几个输入标志。 设置后，MAPI_ASSOCIATED标记将检索关联的内容表。 由于某些文件夹不支持关联内容，并且客户端无法提前确定此内容，因此 **GetContentsTable** 有时在请求关联内容表时MAPI_E_NO_SUPPORT返回错误 MAPI_E_NO_SUPPORT。 
  
the MAPI_DEFERRED_ERRORS flag indicates to the implementer of the table that any errors encountered during the call do not need to be reported until some later time. 
  
对 **IMAPIProp：：OpenProperty** 的调用涉及通过打开内容表的相应属性来访问该目录表，为通讯簿内容表和标准文件夹内容表打开 **PR_CONTAINER_CONTENTS，** 对关联内容表调用 PR_FOLDER_ASSOCIATED_CONTENTS。 尽管这两个属性均无法通过文件夹或容器的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法检索，但这些属性包含在 [由 IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法返回的属性标记数组中。 
  
 **PR_CONTAINER_CONTENTS** 还可用于在复制操作中包括或排除内容表。 如果客户端在复制操作PR_CONTAINER_CONTENTS **IMAPIProp：：CopyTo** 的 *lpExcludeProps* 参数中指定值，则新文件夹或容器将不支持原始文件夹或容器的内容表。 
  
通讯簿容器和文件夹内容表具有一个冗长的必需列列表，这些列是客户端从 **GetContentsTable** 或 **OpenProperty** 检索表后预期可用的列。 如果需要，提供程序可以添加到此必需集，并且客户端通过 **SetColumns** 方法也可以请求修改。 
  
每种类型的内容表的必需列为：
  
|**必需列**|**内容表的类型**|
|:-----|:-----|
|**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md))   <br/> |通讯簿容器表  <br/> |
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |通讯簿容器表  <br/> |
|**PR_DISPLAY_CC (** [PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))   <br/> |邮件存储文件夹表  <br/> |
|**PR_DISPLAY_TO (** [PidTagDisplayTo](pidtagdisplayto-canonical-property.md))   <br/> |所有文件夹内容表  <br/> |
|**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md))   <br/> |通讯簿容器表  <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |所有内容表  <br/> |
|**PR_HASATTACH (** [PidTagHasAttachments)](pidtaghasattachments-canonical-property.md)  <br/> |所有文件夹内容表  <br/> |
|**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md))   <br/> |所有内容表  <br/> |
|**PR_LAST_MODIFICATION_TIME (** [PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))   <br/> |邮件存储文件夹表  <br/> |
|**PR_MAPPING_SIGNATURE (** [PidTagMappingSignature)](pidtagmappingsignature-canonical-property.md)  <br/> |邮件存储文件夹表  <br/> |
|**PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md))   <br/> |所有文件夹内容表  <br/> |
|**PR_MESSAGE_DOWNLOAD_TIME (** [PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))   <br/> |远程传输文件夹表  <br/> |
|**PR_MESSAGE_FLAGS (** [PidTagMessageFlags](pidtagmessageflags-canonical-property.md))   <br/> |所有文件夹内容表  <br/> |
|**PR_MESSAGE_SIZE (** [PidTagMessageSize](pidtagmessagesize-canonical-property.md))   <br/> |所有文件夹内容表  <br/> |
|**PR_MSG_STATUS (** [PidTagMessageStatus)](pidtagmessagestatus-canonical-property.md)  <br/> |所有文件夹内容表  <br/> |
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |所有内容表  <br/> |
|**PR_PARENT_ENTRYID (** [PidTagParentEntryId](pidtagparententryid-canonical-property.md))   <br/> |邮件存储文件夹表  <br/> |
|**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)  <br/> |通讯簿容器和邮件存储文件夹表  <br/> |
|**PR_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md)  <br/> |远程传输文件夹表  <br/> |
|**PR_STORE_ENTRYID (** [PidTagStoreEntryId)](pidtagstoreentryid-canonical-property.md)  <br/> |邮件存储文件夹表  <br/> |
|**PR_STORE_RECORD_KEY (** [PidTagStoreRecordKey)](pidtagstorerecordkey-canonical-property.md)  <br/> |邮件存储文件夹表  <br/> |
   
每行可用的条目标识符可以是短期或长期条目标识符，具体取决于表实现。 短期条目标识符通常用于出现性能问题的情况。 两种类型的条目标识符都可用于访问相应的对象。 
  
内容表还有一组列，这些列是可选的，但通常包含在服务提供程序的实现中。 这些可选列包括：
  
|**可选列**|**内容表的类型**|
|:-----|:-----|
|**PR_CLIENT_SUBMIT_TIME (** [PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))   <br/> |邮件存储文件夹表  <br/> |
|**PR_CONTENT_COUNT (** [PidTagContentCount](pidtagcontentcount-canonical-property.md))   <br/> |标准文件夹内容表  <br/> |
|**PR_CONTENT_UNREAD (** [PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))   <br/> |标准文件夹内容表  <br/> |
|**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))  <br/> |邮件存储文件夹表  <br/> |
|**PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)  <br/> |通讯簿容器表  <br/> |
|**PR_IMPORTANCE (** [PidTagImportance)](pidtagimportance-canonical-property.md)  <br/> |所有文件夹内容表  <br/> |
|**PR_MESSAGE_DELIVERY_TIME (** [PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))   <br/> |所有文件夹内容表  <br/> |
|**PR_NORMALIZED_SUBJECT (** [PidTagNormalizedSubject)](pidtagnormalizedsubject-canonical-property.md)  <br/> |所有文件夹内容表  <br/> |
|**PR_PRIORITY (** [PidTagPriority)](pidtagpriority-canonical-property.md)  <br/> |所有文件夹内容表  <br/> |
|**PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md))   <br/> |通讯簿容器表  <br/> |
|**PR_SEND_RICH_INFO (** [PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))   <br/> |通讯簿容器表  <br/> |
|**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md))   <br/> |所有文件夹内容表  <br/> |
|**PR_SENSITIVITY (** [PidTagSensitivity)](pidtagsensitivity-canonical-property.md)  <br/> |所有文件夹内容表  <br/> |
|**PR_SUBJECT (** [PidTagSubject)](pidtagsubject-canonical-property.md)  <br/> |所有文件夹内容表  <br/> |
|**PR_TRANSMITABLE_DISPLAY_NAME (** [PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))   <br/> |通讯簿容器表  <br/> |
   
邮件存储提供程序 **还必须PR_PARENT_DISPLAY (** [PidTagParentDisplay](pidtagparentdisplay-canonical-property.md)) 搜索结果文件夹内容表。
  
只有在文件夹中的所有邮件具有相同的映射签名（即属性名称与属性标识符的映射相同）时，才能将命名属性添加到文件夹内容表的列集。 如果文件夹内容表支持在文件夹中创建任意邮件，则它们应支持将邮件类特定属性添加到列集。
  
客户端可以通过调用文件夹内容表的 [IMAPIFolder：：SaveContentsSort](imapifolder-savecontentssort.md) 方法保存其默认排序顺序。 如果在RECURSIVE_SORT上指定了子文件夹标记，则排序顺序可以应用于文件夹内的所有子文件夹。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

