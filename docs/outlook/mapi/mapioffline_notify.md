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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414765"
---
# <a name="mapioffline_notify"></a><span data-ttu-id="ca056-103">MAPIOFFLINE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="ca056-103">MAPIOFFLINE_NOTIFY</span></span>

<span data-ttu-id="ca056-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca056-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca056-105">这是连接状态更改的通知。</span><span class="sxs-lookup"><span data-stu-id="ca056-105">This is the notification for a change in the connection state.</span></span> <span data-ttu-id="ca056-106">它指示已更改的连接状态部分、旧连接状态和新连接状态。</span><span class="sxs-lookup"><span data-stu-id="ca056-106">It indicates the part of the connection state that has changed, the old connection state, and the new connection state.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ca056-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="ca056-107">Quick info</span></span>

<span data-ttu-id="ca056-108">请参阅 **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="ca056-108">See **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
  
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

## <a name="members"></a><span data-ttu-id="ca056-109">Members</span><span class="sxs-lookup"><span data-stu-id="ca056-109">Members</span></span>

 <span data-ttu-id="ca056-110">_ulSize_</span><span class="sxs-lookup"><span data-stu-id="ca056-110">_ulSize_</span></span>
  
> <span data-ttu-id="ca056-111">结构 **MAPIOFFLINE_NOTIFY** 的大小。</span><span class="sxs-lookup"><span data-stu-id="ca056-111">Size of the **MAPIOFFLINE_NOTIFY** structure.</span></span> 
    
 <span data-ttu-id="ca056-112">_NotifyType_</span><span class="sxs-lookup"><span data-stu-id="ca056-112">_NotifyType_</span></span>
  
> <span data-ttu-id="ca056-113">通知类型。</span><span class="sxs-lookup"><span data-stu-id="ca056-113">Type of notification.</span></span> <span data-ttu-id="ca056-114">请注意，仅支持有关连接状态更改的通知;唯一支持的值是：</span><span class="sxs-lookup"><span data-stu-id="ca056-114">Note that only notification on change of the connection state is supported; the only supported values are:</span></span>
    
   - <span data-ttu-id="ca056-115">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START</span><span class="sxs-lookup"><span data-stu-id="ca056-115">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START</span></span>
    
   - <span data-ttu-id="ca056-116">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE</span><span class="sxs-lookup"><span data-stu-id="ca056-116">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE</span></span>
    
   - <span data-ttu-id="ca056-117">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE</span><span class="sxs-lookup"><span data-stu-id="ca056-117">MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE</span></span>
    
 <span data-ttu-id="ca056-118">_ulClientToken_</span><span class="sxs-lookup"><span data-stu-id="ca056-118">_ulClientToken_</span></span>
  
> <span data-ttu-id="ca056-119">由客户端在 **[IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)** **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="ca056-119">A token defined by the client in the **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** structure in **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> 
    
 <span data-ttu-id="ca056-120">_ulMask_</span><span class="sxs-lookup"><span data-stu-id="ca056-120">_ulMask_</span></span>
  
> <span data-ttu-id="ca056-121">已更改的连接状态部分。</span><span class="sxs-lookup"><span data-stu-id="ca056-121">The part of the connection state that has changed.</span></span> <span data-ttu-id="ca056-122">唯一支持的值是 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="ca056-122">The only supported value is MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span>
    
 <span data-ttu-id="ca056-123">_ulStateOld_</span><span class="sxs-lookup"><span data-stu-id="ca056-123">_ulStateOld_</span></span>
  
> <span data-ttu-id="ca056-124">旧连接状态。</span><span class="sxs-lookup"><span data-stu-id="ca056-124">The old connection state.</span></span> <span data-ttu-id="ca056-125">唯一支持的值是：</span><span class="sxs-lookup"><span data-stu-id="ca056-125">The only supported values are:</span></span>
    
   - <span data-ttu-id="ca056-126">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="ca056-126">MAPIOFFLINE_STATE_OFFLINE</span></span>
    
   - <span data-ttu-id="ca056-127">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="ca056-127">MAPIOFFLINE_STATE_ONLINE</span></span>
    
 <span data-ttu-id="ca056-128">_ulStateNew_</span><span class="sxs-lookup"><span data-stu-id="ca056-128">_ulStateNew_</span></span>
  
