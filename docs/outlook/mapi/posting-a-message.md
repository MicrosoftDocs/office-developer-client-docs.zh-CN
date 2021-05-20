---
title: 发布邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc3e1546-e58b-413f-82d7-4efeb86b0000
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2c174d48a19e23de725e1d5a1533130175f2ab00
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429766"
---
# <a name="posting-a-message"></a><span data-ttu-id="fdb9a-103">发布邮件</span><span class="sxs-lookup"><span data-stu-id="fdb9a-103">Posting a message</span></span>

<span data-ttu-id="fdb9a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fdb9a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fdb9a-105">发布邮件类似于发送邮件。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-105">Posting a message is similar to sending a message.</span></span> <span data-ttu-id="fdb9a-106">主要区别是目标。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-106">The main difference is the destination.</span></span> <span data-ttu-id="fdb9a-107">发布的邮件将保留在当前邮件存储中的文件夹中，而不是跨一个或多个邮件系统定向到一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-107">Rather than being directed to one or more recipients across one or more messaging systems, a posted message remains in a folder in the current message store.</span></span>
  
### <a name="to-post-a-message"></a><span data-ttu-id="fdb9a-108">发布消息</span><span class="sxs-lookup"><span data-stu-id="fdb9a-108">To post a message</span></span>
  
1. <span data-ttu-id="fdb9a-109">通过调用 [IMsgStore：：OpenEntry 打开目标文件夹](imsgstore-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-109">Open the destination folder by calling [IMsgStore::OpenEntry](imsgstore-openentry.md).</span></span> <span data-ttu-id="fdb9a-110">如果目标文件夹是收件箱，请通过调用 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md)找到要传递到 **OpenEntry** 的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-110">If the destination folder is the Inbox, locate the entry identifier to pass to **OpenEntry** by calling [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md).</span></span> 
    
2. <span data-ttu-id="fdb9a-111">调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 以创建消息。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-111">Call [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) to create the message.</span></span> 
    
3. <span data-ttu-id="fdb9a-112">调用消息的 [IMAPIProp：：SetProps 方法来](imapiprop-setprops.md) 设置：</span><span class="sxs-lookup"><span data-stu-id="fdb9a-112">Call the message's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set:</span></span> 
    
   - <span data-ttu-id="fdb9a-113">**PidTagMessageFlags MSGFLAG_READ PidTagMessageFlags** [ ( PR_MESSAGE_FLAGS)](pidtagmessageflags-canonical-property.md)标记。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-113">The MSGFLAG_READ flag in the **PidTagMessageFlags** ( [PR_MESSAGE_FLAGS](pidtagmessageflags-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="fdb9a-114">属性 **PR_SENDER** 属性。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-114">The **PR_SENDER** properties.</span></span> 
    
   - <span data-ttu-id="fdb9a-115">属性 **PR_SENT_REPRESENTING** 属性。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-115">The **PR_SENT_REPRESENTING** properties.</span></span> 
    
   - <span data-ttu-id="fdb9a-116">The **PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) property.</span><span class="sxs-lookup"><span data-stu-id="fdb9a-116">The **PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="fdb9a-117">The **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) or PR_BODY **(** [PidTagBody](pidtagbody-canonical-property.md)) property.</span><span class="sxs-lookup"><span data-stu-id="fdb9a-117">The **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) or **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="fdb9a-118">The **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span><span class="sxs-lookup"><span data-stu-id="fdb9a-118">The **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="fdb9a-119">The **PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span><span class="sxs-lookup"><span data-stu-id="fdb9a-119">The **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="fdb9a-120">邮件类所需的任何属性。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-120">Any properties required by the message class.</span></span>
    
4. <span data-ttu-id="fdb9a-121">调用邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存邮件。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-121">Call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save the message.</span></span> 
    
5. <span data-ttu-id="fdb9a-122">如有必要，创建附件、设置其属性并保存它。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-122">If necessary, create an attachment, set its properties, and save it.</span></span> <span data-ttu-id="fdb9a-123">有关向邮件添加附件的信息，请参阅 [创建邮件附件](creating-a-message-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-123">For more information about adding attachments to messages, see [Creating a Message Attachment](creating-a-message-attachment.md).</span></span>
    
6. <span data-ttu-id="fdb9a-124">调用 **IMessage：：SaveChanges** 以保存邮件。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-124">Call **IMessage::SaveChanges** to save the message.</span></span> <span data-ttu-id="fdb9a-125">此时，它将显示在目标文件夹的内容表中。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-125">At this point it will appear in the contents table of the destination folder.</span></span> 
    
<span data-ttu-id="fdb9a-126">请注意，您不会创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-126">Notice that you do not create a recipient list.</span></span> <span data-ttu-id="fdb9a-127">相反，您可以设置通常由传输提供程序为已发送的邮件设置的几个属性。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-127">Instead, you set several properties that are normally set by a transport provider for a sent message.</span></span> 
  
<span data-ttu-id="fdb9a-128">如果要在消息出现在可见文件夹的内容表中之前间歇性保存消息，请改为在隐藏文件夹（如 IPM 子树的根文件夹）中创建它，然后将它移动到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="fdb9a-128">If you want to save a message intermittently before having it appear in the contents table of the visible folder, create it instead in a hidden folder such as the root folder of the IPM subtree and then move it to the target folder.</span></span> 
  

