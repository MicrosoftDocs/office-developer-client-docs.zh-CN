---
title: IPM 子树
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b5fc6084-722d-44e8-8637-f4160a4fb19b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 92c7a09d9d608ac31920d49b20f78bedd26f5fcd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421219"
---
# <a name="ipm-subtree"></a><span data-ttu-id="137f2-103">IPM 子树</span><span class="sxs-lookup"><span data-stu-id="137f2-103">IPM Subtree</span></span>

  
  
<span data-ttu-id="137f2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="137f2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="137f2-105">MAPI 将在邮件存储区的根文件夹下创建一个文件夹树, 该树用于向人 (而不是计算机) 收件人发送邮件并从其接收邮件的所有客户端。</span><span class="sxs-lookup"><span data-stu-id="137f2-105">MAPI creates a tree of folders beneath the root folder of a message store for all clients that send messages to and receive messages from human, rather than computer, recipients.</span></span> <span data-ttu-id="137f2-106">在人类收件人之间交换的邮件称为 "人际邮件", 此树称为 "人际邮件" 或 "IPM" 子树。</span><span class="sxs-lookup"><span data-stu-id="137f2-106">Messages exchanged between human recipients are known as interpersonal messages, and this tree is known as the interpersonal message, or IPM, subtree.</span></span> 
  
<span data-ttu-id="137f2-107">传递存储区的 IPM 子树至少包含以下文件夹:</span><span class="sxs-lookup"><span data-stu-id="137f2-107">An IPM subtree for a delivery store consists of at least the following folders:</span></span>
  
- <span data-ttu-id="137f2-108">Inbox</span><span class="sxs-lookup"><span data-stu-id="137f2-108">Inbox</span></span>
    
- <span data-ttu-id="137f2-109">发件箱</span><span class="sxs-lookup"><span data-stu-id="137f2-109">Outbox</span></span>
    
- <span data-ttu-id="137f2-110">已发送邮件</span><span class="sxs-lookup"><span data-stu-id="137f2-110">Sent Items</span></span>
    
- <span data-ttu-id="137f2-111">已删除邮件</span><span class="sxs-lookup"><span data-stu-id="137f2-111">Deleted Items</span></span>
    
<span data-ttu-id="137f2-112">以下是这些文件夹中每个文件夹的默认名称和角色;如果默认名称不合适, 客户端可以指定其自己的名称。</span><span class="sxs-lookup"><span data-stu-id="137f2-112">These are the default names and roles for each of these folders; a client can specify its own names if the default names are not appropriate.</span></span> <span data-ttu-id="137f2-113">如果客户端在为邮件建立接收文件夹, 则 MAPI 会为这些文件夹分配默认名称和关联, 以防止无意中消失邮件。</span><span class="sxs-lookup"><span data-stu-id="137f2-113">MAPI assigns default names and associations for these folders to keep messages from inadvertently disappearing if a client neglects to establish receiving folders for messages.</span></span> 
  
<span data-ttu-id="137f2-114">在 Microsoft Office Outlook 上下文中, IPM 子树由日历、联系人、任务、便笺和日记的其他默认文件夹组成。</span><span class="sxs-lookup"><span data-stu-id="137f2-114">In a Microsoft Office Outlook context, an IPM subtree consists of additional default folders for Calendar, Contacts, Tasks, Notes, and Journal.</span></span>
  
<span data-ttu-id="137f2-115">"收件箱" 通常会保留传入的邮件, 而 "发件箱" 将保留传出邮件 (即等待发送的邮件)。</span><span class="sxs-lookup"><span data-stu-id="137f2-115">The Inbox typically holds incoming messages, and the Outbox holds outgoing messages (that is, messages waiting to be sent).</span></span> <span data-ttu-id="137f2-116">如果客户端将**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性设置为该文件夹的条目标识符, 则 "已发送邮件" 文件夹将保留每个已发送邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="137f2-116">The Sent Items folder holds a copy of each sent message if the client has set the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property to the entry identifier of this folder.</span></span> <span data-ttu-id="137f2-117">"已删除邮件" 文件夹包含标记为要删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="137f2-117">The Deleted Items folder contains messages marked for removal.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="137f2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="137f2-118">See also</span></span>



[<span data-ttu-id="137f2-119">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="137f2-119">MAPI Folders</span></span>](mapi-folders.md)

