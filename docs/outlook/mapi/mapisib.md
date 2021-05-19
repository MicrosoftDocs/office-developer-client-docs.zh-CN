---
title: MAPISIB
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 16452798-7a95-43da-b95e-908debcea050
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cbda978a0d69367e95f9b4b1f53fd6d03b113ccc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418706"
---
# <a name="mapisib"></a><span data-ttu-id="08dd4-103">MAPISIB</span><span class="sxs-lookup"><span data-stu-id="08dd4-103">MAPISIB</span></span>

  
  
<span data-ttu-id="08dd4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08dd4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08dd4-105">此结构与 [IMAPISync：：SynchronizeInBackground 一起使用](imapisyncsynchronizeinbackground.md)。</span><span class="sxs-lookup"><span data-stu-id="08dd4-105">This structure is used with [IMAPISync::SynchronizeInBackground](imapisyncsynchronizeinbackground.md).</span></span>
  
```cpp
typedef struct _MAPISIB
{
ULONG           ulSize;                
ULONG           ulFlags;
LPMAPISESSION   psesSync;
LPUNKNOWN       punkCallBack;
HANDLE          *phSyncDoneEvent;    
} MAPISIB, *PMAPISIB
```

## <a name="members"></a><span data-ttu-id="08dd4-106">Members</span><span class="sxs-lookup"><span data-stu-id="08dd4-106">Members</span></span>

 <span data-ttu-id="08dd4-107">**ulSize**</span><span class="sxs-lookup"><span data-stu-id="08dd4-107">**ulSize**</span></span>
  
> <span data-ttu-id="08dd4-108">结构的大小。</span><span class="sxs-lookup"><span data-stu-id="08dd4-108">The size of the structure.</span></span>
    
 <span data-ttu-id="08dd4-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="08dd4-109">**ulFlags**</span></span>
  
> <span data-ttu-id="08dd4-110">指示同步类型的标志。它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="08dd4-110">A flag that indicates the type of sync. It must be one of the following values:</span></span>
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="08dd4-111">SYNC_OUTGOING_MAIL</span><span class="sxs-lookup"><span data-stu-id="08dd4-111">SYNC_OUTGOING_MAIL</span></span>  <br/> |<span data-ttu-id="08dd4-112">0x00000200</span><span class="sxs-lookup"><span data-stu-id="08dd4-112">0x00000200</span></span>  <br/> |<span data-ttu-id="08dd4-113">将邮件发送到当前 (使用的服务器) 。</span><span class="sxs-lookup"><span data-stu-id="08dd4-113">Send the message to the server (not currently in use).</span></span>  <br/> |
|<span data-ttu-id="08dd4-114">SYNC_UPLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="08dd4-114">SYNC_UPLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="08dd4-115">0x00000001</span><span class="sxs-lookup"><span data-stu-id="08dd4-115">0x00000001</span></span>  <br/> |<span data-ttu-id="08dd4-116">将层次结构更改推送到服务器。</span><span class="sxs-lookup"><span data-stu-id="08dd4-116">Push hierarchy changes to the server.</span></span>  <br/> |
|<span data-ttu-id="08dd4-117">SYNC_DOWNLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="08dd4-117">SYNC_DOWNLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="08dd4-118">0x00000002</span><span class="sxs-lookup"><span data-stu-id="08dd4-118">0x00000002</span></span>  <br/> |<span data-ttu-id="08dd4-119">从服务器拉取层次结构更改。</span><span class="sxs-lookup"><span data-stu-id="08dd4-119">Pull hierarchy changes from server.</span></span>  <br/> |
|<span data-ttu-id="08dd4-120">SYNC_UPLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="08dd4-120">SYNC_UPLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="08dd4-121">0x00000040</span><span class="sxs-lookup"><span data-stu-id="08dd4-121">0x00000040</span></span>  <br/> |<span data-ttu-id="08dd4-122">将邮件更改推送到服务器。</span><span class="sxs-lookup"><span data-stu-id="08dd4-122">Push message changes to server.</span></span>  <br/> |
|<span data-ttu-id="08dd4-123">SYNC_DOWNLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="08dd4-123">SYNC_DOWNLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="08dd4-124">0x00000080</span><span class="sxs-lookup"><span data-stu-id="08dd4-124">0x00000080</span></span>  <br/> |<span data-ttu-id="08dd4-125">从服务器拉取邮件更改。</span><span class="sxs-lookup"><span data-stu-id="08dd4-125">Pull message changes from server.</span></span>  <br/> |
|<span data-ttu-id="08dd4-126">SYNC_ON_DEMAND</span><span class="sxs-lookup"><span data-stu-id="08dd4-126">SYNC_ON_DEMAND</span></span>  <br/> |<span data-ttu-id="08dd4-127">0x20000000</span><span class="sxs-lookup"><span data-stu-id="08dd4-127">0x20000000</span></span>  <br/> |<span data-ttu-id="08dd4-128">同步由用户启动，并且应具有更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="08dd4-128">The sync was initiated by the user and should be a higher priority.</span></span>  <br/> |
|<span data-ttu-id="08dd4-129">SYNC_GLOBAL_HEADERS</span><span class="sxs-lookup"><span data-stu-id="08dd4-129">SYNC_GLOBAL_HEADERS</span></span>  <br/> |<span data-ttu-id="08dd4-130">0x02000000</span><span class="sxs-lookup"><span data-stu-id="08dd4-130">0x02000000</span></span>  <br/> |<span data-ttu-id="08dd4-131">应仅同步标头，而不是完全正文。</span><span class="sxs-lookup"><span data-stu-id="08dd4-131">Should only sync headers and not full bodies.</span></span>  <br/> |
   
 <span data-ttu-id="08dd4-132">**psesSync**</span><span class="sxs-lookup"><span data-stu-id="08dd4-132">**psesSync**</span></span>
  
> <span data-ttu-id="08dd4-133">[IN]指向 MAPI 会话的指针。</span><span class="sxs-lookup"><span data-stu-id="08dd4-133">[IN] A pointer to the MAPI session.</span></span>
    
 <span data-ttu-id="08dd4-134">**punkCallBack**</span><span class="sxs-lookup"><span data-stu-id="08dd4-134">**punkCallBack**</span></span>
  
> <span data-ttu-id="08dd4-135">[IN]指向要提供进度的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="08dd4-135">[IN] A pointer to the interface on which to provide progress.</span></span> <span data-ttu-id="08dd4-136">它可用于查询 [IMAPISyncProgressCallback ： IUnknown 的接口](imapisyncprogresscallbackiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="08dd4-136">It can be used to query the interface for [IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md).</span></span>
    
 <span data-ttu-id="08dd4-137">**\*phSyncDoneEvent**</span><span class="sxs-lookup"><span data-stu-id="08dd4-137">**\*phSyncDoneEvent**</span></span>
  
> <span data-ttu-id="08dd4-138">[OUT]刚刚创建的线程完成时将发生的事件。</span><span class="sxs-lookup"><span data-stu-id="08dd4-138">[OUT] The event that will occur when the thread that was just created is complete.</span></span> <span data-ttu-id="08dd4-139">指针必须有效，因为它将包含 事件。</span><span class="sxs-lookup"><span data-stu-id="08dd4-139">The pointer must be valid because it will contain the event.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="08dd4-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08dd4-140">See also</span></span>



[<span data-ttu-id="08dd4-141">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08dd4-141">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)
  
[<span data-ttu-id="08dd4-142">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08dd4-142">IMAPISync : IUnknown</span></span>](imapisynciunknown.md)

