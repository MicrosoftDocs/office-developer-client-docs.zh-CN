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
ms.openlocfilehash: fd642575a3136eef3193e0bdbe884cf8f54ba337
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571295"
---
# <a name="message-envelope"></a>邮件信封

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
RFC 822 标头映射到 MAPI 属性，如下所示。 PR_SENDER_\*是缩写 5 的以下属性：
  
 **PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))
  
 **PR_SENDER_ADDRTYPE**([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))
  
 **PR_SENDER_EMAIL_ADDRESS**([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))
  
 **PR_SENDER_SEARCH_KEY**([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))
  
 **PR_SENDER_ENTRYID**([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))
  
类似缩写用于 PR_SENT_REPRESENTING_\*和其他组的邮件属性。
  
|**SMTP 标题**|**MAPI 属性**|
|:-----|:-----|
|从：  <br/> |出站： PR_SENDER_\*;入站： PR_SENDER_\*和 PR_SENT_REPRESENTING_\*  <br/> |
|日期：  <br/> |出站： 当前时间;入站： **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |
|自：  <br/> |**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 收件人其中**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 是 MAPI_TO  <br/> |
|抄送:  <br/> |**PR_DISPLAY_NAME**和**PR_EMAIL_ADDRESS**其中**PR_RECIPIENT_TYPE**是 MAPI_CC 收件人  <br/> |
|密件抄送：  <br/> |**PR_DISPLAY_NAME**和**PR_EMAIL_ADDRESS**其中**PR_RECIPIENT_TYPE**是 MAPI_BCC 收件人  <br/> |
|||
|接收：  <br/> |没有相应的 MAPI 属性;在此处输入本地主机名和组件名称  <br/> |
|返回-要回执：  <br/> |**PR_REPORT_NAME**([PidTagReportName](pidtagreportname-canonical-property.md)) 和**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))  <br/> |
|答复到：  <br/> |**PR_REPLY_RECIPIENT_ENTRIES**([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和**PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))  <br/> |
|主题：  <br/> |**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))没有特定的长度限制。  <br/> |
|MIME 的版本：  <br/> |始终"1.0"  <br/> |
|||
|X MS 附件：  <br/> |与 MS 邮件 SMTP 网关的兼容性。 _filename 大小 mm-dd-yyy hh:mm_Details 下面。  <br/> |
|||
| _整个 SMTP 邮件信封_ <br/> |**PR_TRANSPORT_MESSAGE_HEADERS**([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))  <br/> |
|标头名称 TBD  <br/> |**PR_SEND_RICH_INFO**([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for 发件人仅._The TBDheader 用于确定发件人是否能够解释 TNEF 回复中的内容。  <br/> |
|MessageID:  <br/> |**PR_TNEF_CORRELATION_KEY**([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))  <br/> |
|Content-type  <br/> |Text/plain 或多部分/混合。 请参阅"消息内容"部分。  <br/> |
   
X-MS 附件标头的格式设置为四个令牌，由空格分隔：
  
 _命名大小日期时间_
  
第一个标记的文件名，可能包含嵌入的空格，因此应从右上入站邮件分析此标头。 以字节为单位; 后的大小日期的格式设置为_月-日-年_，将时间作为_hh: mm。_
  
> [!NOTE]
> MessageID 未映射到**PR_SEARCH_KEY**因为 SMTP 域都有特定格式的要求的消息标识符进行不可能进行编码任意 MAPI 消息标识符。 而是 MessageID 映射到**PR_TNEF_CORRELATION_KEY**。 此属性是一个传输定义的属性来发送出站邮件传输设置和使用接收的入站的邮件传输。 有关详细信息，请参阅[开发 TNEF-Enabled 传输提供程序](developing-a-tnef-enabled-transport-provider.md)。 
  

