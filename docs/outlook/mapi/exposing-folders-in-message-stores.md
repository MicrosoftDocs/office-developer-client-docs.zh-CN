---
title: 公开邮件存储中的文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9309e47-2a92-4576-9921-c89cc48472c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 457620dd0f805e78d12fc8feba09f8fc8aedc554
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341347"
---
# <a name="exposing-folders-in-message-stores"></a><span data-ttu-id="cc6c8-103">公开邮件存储中的文件夹</span><span class="sxs-lookup"><span data-stu-id="cc6c8-103">Exposing Folders in Message Stores</span></span>

  
  
<span data-ttu-id="cc6c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc6c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc6c8-105">每个邮件存储提供程序都必须向客户端应用程序提供顶级 [IMAPIFolder](imapifolderimapicontainer.md) 界面。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-105">Every message store provider must present a top-level [IMAPIFolder](imapifolderimapicontainer.md) interface to client applications.</span></span> <span data-ttu-id="cc6c8-106">顶级文件夹对应整个邮件存储；它提供用户看作邮件存储内容的文件夹的访问权限。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-106">The top-level folder corresponds to the entire message store; it provides access to the folders that users see as the contents of the message store.</span></span> <span data-ttu-id="cc6c8-107">此外，顶级文件夹通常用作 IPC 邮件的默认接收文件夹和发送已读报表的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-107">In addition, the top-level folder is often used as the default receive folder for IPC messages and as the folder from which read reports are sent.</span></span> <span data-ttu-id="cc6c8-108">邮件存储提供程序还必须向客户端应用程序提供 IPM 子树 — 用于包含 IPM 邮件的文件夹集。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-108">Message store providers must also present an IPM subtree — a set of folders used to contain IPM messages — to client applications.</span></span> 
  
<span data-ttu-id="cc6c8-109">客户端应用程序可以通过调用 [IMsgStore::OpenEntry](imsgstore-openentry.md) 方法打开顶级文件夹，_cbEntryId_ 和 _lpEntryId_ 参数分别 0 和 NULL。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-109">Client applications can open the top-level folder by calling the [IMsgStore::OpenEntry](imsgstore-openentry.md) method with 0 and NULL for the  _cbEntryId_ and  _lpEntryId_ parameters, respectively.</span></span> <span data-ttu-id="cc6c8-110">但是，在大多数情况下，客户端应用程序会打开包含 IPM 邮件的文件夹集。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-110">In most cases, however, client applications open the set of folders that contain IPM messages.</span></span> 
  
<span data-ttu-id="cc6c8-111">若要获取邮件存储 IPM 文件夹树中的文件夹列表，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="cc6c8-111">To get a list of folders in the message store's IPM folder tree, use the following procedure:</span></span>
  
1. <span data-ttu-id="cc6c8-112">使用 MAPI 会话来调用 [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-112">Use your MAPI session to call the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method.</span></span> 
    
2. <span data-ttu-id="cc6c8-113">使用结果邮件数据库指针来调用 **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性的 [IMAPIProp::GetProps](imapiprop-getprops.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-113">Use the resulting message database pointer to call the [IMAPIProp::GetProps](imapiprop-getprops.md) method for the **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) property.</span></span>
    
3. <span data-ttu-id="cc6c8-114">使用条目标识符调用 [IMsgStore::OpenEntry](imsgstore-openentry.md) 方法以获取 **IMAPIFolder** 指针。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-114">Call the [IMsgStore::OpenEntry](imsgstore-openentry.md) method with the entry identifier to get an **IMAPIFolder** pointer.</span></span> 
    
4. <span data-ttu-id="cc6c8-115">调用 [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) 方法以获取文件夹内容表。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-115">Call the [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method to get a table of the contents of the folder.</span></span> 
    
5. <span data-ttu-id="cc6c8-116">调用 [IMAPITable::QueryRows](imapitable-queryrows.md) 方法以列出顶级文件夹中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-116">Call the [IMAPITable::QueryRows](imapitable-queryrows.md) method to list the folders in the top-level folder.</span></span> 
    
<span data-ttu-id="cc6c8-117">MAPI 客户端使用这些文件夹访问邮件存储中的其他文件夹对象和邮件对象。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-117">MAPI clients use these folders to access other folder objects and message objects in the message store.</span></span> <span data-ttu-id="cc6c8-118">**IMAPIFolder** 及其父界面 [IMAPIContainer](imapicontainerimapiprop.md) 包含邮件存储提供程序必须实现的方法，以使用邮件对象填充文件夹并响应客户端操作邮件的请求。</span><span class="sxs-lookup"><span data-stu-id="cc6c8-118">**IMAPIFolder**, and its parent interface [IMAPIContainer](imapicontainerimapiprop.md), contain the methods your message store provider must implement to populate folders with message objects and respond to client requests to operate on messages.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc6c8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc6c8-119">See also</span></span>



[<span data-ttu-id="cc6c8-120">实现邮件存储中的文件夹</span><span class="sxs-lookup"><span data-stu-id="cc6c8-120">Implementing Folders in Message Stores</span></span>](implementing-folders-in-message-stores.md)

