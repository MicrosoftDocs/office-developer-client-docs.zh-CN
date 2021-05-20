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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2482dc39d3f1d1568b45dd3de88358e08d190be4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428856"
---
# <a name="ixplogontransportnotify"></a><span data-ttu-id="68102-103">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="68102-103">IXPLogon::TransportNotify</span></span>

<span data-ttu-id="68102-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="68102-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="68102-105">指示出现传输提供程序请求通知的事件。</span><span class="sxs-lookup"><span data-stu-id="68102-105">Signals the occurrence of an event about which the transport provider requested notification.</span></span>
  
```cpp
HRESULT TransportNotify(
  ULONG FAR * lpulFlags,
  LPVOID FAR * lppvData
);
```

## <a name="parameters"></a><span data-ttu-id="68102-106">参数</span><span class="sxs-lookup"><span data-stu-id="68102-106">Parameters</span></span>

 <span data-ttu-id="68102-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="68102-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="68102-108">[in， out]向通知事件发送信号的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="68102-108">[in, out] A bitmask of flags that signals notification events.</span></span> <span data-ttu-id="68102-109">以下标志可通过 MAPI 后台处理程序在输入上设置，并且必须在输出上返回未更改：</span><span class="sxs-lookup"><span data-stu-id="68102-109">The following flags can be set by the MAPI spooler on input and must be returned unchanged on output:</span></span>
    
<span data-ttu-id="68102-110">NOTIFY_ABORT_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="68102-110">NOTIFY_ABORT_DEFERRED</span></span> 
  
> <span data-ttu-id="68102-111">通知传输提供程序已接受其责任的邮件正在延迟。</span><span class="sxs-lookup"><span data-stu-id="68102-111">Notifies the transport provider that a message for which it accepted responsibility is being deferred.</span></span> <span data-ttu-id="68102-112">只有支持延迟的传输提供程序必须支持此标志。</span><span class="sxs-lookup"><span data-stu-id="68102-112">Only transport providers that support deferral must support this flag.</span></span> <span data-ttu-id="68102-113">_lppvData_ 参数指向已取消邮件的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="68102-113">The  _lppvData_ parameter points to the entry identifier of the canceled message.</span></span> <span data-ttu-id="68102-114">MAPI 后台处理程序尚未处理的邮件仍可通过调用 [IMsgStore：：AbortSubmit](imsgstore-abortsubmit.md) 方法来延迟。</span><span class="sxs-lookup"><span data-stu-id="68102-114">Messages that the MAPI spooler has not processed can still be deferred by calling the [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) method.</span></span> 
    
<span data-ttu-id="68102-115">NOTIFY_BEGIN_INBOUND</span><span class="sxs-lookup"><span data-stu-id="68102-115">NOTIFY_BEGIN_INBOUND</span></span> 
  
