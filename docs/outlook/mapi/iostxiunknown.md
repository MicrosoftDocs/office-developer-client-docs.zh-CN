---
title: IOSTX IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX
api_type:
- COM
ms.assetid: f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9c9252e83ce212bacf185d0eedb75d30617f9807
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581746"
---
# <a name="iostx--iunknown"></a><span data-ttu-id="bc4ae-103">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bc4ae-103">IOSTX : IUnknown</span></span>

  
  
<span data-ttu-id="bc4ae-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc4ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc4ae-105">提供同步的方法。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-105">Provides synchronization methods.</span></span> <span data-ttu-id="bc4ae-106">此接口检索将本地更改复制到的服务器和服务器到本地存储的更改的必要信息。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-106">This interface retrieves the necessary information to replicate local changes to the server and server changes to the local store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bc4ae-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="bc4ae-107">Provided by:</span></span>  <br/> |[<span data-ttu-id="bc4ae-108">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="bc4ae-108">IPSTX::GetSyncObject</span></span>](iostx-setsyncresult.md) <br/> |
|<span data-ttu-id="bc4ae-109">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="bc4ae-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="bc4ae-110">IID_IOSTX</span><span class="sxs-lookup"><span data-stu-id="bc4ae-110">IID_IOSTX</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="bc4ae-111">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="bc4ae-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="bc4ae-112">时出错</span><span class="sxs-lookup"><span data-stu-id="bc4ae-112">GetLastError</span></span>](iostx-getlasterror.md) <br/> |<span data-ttu-id="bc4ae-113">获取有关扩展的信息的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-113">Gets extended information about the last error.</span></span>  <br/> |
|[<span data-ttu-id="bc4ae-114">InitSync</span><span class="sxs-lookup"><span data-stu-id="bc4ae-114">InitSync</span></span>](iostx-initsync.md) <br/> |<span data-ttu-id="bc4ae-115">通知的本地存储同步即将开始。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-115">Informs the local store that synchronization is about to start.</span></span>  <br/> |
|[<span data-ttu-id="bc4ae-116">SyncBeg</span><span class="sxs-lookup"><span data-stu-id="bc4ae-116">SyncBeg</span></span>](iostx-syncbeg.md) <br/> |<span data-ttu-id="bc4ae-117">为特定状态同步准备本地存储并检索复制的必需信息。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-117">Prepares the local store for synchronization in a particular state and retrieves the necessary information to replicate.</span></span>  <br/> |
|[<span data-ttu-id="bc4ae-118">SyncEnd</span><span class="sxs-lookup"><span data-stu-id="bc4ae-118">SyncEnd</span></span>](iostx-syncend.md) <br/> |<span data-ttu-id="bc4ae-119">结束同步中的当前状态并退出该状态。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-119">Ends synchronization in the current state and exits that state.</span></span>  <br/> |
|[<span data-ttu-id="bc4ae-120">SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="bc4ae-120">SyncHdrBeg</span></span>](iostx-synchdrbeg.md) <br/> |<span data-ttu-id="bc4ae-121">邮件头的启动同步。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-121">Starts synchronization for a message header.</span></span>  <br/> |
|[<span data-ttu-id="bc4ae-122">SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="bc4ae-122">SyncHdrEnd</span></span>](iostx-synchdrend.md) <br/> |<span data-ttu-id="bc4ae-123">邮件头的两端同步。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-123">Ends synchronization for a message header.</span></span>  <br/> |
|[<span data-ttu-id="bc4ae-124">SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="bc4ae-124">SetSyncResult</span></span>](iostx-setsyncresult.md) <br/> |<span data-ttu-id="bc4ae-125">设置同步的结果。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-125">Sets the result of the synchronization.</span></span>  <br/> |
| <span data-ttu-id="bc4ae-126">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="bc4ae-126">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="bc4ae-127">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="bc4ae-127">*Not supported or documented.*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bc4ae-128">注解</span><span class="sxs-lookup"><span data-stu-id="bc4ae-128">Remarks</span></span>

<span data-ttu-id="bc4ae-129">当客户端上载或同步文件夹和本地存储区上的文件夹内容时，将本地存储从一种状态到另一个[有关复制状态机](about-the-replication-state-machine.md)中的状态转换关系图中所示。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-129">When a client uploads or synchronizes folders and folder contents on a local store, it moves the local store from one state to another as depicted in the state transition diagram in [About the Replication State Machine](about-the-replication-state-machine.md).</span></span> <span data-ttu-id="bc4ae-130">以下是从一种状态的本地存储移动到另一个客户端的事件的顺序：</span><span class="sxs-lookup"><span data-stu-id="bc4ae-130">The following is the order of events for the client to move the local store from one state to another:</span></span>
  
1. <span data-ttu-id="bc4ae-131">客户端调用**IOSTX::InitSync** ，告知复制即将开始的本地存储。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-131">The client calls **IOSTX::InitSync** to inform the local store that replication is about to start.</span></span> 
    
2. <span data-ttu-id="bc4ae-132">复制和要复制的对象的方向，根据客户端调用**IOSTX::SyncBeg**开始复制中相应的状态。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-132">Depending on the direction of replication and the objects to replicate, the client calls **IOSTX::SyncBeg** to begin replication in the appropriate state.</span></span> <span data-ttu-id="bc4ae-133">Outlook 提供了客户端所需的信息，并在客户端执行复制。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-133">Outlook provides the client the necessary information, and the client performs the replication.</span></span> 
    
3. <span data-ttu-id="bc4ae-134">客户端调用**IOSTX::SetSyncResult**返回复制的结果。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-134">The client calls **IOSTX::SetSyncResult** to return the result of the replication.</span></span> 
    
4. <span data-ttu-id="bc4ae-135">客户端调用**IOSTX::SyncEnd**结束复制，提供 Outlook 后续复制所需的信息。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-135">The client calls **IOSTX::SyncEnd** to end the replication, providing Outlook the necessary information for subsequent replication.</span></span> 
    
<span data-ttu-id="bc4ae-136">具体而言，当下载邮件项目，客户端使用**IOSTX::SyncHdrBeg**和**IOSTX::SyncHdrEnd**更新完整的邮件项目上本地存储消息标头：</span><span class="sxs-lookup"><span data-stu-id="bc4ae-136">In particular, when downloading message items, the client uses **IOSTX::SyncHdrBeg** and **IOSTX::SyncHdrEnd** to update a full message item with the message header on the local store:</span></span> 
  
1. <span data-ttu-id="bc4ae-137">时**IOSTX::SyncHdrBeg**，本地存储转换到该下载邮件头状态。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-137">Upon **IOSTX::SyncHdrBeg**, the local store transitions into the download message header state.</span></span> <span data-ttu-id="bc4ae-138">Outlook 最初上本地存储为客户提供当前的邮件头。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-138">Outlook initially provides the client with the current message header on the local store.</span></span>
    
2. <span data-ttu-id="bc4ae-139">客户端下载完整邮件项目以及邮件头。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-139">The client downloads a full message item together with the message header.</span></span>
    
3. <span data-ttu-id="bc4ae-140">Outlook 更新完整的邮件项目上本地存储的项。</span><span class="sxs-lookup"><span data-stu-id="bc4ae-140">Outlook updates the item on the local store with the full message item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bc4ae-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc4ae-141">See also</span></span>



[<span data-ttu-id="bc4ae-142">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="bc4ae-142">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="bc4ae-143">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="bc4ae-143">MAPI Constants</span></span>](mapi-constants.md)

