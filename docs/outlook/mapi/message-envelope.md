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
# <a name="message-envelope"></a><span data-ttu-id="71ecf-103">邮件信封</span><span class="sxs-lookup"><span data-stu-id="71ecf-103">Message Envelope</span></span>

  
  
<span data-ttu-id="71ecf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="71ecf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="71ecf-105">RFC 822 标头映射到 MAPI 属性，如下所示。</span><span class="sxs-lookup"><span data-stu-id="71ecf-105">RFC 822 headers are mapped to MAPI properties as follows.</span></span> <span data-ttu-id="71ecf-106">PR_SENDER_ \* 是以下 5 个属性的缩写：</span><span class="sxs-lookup"><span data-stu-id="71ecf-106">PR_SENDER_\* is an abbreviation for the following 5 properties:</span></span>
  
 <span data-ttu-id="71ecf-107">**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-107">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>
  
 <span data-ttu-id="71ecf-108">**PR_SENDER_ADDRTYPE (** [PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-108">**PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))</span></span>
  
 <span data-ttu-id="71ecf-109">**PR_SENDER_EMAIL_ADDRESS (** [PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-109">**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))</span></span>
  
 <span data-ttu-id="71ecf-110">**PR_SENDER_SEARCH_KEY (** [PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-110">**PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))</span></span>
  
 <span data-ttu-id="71ecf-111">**PR_SENDER_ENTRYID (** [PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-111">**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))</span></span>
  
<span data-ttu-id="71ecf-112">类似的缩写用于邮件PR_SENT_REPRESENTING_ \* 其他邮件属性组。</span><span class="sxs-lookup"><span data-stu-id="71ecf-112">Similar abbreviations are used for PR_SENT_REPRESENTING_\* and other groups of message properties.</span></span>
  
|<span data-ttu-id="71ecf-113">**SMTP 头**</span><span class="sxs-lookup"><span data-stu-id="71ecf-113">**SMTP header**</span></span>|<span data-ttu-id="71ecf-114">**MAPI 属性**</span><span class="sxs-lookup"><span data-stu-id="71ecf-114">**MAPI property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="71ecf-115">从：</span><span class="sxs-lookup"><span data-stu-id="71ecf-115">From:</span></span>  <br/> |<span data-ttu-id="71ecf-116">出站 \* ：PR_SENDER_;入站：PR_SENDER_ \* 和PR_SENT_REPRESENTING_\*</span><span class="sxs-lookup"><span data-stu-id="71ecf-116">Outbound: PR_SENDER_\*; inbound: PR_SENDER_\* and PR_SENT_REPRESENTING_\*</span></span>  <br/> |
|<span data-ttu-id="71ecf-117">日期：</span><span class="sxs-lookup"><span data-stu-id="71ecf-117">Date:</span></span>  <br/> |<span data-ttu-id="71ecf-118">出站：当前时间;inbound： **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-118">Outbound: current time; inbound: **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="71ecf-119">自：</span><span class="sxs-lookup"><span data-stu-id="71ecf-119">To:</span></span>  <br/> |<span data-ttu-id="71ecf-120">**PR_DISPLAY_NAME (** [PidTagRecipientType](pidtagdisplayname-canonical-property.md)) 的收件人PR_EMAIL_ADDRESS ( [PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) PR_RECIPIENT_TYPE [ (PidTagRecipientType](pidtagrecipienttype-canonical-property.md) ) MAPI_TO</span><span class="sxs-lookup"><span data-stu-id="71ecf-120">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) and **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) for recipients where **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) is MAPI_TO</span></span>  <br/> |
|<span data-ttu-id="71ecf-121">抄送：</span><span class="sxs-lookup"><span data-stu-id="71ecf-121">Cc:</span></span>  <br/> |<span data-ttu-id="71ecf-122">**PR_DISPLAY_NAME PR_EMAIL_ADDRESS** 收件人的 **PR_RECIPIENT_TYPE和MAPI_CC**</span><span class="sxs-lookup"><span data-stu-id="71ecf-122">**PR_DISPLAY_NAME** and **PR_EMAIL_ADDRESS** for recipients where **PR_RECIPIENT_TYPE** is MAPI_CC</span></span>  <br/> |
|<span data-ttu-id="71ecf-123">Bcc：</span><span class="sxs-lookup"><span data-stu-id="71ecf-123">Bcc:</span></span>  <br/> |<span data-ttu-id="71ecf-124">**PR_DISPLAY_NAME PR_EMAIL_ADDRESS** 收件人的 **PR_RECIPIENT_TYPE和MAPI_BCC**</span><span class="sxs-lookup"><span data-stu-id="71ecf-124">**PR_DISPLAY_NAME** and **PR_EMAIL_ADDRESS** for recipients where **PR_RECIPIENT_TYPE** is MAPI_BCC</span></span>  <br/> |
|||
|<span data-ttu-id="71ecf-125">已接收：</span><span class="sxs-lookup"><span data-stu-id="71ecf-125">Received:</span></span>  <br/> |<span data-ttu-id="71ecf-126">没有相应的 MAPI 属性;将本地主机名和组件名称放在此处</span><span class="sxs-lookup"><span data-stu-id="71ecf-126">No corresponding MAPI property; put local host name and your component name here</span></span>  <br/> |
|<span data-ttu-id="71ecf-127">Return-receipt-to：</span><span class="sxs-lookup"><span data-stu-id="71ecf-127">Return-receipt-to:</span></span>  <br/> |<span data-ttu-id="71ecf-128">**PR_REPORT_NAME (** [PidTagReportName](pidtagreportname-canonical-property.md) **)** PR_REPORT_ENTRYID ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-128">**PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) and **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="71ecf-129">答复：</span><span class="sxs-lookup"><span data-stu-id="71ecf-129">Reply-to:</span></span>  <br/> |<span data-ttu-id="71ecf-130">**PR_REPLY_RECIPIENT_ENTRIES (** [PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和 **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-130">**PR_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) and **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="71ecf-131">主题：</span><span class="sxs-lookup"><span data-stu-id="71ecf-131">Subject:</span></span>  <br/> |<span data-ttu-id="71ecf-132">**PR_SUBJECT (** [PidTagSubject](pidtagsubject-canonical-property.md)) 没有特定长度限制。</span><span class="sxs-lookup"><span data-stu-id="71ecf-132">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) No particular length limitation.</span></span>  <br/> |
|<span data-ttu-id="71ecf-133">MIME-version：</span><span class="sxs-lookup"><span data-stu-id="71ecf-133">MIME-version:</span></span>  <br/> |<span data-ttu-id="71ecf-134">始终为"1.0"</span><span class="sxs-lookup"><span data-stu-id="71ecf-134">Always "1.0"</span></span>  <br/> |
|||
|<span data-ttu-id="71ecf-135">X-MS-Attachment：</span><span class="sxs-lookup"><span data-stu-id="71ecf-135">X-MS-Attachment:</span></span>  <br/> |<span data-ttu-id="71ecf-136">为了与 MS 邮件 SMTP 网关兼容。</span><span class="sxs-lookup"><span data-stu-id="71ecf-136">For compatibility with MS Mail SMTP gateway.</span></span> <span data-ttu-id="71ecf-137">_filename尺寸 mm-dd-yyy hh：mm_Details以下。</span><span class="sxs-lookup"><span data-stu-id="71ecf-137">_filename size mm-dd-yyy hh:mm_Details below.</span></span>  <br/> |
|||
| <span data-ttu-id="71ecf-138">_整个 SMTP 邮件信封_</span><span class="sxs-lookup"><span data-stu-id="71ecf-138">_entire SMTP message envelope_</span></span> <br/> |<span data-ttu-id="71ecf-139">**PR_TRANSPORT_MESSAGE_HEADERS (** [PidTagTransportMessageHeaders)](pidtagtransportmessageheaders-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="71ecf-139">**PR_TRANSPORT_MESSAGE_HEADERS** ([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="71ecf-140">标头名称 TBD</span><span class="sxs-lookup"><span data-stu-id="71ecf-140">header name TBD</span></span>  <br/> |<span data-ttu-id="71ecf-141">**PR_SEND_RICH_INFO (** [PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for sender only._The TBDheader 来确定发件人是否可以在回复中解释 TNEF 内容。</span><span class="sxs-lookup"><span data-stu-id="71ecf-141">**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for sender only._The TBDheader should be used to determine whether the sender is capable of interpreting TNEF content in a reply.</span></span>  <br/> |
|<span data-ttu-id="71ecf-142">MessageID：</span><span class="sxs-lookup"><span data-stu-id="71ecf-142">MessageID:</span></span>  <br/> |<span data-ttu-id="71ecf-143">**PR_TNEF_CORRELATION_KEY (** [PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="71ecf-143">**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="71ecf-144">Content-type</span><span class="sxs-lookup"><span data-stu-id="71ecf-144">Content-type</span></span>  <br/> |<span data-ttu-id="71ecf-145">文本/纯文本或多部分/混合。</span><span class="sxs-lookup"><span data-stu-id="71ecf-145">Either text/plain or multipart/mixed.</span></span> <span data-ttu-id="71ecf-146">请参阅"邮件内容"部分。</span><span class="sxs-lookup"><span data-stu-id="71ecf-146">See "Message Content" section.</span></span>  <br/> |
   
<span data-ttu-id="71ecf-147">X-MS-Attachment 标头的格式设置为四个标记，用空格分隔：</span><span class="sxs-lookup"><span data-stu-id="71ecf-147">The X-MS-Attachment header is formatted as four tokens, separated by a space:</span></span>
  
 <span data-ttu-id="71ecf-148">_名称大小日期时间_</span><span class="sxs-lookup"><span data-stu-id="71ecf-148">_name size date time_</span></span>
  
<span data-ttu-id="71ecf-149">第一个标记是可能包含嵌入空格的文件名，因此应从入站邮件的右侧分析此标头。</span><span class="sxs-lookup"><span data-stu-id="71ecf-149">The first token is the filename, which may contain embedded spaces, so this header should be parsed from the right on inbound messages.</span></span> <span data-ttu-id="71ecf-150">大小以字节为单位;日期的格式设置为  _mm-dd-yyyyy，_ 时间设置为  _hh：mm。_</span><span class="sxs-lookup"><span data-stu-id="71ecf-150">The size is in bytes; the date is formatted as  _mm-dd-yyyy,_ and the time as  _hh:mm._</span></span>
  
> [!NOTE]
> <span data-ttu-id="71ecf-151">MessageID 未映射到 PR_SEARCH_KEY因为 SMTP 域对邮件标识符的格式有特定要求，因此无法对任意 MAPI 邮件标识符进行编码。</span><span class="sxs-lookup"><span data-stu-id="71ecf-151">MessageID is not mapped to **PR_SEARCH_KEY** because the SMTP domain has specific requirements on the format of the message identifier which make it impossible to encode an arbitrary MAPI message identifier.</span></span> <span data-ttu-id="71ecf-152">相反，MessageID 会映射到 **PR_TNEF_CORRELATION_KEY**。</span><span class="sxs-lookup"><span data-stu-id="71ecf-152">Instead, MessageID is mapped to **PR_TNEF_CORRELATION_KEY**.</span></span> <span data-ttu-id="71ecf-153">此属性是传输定义的属性，由发送出站邮件的传输设置，由接收入站邮件的传输使用。</span><span class="sxs-lookup"><span data-stu-id="71ecf-153">This property is a transport-defined property that is set by the transport sending an outbound message and used by a transport receiving an inbound message.</span></span> <span data-ttu-id="71ecf-154">有关详细信息，请参阅开发 [传输TNEF-Enabled提供程序](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="71ecf-154">For more information, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span> 
  