> <span data-ttu-id="68102-116">MAPI 后台处理程序现在可以接受此传输提供程序会话的入站邮件。</span><span class="sxs-lookup"><span data-stu-id="68102-116">The MAPI spooler can now accept inbound messages for this transport provider session.</span></span> <span data-ttu-id="68102-117">如果传输提供程序在登录时通过[IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)调用设置 LOGON_SP_POLL 标志，MAPI 后台处理程序会定期调用[IXPLogon：:P oll](ixplogon-poll.md)方法。</span><span class="sxs-lookup"><span data-stu-id="68102-117">The MAPI spooler regularly calls the [IXPLogon::Poll](ixplogon-poll.md) method if the transport provider set the LOGON_SP_POLL flag with the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) call at logon.</span></span> <span data-ttu-id="68102-118">设置NOTIFY_BEGIN_INBOUND标记后，MAPI 后台处理程序将采用在调用中传递至 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法的 NOTIFY_NEWMAIL 标志。</span><span class="sxs-lookup"><span data-stu-id="68102-118">Once the NOTIFY_BEGIN_INBOUND flag is set, the MAPI spooler honors the NOTIFY_NEWMAIL flag passed in the call to the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method.</span></span> <span data-ttu-id="68102-119">在通过调用 [IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md) 方法返回之前，应更新传输提供程序会话的状态表行。</span><span class="sxs-lookup"><span data-stu-id="68102-119">The status table row for the transport provider session should be updated before returning by calling the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method.</span></span> <span data-ttu-id="68102-120">该NOTIFY_BEGIN_INBOUND和NOTIFY_END_INBOUND标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="68102-120">The NOTIFY_BEGIN_INBOUND and NOTIFY_END_INBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="68102-121">NOTIFY_BEGIN_INBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="68102-121">NOTIFY_BEGIN_INBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="68102-122">指示传输提供商尽快循环访问入站邮件。</span><span class="sxs-lookup"><span data-stu-id="68102-122">Signals the transport provider to cycle through inbound messages as quickly as possible.</span></span> <span data-ttu-id="68102-123">为遵守此通知，传输提供程序应尽快使用 **ModifyStatusRow** 在其状态表行的 PR_STATUS_CODE ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置 **STATUS_INBOUND_FLUSH** 标志。</span><span class="sxs-lookup"><span data-stu-id="68102-123">To comply with this notification, the transport provider should set the STATUS_INBOUND_FLUSH flag in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property of its status table row as soon as it can, by using **ModifyStatusRow**.</span></span> <span data-ttu-id="68102-124">当提供商确定已下载所有邮件时，或收到设置了 NOTIFY_END_INBOUND_FLUSH 标志的 **TransportNotify** 方法调用时，入站邮件循环即完成。</span><span class="sxs-lookup"><span data-stu-id="68102-124">An inbound messaging cycle is complete when the provider determines it has downloaded all it can, or when it has received a **TransportNotify** method call with the NOTIFY_END_INBOUND_FLUSH flag set.</span></span> <span data-ttu-id="68102-125">在入站消息周期结束之前，提供程序不应调用 [IMAPISupport：：SpoolerYield](imapisupport-spooleryield.md) 方法，否则将循环释放到操作系统以加快传入邮件的传递。</span><span class="sxs-lookup"><span data-stu-id="68102-125">Until the end of the inbound messaging cycle, the provider should not call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) method or otherwise relinquish cycles to the operating system to speed delivery of incoming messages.</span></span> <span data-ttu-id="68102-126">这是可接受的，因为 MAPI 后台处理程序通常NOTIFY_BEGIN_INBOUND_FLUSH响应用户的请求（通过客户端应用程序）来现在传递所有邮件。</span><span class="sxs-lookup"><span data-stu-id="68102-126">This is acceptable because the MAPI spooler typically uses NOTIFY_BEGIN_INBOUND_FLUSH only in response to a user's request, via a client application, to deliver all messages now.</span></span> <span data-ttu-id="68102-127">在入站刷新操作结束时，提供程序应该使用 **SpoolerNotify** 清除其状态行的 STATUS_INBOUND_FLUSH PR_STATUS_CODE 标记。 </span><span class="sxs-lookup"><span data-stu-id="68102-127">At the end of the inbound flush operation, the provider should use **SpoolerNotify** to clear the STATUS_INBOUND_FLUSH flag in the **PR_STATUS_CODE** property of its status row.</span></span> 
    
<span data-ttu-id="68102-128">NOTIFY_BEGIN_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="68102-128">NOTIFY_BEGIN_OUTBOUND</span></span> 
  
> <span data-ttu-id="68102-129">现在，可以对此传输提供程序会话执行出站操作。</span><span class="sxs-lookup"><span data-stu-id="68102-129">Outbound operations can now occur for this transport provider session.</span></span> <span data-ttu-id="68102-130">如果有任何要为此提供程序发送的消息，将调用 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="68102-130">If there are any messages to be sent for this provider, a call to the [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) method follows.</span></span> <span data-ttu-id="68102-131">在返回之前，应更新此会话的状态表行。</span><span class="sxs-lookup"><span data-stu-id="68102-131">The status table row for this session should be updated before returning.</span></span> <span data-ttu-id="68102-132">该NOTIFY_BEGIN_OUTBOUND和NOTIFY_END_OUTBOUND标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="68102-132">The NOTIFY_BEGIN_OUTBOUND and NOTIFY_END_OUTBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="68102-133">NOTIFY_BEGIN_OUTBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="68102-133">NOTIFY_BEGIN_OUTBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="68102-134">与邮件NOTIFY_BEGIN_INBOUND_FLUSH类似，但指的是出站邮件。</span><span class="sxs-lookup"><span data-stu-id="68102-134">Works similarly to the NOTIFY_BEGIN_INBOUND_FLUSH flag, but refers to outbound messages.</span></span> <span data-ttu-id="68102-135">相应的状态标志STATUS_OUTBOUND_FLUSH。</span><span class="sxs-lookup"><span data-stu-id="68102-135">The appropriate status flag is STATUS_OUTBOUND_FLUSH.</span></span>
    
