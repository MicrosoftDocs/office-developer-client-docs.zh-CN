---
title: IPM 子树
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b5fc6084-722d-44e8-8637-f4160a4fb19b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6fe642d10a50d25874aee170441a07c184b46575
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591091"
---
# <a name="ipm-subtree"></a><span data-ttu-id="a394d-103">IPM 子树</span><span class="sxs-lookup"><span data-stu-id="a394d-103">IPM Subtree</span></span>

  
  
<span data-ttu-id="a394d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a394d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a394d-105">MAPI 的发送和接收来自 human，而不是计算机、 收件人的所有客户端创建下方的消息存储的根文件夹的文件夹的树。</span><span class="sxs-lookup"><span data-stu-id="a394d-105">MAPI creates a tree of folders beneath the root folder of a message store for all clients that send messages to and receive messages from human, rather than computer, recipients.</span></span> <span data-ttu-id="a394d-106">Human 收件人之间交换消息称为人际邮件和已知此树为人际邮件或 IPM，子树。</span><span class="sxs-lookup"><span data-stu-id="a394d-106">Messages exchanged between human recipients are known as interpersonal messages, and this tree is known as the interpersonal message, or IPM, subtree.</span></span> 
  
<span data-ttu-id="a394d-107">传递存储区的 IPM 子树包含至少以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="a394d-107">An IPM subtree for a delivery store consists of at least the following folders:</span></span>
  
- <span data-ttu-id="a394d-108">Inbox</span><span class="sxs-lookup"><span data-stu-id="a394d-108">Inbox</span></span>
    
- <span data-ttu-id="a394d-109">发件箱</span><span class="sxs-lookup"><span data-stu-id="a394d-109">Outbox</span></span>
    
- <span data-ttu-id="a394d-110">已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="a394d-110">Sent Items</span></span>
    
- <span data-ttu-id="a394d-111">已删除的项目</span><span class="sxs-lookup"><span data-stu-id="a394d-111">Deleted Items</span></span>
    
<span data-ttu-id="a394d-112">这些是默认名称和角色其中每个文件夹;如果默认名称不适当，客户端可以指定其自己的名称。</span><span class="sxs-lookup"><span data-stu-id="a394d-112">These are the default names and roles for each of these folders; a client can specify its own names if the default names are not appropriate.</span></span> <span data-ttu-id="a394d-113">MAPI 分配默认名称和这些文件夹能够从无意中消失如果客户端在建立的邮件的接收文件夹中保留邮件的关联。</span><span class="sxs-lookup"><span data-stu-id="a394d-113">MAPI assigns default names and associations for these folders to keep messages from inadvertently disappearing if a client neglects to establish receiving folders for messages.</span></span> 
  
<span data-ttu-id="a394d-114">在 Microsoft Office Outlook 上下文中，IPM 子树的日历、 联系人、 任务、 备注和日记包含其他默认文件夹。</span><span class="sxs-lookup"><span data-stu-id="a394d-114">In a Microsoft Office Outlook context, an IPM subtree consists of additional default folders for Calendar, Contacts, Tasks, Notes, and Journal.</span></span>
  
<span data-ttu-id="a394d-115">收件箱通常包含传入消息，并且发件箱保留传出消息 （即，等待发送的消息）。</span><span class="sxs-lookup"><span data-stu-id="a394d-115">The Inbox typically holds incoming messages, and the Outbox holds outgoing messages (that is, messages waiting to be sent).</span></span> <span data-ttu-id="a394d-116">已发送邮件文件夹包含每个已发送邮件的副本，如果客户端已将**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性设置为此文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="a394d-116">The Sent Items folder holds a copy of each sent message if the client has set the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property to the entry identifier of this folder.</span></span> <span data-ttu-id="a394d-117">已删除邮件文件夹包含标记为删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="a394d-117">The Deleted Items folder contains messages marked for removal.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a394d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a394d-118">See also</span></span>



[<span data-ttu-id="a394d-119">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="a394d-119">MAPI Folders</span></span>](mapi-folders.md)

