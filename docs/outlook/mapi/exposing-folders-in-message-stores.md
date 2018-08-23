---
title: 公开邮件存储区中的文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9309e47-2a92-4576-9921-c89cc48472c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 62f50ed7925305eca7432da17130d2be0365ef03
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582593"
---
# <a name="exposing-folders-in-message-stores"></a><span data-ttu-id="0b0ce-103">公开邮件存储区中的文件夹</span><span class="sxs-lookup"><span data-stu-id="0b0ce-103">Exposing Folders in Message Stores</span></span>

  
  
<span data-ttu-id="0b0ce-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0b0ce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0b0ce-105">每个消息存储提供程序必须提供客户端应用程序的顶级[IMAPIFolder](imapifolderimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-105">Every message store provider must present a top-level [IMAPIFolder](imapifolderimapicontainer.md) interface to client applications.</span></span> <span data-ttu-id="0b0ce-106">顶级文件夹对应的整个邮件存储;它提供用户看到的消息存储内容的文件夹的访问。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-106">The top-level folder corresponds to the entire message store; it provides access to the folders that users see as the contents of the message store.</span></span> <span data-ttu-id="0b0ce-107">此外的顶级文件夹通常用作默认的接收文件夹 IPC 邮件文件夹以及从其阅读报告发送。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-107">In addition, the top-level folder is often used as the default receive folder for IPC messages and as the folder from which read reports are sent.</span></span> <span data-ttu-id="0b0ce-108">消息存储提供程序必须还提供 IPM 子树 — 的一组用于包含 IPM 邮件文件夹 — 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-108">Message store providers must also present an IPM subtree — a set of folders used to contain IPM messages — to client applications.</span></span> 
  
<span data-ttu-id="0b0ce-109">客户端应用程序可以通过分别对于_cbEntryId_和_lpEntryId_参数，调用带 0 和 NULL 的[IMsgStore::OpenEntry](imsgstore-openentry.md)方法打开的顶级文件夹。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-109">Client applications can open the top-level folder by calling the [IMsgStore::OpenEntry](imsgstore-openentry.md) method with 0 and NULL for the  _cbEntryId_ and  _lpEntryId_ parameters, respectively.</span></span> <span data-ttu-id="0b0ce-110">但是，在大多数情况下，客户端应用程序打开的文件夹包含 IPM 邮件的组。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-110">In most cases, however, client applications open the set of folders that contain IPM messages.</span></span> 
  
<span data-ttu-id="0b0ce-111">若要获取的消息存储 IPM 文件夹树中的文件夹的列表，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="0b0ce-111">To get a list of folders in the message store's IPM folder tree, use the following procedure:</span></span>
  
1. <span data-ttu-id="0b0ce-112">使用 MAPI 会话调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-112">Use your MAPI session to call the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method.</span></span> 
    
2. <span data-ttu-id="0b0ce-113">使用生成的邮件数据库指针[IMAPIProp::GetProps](imapiprop-getprops.md)方法调用**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-113">Use the resulting message database pointer to call the [IMAPIProp::GetProps](imapiprop-getprops.md) method for the **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) property.</span></span>
    
3. <span data-ttu-id="0b0ce-114">调用具有条目标识符获取**IMAPIFolder**指针[IMsgStore::OpenEntry](imsgstore-openentry.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-114">Call the [IMsgStore::OpenEntry](imsgstore-openentry.md) method with the entry identifier to get an **IMAPIFolder** pointer.</span></span> 
    
4. <span data-ttu-id="0b0ce-115">调用[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以获取文件夹的目录。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-115">Call the [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method to get a table of the contents of the folder.</span></span> 
    
5. <span data-ttu-id="0b0ce-116">调用[IMAPITable::QueryRows](imapitable-queryrows.md)方法列表中的顶级文件夹的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-116">Call the [IMAPITable::QueryRows](imapitable-queryrows.md) method to list the folders in the top-level folder.</span></span> 
    
<span data-ttu-id="0b0ce-117">MAPI 客户端使用这些文件夹以访问其他 folder 对象和邮件存储区中的消息对象。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-117">MAPI clients use these folders to access other folder objects and message objects in the message store.</span></span> <span data-ttu-id="0b0ce-118">**IMAPIFolder**和[IMAPIContainer](imapicontainerimapiprop.md)，其父接口包含您的消息存储提供程序必须实现以填充消息对象包含的文件夹和响应客户端请求邮件上运行的方法。</span><span class="sxs-lookup"><span data-stu-id="0b0ce-118">**IMAPIFolder**, and its parent interface [IMAPIContainer](imapicontainerimapiprop.md), contain the methods your message store provider must implement to populate folders with message objects and respond to client requests to operate on messages.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b0ce-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b0ce-119">See also</span></span>



[<span data-ttu-id="0b0ce-120">实现邮件存储区中的文件夹</span><span class="sxs-lookup"><span data-stu-id="0b0ce-120">Implementing Folders in Message Stores</span></span>](implementing-folders-in-message-stores.md)

