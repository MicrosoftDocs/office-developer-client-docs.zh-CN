---
title: 选择接收文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 144c7179-b390-479f-a2aa-324974f04eba
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9151b76f74dead5cac771dbdc091bbee03359aec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428415"
---
# <a name="selecting-a-receive-folder"></a><span data-ttu-id="f1c27-103">选择接收文件夹</span><span class="sxs-lookup"><span data-stu-id="f1c27-103">Selecting a Receive Folder</span></span>

  
  
<span data-ttu-id="f1c27-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1c27-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1c27-105">接收文件夹是在其中放置特定类的传入邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="f1c27-105">A receive folder is where incoming messages of a particular class are placed.</span></span> <span data-ttu-id="f1c27-106">对于 IPM 和相关报告邮件, MAPI 将收件箱分配为默认接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-106">For IPM and related report messages, MAPI assigns the Inbox as the default receive folder.</span></span> <span data-ttu-id="f1c27-107">对于 IPC 和相关报告邮件, MAPI 会将邮件存储区的根文件夹指定为默认的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-107">For IPC and related report messages, MAPI assigns the root folder of the message store as the default receive folder.</span></span> <span data-ttu-id="f1c27-108">您可以更改这些分配或对其他邮件类别进行其他分配。</span><span class="sxs-lookup"><span data-stu-id="f1c27-108">You can change these assignments or make additional assignments for other message classes.</span></span> <span data-ttu-id="f1c27-109">为客户端支持的邮件类别生成显式接收文件夹分配是可选的。</span><span class="sxs-lookup"><span data-stu-id="f1c27-109">Making explicit receive folder assignments for your client's supported message classes is optional.</span></span>
  
<span data-ttu-id="f1c27-110">如果传入邮件类没有已分配的接收文件夹, 则邮件存储提供程序将自动使用与传入类的最长可能前缀相匹配的类的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-110">When an incoming message class does not have an assigned receive folder, the message store provider automatically uses the receive folder for the class that matches the longest possible prefix of the incoming class.</span></span> <span data-ttu-id="f1c27-111">例如, 如果您的客户端收到一个类为 IPM 的邮件。注意: MyDocument 和已建立的接收文件夹是 IPM 邮件的收件箱, 因此该邮件将放置在收件箱中, 因为 ipm。注意: MyDocument 派生自基类 IPM。</span><span class="sxs-lookup"><span data-stu-id="f1c27-111">For example, if your client receives a message of class IPM.Note.MyDocument and the only receive folder that has been established is the Inbox for IPM messages, this message will be placed in the Inbox because IPM.Note.MyDocument derives from the base class IPM.</span></span>
  
<span data-ttu-id="f1c27-112">为 IPC 邮件分配接收文件夹时, 决不要使用 IPM 子树中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-112">When you are assigning a receive folder for IPC messages, never use a folder from the IPM subtree.</span></span> <span data-ttu-id="f1c27-113">应仅为 IPM 邮件保留这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-113">These folders should be reserved for IPM messages only.</span></span> <span data-ttu-id="f1c27-114">而不是包含在邮件存储区的根文件夹中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-114">Use instead a folder that is contained within the message store's root folder.</span></span> 
  
 <span data-ttu-id="f1c27-115">**为 IPM 邮件类创建接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="f1c27-115">**To create a receive folder for an IPM message class**</span></span>
  
1. <span data-ttu-id="f1c27-116">调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f1c27-116">Call the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) property.</span></span> 
    
2. <span data-ttu-id="f1c27-117">调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)并将**PR_IPM_SUBTREE_ENTRYID**作为条目标识符, 以打开邮件存储区中的 IPM 子树的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-117">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) with **PR_IPM_SUBTREE_ENTRYID** as the entry identifier to open the root folder of the IPM subtree in the message store.</span></span> 
    
3. <span data-ttu-id="f1c27-118">调用[IMAPIFolder:: CreateFolder](imapifolder-createfolder.md)以创建接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-118">Call [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) to create the receive folder.</span></span> 
    
4. <span data-ttu-id="f1c27-119">调用[IMsgStore:: SetReceiveFolder](imsgstore-setreceivefolder.md)将新文件夹映射到您的 IPM 邮件类。</span><span class="sxs-lookup"><span data-stu-id="f1c27-119">Call [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md) to map the new folder to your IPM message class.</span></span> 
    
 <span data-ttu-id="f1c27-120">**为 IPC 邮件类创建接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="f1c27-120">**To create a receive folder for an IPC message class**</span></span>
  
1. <span data-ttu-id="f1c27-121">调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)和 null 条目标识符, 以打开邮件存储区的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-121">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) with a null entry identifier to open the root folder of the message store.</span></span> 
    
2. <span data-ttu-id="f1c27-122">调用[IMAPIFolder:: CreateFolder](imapifolder-createfolder.md)以创建接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1c27-122">Call [IMAPIFolder::CreateFolder](imapifolder-createfolder.md) to create the receive folder.</span></span> 
    
3. <span data-ttu-id="f1c27-123">调用[IMsgStore:: SetReceiveFolder](imsgstore-setreceivefolder.md)将新文件夹映射到 IPC 邮件类。</span><span class="sxs-lookup"><span data-stu-id="f1c27-123">Call [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md) to map the new folder to your IPC message class.</span></span> 
    
<span data-ttu-id="f1c27-124">为用于邮件的接收文件夹分配相关的报告邮件。</span><span class="sxs-lookup"><span data-stu-id="f1c27-124">Assign the receive folder that you use for messages for related report messages.</span></span> <span data-ttu-id="f1c27-125">例如, 如果您的客户端收到 IPM。注释邮件, 为将来的 IPM 设置一个接收文件夹。注意未来报告的消息和相同的接收文件夹。 IPM. 消息。</span><span class="sxs-lookup"><span data-stu-id="f1c27-125">For example, if your client receives IPM.Note messages, set up one receive folder for future IPM.Note messages and the same receive folder for future Report.IPM.Note messages.</span></span>
  

