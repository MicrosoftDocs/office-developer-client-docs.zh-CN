---
title: 转发邮件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0027fd5a-f30a-4025-b670-c21869b3a480
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d1df84c37cc2a24806c35ae0c90e4bf2a5e438d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433176"
---
# <a name="forwarding-a-message"></a><span data-ttu-id="286e2-103">转发邮件</span><span class="sxs-lookup"><span data-stu-id="286e2-103">Forwarding a message</span></span>

<span data-ttu-id="286e2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="286e2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="286e2-105">转发邮件涉及许多与发送原始邮件相同的任务。</span><span class="sxs-lookup"><span data-stu-id="286e2-105">Forwarding a message involves many of the same tasks as sending an original message.</span></span> <span data-ttu-id="286e2-106">首先，必须打开默认邮件存储和指定用于保留传出邮件的文件夹（通常为发件箱）并调用此文件夹的 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法以创建要转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="286e2-106">First, you must open the default message store and the folder that is designated to hold outgoing messages, typically the Outbox, and call this folder's [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method to create the message to be forwarded.</span></span> <span data-ttu-id="286e2-107">还必须打开保存原始邮件的文件夹，通常为"收件箱"。</span><span class="sxs-lookup"><span data-stu-id="286e2-107">You must also open the folder that holds the original message, typically the Inbox.</span></span> <span data-ttu-id="286e2-108">有关打开不同文件夹的信息，请参阅 [打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="286e2-108">For information about opening different folders, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
  
<span data-ttu-id="286e2-109">创建要转发的邮件和创建原始邮件之间的主要区别在于，对于转发的邮件，大多数属性都是基于原始邮件的属性或直接从原始邮件的属性复制的。</span><span class="sxs-lookup"><span data-stu-id="286e2-109">The main difference between creating a message to be forwarded and creating the original is that with a forwarded message, most of the properties are either based on or copied directly from properties of the original message.</span></span> 
  
<span data-ttu-id="286e2-110">**转发邮件**</span><span class="sxs-lookup"><span data-stu-id="286e2-110">**To forward a message**</span></span>
  
1. <span data-ttu-id="286e2-111">打开默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="286e2-111">Open the default message store.</span></span> <span data-ttu-id="286e2-112">有关详细信息，请参阅 [打开默认邮件存储](opening-the-default-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="286e2-112">For more information, see [Opening the Default Message Store](opening-the-default-message-store.md).</span></span>
    
2. <span data-ttu-id="286e2-113">打开发件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="286e2-113">Open the Outbox folder.</span></span> <span data-ttu-id="286e2-114">有关详细信息，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="286e2-114">For more information, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
    
3. <span data-ttu-id="286e2-115">调用发件箱的 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法以创建新的转发邮件。</span><span class="sxs-lookup"><span data-stu-id="286e2-115">Call the Outbox's [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method to create a new forwarded message.</span></span> 
    
4. <span data-ttu-id="286e2-116">调用原始邮件的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法将以下属性复制到转发的邮件：</span><span class="sxs-lookup"><span data-stu-id="286e2-116">Call the original message's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the following properties to the forwarded message:</span></span> 
    
   - <span data-ttu-id="286e2-117">**PR \_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 、PR **\_ HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 或 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) ，具体取决于您是否支持格式文本格式、纯文本或 HTML。</span><span class="sxs-lookup"><span data-stu-id="286e2-117">**PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), or **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)), depending on whether or not you support Rich Text Format, plain text, or HTML.</span></span>
    
   - <span data-ttu-id="286e2-118">**PR \_NORMALIZED_SUBJECT (** [PidTagNormalizedSubject)](pidtagnormalizedsubject-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="286e2-118">**PR\_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))</span></span> 
    
5. <span data-ttu-id="286e2-119">通过调用原始邮件的 **IMAPIProp：：CopyTo** 方法来复制 **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性，或者调用要复制的每个附件的以下三个步骤过程，从原始邮件复制邮件附件：</span><span class="sxs-lookup"><span data-stu-id="286e2-119">Copy the message attachments from the original message either by calling the original message's **IMAPIProp::CopyTo** method to copy the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property or by invoking the following three step procedure for each attachment to be copied:</span></span>
    
   1. <span data-ttu-id="286e2-120">调用新转发邮件的 [IMessage：：CreateAttach](imessage-createattach.md) 方法以创建新的附件。</span><span class="sxs-lookup"><span data-stu-id="286e2-120">Call the new forwarded message's [IMessage::CreateAttach](imessage-createattach.md) method to create a new attachment.</span></span> 
      
   2. <span data-ttu-id="286e2-121">调用原始邮件的 [IMessage：：OpenAttach](imessage-openattach.md) 方法打开要复制的附件。</span><span class="sxs-lookup"><span data-stu-id="286e2-121">Call the original message's [IMessage::OpenAttach](imessage-openattach.md) method to open the attachment to be copied.</span></span> 
      
   3. <span data-ttu-id="286e2-122">调用原始邮件的 **IMAPIProp：：CopyTo** 方法，将旧附件的所有附件属性复制到新附件。</span><span class="sxs-lookup"><span data-stu-id="286e2-122">Call the original message's **IMAPIProp::CopyTo** method to copy all of the attachment properties from the old attachment to the new one.</span></span> 
    
