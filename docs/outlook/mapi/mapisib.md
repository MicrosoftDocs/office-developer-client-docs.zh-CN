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
ms.openlocfilehash: a8044eb6647e6f437c87bb4d8b021c62ea15f606
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776393"
---
# <a name="mapisib"></a><span data-ttu-id="0cd88-103">MAPISIB</span><span class="sxs-lookup"><span data-stu-id="0cd88-103">MAPISIB</span></span>

  
  
<span data-ttu-id="0cd88-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0cd88-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0cd88-105">此结构用于[IMAPISync::SynchronizeInBackground](imapisyncsynchronizeinbackground.md)。</span><span class="sxs-lookup"><span data-stu-id="0cd88-105">This structure is used with [IMAPISync::SynchronizeInBackground](imapisyncsynchronizeinbackground.md).</span></span>
  
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

## <a name="members"></a><span data-ttu-id="0cd88-106">Members</span><span class="sxs-lookup"><span data-stu-id="0cd88-106">Members</span></span>

 <span data-ttu-id="0cd88-107">**ulSize**</span><span class="sxs-lookup"><span data-stu-id="0cd88-107">**ulSize**</span></span>
  
> <span data-ttu-id="0cd88-108">结构的大小。</span><span class="sxs-lookup"><span data-stu-id="0cd88-108">The size of the structure.</span></span>
    
 <span data-ttu-id="0cd88-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="0cd88-109">**ulFlags**</span></span>
  
> <span data-ttu-id="0cd88-110">指示的同步类型的标志。它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="0cd88-110">A flag that indicates the type of sync. It must be one of the following values:</span></span>
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="0cd88-111">SYNC_OUTGOING_MAIL</span><span class="sxs-lookup"><span data-stu-id="0cd88-111">SYNC_OUTGOING_MAIL</span></span>  <br/> |<span data-ttu-id="0cd88-112">0x00000200</span><span class="sxs-lookup"><span data-stu-id="0cd88-112">0x00000200</span></span>  <br/> |<span data-ttu-id="0cd88-113">向服务器 （当前未在使用） 发送消息。</span><span class="sxs-lookup"><span data-stu-id="0cd88-113">Send the message to the server (not currently in use).</span></span>  <br/> |
|<span data-ttu-id="0cd88-114">SYNC_UPLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="0cd88-114">SYNC_UPLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="0cd88-115">0x00000001</span><span class="sxs-lookup"><span data-stu-id="0cd88-115">0x00000001</span></span>  <br/> |<span data-ttu-id="0cd88-116">层次结构更改推送到服务器。</span><span class="sxs-lookup"><span data-stu-id="0cd88-116">Push hierarchy changes to the server.</span></span>  <br/> |
|<span data-ttu-id="0cd88-117">SYNC_DOWNLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="0cd88-117">SYNC_DOWNLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="0cd88-118">0x00000002</span><span class="sxs-lookup"><span data-stu-id="0cd88-118">0x00000002</span></span>  <br/> |<span data-ttu-id="0cd88-119">从服务器中提取层次结构更改。</span><span class="sxs-lookup"><span data-stu-id="0cd88-119">Pull hierarchy changes from server.</span></span>  <br/> |
|<span data-ttu-id="0cd88-120">SYNC_UPLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="0cd88-120">SYNC_UPLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="0cd88-121">0x00000040</span><span class="sxs-lookup"><span data-stu-id="0cd88-121">0x00000040</span></span>  <br/> |<span data-ttu-id="0cd88-122">消息更改推送到服务器。</span><span class="sxs-lookup"><span data-stu-id="0cd88-122">Push message changes to server.</span></span>  <br/> |
|<span data-ttu-id="0cd88-123">SYNC_DOWNLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="0cd88-123">SYNC_DOWNLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="0cd88-124">0x00000080</span><span class="sxs-lookup"><span data-stu-id="0cd88-124">0x00000080</span></span>  <br/> |<span data-ttu-id="0cd88-125">从服务器中提取消息更改。</span><span class="sxs-lookup"><span data-stu-id="0cd88-125">Pull message changes from server.</span></span>  <br/> |
|<span data-ttu-id="0cd88-126">SYNC_ON_DEMAND</span><span class="sxs-lookup"><span data-stu-id="0cd88-126">SYNC_ON_DEMAND</span></span>  <br/> |<span data-ttu-id="0cd88-127">0x20000000</span><span class="sxs-lookup"><span data-stu-id="0cd88-127">0x20000000</span></span>  <br/> |<span data-ttu-id="0cd88-128">同步用户启动，并且应更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="0cd88-128">The sync was initiated by the user and should be a higher priority.</span></span>  <br/> |
|<span data-ttu-id="0cd88-129">SYNC_GLOBAL_HEADERS</span><span class="sxs-lookup"><span data-stu-id="0cd88-129">SYNC_GLOBAL_HEADERS</span></span>  <br/> |<span data-ttu-id="0cd88-130">0x02000000</span><span class="sxs-lookup"><span data-stu-id="0cd88-130">0x02000000</span></span>  <br/> |<span data-ttu-id="0cd88-131">应仅同步邮件头和不完整的正文。</span><span class="sxs-lookup"><span data-stu-id="0cd88-131">Should only sync headers and not full bodies.</span></span>  <br/> |
   
 <span data-ttu-id="0cd88-132">**psesSync**</span><span class="sxs-lookup"><span data-stu-id="0cd88-132">**psesSync**</span></span>
  
> <span data-ttu-id="0cd88-133">[输入]一个指向 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="0cd88-133">[IN] A pointer to the MAPI session.</span></span>
    
 <span data-ttu-id="0cd88-134">**punkCallBack**</span><span class="sxs-lookup"><span data-stu-id="0cd88-134">**punkCallBack**</span></span>
  
> <span data-ttu-id="0cd88-135">[输入]指向要提供进度接口的指针。</span><span class="sxs-lookup"><span data-stu-id="0cd88-135">[IN] A pointer to the interface on which to provide progress.</span></span> <span data-ttu-id="0cd88-136">可用于查询的界面[IMAPISyncProgressCallback: IUnknown](imapisyncprogresscallbackiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="0cd88-136">It can be used to query the interface for [IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md).</span></span>
    
 <span data-ttu-id="0cd88-137">**\*phSyncDoneEvent**</span><span class="sxs-lookup"><span data-stu-id="0cd88-137">**\*phSyncDoneEvent**</span></span>
  
> <span data-ttu-id="0cd88-138">[输出]刚刚创建的线程完成时，则会发生该事件。</span><span class="sxs-lookup"><span data-stu-id="0cd88-138">[OUT] The event that will occur when the thread that was just created is complete.</span></span> <span data-ttu-id="0cd88-139">指针必须是有效，因为它会包含该事件。</span><span class="sxs-lookup"><span data-stu-id="0cd88-139">The pointer must be valid because it will contain the event.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0cd88-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cd88-140">See also</span></span>



[<span data-ttu-id="0cd88-141">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0cd88-141">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)
  
[<span data-ttu-id="0cd88-142">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0cd88-142">IMAPISync : IUnknown</span></span>](imapisynciunknown.md)

