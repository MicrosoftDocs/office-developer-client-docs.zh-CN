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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ddc61aa42b1087ed5f0ecb7986125ceef27cddce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775954"
---
# <a name="iostxsyncbeg"></a><span data-ttu-id="4a19c-103">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="4a19c-103">IOSTX::SyncBeg</span></span>

  
  
<span data-ttu-id="4a19c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4a19c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4a19c-105">为特定状态同步准备本地存储并检索复制的必需信息。</span><span class="sxs-lookup"><span data-stu-id="4a19c-105">Prepares the local store for synchronization in a particular state and retrieves the necessary information to replicate.</span></span>
  
```cpp
HRESULT SyncBeg( 
    UINT uiSync, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a><span data-ttu-id="4a19c-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a19c-106">Parameters</span></span>

 <span data-ttu-id="4a19c-107">_uiSync_</span><span class="sxs-lookup"><span data-stu-id="4a19c-107">_uiSync_</span></span>
  
>  <span data-ttu-id="4a19c-108">[in]将输入本地存储的状态。</span><span class="sxs-lookup"><span data-stu-id="4a19c-108">[in] The state that the local store will enter.</span></span> <span data-ttu-id="4a19c-109">以下是状态标识符都的列表：</span><span class="sxs-lookup"><span data-stu-id="4a19c-109">The following is a list of state identifers:</span></span> 
    
<span data-ttu-id="4a19c-110">LR_SYNC_IDLE</span><span class="sxs-lookup"><span data-stu-id="4a19c-110">LR_SYNC_IDLE</span></span>
  
> 
    
<span data-ttu-id="4a19c-111">LR_SYNC</span><span class="sxs-lookup"><span data-stu-id="4a19c-111">LR_SYNC</span></span>
  
> 
    
<span data-ttu-id="4a19c-112">LR_SYNC_UPLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="4a19c-112">LR_SYNC_UPLOAD_HIERARCHY</span></span>
  
> 
    
<span data-ttu-id="4a19c-113">LR_SYNC_UPLOAD_FOLDER</span><span class="sxs-lookup"><span data-stu-id="4a19c-113">LR_SYNC_UPLOAD_FOLDER</span></span>
  
> 
    
<span data-ttu-id="4a19c-114">LR_SYNC_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="4a19c-114">LR_SYNC_CONTENTS</span></span>
  
> 
    
<span data-ttu-id="4a19c-115">LR_SYNC_UPLOAD_TABLE</span><span class="sxs-lookup"><span data-stu-id="4a19c-115">LR_SYNC_UPLOAD_TABLE</span></span>
  
> 
    
<span data-ttu-id="4a19c-116">LR_SYNC_UPLOAD_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="4a19c-116">LR_SYNC_UPLOAD_MESSAGE</span></span>
  
> 
    
<span data-ttu-id="4a19c-117">LR_SYNC_UPLOAD_MESSAGE_READ</span><span class="sxs-lookup"><span data-stu-id="4a19c-117">LR_SYNC_UPLOAD_MESSAGE_READ</span></span>
  
> 
    
<span data-ttu-id="4a19c-118">LR_SYNC_UPLOAD_MESSAGE_DEL</span><span class="sxs-lookup"><span data-stu-id="4a19c-118">LR_SYNC_UPLOAD_MESSAGE_DEL</span></span>
  
> 
    
<span data-ttu-id="4a19c-119">LR_SYNC_DOWNLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="4a19c-119">LR_SYNC_DOWNLOAD_HIERARCHY</span></span>
  
> 
    
<span data-ttu-id="4a19c-120">LR_SYNC_DOWNLOAD_TABLE</span><span class="sxs-lookup"><span data-stu-id="4a19c-120">LR_SYNC_DOWNLOAD_TABLE</span></span>
  
> 
    
 <span data-ttu-id="4a19c-121">_ppv_</span><span class="sxs-lookup"><span data-stu-id="4a19c-121">_ppv_</span></span>
  
>  <span data-ttu-id="4a19c-122">[in] / [输出] 指向状态相对应的数据结构输入。</span><span class="sxs-lookup"><span data-stu-id="4a19c-122">[in]/[out] Pointer to the data structure corresponding to the state to enter.</span></span> 
    
[<span data-ttu-id="4a19c-123">DNHIER</span><span class="sxs-lookup"><span data-stu-id="4a19c-123">DNHIER</span></span>](dnhier.md)
  
> 
    
[<span data-ttu-id="4a19c-124">DNTBL</span><span class="sxs-lookup"><span data-stu-id="4a19c-124">DNTBL</span></span>](dntbl.md)
  
> 
    
[<span data-ttu-id="4a19c-125">DNTBL</span><span class="sxs-lookup"><span data-stu-id="4a19c-125">DNTBL</span></span>](dntbl.md)
  
> 
    
[<span data-ttu-id="4a19c-126">SYNC</span><span class="sxs-lookup"><span data-stu-id="4a19c-126">SYNC</span></span>](sync.md)
  
> 
    
[<span data-ttu-id="4a19c-127">SYNCCONT</span><span class="sxs-lookup"><span data-stu-id="4a19c-127">SYNCCONT</span></span>](synccont.md)
  
> 
    
[<span data-ttu-id="4a19c-128">UPDEL</span><span class="sxs-lookup"><span data-stu-id="4a19c-128">UPDEL</span></span>](updel.md)
  
> 
    
[<span data-ttu-id="4a19c-129">UPDELE</span><span class="sxs-lookup"><span data-stu-id="4a19c-129">UPDELE</span></span>](updele.md)
  
> 
    
[<span data-ttu-id="4a19c-130">UPFLD</span><span class="sxs-lookup"><span data-stu-id="4a19c-130">UPFLD</span></span>](upfld.md)
  
> 
    
[<span data-ttu-id="4a19c-131">UPHIER</span><span class="sxs-lookup"><span data-stu-id="4a19c-131">UPHIER</span></span>](uphier.md)
  
> 
    
[<span data-ttu-id="4a19c-132">UPMOV</span><span class="sxs-lookup"><span data-stu-id="4a19c-132">UPMOV</span></span>](upmov.md)
  
> 
    
[<span data-ttu-id="4a19c-133">UPMSG</span><span class="sxs-lookup"><span data-stu-id="4a19c-133">UPMSG</span></span>](upmsg.md)
  
> 
    
[<span data-ttu-id="4a19c-134">UPREAD</span><span class="sxs-lookup"><span data-stu-id="4a19c-134">UPREAD</span></span>](upread.md)
  
> 
    
[<span data-ttu-id="4a19c-135">UPREADE</span><span class="sxs-lookup"><span data-stu-id="4a19c-135">UPREADE</span></span>](upreade.md)
  
> 
    
[<span data-ttu-id="4a19c-136">UPTBL</span><span class="sxs-lookup"><span data-stu-id="4a19c-136">UPTBL</span></span>](uptbl.md)
  
> 
    
[<span data-ttu-id="4a19c-137">UPTBLE</span><span class="sxs-lookup"><span data-stu-id="4a19c-137">UPTBLE</span></span>](uptble.md)
  
> 
    
## <a name="remarks"></a><span data-ttu-id="4a19c-138">说明</span><span class="sxs-lookup"><span data-stu-id="4a19c-138">Remarks</span></span>

<span data-ttu-id="4a19c-139">客户端调用**[IOSTX::SetSyncResult](iostx-setsyncresult.md)** 将同步的结果设置，然后调用**[IOSTX::SyncEnd](iostx-syncend.md)** 结束该状态。</span><span class="sxs-lookup"><span data-stu-id="4a19c-139">The client calls **[IOSTX::SetSyncResult](iostx-setsyncresult.md)** to set the result of the synchronization, and then calls **[IOSTX::SyncEnd](iostx-syncend.md)** to end that state.</span></span> <span data-ttu-id="4a19c-140">客户端必须为**IOSTX::SyncBeg**来确定状态是否已成功复制每个呼叫的呼叫**[IOSTX::SyncEnd](iostx-syncend.md)** 。</span><span class="sxs-lookup"><span data-stu-id="4a19c-140">The client must call **[IOSTX::SyncEnd](iostx-syncend.md)** for each call to **IOSTX::SyncBeg** in order to determine whether the state has been successfully replicated.</span></span> <span data-ttu-id="4a19c-141">一旦确定此，可以开始 Outlook 清理其内部状态。</span><span class="sxs-lookup"><span data-stu-id="4a19c-141">Once this has been determined, Outlook can begin to clean up its internal state.</span></span> 
  
<span data-ttu-id="4a19c-142">[输出] 包含这些结构大部分 / [in] 允许 Outlook 将信息传递给客户端，并将信息传递到 Outlook 客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="4a19c-142">Most of these structures contain [out]/[in] information, allowing Outlook to pass information to the client, and the client to pass information to Outlook.</span></span> <span data-ttu-id="4a19c-143">当客户端调用**IOSTX::SyncBeg**时，Outlook 将给定的状态分配的数据结构，并且使用其初始化的状态信息。</span><span class="sxs-lookup"><span data-stu-id="4a19c-143">When the client calls **IOSTX::SyncBeg**, Outlook allocates the data structure for a given state and initializes it with information for that state.</span></span> <span data-ttu-id="4a19c-144">这是 [out] 的信息。</span><span class="sxs-lookup"><span data-stu-id="4a19c-144">This is the [out] information.</span></span> <span data-ttu-id="4a19c-145">在状态下，客户端更新该状态的相应数据结构。</span><span class="sxs-lookup"><span data-stu-id="4a19c-145">While in a state, the client updates the corresponding data structure for that state.</span></span> <span data-ttu-id="4a19c-146">这是 [in] 此信息。</span><span class="sxs-lookup"><span data-stu-id="4a19c-146">This is the [in] information.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4a19c-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a19c-147">See also</span></span>



[<span data-ttu-id="4a19c-148">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="4a19c-148">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="4a19c-149">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="4a19c-149">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="4a19c-150">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="4a19c-150">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="4a19c-151">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="4a19c-151">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="4a19c-152">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="4a19c-152">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="4a19c-153">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="4a19c-153">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="4a19c-154">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4a19c-154">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="4a19c-155">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="4a19c-155">MAPI Constants</span></span>](mapi-constants.md)

