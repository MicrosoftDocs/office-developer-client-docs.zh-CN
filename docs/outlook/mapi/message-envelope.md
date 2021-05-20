---
title: 邮件信封
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 613956da-c49b-4836-9fde-4601510e8b89
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ccd14244bf7ee76396dc239437ca19f080edb170
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427190"
---
# <a name="message-envelope"></a>邮件信封

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
RFC 822 标头映射到 MAPI 属性，如下所示。 PR_SENDER_ \* 是以下 5 个属性的缩写：
  
 **PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md)) 
  
 **PR_SENDER_ADDRTYPE (** [PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 
  
 **PR_SENDER_EMAIL_ADDRESS (** [PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) 
  
 **PR_SENDER_SEARCH_KEY (** [PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)) 
  
 **PR_SENDER_ENTRYID (** [PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 
  
类似的缩写用于邮件PR_SENT_REPRESENTING_ \* 其他邮件属性组。
  
|**SMTP 头**|**MAPI 属性**|
|:-----|:-----|
|从：  <br/> |出站 \* ：PR_SENDER_;入站：PR_SENDER_ \* 和PR_SENT_REPRESENTING_\*  <br/> |
|日期：  <br/> |出站：当前时间;inbound： **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))   <br/> |
|自：  <br/> |**PR_DISPLAY_NAME (** [PidTagRecipientType](pidtagdisplayname-canonical-property.md)) 的收件人PR_EMAIL_ADDRESS ( [PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) PR_RECIPIENT_TYPE [ (PidTagRecipientType](pidtagrecipienttype-canonical-property.md) ) MAPI_TO  <br/> |
|抄送：  <br/> |**PR_DISPLAY_NAME PR_EMAIL_ADDRESS** 收件人的 **PR_RECIPIENT_TYPE和MAPI_CC**  <br/> |
|Bcc：  <br/> |**PR_DISPLAY_NAME PR_EMAIL_ADDRESS** 收件人的 **PR_RECIPIENT_TYPE和MAPI_BCC**  <br/> |
|||
|已接收：  <br/> |没有相应的 MAPI 属性;将本地主机名和组件名称放在此处  <br/> |
|Return-receipt-to：  <br/> |**PR_REPORT_NAME (** [PidTagReportName](pidtagreportname-canonical-property.md) **)** PR_REPORT_ENTRYID ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))   <br/> |
|答复：  <br/> |**PR_REPLY_RECIPIENT_ENTRIES (** [PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和 **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))   <br/> |
|主题：  <br/> |**PR_SUBJECT (** [PidTagSubject](pidtagsubject-canonical-property.md)) 没有特定长度限制。  <br/> |
|MIME-version：  <br/> |始终为"1.0"  <br/> |
|||
|X-MS-Attachment：  <br/> |为了与 MS 邮件 SMTP 网关兼容。 _filename尺寸 mm-dd-yyy hh：mm_Details以下。  <br/> |
|||
| _整个 SMTP 邮件信封_ <br/> |**PR_TRANSPORT_MESSAGE_HEADERS (** [PidTagTransportMessageHeaders)](pidtagtransportmessageheaders-canonical-property.md)  <br/> |
|标头名称 TBD  <br/> |**PR_SEND_RICH_INFO (** [PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for sender only._The TBDheader 来确定发件人是否可以在回复中解释 TNEF 内容。  <br/> |
|MessageID：  <br/> |**PR_TNEF_CORRELATION_KEY (** [PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))   <br/> |
|Content-type  <br/> |文本/纯文本或多部分/混合。 请参阅"邮件内容"部分。  <br/> |
   
X-MS-Attachment 标头的格式设置为四个标记，用空格分隔：
  
 _名称大小日期时间_
  
第一个标记是可能包含嵌入空格的文件名，因此应从入站邮件的右侧分析此标头。 大小以字节为单位;日期的格式设置为  _mm-dd-yyyyy，_ 时间设置为  _hh：mm。_
  
> [!NOTE]
> MessageID 未映射到 PR_SEARCH_KEY因为 SMTP 域对邮件标识符的格式有特定要求，因此无法对任意 MAPI 邮件标识符进行编码。 相反，MessageID 会映射到 **PR_TNEF_CORRELATION_KEY**。 此属性是传输定义的属性，由发送出站邮件的传输设置，由接收入站邮件的传输使用。 有关详细信息，请参阅开发 [传输TNEF-Enabled提供程序](developing-a-tnef-enabled-transport-provider.md)。 
  

