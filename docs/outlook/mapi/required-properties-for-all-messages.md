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
ms.openlocfilehash: 068bd55761ffd6b10761412314de97791c016f9b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594325"
---
# <a name="required-properties-for-all-messages"></a>所有邮件的必需属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
下表介绍了客户端可以预期设置或请参阅支持的所有类的邮件的属性。
  
|**属性**|**说明**|
|:-----|:-----|
|**PR_CREATION_TIME**[PidTagCreationTime 规范属性](pidtagcreationtime-canonical-property.md)([PidTagCreationTime](pidtagcreationtime-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|**PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))  <br/> **PR_DISPLAY_CC**([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))  <br/> **仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|||
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))  <br/> |可以通过对传出邮件; 客户端设置必须为设置消息存储提供程序如果未设置由客户端。  <br/> |
|**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |它们保存和消息存储提供程序后对其进行保存之前，对传出邮件的客户端设置。  <br/> |
|**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|**PR_MESSAGE_CC_ME**([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))  <br/> **PR_MESSAGE_RECIP_ME**([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))  <br/> **PR_MESSAGE_TO_ME**([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))  <br/> |设置由传输提供程序对传入邮件。  <br/> |
|||
|**PR_NORMALIZED_SUBJECT**([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序  <br/> |
|**PR_ORIGINATOR_AND_DL_EXPANSION_HISTORY**([PidTagOriginatorAndDistributionListExpansionHistory](pidtagoriginatoranddistributionlistexpansionhistory-canonical-property.md))  <br/> **PR_ORIGINATOR_CERTIFICATE**([PidTagOriginatorCertificate](pidtagoriginatorcertificate-canonical-property.md))  <br/> **邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))  <br/> **PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED**([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md))  <br/> **PR_ORIGINATOR_REQUESTED_ALTERNATE_RECIPIENT**([PidTagOriginatorRequestedAlternateRecipient](pidtagoriginatorrequestedalternaterecipient-canonical-property.md))  <br/> **PR_ORIGINATOR_RETURN_ADDRESS**([PidTagOriginatorReturnAddress](pidtagoriginatorreturnaddress-canonical-property.md))  <br/> |由传输提供程序对传出邮件设置。  <br/> |
|**PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))  <br/> **PR_PARENT_DISPLAY**([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|||
|**PR_RCVD_REPRESENTING_ADDRTYPE**([PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md))  <br/> **PR_RCVD_REPRESENTING_EMAIL_ADDRESS**([PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md))  <br/> **PR_RCVD_REPRESENTING_ENTRYID**([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md))  <br/> **PR_RCVD_REPRESENTING_NAME**([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))  <br/> **PR_RCVD_REPRESENTING_SEARCH_KEY**([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))  <br/> |设置由传输提供程序对传入邮件。  <br/> |
|**PR_RECEIVED_BY_ADDRTYPE**([PidTagReceivedByAddressType](pidtagreceivedbyaddresstype-canonical-property.md))  <br/> **PR_RECEIVED_BY_EMAIL_ADDRESS**([PidTagReceivedByEmailAddress](pidtagreceivedbyemailaddress-canonical-property.md))  <br/> **PR_RECEIVED_BY_ENTRYID**([PidTagReceivedByEntryId](pidtagreceivedbyentryid-canonical-property.md))  <br/> **PR_RECEIVED_BY_NAME**([PidTagReceivedByName](pidtagreceivedbyname-canonical-property.md))  <br/> **PR_RECEIVED_BY_SEARCH_KEY**([PidTagReceivedBySearchKey](pidtagreceivedbysearchkey-canonical-property.md))  <br/> |设置由传输提供程序对传入邮件。  <br/> |
|**PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))  <br/> |设置由对传入邮件的消息存储提供程序。  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
|**PR_SENDER_ADDRTYPE**([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))  <br/> **PR_SENDER_EMAIL_ADDRESS**([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))  <br/> **PR_SENDER_ENTRYID**([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))  <br/> **PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> **PR_SENDER_SEARCH_KEY**([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))  <br/> |客户端可以对传出邮件设置这些属性，但传输提供程序必须将它们进行设置。  <br/> |
|**PR_SENT_REPRESENTING_ADDRTYPE**([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md))  <br/> **PR_SENT_REPRESENTING_EMAIL_ADDRESS**([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md))  <br/> **PR_SENT_REPRESENTING_ENTRYID**([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))  <br/> **PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))  <br/> **PR_SENT_REPRESENTING_SEARCH_KEY**([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))  <br/> |客户端可以对传出邮件设置这些属性，但传输提供程序必须将它们进行设置。  <br/> |
|**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))  <br/> **PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))  <br/> |设置由传出邮件的消息存储提供程序。  <br/> |
   

