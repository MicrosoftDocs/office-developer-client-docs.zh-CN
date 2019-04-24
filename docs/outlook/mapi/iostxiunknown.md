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
ms.openlocfilehash: 6d7de4d6c14179ddaba4e2ad907f1acc1c53b125
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317176"
---
# <a name="iostx--iunknown"></a><span data-ttu-id="7e7b3-103">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7e7b3-103">IOSTX : IUnknown</span></span>

  
  
<span data-ttu-id="7e7b3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e7b3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e7b3-105">提供同步方法。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-105">Provides synchronization methods.</span></span> <span data-ttu-id="7e7b3-106">此接口检索将本地更改复制到服务器并将服务器更改复制到本地存储的必要信息。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-106">This interface retrieves the necessary information to replicate local changes to the server and server changes to the local store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7e7b3-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="7e7b3-107">Provided by:</span></span>  <br/> |[<span data-ttu-id="7e7b3-108">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="7e7b3-108">IPSTX::GetSyncObject</span></span>](iostx-setsyncresult.md) <br/> |
|<span data-ttu-id="7e7b3-109">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="7e7b3-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="7e7b3-110">IID_IOSTX</span><span class="sxs-lookup"><span data-stu-id="7e7b3-110">IID_IOSTX</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="7e7b3-111">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="7e7b3-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="7e7b3-112">GetLastError</span><span class="sxs-lookup"><span data-stu-id="7e7b3-112">GetLastError</span></span>](iostx-getlasterror.md) <br/> |<span data-ttu-id="7e7b3-113">获取有关上一个错误的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-113">Gets extended information about the last error.</span></span>  <br/> |
|[<span data-ttu-id="7e7b3-114">InitSync</span><span class="sxs-lookup"><span data-stu-id="7e7b3-114">InitSync</span></span>](iostx-initsync.md) <br/> |<span data-ttu-id="7e7b3-115">通知本地存储即将启动同步。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-115">Informs the local store that synchronization is about to start.</span></span>  <br/> |
|[<span data-ttu-id="7e7b3-116">SyncBeg</span><span class="sxs-lookup"><span data-stu-id="7e7b3-116">SyncBeg</span></span>](iostx-syncbeg.md) <br/> |<span data-ttu-id="7e7b3-117">准备本地存储以在特定状态进行同步并检索要复制的必要信息。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-117">Prepares the local store for synchronization in a particular state and retrieves the necessary information to replicate.</span></span>  <br/> |
|[<span data-ttu-id="7e7b3-118">SyncEnd</span><span class="sxs-lookup"><span data-stu-id="7e7b3-118">SyncEnd</span></span>](iostx-syncend.md) <br/> |<span data-ttu-id="7e7b3-119">在当前状态结束同步并退出该状态。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-119">Ends synchronization in the current state and exits that state.</span></span>  <br/> |
|[<span data-ttu-id="7e7b3-120">SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="7e7b3-120">SyncHdrBeg</span></span>](iostx-synchdrbeg.md) <br/> |<span data-ttu-id="7e7b3-121">启动邮件头同步。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-121">Starts synchronization for a message header.</span></span>  <br/> |
|[<span data-ttu-id="7e7b3-122">SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="7e7b3-122">SyncHdrEnd</span></span>](iostx-synchdrend.md) <br/> |<span data-ttu-id="7e7b3-123">结束邮件头同步。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-123">Ends synchronization for a message header.</span></span>  <br/> |
|[<span data-ttu-id="7e7b3-124">SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="7e7b3-124">SetSyncResult</span></span>](iostx-setsyncresult.md) <br/> |<span data-ttu-id="7e7b3-125">设置同步的结果。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-125">Sets the result of the synchronization.</span></span>  <br/> |
| <span data-ttu-id="7e7b3-126">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="7e7b3-126">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="7e7b3-127">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="7e7b3-127">*Not supported or documented.*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e7b3-128">注解</span><span class="sxs-lookup"><span data-stu-id="7e7b3-128">Remarks</span></span>

<span data-ttu-id="7e7b3-129">当客户端在本地存储上上载或同步文件夹和文件夹内容时, 它会将本地存储从一个状态移动到另一个状态, 如[关于复制状态机](about-the-replication-state-machine.md)中的状态转换关系图中所示。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-129">When a client uploads or synchronizes folders and folder contents on a local store, it moves the local store from one state to another as depicted in the state transition diagram in [About the Replication State Machine](about-the-replication-state-machine.md).</span></span> <span data-ttu-id="7e7b3-130">以下是客户端将本地存储从一个状态移动到另一个状态的事件的顺序:</span><span class="sxs-lookup"><span data-stu-id="7e7b3-130">The following is the order of events for the client to move the local store from one state to another:</span></span>
  
1. <span data-ttu-id="7e7b3-131">客户端调用**IOSTX:: InitSync**来通知本地存储即将启动复制。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-131">The client calls **IOSTX::InitSync** to inform the local store that replication is about to start.</span></span> 
    
2. <span data-ttu-id="7e7b3-132">根据复制方向和要复制的对象, 客户端会调用**IOSTX:: SyncBeg**以在适当的状态下开始复制。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-132">Depending on the direction of replication and the objects to replicate, the client calls **IOSTX::SyncBeg** to begin replication in the appropriate state.</span></span> <span data-ttu-id="7e7b3-133">Outlook 向客户端提供必要的信息, 客户端执行复制。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-133">Outlook provides the client the necessary information, and the client performs the replication.</span></span> 
    
3. <span data-ttu-id="7e7b3-134">客户端调用**IOSTX:: SetSyncResult**以返回复制的结果。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-134">The client calls **IOSTX::SetSyncResult** to return the result of the replication.</span></span> 
    
4. <span data-ttu-id="7e7b3-135">客户端调用**IOSTX:: SyncEnd**结束复制, 为 Outlook 提供了后续复制所需的信息。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-135">The client calls **IOSTX::SyncEnd** to end the replication, providing Outlook the necessary information for subsequent replication.</span></span> 
    
<span data-ttu-id="7e7b3-136">特别是在下载邮件项目时, 客户端使用**IOSTX:: SyncHdrBeg**和**IOSTX:: SyncHdrEnd**更新本地存储区上的邮件头的完整邮件项:</span><span class="sxs-lookup"><span data-stu-id="7e7b3-136">In particular, when downloading message items, the client uses **IOSTX::SyncHdrBeg** and **IOSTX::SyncHdrEnd** to update a full message item with the message header on the local store:</span></span> 
  
1. <span data-ttu-id="7e7b3-137">在**IOSTX:: SyncHdrBeg**中, 本地存储将转换为下载邮件标头状态。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-137">Upon **IOSTX::SyncHdrBeg**, the local store transitions into the download message header state.</span></span> <span data-ttu-id="7e7b3-138">Outlook 最初为客户端提供本地存储上的当前邮件头。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-138">Outlook initially provides the client with the current message header on the local store.</span></span>
    
2. <span data-ttu-id="7e7b3-139">客户端将完整的邮件项与邮件头一起下载。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-139">The client downloads a full message item together with the message header.</span></span>
    
3. <span data-ttu-id="7e7b3-140">Outlook 使用完整邮件项更新本地存储区上的项目。</span><span class="sxs-lookup"><span data-stu-id="7e7b3-140">Outlook updates the item on the local store with the full message item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7e7b3-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e7b3-141">See also</span></span>



[<span data-ttu-id="7e7b3-142">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="7e7b3-142">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="7e7b3-143">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="7e7b3-143">MAPI Constants</span></span>](mapi-constants.md)

