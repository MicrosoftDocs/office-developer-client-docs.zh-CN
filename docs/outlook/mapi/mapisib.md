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
ms.openlocfilehash: f696d9739014659812de3309ec885f37a6f85cc5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572135"
---
# <a name="mapisib"></a><span data-ttu-id="c05bb-103">MAPISIB</span><span class="sxs-lookup"><span data-stu-id="c05bb-103">MAPISIB</span></span>

  
  
<span data-ttu-id="c05bb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c05bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c05bb-105">此结构用于[IMAPISync::SynchronizeInBackground](imapisyncsynchronizeinbackground.md)。</span><span class="sxs-lookup"><span data-stu-id="c05bb-105">This structure is used with [IMAPISync::SynchronizeInBackground](imapisyncsynchronizeinbackground.md).</span></span>
  
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

## <a name="members"></a><span data-ttu-id="c05bb-106">Members</span><span class="sxs-lookup"><span data-stu-id="c05bb-106">Members</span></span>

 <span data-ttu-id="c05bb-107">**ulSize**</span><span class="sxs-lookup"><span data-stu-id="c05bb-107">**ulSize**</span></span>
  
> <span data-ttu-id="c05bb-108">结构的大小。</span><span class="sxs-lookup"><span data-stu-id="c05bb-108">The size of the structure.</span></span>
    
 <span data-ttu-id="c05bb-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="c05bb-109">**ulFlags**</span></span>
  
> <span data-ttu-id="c05bb-110">指示的同步类型的标志。它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="c05bb-110">A flag that indicates the type of sync. It must be one of the following values:</span></span>
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="c05bb-111">SYNC_OUTGOING_MAIL</span><span class="sxs-lookup"><span data-stu-id="c05bb-111">SYNC_OUTGOING_MAIL</span></span>  <br/> |<span data-ttu-id="c05bb-112">0x00000200</span><span class="sxs-lookup"><span data-stu-id="c05bb-112">0x00000200</span></span>  <br/> |<span data-ttu-id="c05bb-113">向服务器 （当前未在使用） 发送消息。</span><span class="sxs-lookup"><span data-stu-id="c05bb-113">Send the message to the server (not currently in use).</span></span>  <br/> |
|<span data-ttu-id="c05bb-114">SYNC_UPLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="c05bb-114">SYNC_UPLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="c05bb-115">0x00000001</span><span class="sxs-lookup"><span data-stu-id="c05bb-115">0x00000001</span></span>  <br/> |<span data-ttu-id="c05bb-116">层次结构更改推送到服务器。</span><span class="sxs-lookup"><span data-stu-id="c05bb-116">Push hierarchy changes to the server.</span></span>  <br/> |
|<span data-ttu-id="c05bb-117">SYNC_DOWNLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="c05bb-117">SYNC_DOWNLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="c05bb-118">0x00000002</span><span class="sxs-lookup"><span data-stu-id="c05bb-118">0x00000002</span></span>  <br/> |<span data-ttu-id="c05bb-119">从服务器中提取层次结构更改。</span><span class="sxs-lookup"><span data-stu-id="c05bb-119">Pull hierarchy changes from server.</span></span>  <br/> |
|<span data-ttu-id="c05bb-120">SYNC_UPLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="c05bb-120">SYNC_UPLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="c05bb-121">0x00000040</span><span class="sxs-lookup"><span data-stu-id="c05bb-121">0x00000040</span></span>  <br/> |<span data-ttu-id="c05bb-122">消息更改推送到服务器。</span><span class="sxs-lookup"><span data-stu-id="c05bb-122">Push message changes to server.</span></span>  <br/> |
|<span data-ttu-id="c05bb-123">SYNC_DOWNLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="c05bb-123">SYNC_DOWNLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="c05bb-124">0x00000080</span><span class="sxs-lookup"><span data-stu-id="c05bb-124">0x00000080</span></span>  <br/> |<span data-ttu-id="c05bb-125">从服务器中提取消息更改。</span><span class="sxs-lookup"><span data-stu-id="c05bb-125">Pull message changes from server.</span></span>  <br/> |
|<span data-ttu-id="c05bb-126">SYNC_ON_DEMAND</span><span class="sxs-lookup"><span data-stu-id="c05bb-126">SYNC_ON_DEMAND</span></span>  <br/> |<span data-ttu-id="c05bb-127">0x20000000</span><span class="sxs-lookup"><span data-stu-id="c05bb-127">0x20000000</span></span>  <br/> |<span data-ttu-id="c05bb-128">同步用户启动，并且应更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="c05bb-128">The sync was initiated by the user and should be a higher priority.</span></span>  <br/> |
|<span data-ttu-id="c05bb-129">SYNC_GLOBAL_HEADERS</span><span class="sxs-lookup"><span data-stu-id="c05bb-129">SYNC_GLOBAL_HEADERS</span></span>  <br/> |<span data-ttu-id="c05bb-130">0x02000000</span><span class="sxs-lookup"><span data-stu-id="c05bb-130">0x02000000</span></span>  <br/> |<span data-ttu-id="c05bb-131">应仅同步邮件头和不完整的正文。</span><span class="sxs-lookup"><span data-stu-id="c05bb-131">Should only sync headers and not full bodies.</span></span>  <br/> |
   
 <span data-ttu-id="c05bb-132">**psesSync**</span><span class="sxs-lookup"><span data-stu-id="c05bb-132">**psesSync**</span></span>
  
> <span data-ttu-id="c05bb-133">[输入]一个指向 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="c05bb-133">[IN] A pointer to the MAPI session.</span></span>
    
 <span data-ttu-id="c05bb-134">**punkCallBack**</span><span class="sxs-lookup"><span data-stu-id="c05bb-134">**punkCallBack**</span></span>
  
> <span data-ttu-id="c05bb-135">[输入]指向要提供进度接口的指针。</span><span class="sxs-lookup"><span data-stu-id="c05bb-135">[IN] A pointer to the interface on which to provide progress.</span></span> <span data-ttu-id="c05bb-136">可用于查询的界面[IMAPISyncProgressCallback: IUnknown](imapisyncprogresscallbackiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="c05bb-136">It can be used to query the interface for [IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md).</span></span>
    
 <span data-ttu-id="c05bb-137">**\*phSyncDoneEvent**</span><span class="sxs-lookup"><span data-stu-id="c05bb-137">**\*phSyncDoneEvent**</span></span>
  
> <span data-ttu-id="c05bb-138">[输出]刚刚创建的线程完成时，则会发生该事件。</span><span class="sxs-lookup"><span data-stu-id="c05bb-138">[OUT] The event that will occur when the thread that was just created is complete.</span></span> <span data-ttu-id="c05bb-139">指针必须是有效，因为它会包含该事件。</span><span class="sxs-lookup"><span data-stu-id="c05bb-139">The pointer must be valid because it will contain the event.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c05bb-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c05bb-140">See also</span></span>



[<span data-ttu-id="c05bb-141">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c05bb-141">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)
  
[<span data-ttu-id="c05bb-142">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c05bb-142">IMAPISync : IUnknown</span></span>](imapisynciunknown.md)

