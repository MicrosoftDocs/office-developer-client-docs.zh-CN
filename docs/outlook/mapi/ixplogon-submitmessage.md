---
title: IXPLogonSubmitMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.SubmitMessage
api_type:
- COM
ms.assetid: a261ba0d-cb56-4935-b745-1d4bbd0b8b9d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae124cb94cff5be0a655386d31f1bf2c82f66a85
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423319"
---
# <a name="ixplogonsubmitmessage"></a><span data-ttu-id="f60b1-103">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="f60b1-103">IXPLogon::SubmitMessage</span></span>

  
  
<span data-ttu-id="f60b1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f60b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f60b1-105">指示 MAPI 后台处理程序具有要传递的传输提供程序的邮件。</span><span class="sxs-lookup"><span data-stu-id="f60b1-105">Indicates that the MAPI spooler has a message for the transport provider to deliver.</span></span>
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef,
  ULONG FAR * lpulReturnParm
);
```

## <a name="parameters"></a><span data-ttu-id="f60b1-106">参数</span><span class="sxs-lookup"><span data-stu-id="f60b1-106">Parameters</span></span>

 <span data-ttu-id="f60b1-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f60b1-107">_ulFlags_</span></span>
  
> <span data-ttu-id="f60b1-108">[in]控制邮件提交方式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="f60b1-108">[in] A bitmask of flags that controls how the message is submitted.</span></span> <span data-ttu-id="f60b1-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f60b1-109">The following flag can be set:</span></span>
    
<span data-ttu-id="f60b1-110">BEGIN_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="f60b1-110">BEGIN_DEFERRED</span></span> 
  
> <span data-ttu-id="f60b1-111">MAPI 后台处理程序使用之前延迟的邮件调用传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="f60b1-111">The MAPI spooler is calling a transport provider with a message that was previously deferred.</span></span> <span data-ttu-id="f60b1-112">邮件的条目标识符与延迟时相同。</span><span class="sxs-lookup"><span data-stu-id="f60b1-112">The entry identifier of the message is the same as when it was deferred.</span></span> <span data-ttu-id="f60b1-113">通过使用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法（带 NOTIFY_SENTDEFERRED 标志）将邮件传递回 MAPI 后台处理程序，延迟了消息。</span><span class="sxs-lookup"><span data-stu-id="f60b1-113">The message was deferred by passing its entry identifier back to the MAPI spooler by using the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method with the NOTIFY_SENTDEFERRED flag.</span></span> 
    
 <span data-ttu-id="f60b1-114">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="f60b1-114">_lpMessage_</span></span>
  
> <span data-ttu-id="f60b1-115">[in]指向邮件对象 (表示要传递的邮件) 具有读/写权限的邮件对象，传输提供程序使用该指针访问和处理该邮件。</span><span class="sxs-lookup"><span data-stu-id="f60b1-115">[in] A pointer to a message object (representing the message to deliver) that has read/write permission, which the transport provider uses to access and manipulate that message.</span></span> <span data-ttu-id="f60b1-116">在传输提供程序从对 [IXPLogon：：EndMessage](ixplogon-endmessage.md) 方法的后续调用返回之前，此对象一直有效。</span><span class="sxs-lookup"><span data-stu-id="f60b1-116">This object remains valid until after the transport provider returns from a subsequent call to the [IXPLogon::EndMessage](ixplogon-endmessage.md) method.</span></span> 
    
 <span data-ttu-id="f60b1-117">_lpulMsgRef_</span><span class="sxs-lookup"><span data-stu-id="f60b1-117">_lpulMsgRef_</span></span>
  
> <span data-ttu-id="f60b1-118">[out]指向一个变量的指针，传输提供程序在此变量中返回分配给此邮件的引用值。</span><span class="sxs-lookup"><span data-stu-id="f60b1-118">[out] A pointer to a variable in which the transport provider returns the reference value it assigned to this message.</span></span> <span data-ttu-id="f60b1-119">MAPI 后台处理程序在此消息的后续调用中传递此引用值。</span><span class="sxs-lookup"><span data-stu-id="f60b1-119">The MAPI spooler passes this reference value in subsequent calls for this message.</span></span> <span data-ttu-id="f60b1-120">MAPI 后台处理程序将该值初始化为 0，然后再将该值返回到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="f60b1-120">The MAPI spooler initializes the value to 0 before returning it to the transport provider.</span></span>
    
 <span data-ttu-id="f60b1-121">_lpulReturnParm_</span><span class="sxs-lookup"><span data-stu-id="f60b1-121">_lpulReturnParm_</span></span>
  
> <span data-ttu-id="f60b1-122">[out]指向对应于 **SubmitMessage** 返回的错误MAPI_E_WAIT或MAPI_E_NETWORK_ERROR返回的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="f60b1-122">[out] A pointer to a variable that corresponds to the MAPI_E_WAIT or MAPI_E_NETWORK_ERROR error value returned by **SubmitMessage**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f60b1-123">返回值</span><span class="sxs-lookup"><span data-stu-id="f60b1-123">Return value</span></span>

<span data-ttu-id="f60b1-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="f60b1-124">S_OK</span></span> 
  
> <span data-ttu-id="f60b1-125">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="f60b1-125">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="f60b1-126">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="f60b1-126">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="f60b1-127">传输提供程序无法处理邮件，因为它正在执行另一个操作。</span><span class="sxs-lookup"><span data-stu-id="f60b1-127">The transport provider cannot handle the message, because it is performing another operation.</span></span> <span data-ttu-id="f60b1-128">提供程序应该使用此返回值来指示未进行处理，并且 MAPI 后台处理程序不应调用 **EndMessage**。</span><span class="sxs-lookup"><span data-stu-id="f60b1-128">A provider should use this return value to indicate that no processing occurred and that the MAPI spooler should not call **EndMessage**.</span></span> <span data-ttu-id="f60b1-129">MAPI 后台处理程序稍后将再次尝试 **SubmitMessage** 调用。</span><span class="sxs-lookup"><span data-stu-id="f60b1-129">The MAPI spooler will try the **SubmitMessage** call again later.</span></span> 
    
<span data-ttu-id="f60b1-130">MAPI_E_CANCEL</span><span class="sxs-lookup"><span data-stu-id="f60b1-130">MAPI_E_CANCEL</span></span> 
  
> <span data-ttu-id="f60b1-131">尽管传输提供程序请求 MAPI 后台处理程序在之前的 **SpoolerNotify** 调用上重新提交邮件，但之后条件已更改，不应重新发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="f60b1-131">Although the transport provider requested that the MAPI spooler resubmit the message on a previous **SpoolerNotify** call, conditions have since changed, and the message should not be resent.</span></span> <span data-ttu-id="f60b1-132">MAPI 后台处理程序将继续处理其他操作。</span><span class="sxs-lookup"><span data-stu-id="f60b1-132">The MAPI spooler will go on to handle something else.</span></span> 
    
<span data-ttu-id="f60b1-133">MAPI_E_NETWORK_ERROR</span><span class="sxs-lookup"><span data-stu-id="f60b1-133">MAPI_E_NETWORK_ERROR</span></span> 
  
> <span data-ttu-id="f60b1-134">网络错误阻止成功完成操作。</span><span class="sxs-lookup"><span data-stu-id="f60b1-134">A network error prevented successful completion of the operation.</span></span> <span data-ttu-id="f60b1-135">_lpulReturnParm_ 参数应设置为 MAPI 后台处理程序重新提交邮件之前经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="f60b1-135">The  _lpulReturnParm_ parameter should be set to the number of seconds that will elapse before the MAPI spooler resubmits the message.</span></span> 
    
<span data-ttu-id="f60b1-136">MAPI_E_NOT_ME</span><span class="sxs-lookup"><span data-stu-id="f60b1-136">MAPI_E_NOT_ME</span></span> 
  
> <span data-ttu-id="f60b1-137">传输提供程序无法处理此邮件。</span><span class="sxs-lookup"><span data-stu-id="f60b1-137">The transport provider cannot handle this message.</span></span> <span data-ttu-id="f60b1-138">MAPI 后台处理程序应尝试查找它的另一个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="f60b1-138">The MAPI spooler should try to find another transport provider for it.</span></span> <span data-ttu-id="f60b1-139">提供程序应该使用此返回值来指示未进行处理，并且 MAPI 后台处理程序不应调用 **EndMessage**。</span><span class="sxs-lookup"><span data-stu-id="f60b1-139">A provider should use this return value to indicate that no processing occurred and that the MAPI spooler should not call **EndMessage**.</span></span>
    
<span data-ttu-id="f60b1-140">MAPI_E_WAIT</span><span class="sxs-lookup"><span data-stu-id="f60b1-140">MAPI_E_WAIT</span></span> 
  
> <span data-ttu-id="f60b1-141">临时问题阻止传输提供程序处理邮件。</span><span class="sxs-lookup"><span data-stu-id="f60b1-141">A temporary problem prevents the transport provider from handling the message.</span></span> <span data-ttu-id="f60b1-142">_lpulReturnParm_ 参数应设置为 MAPI 后台处理程序重新提交邮件之前经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="f60b1-142">The  _lpulReturnParm_ parameter should be set to the number of seconds that will elapse before the MAPI spooler resubmits the message.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f60b1-143">备注</span><span class="sxs-lookup"><span data-stu-id="f60b1-143">Remarks</span></span>

<span data-ttu-id="f60b1-144">当 MAPI 后台处理程序有消息供传输提供程序传递时，它将调用 **IXPLogon：：SubmitMessage** 方法。</span><span class="sxs-lookup"><span data-stu-id="f60b1-144">The MAPI spooler calls the **IXPLogon::SubmitMessage** method when it has a message for the transport provider to deliver.</span></span> <span data-ttu-id="f60b1-145">邮件使用  _lpMessage_ 参数传递给传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="f60b1-145">The message is passed to the transport provider by using the  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="f60b1-146">如果提供程序已准备好接受邮件，它应通过使用  _lpulMsgRef_ 参数返回一个引用值，处理传递的对象，并返回 (值S_OK) 。</span><span class="sxs-lookup"><span data-stu-id="f60b1-146">If the provider is ready to accept the message, it should return a reference value by using the  _lpulMsgRef_ parameter, process the passed object, and return the appropriate value (usually S_OK).</span></span> <span data-ttu-id="f60b1-147">如果提供程序未准备好处理传输，它应返回一个错误值，并且（可选）在  _lpulReturnParm_ 中返回另一个 MAPI 返回值，以指示 MAPI 后台处理程序在重新提交邮件之前应等待多久。</span><span class="sxs-lookup"><span data-stu-id="f60b1-147">If the provider is not prepared to handle the transfer, it should return an error value and, optionally, another MAPI return value in  _lpulReturnParm_ to indicate how long the MAPI spooler should wait before resubmitting the message.</span></span> 
  
<span data-ttu-id="f60b1-148">传输提供程序的此方法实现可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f60b1-148">A transport provider's implementation of this method can do the following:</span></span>
  
- <span data-ttu-id="f60b1-149">将邮件放入内部队列以等待传输，可能会将邮件复制到本地存储并返回。</span><span class="sxs-lookup"><span data-stu-id="f60b1-149">Put the message into an internal queue to wait for transmission, possibly copying the message to local storage, and return.</span></span>
    
- <span data-ttu-id="f60b1-150">尝试执行实际传输，在传输完成时返回成功或不成功。</span><span class="sxs-lookup"><span data-stu-id="f60b1-150">Attempt to perform the actual transmission and return when the transmission completes, either successfully or unsuccessfully.</span></span>
    
- <span data-ttu-id="f60b1-151">确定在检查涉及的资源后是否发送邮件。</span><span class="sxs-lookup"><span data-stu-id="f60b1-151">Determine whether to send the message after checking the resource involved.</span></span> <span data-ttu-id="f60b1-152">在这种情况下，如果资源是免费的，则提供程序可以锁定资源、准备消息并提交它。</span><span class="sxs-lookup"><span data-stu-id="f60b1-152">In this case, if the resource is free, the provider can lock the resource, prepare the message, and submit it.</span></span> <span data-ttu-id="f60b1-153">如果资源繁忙，提供程序可以准备消息并延迟到以后发送。</span><span class="sxs-lookup"><span data-stu-id="f60b1-153">If the resource is busy, the provider can prepare the message and defer sending to a later time.</span></span>
    
<span data-ttu-id="f60b1-154">邮件传输的首选技术取决于传输提供程序和与系统资源竞争的预期进程数。</span><span class="sxs-lookup"><span data-stu-id="f60b1-154">The preferred technique for message transmission depends on the transport provider and the expected number of processes competing for system resources.</span></span> 
  
<span data-ttu-id="f60b1-155">在 **SubmitMessage** 调用期间，传输提供程序控制从邮件对象传输邮件数据。</span><span class="sxs-lookup"><span data-stu-id="f60b1-155">During a **SubmitMessage** call, the transport provider controls the transfer of message data from the message object.</span></span> <span data-ttu-id="f60b1-156">但是，传输提供程序应为邮件分配一个引用值，在传输数据之前，它会在  _lpulMsgRef_ 中向该邮件返回一个指针。</span><span class="sxs-lookup"><span data-stu-id="f60b1-156">However, the transport provider should assign a reference value to the message, to which it returns a pointer in  _lpulMsgRef_, before transferring data.</span></span> <span data-ttu-id="f60b1-157">它这样做是因为，在过程中的任何时间点，MAPI 后台处理程序都可以调用 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 方法，同时将 NOTIFY_CANCEL_MESSAGE 标志设置为向提供程序发出信号，指示它应释放任何打开的对象并停止消息传输。</span><span class="sxs-lookup"><span data-stu-id="f60b1-157">It does so because at any point during the process, the MAPI spooler can call the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method with the NOTIFY_CANCEL_MESSAGE flag set to signal the provider that it should release any open objects and stop message transfer.</span></span> 
  
<span data-ttu-id="f60b1-158">传输提供程序不应发送邮件的任何不可传递的属性。</span><span class="sxs-lookup"><span data-stu-id="f60b1-158">The transport provider should not send any nontransmittable properties of the message.</span></span> <span data-ttu-id="f60b1-159">当找到此类属性时，它应继续处理下一个属性。</span><span class="sxs-lookup"><span data-stu-id="f60b1-159">When it finds such a property, it should go on to process the next property.</span></span> <span data-ttu-id="f60b1-160">提供商应尽一切努力不将MAPI_P1信息作为传输的邮件内容的一部分显示;提供程序应仅出于寻址目的使用此收件人信息。</span><span class="sxs-lookup"><span data-stu-id="f60b1-160">The provider should make every effort not to display MAPI_P1 recipient information as part of the transmitted message content; the provider should use this recipient information only for addressing purposes.</span></span> <span data-ttu-id="f60b1-161">MAPI_P1收件人是内部生成的用于重新发送邮件的收件人;它们不应进行传输。</span><span class="sxs-lookup"><span data-stu-id="f60b1-161">MAPI_P1 recipients are internally generated recipients that are used for resending messages; they should not be transmitted.</span></span> <span data-ttu-id="f60b1-162">请改为使用其他收件人传输收件人信息。</span><span class="sxs-lookup"><span data-stu-id="f60b1-162">Instead, use the other recipients for transmitting recipient information.</span></span> <span data-ttu-id="f60b1-163">这种安排的目的是允许重新发送收件人查看与原始收件人完全相同的收件人表。</span><span class="sxs-lookup"><span data-stu-id="f60b1-163">The purpose of this arrangement is to permit resend recipients to see the exact same recipient table as the original recipients.</span></span>
  
<span data-ttu-id="f60b1-164">在 **SubmitMessage** 调用期间，MAPI 后台处理程序处理在邮件传输过程中打开的对象的方法，并处理任何附件。</span><span class="sxs-lookup"><span data-stu-id="f60b1-164">During a **SubmitMessage** call, the MAPI spooler processes methods for objects that are opened during the transfer of the message, and it processes any attachments.</span></span> <span data-ttu-id="f60b1-165">此处理可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="f60b1-165">This processing can take a long time.</span></span> <span data-ttu-id="f60b1-166">传输提供程序可以在此处理过程中频繁调用 MAPI 后台处理程序的 [IMAPISupport：：SpoolerYield](imapisupport-spooleryield.md) 方法，以释放其他系统任务的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="f60b1-166">Transport providers can call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) method for the MAPI spooler frequently during this processing to release CPU time for other system tasks.</span></span> 
  
<span data-ttu-id="f60b1-167">所有邮件收件人都显示在 MAPI 后台处理程序最初传递的邮件的收件人表中。</span><span class="sxs-lookup"><span data-stu-id="f60b1-167">All message recipients are visible in the recipient table of the message that the MAPI spooler originally passed.</span></span> <span data-ttu-id="f60b1-168">传输提供程序应仅处理可处理的收件人（基于条目标识符、地址类型或两者）以及尚未将 **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE 的收件人。</span><span class="sxs-lookup"><span data-stu-id="f60b1-168">The transport provider should process only those recipients that it can handle — based on entry identifier, address type, or both — and that do not already have their **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property set to TRUE.</span></span> <span data-ttu-id="f60b1-169">如果 **PR_RESPONSIBILITY** 设置为 TRUE，则另一个传输提供程序已处理该收件人。</span><span class="sxs-lookup"><span data-stu-id="f60b1-169">If **PR_RESPONSIBILITY** is already set to TRUE, another transport provider has handled that recipient.</span></span> <span data-ttu-id="f60b1-170">当提供程序完成收件人的充分处理以确定其是否可以处理该收件人的邮件时，它应在传递的邮件中将收件人的 **PR_RESPONSIBILITY** 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="f60b1-170">When the provider completes sufficient processing of a recipient to determine whether it can handle messages for that recipient, it should set that recipient's **PR_RESPONSIBILITY** property to TRUE in the passed message.</span></span> <span data-ttu-id="f60b1-171">通常，提供程序在邮件传递完成后做出此决定。</span><span class="sxs-lookup"><span data-stu-id="f60b1-171">Usually, the provider makes this determination after message delivery is complete.</span></span> 
  
<span data-ttu-id="f60b1-172">通常，在传输提供程序完成邮件数据的传输之前，不会从 **SubmitMessage** 调用返回。</span><span class="sxs-lookup"><span data-stu-id="f60b1-172">Typically, the transport provider does not return from a **SubmitMessage** call until it completes the transfer of message data.</span></span> <span data-ttu-id="f60b1-173">如果未返回错误，则从 MAPI 后台处理程序到提供程序的下一个调用是调用 [IXPLogon：：EndMessage](ixplogon-endmessage.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="f60b1-173">If no error is returned, the next call from the MAPI spooler to the provider is a call to the [IXPLogon::EndMessage](ixplogon-endmessage.md) method.</span></span> 
  
<span data-ttu-id="f60b1-174">如果 **SubmitMessage** 返回错误，MAPI 后台处理程序将在不保存更改的情况下释放正在处理的消息。</span><span class="sxs-lookup"><span data-stu-id="f60b1-174">If **SubmitMessage** returns an error, the MAPI spooler releases the message in process without saving changes.</span></span> <span data-ttu-id="f60b1-175">如果传输提供程序要求保存邮件更改，则必须在返回之前对邮件调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="f60b1-175">If the transport provider requires message changes to be saved, it must call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the message before returning.</span></span> 
  
<span data-ttu-id="f60b1-176">如果由于传输问题而发生错误，MAPI 后台处理程序会保留邮件，但会延迟根据  _lpulReturnParm_ 中返回的值将邮件重新提交到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="f60b1-176">In case of errors that occur because of transport problems, the MAPI spooler retains the message, but it delays resubmitting the message to the transport provider based on the value returned in  _lpulReturnParm_.</span></span> <span data-ttu-id="f60b1-177">如果 **SubmitMessage** 返回的值是 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR。</span><span class="sxs-lookup"><span data-stu-id="f60b1-177">The transport provider must fill in that value if its return value from **SubmitMessage** is MAPI_E_WAIT or MAPI_E_NETWORK_ERROR.</span></span> <span data-ttu-id="f60b1-178">如果发生严重错误情况，传输提供程序必须调用具有"错误"标志的 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) NOTIFY_CRITICAL_ERROR方法。</span><span class="sxs-lookup"><span data-stu-id="f60b1-178">If a severe error condition occurs, the transport provider must call the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method with the NOTIFY_CRITICAL_ERROR flag.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f60b1-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f60b1-179">See also</span></span>



[<span data-ttu-id="f60b1-180">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="f60b1-180">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="f60b1-181">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="f60b1-181">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="f60b1-182">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="f60b1-182">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md)
  
[<span data-ttu-id="f60b1-183">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="f60b1-183">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md)
  
[<span data-ttu-id="f60b1-184">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="f60b1-184">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md)
  
[<span data-ttu-id="f60b1-185">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f60b1-185">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

