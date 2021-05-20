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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431993"
---
# <a name="iostx--iunknown"></a><span data-ttu-id="65bb0-103">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="65bb0-103">IOSTX : IUnknown</span></span>

  
  
<span data-ttu-id="65bb0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65bb0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65bb0-105">提供同步方法。</span><span class="sxs-lookup"><span data-stu-id="65bb0-105">Provides synchronization methods.</span></span> <span data-ttu-id="65bb0-106">此接口检索将本地更改复制到服务器和服务器更改到本地存储的必要信息。</span><span class="sxs-lookup"><span data-stu-id="65bb0-106">This interface retrieves the necessary information to replicate local changes to the server and server changes to the local store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="65bb0-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="65bb0-107">Provided by:</span></span>  <br/> |[<span data-ttu-id="65bb0-108">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="65bb0-108">IPSTX::GetSyncObject</span></span>](iostx-setsyncresult.md) <br/> |
|<span data-ttu-id="65bb0-109">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="65bb0-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="65bb0-110">IID_IOSTX</span><span class="sxs-lookup"><span data-stu-id="65bb0-110">IID_IOSTX</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="65bb0-111">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="65bb0-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="65bb0-112">GetLastError</span><span class="sxs-lookup"><span data-stu-id="65bb0-112">GetLastError</span></span>](iostx-getlasterror.md) <br/> |<span data-ttu-id="65bb0-113">获取有关最后一个错误的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="65bb0-113">Gets extended information about the last error.</span></span>  <br/> |
|[<span data-ttu-id="65bb0-114">InitSync</span><span class="sxs-lookup"><span data-stu-id="65bb0-114">InitSync</span></span>](iostx-initsync.md) <br/> |<span data-ttu-id="65bb0-115">通知本地存储即将启动同步。</span><span class="sxs-lookup"><span data-stu-id="65bb0-115">Informs the local store that synchronization is about to start.</span></span>  <br/> |
|[<span data-ttu-id="65bb0-116">SyncBeg</span><span class="sxs-lookup"><span data-stu-id="65bb0-116">SyncBeg</span></span>](iostx-syncbeg.md) <br/> |<span data-ttu-id="65bb0-117">准备本地存储以用于特定状态同步，并检索要复制的必要信息。</span><span class="sxs-lookup"><span data-stu-id="65bb0-117">Prepares the local store for synchronization in a particular state and retrieves the necessary information to replicate.</span></span>  <br/> |
|[<span data-ttu-id="65bb0-118">SyncEnd</span><span class="sxs-lookup"><span data-stu-id="65bb0-118">SyncEnd</span></span>](iostx-syncend.md) <br/> |<span data-ttu-id="65bb0-119">在当前状态中结束同步并退出该状态。</span><span class="sxs-lookup"><span data-stu-id="65bb0-119">Ends synchronization in the current state and exits that state.</span></span>  <br/> |
|[<span data-ttu-id="65bb0-120">SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="65bb0-120">SyncHdrBeg</span></span>](iostx-synchdrbeg.md) <br/> |<span data-ttu-id="65bb0-121">启动邮件头的同步。</span><span class="sxs-lookup"><span data-stu-id="65bb0-121">Starts synchronization for a message header.</span></span>  <br/> |
|[<span data-ttu-id="65bb0-122">SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="65bb0-122">SyncHdrEnd</span></span>](iostx-synchdrend.md) <br/> |<span data-ttu-id="65bb0-123">结束邮件头的同步。</span><span class="sxs-lookup"><span data-stu-id="65bb0-123">Ends synchronization for a message header.</span></span>  <br/> |
|[<span data-ttu-id="65bb0-124">SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="65bb0-124">SetSyncResult</span></span>](iostx-setsyncresult.md) <br/> |<span data-ttu-id="65bb0-125">设置同步的结果。</span><span class="sxs-lookup"><span data-stu-id="65bb0-125">Sets the result of the synchronization.</span></span>  <br/> |
| <span data-ttu-id="65bb0-126">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="65bb0-126">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="65bb0-127">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="65bb0-127">*Not supported or documented.*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="65bb0-128">备注</span><span class="sxs-lookup"><span data-stu-id="65bb0-128">Remarks</span></span>

