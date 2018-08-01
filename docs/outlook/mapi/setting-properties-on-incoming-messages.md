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
ms.openlocfilehash: f6233afffd532c420ae170ae45b1bf93d6571865
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778783"
---
# <a name="setting-properties-on-incoming-messages"></a>设置传入邮件的属性

  
  
**适用于**： Outlook 
  
MAPI 子系统中的客户端应用程序期望中接收的任何消息的属性数目。 当传输提供程序到 MAPI，将显示一条消息时，应设置这些属性，因为它是过程任一仅使用所需的信息，为此，请或至少是最佳源的信息。
  
鼓励设置接收的邮件中的所有这些属性的值将提供程序。
  
|**属性名称**|**说明**|
|:-----|:-----|
|**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |邮件的主题。  <br/> |
|**PR_BODY**([PidTagBody](pidtagbody-canonical-property.md))  <br/> |纯文本消息文本。  <br/> |
|**PR_RTF_COMPRESSED**([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))  <br/> |压缩的 RTF 消息文本。  <br/> |
|**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |日期和时间邮件已送达。  <br/> |
|**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |原始邮件发件人显示名称。  <br/> |
|**PR_SENDER_ENTRYID**([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))  <br/> |消息发起方的通讯簿条目。  <br/> |
|**PR_SENDER_SEARCH_KEY**([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))  <br/> |消息发起方的通讯簿搜索键。  <br/> |
|**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))  <br/> |邮件由发件人的邮件客户端已提交到其消息的系统时间。  <br/> |
|**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))  <br/> |发送代表性代理人的姓名。  <br/> |
|**PR_SENT_REPRESENTING_ENTRYID**([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md))  <br/> |发送委托通讯簿条目。  <br/> |
|**PR_SENT_REPRESENTING_SEARCH_KEY**([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))  <br/> |地址簿搜索关键字的发送的代理人。  <br/> |
|**PR_RCVD_REPRESENTING_NAME**([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))  <br/> |用于接收代表性代理人的姓名。  <br/> |
|**PR_RCVD_REPRESENTING_ENTRYID**([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md))  <br/> |接收委托通讯簿条目。  <br/> |
|**PR_RCVD_REPRESENTING_SEARCH_KEY**([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))  <br/> |地址簿搜索关键字的接收的代理人。  <br/> |
|**PR_REPLY_RECIPIENT_NAMES**([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))  <br/> |委派的收件人的列表显示由分号和空格分隔的名称 （";"）。  <br/> |
|**PR_REPLY_RECIPIENT_ENTRIES**([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md))  <br/> |委派的回复的收件人列表。  <br/> |
|**PR_MESSAGE_TO_ME**([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))  <br/> |指示收件人已专门命名为"目标"收件人 （不在一组）。  <br/> |
|**PR_MESSAGE_CC_ME**([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))  <br/> |指示收件人已专门命名为"抄送"收件人 （不在一组）。  <br/> |
|**PR_MESSAGE_RECIP_ME**([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))  <br/> |指示收件人为"目标"，特别是名为"抄送"或"密件抄送"收件人 （不在一组）。  <br/> |
   
不明显映射提供商可以将**PR_SENT_REPRESENTING**组属性设置为相同的值的**PR_SENDER**组中，属性设置为相同的值**PR_RECEIVED_BY **PR_RCVD_REPRESENTING**组**组，并可以生成的基于**PR_SENDER**组的值的属性**PR_REPLY_RECIPIENT**组。 例如， **PR_SENT_REPRESENTING_NAME**可以设置为**PR_SENDER_NAME**相同的值。
  
**PR_ENTRYID**或**PR_ENTRYLIST**属性可以生成，如有必要，通过调用[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)方法。 可以通过将与用户、 冒号 （:） 和与用户关联的**PR_EMAIL_ADDRESS**属性关联的**PR_ADDRTYPE**属性生成的属性**PR_SEARCH_KEY**组然后更改为大写形式的结果. Windows API 函数**CharUpperBuff**是一种方便的功能，用于实现此目的。 必须执行此过程的是使规范窗体可以作为二进制数量比较的地址。 注意，这是不必要传输提供程序是否区分大小写相对于电子邮件地址。 
  

