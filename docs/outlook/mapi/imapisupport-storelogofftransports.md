---
title: IMAPISupportStoreLogoffTransports
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.StoreLogoffTransports
api_type:
- COM
ms.assetid: f21fba96-c5ca-4d41-9b93-c7955ab7327f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b77a58b04e5cdeee7a9e84051a6ed287c1a20115
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578309"
---
# <a name="imapisupportstorelogofftransports"></a><span data-ttu-id="d6815-103">IMAPISupport::StoreLogoffTransports</span><span class="sxs-lookup"><span data-stu-id="d6815-103">IMAPISupport::StoreLogoffTransports</span></span>

  
  
<span data-ttu-id="d6815-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6815-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6815-105">请求的消息存储的有序版本。</span><span class="sxs-lookup"><span data-stu-id="d6815-105">Requests the orderly release of a message store.</span></span>
  
```cpp
HRESULT StoreLogoffTransports(
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="d6815-106">参数</span><span class="sxs-lookup"><span data-stu-id="d6815-106">Parameters</span></span>

 <span data-ttu-id="d6815-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="d6815-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="d6815-108">[传入、 传出]位掩码的标志，控制如何消息存储注销发生此事件。</span><span class="sxs-lookup"><span data-stu-id="d6815-108">[in, out] A bitmask of flags that controls how message store logoff occurs.</span></span> <span data-ttu-id="d6815-109">在输入时，此参数的所有标志相互都排斥;每次呼叫，可以设置以下标志中的只有一个：</span><span class="sxs-lookup"><span data-stu-id="d6815-109">On input, all flags for this parameter are mutually exclusive; only one of the following flags can be set per call:</span></span>
    
<span data-ttu-id="d6815-110">LOGOFF_ABORT</span><span class="sxs-lookup"><span data-stu-id="d6815-110">LOGOFF_ABORT</span></span> 
  
> <span data-ttu-id="d6815-111">在注销之前，应停止此存储的任何传输提供程序活动。</span><span class="sxs-lookup"><span data-stu-id="d6815-111">Any transport provider activity for this store should be stopped before logoff.</span></span> <span data-ttu-id="d6815-112">停止活动和 MAPI 后台处理程序已关闭存储记录之后，将返回到客户端控制权。</span><span class="sxs-lookup"><span data-stu-id="d6815-112">Control is returned to the client after the activity is stopped and the MAPI spooler has logged off the store.</span></span> <span data-ttu-id="d6815-113">如果任何传输活动正在进行，不会发生注销并 MAPI 后台处理程序或传输提供程序行为中的任何更改。</span><span class="sxs-lookup"><span data-stu-id="d6815-113">If any transport activity is taking place, the logoff does not occur and no change in the MAPI spooler or transport provider behavior occurs.</span></span> <span data-ttu-id="d6815-114">如果当前没有任何活动，MAPI 后台处理程序释放存储。</span><span class="sxs-lookup"><span data-stu-id="d6815-114">If there is currently no activity, the MAPI spooler releases the store.</span></span> 
    
<span data-ttu-id="d6815-115">LOGOFF_NO_WAIT</span><span class="sxs-lookup"><span data-stu-id="d6815-115">LOGOFF_NO_WAIT</span></span> 
  
> <span data-ttu-id="d6815-116">MAPI 后台处理程序应释放存储并立即发送后所有出站邮件可以发送的控制权归还给客户端。</span><span class="sxs-lookup"><span data-stu-id="d6815-116">The MAPI spooler should release the store and return control to the client immediately after all outbound mail that is ready to be sent is sent.</span></span> <span data-ttu-id="d6815-117">消息存储库具有默认收件箱，如果收到任何进程内邮件，然后禁用进一步接收。</span><span class="sxs-lookup"><span data-stu-id="d6815-117">If the message store has the default Inbox, any in-process message is received, and then further reception is disabled.</span></span> 
    
<span data-ttu-id="d6815-118">LOGOFF_ORDERLY</span><span class="sxs-lookup"><span data-stu-id="d6815-118">LOGOFF_ORDERLY</span></span> 
  
> <span data-ttu-id="d6815-119">MAPI 后台处理程序应释放存储并返回到客户端的控件，任何挂起的邮件已完成后，立即处理。</span><span class="sxs-lookup"><span data-stu-id="d6815-119">The MAPI spooler should release the store and return control to the client immediately after any pending messages are finished processing.</span></span> <span data-ttu-id="d6815-120">应处理没有新邮件。</span><span class="sxs-lookup"><span data-stu-id="d6815-120">No new messages should be processed.</span></span> 
    
<span data-ttu-id="d6815-121">LOGOFF_PURGE</span><span class="sxs-lookup"><span data-stu-id="d6815-121">LOGOFF_PURGE</span></span> 
  
> <span data-ttu-id="d6815-122">适用于 LOGOFF_NO_WAIT 标志相同。</span><span class="sxs-lookup"><span data-stu-id="d6815-122">Works the same as the LOGOFF_NO_WAIT flag.</span></span> <span data-ttu-id="d6815-123">LOGOFF_PURGE 标志完成后返回到呼叫者的控件。</span><span class="sxs-lookup"><span data-stu-id="d6815-123">The LOGOFF_PURGE flag returns control to the caller after completion.</span></span> 
    
<span data-ttu-id="d6815-124">LOGOFF_QUIET</span><span class="sxs-lookup"><span data-stu-id="d6815-124">LOGOFF_QUIET</span></span> 
  
> <span data-ttu-id="d6815-125">如果任何传输提供程序活动正在进行，不应发生注销。</span><span class="sxs-lookup"><span data-stu-id="d6815-125">The logoff should not occur if any transport provider activity is taking place.</span></span> <span data-ttu-id="d6815-126">正在进行的活动的类型输出返回作为的标志。</span><span class="sxs-lookup"><span data-stu-id="d6815-126">The type of activity taking place is returned as a flag on output.</span></span>
    
    On output, MAPI spooler can return one or more of the following flags:
    
<span data-ttu-id="d6815-127">LOGOFF_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="d6815-127">LOGOFF_COMPLETE</span></span> 
  
> <span data-ttu-id="d6815-128">可以完成注销。</span><span class="sxs-lookup"><span data-stu-id="d6815-128">The logoff can complete.</span></span> <span data-ttu-id="d6815-129">已发布与存储关联的所有资源，并已失效对象。</span><span class="sxs-lookup"><span data-stu-id="d6815-129">All resources associated with the store have been released, and the object has been invalidated.</span></span> <span data-ttu-id="d6815-130">MAPI 后台处理程序已执行，或将执行所有请求。</span><span class="sxs-lookup"><span data-stu-id="d6815-130">The MAPI spooler has performed or will perform all requests.</span></span> <span data-ttu-id="d6815-131">应在此时调用仅的消息存储**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="d6815-131">Only the message store's **IUnknown::Release** method should be called at this point.</span></span> 
    
<span data-ttu-id="d6815-132">LOGOFF_INBOUND</span><span class="sxs-lookup"><span data-stu-id="d6815-132">LOGOFF_INBOUND</span></span> 
  
> <span data-ttu-id="d6815-133">邮件当前来自到存储一个或多个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="d6815-133">A message is currently coming into the store from one or more transport providers.</span></span> 
    
<span data-ttu-id="d6815-134">LOGOFF_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="d6815-134">LOGOFF_OUTBOUND</span></span> 
  
> <span data-ttu-id="d6815-135">由一个或多个传输提供程序从存储是当前正在发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="d6815-135">A message is currently being sent from the store by one or more transport providers.</span></span> 
    
<span data-ttu-id="d6815-136">LOGOFF_OUTBOUND_QUEUE</span><span class="sxs-lookup"><span data-stu-id="d6815-136">LOGOFF_OUTBOUND_QUEUE</span></span> 
  
> <span data-ttu-id="d6815-137">存储的出站队列中当前没有消息。</span><span class="sxs-lookup"><span data-stu-id="d6815-137">There are currently messages in the outbound queue for the store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d6815-138">返回值</span><span class="sxs-lookup"><span data-stu-id="d6815-138">Return value</span></span>

<span data-ttu-id="d6815-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6815-139">S_OK</span></span> 
  
> <span data-ttu-id="d6815-140">注销过程成功。</span><span class="sxs-lookup"><span data-stu-id="d6815-140">The logoff procedure was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d6815-141">注解</span><span class="sxs-lookup"><span data-stu-id="d6815-141">Remarks</span></span>

<span data-ttu-id="d6815-142">消息存储提供程序支持对象的实现**IMAPISupport::StoreLogoffTransports**方法。</span><span class="sxs-lookup"><span data-stu-id="d6815-142">The **IMAPISupport::StoreLogoffTransports** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="d6815-143">消息存储提供程序调用**StoreLogoffTransports**以提供一些控制如何 MAPI 句柄传输的消息存储提供程序活动正在关闭的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6815-143">Message store providers call **StoreLogoffTransports** to give client applications some control over how MAPI handles transport provider activity as a message store is closing.</span></span> 
  
<span data-ttu-id="d6815-144">如果另一个进程要被注销打开的同一配置文件的存储，MAPI 将忽略**StoreLogoffTransports**调用，返回的标志 LOGOFF_COMPLETE _lpulFlags_参数中。</span><span class="sxs-lookup"><span data-stu-id="d6815-144">If another process has the store to be logged off open for the same profile, MAPI ignores a call to **StoreLogoffTransports** and returns the flag LOGOFF_COMPLETE in the  _lpulFlags_ parameter.</span></span> 
  
<span data-ttu-id="d6815-145">关注**StoreLogoffTransports**从返回的存储提供程序的行为应基于_lpulFlags_，指示系统状态和传达注销行为的客户端说明的值。</span><span class="sxs-lookup"><span data-stu-id="d6815-145">The behavior of the store provider following the return from **StoreLogoffTransports** should be based on the value of  _lpulFlags_, which indicates system status and conveys client instructions for logoff behavior.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d6815-146">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d6815-146">Notes to callers</span></span>

 <span data-ttu-id="d6815-147">**StoreLogoffTransports**通常从存储提供程序的[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="d6815-147">**StoreLogoffTransports** is typically called from a store provider's [IMsgStore::StoreLogoff](imsgstore-storelogoff.md) method.</span></span> <span data-ttu-id="d6815-148">但是，它也可以调用从消息存储库的**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="d6815-148">However, it can also be called from the **IUnknown::Release** method of the message store.</span></span> <span data-ttu-id="d6815-149">发生的消息存储以便您可以检查**StoreLogoffTransports**调用**Release**方法的实现。</span><span class="sxs-lookup"><span data-stu-id="d6815-149">Implement the **Release** method of your message store so you can check whether or not a call to **StoreLogoffTransports** has occurred.</span></span> <span data-ttu-id="d6815-150">如果未发生呼叫，呼叫**StoreLogoffTransports**设置了 LOGOFF_ABORT 标志。</span><span class="sxs-lookup"><span data-stu-id="d6815-150">If a call has not occurred, call **StoreLogoffTransports** with the LOGOFF_ABORT flag set.</span></span> 
  
<span data-ttu-id="d6815-151">_LpulFlags_参数设置为一个标志，指示如何客户端要求要关闭的消息存储。</span><span class="sxs-lookup"><span data-stu-id="d6815-151">The  _lpulFlags_ parameter is set to a flag that indicates how the client requires the message store to be shut down.</span></span> <span data-ttu-id="d6815-152">确定_ulFlags_基于对**StoreLogoff**的调用中的相应参数设置为适当的设置。</span><span class="sxs-lookup"><span data-stu-id="d6815-152">Determine the appropriate setting for  _ulFlags_ based on the setting of the corresponding parameter in the call to **StoreLogoff**.</span></span> <span data-ttu-id="d6815-153">即，如果客户端调用，设置为 LOGOFF_ORDERLY _ulFlags_ **StoreLogoff**方法，您应与_ulFlags_设置为 LOGOFF_ORDERLY 调用**StoreLogoffTransports** 。</span><span class="sxs-lookup"><span data-stu-id="d6815-153">That is, if a client called your **StoreLogoff** method with  _ulFlags_ set to LOGOFF_ORDERLY, you should call **StoreLogoffTransports** with  _ulFlags_ set to LOGOFF_ORDERLY.</span></span> 
  
<span data-ttu-id="d6815-154">有关邮件存储注销过程的详细信息，请参阅[关机的情况下消息存储提供程序](shutting-down-a-message-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d6815-154">For more information about the message store logoff process, see [Shutting Down a Message Store Provider](shutting-down-a-message-store-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d6815-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6815-155">See also</span></span>



[<span data-ttu-id="d6815-156">IMsgStore::StoreLogoff</span><span class="sxs-lookup"><span data-stu-id="d6815-156">IMsgStore::StoreLogoff</span></span>](imsgstore-storelogoff.md)
  
[<span data-ttu-id="d6815-157">IXPLogon::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="d6815-157">IXPLogon::FlushQueues</span></span>](ixplogon-flushqueues.md)
  
[<span data-ttu-id="d6815-158">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d6815-158">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