> <span data-ttu-id="ca056-129">新的连接状态。</span><span class="sxs-lookup"><span data-stu-id="ca056-129">The new connection state.</span></span> <span data-ttu-id="ca056-130">唯一支持的值是：</span><span class="sxs-lookup"><span data-stu-id="ca056-130">The only supported values are:</span></span>
    
   - <span data-ttu-id="ca056-131">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="ca056-131">MAPIOFFLINE_STATE_OFFLINE</span></span>
    
   - <span data-ttu-id="ca056-132">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="ca056-132">MAPIOFFLINE_STATE_ONLINE</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ca056-133">备注</span><span class="sxs-lookup"><span data-stu-id="ca056-133">Remarks</span></span>

<span data-ttu-id="ca056-134">脱机状态 API 仅支持联机/脱机更改的通知。</span><span class="sxs-lookup"><span data-stu-id="ca056-134">The Offline State API supports only notifications for online/offline changes.</span></span> <span data-ttu-id="ca056-135">在检查实际更改Outlook客户端必须检查是否返回以下值：</span><span class="sxs-lookup"><span data-stu-id="ca056-135">A client must check that Outlook returns the following values before examining the actual change:</span></span>
  
1.  <span data-ttu-id="ca056-136">*NotifyType*  的值为 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START、MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE 或 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE。</span><span class="sxs-lookup"><span data-stu-id="ca056-136">*NotifyType*  has the value MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START, MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE, or MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE.</span></span> <span data-ttu-id="ca056-137">在这种情况下，客户端可以假定更改是连接状态更改，  *而 Info*  是  *StateChange 结构*  。</span><span class="sxs-lookup"><span data-stu-id="ca056-137">In this case, the client can assume that the change is a connection state change, and  *Info*  is of the structure  *StateChange*  .</span></span> 
    
2.  <span data-ttu-id="ca056-138">*ulMask*  具有值 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="ca056-138">*ulMask*  has the value MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span> <span data-ttu-id="ca056-139">在这种情况下，客户端可以假定更改是联机/脱机连接状态更改，并可以继续检查  *ulStateOld*  和  *ulStateNew*  。</span><span class="sxs-lookup"><span data-stu-id="ca056-139">In this case, the client can assume that the change is an online/offline connection state change, and can proceed with examining  *ulStateOld*  and  *ulStateNew*  .</span></span> 
    
<span data-ttu-id="ca056-140">用户可能会Outlook不支持的其他更改通知客户端。</span><span class="sxs-lookup"><span data-stu-id="ca056-140">It is possible that Outlook notifies a client of other changes that are not supported.</span></span> <span data-ttu-id="ca056-141">在这种情况下  *，NotifyType*  不是前面提到的三个值中的任一个值，或者  *ulMask*  不会为 MAPIOFFLINE_STATE_OFFLINE_MASK，并且客户端必须忽略 Info 中的其余  *数据*  。</span><span class="sxs-lookup"><span data-stu-id="ca056-141">In such cases,  *NotifyType*  would not be any one of the three values stated previously, or  *ulMask*  would not be MAPIOFFLINE_STATE_OFFLINE_MASK, and the client must ignore the rest of the data in  *Info*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ca056-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca056-142">See also</span></span>

- [<span data-ttu-id="ca056-143">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="ca056-143">About the Offline State API</span></span>](about-the-offline-state-api.md)  
- [<span data-ttu-id="ca056-144">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="ca056-144">MAPI Constants</span></span>](mapi-constants.md)  
- [<span data-ttu-id="ca056-145">MAPIOFFLINE_NOTIFY_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca056-145">MAPIOFFLINE_NOTIFY_TYPE</span></span>](mapioffline_notify_type.md)

