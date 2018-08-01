---
title: MAPIOFFLINE_NOTIFY
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e03c5a87-4513-2133-ae0a-11d242f80e4b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9d8eb3f2c52f20ffe57d84823a0ed736337b4d9b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776385"
---
# <a name="mapiofflinenotify"></a><span data-ttu-id="d9973-103">MAPIOFFLINE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="d9973-103">MAPIOFFLINE_NOTIFY</span></span>

<span data-ttu-id="d9973-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d9973-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d9973-105">这是处于连接状态更改通知。</span><span class="sxs-lookup"><span data-stu-id="d9973-105">This is the notification for a change in the connection state.</span></span> <span data-ttu-id="d9973-106">表示已更改的连接状态、 旧的连接状态和新的连接状态的一部分。</span><span class="sxs-lookup"><span data-stu-id="d9973-106">It indicates the part of the connection state that has changed, the old connection state, and the new connection state.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d9973-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="d9973-107">Quick info</span></span>

<span data-ttu-id="d9973-108">请参阅**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="d9973-108">See **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
  
```cpp
typedef struct  
{ 
      ULONG ulSize; 
      MAPIOFFLINE_NOTIFY_TYPE NotifyType; 
      ULONG ulClientToken; 
      union { 
         struct 
           { 
           ULONG ulMask; 
           ULONG ulStateOld; 
           ULONG ulStateNew; 
           } StateChange; 
             } Info; 
} MAPIOFFLINE_NOTIFY;
```

## <a name="members"></a><span data-ttu-id="d9973-109">Members</span><span class="sxs-lookup"><span data-stu-id="d9973-109">Members</span></span>

 <span data-ttu-id="d9973-110">_ulSize_</span><span class="sxs-lookup"><span data-stu-id="d9973-110">_ulSize_</span></span>
  
> <span data-ttu-id="d9973-111">**MAPIOFFLINE_NOTIFY**结构大小。</span><span class="sxs-lookup"><span data-stu-id="d9973-111">Size of the **MAPIOFFLINE_NOTIFY** structure.</span></span> 
    
 <span data-ttu-id="d9973-112">_NotifyType_</span><span class="sxs-lookup"><span data-stu-id="d9973-112">_NotifyType_</span></span>
  
> <span data-ttu-id="d9973-113">通知类型。</span><span class="sxs-lookup"><span data-stu-id="d9973-113">Type of notification.</span></span> <span data-ttu-id="d9973-114">请注意，仅通知上的连接状态更改支持;仅支持的值包括：</span><span class="sxs-lookup"><span data-stu-id="d9973-114">Note that only notification on change of the connection state is supported; the only supported values are:</span></span>
    
   - <span data-ttu-id="d9973-115">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START</span><span class="sxs-lookup"><span data-stu-id="d9973-115">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START</span></span>
    
   - <span data-ttu-id="d9973-116">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE</span><span class="sxs-lookup"><span data-stu-id="d9973-116">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE</span></span>
    
   - <span data-ttu-id="d9973-117">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE</span><span class="sxs-lookup"><span data-stu-id="d9973-117">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE</span></span>
    
 <span data-ttu-id="d9973-118">_ulClientToken_</span><span class="sxs-lookup"><span data-stu-id="d9973-118">_ulClientToken_</span></span>
  
> <span data-ttu-id="d9973-119">定义由客户端在**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 的**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 结构中的标记。</span><span class="sxs-lookup"><span data-stu-id="d9973-119">A token defined by the client in the **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** structure in **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> 
    
 <span data-ttu-id="d9973-120">_ulMask_</span><span class="sxs-lookup"><span data-stu-id="d9973-120">_ulMask_</span></span>
  
> <span data-ttu-id="d9973-121">连接状态的已更改的一部分。</span><span class="sxs-lookup"><span data-stu-id="d9973-121">The part of the connection state that has changed.</span></span> <span data-ttu-id="d9973-122">仅受支持的值是 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="d9973-122">The only supported value is MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span>
    
 <span data-ttu-id="d9973-123">_ulStateOld_</span><span class="sxs-lookup"><span data-stu-id="d9973-123">_ulStateOld_</span></span>
  
