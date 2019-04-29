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
  
MAPI 子系统中的客户端应用程序会在收到的任何邮件中使用多个属性。 当传输提供程序将邮件引入 MAPI 时, 它应设置这些属性, 因为它是唯一具有必要信息的进程, 或者至少是信息的最佳来源。
  
建议提供程序在传入邮件中设置所有这些属性的值。
  
|**属性名称**|**说明**|
|:-----|:-----|
|**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |邮件的主题。  <br/> |
|**PR_BODY**([PidTagBody](pidtagbody-canonical-property.md))  <br/> |纯文本邮件文本。  <br/> |
|**PR_RTF_COMPRESSED**([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))  <br/> |压缩的 RTF 邮件文本。  <br/> |
|**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |邮件的传递日期和时间。  <br/> |
|**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |邮件原始发件人的显示名称。  <br/> |
|**PR_SENDER_ENTRYID**([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))  <br/> |邮件原始发件人的通讯簿条目。  <br/> |
|**PR_SENDER_SEARCH_KEY**([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))  <br/> |邮件原始发件人的通讯簿搜索键。  <br/> |
|**PR_CLIENT_SUBMIT_TIME**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))  <br/> |发件人的邮件客户端向其邮件系统提交邮件的时间。  <br/> |
|**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))  <br/> |用于发送的代表委派的名称。  <br/> |
|**PR_SENT_REPRESENTING_ENTRYID**([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))  <br/> |发送委派的通讯簿条目。  <br/> |
|**PR_SENT_REPRESENTING_SEARCH_KEY**([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))  <br/> |发送委派的通讯簿搜索关键字。  <br/> |
|**PR_RCVD_REPRESENTING_NAME**([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))  <br/> |用于接收的代表委派的名称。  <br/> |
|**PR_RCVD_REPRESENTING_ENTRYID**([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md))  <br/> |接收代理的通讯簿条目。  <br/> |
|**PR_RCVD_REPRESENTING_SEARCH_KEY**([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))  <br/> |接收代理的通讯簿搜索关键字。  <br/> |
|**PR_REPLY_RECIPIENT_NAMES**([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))  <br/> |委派收件人显示名称的列表, 用分号和空格 (";") 分隔。  <br/> |
|**PR_REPLY_RECIPIENT_ENTRIES**([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md))  <br/> |答复的已委派收件人列表。  <br/> |
|**PR_MESSAGE_TO_ME**([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))  <br/> |指示收件人专门指定为 "收件人" 收件人 (不在组中)。  <br/> |
|**PR_MESSAGE_CC_ME**([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))  <br/> |指示收件人专门指定为 "抄送" 收件人 (不在组中)。  <br/> |
|**PR_MESSAGE_RECIP_ME**([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))  <br/> |指示收件人专门指定为 "收件人"、"抄送" 或 "密件抄送" 收件人 (不在组中)。  <br/> |
   
没有明显映射的提供程序可以将**PR_SENT_REPRESENTING**组属性设置为与**PR_SENDER**组相同的值, 将**PR_RCVD_REPRESENTING**组属性设置为与 PR_RECEIVED_BY 相同的值。 **** 组, 并且可以根据**PR_SENDER**组的值生成**PR_REPLY_RECIPIENT**组的属性。 例如, **PR_SENT_REPRESENTING_NAME**可以设置为与**PR_SENDER_NAME**相同的值。
  
如有必要, 可以通过调用[IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md)方法来生成**PR_ENTRYID**或**PR_ENTRYLIST**属性。 可以通过将与用户关联的**PR_ADDRTYPE**属性、冒号 (:) 和与用户关联的**PR_EMAIL_ADDRESS**属性, 然后将结果更改为大写来生成属性的**PR_SEARCH_KEY**组。. Windows API 函数**CharUpperBuff**是用于此目的的一种方便的函数。 此过程所需的操作是, 对可以作为二进制数量进行比较的地址采用规范形式。 请注意, 如果传输提供程序对电子邮件地址而言区分大小写, 则不需要执行此步骤。 
  

