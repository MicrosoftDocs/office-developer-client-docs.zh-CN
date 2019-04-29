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
  
RFC 822 标头映射到 MAPI 属性, 如下所示。 PR_SENDER_\*是以下5个属性的缩写:
  
 **PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))
  
 **PR_SENDER_ADDRTYPE**([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))
  
 **PR_SENDER_EMAIL_ADDRESS**([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))
  
 **PR_SENDER_SEARCH_KEY**([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))
  
 **PR_SENDER_ENTRYID**([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))
  
类似的缩写词用于 PR_SENT_REPRESENTING_\*和其他邮件属性组。
  
|**SMTP 头**|**MAPI 属性**|
|:-----|:-----|
|从：  <br/> |出站:\*PR_SENDER_;入站:\* PR_SENDER_ 和 PR_SENT_REPRESENTING_\*  <br/> |
|结束  <br/> |出站: 当前时间;入站: **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |
|自：  <br/> |**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), 适用于**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 为 MAPI_TO 的收件人  <br/> |
|收件人  <br/> |**PR_RECIPIENT_TYPE**为 MAPI_CC 的收件人的**PR_DISPLAY_NAME**和**PR_EMAIL_ADDRESS**  <br/> |
|相邻  <br/> |**PR_RECIPIENT_TYPE**为 MAPI_BCC 的收件人的**PR_DISPLAY_NAME**和**PR_EMAIL_ADDRESS**  <br/> |
|||
|收到  <br/> |无相应的 MAPI 属性;在此处放置本地主机名和组件名称  <br/> |
|退货收据-收件人:  <br/> |**PR_REPORT_NAME**([PidTagReportName](pidtagreportname-canonical-property.md)) 和**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))  <br/> |
|答复:  <br/> |**PR_REPLY_RECIPIENT_ENTRIES**([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和**PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))  <br/> |
|主题：  <br/> |**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))无特定长度限制。  <br/> |
|MIME 版本:  <br/> |始终为 "1.0"  <br/> |
|||
|X-MS-附件:  <br/> |用于与 MS Mail SMTP 网关兼容。 _filename size mm-dd-yyy hh: mm_Details。  <br/> |
|||
| _整个 SMTP 邮件信封_ <br/> |**PR_TRANSPORT_MESSAGE_HEADERS**([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))  <br/> |
|标头名称 TBD  <br/> |**PR_SEND_RICH_INFO**([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for 仅发件人。应使用 _The TBDheader 来确定发件人是否能够在答复中解释 TNEF 内容。  <br/> |
|MessageID  <br/> |**PR_TNEF_CORRELATION_KEY**([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))  <br/> |
|Content-type  <br/> |文本/纯文本或多部分/混合。 请参阅 "邮件内容" 部分。  <br/> |
   
X 毫秒-附件标头被格式化为四个标记, 由空格分隔:
  
 _名称大小日期时间_
  
第一个令牌是文件名, 其中可能包含嵌入的空格, 因此应在入站邮件上从右端对此标头进行分析。 大小, 以字节为单位。将日期设置为_mm-dd,_ 并将时间设置为_hh: mm。_
  
> [!NOTE]
> MessageID 不会映射到**PR_SEARCH_KEY** , 因为 SMTP 域对邮件标识符的格式有特定要求, 使得无法对任意 MAPI 邮件标识符进行编码。 而是将 MessageID 映射到**PR_TNEF_CORRELATION_KEY**。 此属性是传输定义的属性, 由发送出站邮件并由传输接收入站邮件使用的传输进行设置。 有关详细信息, 请参阅[开发启用 TNEF 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)。 
  

