---
title: MAPIOFFLINE_NOTIFY
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e03c5a87-4513-2133-ae0a-11d242f80e4b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c5480a8f5e008c01c7ab8141317f5f19547ab10
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270292"
---
# <a name="mapiofflinenotify"></a><span data-ttu-id="f612f-103">MAPIOFFLINE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="f612f-103">MAPIOFFLINE_NOTIFY</span></span>

<span data-ttu-id="f612f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f612f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f612f-105">这是连接状态更改的通知。</span><span class="sxs-lookup"><span data-stu-id="f612f-105">This is the notification for a change in the connection state.</span></span> <span data-ttu-id="f612f-106">它指示已更改的连接状态部分、旧的连接状态和新的连接状态。</span><span class="sxs-lookup"><span data-stu-id="f612f-106">It indicates the part of the connection state that has changed, the old connection state, and the new connection state.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="f612f-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="f612f-107">Quick info</span></span>

<span data-ttu-id="f612f-108">请参阅**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="f612f-108">See **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
  
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

## <a name="members"></a><span data-ttu-id="f612f-109">Members</span><span class="sxs-lookup"><span data-stu-id="f612f-109">Members</span></span>

 <span data-ttu-id="f612f-110">_ulSize_</span><span class="sxs-lookup"><span data-stu-id="f612f-110">_ulSize_</span></span>
  
> <span data-ttu-id="f612f-111">**MAPIOFFLINE_NOTIFY**结构的大小。</span><span class="sxs-lookup"><span data-stu-id="f612f-111">Size of the **MAPIOFFLINE_NOTIFY** structure.</span></span> 
    
 <span data-ttu-id="f612f-112">_NotifyType_</span><span class="sxs-lookup"><span data-stu-id="f612f-112">_NotifyType_</span></span>
  
> <span data-ttu-id="f612f-113">通知的类型。</span><span class="sxs-lookup"><span data-stu-id="f612f-113">Type of notification.</span></span> <span data-ttu-id="f612f-114">请注意, 仅支持更改连接状态通知;唯一受支持的值是:</span><span class="sxs-lookup"><span data-stu-id="f612f-114">Note that only notification on change of the connection state is supported; the only supported values are:</span></span>
    
   - <span data-ttu-id="f612f-115">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START</span><span class="sxs-lookup"><span data-stu-id="f612f-115">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START</span></span>
    
   - <span data-ttu-id="f612f-116">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE</span><span class="sxs-lookup"><span data-stu-id="f612f-116">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE</span></span>
    
   - <span data-ttu-id="f612f-117">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE</span><span class="sxs-lookup"><span data-stu-id="f612f-117">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE</span></span>
    
 <span data-ttu-id="f612f-118">_ulClientToken_</span><span class="sxs-lookup"><span data-stu-id="f612f-118">_ulClientToken_</span></span>
  
> <span data-ttu-id="f612f-119">客户端在**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 的**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 结构中定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="f612f-119">A token defined by the client in the **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** structure in **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> 
    
 <span data-ttu-id="f612f-120">_ulMask_</span><span class="sxs-lookup"><span data-stu-id="f612f-120">_ulMask_</span></span>
  
> <span data-ttu-id="f612f-121">已更改的连接状态部分。</span><span class="sxs-lookup"><span data-stu-id="f612f-121">The part of the connection state that has changed.</span></span> <span data-ttu-id="f612f-122">唯一受支持的值为 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="f612f-122">The only supported value is MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span>
    
 <span data-ttu-id="f612f-123">_ulStateOld_</span><span class="sxs-lookup"><span data-stu-id="f612f-123">_ulStateOld_</span></span>
  
> <span data-ttu-id="f612f-124">旧的连接状态。</span><span class="sxs-lookup"><span data-stu-id="f612f-124">The old connection state.</span></span> <span data-ttu-id="f612f-125">唯一受支持的值是:</span><span class="sxs-lookup"><span data-stu-id="f612f-125">The only supported values are:</span></span>
    
   - <span data-ttu-id="f612f-126">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="f612f-126">MAPIOFFLINE_STATE_OFFLINE</span></span>
    
   - <span data-ttu-id="f612f-127">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="f612f-127">MAPIOFFLINE_STATE_ONLINE</span></span>
    
 <span data-ttu-id="f612f-128">_ulStateNew_</span><span class="sxs-lookup"><span data-stu-id="f612f-128">_ulStateNew_</span></span>
  
