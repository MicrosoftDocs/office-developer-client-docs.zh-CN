---
title: IOSTXSyncBeg
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SyncBeg
api_type:
- COM
ms.assetid: 4a935df3-98c4-2742-206e-4e16eda7b9bc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae4497295328155780fc5208d1699169698e02d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411937"
---
# <a name="iostxsyncbeg"></a><span data-ttu-id="b0091-103">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="b0091-103">IOSTX::SyncBeg</span></span>

  
  
<span data-ttu-id="b0091-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0091-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0091-105">准备本地存储以用于特定状态同步，并检索要复制的必要信息。</span><span class="sxs-lookup"><span data-stu-id="b0091-105">Prepares the local store for synchronization in a particular state and retrieves the necessary information to replicate.</span></span>
  
```cpp
HRESULT SyncBeg( 
    UINT uiSync, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a><span data-ttu-id="b0091-106">参数</span><span class="sxs-lookup"><span data-stu-id="b0091-106">Parameters</span></span>

 <span data-ttu-id="b0091-107">_uiSync_</span><span class="sxs-lookup"><span data-stu-id="b0091-107">_uiSync_</span></span>
  
>  <span data-ttu-id="b0091-108">[in]本地存储将进入的状态。</span><span class="sxs-lookup"><span data-stu-id="b0091-108">[in] The state that the local store will enter.</span></span> <span data-ttu-id="b0091-109">以下是状态标识列表：</span><span class="sxs-lookup"><span data-stu-id="b0091-109">The following is a list of state identifers:</span></span> 
    
<span data-ttu-id="b0091-110">LR_SYNC_IDLE</span><span class="sxs-lookup"><span data-stu-id="b0091-110">LR_SYNC_IDLE</span></span>
  
> 
    
<span data-ttu-id="b0091-111">LR_SYNC</span><span class="sxs-lookup"><span data-stu-id="b0091-111">LR_SYNC</span></span>
  
> 
    
<span data-ttu-id="b0091-112">LR_SYNC_UPLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="b0091-112">LR_SYNC_UPLOAD_HIERARCHY</span></span>
  
> 
    
<span data-ttu-id="b0091-113">LR_SYNC_UPLOAD_FOLDER</span><span class="sxs-lookup"><span data-stu-id="b0091-113">LR_SYNC_UPLOAD_FOLDER</span></span>
  
> 
    
<span data-ttu-id="b0091-114">LR_SYNC_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="b0091-114">LR_SYNC_CONTENTS</span></span>
  
> 
    
<span data-ttu-id="b0091-115">LR_SYNC_UPLOAD_TABLE</span><span class="sxs-lookup"><span data-stu-id="b0091-115">LR_SYNC_UPLOAD_TABLE</span></span>
  
> 
    
<span data-ttu-id="b0091-116">LR_SYNC_UPLOAD_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="b0091-116">LR_SYNC_UPLOAD_MESSAGE</span></span>
  
> 
    
<span data-ttu-id="b0091-117">LR_SYNC_UPLOAD_MESSAGE_READ</span><span class="sxs-lookup"><span data-stu-id="b0091-117">LR_SYNC_UPLOAD_MESSAGE_READ</span></span>
  
> 
    
<span data-ttu-id="b0091-118">LR_SYNC_UPLOAD_MESSAGE_DEL</span><span class="sxs-lookup"><span data-stu-id="b0091-118">LR_SYNC_UPLOAD_MESSAGE_DEL</span></span>
  
> 
    
<span data-ttu-id="b0091-119">LR_SYNC_DOWNLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="b0091-119">LR_SYNC_DOWNLOAD_HIERARCHY</span></span>
  
> 
    
<span data-ttu-id="b0091-120">LR_SYNC_DOWNLOAD_TABLE</span><span class="sxs-lookup"><span data-stu-id="b0091-120">LR_SYNC_DOWNLOAD_TABLE</span></span>
  
> 
    
 <span data-ttu-id="b0091-121">_ppv_</span><span class="sxs-lookup"><span data-stu-id="b0091-121">_ppv_</span></span>
  
>  <span data-ttu-id="b0091-122">[in]/[out] 指向对应于要输入的状态的数据结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b0091-122">[in]/[out] Pointer to the data structure corresponding to the state to enter.</span></span> 
    
[<span data-ttu-id="b0091-123">DNHIER</span><span class="sxs-lookup"><span data-stu-id="b0091-123">DNHIER</span></span>](dnhier.md)
  
> 
    
[<span data-ttu-id="b0091-124">DNTBL</span><span class="sxs-lookup"><span data-stu-id="b0091-124">DNTBL</span></span>](dntbl.md)
  
> 
    
[<span data-ttu-id="b0091-125">DNTBL</span><span class="sxs-lookup"><span data-stu-id="b0091-125">DNTBL</span></span>](dntbl.md)
  
> 
    
[<span data-ttu-id="b0091-126">SYNC</span><span class="sxs-lookup"><span data-stu-id="b0091-126">SYNC</span></span>](sync.md)
  
> 
    
[<span data-ttu-id="b0091-127">SYNCCONT</span><span class="sxs-lookup"><span data-stu-id="b0091-127">SYNCCONT</span></span>](synccont.md)
  
> 
    
[<span data-ttu-id="b0091-128">UPDEL</span><span class="sxs-lookup"><span data-stu-id="b0091-128">UPDEL</span></span>](updel.md)
  
> 
    
[<span data-ttu-id="b0091-129">UPDELE</span><span class="sxs-lookup"><span data-stu-id="b0091-129">UPDELE</span></span>](updele.md)
  
> 
    
[<span data-ttu-id="b0091-130">UPFLD</span><span class="sxs-lookup"><span data-stu-id="b0091-130">UPFLD</span></span>](upfld.md)
  
> 
    
[<span data-ttu-id="b0091-131">UPHIER</span><span class="sxs-lookup"><span data-stu-id="b0091-131">UPHIER</span></span>](uphier.md)
  
> 
    
[<span data-ttu-id="b0091-132">UPMOV</span><span class="sxs-lookup"><span data-stu-id="b0091-132">UPMOV</span></span>](upmov.md)
  
> 
    
[<span data-ttu-id="b0091-133">UPMSG</span><span class="sxs-lookup"><span data-stu-id="b0091-133">UPMSG</span></span>](upmsg.md)
  
> 
    
[<span data-ttu-id="b0091-134">UPREAD</span><span class="sxs-lookup"><span data-stu-id="b0091-134">UPREAD</span></span>](upread.md)
  
> 
    
[<span data-ttu-id="b0091-135">UPREADE</span><span class="sxs-lookup"><span data-stu-id="b0091-135">UPREADE</span></span>](upreade.md)
  
> 
    
[<span data-ttu-id="b0091-136">UPTBL</span><span class="sxs-lookup"><span data-stu-id="b0091-136">UPTBL</span></span>](uptbl.md)
  
> 
    
[<span data-ttu-id="b0091-137">UPTBLE</span><span class="sxs-lookup"><span data-stu-id="b0091-137">UPTBLE</span></span>](uptble.md)
  
> 
    
## <a name="remarks"></a><span data-ttu-id="b0091-138">备注</span><span class="sxs-lookup"><span data-stu-id="b0091-138">Remarks</span></span>

<span data-ttu-id="b0091-139">客户端调用 **[IOSTX：：SetSyncResult](iostx-setsyncresult.md)** 以设置同步结果，然后调用 **[IOSTX：：SyncEnd](iostx-syncend.md)** 结束该状态。</span><span class="sxs-lookup"><span data-stu-id="b0091-139">The client calls **[IOSTX::SetSyncResult](iostx-setsyncresult.md)** to set the result of the synchronization, and then calls **[IOSTX::SyncEnd](iostx-syncend.md)** to end that state.</span></span> <span data-ttu-id="b0091-140">对于每次调用 **IOSTX：：SyncBeg** 时，客户端必须调用 **[IOSTX：：SyncEnd，](iostx-syncend.md)** 以确定是否已成功复制状态。</span><span class="sxs-lookup"><span data-stu-id="b0091-140">The client must call **[IOSTX::SyncEnd](iostx-syncend.md)** for each call to **IOSTX::SyncBeg** in order to determine whether the state has been successfully replicated.</span></span> <span data-ttu-id="b0091-141">确定此状态后，Outlook可以开始清理其内部状态。</span><span class="sxs-lookup"><span data-stu-id="b0091-141">Once this has been determined, Outlook can begin to clean up its internal state.</span></span> 
  
<span data-ttu-id="b0091-142">其中大多数结构包含 [out]/[in] 信息，Outlook向客户端传递信息，客户端将信息传递到Outlook。</span><span class="sxs-lookup"><span data-stu-id="b0091-142">Most of these structures contain [out]/[in] information, allowing Outlook to pass information to the client, and the client to pass information to Outlook.</span></span> <span data-ttu-id="b0091-143">当客户端调用 **IOSTX：：SyncBeg** 时，Outlook为给定状态分配数据结构，并初始化该状态的信息。</span><span class="sxs-lookup"><span data-stu-id="b0091-143">When the client calls **IOSTX::SyncBeg**, Outlook allocates the data structure for a given state and initializes it with information for that state.</span></span> <span data-ttu-id="b0091-144">这是 [out] 信息。</span><span class="sxs-lookup"><span data-stu-id="b0091-144">This is the [out] information.</span></span> <span data-ttu-id="b0091-145">当状态为 时，客户端会更新相应状态对应的数据结构。</span><span class="sxs-lookup"><span data-stu-id="b0091-145">While in a state, the client updates the corresponding data structure for that state.</span></span> <span data-ttu-id="b0091-146">这是 [in] 信息。</span><span class="sxs-lookup"><span data-stu-id="b0091-146">This is the [in] information.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b0091-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0091-147">See also</span></span>



[<span data-ttu-id="b0091-148">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="b0091-148">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="b0091-149">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="b0091-149">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="b0091-150">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="b0091-150">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="b0091-151">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="b0091-151">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="b0091-152">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="b0091-152">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="b0091-153">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="b0091-153">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="b0091-154">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b0091-154">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="b0091-155">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="b0091-155">MAPI Constants</span></span>](mapi-constants.md)

