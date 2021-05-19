---
title: 设置传入邮件的属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cf4a0501-f42b-4652-a239-003022686475
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d7043004799d534f11aa98770e2e323cbdae95a8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432693"
---
# <a name="setting-properties-on-incoming-messages"></a>设置传入邮件的属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 子系统内的客户端应用程序期望收到的任何邮件中具有许多属性。 当传输提供程序将邮件引入 MAPI 时，它应设置这些属性，因为它是唯一具有所需信息的进程，或者至少是信息的最佳来源。
  
建议提供程序在传入邮件中设置所有这些属性的值。
  
|**属性名称**|**说明**|
|:-----|:-----|
|**PR_SUBJECT (** [PidTagSubject)](pidtagsubject-canonical-property.md)  <br/> |邮件的主题。  <br/> |
|**PR_BODY (** [PidTagBody](pidtagbody-canonical-property.md))   <br/> |纯文本消息文本。  <br/> |
|**PR_RTF_COMPRESSED (** [PidTagRtfCompressed)](pidtagrtfcompressed-canonical-property.md)  <br/> |压缩的 RTF 消息文本。  <br/> |
|**PR_MESSAGE_DELIVERY_TIME (** [PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))   <br/> |邮件的传递日期和时间。  <br/> |
|**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md))   <br/> |邮件显示名称的收件人。  <br/> |
|**PR_SENDER_ENTRYID (** [PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))   <br/> |邮件发起者的地址簿条目。  <br/> |
|**PR_SENDER_SEARCH_KEY (** [PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))   <br/> |邮件发起方的地址簿搜索密钥。  <br/> |
|**PR_CLIENT_SUBMIT_TIME (** [PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))   <br/> |发件人的邮件客户端将邮件提交到邮件系统的时间。  <br/> |
|**PR_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md)  <br/> |要发送的代表代理的名称。  <br/> |
|**PR_SENT_REPRESENTING_ENTRYID (** [PidTagSentRepresentingEntryId)](pidtagsentrepresentingentryid-canonical-property.md)  <br/> |发送代理的通讯簿条目。  <br/> |
|**PR_SENT_REPRESENTING_SEARCH_KEY (** [PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))   <br/> |发送代理的通讯簿搜索密钥。  <br/> |
|**PR_RCVD_REPRESENTING_NAME (** [PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))   <br/> |用于接收的代表代理人的名称。  <br/> |
|**PR_RCVD_REPRESENTING_ENTRYID (** [PidTagReceivedRepresentingEntryId)](pidtagreceivedrepresentingentryid-canonical-property.md)  <br/> |接收代理的通讯簿条目。  <br/> |
|**PR_RCVD_REPRESENTING_SEARCH_KEY (** [PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))   <br/> |接收代理的通讯簿搜索密钥。  <br/> |
|**PR_REPLY_RECIPIENT_NAMES (** [PidTagReplyRecipientNames)](pidtagreplyrecipientnames-canonical-property.md)  <br/> |委派收件人显示名称的列表，用分号和空格分隔 (";") 。  <br/> |
|**PR_REPLY_RECIPIENT_ENTRIES (** [PidTagReplyRecipientEntries)](pidtagreplyrecipiententries-canonical-property.md)  <br/> |答复的委派收件人列表。  <br/> |
|**PR_MESSAGE_TO_ME (** [PidTagMessageToMe)](pidtagmessagetome-canonical-property.md)  <br/> |指示收件人被明确命名为"收件人"收件人 (不在组或) 。  <br/> |
|**PR_MESSAGE_CC_ME (** [PidTagMessageCcMe)](pidtagmessageccme-canonical-property.md)  <br/> |指示收件人被专门命名为"cc"收件人 (不在组或) 。  <br/> |
|**PR_MESSAGE_RECIP_ME (** [PidTagMessageRecipientMe)](pidtagmessagerecipientme-canonical-property.md)  <br/> |指示收件人被专门命名为"to"、"cc"或"bcc"收件人 (不在组或) 。  <br/> |
   
没有明显映射的提供程序可以将 **PR_SENT_REPRESENTING** 属性组设置为 **与 PR_SENDER** 组相同的值，将 **PR_RCVD_REPRESENTING** 属性组设置为与 **PR_RECEIVED_BY** 组相同的值，并可以基于 **PR_SENDER** 组的值构建 **PR_REPLY_RECIPIENT** 属性组。 例如 **，PR_SENT_REPRESENTING_NAME** 可以设置为与 PR_SENDER_NAME **相同的值**。
  
如有必要 **PR_ENTRYID** [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)方法生成 PR_ENTRYID 或 PR_ENTRYLIST 属性。  可以通过 **连接与** 用户关联的 **PR_ADDRTYPE** 属性、冒号 (：) 和与用户关联的 PR_EMAIL_ADDRESS 属性，然后将结果更改为大写来生成 **PR_SEARCH_KEY** 组属性。 此Windows API 函数 **CharUpperBuff** 是一个方便使用的函数。 此过程所需的是制作可以比较为二进制数量的地址的规范形式。 请注意，如果传输提供程序的电子邮件地址区分大小写，则不需要这样做。 
  

