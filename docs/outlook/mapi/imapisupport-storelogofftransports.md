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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 30c91ec7a5a28b0c270da5223a2a245fb504d8c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421380"
---
# <a name="imapisupportstorelogofftransports"></a><span data-ttu-id="d1457-103">IMAPISupport::StoreLogoffTransports</span><span class="sxs-lookup"><span data-stu-id="d1457-103">IMAPISupport::StoreLogoffTransports</span></span>

  
  
<span data-ttu-id="d1457-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1457-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1457-105">请求有序释放邮件存储。</span><span class="sxs-lookup"><span data-stu-id="d1457-105">Requests the orderly release of a message store.</span></span>
  
```cpp
HRESULT StoreLogoffTransports(
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="d1457-106">参数</span><span class="sxs-lookup"><span data-stu-id="d1457-106">Parameters</span></span>

 <span data-ttu-id="d1457-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="d1457-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="d1457-108">[in， out]控制邮件存储注销发生方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="d1457-108">[in, out] A bitmask of flags that controls how message store logoff occurs.</span></span> <span data-ttu-id="d1457-109">在输入时，此参数的所有标志都是互斥的;每个调用只能设置以下标志之一：</span><span class="sxs-lookup"><span data-stu-id="d1457-109">On input, all flags for this parameter are mutually exclusive; only one of the following flags can be set per call:</span></span>
    
<span data-ttu-id="d1457-110">LOGOFF_ABORT</span><span class="sxs-lookup"><span data-stu-id="d1457-110">LOGOFF_ABORT</span></span> 
  
> <span data-ttu-id="d1457-111">此存储的任何传输提供程序活动都应在注销之前停止。</span><span class="sxs-lookup"><span data-stu-id="d1457-111">Any transport provider activity for this store should be stopped before logoff.</span></span> <span data-ttu-id="d1457-112">在活动停止且 MAPI 后台处理程序注销存储后，控制权将返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="d1457-112">Control is returned to the client after the activity is stopped and the MAPI spooler has logged off the store.</span></span> <span data-ttu-id="d1457-113">如果发生任何传输活动，将不会发生注销，并且 MAPI 后台处理程序或传输提供程序行为不会发生任何更改。</span><span class="sxs-lookup"><span data-stu-id="d1457-113">If any transport activity is taking place, the logoff does not occur and no change in the MAPI spooler or transport provider behavior occurs.</span></span> <span data-ttu-id="d1457-114">如果当前没有活动，MAPI 后台处理程序将释放存储。</span><span class="sxs-lookup"><span data-stu-id="d1457-114">If there is currently no activity, the MAPI spooler releases the store.</span></span> 
    
<span data-ttu-id="d1457-115">LOGOFF_NO_WAIT</span><span class="sxs-lookup"><span data-stu-id="d1457-115">LOGOFF_NO_WAIT</span></span> 
  
> <span data-ttu-id="d1457-116">MAPI 后台处理程序应在准备好发送的所有出站邮件发送后立即释放存储，将控制权返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="d1457-116">The MAPI spooler should release the store and return control to the client immediately after all outbound mail that is ready to be sent is sent.</span></span> <span data-ttu-id="d1457-117">如果邮件存储具有默认收件箱，则接收任何进程内邮件，然后进一步禁用接收。</span><span class="sxs-lookup"><span data-stu-id="d1457-117">If the message store has the default Inbox, any in-process message is received, and then further reception is disabled.</span></span> 
    
<span data-ttu-id="d1457-118">LOGOFF_ORDERLY</span><span class="sxs-lookup"><span data-stu-id="d1457-118">LOGOFF_ORDERLY</span></span> 
  
> <span data-ttu-id="d1457-119">MAPI 后台处理程序应在处理完任何待定消息后立即释放存储，将控制权返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="d1457-119">The MAPI spooler should release the store and return control to the client immediately after any pending messages are finished processing.</span></span> <span data-ttu-id="d1457-120">不应处理新邮件。</span><span class="sxs-lookup"><span data-stu-id="d1457-120">No new messages should be processed.</span></span> 
    
<span data-ttu-id="d1457-121">LOGOFF_PURGE</span><span class="sxs-lookup"><span data-stu-id="d1457-121">LOGOFF_PURGE</span></span> 
  
> <span data-ttu-id="d1457-122">工作原理与LOGOFF_NO_WAIT相同。</span><span class="sxs-lookup"><span data-stu-id="d1457-122">Works the same as the LOGOFF_NO_WAIT flag.</span></span> <span data-ttu-id="d1457-123">the LOGOFF_PURGE flag returns control to the caller after completion.</span><span class="sxs-lookup"><span data-stu-id="d1457-123">The LOGOFF_PURGE flag returns control to the caller after completion.</span></span> 
    
<span data-ttu-id="d1457-124">LOGOFF_QUIET</span><span class="sxs-lookup"><span data-stu-id="d1457-124">LOGOFF_QUIET</span></span> 
  
> <span data-ttu-id="d1457-125">如果正在发生任何传输提供程序活动，则不应发生注销。</span><span class="sxs-lookup"><span data-stu-id="d1457-125">The logoff should not occur if any transport provider activity is taking place.</span></span> <span data-ttu-id="d1457-126">发生活动的类型在输出时作为标志返回。</span><span class="sxs-lookup"><span data-stu-id="d1457-126">The type of activity taking place is returned as a flag on output.</span></span>
    
    On output, MAPI spooler can return one or more of the following flags:
    
<span data-ttu-id="d1457-127">LOGOFF_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="d1457-127">LOGOFF_COMPLETE</span></span> 
  
> <span data-ttu-id="d1457-128">可以完成注销。</span><span class="sxs-lookup"><span data-stu-id="d1457-128">The logoff can complete.</span></span> <span data-ttu-id="d1457-129">与存储关联的所有资源已释放，并且该对象已失效。</span><span class="sxs-lookup"><span data-stu-id="d1457-129">All resources associated with the store have been released, and the object has been invalidated.</span></span> <span data-ttu-id="d1457-130">MAPI 后台处理程序已执行或将执行所有请求。</span><span class="sxs-lookup"><span data-stu-id="d1457-130">The MAPI spooler has performed or will perform all requests.</span></span> <span data-ttu-id="d1457-131">此时应仅调用邮件存储 **的 IUnknown：：Release** 方法。</span><span class="sxs-lookup"><span data-stu-id="d1457-131">Only the message store's **IUnknown::Release** method should be called at this point.</span></span> 
    
<span data-ttu-id="d1457-132">LOGOFF_INBOUND</span><span class="sxs-lookup"><span data-stu-id="d1457-132">LOGOFF_INBOUND</span></span> 
  
> <span data-ttu-id="d1457-133">邮件当前正在从一个或多个传输提供程序进入存储区。</span><span class="sxs-lookup"><span data-stu-id="d1457-133">A message is currently coming into the store from one or more transport providers.</span></span> 
    
<span data-ttu-id="d1457-134">LOGOFF_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="d1457-134">LOGOFF_OUTBOUND</span></span> 
  
> <span data-ttu-id="d1457-135">一个或多个传输提供程序当前正在从存储中发送邮件。</span><span class="sxs-lookup"><span data-stu-id="d1457-135">A message is currently being sent from the store by one or more transport providers.</span></span> 
    
<span data-ttu-id="d1457-136">LOGOFF_OUTBOUND_QUEUE</span><span class="sxs-lookup"><span data-stu-id="d1457-136">LOGOFF_OUTBOUND_QUEUE</span></span> 
  
> <span data-ttu-id="d1457-137">当前存在存储的出站队列中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d1457-137">There are currently messages in the outbound queue for the store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d1457-138">返回值</span><span class="sxs-lookup"><span data-stu-id="d1457-138">Return value</span></span>

<span data-ttu-id="d1457-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1457-139">S_OK</span></span> 
  
> <span data-ttu-id="d1457-140">注销过程成功。</span><span class="sxs-lookup"><span data-stu-id="d1457-140">The logoff procedure was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d1457-141">备注</span><span class="sxs-lookup"><span data-stu-id="d1457-141">Remarks</span></span>

<span data-ttu-id="d1457-142">**IMAPISupport：：StoreLogoffTransports** 方法为邮件存储提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="d1457-142">The **IMAPISupport::StoreLogoffTransports** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="d1457-143">邮件存储提供程序调用 **StoreLogoffTransports，** 以向客户端应用程序提供对 MAPI 在邮件存储关闭时如何处理传输提供程序活动的一些控制。</span><span class="sxs-lookup"><span data-stu-id="d1457-143">Message store providers call **StoreLogoffTransports** to give client applications some control over how MAPI handles transport provider activity as a message store is closing.</span></span> 
  
<span data-ttu-id="d1457-144">如果另一个进程对同一配置文件关闭存储，MAPI 将忽略对 **StoreLogoffTransports** 的调用，并返回  _lpulFlags_ 参数LOGOFF_COMPLETE标志 LOGOFF_COMPLETE。</span><span class="sxs-lookup"><span data-stu-id="d1457-144">If another process has the store to be logged off open for the same profile, MAPI ignores a call to **StoreLogoffTransports** and returns the flag LOGOFF_COMPLETE in the  _lpulFlags_ parameter.</span></span> 
  
<span data-ttu-id="d1457-145">**StoreLogoffTransports** 返回后存储提供程序的行为应基于 _lpulFlags_ 的值，该值指示系统状态并传达有关注销行为的客户端指令。</span><span class="sxs-lookup"><span data-stu-id="d1457-145">The behavior of the store provider following the return from **StoreLogoffTransports** should be based on the value of  _lpulFlags_, which indicates system status and conveys client instructions for logoff behavior.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d1457-146">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d1457-146">Notes to callers</span></span>

 <span data-ttu-id="d1457-147">通常从存储提供程序的 [IMsgStore：：StoreLogoff](imsgstore-storelogoff.md)方法调用 **StoreLogoffTransports。**</span><span class="sxs-lookup"><span data-stu-id="d1457-147">**StoreLogoffTransports** is typically called from a store provider's [IMsgStore::StoreLogoff](imsgstore-storelogoff.md) method.</span></span> <span data-ttu-id="d1457-148">但是，也可以从邮件存储的 **IUnknown：：Release** 方法调用它。</span><span class="sxs-lookup"><span data-stu-id="d1457-148">However, it can also be called from the **IUnknown::Release** method of the message store.</span></span> <span data-ttu-id="d1457-149">实现 **邮件存储** 的 Release 方法，以便检查是否已发生 **对 StoreLogoffTransports** 的调用。</span><span class="sxs-lookup"><span data-stu-id="d1457-149">Implement the **Release** method of your message store so you can check whether or not a call to **StoreLogoffTransports** has occurred.</span></span> <span data-ttu-id="d1457-150">如果尚未发生呼叫，请调用设置了 LOGOFF_ABORT 标记的 **StoreLogoffTransports。**</span><span class="sxs-lookup"><span data-stu-id="d1457-150">If a call has not occurred, call **StoreLogoffTransports** with the LOGOFF_ABORT flag set.</span></span> 
  
<span data-ttu-id="d1457-151">_lpulFlags_ 参数设置为指示客户端如何要求关闭邮件存储的标志。</span><span class="sxs-lookup"><span data-stu-id="d1457-151">The  _lpulFlags_ parameter is set to a flag that indicates how the client requires the message store to be shut down.</span></span> <span data-ttu-id="d1457-152">根据对 **StoreLogoff** 的调用中的相应参数的设置，确定 _ulFlags_ 的相应设置。</span><span class="sxs-lookup"><span data-stu-id="d1457-152">Determine the appropriate setting for  _ulFlags_ based on the setting of the corresponding parameter in the call to **StoreLogoff**.</span></span> <span data-ttu-id="d1457-153">也就是说，如果客户端调用 **StoreLogoff** 方法，将 _ulFlags_ 设置为 LOGOFF_ORDERLY，则应该调用将 _ulFlags_ 设置为 LOGOFF_ORDERLY 的 **StoreLogoffTransports。**</span><span class="sxs-lookup"><span data-stu-id="d1457-153">That is, if a client called your **StoreLogoff** method with  _ulFlags_ set to LOGOFF_ORDERLY, you should call **StoreLogoffTransports** with  _ulFlags_ set to LOGOFF_ORDERLY.</span></span> 
  
<span data-ttu-id="d1457-154">有关邮件存储注销过程的信息，请参阅 [关闭邮件存储提供程序](shutting-down-a-message-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d1457-154">For more information about the message store logoff process, see [Shutting Down a Message Store Provider](shutting-down-a-message-store-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1457-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1457-155">See also</span></span>



[<span data-ttu-id="d1457-156">IMsgStore::StoreLogoff</span><span class="sxs-lookup"><span data-stu-id="d1457-156">IMsgStore::StoreLogoff</span></span>](imsgstore-storelogoff.md)
  
[<span data-ttu-id="d1457-157">IXPLogon::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="d1457-157">IXPLogon::FlushQueues</span></span>](ixplogon-flushqueues.md)
  
[<span data-ttu-id="d1457-158">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d1457-158">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

