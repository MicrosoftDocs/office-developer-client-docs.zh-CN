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
# <a name="ixplogontransportnotify"></a><span data-ttu-id="262fc-103">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="262fc-103">IXPLogon::TransportNotify</span></span>

<span data-ttu-id="262fc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="262fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="262fc-105">指示发生了传输提供程序请求通知的事件。</span><span class="sxs-lookup"><span data-stu-id="262fc-105">Signals the occurrence of an event about which the transport provider requested notification.</span></span>
  
```cpp
HRESULT TransportNotify(
  ULONG FAR * lpulFlags,
  LPVOID FAR * lppvData
);
```

## <a name="parameters"></a><span data-ttu-id="262fc-106">参数</span><span class="sxs-lookup"><span data-stu-id="262fc-106">Parameters</span></span>

 <span data-ttu-id="262fc-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="262fc-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="262fc-108">[in, out]指示通知事件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="262fc-108">[in, out] A bitmask of flags that signals notification events.</span></span> <span data-ttu-id="262fc-109">在输入时, MAPI 后台处理程序可以设置以下标志, 并且在输出时必须返回不变的标志:</span><span class="sxs-lookup"><span data-stu-id="262fc-109">The following flags can be set by the MAPI spooler on input and must be returned unchanged on output:</span></span>
    
<span data-ttu-id="262fc-110">NOTIFY_ABORT_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="262fc-110">NOTIFY_ABORT_DEFERRED</span></span> 
  
> <span data-ttu-id="262fc-111">通知传输提供程序其接受其接受责任的邮件已延迟。</span><span class="sxs-lookup"><span data-stu-id="262fc-111">Notifies the transport provider that a message for which it accepted responsibility is being deferred.</span></span> <span data-ttu-id="262fc-112">仅支持延期的传输提供程序必须支持此标志。</span><span class="sxs-lookup"><span data-stu-id="262fc-112">Only transport providers that support deferral must support this flag.</span></span> <span data-ttu-id="262fc-113">_lppvData_参数指向已取消邮件的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="262fc-113">The  _lppvData_ parameter points to the entry identifier of the canceled message.</span></span> <span data-ttu-id="262fc-114">MAPI 后台处理程序尚未处理的邮件仍可以通过调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)方法来延迟。</span><span class="sxs-lookup"><span data-stu-id="262fc-114">Messages that the MAPI spooler has not processed can still be deferred by calling the [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) method.</span></span> 
    
<span data-ttu-id="262fc-115">NOTIFY_BEGIN_INBOUND</span><span class="sxs-lookup"><span data-stu-id="262fc-115">NOTIFY_BEGIN_INBOUND</span></span> 
  