<span data-ttu-id="68102-136">NOTIFY_CANCEL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="68102-136">NOTIFY_CANCEL_MESSAGE</span></span> 
  
> <span data-ttu-id="68102-137">MAPI 后台处理程序必须取消传输  _lppvData_ 参数指向 **IXPLogon：：SubmitMessage** 方法调用中的 32 位值的邮件。</span><span class="sxs-lookup"><span data-stu-id="68102-137">The MAPI spooler must cancel transfer of the message for which the  _lppvData_ parameter points to the 32-bit value from the **IXPLogon::SubmitMessage** method call.</span></span> <span data-ttu-id="68102-138">无需传输提供程序从与邮件关联的 **SubmitMessage** **、IXPLogon：：StartMessage** 或 **IXPLogon：：EndMessage** 方法调用返回，即可设置 NOTIFY_CANCEL_MESSAGE 标志。</span><span class="sxs-lookup"><span data-stu-id="68102-138">The NOTIFY_CANCEL_MESSAGE flag can be set without the transport provider having returned from the **SubmitMessage**, **IXPLogon::StartMessage**, or **IXPLogon::EndMessage** method call that is associated with the message.</span></span> <span data-ttu-id="68102-139">传输提供程序必须从处理已取消邮件的入口点尽快返回。</span><span class="sxs-lookup"><span data-stu-id="68102-139">The transport provider must return as soon as possible from the entry point that is handling the canceled message.</span></span> <span data-ttu-id="68102-140">对于当前正在处理的入站邮件，传输提供程序应该将传入邮件保存到当前存储的位置，并下次方便时再次传递。</span><span class="sxs-lookup"><span data-stu-id="68102-140">For an inbound message that is currently being processed, the transport provider should save the incoming message wherever it is presently stored and deliver it again at the next convenient time.</span></span> <span data-ttu-id="68102-141">已为传入邮件存储的邮件对象数据将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="68102-141">The message object data already stored for the incoming message is discarded.</span></span> <span data-ttu-id="68102-142">如果传输提供程序在 **StartMessage 或 SubmitMessage** 时未更新此 32 位值，则出站邮件的值为 0，入站邮件的值为 1。</span><span class="sxs-lookup"><span data-stu-id="68102-142">If the transport provider did not update this 32-bit value at the **StartMessage** or **SubmitMessage** time, the value is 0 for outbound messages and 1 for inbound messages.</span></span> 
    
<span data-ttu-id="68102-143">NOTIFY_END_INBOUND</span><span class="sxs-lookup"><span data-stu-id="68102-143">NOTIFY_END_INBOUND</span></span> 
  
