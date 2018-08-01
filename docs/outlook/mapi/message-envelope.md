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
ms.openlocfilehash: bbdc5993a07209f381065ce1b60f860ba54c35d5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776517"
---
# <a name="message-envelope"></a><span data-ttu-id="3e4d4-103">邮件信封</span><span class="sxs-lookup"><span data-stu-id="3e4d4-103">Message Envelope</span></span>

  
  
<span data-ttu-id="3e4d4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3e4d4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3e4d4-105">RFC 822 标头映射到 MAPI 属性，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-105">RFC 822 headers are mapped to MAPI properties as follows.</span></span> <span data-ttu-id="3e4d4-106">PR_SENDER_\*是缩写 5 的以下属性：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-106">PR_SENDER_\* is an abbreviation for the following 5 properties:</span></span>
  
 <span data-ttu-id="3e4d4-107">**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-107">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>
  
 <span data-ttu-id="3e4d4-108">**PR_SENDER_ADDRTYPE**([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-108">**PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))</span></span>
  
 <span data-ttu-id="3e4d4-109">**PR_SENDER_EMAIL_ADDRESS**([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-109">**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))</span></span>
  
 <span data-ttu-id="3e4d4-110">**PR_SENDER_SEARCH_KEY**([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-110">**PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))</span></span>
  
 <span data-ttu-id="3e4d4-111">**PR_SENDER_ENTRYID**([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-111">**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))</span></span>
  
<span data-ttu-id="3e4d4-112">类似缩写用于 PR_SENT_REPRESENTING_\*和其他组的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-112">Similar abbreviations are used for PR_SENT_REPRESENTING_\* and other groups of message properties.</span></span>
  
|<span data-ttu-id="3e4d4-113">**SMTP 标题**</span><span class="sxs-lookup"><span data-stu-id="3e4d4-113">**SMTP header**</span></span>|<span data-ttu-id="3e4d4-114">**MAPI 属性**</span><span class="sxs-lookup"><span data-stu-id="3e4d4-114">**MAPI property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e4d4-115">从：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-115">From:</span></span>  <br/> |<span data-ttu-id="3e4d4-116">出站： PR_SENDER_\*;入站： PR_SENDER_\*和 PR_SENT_REPRESENTING_\*</span><span class="sxs-lookup"><span data-stu-id="3e4d4-116">Outbound: PR_SENDER_\*; inbound: PR_SENDER_\* and PR_SENT_REPRESENTING_\*</span></span>  <br/> |
|<span data-ttu-id="3e4d4-117">日期：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-117">Date:</span></span>  <br/> |<span data-ttu-id="3e4d4-118">出站： 当前时间;入站： **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-118">Outbound: current time; inbound: **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="3e4d4-119">自：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-119">To:</span></span>  <br/> |<span data-ttu-id="3e4d4-120">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 收件人其中**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 是 MAPI_TO</span><span class="sxs-lookup"><span data-stu-id="3e4d4-120">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) and **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) for recipients where **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) is MAPI_TO</span></span>  <br/> |
|<span data-ttu-id="3e4d4-121">抄送:</span><span class="sxs-lookup"><span data-stu-id="3e4d4-121">Cc:</span></span>  <br/> |<span data-ttu-id="3e4d4-122">**PR_DISPLAY_NAME**和**PR_EMAIL_ADDRESS**其中**PR_RECIPIENT_TYPE**是 MAPI_CC 收件人</span><span class="sxs-lookup"><span data-stu-id="3e4d4-122">**PR_DISPLAY_NAME** and **PR_EMAIL_ADDRESS** for recipients where **PR_RECIPIENT_TYPE** is MAPI_CC</span></span>  <br/> |
|<span data-ttu-id="3e4d4-123">密件抄送：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-123">Bcc:</span></span>  <br/> |<span data-ttu-id="3e4d4-124">**PR_DISPLAY_NAME**和**PR_EMAIL_ADDRESS**其中**PR_RECIPIENT_TYPE**是 MAPI_BCC 收件人</span><span class="sxs-lookup"><span data-stu-id="3e4d4-124">**PR_DISPLAY_NAME** and **PR_EMAIL_ADDRESS** for recipients where **PR_RECIPIENT_TYPE** is MAPI_BCC</span></span>  <br/> |
|||
|<span data-ttu-id="3e4d4-125">接收：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-125">Received:</span></span>  <br/> |<span data-ttu-id="3e4d4-126">没有相应的 MAPI 属性;在此处输入本地主机名和组件名称</span><span class="sxs-lookup"><span data-stu-id="3e4d4-126">No corresponding MAPI property; put local host name and your component name here</span></span>  <br/> |
|<span data-ttu-id="3e4d4-127">返回-要回执：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-127">Return-receipt-to:</span></span>  <br/> |<span data-ttu-id="3e4d4-128">**PR_REPORT_NAME**([PidTagReportName](pidtagreportname-canonical-property.md)) 和**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-128">**PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) and **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="3e4d4-129">答复到：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-129">Reply-to:</span></span>  <br/> |<span data-ttu-id="3e4d4-130">**PR_REPLY_RECIPIENT_ENTRIES**([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和**PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-130">**PR_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) and **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="3e4d4-131">主题：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-131">Subject:</span></span>  <br/> |<span data-ttu-id="3e4d4-132">**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))没有特定的长度限制。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-132">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) No particular length limitation.</span></span>  <br/> |
|<span data-ttu-id="3e4d4-133">MIME 的版本：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-133">MIME-version:</span></span>  <br/> |<span data-ttu-id="3e4d4-134">始终"1.0"</span><span class="sxs-lookup"><span data-stu-id="3e4d4-134">Always "1.0"</span></span>  <br/> |
|||
|<span data-ttu-id="3e4d4-135">X MS 附件：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-135">X-MS-Attachment:</span></span>  <br/> |<span data-ttu-id="3e4d4-136">与 MS 邮件 SMTP 网关的兼容性。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-136">For compatibility with MS Mail SMTP gateway.</span></span> <span data-ttu-id="3e4d4-137">_filename 大小 mm-dd-yyy hh:mm_Details 下面。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-137">_filename size mm-dd-yyy hh:mm_Details below.</span></span>  <br/> |
|||
| <span data-ttu-id="3e4d4-138">_整个 SMTP 邮件信封_</span><span class="sxs-lookup"><span data-stu-id="3e4d4-138">_entire SMTP message envelope_</span></span> <br/> |<span data-ttu-id="3e4d4-139">**PR_TRANSPORT_MESSAGE_HEADERS**([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-139">**PR_TRANSPORT_MESSAGE_HEADERS** ([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="3e4d4-140">标头名称 TBD</span><span class="sxs-lookup"><span data-stu-id="3e4d4-140">header name TBD</span></span>  <br/> |<span data-ttu-id="3e4d4-141">**PR_SEND_RICH_INFO**([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for 发件人仅._The TBDheader 用于确定发件人是否能够解释 TNEF 回复中的内容。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-141">**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) _for sender only._The TBDheader should be used to determine whether the sender is capable of interpreting TNEF content in a reply.</span></span>  <br/> |
|<span data-ttu-id="3e4d4-142">MessageID:</span><span class="sxs-lookup"><span data-stu-id="3e4d4-142">MessageID:</span></span>  <br/> |<span data-ttu-id="3e4d4-143">**PR_TNEF_CORRELATION_KEY**([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e4d4-143">**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="3e4d4-144">Content-type</span><span class="sxs-lookup"><span data-stu-id="3e4d4-144">Content-type</span></span>  <br/> |<span data-ttu-id="3e4d4-145">Text/plain 或多部分/混合。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-145">Either text/plain or multipart/mixed.</span></span> <span data-ttu-id="3e4d4-146">请参阅"消息内容"部分。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-146">See "Message Content" section.</span></span>  <br/> |
   
<span data-ttu-id="3e4d4-147">X-MS 附件标头的格式设置为四个令牌，由空格分隔：</span><span class="sxs-lookup"><span data-stu-id="3e4d4-147">The X-MS-Attachment header is formatted as four tokens, separated by a space:</span></span>
  
 <span data-ttu-id="3e4d4-148">_命名大小日期时间_</span><span class="sxs-lookup"><span data-stu-id="3e4d4-148">_name size date time_</span></span>
  
<span data-ttu-id="3e4d4-149">第一个标记的文件名，可能包含嵌入的空格，因此应从右上入站邮件分析此标头。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-149">The first token is the filename, which may contain embedded spaces, so this header should be parsed from the right on inbound messages.</span></span> <span data-ttu-id="3e4d4-150">以字节为单位; 后的大小日期的格式设置为_月-日-年_，将时间作为_hh: mm。_</span><span class="sxs-lookup"><span data-stu-id="3e4d4-150">The size is in bytes; the date is formatted as  _mm-dd-yyyy,_ and the time as  _hh:mm._</span></span>
  
> [!NOTE]
> <span data-ttu-id="3e4d4-151">MessageID 未映射到**PR_SEARCH_KEY**因为 SMTP 域都有特定格式的要求的消息标识符进行不可能进行编码任意 MAPI 消息标识符。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-151">MessageID is not mapped to **PR_SEARCH_KEY** because the SMTP domain has specific requirements on the format of the message identifier which make it impossible to encode an arbitrary MAPI message identifier.</span></span> <span data-ttu-id="3e4d4-152">而是 MessageID 映射到**PR_TNEF_CORRELATION_KEY**。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-152">Instead, MessageID is mapped to **PR_TNEF_CORRELATION_KEY**.</span></span> <span data-ttu-id="3e4d4-153">此属性是一个传输定义的属性来发送出站邮件传输设置和使用接收的入站的邮件传输。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-153">This property is a transport-defined property that is set by the transport sending an outbound message and used by a transport receiving an inbound message.</span></span> <span data-ttu-id="3e4d4-154">有关详细信息，请参阅[开发 TNEF-Enabled 传输提供程序](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="3e4d4-154">For more information, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span> 
  

