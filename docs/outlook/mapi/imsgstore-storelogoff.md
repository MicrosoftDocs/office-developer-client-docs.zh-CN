---
title: IMsgStoreStoreLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.StoreLogoff
api_type:
- COM
ms.assetid: 3773c98e-531e-4bdc-a39a-2c3bb7378cd3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2ac8fb6f4e56b6f086e6061c227120cd49fc621a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775884"
---
# <a name="imsgstorestorelogoff"></a><span data-ttu-id="46727-103">IMsgStore::StoreLogoff</span><span class="sxs-lookup"><span data-stu-id="46727-103">IMsgStore::StoreLogoff</span></span>

  
  
<span data-ttu-id="46727-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="46727-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="46727-105">允许的邮件存储的有序注销。</span><span class="sxs-lookup"><span data-stu-id="46727-105">Enables the orderly logoff of the message store.</span></span>
  
```cpp
HRESULT StoreLogoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="46727-106">参数</span><span class="sxs-lookup"><span data-stu-id="46727-106">Parameters</span></span>

 <span data-ttu-id="46727-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="46727-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="46727-108">[传入、 传出]位掩码的标志控制消息存储中的注销。</span><span class="sxs-lookup"><span data-stu-id="46727-108">[in, out] A bitmask of flags that controls logoff from the message store.</span></span> <span data-ttu-id="46727-109">在输入所有标志设置为此参数相互都排斥;呼叫者必须指定每次呼叫只有一个标志。</span><span class="sxs-lookup"><span data-stu-id="46727-109">On input, all flags set for this parameter are mutually exclusive; a caller must specify only one flag per call.</span></span> <span data-ttu-id="46727-110">以下标志是上输入有效的：</span><span class="sxs-lookup"><span data-stu-id="46727-110">The following flags are valid on input:</span></span>
    
<span data-ttu-id="46727-111">LOGOFF_ABORT</span><span class="sxs-lookup"><span data-stu-id="46727-111">LOGOFF_ABORT</span></span> 
  
> <span data-ttu-id="46727-112">在注销之前，应停止此消息存储的任何传输提供程序活动。</span><span class="sxs-lookup"><span data-stu-id="46727-112">Any transport provider activity for this message store should be stopped before logoff.</span></span> <span data-ttu-id="46727-113">停止活动后，将返回到呼叫者控制权。</span><span class="sxs-lookup"><span data-stu-id="46727-113">Control is returned to the caller after activity is stopped.</span></span> <span data-ttu-id="46727-114">如果任何传输提供程序活动正在进行，注销，不会发生，就会发生任何更改 MAPI 后台处理程序或传输提供程序的行为。</span><span class="sxs-lookup"><span data-stu-id="46727-114">If any transport provider activity is taking place, the logoff does not occur and no change in the behavior of the MAPI spooler or transport providers occurs.</span></span> <span data-ttu-id="46727-115">传输提供程序活动处于空闲状态，如果 MAPI 后台处理程序释放存储。</span><span class="sxs-lookup"><span data-stu-id="46727-115">If transport provider activity is idle, the MAPI spooler releases the store.</span></span> 
    
<span data-ttu-id="46727-116">LOGOFF_NO_WAIT</span><span class="sxs-lookup"><span data-stu-id="46727-116">LOGOFF_NO_WAIT</span></span> 
  
> <span data-ttu-id="46727-117">消息存储不应等待来自传输提供程序在关闭之前的邮件。</span><span class="sxs-lookup"><span data-stu-id="46727-117">The message store should not wait for messages from transport providers before closing.</span></span> <span data-ttu-id="46727-118">已准备好进行发送出站邮件发送。</span><span class="sxs-lookup"><span data-stu-id="46727-118">Outbound messages that are ready to be sent are sent.</span></span> <span data-ttu-id="46727-119">如果将此存储区包含默认收件箱，收到任何进程内消息，然后禁用进一步接收。</span><span class="sxs-lookup"><span data-stu-id="46727-119">If this store contains the default Inbox, any in-process messages are received, and then further reception is disabled.</span></span> <span data-ttu-id="46727-120">所有活动完成后，MAPI 后台处理程序释放存储，并控制立即返回到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="46727-120">When all activity is complete, the MAPI spooler releases the store, and control is immediately returned to the caller.</span></span> 
    
<span data-ttu-id="46727-121">LOGOFF_ORDERLY</span><span class="sxs-lookup"><span data-stu-id="46727-121">LOGOFF_ORDERLY</span></span> 
  
> <span data-ttu-id="46727-122">消息存储不应等待关闭前的传输提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="46727-122">The message store should not wait for information from transport providers before closing.</span></span> <span data-ttu-id="46727-123">当前正在处理的消息都已完成，但没有新邮件处理。</span><span class="sxs-lookup"><span data-stu-id="46727-123">Messages that are currently being processed are completed, but no new messages are processed.</span></span> <span data-ttu-id="46727-124">所有活动完成后，MAPI 后台处理程序释放存储，并控制立即返回到存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="46727-124">When all activity is complete, the MAPI spooler releases the store, and control is immediately returned to the store provider.</span></span> 
    
<span data-ttu-id="46727-125">LOGOFF_PURGE</span><span class="sxs-lookup"><span data-stu-id="46727-125">LOGOFF_PURGE</span></span> 
  
> <span data-ttu-id="46727-126">注销应工作相同设置 LOGOFF_NO_WAIT 标志，但应调用[IXPLogon::FlushQueues](ixplogon-flushqueues.md)或[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法的合适的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="46727-126">The logoff should work the same as if the LOGOFF_NO_WAIT flag is set, but either the [IXPLogon::FlushQueues](ixplogon-flushqueues.md) or [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method for the appropriate transport providers should be called.</span></span> <span data-ttu-id="46727-127">LOGOFF_PURGE 标志完成后返回到呼叫者的控件。</span><span class="sxs-lookup"><span data-stu-id="46727-127">The LOGOFF_PURGE flag returns control to the caller after completion.</span></span> 
    
<span data-ttu-id="46727-128">LOGOFF_QUIET</span><span class="sxs-lookup"><span data-stu-id="46727-128">LOGOFF_QUIET</span></span> 
  
> <span data-ttu-id="46727-129">如果任何传输提供程序活动正在进行，不应发生注销。</span><span class="sxs-lookup"><span data-stu-id="46727-129">If any transport provider activity is taking place, the logoff should not occur.</span></span>
    
    The following flags are valid on output:
    
<span data-ttu-id="46727-130">LOGOFF_INBOUND</span><span class="sxs-lookup"><span data-stu-id="46727-130">LOGOFF_INBOUND</span></span> 
  
> <span data-ttu-id="46727-131">当前正在传入入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="46727-131">Inbound messages are currently arriving.</span></span>
    
<span data-ttu-id="46727-132">LOGOFF_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="46727-132">LOGOFF_OUTBOUND</span></span> 
  
> <span data-ttu-id="46727-133">发送正在出站邮件。</span><span class="sxs-lookup"><span data-stu-id="46727-133">Outbound messages are in the process of being sent.</span></span>
    
<span data-ttu-id="46727-134">LOGOFF_OUTBOUND_QUEUE</span><span class="sxs-lookup"><span data-stu-id="46727-134">LOGOFF_OUTBOUND_QUEUE</span></span> 
  
> <span data-ttu-id="46727-135">出站邮件处于挂起状态 （即，它们是在发件箱）。</span><span class="sxs-lookup"><span data-stu-id="46727-135">Outbound messages are pending (that is, they are in the Outbox).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="46727-136">返回值</span><span class="sxs-lookup"><span data-stu-id="46727-136">Return value</span></span>

<span data-ttu-id="46727-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="46727-137">S_OK</span></span> 
  
> <span data-ttu-id="46727-138">成功完成注销。</span><span class="sxs-lookup"><span data-stu-id="46727-138">The logoff completed successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="46727-139">说明</span><span class="sxs-lookup"><span data-stu-id="46727-139">Remarks</span></span>

<span data-ttu-id="46727-140">**IMsgStore::StoreLogoff**方法 exerts 控件通过交互的邮件存储并注销过程中传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="46727-140">The **IMsgStore::StoreLogoff** method exerts control over the interaction of the message store and transport providers during the logoff process.</span></span> <span data-ttu-id="46727-141">调用**StoreLogoff**是仅供正在使用仅的呼叫者的消息存储。</span><span class="sxs-lookup"><span data-stu-id="46727-141">Calling **StoreLogoff** is valid only for message stores that are being used only by the caller.</span></span> <span data-ttu-id="46727-142">例如，当两个客户端使用相同的消息存储，并且其中之一调用**StoreLogoff**，立即发布的消息存储和控制返回到调用客户端。</span><span class="sxs-lookup"><span data-stu-id="46727-142">For example, when two clients are using the same message store and one of them calls **StoreLogoff**, the message store is immediately released and control is returned to the calling client.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="46727-143">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="46727-143">Notes to implementers</span></span>

<span data-ttu-id="46727-144">保存传递给**StoreLogoff**的标志，并将它们传递调用[IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md)方法时。</span><span class="sxs-lookup"><span data-stu-id="46727-144">Save the flags that are passed to **StoreLogoff** and pass them when you call the [IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md) method.</span></span> <span data-ttu-id="46727-145">不要调用**StoreLogoffTransports** ，直到消息存储库的引用计数为 0。</span><span class="sxs-lookup"><span data-stu-id="46727-145">Do not call **StoreLogoffTransports** until the message store's reference count drops to zero.</span></span> <span data-ttu-id="46727-146">多个调用**StoreLogoffTransports**只需覆盖已保存的标志。</span><span class="sxs-lookup"><span data-stu-id="46727-146">Multiple calls to **StoreLogoffTransports** simply overwrite the saved flags.</span></span> 
  
<span data-ttu-id="46727-147">如果没有呼叫做**StoreLogoff**之前邮件存储的引用计数为零时，传递给**StoreLogoffTransports** _ulFlags_参数中设置 LOGOFF_ABORT 标志。</span><span class="sxs-lookup"><span data-stu-id="46727-147">If no call has been made to **StoreLogoff** before the message store's reference count reaches zero, set the LOGOFF_ABORT flag in the  _ulFlags_ parameter that you pass to **StoreLogoffTransports**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="46727-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46727-148">See also</span></span>



[<span data-ttu-id="46727-149">IMAPIStatus::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="46727-149">IMAPIStatus::FlushQueues</span></span>](imapistatus-flushqueues.md)
  
[<span data-ttu-id="46727-150">IMAPISupport::StoreLogoffTransports</span><span class="sxs-lookup"><span data-stu-id="46727-150">IMAPISupport::StoreLogoffTransports</span></span>](imapisupport-storelogofftransports.md)
  
[<span data-ttu-id="46727-151">IXPLogon::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="46727-151">IXPLogon::FlushQueues</span></span>](ixplogon-flushqueues.md)
  
[<span data-ttu-id="46727-152">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="46727-152">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

