---
title: 在收件箱中保存邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3df04d4e-7e80-4232-aadc-c05c99ab59cb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 672a9df55ce711b88451a517a2813c9ad8c599ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407891"
---
# <a name="saving-a-message-in-the-inbox"></a><span data-ttu-id="d0a46-103">在收件箱中保存邮件</span><span class="sxs-lookup"><span data-stu-id="d0a46-103">Saving a Message in the Inbox</span></span>

  
  
<span data-ttu-id="d0a46-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d0a46-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="d0a46-105">**在收件箱中存储没有任何收件人的邮件**</span><span class="sxs-lookup"><span data-stu-id="d0a46-105">**To store a message in the Inbox without any recipients**</span></span>
  
1. <span data-ttu-id="d0a46-106">调用 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 检索收件箱的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d0a46-106">Call [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) to retrieve the entry identifier of the Inbox.</span></span> 
    
2. <span data-ttu-id="d0a46-107">调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 打开收件箱并检索指向它的指针。</span><span class="sxs-lookup"><span data-stu-id="d0a46-107">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the Inbox and retrieve a pointer to it.</span></span> 
    
3. <span data-ttu-id="d0a46-108">调用收件箱的 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法来创建邮件。</span><span class="sxs-lookup"><span data-stu-id="d0a46-108">Call the Inbox's [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method to create the message.</span></span> 
    
4. <span data-ttu-id="d0a46-109">调用邮件的 [IMAPIProp：：SetProps](imapiprop-setprops.md)方法以添加 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 、PR_HTML ([PidTagHtml](pidtaghtml-canonical-property.md)) 或 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 和 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="d0a46-109">Call the message's [IMAPIProp::SetProps](imapiprop-setprops.md) method to add the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), or **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) and **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) properties.</span></span> 
    
5. <span data-ttu-id="d0a46-110">创建每个附件，设置其属性并保存它。</span><span class="sxs-lookup"><span data-stu-id="d0a46-110">Create each attachment, set its properties, and save it.</span></span> <span data-ttu-id="d0a46-111">有关向邮件添加附件的详细信息，请参阅 [创建邮件附件](creating-a-message-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="d0a46-111">For detailed information about adding attachments to messages, see [Creating a Message Attachment](creating-a-message-attachment.md).</span></span>
    
6. <span data-ttu-id="d0a46-112">调用 **IMessage：：SaveChanges** 以保存邮件。</span><span class="sxs-lookup"><span data-stu-id="d0a46-112">Call **IMessage::SaveChanges** to save the message.</span></span> <span data-ttu-id="d0a46-113">此时，它将显示在"收件箱"的"内容"表中。</span><span class="sxs-lookup"><span data-stu-id="d0a46-113">At this point it will appear in the contents table of the Inbox.</span></span> 
    
<span data-ttu-id="d0a46-114">如果要在邮件显示在收件箱的内容表中之前，在隐藏文件夹中（如 IPM 子树的根文件夹）创建邮件，然后移动到收件箱。</span><span class="sxs-lookup"><span data-stu-id="d0a46-114">If you want to save a message intermittantly before having it appear in the contents table of the Inbox, create it instead in a hidden folder such as the root folder of the IPM subtree and then move it to the Inbox.</span></span> 
  

