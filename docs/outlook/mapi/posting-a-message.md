---
title: 发布一条消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc3e1546-e58b-413f-82d7-4efeb86b0000
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 33bf6780979ee25739abf93d89744e1517363c63
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778561"
---
# <a name="posting-a-message"></a><span data-ttu-id="0cd1a-103">发布一条消息</span><span class="sxs-lookup"><span data-stu-id="0cd1a-103">Posting a message</span></span>

<span data-ttu-id="0cd1a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0cd1a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0cd1a-105">发送一条消息是类似于发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-105">Posting a message is similar to sending a message.</span></span> <span data-ttu-id="0cd1a-106">主要区别是目标。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-106">The main difference is the destination.</span></span> <span data-ttu-id="0cd1a-107">而不是正在跨一个或多个邮件系统定向到一个或多个收件人，已发布的消息仍保留在当前消息存储的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-107">Rather than being directed to one or more recipients across one or more messaging systems, a posted message remains in a folder in the current message store.</span></span>
  
### <a name="to-post-a-message"></a><span data-ttu-id="0cd1a-108">若要发布消息</span><span class="sxs-lookup"><span data-stu-id="0cd1a-108">To post a message</span></span>
  
1. <span data-ttu-id="0cd1a-109">通过调用[IMsgStore::OpenEntry](imsgstore-openentry.md)打开目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-109">Open the destination folder by calling [IMsgStore::OpenEntry](imsgstore-openentry.md).</span></span> <span data-ttu-id="0cd1a-110">如果目标文件夹收件箱，找到要传递给**OpenEntry**通过调用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)的项标识符。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-110">If the destination folder is the Inbox, locate the entry identifier to pass to **OpenEntry** by calling [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md).</span></span> 
    
2. <span data-ttu-id="0cd1a-111">调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)创建邮件。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-111">Call [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) to create the message.</span></span> 
    
3. <span data-ttu-id="0cd1a-112">呼叫消息的[IMAPIProp::SetProps](imapiprop-setprops.md)方法，以便设置：</span><span class="sxs-lookup"><span data-stu-id="0cd1a-112">Call the message's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set:</span></span> 
    
   - <span data-ttu-id="0cd1a-113">**PidTagMessageFlags** ( [PR_MESSAGE_FLAGS](pidtagmessageflags-canonical-property.md)) 属性中 MSGFLAG_READ 标志。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-113">The MSGFLAG_READ flag in the **PidTagMessageFlags** ( [PR_MESSAGE_FLAGS](pidtagmessageflags-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="0cd1a-114">**PR_SENDER**属性。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-114">The **PR_SENDER** properties.</span></span> 
    
   - <span data-ttu-id="0cd1a-115">**PR_SENT_REPRESENTING**属性。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-115">The **PR_SENT_REPRESENTING** properties.</span></span> 
    
   - <span data-ttu-id="0cd1a-116">**PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-116">The **PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="0cd1a-117">**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-117">The **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) or **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="0cd1a-118">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-118">The **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="0cd1a-119">**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-119">The **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="0cd1a-120">所需的邮件类的任何属性。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-120">Any properties required by the message class.</span></span>
    
4. <span data-ttu-id="0cd1a-121">调用消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以保存邮件。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-121">Call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save the message.</span></span> 
    
5. <span data-ttu-id="0cd1a-122">如有必要，创建附件，设置其属性，并将其保存。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-122">If necessary, create an attachment, set its properties, and save it.</span></span> <span data-ttu-id="0cd1a-123">有关将附件添加到邮件的详细信息，请参阅[创建邮件附件](creating-a-message-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-123">For more information about adding attachments to messages, see [Creating a Message Attachment](creating-a-message-attachment.md).</span></span>
    
6. <span data-ttu-id="0cd1a-124">调用**IMessage::SaveChanges**保存邮件。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-124">Call **IMessage::SaveChanges** to save the message.</span></span> <span data-ttu-id="0cd1a-125">此时将显示在内容中的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-125">At this point it will appear in the contents table of the destination folder.</span></span> 
    
<span data-ttu-id="0cd1a-126">请注意，未创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-126">Notice that you do not create a recipient list.</span></span> <span data-ttu-id="0cd1a-127">相反，您可以设置通常设置为已发送的邮件传输提供程序的多个属性。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-127">Instead, you set several properties that are normally set by a transport provider for a sent message.</span></span> 
  
<span data-ttu-id="0cd1a-128">如果您想要让其出现在内容表中的可见文件夹之前间歇性保存一条消息，而是在隐藏的文件夹，如 IPM 子树的根文件夹中创建它，并将其移动到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="0cd1a-128">If you want to save a message intermittently before having it appear in the contents table of the visible folder, create it instead in a hidden folder such as the root folder of the IPM subtree and then move it to the target folder.</span></span> 
  

