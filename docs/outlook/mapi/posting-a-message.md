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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350748"
---
# <a name="posting-a-message"></a><span data-ttu-id="12eb0-103">发布邮件</span><span class="sxs-lookup"><span data-stu-id="12eb0-103">Posting a message</span></span>

<span data-ttu-id="12eb0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12eb0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12eb0-105">发布邮件类似于发送邮件。</span><span class="sxs-lookup"><span data-stu-id="12eb0-105">Posting a message is similar to sending a message.</span></span> <span data-ttu-id="12eb0-106">主要区别在于目标。</span><span class="sxs-lookup"><span data-stu-id="12eb0-106">The main difference is the destination.</span></span> <span data-ttu-id="12eb0-107">已发布的邮件仍保留在当前邮件存储区中的文件夹中, 而不是定向到一个或多个邮件系统上的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="12eb0-107">Rather than being directed to one or more recipients across one or more messaging systems, a posted message remains in a folder in the current message store.</span></span>
  
### <a name="to-post-a-message"></a><span data-ttu-id="12eb0-108">发布邮件</span><span class="sxs-lookup"><span data-stu-id="12eb0-108">To post a message</span></span>
  
1. <span data-ttu-id="12eb0-109">通过调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)打开目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="12eb0-109">Open the destination folder by calling [IMsgStore::OpenEntry](imsgstore-openentry.md).</span></span> <span data-ttu-id="12eb0-110">如果目标文件夹是收件箱, 则通过调用[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)找到要传递给**OpenEntry**的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="12eb0-110">If the destination folder is the Inbox, locate the entry identifier to pass to **OpenEntry** by calling [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md).</span></span> 
    
2. <span data-ttu-id="12eb0-111">调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)以创建邮件。</span><span class="sxs-lookup"><span data-stu-id="12eb0-111">Call [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) to create the message.</span></span> 
    
3. <span data-ttu-id="12eb0-112">调用要设置的邮件的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法:</span><span class="sxs-lookup"><span data-stu-id="12eb0-112">Call the message's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set:</span></span> 
    
   - <span data-ttu-id="12eb0-113">**PidTagMessageFlags** ( [PR_MESSAGE_FLAGS](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标志。</span><span class="sxs-lookup"><span data-stu-id="12eb0-113">The MSGFLAG_READ flag in the **PidTagMessageFlags** ( [PR_MESSAGE_FLAGS](pidtagmessageflags-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="12eb0-114">**PR_SENDER**属性。</span><span class="sxs-lookup"><span data-stu-id="12eb0-114">The **PR_SENDER** properties.</span></span> 
    
   - <span data-ttu-id="12eb0-115">**PR_SENT_REPRESENTING**属性。</span><span class="sxs-lookup"><span data-stu-id="12eb0-115">The **PR_SENT_REPRESENTING** properties.</span></span> 
    
   - <span data-ttu-id="12eb0-116">**PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="12eb0-116">The **PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="12eb0-117">**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="12eb0-117">The **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) or **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="12eb0-118">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="12eb0-118">The **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="12eb0-119">**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="12eb0-119">The **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span></span>
    
   - <span data-ttu-id="12eb0-120">邮件类所需的任何属性。</span><span class="sxs-lookup"><span data-stu-id="12eb0-120">Any properties required by the message class.</span></span>
    
4. <span data-ttu-id="12eb0-121">调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存该邮件。</span><span class="sxs-lookup"><span data-stu-id="12eb0-121">Call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save the message.</span></span> 
    
5. <span data-ttu-id="12eb0-122">如有必要, 请创建一个附件, 设置其属性, 然后保存它。</span><span class="sxs-lookup"><span data-stu-id="12eb0-122">If necessary, create an attachment, set its properties, and save it.</span></span> <span data-ttu-id="12eb0-123">有关将附件添加到邮件的详细信息, 请参阅[创建邮件附件](creating-a-message-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="12eb0-123">For more information about adding attachments to messages, see [Creating a Message Attachment](creating-a-message-attachment.md).</span></span>
    
6. <span data-ttu-id="12eb0-124">调用**IMessage:: SaveChanges**以保存邮件。</span><span class="sxs-lookup"><span data-stu-id="12eb0-124">Call **IMessage::SaveChanges** to save the message.</span></span> <span data-ttu-id="12eb0-125">此时, 它将显示在目标文件夹的 "内容" 表中。</span><span class="sxs-lookup"><span data-stu-id="12eb0-125">At this point it will appear in the contents table of the destination folder.</span></span> 
    
<span data-ttu-id="12eb0-126">请注意, 您不会创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="12eb0-126">Notice that you do not create a recipient list.</span></span> <span data-ttu-id="12eb0-127">而是设置多个通常由传输提供程序为已发送的邮件设置的属性。</span><span class="sxs-lookup"><span data-stu-id="12eb0-127">Instead, you set several properties that are normally set by a transport provider for a sent message.</span></span> 
  
<span data-ttu-id="12eb0-128">如果要在显示在可见文件夹的内容表中之前间歇保存邮件, 请在隐藏文件夹 (如 IPM 子树的根文件夹) 中创建邮件, 然后将其移动到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="12eb0-128">If you want to save a message intermittently before having it appear in the contents table of the visible folder, create it instead in a hidden folder such as the root folder of the IPM subtree and then move it to the target folder.</span></span> 
  

