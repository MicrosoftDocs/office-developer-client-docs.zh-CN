---
title: 选择接收文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 144c7179-b390-479f-a2aa-324974f04eba
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a4245b5dd1b70d4cf695190c65b447cf92566ef7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574480"
---
# <a name="selecting-a-receive-folder"></a><span data-ttu-id="dba85-103">选择接收文件夹</span><span class="sxs-lookup"><span data-stu-id="dba85-103">Selecting a Receive Folder</span></span>

  
  
<span data-ttu-id="dba85-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dba85-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dba85-105">接收文件夹是特定类的传入消息的放置位置。</span><span class="sxs-lookup"><span data-stu-id="dba85-105">A receive folder is where incoming messages of a particular class are placed.</span></span> <span data-ttu-id="dba85-106">有关 IPM 和相关的报告消息，MAPI 分配收件箱，如默认的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-106">For IPM and related report messages, MAPI assigns the Inbox as the default receive folder.</span></span> <span data-ttu-id="dba85-107">有关 IPC 和相关的报告消息，MAPI 分配消息存储库的根文件夹，如默认的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-107">For IPC and related report messages, MAPI assigns the root folder of the message store as the default receive folder.</span></span> <span data-ttu-id="dba85-108">您可以更改这些分配或进行的其他邮件类的其他工作分配。</span><span class="sxs-lookup"><span data-stu-id="dba85-108">You can change these assignments or make additional assignments for other message classes.</span></span> <span data-ttu-id="dba85-109">为您的客户端的支持的类是可选的消息进行显式接收文件夹工作分配。</span><span class="sxs-lookup"><span data-stu-id="dba85-109">Making explicit receive folder assignments for your client's supported message classes is optional.</span></span>
  
<span data-ttu-id="dba85-110">当传入的邮件类不具有已分配的接收文件夹时，消息存储提供程序类相匹配的传入类可能的最长前缀自动使用的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-110">When an incoming message class does not have an assigned receive folder, the message store provider automatically uses the receive folder for the class that matches the longest possible prefix of the incoming class.</span></span> <span data-ttu-id="dba85-111">例如，如果您的客户端接收的邮件类 IPM。Note.MyDocument 和仅接收已建立的文件夹的 IPM 邮件收件箱，此消息将放置在收件箱，因为 IPM。Note.MyDocument 派生自基类 IPM。</span><span class="sxs-lookup"><span data-stu-id="dba85-111">For example, if your client receives a message of class IPM.Note.MyDocument and the only receive folder that has been established is the Inbox for IPM messages, this message will be placed in the Inbox because IPM.Note.MyDocument derives from the base class IPM.</span></span>
  
<span data-ttu-id="dba85-112">当您要分配 IPC 邮件的接收文件夹时，从不使用从 IPM 子树文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-112">When you are assigning a receive folder for IPC messages, never use a folder from the IPM subtree.</span></span> <span data-ttu-id="dba85-113">应仅 IPM 邮件保留这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-113">These folders should be reserved for IPM messages only.</span></span> <span data-ttu-id="dba85-114">改用消息存储的根文件夹中包含的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-114">Use instead a folder that is contained within the message store's root folder.</span></span> 
  
 <span data-ttu-id="dba85-115">**若要创建 IPM 邮件类的接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="dba85-115">**To create a receive folder for an IPM message class**</span></span>
  
1. <span data-ttu-id="dba85-116">调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="dba85-116">Call the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) property.</span></span> 
    
2. <span data-ttu-id="dba85-117">调用与**PR_IPM_SUBTREE_ENTRYID** [IMsgStore::OpenEntry](imsgstore-openentry.md)作为消息存储库中打开 IPM 子树的根文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="dba85-117">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) with **PR_IPM_SUBTREE_ENTRYID** as the entry identifier to open the root folder of the IPM subtree in the message store.</span></span> 
    
3. <span data-ttu-id="dba85-118">调用[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)创建的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-118">Call [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) to create the receive folder.</span></span> 
    
4. <span data-ttu-id="dba85-119">调用[IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)到邮件类 IPM 映射新文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-119">Call [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md) to map the new folder to your IPM message class.</span></span> 
    
 <span data-ttu-id="dba85-120">**若要创建 IPC 邮件类的接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="dba85-120">**To create a receive folder for an IPC message class**</span></span>
  
1. <span data-ttu-id="dba85-121">要打开的邮件存储区的根文件夹的 null 条目标识符调用[IMsgStore::OpenEntry](imsgstore-openentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="dba85-121">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) with a null entry identifier to open the root folder of the message store.</span></span> 
    
2. <span data-ttu-id="dba85-122">调用[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)创建的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-122">Call [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) to create the receive folder.</span></span> 
    
3. <span data-ttu-id="dba85-123">调用[IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)映射到您 IPC 邮件类的新文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-123">Call [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md) to map the new folder to your IPC message class.</span></span> 
    
<span data-ttu-id="dba85-124">分配用于相关的报告邮件的邮件的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-124">Assign the receive folder that you use for messages for related report messages.</span></span> <span data-ttu-id="dba85-125">例如，如果您的客户端收到 IPM。说明消息，设置一个将来 IPM 接收文件夹。注意消息和相同接收的未来 Report.IPM.Note 邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dba85-125">For example, if your client receives IPM.Note messages, set up one receive folder for future IPM.Note messages and the same receive folder for future Report.IPM.Note messages.</span></span>
  

