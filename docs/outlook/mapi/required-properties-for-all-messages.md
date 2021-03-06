---
title: 所有邮件的必需属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: df7e122f-0c44-4d81-8174-3a2d51671ba9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 329841a49154763a3e73a234e28def149719cb08
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435976"
---
# <a name="required-properties-for-all-messages"></a>所有邮件的必需属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
下表描述了客户端预期在所有类的消息上设置或查看支持的属性。
  
|**属性**|**说明**|
|:-----|:-----|
|**PR_CREATION_TIME**[PidTagCreationTime 规范属性 (](pidtagcreationtime-canonical-property.md) [PidTagCreationTime](pidtagcreationtime-canonical-property.md))   <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|**PR_DISPLAY_BCC (** [PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))   <br/> **PR_DISPLAY_CC (** [PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))   <br/> **PR_DISPLAY_TO (** [PidTagDisplayTo](pidtagdisplayto-canonical-property.md))   <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|||
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|**PR_LAST_MODIFICATION_TIME (** [PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))   <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|**PR_MESSAGE_ATTACHMENTS (** [PidTagMessageAttachments)](pidtagmessageattachments-canonical-property.md)  <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|**PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md))   <br/> |客户端可以在待发邮件上设置;必须由邮件存储提供程序设置（如果未由客户端设置）。  <br/> |
|**PR_MESSAGE_FLAGS (** [PidTagMessageFlags](pidtagmessageflags-canonical-property.md))   <br/> |在保存传出邮件之前由客户端设置，保存后由邮件存储提供程序设置。  <br/> |
|**PR_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients)](pidtagmessagerecipients-canonical-property.md)  <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|**PR_MESSAGE_SIZE (** [PidTagMessageSize](pidtagmessagesize-canonical-property.md))   <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|**PR_MESSAGE_CC_ME (** [PidTagMessageCcMe)](pidtagmessageccme-canonical-property.md)  <br/> **PR_MESSAGE_RECIP_ME (** [PidTagMessageRecipientMe)](pidtagmessagerecipientme-canonical-property.md)  <br/> **PR_MESSAGE_TO_ME (** [PidTagMessageToMe)](pidtagmessagetome-canonical-property.md)  <br/> |由传入邮件上的传输提供程序设置。  <br/> |
|||
|**PR_NORMALIZED_SUBJECT (** [PidTagNormalizedSubject)](pidtagnormalizedsubject-canonical-property.md)  <br/> |由待发邮件上的邮件存储提供程序设置  <br/> |
|**PR_ORIGINATOR_AND_DL_EXPANSION_HISTORY (** [PidTagOriginatorAndDistributionListExpansionHistory](pidtagoriginatoranddistributionlistexpansionhistory-canonical-property.md))   <br/> **PR_ORIGINATOR_CERTIFICATE (** [PidTagOriginatorCertificate](pidtagoriginatorcertificate-canonical-property.md))   <br/> **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED (** [PidTagOriginatorDeliveryReportRequested)](pidtagoriginatordeliveryreportrequested-canonical-property.md)  <br/> **PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED (** [PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md))   <br/> **PR_ORIGINATOR_REQUESTED_ALTERNATE_RECIPIENT (** [PidTagOriginatorRequestedAlternateRecipient](pidtagoriginatorrequestedalternaterecipient-canonical-property.md))   <br/> **PR_ORIGINATOR_RETURN_ADDRESS (** [PidTagOriginatorReturnAddress](pidtagoriginatorreturnaddress-canonical-property.md))   <br/> |由传出邮件上的传输提供程序设置。  <br/> |
|**PR_PARENT_ENTRYID (** [PidTagParentEntryId](pidtagparententryid-canonical-property.md))   <br/> **PR_PARENT_DISPLAY (** [PidTagParentDisplay](pidtagparentdisplay-canonical-property.md))   <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|||
|**PR_RCVD_REPRESENTING_ADDRTYPE (** [PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md))   <br/> **PR_RCVD_REPRESENTING_EMAIL_ADDRESS (** [PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md))   <br/> **PR_RCVD_REPRESENTING_ENTRYID (** [PidTagReceivedRepresentingEntryId)](pidtagreceivedrepresentingentryid-canonical-property.md)  <br/> **PR_RCVD_REPRESENTING_NAME (** [PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))   <br/> **PR_RCVD_REPRESENTING_SEARCH_KEY (** [PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))   <br/> |由传入邮件上的传输提供程序设置。  <br/> |
|**PR_RECEIVED_BY_ADDRTYPE (** [PidTagReceivedByAddressType](pidtagreceivedbyaddresstype-canonical-property.md))   <br/> **PR_RECEIVED_BY_EMAIL_ADDRESS (** [PidTagReceivedByEmailAddress](pidtagreceivedbyemailaddress-canonical-property.md))   <br/> **PR_RECEIVED_BY_ENTRYID (** [PidTagReceivedByEntryId)](pidtagreceivedbyentryid-canonical-property.md)  <br/> **PR_RECEIVED_BY_NAME (** [PidTagReceivedByName](pidtagreceivedbyname-canonical-property.md))   <br/> **PR_RECEIVED_BY_SEARCH_KEY (** [PidTagReceivedBySearchKey](pidtagreceivedbysearchkey-canonical-property.md))   <br/> |由传入邮件上的传输提供程序设置。  <br/> |
|**PR_RECIPIENT_TYPE (** [PidTagRecipientType](pidtagrecipienttype-canonical-property.md))   <br/> |由传入邮件上的邮件存储提供程序设置。  <br/> |
|**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)  <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|**PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md))   <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
|**PR_SENDER_ADDRTYPE (** [PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))   <br/> **PR_SENDER_EMAIL_ADDRESS (** [PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))   <br/> **PR_SENDER_ENTRYID (** [PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))   <br/> **PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md))   <br/> **PR_SENDER_SEARCH_KEY (** [PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))   <br/> |客户端可以在传出邮件上设置这些属性，但传输提供程序必须设置这些属性。  <br/> |
|**PR_SENT_REPRESENTING_ADDRTYPE (** [PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md))   <br/> **PR_SENT_REPRESENTING_EMAIL_ADDRESS (** [PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md))   <br/> **PR_SENT_REPRESENTING_ENTRYID (** [PidTagSentRepresentingEntryId)](pidtagsentrepresentingentryid-canonical-property.md)  <br/> **PR_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md)  <br/> **PR_SENT_REPRESENTING_SEARCH_KEY (** [PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))   <br/> |客户端可以在传出邮件上设置这些属性，但传输提供程序必须设置这些属性。  <br/> |
|**PR_STORE_ENTRYID (** [PidTagStoreEntryId)](pidtagstoreentryid-canonical-property.md)  <br/> **PR_STORE_RECORD_KEY (** [PidTagStoreRecordKey)](pidtagstorerecordkey-canonical-property.md)  <br/> |由待发邮件上的邮件存储提供程序设置。  <br/> |
   