> <span data-ttu-id="68102-144">对于此传输提供程序会话，入站操作必须停止。</span><span class="sxs-lookup"><span data-stu-id="68102-144">Inbound operations must cease for this transport provider session.</span></span> <span data-ttu-id="68102-145">MAPI 后台处理程序将停止使用 **Poll** 方法，并忽略NOTIFY_NEWMAIL的轮询。</span><span class="sxs-lookup"><span data-stu-id="68102-145">The MAPI spooler ceases to use the **Poll** method and ignores NOTIFY_NEWMAIL for this session.</span></span> <span data-ttu-id="68102-146">应完成进程内消息。</span><span class="sxs-lookup"><span data-stu-id="68102-146">In-process messages should be completed.</span></span> <span data-ttu-id="68102-147">传输会话的状态表行应在返回前通过调用 [ModifyStatusRow](imapisupport-modifystatusrow.md) 进行更新。</span><span class="sxs-lookup"><span data-stu-id="68102-147">The status table row for the transport session should be updated by calling [ModifyStatusRow](imapisupport-modifystatusrow.md) before returning.</span></span> <span data-ttu-id="68102-148">该NOTIFY_END_INBOUND和NOTIFY_BEGIN_INBOUND标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="68102-148">The NOTIFY_END_INBOUND and NOTIFY_BEGIN_INBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="68102-149">NOTIFY_END_INBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="68102-149">NOTIFY_END_INBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="68102-150">通知传输提供程序退出入站刷新模式。</span><span class="sxs-lookup"><span data-stu-id="68102-150">Notifies the transport provider to come out of inbound flush mode.</span></span> <span data-ttu-id="68102-151">传输提供程序不应停止下载，但应在后台进行下载。</span><span class="sxs-lookup"><span data-stu-id="68102-151">The transport provider should not stop downloading, but downloading should be done in the background.</span></span> <span data-ttu-id="68102-152">传输会话的状态表行应在传输提供程序符合此通知时通过调用 **ModifyStatusRow** 进行更新。</span><span class="sxs-lookup"><span data-stu-id="68102-152">The status table row for the transport session should be updated by calling **ModifyStatusRow** when the transport provider can comply with this notification.</span></span> 
    
<span data-ttu-id="68102-153">NOTIFY_END_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="68102-153">NOTIFY_END_OUTBOUND</span></span> 
  
> <span data-ttu-id="68102-154">对于此传输提供程序会话，出站操作必须停止。</span><span class="sxs-lookup"><span data-stu-id="68102-154">Outbound operations must cease for this transport provider session.</span></span> <span data-ttu-id="68102-155">MAPI 后台处理程序停止调用 **SubmitMessage** 并忽略 **SpoolerNotify** NOTIFY_READYTOSEND标志。</span><span class="sxs-lookup"><span data-stu-id="68102-155">The MAPI spooler ceases to call **SubmitMessage** and ignores the **SpoolerNotify** NOTIFY_READYTOSEND flag.</span></span> <span data-ttu-id="68102-156">如果当前正在发送出站邮件，则不应停止;若要停止传递邮件，请使用 NOTIFY_CANCEL_MESSAGE 标志。</span><span class="sxs-lookup"><span data-stu-id="68102-156">If there is an outbound message currently being sent, it should not be stopped; to stop delivery of a message, use the NOTIFY_CANCEL_MESSAGE flag.</span></span> <span data-ttu-id="68102-157">应先调用 **ModifyStatusRow** 更新此会话的状态表行，然后再返回。</span><span class="sxs-lookup"><span data-stu-id="68102-157">The status table row for this session should be updated by calling **ModifyStatusRow** before returning.</span></span> <span data-ttu-id="68102-158">该NOTIFY_END_INBOUND和NOTIFY_BEGIN_OUTBOUND标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="68102-158">The NOTIFY_END_INBOUND and NOTIFY_BEGIN_OUTBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="68102-159">NOTIFY_END_OUTBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="68102-159">NOTIFY_END_OUTBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="68102-160">与邮件NOTIFY_END_INBOUND_FLUSH类似，但指的是出站邮件。</span><span class="sxs-lookup"><span data-stu-id="68102-160">Works similarly to NOTIFY_END_INBOUND_FLUSH, but refers to outbound messages.</span></span> <span data-ttu-id="68102-161">相应的状态标志STATUS_OUTBOUND_FLUSH。</span><span class="sxs-lookup"><span data-stu-id="68102-161">The appropriate status flag is STATUS_OUTBOUND_FLUSH.</span></span>
    
 <span data-ttu-id="68102-162">_lppvData_</span><span class="sxs-lookup"><span data-stu-id="68102-162">_lppvData_</span></span>
  
> <span data-ttu-id="68102-163">[out]指向特定于事件的数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="68102-163">[out] A pointer to a pointer to event-specific data.</span></span> <span data-ttu-id="68102-164">有关  _lppvData 指定_ 内容的信息，请参阅  _lpulFlags_ 参数的说明。</span><span class="sxs-lookup"><span data-stu-id="68102-164">For more information about what  _lppvData_ specifies, see the description for the  _lpulFlags_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="68102-165">返回值</span><span class="sxs-lookup"><span data-stu-id="68102-165">Return value</span></span>

