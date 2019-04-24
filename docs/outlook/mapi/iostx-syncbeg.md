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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317169"
---
# <a name="iostxsyncbeg"></a><span data-ttu-id="fdc27-103">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="fdc27-103">IOSTX::SyncBeg</span></span>

  
  
<span data-ttu-id="fdc27-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fdc27-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fdc27-105">准备本地存储以在特定状态进行同步并检索要复制的必要信息。</span><span class="sxs-lookup"><span data-stu-id="fdc27-105">Prepares the local store for synchronization in a particular state and retrieves the necessary information to replicate.</span></span>
  
```cpp
HRESULT SyncBeg( 
    UINT uiSync, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a><span data-ttu-id="fdc27-106">参数</span><span class="sxs-lookup"><span data-stu-id="fdc27-106">Parameters</span></span>

 <span data-ttu-id="fdc27-107">_uiSync_</span><span class="sxs-lookup"><span data-stu-id="fdc27-107">_uiSync_</span></span>
  
>  <span data-ttu-id="fdc27-108">实时本地存储将输入的省/市/自治区。</span><span class="sxs-lookup"><span data-stu-id="fdc27-108">[in] The state that the local store will enter.</span></span> <span data-ttu-id="fdc27-109">以下是状态终止的列表:</span><span class="sxs-lookup"><span data-stu-id="fdc27-109">The following is a list of state identifers:</span></span> 
    
<span data-ttu-id="fdc27-110">LR_SYNC_IDLE</span><span class="sxs-lookup"><span data-stu-id="fdc27-110">LR_SYNC_IDLE</span></span>
  
> 
    
<span data-ttu-id="fdc27-111">LR_SYNC</span><span class="sxs-lookup"><span data-stu-id="fdc27-111">LR_SYNC</span></span>
  
> 
    
<span data-ttu-id="fdc27-112">LR_SYNC_UPLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="fdc27-112">LR_SYNC_UPLOAD_HIERARCHY</span></span>
  
> 
    
<span data-ttu-id="fdc27-113">LR_SYNC_UPLOAD_FOLDER</span><span class="sxs-lookup"><span data-stu-id="fdc27-113">LR_SYNC_UPLOAD_FOLDER</span></span>
  
> 
    
<span data-ttu-id="fdc27-114">LR_SYNC_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="fdc27-114">LR_SYNC_CONTENTS</span></span>
  
> 
    
<span data-ttu-id="fdc27-115">LR_SYNC_UPLOAD_TABLE</span><span class="sxs-lookup"><span data-stu-id="fdc27-115">LR_SYNC_UPLOAD_TABLE</span></span>
  
> 
    
<span data-ttu-id="fdc27-116">LR_SYNC_UPLOAD_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="fdc27-116">LR_SYNC_UPLOAD_MESSAGE</span></span>
  
> 
    
<span data-ttu-id="fdc27-117">LR_SYNC_UPLOAD_MESSAGE_READ</span><span class="sxs-lookup"><span data-stu-id="fdc27-117">LR_SYNC_UPLOAD_MESSAGE_READ</span></span>
  
> 
    
<span data-ttu-id="fdc27-118">LR_SYNC_UPLOAD_MESSAGE_DEL</span><span class="sxs-lookup"><span data-stu-id="fdc27-118">LR_SYNC_UPLOAD_MESSAGE_DEL</span></span>
  
> 
    
<span data-ttu-id="fdc27-119">LR_SYNC_DOWNLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="fdc27-119">LR_SYNC_DOWNLOAD_HIERARCHY</span></span>
  
> 
    
<span data-ttu-id="fdc27-120">LR_SYNC_DOWNLOAD_TABLE</span><span class="sxs-lookup"><span data-stu-id="fdc27-120">LR_SYNC_DOWNLOAD_TABLE</span></span>
  
> 
    
 <span data-ttu-id="fdc27-121">_ppv_</span><span class="sxs-lookup"><span data-stu-id="fdc27-121">_ppv_</span></span>
  
>  <span data-ttu-id="fdc27-122">[in]/[out] 指针, 指向与要输入的状态相对应的数据结构。</span><span class="sxs-lookup"><span data-stu-id="fdc27-122">[in]/[out] Pointer to the data structure corresponding to the state to enter.</span></span> 
    
[<span data-ttu-id="fdc27-123">DNHIER</span><span class="sxs-lookup"><span data-stu-id="fdc27-123">DNHIER</span></span>](dnhier.md)
  
> 
    
[<span data-ttu-id="fdc27-124">DNTBL</span><span class="sxs-lookup"><span data-stu-id="fdc27-124">DNTBL</span></span>](dntbl.md)
  
> 
    
[<span data-ttu-id="fdc27-125">DNTBL</span><span class="sxs-lookup"><span data-stu-id="fdc27-125">DNTBL</span></span>](dntbl.md)
  
> 
    
[<span data-ttu-id="fdc27-126">同步</span><span class="sxs-lookup"><span data-stu-id="fdc27-126">SYNC</span></span>](sync.md)
  
> 
    
[<span data-ttu-id="fdc27-127">SYNCCONT</span><span class="sxs-lookup"><span data-stu-id="fdc27-127">SYNCCONT</span></span>](synccont.md)
  
> 
    
[<span data-ttu-id="fdc27-128">UPDEL</span><span class="sxs-lookup"><span data-stu-id="fdc27-128">UPDEL</span></span>](updel.md)
  
> 
    
[<span data-ttu-id="fdc27-129">UPDELE</span><span class="sxs-lookup"><span data-stu-id="fdc27-129">UPDELE</span></span>](updele.md)
  
> 
    
[<span data-ttu-id="fdc27-130">UPFLD</span><span class="sxs-lookup"><span data-stu-id="fdc27-130">UPFLD</span></span>](upfld.md)
  
> 
    
[<span data-ttu-id="fdc27-131">UPHIER</span><span class="sxs-lookup"><span data-stu-id="fdc27-131">UPHIER</span></span>](uphier.md)
  
> 
    
[<span data-ttu-id="fdc27-132">UPMOV</span><span class="sxs-lookup"><span data-stu-id="fdc27-132">UPMOV</span></span>](upmov.md)
  
> 
    
[<span data-ttu-id="fdc27-133">UPMSG</span><span class="sxs-lookup"><span data-stu-id="fdc27-133">UPMSG</span></span>](upmsg.md)
  
> 
    
[<span data-ttu-id="fdc27-134">UPREAD</span><span class="sxs-lookup"><span data-stu-id="fdc27-134">UPREAD</span></span>](upread.md)
  
> 
    
[<span data-ttu-id="fdc27-135">UPREADE</span><span class="sxs-lookup"><span data-stu-id="fdc27-135">UPREADE</span></span>](upreade.md)
  
> 
    
[<span data-ttu-id="fdc27-136">UPTBL</span><span class="sxs-lookup"><span data-stu-id="fdc27-136">UPTBL</span></span>](uptbl.md)
  
> 
    
[<span data-ttu-id="fdc27-137">UPTBLE</span><span class="sxs-lookup"><span data-stu-id="fdc27-137">UPTBLE</span></span>](uptble.md)
  
> 
    
## <a name="remarks"></a><span data-ttu-id="fdc27-138">注解</span><span class="sxs-lookup"><span data-stu-id="fdc27-138">Remarks</span></span>

<span data-ttu-id="fdc27-139">客户端调用**[IOSTX:: SetSyncResult](iostx-setsyncresult.md)** 设置同步的结果, 然后调用**[IOSTX:: SyncEnd](iostx-syncend.md)** 结束该状态。</span><span class="sxs-lookup"><span data-stu-id="fdc27-139">The client calls **[IOSTX::SetSyncResult](iostx-setsyncresult.md)** to set the result of the synchronization, and then calls **[IOSTX::SyncEnd](iostx-syncend.md)** to end that state.</span></span> <span data-ttu-id="fdc27-140">客户端必须为对**IOSTX:: SyncBeg**的每个调用调用**[IOSTX:: SyncEnd](iostx-syncend.md)** , 以确定状态是否已成功复制。</span><span class="sxs-lookup"><span data-stu-id="fdc27-140">The client must call **[IOSTX::SyncEnd](iostx-syncend.md)** for each call to **IOSTX::SyncBeg** in order to determine whether the state has been successfully replicated.</span></span> <span data-ttu-id="fdc27-141">确定后, Outlook 可以开始清理其内部状态。</span><span class="sxs-lookup"><span data-stu-id="fdc27-141">Once this has been determined, Outlook can begin to clean up its internal state.</span></span> 
  
<span data-ttu-id="fdc27-142">大多数结构都包含 [out]/[in] 信息, 使 Outlook 能够将信息传递到客户端, 以及将信息传递给 Outlook 的客户端。</span><span class="sxs-lookup"><span data-stu-id="fdc27-142">Most of these structures contain [out]/[in] information, allowing Outlook to pass information to the client, and the client to pass information to Outlook.</span></span> <span data-ttu-id="fdc27-143">当客户端调用**IOSTX:: SyncBeg**时, Outlook 将为给定状态分配数据结构, 并使用该状态的信息对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="fdc27-143">When the client calls **IOSTX::SyncBeg**, Outlook allocates the data structure for a given state and initializes it with information for that state.</span></span> <span data-ttu-id="fdc27-144">这是 [输出] 信息。</span><span class="sxs-lookup"><span data-stu-id="fdc27-144">This is the [out] information.</span></span> <span data-ttu-id="fdc27-145">在状态下, 客户端更新该状态对应的数据结构。</span><span class="sxs-lookup"><span data-stu-id="fdc27-145">While in a state, the client updates the corresponding data structure for that state.</span></span> <span data-ttu-id="fdc27-146">这是 [!] 信息。</span><span class="sxs-lookup"><span data-stu-id="fdc27-146">This is the [in] information.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fdc27-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdc27-147">See also</span></span>



[<span data-ttu-id="fdc27-148">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="fdc27-148">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="fdc27-149">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="fdc27-149">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="fdc27-150">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="fdc27-150">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="fdc27-151">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="fdc27-151">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="fdc27-152">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="fdc27-152">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="fdc27-153">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="fdc27-153">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="fdc27-154">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fdc27-154">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="fdc27-155">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="fdc27-155">MAPI Constants</span></span>](mapi-constants.md)