> <span data-ttu-id="d9973-124">旧的连接状态。</span><span class="sxs-lookup"><span data-stu-id="d9973-124">The old connection state.</span></span> <span data-ttu-id="d9973-125">仅支持的值包括：</span><span class="sxs-lookup"><span data-stu-id="d9973-125">The only supported values are:</span></span>
    
   - <span data-ttu-id="d9973-126">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="d9973-126">MAPIOFFLINE_STATE_OFFLINE</span></span>
    
   - <span data-ttu-id="d9973-127">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="d9973-127">MAPIOFFLINE_STATE_ONLINE</span></span>
    
 <span data-ttu-id="d9973-128">_ulStateNew_</span><span class="sxs-lookup"><span data-stu-id="d9973-128">_ulStateNew_</span></span>
  
> <span data-ttu-id="d9973-129">新的连接状态。</span><span class="sxs-lookup"><span data-stu-id="d9973-129">The new connection state.</span></span> <span data-ttu-id="d9973-130">仅支持的值包括：</span><span class="sxs-lookup"><span data-stu-id="d9973-130">The only supported values are:</span></span>
    
   - <span data-ttu-id="d9973-131">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="d9973-131">MAPIOFFLINE_STATE_OFFLINE</span></span>
    
   - <span data-ttu-id="d9973-132">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="d9973-132">MAPIOFFLINE_STATE_ONLINE</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d9973-133">说明</span><span class="sxs-lookup"><span data-stu-id="d9973-133">Remarks</span></span>

<span data-ttu-id="d9973-134">脱机状态 API 支持联机/脱机更改仅通知。</span><span class="sxs-lookup"><span data-stu-id="d9973-134">The Offline State API supports only notifications for online/offline changes.</span></span> <span data-ttu-id="d9973-135">客户端必须检查的 Outlook 检查实际更改之前将返回以下值：</span><span class="sxs-lookup"><span data-stu-id="d9973-135">A client must check that Outlook returns the following values before examining the actual change:</span></span>
  
1.  <span data-ttu-id="d9973-136">*NotifyType*有 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START、 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE 或 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE 值。</span><span class="sxs-lookup"><span data-stu-id="d9973-136">*NotifyType*  has the value MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START, MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE, or MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE.</span></span> <span data-ttu-id="d9973-137">在这种情况下，客户端可以假设已更改的更改的连接状态*信息*的*状态*的结构。</span><span class="sxs-lookup"><span data-stu-id="d9973-137">In this case, the client can assume that the change is a connection state change, and  *Info*  is of the structure  *StateChange*  .</span></span> 
    
2.  <span data-ttu-id="d9973-138">*ulMask*有值 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="d9973-138">*ulMask*  has the value MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span> <span data-ttu-id="d9973-139">在这种情况下，客户端可以假定更改是联机/脱机连接的状态更改，并可以继续进行检查*ulStateOld*和*ulStateNew* 。</span><span class="sxs-lookup"><span data-stu-id="d9973-139">In this case, the client can assume that the change is an online/offline connection state change, and can proceed with examining  *ulStateOld*  and  *ulStateNew*  .</span></span> 
    
<span data-ttu-id="d9973-140">则可能 Outlook 通知不支持其他更改的客户端。</span><span class="sxs-lookup"><span data-stu-id="d9973-140">It is possible that Outlook notifies a client of other changes that are not supported.</span></span> <span data-ttu-id="d9973-141">在这种情况下， *NotifyType*不会任一前面所述的三个值或*ulMask*不会 MAPIOFFLINE_STATE_OFFLINE_MASK，和客户端必须忽略*信息*中数据的其余部分。</span><span class="sxs-lookup"><span data-stu-id="d9973-141">In such cases,  *NotifyType*  would not be any one of the three values stated previously, or  *ulMask*  would not be MAPIOFFLINE_STATE_OFFLINE_MASK, and the client must ignore the rest of the data in  *Info*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d9973-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9973-142">See also</span></span>

- [<span data-ttu-id="d9973-143">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="d9973-143">About the Offline State API</span></span>](about-the-offline-state-api.md)  
- [<span data-ttu-id="d9973-144">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d9973-144">MAPI Constants</span></span>](mapi-constants.md)  
- [<span data-ttu-id="d9973-145">MAPIOFFLINE_NOTIFY_TYPE</span><span class="sxs-lookup"><span data-stu-id="d9973-145">MAPIOFFLINE_NOTIFY_TYPE</span></span>](mapioffline_notify_type.md)

