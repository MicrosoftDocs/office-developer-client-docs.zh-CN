---
title: 保存收件箱中的某封邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3df04d4e-7e80-4232-aadc-c05c99ab59cb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3c48ded73d924a400632a94feab65f7afca6e526
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778660"
---
# <a name="saving-a-message-in-the-inbox"></a><span data-ttu-id="80686-103">保存收件箱中的某封邮件</span><span class="sxs-lookup"><span data-stu-id="80686-103">Saving a Message in the Inbox</span></span>

  
  
<span data-ttu-id="80686-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="80686-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="80686-105">**若要在没有任何收件人的收件箱中存储一条消息**</span><span class="sxs-lookup"><span data-stu-id="80686-105">**To store a message in the Inbox without any recipients**</span></span>
  
1. <span data-ttu-id="80686-106">调用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)检索的收件箱的项标识符。</span><span class="sxs-lookup"><span data-stu-id="80686-106">Call [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) to retrieve the entry identifier of the Inbox.</span></span> 
    
2. <span data-ttu-id="80686-107">调用[IMsgStore::OpenEntry](imsgstore-openentry.md)打开收件箱并检索指向它的指针。</span><span class="sxs-lookup"><span data-stu-id="80686-107">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the Inbox and retrieve a pointer to it.</span></span> 
    
3. <span data-ttu-id="80686-108">调用收件箱的[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法来创建邮件。</span><span class="sxs-lookup"><span data-stu-id="80686-108">Call the Inbox's [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method to create the message.</span></span> 
    
4. <span data-ttu-id="80686-109">调用消息的[IMAPIProp::SetProps](imapiprop-setprops.md)方法来添加**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))、 **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 和**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="80686-109">Call the message's [IMAPIProp::SetProps](imapiprop-setprops.md) method to add the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), or **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) and **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) properties.</span></span> 
    
5. <span data-ttu-id="80686-110">创建每个附件，设置其属性，并将其保存。</span><span class="sxs-lookup"><span data-stu-id="80686-110">Create each attachment, set its properties, and save it.</span></span> <span data-ttu-id="80686-111">有关将附件添加到邮件的详细信息，请参阅[创建邮件附件](creating-a-message-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="80686-111">For detailed information about adding attachments to messages, see [Creating a Message Attachment](creating-a-message-attachment.md).</span></span>
    
6. <span data-ttu-id="80686-112">调用**IMessage::SaveChanges**保存邮件。</span><span class="sxs-lookup"><span data-stu-id="80686-112">Call **IMessage::SaveChanges** to save the message.</span></span> <span data-ttu-id="80686-113">此时将显示内容表的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="80686-113">At this point it will appear in the contents table of the Inbox.</span></span> 
    
<span data-ttu-id="80686-114">如果您希望让其出现在收件箱的内容表之前保存消息 intermittantly，改为在隐藏的文件夹，如 IPM 子树的根文件夹中创建它，然后将其移至收件箱。</span><span class="sxs-lookup"><span data-stu-id="80686-114">If you want to save a message intermittantly before having it appear in the contents table of the Inbox, create it instead in a hidden folder such as the root folder of the IPM subtree and then move it to the Inbox.</span></span> 
  

