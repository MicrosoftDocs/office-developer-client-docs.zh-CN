---
title: IXPLogonTransportNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.TransportNotify
api_type:
- COM
ms.assetid: c712fc17-f436-41cf-9aa3-186c9a86d56e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5429f98a0335ae99b719d0f15b66a95ba87430e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776135"
---
# <a name="ixplogontransportnotify"></a><span data-ttu-id="0e5cd-103">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="0e5cd-103">IXPLogon::TransportNotify</span></span>

<span data-ttu-id="0e5cd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0e5cd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0e5cd-105">信号传输提供程序有关哪些请求发送通知的事件的匹配项。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-105">Signals the occurrence of an event about which the transport provider requested notification.</span></span>
  
```cpp
HRESULT TransportNotify(
  ULONG FAR * lpulFlags,
  LPVOID FAR * lppvData
);
```

## <a name="parameters"></a><span data-ttu-id="0e5cd-106">参数</span><span class="sxs-lookup"><span data-stu-id="0e5cd-106">Parameters</span></span>

 <span data-ttu-id="0e5cd-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="0e5cd-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="0e5cd-108">[传入、 传出]位掩码的标志指示通知事件。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-108">[in, out] A bitmask of flags that signals notification events.</span></span> <span data-ttu-id="0e5cd-109">以下标志可由上输入 MAPI 后台打印程序设置和必须返回不变输出：</span><span class="sxs-lookup"><span data-stu-id="0e5cd-109">The following flags can be set by the MAPI spooler on input and must be returned unchanged on output:</span></span>
    
<span data-ttu-id="0e5cd-110">NOTIFY_ABORT_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="0e5cd-110">NOTIFY_ABORT_DEFERRED</span></span> 
  
> <span data-ttu-id="0e5cd-111">通知传输提供程序为其接受它，责任邮件将被延迟。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-111">Notifies the transport provider that a message for which it accepted responsibility is being deferred.</span></span> <span data-ttu-id="0e5cd-112">仅传输提供程序支持延期必须支持此标志。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-112">Only transport providers that support deferral must support this flag.</span></span> <span data-ttu-id="0e5cd-113">_LppvData_参数指向已取消的消息的项标识符。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-113">The  _lppvData_ parameter points to the entry identifier of the canceled message.</span></span> <span data-ttu-id="0e5cd-114">调用[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)方法，仍可以延迟 MAPI 后台处理程序尚未处理的消息。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-114">Messages that the MAPI spooler has not processed can still be deferred by calling the [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) method.</span></span> 
    
<span data-ttu-id="0e5cd-115">NOTIFY_BEGIN_INBOUND</span><span class="sxs-lookup"><span data-stu-id="0e5cd-115">NOTIFY_BEGIN_INBOUND</span></span> 
  
