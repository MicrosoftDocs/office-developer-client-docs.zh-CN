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
ms.openlocfilehash: 146c8b4d711982118fd9da185a5b095a1bae6b2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774982"
---
# <a name="forwarding-a-message"></a><span data-ttu-id="5e3ad-103">转发邮件</span><span class="sxs-lookup"><span data-stu-id="5e3ad-103">Forwarding a message</span></span>

<span data-ttu-id="5e3ad-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5e3ad-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5e3ad-105">转发邮件涉及多个与发送原始邮件相同的任务。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-105">Forwarding a message involves many of the same tasks as sending an original message.</span></span> <span data-ttu-id="5e3ad-106">首先，必须打开默认的邮件存储和指定用于保存传出消息，通常箱文件夹，并调用此文件夹[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法来创建邮件转发。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-106">First, you must open the default message store and the folder that is designated to hold outgoing messages, typically the Outbox, and call this folder's [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method to create the message to be forwarded.</span></span> <span data-ttu-id="5e3ad-107">您还必须打开包含原始邮件，通常收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-107">You must also open the folder that holds the original message, typically the Inbox.</span></span> <span data-ttu-id="5e3ad-108">有关打开不同的文件夹的信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-108">For information about opening different folders, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
  
<span data-ttu-id="5e3ad-109">创建要转接的消息和创建原始的主要区别是，转发邮件、 大部分属性是基于或复制直接从原始邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-109">The main difference between creating a message to be forwarded and creating the original is that with a forwarded message, most of the properties are either based on or copied directly from properties of the original message.</span></span> 
  
<span data-ttu-id="5e3ad-110">**转发邮件**</span><span class="sxs-lookup"><span data-stu-id="5e3ad-110">**To forward a message**</span></span>
  
1. <span data-ttu-id="5e3ad-111">打开默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-111">Open the default message store.</span></span> <span data-ttu-id="5e3ad-112">有关详细信息，请参阅[打开默认邮件存储区](opening-the-default-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-112">For more information, see [Opening the Default Message Store](opening-the-default-message-store.md).</span></span>
    
2. <span data-ttu-id="5e3ad-113">打开发件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-113">Open the Outbox folder.</span></span> <span data-ttu-id="5e3ad-114">有关详细信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-114">For more information, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span>
    
3. <span data-ttu-id="5e3ad-115">调用发件箱的[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法，以创建新的转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-115">Call the Outbox's [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method to create a new forwarded message.</span></span> 
    
4. <span data-ttu-id="5e3ad-116">调用原始消息的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法复制到转发邮件的以下属性：</span><span class="sxs-lookup"><span data-stu-id="5e3ad-116">Call the original message's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the following properties to the forwarded message:</span></span> 
    
   - <span data-ttu-id="5e3ad-117">**PR\_正文**([PidTagBody](pidtagbody-canonical-property.md))， **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))，具体取决于您是否支持富文本格式、 纯文本或 HTML。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-117">**PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), or **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)), depending on whether or not you support Rich Text Format, plain text, or HTML.</span></span>
    
   - <span data-ttu-id="5e3ad-118">**PR\_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-118">**PR\_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))</span></span> 
    
5. <span data-ttu-id="5e3ad-119">通过调用原始消息的**IMAPIProp::CopyTo**方法复制的**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性或通过调用下列从原始邮件复制邮件附件每个附件要复制的三个步骤过程：</span><span class="sxs-lookup"><span data-stu-id="5e3ad-119">Copy the message attachments from the original message either by calling the original message's **IMAPIProp::CopyTo** method to copy the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property or by invoking the following three step procedure for each attachment to be copied:</span></span>
    
   1. <span data-ttu-id="5e3ad-120">调用新的转发邮件的[IMessage::CreateAttach](imessage-createattach.md)方法创建一个新附件。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-120">Call the new forwarded message's [IMessage::CreateAttach](imessage-createattach.md) method to create a new attachment.</span></span> 
      
   2. <span data-ttu-id="5e3ad-121">调用原始消息的[IMessage::OpenAttach](imessage-openattach.md)方法以打开要复制的附件。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-121">Call the original message's [IMessage::OpenAttach](imessage-openattach.md) method to open the attachment to be copied.</span></span> 
      
   3. <span data-ttu-id="5e3ad-122">调用原始消息的**IMAPIProp::CopyTo**方法复制的所有附件属性到新的旧附件。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-122">Call the original message's **IMAPIProp::CopyTo** method to copy all of the attachment properties from the old attachment to the new one.</span></span> 
    
