---
title: 映射到 MAPI 属性 TNEF 属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1a724fac-2e64-48a7-92b5-d7cf1528cb2c
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 18c11c3f945e00ae1f12e5c948b81abfb88e41ef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776417"
---
# <a name="mapping-of-tnef-attributes-to-mapi-properties"></a>映射到 MAPI 属性 TNEF 属性

  
  
**适用于**： Outlook 
  
下表列出 TNEF 实现和其映射到 MAPI 属性中定义的所有属性。 在某些情况下，多个 MAPI 属性被编码为单个属性。 某些属性已扩展本节后面的说明。
  
|**TNEF 属性**|**MAPI 属性或属性**|
|:-----|:-----|
|**attAidOwner** <br/> |**PR_OWNER_APPT_ID**([PidTagOwnerAppointmentId](pidtagownerappointmentid-canonical-property.md))  <br/> |
|**attAttachCreateDate** <br/> |**PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))  <br/> |
|**attAttachData** <br/> |**PR_ATTACH_DATA_BIN**([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))  <br/> |
|**attAttachment** <br/> |有关此映射的信息，请参阅[TNEF 属性](tnef-attributes.md)。  <br/> |
|**attAttachMetaFile** <br/> |**PR_ATTACH_RENDERING**([PidTagAttachRendering](pidtagattachrendering-canonical-property.md))  <br/> |
|**attAttachModifyDate** <br/> |**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))  <br/> |
|**attAttachRenddata** <br/> |**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))， **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))  <br/> |
|**attAttachTitle** <br/> |**PR_ATTACH_FILENAME**([PidTagAttachFilename](pidtagattachfilename-canonical-property.md))  <br/> |
|**attAttachTransportFilename** <br/> |**PR_ATTACH_TRANSPORT_NAME**([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))  <br/> |
|**attBody** <br/> |**PR_BODY**([PidTagBody](pidtagbody-canonical-property.md))  <br/> |
|**attConversationID** <br/> |**PR_CONVERSATION_KEY**([PidTagConversationKey](pidtagconversationkey-canonical-property.md))Microsoft Exchange Server 中已弃用此属性： 其使用依然存在，请在 Outlook 中仅用于查找**IPM。MessageManager**消息。  <br/> |
|**attDateEnd** <br/> |**PR_END_DATE**([PidTagEndDate](pidtagenddate-canonical-property.md))有关详细信息，请参阅[attDate 属性](attdate-attributes.md)。  <br/> |
|**attDateModified** <br/> |**操作**有关详细信息，请参阅[attDate 属性](attdate-attributes.md)。  <br/> |
|**attDateRecd** <br/> |**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))有关详细信息，请参阅[attDate 属性](attdate-attributes.md)。  <br/> |
|**attDateSent** <br/> |**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))有关详细信息，请参阅[attDate 属性](attdate-attributes.md)。  <br/> |
|**attDateStart** <br/> |**PR_START_DATE**([PidTagStartDate](pidtagstartdate-canonical-property.md))有关详细信息，请参阅[attDate 属性](attdate-attributes.md)。  <br/> |
|**attFrom** <br/> |**PR_SENDER_ENTRYID**([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 和**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |
|**attMAPIProps** <br/> |有关此属性的信息，请参阅[attMAPIProps](attmapiprops.md)。  <br/> |
|**attMessageClass** <br/> |**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))  <br/> |
|**attMessageID** <br/> |**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))请参见[X.400 网关和传输中的 TNEF 关联](tnef-correlation-in-x-400-gateways-and-transports.md)。  <br/> |
|**attMessageStatus** <br/> |**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |
|**attOriginalMessageClass** <br/> |* * PR_ORIG_MESSAGE_CLASS * * ([PidTagOriginalMessageClass](pidtagoriginalmessageclass-canonical-property.md))  <br/> |
|**attOwner** <br/> |请参阅[attOwner](attowner.md)。  <br/> |
|**attParentID** <br/> |**PR_PARENT_KEY**(**PidTagParentKey**)此属性已被弃用。 有关详细信息，请参阅[API 此版本中已弃用的元素](api-elements-deprecated-in-this-edition.md)。  <br/> |
|**attPriority** <br/> |**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))  <br/> |
|**attRecipTable** <br/> |**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))  <br/> |
|**attRequestRes** <br/> |**PR_RESPONSE_REQUESTED**([PidTagResponseRequested](pidtagresponserequested-canonical-property.md))  <br/> |
|**attSentFor** <br/> |**PR_SENT_REPRESENTING_ENTRYID**([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))  <br/> |
|**attSubject** <br/> |**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |
   