<span data-ttu-id="68102-166">S_OK</span><span class="sxs-lookup"><span data-stu-id="68102-166">S_OK</span></span> 
  
> <span data-ttu-id="68102-167">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="68102-167">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="68102-168">备注</span><span class="sxs-lookup"><span data-stu-id="68102-168">Remarks</span></span>

<span data-ttu-id="68102-169">MAPI 后台处理程序调用 **IXPLogon：：TransportNotify** 方法，向传输提供程序发送有关已请求通知的事件的信号。</span><span class="sxs-lookup"><span data-stu-id="68102-169">The MAPI spooler calls the **IXPLogon::TransportNotify** method to signal the transport provider about events for which notification has been requested.</span></span> <span data-ttu-id="68102-170">这些事件包括取消邮件传输的 MAPI 后台处理程序请求、入站或出站传输操作开始或结束，以及清除入站或出站邮件队列的操作的开始或结束。</span><span class="sxs-lookup"><span data-stu-id="68102-170">These events include a MAPI spooler request to cancel a message transfer, the beginning or ending of inbound or outbound transport operations, and the beginning or ending of an operation to clear an inbound or outbound message queue.</span></span> 
  
<span data-ttu-id="68102-171">当用户尝试取消传输提供程序之前已延迟的邮件时，MAPI 后台处理程序将调用 **TransportNotify**，在  _ulFlags_ 中同时传递 NOTIFY_ABORT_DEFERRED 和 NOTIFY_CANCEL_MESSAGE 标志。</span><span class="sxs-lookup"><span data-stu-id="68102-171">When the user tries to cancel a message that the transport provider has previously deferred, the MAPI spooler calls **TransportNotify**, passing in both the NOTIFY_ABORT_DEFERRED and NOTIFY_CANCEL_MESSAGE flags in  _ulFlags_.</span></span> <span data-ttu-id="68102-172">如果 MAPI 后台处理程序正在注销并且队列中仍有消息，则它在调用 **TransportNotify** NOTIFY_ABORT_DEFERRED _仅在 ulFlags_ 中传递消息。</span><span class="sxs-lookup"><span data-stu-id="68102-172">If the MAPI spooler is logging off and still has messages in the queue, it passes only NOTIFY_ABORT_DEFERRED in  _ulFlags_ when it calls **TransportNotify**.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="68102-173">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="68102-173">Notes to implementers</span></span>

<span data-ttu-id="68102-174">提供程序必须同步对此调用中其数据的访问，因为 MAPI 后台处理程序可以从另一个执行线程或其他窗口的过程调用此方法。</span><span class="sxs-lookup"><span data-stu-id="68102-174">The provider must synchronize access to its data on this call, because the MAPI spooler can invoke this method from another thread of execution or from a procedure for a different window.</span></span> <span data-ttu-id="68102-175">当 MAPI 后台处理程序发出取消传输提供程序已开始发送的邮件的信号时，很可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="68102-175">This will most likely occur when the MAPI spooler signals the cancellation of a message that the transport provider has started sending.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="68102-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68102-176">See also</span></span>

- [<span data-ttu-id="68102-177">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="68102-177">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md) 
- [<span data-ttu-id="68102-178">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="68102-178">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md) 
- [<span data-ttu-id="68102-179">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="68102-179">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md) 
- [<span data-ttu-id="68102-180">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="68102-180">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md) 
- [<span data-ttu-id="68102-181">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="68102-181">IXPLogon::Poll</span></span>](ixplogon-poll.md)
- [<span data-ttu-id="68102-182">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="68102-182">IXPLogon::StartMessage</span></span>](ixplogon-startmessage.md)
- [<span data-ttu-id="68102-183">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="68102-183">IXPLogon::SubmitMessage</span></span>](ixplogon-submitmessage.md)
- [<span data-ttu-id="68102-184">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="68102-184">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
- [<span data-ttu-id="68102-185">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="68102-185">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

