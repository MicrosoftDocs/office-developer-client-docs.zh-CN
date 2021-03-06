---
title: TNEF 属性到 MAPI 属性的映射
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1a724fac-2e64-48a7-92b5-d7cf1528cb2c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 25647a6488fec9a39f8b41441fe9afc4c4aa0a7d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405021"
---
# <a name="mapping-of-tnef-attributes-to-mapi-properties"></a>TNEF 属性到 MAPI 属性的映射

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
下表列出了 TNEF 实现中定义的所有属性及其到 MAPI 属性的映射。 在某些情况下，多个 MAPI 属性编码为单个属性。 一些属性在本节的稍后部分中具有扩展说明。
  
|**TNEF 属性**|**MAPI 属性**|
|:-----|:-----|
|**attOwnOwner** <br/> |**PR_OWNER_APPT_ID (** [PidTagOwnerAppointmentId](pidtagownerappointmentid-canonical-property.md))   <br/> |
|**attAttachCreateDate** <br/> |**PR_CREATION_TIME (** [PidTagCreationTime](pidtagcreationtime-canonical-property.md))   <br/> |
|**attAttachData** <br/> |**PR_ATTACH_DATA_BIN (** [PidTagAttachDataObject](pidtagattachdatabinary-canonical-property.md)) 或 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))   <br/> |
|**attAttachment** <br/> |有关此映射的信息，请参阅 [TNEF 属性](tnef-attributes.md)。  <br/> |
|**attAttachMetaFile** <br/> |**PR_ATTACH_RENDERING (** [PidTagAttachRendering](pidtagattachrendering-canonical-property.md))   <br/> |
|**attAttachModifyDate** <br/> |**PR_LAST_MODIFICATION_TIME (** [PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))   <br/> |
|**attAttachRenddata** <br/> |**PR_ATTACH_METHOD (** [PidTagAttachMethod](pidtagattachmethod-canonical-property.md) **) ，PR_RENDERING_POSITION (** [PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))   <br/> |
|**attAttachTitle** <br/> |**PR_ATTACH_FILENAME (** [PidTagAttachFilename)](pidtagattachfilename-canonical-property.md)  <br/> |
|**attAttachTransportFilename** <br/> |**PR_ATTACH_TRANSPORT_NAME (** [PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))   <br/> |
|**attBody** <br/> |**PR_BODY (** [PidTagBody](pidtagbody-canonical-property.md))   <br/> |
|**attConversationID** <br/> |**PR_CONVERSATION_KEY (** [PidTagConversationKey](pidtagconversationkey-canonical-property.md)) 此属性已在 Microsoft Exchange Server 中弃用：它仅在 Outlook 中保留用于定位 **IPM。MessageManager** 邮件。  <br/> |
|**attDateEnd** <br/> |**PR_END_DATE (** [PidTagEndDate](pidtagenddate-canonical-property.md)) 有关详细信息，请参阅 [attDate](attdate-attributes.md) 属性。  <br/> |
|**attDateModified** <br/> |**PR_LAST_MODIFICATION_TIME** 有关详细信息 [，请参阅 attDate](attdate-attributes.md) 属性。  <br/> |
|**attDateRecd** <br/> |**PR_MESSAGE_DELIVERY_TIME (** [PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 请参阅 [attDate 属性](attdate-attributes.md) 了解详细信息。  <br/> |
|**attDateSent** <br/> |**PR_CLIENT_SUBMIT_TIME (** [PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 请参阅 [attDate 属性](attdate-attributes.md) 了解详细信息。  <br/> |
|**attDateStart** <br/> |**PR_START_DATE (** [PidTagStartDate](pidtagstartdate-canonical-property.md)) 请参阅 [attDate 属性](attdate-attributes.md) 了解详细信息。  <br/> |
|**attFrom** <br/> |**PR_SENDER_ENTRYID (** [PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md) **)** [PidTagSenderName PR_SENDER_NAME (PidTagSenderName](pidtagsendername-canonical-property.md))   <br/> |
|**attMAPIProps** <br/> |有关此属性的信息，请参阅 [attMAPIProps](attmapiprops.md)。  <br/> |
|**attMessageClass** <br/> |**PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md))   <br/> |
|**attMessageID** <br/> |**PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 请参阅 [X.400 Gateways and Transports 中的 TNEF Correlation。](tnef-correlation-in-x-400-gateways-and-transports.md)  <br/> |
|**attMessageStatus** <br/> |**PR_MESSAGE_FLAGS (** [PidTagMessageFlags](pidtagmessageflags-canonical-property.md))   <br/> |
|**attOriginalMessageClass** <br/> |**PR_ORIG_MESSAGE_CLASS ** ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md))   <br/> |
|**attOwner** <br/> |请参阅 [attOwner](attowner.md)。  <br/> |
|**attParentID** <br/> |**PR_PARENT_KEY (** **PidTagParentKey**) 此属性已被弃用。 有关详细信息 [，请参阅](api-elements-deprecated-in-this-edition.md) 此版本中弃用 API 元素。  <br/> |
|**attPriority** <br/> |**PR_PRIORITY (** [PidTagPriority)](pidtagpriority-canonical-property.md)  <br/> |
|**attRecipTable** <br/> |**PR_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients)](pidtagmessagerecipients-canonical-property.md)  <br/> |
|**attRequestRes** <br/> |**PR_RESPONSE_REQUESTED (** [PidTagResponseRequested](pidtagresponserequested-canonical-property.md))   <br/> |
|**attSentFor** <br/> |**PR_SENT_REPRESENTING_ENTRYID (** [PidTagSentRepresentingEntryId)](pidtagsentrepresentingentryid-canonical-property.md)  <br/> |
|**attSubject** <br/> |**PR_SUBJECT (** [PidTagSubject)](pidtagsubject-canonical-property.md)  <br/> |
   