6. <span data-ttu-id="286e2-123">请勿在 **IMAPIProp：：CopyTo 调用中包括以下属性**：</span><span class="sxs-lookup"><span data-stu-id="286e2-123">Do not include the following properties in your call to **IMAPIProp::CopyTo**:</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="286e2-124">**PR_CLIENT_SUBMIT_TIME (** [PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="286e2-124">**PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="286e2-125">**PR_MESSAGE_DELIVERY_TIME (** [PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="286e2-125">**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="286e2-126">**PR_MESSAGE_DOWNLOAD_TIME (** [PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="286e2-126">**PR_MESSAGE_DOWNLOAD_TIME** ([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="286e2-127">**PR_MESSAGE_FLAGS (** [PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="286e2-127">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="286e2-128">**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED (** [PidTagOriginatorDeliveryReportRequested)](pidtagoriginatordeliveryreportrequested-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="286e2-128">**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="286e2-129">**PR_RCVD_REPRESENTING** 属性</span><span class="sxs-lookup"><span data-stu-id="286e2-129">**PR_RCVD_REPRESENTING** properties</span></span>  <br/> |
|<span data-ttu-id="286e2-130">**PR_READ_RECEIPT_ENTRYID (** [PidTagReadReceiptEntryId)](pidtagreadreceiptentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="286e2-130">**PR_READ_RECEIPT_ENTRYID** ([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="286e2-131">**PR_READ_RECEIPT_REQUESTED (** [PidTagReadReceiptRequested)](pidtagreadreceiptrequested-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="286e2-131">**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="286e2-132">**PR_RECEIVED_BY** 属性</span><span class="sxs-lookup"><span data-stu-id="286e2-132">**PR_RECEIVED_BY** properties</span></span>  <br/> |<span data-ttu-id="286e2-133">**PR_REPLY_RECIPIENT** 属性</span><span class="sxs-lookup"><span data-stu-id="286e2-133">**PR_REPLY_RECIPIENT** properties</span></span>  <br/> |
|<span data-ttu-id="286e2-134">**PR_REPORT_ENTRYID (** [PidTagReportEntryId)](pidtagreportentryid-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="286e2-134">**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="286e2-135">**PR_SENDER** 属性</span><span class="sxs-lookup"><span data-stu-id="286e2-135">**PR_SENDER** properties</span></span>  <br/> |
|<span data-ttu-id="286e2-136">**PR_SENT_REPRESENTING** 属性</span><span class="sxs-lookup"><span data-stu-id="286e2-136">**PR_SENT_REPRESENTING** properties</span></span>  <br/> |<span data-ttu-id="286e2-137">**PR_SENTMAIL_ENTRYID (** [PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="286e2-137">**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="286e2-138">**PR_SUBJECT_PREFIX (** [PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="286e2-138">**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))</span></span>  <br/> | <br/> |
   
1. <span data-ttu-id="286e2-139">通过添加缩进和包含原始发件人、传输日期、主题和收件人列表的头段落来设置邮件文本的格式。</span><span class="sxs-lookup"><span data-stu-id="286e2-139">Format the message text by adding indentation and a header paragraph that includes the original sender, date of transmission, subject, and recipient list.</span></span> <span data-ttu-id="286e2-140">请勿在内容中包括 Internet 样式的前缀字符。</span><span class="sxs-lookup"><span data-stu-id="286e2-140">Do not include Internet-style prefix characters with the content.</span></span>
    
2. <span data-ttu-id="286e2-141">调用 [ScCreateConversationIndex](sccreateconversationindex.md)，将原始邮件的 **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 值。</span><span class="sxs-lookup"><span data-stu-id="286e2-141">Call [ScCreateConversationIndex](sccreateconversationindex.md), passing in the value of the original message's **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) property.</span></span>
    
3. <span data-ttu-id="286e2-142">为转发的邮件设置前缀。</span><span class="sxs-lookup"><span data-stu-id="286e2-142">Set a prefix for the forwarded message.</span></span> <span data-ttu-id="286e2-143">如果使用标准"FW："，请连接这些字符到 PR_NORMALIZED_SUBJECT 开头 **，PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 此新字符串。 </span><span class="sxs-lookup"><span data-stu-id="286e2-143">If you are using the standard "FW:", concatenate these characters onto the beginning of **PR_NORMALIZED_SUBJECT** and set **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) to this new string.</span></span> <span data-ttu-id="286e2-144">请勿将 PR_SUBJECT_PREFIX **(** [PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="286e2-144">Do not set **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)).</span></span> <span data-ttu-id="286e2-145">如果使用非标准前缀（如长度超过三个字符的字符串），请存储在 **PR_SUBJECT_PREFIX。**</span><span class="sxs-lookup"><span data-stu-id="286e2-145">If you are using a nonstandard prefix, such as a string longer than three characters, store it in **PR_SUBJECT_PREFIX**.</span></span> 
    
4. <span data-ttu-id="286e2-146">将 **PR_SENT_REPRESENTING** 属性设置为活动属性 **中的PR_RCVD_REPRESENTING值** 。</span><span class="sxs-lookup"><span data-stu-id="286e2-146">Set the **PR_SENT_REPRESENTING** properties to the corresponding values in the **PR_RCVD_REPRESENTING** properties.</span></span> 
    
5. <span data-ttu-id="286e2-147">创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="286e2-147">Create a recipient list.</span></span> <span data-ttu-id="286e2-148">有关详细信息，请参阅创建 [收件人列表](creating-a-recipient-list.md)。</span><span class="sxs-lookup"><span data-stu-id="286e2-148">For more information, see [Creating a Recipient List](creating-a-recipient-list.md).</span></span>
    
6. <span data-ttu-id="286e2-149">调用转发的邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存它，或者 [调用 IMessage：：SubmitMessage](imessage-submitmessage.md) 保存并发送它。</span><span class="sxs-lookup"><span data-stu-id="286e2-149">Call the forwarded message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save it or [IMessage::SubmitMessage](imessage-submitmessage.md) to save and send it.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="286e2-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="286e2-150">See also</span></span>

- [<span data-ttu-id="286e2-151">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="286e2-151">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)