> <span data-ttu-id="262fc-116">MAPI 后台处理程序现在可以接受此传输提供程序会话的入站邮件。</span><span class="sxs-lookup"><span data-stu-id="262fc-116">The MAPI spooler can now accept inbound messages for this transport provider session.</span></span> <span data-ttu-id="262fc-117">如果传输提供程序在登录时将 LOGON_SP_POLL 标记设置为[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md) , MAPI 后台处理程序将定期调用[IXPLogon::P oll](ixplogon-poll.md)方法。</span><span class="sxs-lookup"><span data-stu-id="262fc-117">The MAPI spooler regularly calls the [IXPLogon::Poll](ixplogon-poll.md) method if the transport provider set the LOGON_SP_POLL flag with the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) call at logon.</span></span> <span data-ttu-id="262fc-118">设置 NOTIFY_BEGIN_INBOUND 标志后, MAPI 后台处理程序会在调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法时接受在调用中传递的 NOTIFY_NEWMAIL 标志。</span><span class="sxs-lookup"><span data-stu-id="262fc-118">Once the NOTIFY_BEGIN_INBOUND flag is set, the MAPI spooler honors the NOTIFY_NEWMAIL flag passed in the call to the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method.</span></span> <span data-ttu-id="262fc-119">在返回之前, 应通过调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法来更新传输提供程序会话的状态表格行。</span><span class="sxs-lookup"><span data-stu-id="262fc-119">The status table row for the transport provider session should be updated before returning by calling the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method.</span></span> <span data-ttu-id="262fc-120">NOTIFY_BEGIN_INBOUND 和 NOTIFY_END_INBOUND 标志是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="262fc-120">The NOTIFY_BEGIN_INBOUND and NOTIFY_END_INBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="262fc-121">NOTIFY_BEGIN_INBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="262fc-121">NOTIFY_BEGIN_INBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="262fc-122">通知传输提供程序尽快通过入站邮件进行循环。</span><span class="sxs-lookup"><span data-stu-id="262fc-122">Signals the transport provider to cycle through inbound messages as quickly as possible.</span></span> <span data-ttu-id="262fc-123">若要符合此通知, 传输提供程序应尽快在其状态表行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置 STATUS_INBOUND_FLUSH 标志, 方法是使用**ModifyStatusRow**。</span><span class="sxs-lookup"><span data-stu-id="262fc-123">To comply with this notification, the transport provider should set the STATUS_INBOUND_FLUSH flag in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property of its status table row as soon as it can, by using **ModifyStatusRow**.</span></span> <span data-ttu-id="262fc-124">当提供程序确定已下载所有的传入邮件循环时, 或者在使用 NOTIFY_END_INBOUND_FLUSH 标志集收到**TransportNotify**方法调用时, 该循环将完成。</span><span class="sxs-lookup"><span data-stu-id="262fc-124">An inbound messaging cycle is complete when the provider determines it has downloaded all it can, or when it has received a **TransportNotify** method call with the NOTIFY_END_INBOUND_FLUSH flag set.</span></span> <span data-ttu-id="262fc-125">在入站邮件循环结束之前, 提供程序不应调用[IMAPISupport:: SpoolerYield](imapisupport-spooleryield.md)方法或以其他方式放弃操作系统以加快传入邮件的传递。</span><span class="sxs-lookup"><span data-stu-id="262fc-125">Until the end of the inbound messaging cycle, the provider should not call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) method or otherwise relinquish cycles to the operating system to speed delivery of incoming messages.</span></span> <span data-ttu-id="262fc-126">这是可以接受的, 因为 MAPI 后台处理程序通常仅使用 NOTIFY_BEGIN_INBOUND_FLUSH 响应用户的请求, 通过客户端应用程序立即传递所有邮件。</span><span class="sxs-lookup"><span data-stu-id="262fc-126">This is acceptable because the MAPI spooler typically uses NOTIFY_BEGIN_INBOUND_FLUSH only in response to a user's request, via a client application, to deliver all messages now.</span></span> <span data-ttu-id="262fc-127">在入站刷新操作结束时, 提供程序应使用**SpoolerNotify**来清除其状态行的**PR_STATUS_CODE**属性中的 STATUS_INBOUND_FLUSH 标志。</span><span class="sxs-lookup"><span data-stu-id="262fc-127">At the end of the inbound flush operation, the provider should use **SpoolerNotify** to clear the STATUS_INBOUND_FLUSH flag in the **PR_STATUS_CODE** property of its status row.</span></span> 
    
<span data-ttu-id="262fc-128">NOTIFY_BEGIN_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="262fc-128">NOTIFY_BEGIN_OUTBOUND</span></span> 
  