6. <span data-ttu-id="5e3ad-123">**IMAPIProp::CopyTo**到呼叫中不包括以下属性：</span><span class="sxs-lookup"><span data-stu-id="5e3ad-123">Do not include the following properties in your call to **IMAPIProp::CopyTo**:</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="5e3ad-124">**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-124">**PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5e3ad-125">**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-125">**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="5e3ad-126">**PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-126">**PR_MESSAGE_DOWNLOAD_TIME** ([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5e3ad-127">**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-127">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="5e3ad-128">**邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-128">**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5e3ad-129">**PR_RCVD_REPRESENTING**属性</span><span class="sxs-lookup"><span data-stu-id="5e3ad-129">**PR_RCVD_REPRESENTING** properties</span></span>  <br/> |
|<span data-ttu-id="5e3ad-130">**PR_READ_RECEIPT_ENTRYID**([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-130">**PR_READ_RECEIPT_ENTRYID** ([PidTagReadReceiptEntryId](pidtagreadreceiptentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5e3ad-131">**PR_READ_RECEIPT_REQUESTED**([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-131">**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="5e3ad-132">**PR_RECEIVED_BY**属性</span><span class="sxs-lookup"><span data-stu-id="5e3ad-132">**PR_RECEIVED_BY** properties</span></span>  <br/> |<span data-ttu-id="5e3ad-133">**PR_REPLY_RECIPIENT**属性</span><span class="sxs-lookup"><span data-stu-id="5e3ad-133">**PR_REPLY_RECIPIENT** properties</span></span>  <br/> |
|<span data-ttu-id="5e3ad-134">**PR_REPORT_ENTRYID**([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-134">**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5e3ad-135">**PR_SENDER**属性</span><span class="sxs-lookup"><span data-stu-id="5e3ad-135">**PR_SENDER** properties</span></span>  <br/> |
|<span data-ttu-id="5e3ad-136">**PR_SENT_REPRESENTING**属性</span><span class="sxs-lookup"><span data-stu-id="5e3ad-136">**PR_SENT_REPRESENTING** properties</span></span>  <br/> |<span data-ttu-id="5e3ad-137">**PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-137">**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="5e3ad-138">**PR_SUBJECT_PREFIX**([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5e3ad-138">**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))</span></span>  <br/> | <br/> |
   
1. <span data-ttu-id="5e3ad-139">通过添加缩进和包含原始发件人，标头段落格式的消息文本的传输、 主题和收件人列表的日期。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-139">Format the message text by adding indentation and a header paragraph that includes the original sender, date of transmission, subject, and recipient list.</span></span> <span data-ttu-id="5e3ad-140">不包含内容的 Internet 风格前缀字符。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-140">Do not include Internet-style prefix characters with the content.</span></span>
    
2. <span data-ttu-id="5e3ad-141">调用[ScCreateConversationIndex](sccreateconversationindex.md)，传递中原始消息的**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-141">Call [ScCreateConversationIndex](sccreateconversationindex.md), passing in the value of the original message's **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) property.</span></span>
    
3. <span data-ttu-id="5e3ad-142">设置转发邮件的前缀。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-142">Set a prefix for the forwarded message.</span></span> <span data-ttu-id="5e3ad-143">如果您使用的是标准"FW:"连接到的**PR_NORMALIZED_SUBJECT**开头这些字符和将**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 设置为此新字符串。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-143">If you are using the standard "FW:", concatenate these characters onto the beginning of **PR_NORMALIZED_SUBJECT** and set **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) to this new string.</span></span> <span data-ttu-id="5e3ad-144">未设置**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-144">Do not set **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)).</span></span> <span data-ttu-id="5e3ad-145">如果您使用非标准前缀，例如 string 超过三个字符，则将其存储在**PR_SUBJECT_PREFIX**。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-145">If you are using a nonstandard prefix, such as a string longer than three characters, store it in **PR_SUBJECT_PREFIX**.</span></span> 
    
4. <span data-ttu-id="5e3ad-146">设置为**PR_RCVD_REPRESENTING**属性中的相应值的**PR_SENT_REPRESENTING**属性。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-146">Set the **PR_SENT_REPRESENTING** properties to the corresponding values in the **PR_RCVD_REPRESENTING** properties.</span></span> 
    
5. <span data-ttu-id="5e3ad-147">创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-147">Create a recipient list.</span></span> <span data-ttu-id="5e3ad-148">有关详细信息，请参阅[创建收件人列表](creating-a-recipient-list.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-148">For more information, see [Creating a Recipient List](creating-a-recipient-list.md).</span></span>
    
6. <span data-ttu-id="5e3ad-149">调用转发的邮件[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以保存它或者[IMessage::SubmitMessage](imessage-submitmessage.md)以保存并发送它。</span><span class="sxs-lookup"><span data-stu-id="5e3ad-149">Call the forwarded message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save it or [IMessage::SubmitMessage](imessage-submitmessage.md) to save and send it.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="5e3ad-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e3ad-150">See also</span></span>

- [<span data-ttu-id="5e3ad-151">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="5e3ad-151">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)