> <span data-ttu-id="f612f-129">新的连接状态。</span><span class="sxs-lookup"><span data-stu-id="f612f-129">The new connection state.</span></span> <span data-ttu-id="f612f-130">唯一受支持的值是:</span><span class="sxs-lookup"><span data-stu-id="f612f-130">The only supported values are:</span></span>
    
   - <span data-ttu-id="f612f-131">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="f612f-131">MAPIOFFLINE_STATE_OFFLINE</span></span>
    
   - <span data-ttu-id="f612f-132">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="f612f-132">MAPIOFFLINE_STATE_ONLINE</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f612f-133">注解</span><span class="sxs-lookup"><span data-stu-id="f612f-133">Remarks</span></span>

<span data-ttu-id="f612f-134">脱机状态 API 仅支持联机/脱机更改的通知。</span><span class="sxs-lookup"><span data-stu-id="f612f-134">The Offline State API supports only notifications for online/offline changes.</span></span> <span data-ttu-id="f612f-135">在检查实际更改之前, 客户端必须先检查 Outlook 是否返回以下值:</span><span class="sxs-lookup"><span data-stu-id="f612f-135">A client must check that Outlook returns the following values before examining the actual change:</span></span>
  
1.  <span data-ttu-id="f612f-136">*NotifyType*的值为 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START、MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE 或 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE。</span><span class="sxs-lookup"><span data-stu-id="f612f-136">*NotifyType*  has the value MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START, MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE, or MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE.</span></span> <span data-ttu-id="f612f-137">在这种情况下, 客户端可以假定更改是连接状态更改,*信息*的结构*StateChange* 。</span><span class="sxs-lookup"><span data-stu-id="f612f-137">In this case, the client can assume that the change is a connection state change, and  *Info*  is of the structure  *StateChange*  .</span></span> 
    
2.  <span data-ttu-id="f612f-138">*ulMask*的值为 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="f612f-138">*ulMask*  has the value MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span> <span data-ttu-id="f612f-139">在这种情况下, 客户端可以假定更改为联机/脱机连接状态更改, 并可继续检查*ulStateOld*和*ulStateNew* 。</span><span class="sxs-lookup"><span data-stu-id="f612f-139">In this case, the client can assume that the change is an online/offline connection state change, and can proceed with examining  *ulStateOld*  and  *ulStateNew*  .</span></span> 
    
<span data-ttu-id="f612f-140">Outlook 可能会向客户端通知不受支持的其他更改。</span><span class="sxs-lookup"><span data-stu-id="f612f-140">It is possible that Outlook notifies a client of other changes that are not supported.</span></span> <span data-ttu-id="f612f-141">在这种情况下, *NotifyType*不会是前面提到的三个值中的\*\* 任何一个, 否则, 客户端必须忽略*Info*中的其余数据。</span><span class="sxs-lookup"><span data-stu-id="f612f-141">In such cases,  *NotifyType*  would not be any one of the three values stated previously, or  *ulMask*  would not be MAPIOFFLINE_STATE_OFFLINE_MASK, and the client must ignore the rest of the data in  *Info*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f612f-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f612f-142">See also</span></span>

- [<span data-ttu-id="f612f-143">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="f612f-143">About the Offline State API</span></span>](about-the-offline-state-api.md)  
- [<span data-ttu-id="f612f-144">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f612f-144">MAPI Constants</span></span>](mapi-constants.md)  
- [<span data-ttu-id="f612f-145">MAPIOFFLINE_NOTIFY_TYPE</span><span class="sxs-lookup"><span data-stu-id="f612f-145">MAPIOFFLINE_NOTIFY_TYPE</span></span>](mapioffline_notify_type.md)