> <span data-ttu-id="262fc-129">现在可以对此传输提供程序会话执行出站操作。</span><span class="sxs-lookup"><span data-stu-id="262fc-129">Outbound operations can now occur for this transport provider session.</span></span> <span data-ttu-id="262fc-130">如果要为此提供程序发送的任何邮件, 请调用[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="262fc-130">If there are any messages to be sent for this provider, a call to the [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) method follows.</span></span> <span data-ttu-id="262fc-131">应在返回之前更新此会话的状态表行。</span><span class="sxs-lookup"><span data-stu-id="262fc-131">The status table row for this session should be updated before returning.</span></span> <span data-ttu-id="262fc-132">NOTIFY_BEGIN_OUTBOUND 和 NOTIFY_END_OUTBOUND 标志是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="262fc-132">The NOTIFY_BEGIN_OUTBOUND and NOTIFY_END_OUTBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="262fc-133">NOTIFY_BEGIN_OUTBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="262fc-133">NOTIFY_BEGIN_OUTBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="262fc-134">的工作方式与 NOTIFY_BEGIN_INBOUND_FLUSH 标志类似, 但引用出站邮件。</span><span class="sxs-lookup"><span data-stu-id="262fc-134">Works similarly to the NOTIFY_BEGIN_INBOUND_FLUSH flag, but refers to outbound messages.</span></span> <span data-ttu-id="262fc-135">相应的状态标志为 STATUS_OUTBOUND_FLUSH。</span><span class="sxs-lookup"><span data-stu-id="262fc-135">The appropriate status flag is STATUS_OUTBOUND_FLUSH.</span></span>
    
<span data-ttu-id="262fc-136">NOTIFY_CANCEL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="262fc-136">NOTIFY_CANCEL_MESSAGE</span></span> 
  
> <span data-ttu-id="262fc-137">MAPI 后台处理程序必须取消从**IXPLogon:: SubmitMessage**方法调用的_lppvData_参数指向32位值的邮件的传输。</span><span class="sxs-lookup"><span data-stu-id="262fc-137">The MAPI spooler must cancel transfer of the message for which the  _lppvData_ parameter points to the 32-bit value from the **IXPLogon::SubmitMessage** method call.</span></span> <span data-ttu-id="262fc-138">可以在没有传输提供程序的情况下设置 NOTIFY_CANCEL_MESSAGE 标志, 该传输提供程序从**SubmitMessage**、 **IXPLogon:: StartMessage**或**IXPLogon:: EndMessage**方法调用 (与邮件关联) 中返回。</span><span class="sxs-lookup"><span data-stu-id="262fc-138">The NOTIFY_CANCEL_MESSAGE flag can be set without the transport provider having returned from the **SubmitMessage**, **IXPLogon::StartMessage**, or **IXPLogon::EndMessage** method call that is associated with the message.</span></span> <span data-ttu-id="262fc-139">传输提供程序必须从处理已取消的邮件的入口点尽快返回。</span><span class="sxs-lookup"><span data-stu-id="262fc-139">The transport provider must return as soon as possible from the entry point that is handling the canceled message.</span></span> <span data-ttu-id="262fc-140">对于当前正在处理的入站邮件, 传输提供程序应在其当前存储的任何位置保存传入邮件, 并在下一个方便的时间再次传递该邮件。</span><span class="sxs-lookup"><span data-stu-id="262fc-140">For an inbound message that is currently being processed, the transport provider should save the incoming message wherever it is presently stored and deliver it again at the next convenient time.</span></span> <span data-ttu-id="262fc-141">已为传入邮件存储的邮件对象数据将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="262fc-141">The message object data already stored for the incoming message is discarded.</span></span> <span data-ttu-id="262fc-142">如果传输提供程序未在**StartMessage**或**SubmitMessage**时间更新此32位值, 则值为0表示出站邮件, 1 表示入站邮件。</span><span class="sxs-lookup"><span data-stu-id="262fc-142">If the transport provider did not update this 32-bit value at the **StartMessage** or **SubmitMessage** time, the value is 0 for outbound messages and 1 for inbound messages.</span></span> 
    
<span data-ttu-id="262fc-143">NOTIFY_END_INBOUND</span><span class="sxs-lookup"><span data-stu-id="262fc-143">NOTIFY_END_INBOUND</span></span> 
  
> <span data-ttu-id="262fc-144">对于此传输提供程序会话, 入站操作必须停止。</span><span class="sxs-lookup"><span data-stu-id="262fc-144">Inbound operations must cease for this transport provider session.</span></span> <span data-ttu-id="262fc-145">MAPI 后台处理程序将停止使用**轮询**方法, 并忽略此会话的 NOTIFY_NEWMAIL。</span><span class="sxs-lookup"><span data-stu-id="262fc-145">The MAPI spooler ceases to use the **Poll** method and ignores NOTIFY_NEWMAIL for this session.</span></span> <span data-ttu-id="262fc-146">应完成进程内邮件。</span><span class="sxs-lookup"><span data-stu-id="262fc-146">In-process messages should be completed.</span></span> <span data-ttu-id="262fc-147">应在返回之前调用[ModifyStatusRow](imapisupport-modifystatusrow.md) , 以更新传输会话的状态表格行。</span><span class="sxs-lookup"><span data-stu-id="262fc-147">The status table row for the transport session should be updated by calling [ModifyStatusRow](imapisupport-modifystatusrow.md) before returning.</span></span> <span data-ttu-id="262fc-148">NOTIFY_END_INBOUND 和 NOTIFY_BEGIN_INBOUND 标志是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="262fc-148">The NOTIFY_END_INBOUND and NOTIFY_BEGIN_INBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="262fc-149">NOTIFY_END_INBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="262fc-149">NOTIFY_END_INBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="262fc-150">通知传输提供程序无法进入入站刷新模式。</span><span class="sxs-lookup"><span data-stu-id="262fc-150">Notifies the transport provider to come out of inbound flush mode.</span></span> <span data-ttu-id="262fc-151">传输提供程序不应停止下载, 但应在后台进行下载。</span><span class="sxs-lookup"><span data-stu-id="262fc-151">The transport provider should not stop downloading, but downloading should be done in the background.</span></span> <span data-ttu-id="262fc-152">传输会话的状态表行应在传输提供程序可以符合此通知时调用**ModifyStatusRow**进行更新。</span><span class="sxs-lookup"><span data-stu-id="262fc-152">The status table row for the transport session should be updated by calling **ModifyStatusRow** when the transport provider can comply with this notification.</span></span> 
    
<span data-ttu-id="262fc-153">NOTIFY_END_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="262fc-153">NOTIFY_END_OUTBOUND</span></span> 
  
> <span data-ttu-id="262fc-154">对于此传输提供程序会话, 出站操作必须停止。</span><span class="sxs-lookup"><span data-stu-id="262fc-154">Outbound operations must cease for this transport provider session.</span></span> <span data-ttu-id="262fc-155">MAPI 后台处理程序将停止调用**SubmitMessage**并忽略**SpoolerNotify** NOTIFY_READYTOSEND 标记。</span><span class="sxs-lookup"><span data-stu-id="262fc-155">The MAPI spooler ceases to call **SubmitMessage** and ignores the **SpoolerNotify** NOTIFY_READYTOSEND flag.</span></span> <span data-ttu-id="262fc-156">如果当前正在发送出站邮件, 则不应将其停止;若要停止传递邮件, 请使用 NOTIFY_CANCEL_MESSAGE 标志。</span><span class="sxs-lookup"><span data-stu-id="262fc-156">If there is an outbound message currently being sent, it should not be stopped; to stop delivery of a message, use the NOTIFY_CANCEL_MESSAGE flag.</span></span> <span data-ttu-id="262fc-157">在返回之前, 应通过调用**ModifyStatusRow**更新此会话的状态表格行。</span><span class="sxs-lookup"><span data-stu-id="262fc-157">The status table row for this session should be updated by calling **ModifyStatusRow** before returning.</span></span> <span data-ttu-id="262fc-158">NOTIFY_END_INBOUND 和 NOTIFY_BEGIN_OUTBOUND 标志是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="262fc-158">The NOTIFY_END_INBOUND and NOTIFY_BEGIN_OUTBOUND flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="262fc-159">NOTIFY_END_OUTBOUND_FLUSH</span><span class="sxs-lookup"><span data-stu-id="262fc-159">NOTIFY_END_OUTBOUND_FLUSH</span></span> 
  
> <span data-ttu-id="262fc-160">的工作方式与 NOTIFY_END_INBOUND_FLUSH 类似, 但引用出站邮件。</span><span class="sxs-lookup"><span data-stu-id="262fc-160">Works similarly to NOTIFY_END_INBOUND_FLUSH, but refers to outbound messages.</span></span> <span data-ttu-id="262fc-161">相应的状态标志为 STATUS_OUTBOUND_FLUSH。</span><span class="sxs-lookup"><span data-stu-id="262fc-161">The appropriate status flag is STATUS_OUTBOUND_FLUSH.</span></span>
    
 <span data-ttu-id="262fc-162">_lppvData_</span><span class="sxs-lookup"><span data-stu-id="262fc-162">_lppvData_</span></span>
  
> <span data-ttu-id="262fc-163">排除指向指向事件特定数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="262fc-163">[out] A pointer to a pointer to event-specific data.</span></span> <span data-ttu-id="262fc-164">有关_lppvData_指定的内容的详细信息, 请参阅_lpulFlags_参数的说明。</span><span class="sxs-lookup"><span data-stu-id="262fc-164">For more information about what  _lppvData_ specifies, see the description for the  _lpulFlags_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="262fc-165">返回值</span><span class="sxs-lookup"><span data-stu-id="262fc-165">Return value</span></span>

<span data-ttu-id="262fc-166">S_OK</span><span class="sxs-lookup"><span data-stu-id="262fc-166">S_OK</span></span> 
  
> <span data-ttu-id="262fc-167">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="262fc-167">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="262fc-168">说明</span><span class="sxs-lookup"><span data-stu-id="262fc-168">Remarks</span></span>

<span data-ttu-id="262fc-169">MAPI 后台处理程序调用**IXPLogon:: TransportNotify**方法向传输提供程序发出通知请求的事件。</span><span class="sxs-lookup"><span data-stu-id="262fc-169">The MAPI spooler calls the **IXPLogon::TransportNotify** method to signal the transport provider about events for which notification has been requested.</span></span> <span data-ttu-id="262fc-170">这些事件包括取消邮件传输的 MAPI 后台处理程序请求、入站或出站传输操作的开始或结束以及清除入站或出站邮件队列的操作的开始或结束。</span><span class="sxs-lookup"><span data-stu-id="262fc-170">These events include a MAPI spooler request to cancel a message transfer, the beginning or ending of inbound or outbound transport operations, and the beginning or ending of an operation to clear an inbound or outbound message queue.</span></span> 
  
<span data-ttu-id="262fc-171">当用户尝试取消传输提供程序之前已延迟的邮件时, MAPI 后台处理程序将调用**TransportNotify**, 同时在_ulFlags_中传入 NOTIFY_ABORT_DEFERRED 和 NOTIFY_CANCEL_MESSAGE 标志。</span><span class="sxs-lookup"><span data-stu-id="262fc-171">When the user tries to cancel a message that the transport provider has previously deferred, the MAPI spooler calls **TransportNotify**, passing in both the NOTIFY_ABORT_DEFERRED and NOTIFY_CANCEL_MESSAGE flags in  _ulFlags_.</span></span> <span data-ttu-id="262fc-172">如果 MAPI 后台处理程序正在注销, 并且队列中仍有邮件, 则它会在调用**TransportNotify**时仅在_ulFlags_中传递 NOTIFY_ABORT_DEFERRED。</span><span class="sxs-lookup"><span data-stu-id="262fc-172">If the MAPI spooler is logging off and still has messages in the queue, it passes only NOTIFY_ABORT_DEFERRED in  _ulFlags_ when it calls **TransportNotify**.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="262fc-173">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="262fc-173">Notes to implementers</span></span>

<span data-ttu-id="262fc-174">提供程序必须在此调用上同步对其数据的访问, 因为 MAPI 后台处理程序可以从另一个执行线程或从另一个窗口的过程中调用此方法。</span><span class="sxs-lookup"><span data-stu-id="262fc-174">The provider must synchronize access to its data on this call, because the MAPI spooler can invoke this method from another thread of execution or from a procedure for a different window.</span></span> <span data-ttu-id="262fc-175">当 MAPI 后台处理程序发出邮件的取消通知传输提供程序已开始发送邮件时, 这很可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="262fc-175">This will most likely occur when the MAPI spooler signals the cancellation of a message that the transport provider has started sending.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="262fc-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="262fc-176">See also</span></span>

- [<span data-ttu-id="262fc-177">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="262fc-177">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md) 
- [<span data-ttu-id="262fc-178">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="262fc-178">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md) 
- [<span data-ttu-id="262fc-179">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="262fc-179">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md) 
- [<span data-ttu-id="262fc-180">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="262fc-180">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md) 
- [<span data-ttu-id="262fc-181">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="262fc-181">IXPLogon::Poll</span></span>](ixplogon-poll.md)
- [<span data-ttu-id="262fc-182">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="262fc-182">IXPLogon::StartMessage</span></span>](ixplogon-startmessage.md)
- [<span data-ttu-id="262fc-183">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="262fc-183">IXPLogon::SubmitMessage</span></span>](ixplogon-submitmessage.md)
- [<span data-ttu-id="262fc-184">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="262fc-184">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
- [<span data-ttu-id="262fc-185">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="262fc-185">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