> <span data-ttu-id="0e5cd-116">MAPI 后台处理程序现在可以接受该传输提供程序会话的入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-116">The MAPI spooler can now accept inbound messages for this transport provider session.</span></span> <span data-ttu-id="0e5cd-117">MAPI 后台处理程序定期调用[IXPLogon::Poll](ixplogon-poll.md)方法，如果传输提供程序在登录设置[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)调用 LOGON_SP_POLL 标志。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-117">The MAPI spooler regularly calls the [IXPLogon::Poll](ixplogon-poll.md) method if the transport provider set the LOGON_SP_POLL flag with the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) call at logon.</span></span> <span data-ttu-id="0e5cd-118">一旦设置 NOTIFY_BEGIN_INBOUND 标志，MAPI 后台处理程序采用对[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法的调用中传递的 NOTIFY_NEWMAIL 标志。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-118">Once the NOTIFY_BEGIN_INBOUND flag is set, the MAPI spooler honors the NOTIFY_NEWMAIL flag passed in the call to the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method.</span></span> <span data-ttu-id="0e5cd-119">通过调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法返回之前，应更新传输提供程序会话状态表格行。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-119">The status table row for the transport provider session should be updated before returning by calling the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method.</span></span> <span data-ttu-id="0e5cd-120">NOTIFY_BEGIN_INBOUND 和 NOTIFY_END_INBOUND 标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-120">The NOTIFY_BEGIN_INBOUND and NOTIFY_END_INBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="0e5cd-121">NOTIFY_BEGIN_INBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="0e5cd-121">NOTIFY_BEGIN_INBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="0e5cd-122">信号传输提供程序尽快循环入站邮件。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-122">Signals the transport provider to cycle through inbound messages as quickly as possible.</span></span> <span data-ttu-id="0e5cd-123">为遵守此通知，传输提供程序应设置 STATUS_INBOUND_FLUSH 标志其状态表格行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中为它可以使用**ModifyStatusRow**。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-123">To comply with this notification, the transport provider should set the STATUS_INBOUND_FLUSH flag in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property of its status table row as soon as it can, by using **ModifyStatusRow**.</span></span> <span data-ttu-id="0e5cd-124">入站消息周期已完成时提供程序确定它已下载所有可以, 或者它已接收**TransportNotify**方法调用设置了 NOTIFY_END_INBOUND_FLUSH 标志。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-124">An inbound messaging cycle is complete when the provider determines it has downloaded all it can, or when it has received a **TransportNotify** method call with the NOTIFY_END_INBOUND_FLUSH flag set.</span></span> <span data-ttu-id="0e5cd-125">之前的入站消息周期结束时，提供程序不应调用[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)方法或否则释放给操作系统的传入消息的速度传递周期。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-125">Until the end of the inbound messaging cycle, the provider should not call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) method or otherwise relinquish cycles to the operating system to speed delivery of incoming messages.</span></span> <span data-ttu-id="0e5cd-126">这是可接受的因为 MAPI 后台处理程序通常使用 NOTIFY_BEGIN_INBOUND_FLUSH 仅在响应用户的请求，通过客户端应用程序，现在将所有邮件的都传递。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-126">This is acceptable because the MAPI spooler typically uses NOTIFY_BEGIN_INBOUND_FLUSH only in response to a user's request, via a client application, to deliver all messages now.</span></span> <span data-ttu-id="0e5cd-127">在的入站刷新操作的末尾，提供程序应使用**SpoolerNotify**清除 STATUS_INBOUND_FLUSH 标志其状态的行的**PR_STATUS_CODE**属性中。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-127">At the end of the inbound flush operation, the provider should use **SpoolerNotify** to clear the STATUS_INBOUND_FLUSH flag in the **PR_STATUS_CODE** property of its status row.</span></span> 
    
<span data-ttu-id="0e5cd-128">NOTIFY_BEGIN_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="0e5cd-128">NOTIFY_BEGIN_OUTBOUND</span></span> 
  
> <span data-ttu-id="0e5cd-129">出站操作会立即发生该传输提供程序会话的。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-129">Outbound operations can now occur for this transport provider session.</span></span> <span data-ttu-id="0e5cd-130">如果有任何邮件发送此提供程序，遵循对[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-130">If there are any messages to be sent for this provider, a call to the [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) method follows.</span></span> <span data-ttu-id="0e5cd-131">返回之前，应更新此会话状态表格行。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-131">The status table row for this session should be updated before returning.</span></span> <span data-ttu-id="0e5cd-132">NOTIFY_BEGIN_OUTBOUND 和 NOTIFY_END_OUTBOUND 标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-132">The NOTIFY_BEGIN_OUTBOUND and NOTIFY_END_OUTBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="0e5cd-133">NOTIFY_BEGIN_OUTBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="0e5cd-133">NOTIFY_BEGIN_OUTBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="0e5cd-134">工作方式类似于 NOTIFY_BEGIN_INBOUND_FLUSH 标志，但指的出站邮件。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-134">Works similarly to the NOTIFY_BEGIN_INBOUND_FLUSH flag, but refers to outbound messages.</span></span> <span data-ttu-id="0e5cd-135">相应的状态标志是 STATUS_OUTBOUND_FLUSH。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-135">The appropriate status flag is STATUS_OUTBOUND_FLUSH.</span></span>
    
<span data-ttu-id="0e5cd-136">NOTIFY_CANCEL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="0e5cd-136">NOTIFY_CANCEL_MESSAGE</span></span> 
  
> <span data-ttu-id="0e5cd-137">MAPI 后台处理程序必须取消转接呼叫的_lppvData_参数指向的 32 位值从**IXPLogon::SubmitMessage**方法的邮件。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-137">The MAPI spooler must cancel transfer of the message for which the  _lppvData_ parameter points to the 32-bit value from the **IXPLogon::SubmitMessage** method call.</span></span> <span data-ttu-id="0e5cd-138">传输提供程序具有返回来自**SubmitMessage**、 **IXPLogon::StartMessage**或与邮件相关联的**IXPLogon::EndMessage**方法调用的情况下，可设置 NOTIFY_CANCEL_MESSAGE 标志。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-138">The NOTIFY_CANCEL_MESSAGE flag can be set without the transport provider having returned from the **SubmitMessage**, **IXPLogon::StartMessage**, or **IXPLogon::EndMessage** method call that is associated with the message.</span></span> <span data-ttu-id="0e5cd-139">传输提供程序必须尽可能快地返回从处理已取消的邮件的入口点。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-139">The transport provider must return as soon as possible from the entry point that is handling the canceled message.</span></span> <span data-ttu-id="0e5cd-140">当前正在处理入站邮件，传输提供程序应无论目前正在保存传入邮件，并提供再次在下一个方便的时间。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-140">For an inbound message that is currently being processed, the transport provider should save the incoming message wherever it is presently stored and deliver it again at the next convenient time.</span></span> <span data-ttu-id="0e5cd-141">部分将被丢弃的传入邮件已存储的消息对象数据。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-141">The message object data already stored for the incoming message is discarded.</span></span> <span data-ttu-id="0e5cd-142">如果传输提供程序没有**StartMessage**或**SubmitMessage**次更新此 32 位值，则值将为出站邮件 0 和 1 入站邮件。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-142">If the transport provider did not update this 32-bit value at the **StartMessage** or **SubmitMessage** time, the value is 0 for outbound messages and 1 for inbound messages.</span></span> 
    
<span data-ttu-id="0e5cd-143">NOTIFY_END_INBOUND</span><span class="sxs-lookup"><span data-stu-id="0e5cd-143">NOTIFY_END_INBOUND</span></span> 
  
> <span data-ttu-id="0e5cd-144">入站的操作必须停止此传输提供程序会话。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-144">Inbound operations must cease for this transport provider session.</span></span> <span data-ttu-id="0e5cd-145">MAPI 后台处理程序停止使用**投票**方法，并为此会话忽略 NOTIFY_NEWMAIL。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-145">The MAPI spooler ceases to use the **Poll** method and ignores NOTIFY_NEWMAIL for this session.</span></span> <span data-ttu-id="0e5cd-146">应完成在处理邮件。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-146">In-process messages should be completed.</span></span> <span data-ttu-id="0e5cd-147">通过调用[ModifyStatusRow](imapisupport-modifystatusrow.md)返回之前，应更新传输会话状态表格行。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-147">The status table row for the transport session should be updated by calling [ModifyStatusRow](imapisupport-modifystatusrow.md) before returning.</span></span> <span data-ttu-id="0e5cd-148">NOTIFY_END_INBOUND 和 NOTIFY_BEGIN_INBOUND 标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-148">The NOTIFY_END_INBOUND and NOTIFY_BEGIN_INBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="0e5cd-149">NOTIFY_END_INBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="0e5cd-149">NOTIFY_END_INBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="0e5cd-150">通知传输提供程序可以利用入站刷新模式。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-150">Notifies the transport provider to come out of inbound flush mode.</span></span> <span data-ttu-id="0e5cd-151">传输提供程序应停止下载，但在后台应完成下载。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-151">The transport provider should not stop downloading, but downloading should be done in the background.</span></span> <span data-ttu-id="0e5cd-152">通过调用**ModifyStatusRow**传输提供程序可以符合此通知时，应更新传输会话状态表格行。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-152">The status table row for the transport session should be updated by calling **ModifyStatusRow** when the transport provider can comply with this notification.</span></span> 
    
<span data-ttu-id="0e5cd-153">NOTIFY_END_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="0e5cd-153">NOTIFY_END_OUTBOUND</span></span> 
  
> <span data-ttu-id="0e5cd-154">出站操作必须停止此传输提供程序会话。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-154">Outbound operations must cease for this transport provider session.</span></span> <span data-ttu-id="0e5cd-155">MAPI 后台处理程序调用**SubmitMessage**中消失，并忽略**SpoolerNotify** NOTIFY_READYTOSEND 标志。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-155">The MAPI spooler ceases to call **SubmitMessage** and ignores the **SpoolerNotify** NOTIFY_READYTOSEND flag.</span></span> <span data-ttu-id="0e5cd-156">如果没有当前发送出站邮件，则应不停止;若要停止邮件传递，请使用 NOTIFY_CANCEL_MESSAGE 标志。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-156">If there is an outbound message currently being sent, it should not be stopped; to stop delivery of a message, use the NOTIFY_CANCEL_MESSAGE flag.</span></span> <span data-ttu-id="0e5cd-157">通过调用**ModifyStatusRow**返回之前，应更新此会话状态表格行。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-157">The status table row for this session should be updated by calling **ModifyStatusRow** before returning.</span></span> <span data-ttu-id="0e5cd-158">NOTIFY_END_INBOUND 和 NOTIFY_BEGIN_OUTBOUND 标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-158">The NOTIFY_END_INBOUND and NOTIFY_BEGIN_OUTBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="0e5cd-159">NOTIFY_END_OUTBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="0e5cd-159">NOTIFY_END_OUTBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="0e5cd-160">工作原理同样到 NOTIFY_END_INBOUND_FLUSH，但指出站邮件。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-160">Works similarly to NOTIFY_END_INBOUND_FLUSH, but refers to outbound messages.</span></span> <span data-ttu-id="0e5cd-161">相应的状态标志是 STATUS_OUTBOUND_FLUSH。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-161">The appropriate status flag is STATUS_OUTBOUND_FLUSH.</span></span>
    
 <span data-ttu-id="0e5cd-162">_lppvData_</span><span class="sxs-lookup"><span data-stu-id="0e5cd-162">_lppvData_</span></span>
  
> <span data-ttu-id="0e5cd-163">[输出]指向特定于事件的数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-163">[out] A pointer to a pointer to event-specific data.</span></span> <span data-ttu-id="0e5cd-164">有关哪些_lppvData_指定的详细信息，请参阅_lpulFlags_参数的说明。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-164">For more information about what  _lppvData_ specifies, see the description for the  _lpulFlags_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0e5cd-165">返回值</span><span class="sxs-lookup"><span data-stu-id="0e5cd-165">Return value</span></span>

<span data-ttu-id="0e5cd-166">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e5cd-166">S_OK</span></span> 
  
> <span data-ttu-id="0e5cd-167">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-167">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0e5cd-168">备注</span><span class="sxs-lookup"><span data-stu-id="0e5cd-168">Remarks</span></span>

<span data-ttu-id="0e5cd-169">MAPI 后台处理程序调用信号传输提供程序为其请求通知的事件有关的**IXPLogon::TransportNotify**方法。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-169">The MAPI spooler calls the **IXPLogon::TransportNotify** method to signal the transport provider about events for which notification has been requested.</span></span> <span data-ttu-id="0e5cd-170">这些事件包括 MAPI 后台处理程序请求取消邮件传输、 开始或结束的入站或出站传输操作和开始或结束的操作以清除入站或出站消息队列。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-170">These events include a MAPI spooler request to cancel a message transfer, the beginning or ending of inbound or outbound transport operations, and the beginning or ending of an operation to clear an inbound or outbound message queue.</span></span> 
  
<span data-ttu-id="0e5cd-171">当用户尝试取消以前延迟传输提供程序具有一条消息时，MAPI 后台处理程序调用**TransportNotify**中的 NOTIFY_ABORT_DEFERRED 和 NOTIFY_CANCEL_MESSAGE 标志_ulFlags_中传递。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-171">When the user tries to cancel a message that the transport provider has previously deferred, the MAPI spooler calls **TransportNotify**, passing in both the NOTIFY_ABORT_DEFERRED and NOTIFY_CANCEL_MESSAGE flags in  _ulFlags_.</span></span> <span data-ttu-id="0e5cd-172">如果 MAPI 后台处理程序正在注销，仍在队列中邮件，它将传递仅 NOTIFY_ABORT_DEFERRED _ulFlags_中时它调用**TransportNotify**。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-172">If the MAPI spooler is logging off and still has messages in the queue, it passes only NOTIFY_ABORT_DEFERRED in  _ulFlags_ when it calls **TransportNotify**.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0e5cd-173">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="0e5cd-173">Notes to implementers</span></span>

<span data-ttu-id="0e5cd-174">提供程序必须同步到此呼叫，其数据的访问，因为 MAPI 后台处理程序可以调用此方法从另一个线程的执行或过程对于另一个窗口。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-174">The provider must synchronize access to its data on this call, because the MAPI spooler can invoke this method from another thread of execution or from a procedure for a different window.</span></span> <span data-ttu-id="0e5cd-175">这很可能会发生时 MAPI 后台处理程序信号传输提供程序已启动发送一条消息的取消。</span><span class="sxs-lookup"><span data-stu-id="0e5cd-175">This will most likely occur when the MAPI spooler signals the cancellation of a message that the transport provider has started sending.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e5cd-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e5cd-176">See also</span></span>

- [<span data-ttu-id="0e5cd-177">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="0e5cd-177">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md) 
- [<span data-ttu-id="0e5cd-178">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="0e5cd-178">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md) 
- [<span data-ttu-id="0e5cd-179">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="0e5cd-179">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md) 
- [<span data-ttu-id="0e5cd-180">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="0e5cd-180">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md) 
- [<span data-ttu-id="0e5cd-181">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="0e5cd-181">IXPLogon::Poll</span></span>](ixplogon-poll.md)
- [<span data-ttu-id="0e5cd-182">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="0e5cd-182">IXPLogon::StartMessage</span></span>](ixplogon-startmessage.md)
- [<span data-ttu-id="0e5cd-183">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="0e5cd-183">IXPLogon::SubmitMessage</span></span>](ixplogon-submitmessage.md)
- [<span data-ttu-id="0e5cd-184">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="0e5cd-184">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
- [<span data-ttu-id="0e5cd-185">IXPLogon: IUnknown</span><span class="sxs-lookup"><span data-stu-id="0e5cd-185">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

