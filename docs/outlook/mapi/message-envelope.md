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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356922"
---
# <a name="message-envelope"></a><span data-ttu-id="8d65b-103">邮件信封</span><span class="sxs-lookup"><span data-stu-id="8d65b-103">Message Envelope</span></span>

  
  
<span data-ttu-id="8d65b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8d65b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8d65b-105">RFC 822 标头映射到 MAPI 属性, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="8d65b-105">RFC 822 headers are mapped to MAPI properties as follows.</span></span> <span data-ttu-id="8d65b-106">PR_SENDER_\*是以下5个属性的缩写:</span><span class="sxs-lookup"><span data-stu-id="8d65b-106">PR_SENDER_\* is an abbreviation for the following 5 properties:</span></span>
  
 <span data-ttu-id="8d65b-107">**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-107">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>
  
 <span data-ttu-id="8d65b-108">**PR_SENDER_ADDRTYPE**([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-108">**PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))</span></span>
  
 <span data-ttu-id="8d65b-109">**PR_SENDER_EMAIL_ADDRESS**([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-109">**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))</span></span>
  
 <span data-ttu-id="8d65b-110">**PR_SENDER_SEARCH_KEY**([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-110">**PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))</span></span>
  
 <span data-ttu-id="8d65b-111">**PR_SENDER_ENTRYID**([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-111">**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))</span></span>
  
<span data-ttu-id="8d65b-112">类似的缩写词用于 PR_SENT_REPRESENTING_\*和其他邮件属性组。</span><span class="sxs-lookup"><span data-stu-id="8d65b-112">Similar abbreviations are used for PR_SENT_REPRESENTING_\* and other groups of message properties.</span></span>
  
|<span data-ttu-id="8d65b-113">**SMTP 头**</span><span class="sxs-lookup"><span data-stu-id="8d65b-113">**SMTP header**</span></span>|<span data-ttu-id="8d65b-114">**MAPI 属性**</span><span class="sxs-lookup"><span data-stu-id="8d65b-114">**MAPI property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d65b-115">从：</span><span class="sxs-lookup"><span data-stu-id="8d65b-115">From:</span></span>  <br/> |<span data-ttu-id="8d65b-116">出站:\*PR_SENDER_;入站:\* PR_SENDER_ 和 PR_SENT_REPRESENTING_\*</span><span class="sxs-lookup"><span data-stu-id="8d65b-116">Outbound: PR_SENDER_\*; inbound: PR_SENDER_\* and PR_SENT_REPRESENTING_\*</span></span>  <br/> |
|<span data-ttu-id="8d65b-117">结束</span><span class="sxs-lookup"><span data-stu-id="8d65b-117">Date:</span></span>  <br/> |<span data-ttu-id="8d65b-118">出站: 当前时间;入站: **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-118">Outbound: current time; inbound: **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="8d65b-119">自：</span><span class="sxs-lookup"><span data-stu-id="8d65b-119">To:</span></span>  <br/> |<span data-ttu-id="8d65b-120">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), 适用于**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 为 MAPI_TO 的收件人</span><span class="sxs-lookup"><span data-stu-id="8d65b-120">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) and **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) for recipients where **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) is MAPI_TO</span></span>  <br/> |
|<span data-ttu-id="8d65b-121">收件人</span><span class="sxs-lookup"><span data-stu-id="8d65b-121">Cc:</span></span>  <br/> |<span data-ttu-id="8d65b-122">**PR_RECIPIENT_TYPE**为 MAPI_CC 的收件人的**PR_DISPLAY_NAME**和**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="8d65b-122">**PR_DISPLAY_NAME** and **PR_EMAIL_ADDRESS** for recipients where **PR_RECIPIENT_TYPE** is MAPI_CC</span></span>  <br/> |
|<span data-ttu-id="8d65b-123">相邻</span><span class="sxs-lookup"><span data-stu-id="8d65b-123">Bcc:</span></span>  <br/> |<span data-ttu-id="8d65b-124">**PR_RECIPIENT_TYPE**为 MAPI_BCC 的收件人的**PR_DISPLAY_NAME**和**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="8d65b-124">**PR_DISPLAY_NAME** and **PR_EMAIL_ADDRESS** for recipients where **PR_RECIPIENT_TYPE** is MAPI_BCC</span></span>  <br/> |
|||
|<span data-ttu-id="8d65b-125">收到</span><span class="sxs-lookup"><span data-stu-id="8d65b-125">Received:</span></span>  <br/> |<span data-ttu-id="8d65b-126">无相应的 MAPI 属性;在此处放置本地主机名和组件名称</span><span class="sxs-lookup"><span data-stu-id="8d65b-126">No corresponding MAPI property; put local host name and your component name here</span></span>  <br/> |
|<span data-ttu-id="8d65b-127">退货收据-收件人:</span><span class="sxs-lookup"><span data-stu-id="8d65b-127">Return-receipt-to:</span></span>  <br/> |<span data-ttu-id="8d65b-128">**PR_REPORT_NAME**([PidTagReportName](pidtagreportname-canonical-property.md)) 和**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-128">**PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) and **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="8d65b-129">答复:</span><span class="sxs-lookup"><span data-stu-id="8d65b-129">Reply-to:</span></span>  <br/> |<span data-ttu-id="8d65b-130">**PR_REPLY_RECIPIENT_ENTRIES**([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和**PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-130">**PR_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) and **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="8d65b-131">主题：</span><span class="sxs-lookup"><span data-stu-id="8d65b-131">Subject:</span></span>  <br/> |<span data-ttu-id="8d65b-132">**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))无特定长度限制。</span><span class="sxs-lookup"><span data-stu-id="8d65b-132">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) No particular length limitation.</span></span>  <br/> |
|<span data-ttu-id="8d65b-133">MIME 版本:</span><span class="sxs-lookup"><span data-stu-id="8d65b-133">MIME-version:</span></span>  <br/> |<span data-ttu-id="8d65b-134">始终为 "1.0"</span><span class="sxs-lookup"><span data-stu-id="8d65b-134">Always "1.0"</span></span>  <br/> |
|||
|<span data-ttu-id="8d65b-135">X-MS-附件:</span><span class="sxs-lookup"><span data-stu-id="8d65b-135">X-MS-Attachment:</span></span>  <br/> |<span data-ttu-id="8d65b-136">用于与 MS Mail SMTP 网关兼容。</span><span class="sxs-lookup"><span data-stu-id="8d65b-136">For compatibility with MS Mail SMTP gateway.</span></span> <span data-ttu-id="8d65b-137">_filename size mm-dd-yyy hh: mm_Details。</span><span class="sxs-lookup"><span data-stu-id="8d65b-137">_filename size mm-dd-yyy hh:mm_Details below.</span></span>  <br/> |
|||
| <span data-ttu-id="8d65b-138">_整个 SMTP 邮件信封_</span><span class="sxs-lookup"><span data-stu-id="8d65b-138">_entire SMTP message envelope_</span></span> <br/> |<span data-ttu-id="8d65b-139">**PR_TRANSPORT_MESSAGE_HEADERS**([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-139">**PR_TRANSPORT_MESSAGE_HEADERS** ([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="8d65b-140">标头名称 TBD</span><span class="sxs-lookup"><span data-stu-id="8d65b-140">header name TBD</span></span>  <br/> |<span data-ttu-id="8d65b-141">**PR_SEND_RICH_INFO**([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for 仅发件人。应使用 _The TBDheader 来确定发件人是否能够在答复中解释 TNEF 内容。</span><span class="sxs-lookup"><span data-stu-id="8d65b-141">**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for sender only._The TBDheader should be used to determine whether the sender is capable of interpreting TNEF content in a reply.</span></span>  <br/> |
|<span data-ttu-id="8d65b-142">MessageID</span><span class="sxs-lookup"><span data-stu-id="8d65b-142">MessageID:</span></span>  <br/> |<span data-ttu-id="8d65b-143">**PR_TNEF_CORRELATION_KEY**([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8d65b-143">**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="8d65b-144">Content-type</span><span class="sxs-lookup"><span data-stu-id="8d65b-144">Content-type</span></span>  <br/> |<span data-ttu-id="8d65b-145">文本/纯文本或多部分/混合。</span><span class="sxs-lookup"><span data-stu-id="8d65b-145">Either text/plain or multipart/mixed.</span></span> <span data-ttu-id="8d65b-146">请参阅 "邮件内容" 部分。</span><span class="sxs-lookup"><span data-stu-id="8d65b-146">See "Message Content" section.</span></span>  <br/> |
   
<span data-ttu-id="8d65b-147">X 毫秒-附件标头被格式化为四个标记, 由空格分隔:</span><span class="sxs-lookup"><span data-stu-id="8d65b-147">The X-MS-Attachment header is formatted as four tokens, separated by a space:</span></span>
  
 <span data-ttu-id="8d65b-148">_名称大小日期时间_</span><span class="sxs-lookup"><span data-stu-id="8d65b-148">_name size date time_</span></span>
  
<span data-ttu-id="8d65b-149">第一个令牌是文件名, 其中可能包含嵌入的空格, 因此应在入站邮件上从右端对此标头进行分析。</span><span class="sxs-lookup"><span data-stu-id="8d65b-149">The first token is the filename, which may contain embedded spaces, so this header should be parsed from the right on inbound messages.</span></span> <span data-ttu-id="8d65b-150">大小, 以字节为单位。将日期设置为_mm-dd,_ 并将时间设置为_hh: mm。_</span><span class="sxs-lookup"><span data-stu-id="8d65b-150">The size is in bytes; the date is formatted as  _mm-dd-yyyy,_ and the time as  _hh:mm._</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d65b-151">MessageID 不会映射到**PR_SEARCH_KEY** , 因为 SMTP 域对邮件标识符的格式有特定要求, 使得无法对任意 MAPI 邮件标识符进行编码。</span><span class="sxs-lookup"><span data-stu-id="8d65b-151">MessageID is not mapped to **PR_SEARCH_KEY** because the SMTP domain has specific requirements on the format of the message identifier which make it impossible to encode an arbitrary MAPI message identifier.</span></span> <span data-ttu-id="8d65b-152">而是将 MessageID 映射到**PR_TNEF_CORRELATION_KEY**。</span><span class="sxs-lookup"><span data-stu-id="8d65b-152">Instead, MessageID is mapped to **PR_TNEF_CORRELATION_KEY**.</span></span> <span data-ttu-id="8d65b-153">此属性是传输定义的属性, 由发送出站邮件并由传输接收入站邮件使用的传输进行设置。</span><span class="sxs-lookup"><span data-stu-id="8d65b-153">This property is a transport-defined property that is set by the transport sending an outbound message and used by a transport receiving an inbound message.</span></span> <span data-ttu-id="8d65b-154">有关详细信息, 请参阅[开发启用 TNEF 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="8d65b-154">For more information, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span> 
  