<span data-ttu-id="65bb0-129">当客户端上载或同步本地存储上的文件夹和文件夹内容时，它会将本地存储从一个状态移动到另一个状态，如关于复制状态机 的状态转换 [图中所示](about-the-replication-state-machine.md)。</span><span class="sxs-lookup"><span data-stu-id="65bb0-129">When a client uploads or synchronizes folders and folder contents on a local store, it moves the local store from one state to another as depicted in the state transition diagram in [About the Replication State Machine](about-the-replication-state-machine.md).</span></span> <span data-ttu-id="65bb0-130">以下是客户端将本地存储从一个状态移动到另一个状态的事件顺序：</span><span class="sxs-lookup"><span data-stu-id="65bb0-130">The following is the order of events for the client to move the local store from one state to another:</span></span>
  
1. <span data-ttu-id="65bb0-131">客户端调用 **IOSTX：：InitSync** 以通知本地存储即将开始复制。</span><span class="sxs-lookup"><span data-stu-id="65bb0-131">The client calls **IOSTX::InitSync** to inform the local store that replication is about to start.</span></span> 
    
2. <span data-ttu-id="65bb0-132">根据复制方向和要复制的对象，客户端会调用 **IOSTX：：SyncBeg** 以在适当的状态开始复制。</span><span class="sxs-lookup"><span data-stu-id="65bb0-132">Depending on the direction of replication and the objects to replicate, the client calls **IOSTX::SyncBeg** to begin replication in the appropriate state.</span></span> <span data-ttu-id="65bb0-133">Outlook向客户端提供必要信息，并且客户端执行复制。</span><span class="sxs-lookup"><span data-stu-id="65bb0-133">Outlook provides the client the necessary information, and the client performs the replication.</span></span> 
    
3. <span data-ttu-id="65bb0-134">客户端调用 **IOSTX：：SetSyncResult** 以返回复制结果。</span><span class="sxs-lookup"><span data-stu-id="65bb0-134">The client calls **IOSTX::SetSyncResult** to return the result of the replication.</span></span> 
    
4. <span data-ttu-id="65bb0-135">客户端调用 **IOSTX：：SyncEnd** 以结束复制，Outlook复制的必需信息。</span><span class="sxs-lookup"><span data-stu-id="65bb0-135">The client calls **IOSTX::SyncEnd** to end the replication, providing Outlook the necessary information for subsequent replication.</span></span> 
    
<span data-ttu-id="65bb0-136">特别是，在下载邮件项目时，客户端使用 **IOSTX：：SyncHdrBeg** 和 **IOSTX：：SyncHdrEnd** 在本地存储上使用邮件头更新完整邮件项目：</span><span class="sxs-lookup"><span data-stu-id="65bb0-136">In particular, when downloading message items, the client uses **IOSTX::SyncHdrBeg** and **IOSTX::SyncHdrEnd** to update a full message item with the message header on the local store:</span></span> 
  
1. <span data-ttu-id="65bb0-137">**IOSTX：：SyncHdrBeg** 时，本地存储将转换为下载邮件头状态。</span><span class="sxs-lookup"><span data-stu-id="65bb0-137">Upon **IOSTX::SyncHdrBeg**, the local store transitions into the download message header state.</span></span> <span data-ttu-id="65bb0-138">Outlook最初为客户端提供本地存储上的当前邮件头。</span><span class="sxs-lookup"><span data-stu-id="65bb0-138">Outlook initially provides the client with the current message header on the local store.</span></span>
    
2. <span data-ttu-id="65bb0-139">客户端下载包含邮件头的完整邮件项目。</span><span class="sxs-lookup"><span data-stu-id="65bb0-139">The client downloads a full message item together with the message header.</span></span>
    
3. <span data-ttu-id="65bb0-140">Outlook使用完整邮件项目更新本地存储上的项。</span><span class="sxs-lookup"><span data-stu-id="65bb0-140">Outlook updates the item on the local store with the full message item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="65bb0-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65bb0-141">See also</span></span>



[<span data-ttu-id="65bb0-142">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="65bb0-142">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="65bb0-143">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="65bb0-143">MAPI Constants</span></span>](mapi-constants.md)

