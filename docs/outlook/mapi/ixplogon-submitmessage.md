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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8a0b10596bdfdc1ea33f6d170ee1e021193d3788
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776138"
---
# <a name="ixplogonsubmitmessage"></a><span data-ttu-id="9347e-103">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="9347e-103">IXPLogon::SubmitMessage</span></span>

  
  
<span data-ttu-id="9347e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9347e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9347e-105">指示 MAPI 后台处理程序都有要提供的传输提供程序的消息。</span><span class="sxs-lookup"><span data-stu-id="9347e-105">Indicates that the MAPI spooler has a message for the transport provider to deliver.</span></span>
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef,
  ULONG FAR * lpulReturnParm
);
```

## <a name="parameters"></a><span data-ttu-id="9347e-106">参数</span><span class="sxs-lookup"><span data-stu-id="9347e-106">Parameters</span></span>

 <span data-ttu-id="9347e-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9347e-107">_ulFlags_</span></span>
  
> <span data-ttu-id="9347e-108">[in]位掩码的标志，控制如何提交邮件。</span><span class="sxs-lookup"><span data-stu-id="9347e-108">[in] A bitmask of flags that controls how the message is submitted.</span></span> <span data-ttu-id="9347e-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="9347e-109">The following flag can be set:</span></span>
    
<span data-ttu-id="9347e-110">BEGIN_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="9347e-110">BEGIN_DEFERRED</span></span> 
  
> <span data-ttu-id="9347e-111">MAPI 后台处理程序调用以前推迟一条消息的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="9347e-111">The MAPI spooler is calling a transport provider with a message that was previously deferred.</span></span> <span data-ttu-id="9347e-112">邮件的项标识符时相同它已被延迟。</span><span class="sxs-lookup"><span data-stu-id="9347e-112">The entry identifier of the message is the same as when it was deferred.</span></span> <span data-ttu-id="9347e-113">邮件已被延迟通过将其条目标识符传递回 MAPI 后台处理程序[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法使用 NOTIFY_SENTDEFERRED 标志。</span><span class="sxs-lookup"><span data-stu-id="9347e-113">The message was deferred by passing its entry identifier back to the MAPI spooler by using the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method with the NOTIFY_SENTDEFERRED flag.</span></span> 
    
 <span data-ttu-id="9347e-114">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="9347e-114">_lpMessage_</span></span>
  
> <span data-ttu-id="9347e-115">[in]一个指向 message 对象 （表示要发送的消息） 具有读/写权限，传输提供程序使用来访问和处理该邮件。</span><span class="sxs-lookup"><span data-stu-id="9347e-115">[in] A pointer to a message object (representing the message to deliver) that has read/write permission, which the transport provider uses to access and manipulate that message.</span></span> <span data-ttu-id="9347e-116">传输提供程序返回从后续调用[IXPLogon::EndMessage](ixplogon-endmessage.md)方法后，该对象保持有效之前。</span><span class="sxs-lookup"><span data-stu-id="9347e-116">This object remains valid until after the transport provider returns from a subsequent call to the [IXPLogon::EndMessage](ixplogon-endmessage.md) method.</span></span> 
    
 <span data-ttu-id="9347e-117">_lpulMsgRef_</span><span class="sxs-lookup"><span data-stu-id="9347e-117">_lpulMsgRef_</span></span>
  
> <span data-ttu-id="9347e-118">[输出]指向中传输提供程序返回其分配给此消息的参考值变量的指针。</span><span class="sxs-lookup"><span data-stu-id="9347e-118">[out] A pointer to a variable in which the transport provider returns the reference value it assigned to this message.</span></span> <span data-ttu-id="9347e-119">MAPI 后台处理程序中后续呼叫，此消息传递参考该值。</span><span class="sxs-lookup"><span data-stu-id="9347e-119">The MAPI spooler passes this reference value in subsequent calls for this message.</span></span> <span data-ttu-id="9347e-120">MAPI 后台处理程序返回到传输提供程序之前初始化为 0 的值。</span><span class="sxs-lookup"><span data-stu-id="9347e-120">The MAPI spooler initializes the value to 0 before returning it to the transport provider.</span></span>
    
 <span data-ttu-id="9347e-121">_lpulReturnParm_</span><span class="sxs-lookup"><span data-stu-id="9347e-121">_lpulReturnParm_</span></span>
  
> <span data-ttu-id="9347e-122">[输出]指向由**SubmitMessage**返回的 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR 错误值对应一个变量的指针。</span><span class="sxs-lookup"><span data-stu-id="9347e-122">[out] A pointer to a variable that corresponds to the MAPI_E_WAIT or MAPI_E_NETWORK_ERROR error value returned by **SubmitMessage**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9347e-123">返回值</span><span class="sxs-lookup"><span data-stu-id="9347e-123">Return value</span></span>

<span data-ttu-id="9347e-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="9347e-124">S_OK</span></span> 
  
> <span data-ttu-id="9347e-125">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="9347e-125">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="9347e-126">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="9347e-126">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="9347e-127">传输提供程序无法处理邮件，因为它执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="9347e-127">The transport provider cannot handle the message, because it is performing another operation.</span></span> <span data-ttu-id="9347e-128">提供程序应使用此返回的值，以指示不会处理出现和 MAPI 后台处理程序不应调用**EndMessage**。</span><span class="sxs-lookup"><span data-stu-id="9347e-128">A provider should use this return value to indicate that no processing occurred and that the MAPI spooler should not call **EndMessage**.</span></span> <span data-ttu-id="9347e-129">MAPI 后台处理程序将稍后再试**SubmitMessage**呼叫。</span><span class="sxs-lookup"><span data-stu-id="9347e-129">The MAPI spooler will try the **SubmitMessage** call again later.</span></span> 
    
<span data-ttu-id="9347e-130">MAPI_E_CANCEL</span><span class="sxs-lookup"><span data-stu-id="9347e-130">MAPI_E_CANCEL</span></span> 
  
> <span data-ttu-id="9347e-131">尽管传输提供程序请求 MAPI 后台处理程序重新提交邮件在以前**SpoolerNotify**呼叫，此后更改条件，并且应不重新发送邮件。</span><span class="sxs-lookup"><span data-stu-id="9347e-131">Although the transport provider requested that the MAPI spooler resubmit the message on a previous **SpoolerNotify** call, conditions have since changed, and the message should not be resent.</span></span> <span data-ttu-id="9347e-132">MAPI 后台处理程序将继续处理其他内容。</span><span class="sxs-lookup"><span data-stu-id="9347e-132">The MAPI spooler will go on to handle something else.</span></span> 
    
<span data-ttu-id="9347e-133">MAPI_E_NETWORK_ERROR</span><span class="sxs-lookup"><span data-stu-id="9347e-133">MAPI_E_NETWORK_ERROR</span></span> 
  
> <span data-ttu-id="9347e-134">网络错误阻止操作成功的完成。</span><span class="sxs-lookup"><span data-stu-id="9347e-134">A network error prevented successful completion of the operation.</span></span> <span data-ttu-id="9347e-135">_LpulReturnParm_参数应设置为的 MAPI 后台处理程序重新提交邮件之前所经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="9347e-135">The  _lpulReturnParm_ parameter should be set to the number of seconds that will elapse before the MAPI spooler resubmits the message.</span></span> 
    
<span data-ttu-id="9347e-136">MAPI_E_NOT_ME</span><span class="sxs-lookup"><span data-stu-id="9347e-136">MAPI_E_NOT_ME</span></span> 
  
> <span data-ttu-id="9347e-137">传输提供程序无法处理此消息。</span><span class="sxs-lookup"><span data-stu-id="9347e-137">The transport provider cannot handle this message.</span></span> <span data-ttu-id="9347e-138">MAPI 后台处理程序应尝试查找另一个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="9347e-138">The MAPI spooler should try to find another transport provider for it.</span></span> <span data-ttu-id="9347e-139">提供程序应使用此返回的值，以指示不会处理出现和 MAPI 后台处理程序不应调用**EndMessage**。</span><span class="sxs-lookup"><span data-stu-id="9347e-139">A provider should use this return value to indicate that no processing occurred and that the MAPI spooler should not call **EndMessage**.</span></span>
    
<span data-ttu-id="9347e-140">MAPI_E_WAIT</span><span class="sxs-lookup"><span data-stu-id="9347e-140">MAPI_E_WAIT</span></span> 
  
> <span data-ttu-id="9347e-141">暂时出现问题阻止传输提供程序处理邮件。</span><span class="sxs-lookup"><span data-stu-id="9347e-141">A temporary problem prevents the transport provider from handling the message.</span></span> <span data-ttu-id="9347e-142">_LpulReturnParm_参数应设置为的 MAPI 后台处理程序重新提交邮件之前所经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="9347e-142">The  _lpulReturnParm_ parameter should be set to the number of seconds that will elapse before the MAPI spooler resubmits the message.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="9347e-143">备注</span><span class="sxs-lookup"><span data-stu-id="9347e-143">Remarks</span></span>

<span data-ttu-id="9347e-144">MAPI 后台处理程序调用**IXPLogon::SubmitMessage**方法时要提供的传输提供程序的消息。</span><span class="sxs-lookup"><span data-stu-id="9347e-144">The MAPI spooler calls the **IXPLogon::SubmitMessage** method when it has a message for the transport provider to deliver.</span></span> <span data-ttu-id="9347e-145">通过使用_lpMessage_参数情况下，邮件传递到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="9347e-145">The message is passed to the transport provider by using the  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="9347e-146">如果已准备好接受消息提供程序，它应通过_lpulMsgRef_参数，过程传递的对象，返回的引用值并返回相应的值 (通常 S_OK)。</span><span class="sxs-lookup"><span data-stu-id="9347e-146">If the provider is ready to accept the message, it should return a reference value by using the  _lpulMsgRef_ parameter, process the passed object, and return the appropriate value (usually S_OK).</span></span> <span data-ttu-id="9347e-147">如果不准备处理传输提供程序，它应返回错误值，并 （可选），另一个 MAPI 返回中_lpulReturnParm_以指示 MAPI 后台处理程序重新提交邮件之前应等待的时间长度值。</span><span class="sxs-lookup"><span data-stu-id="9347e-147">If the provider is not prepared to handle the transfer, it should return an error value and, optionally, another MAPI return value in  _lpulReturnParm_ to indicate how long the MAPI spooler should wait before resubmitting the message.</span></span> 
  
<span data-ttu-id="9347e-148">传输提供程序实现此方法可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9347e-148">A transport provider's implementation of this method can do the following:</span></span>
  
- <span data-ttu-id="9347e-149">邮件置于内部队列等待传输，原因可能将邮件复制到本地存储，并返回。</span><span class="sxs-lookup"><span data-stu-id="9347e-149">Put the message into an internal queue to wait for transmission, possibly copying the message to local storage, and return.</span></span>
    
- <span data-ttu-id="9347e-150">尝试执行的实际传输和返回传输完成后，成功或失败。</span><span class="sxs-lookup"><span data-stu-id="9347e-150">Attempt to perform the actual transmission and return when the transmission completes, either successfully or unsuccessfully.</span></span>
    
- <span data-ttu-id="9347e-151">确定是否检查所涉及的资源后发送邮件。</span><span class="sxs-lookup"><span data-stu-id="9347e-151">Determine whether to send the message after checking the resource involved.</span></span> <span data-ttu-id="9347e-152">在这种情况下，如果资源是免费的提供程序可以锁定资源、 准备邮件，并将其提交。</span><span class="sxs-lookup"><span data-stu-id="9347e-152">In this case, if the resource is free, the provider can lock the resource, prepare the message, and submit it.</span></span> <span data-ttu-id="9347e-153">如果资源正忙，提供程序可以准备邮件并推迟到以后某个时间发送。</span><span class="sxs-lookup"><span data-stu-id="9347e-153">If the resource is busy, the provider can prepare the message and defer sending to a later time.</span></span>
    
<span data-ttu-id="9347e-154">邮件传输的首选的方法取决于传输提供程序和预期的数量的流程争夺系统资源。</span><span class="sxs-lookup"><span data-stu-id="9347e-154">The preferred technique for message transmission depends on the transport provider and the expected number of processes competing for system resources.</span></span> 
  
<span data-ttu-id="9347e-155">**SubmitMessage**呼叫期间，传输提供程序控制传输的消息数据从 message 对象。</span><span class="sxs-lookup"><span data-stu-id="9347e-155">During a **SubmitMessage** call, the transport provider controls the transfer of message data from the message object.</span></span> <span data-ttu-id="9347e-156">但是，传输提供程序应将引用值分配给邮件，向其返回一个指向在_lpulMsgRef_之前传输数据。</span><span class="sxs-lookup"><span data-stu-id="9347e-156">However, the transport provider should assign a reference value to the message, to which it returns a pointer in  _lpulMsgRef_, before transferring data.</span></span> <span data-ttu-id="9347e-157">它因此因为可以在任何点在过程中，调用 MAPI 后台处理程序将[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法与 NOTIFY_CANCEL_MESSAGE 标志设置为信号提供程序，它应释放任何打开的对象并停止邮件传输。</span><span class="sxs-lookup"><span data-stu-id="9347e-157">It does so because at any point during the process, the MAPI spooler can call the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method with the NOTIFY_CANCEL_MESSAGE flag set to signal the provider that it should release any open objects and stop message transfer.</span></span> 
  
<span data-ttu-id="9347e-158">传输提供程序不应发送消息的任何 nontransmittable 属性。</span><span class="sxs-lookup"><span data-stu-id="9347e-158">The transport provider should not send any nontransmittable properties of the message.</span></span> <span data-ttu-id="9347e-159">如果找到此类属性，它应继续处理的下一个属性。</span><span class="sxs-lookup"><span data-stu-id="9347e-159">When it finds such a property, it should go on to process the next property.</span></span> <span data-ttu-id="9347e-160">提供程序应尽力不传输的消息内容; 的一部分显示 MAPI_P1 收件人信息提供程序应仅对寻址目的使用此收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="9347e-160">The provider should make every effort not to display MAPI_P1 recipient information as part of the transmitted message content; the provider should use this recipient information only for addressing purposes.</span></span> <span data-ttu-id="9347e-161">MAPI_P1 收件人是内部生成的用于重新发送消息;他们应不会传输。</span><span class="sxs-lookup"><span data-stu-id="9347e-161">MAPI_P1 recipients are internally generated recipients that are used for resending messages; they should not be transmitted.</span></span> <span data-ttu-id="9347e-162">相反，使用其他收件人的传输收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="9347e-162">Instead, use the other recipients for transmitting recipient information.</span></span> <span data-ttu-id="9347e-163">这种排列的用途是允许重新发送收件人为原始收件人看到完全相同的收件人表。</span><span class="sxs-lookup"><span data-stu-id="9347e-163">The purpose of this arrangement is to permit resend recipients to see the exact same recipient table as the original recipients.</span></span>
  
<span data-ttu-id="9347e-164">**SubmitMessage**调用，过程中 MAPI 后台处理程序处理的邮件传输过程中打开的对象的方法以及处理任何附件。</span><span class="sxs-lookup"><span data-stu-id="9347e-164">During a **SubmitMessage** call, the MAPI spooler processes methods for objects that are opened during the transfer of the message, and it processes any attachments.</span></span> <span data-ttu-id="9347e-165">此处理花费很长时间。</span><span class="sxs-lookup"><span data-stu-id="9347e-165">This processing can take a long time.</span></span> <span data-ttu-id="9347e-166">传输提供程序可以发布的其他系统任务的 CPU 时间此处理过程中经常调用了的 MAPI 后台处理程序的[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9347e-166">Transport providers can call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) method for the MAPI spooler frequently during this processing to release CPU time for other system tasks.</span></span> 
  
<span data-ttu-id="9347e-167">所有收件人都都能看到收件人的 MAPI 后台处理程序最初传递的消息表中。</span><span class="sxs-lookup"><span data-stu-id="9347e-167">All message recipients are visible in the recipient table of the message that the MAPI spooler originally passed.</span></span> <span data-ttu-id="9347e-168">传输提供程序应处理只有它可以处理这些收件人 — 基于条目标识符、 地址类型，或同时 — 和尚未其**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9347e-168">The transport provider should process only those recipients that it can handle — based on entry identifier, address type, or both — and that do not already have their **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property set to TRUE.</span></span> <span data-ttu-id="9347e-169">如果**PR_RESPONSIBILITY**已设置为 TRUE，另一个传输提供程序已经处理该收件人。</span><span class="sxs-lookup"><span data-stu-id="9347e-169">If **PR_RESPONSIBILITY** is already set to TRUE, another transport provider has handled that recipient.</span></span> <span data-ttu-id="9347e-170">提供程序完成后足够处理的以确定是否可以为该收件人处理邮件的收件人，它应将该收件人**PR_RESPONSIBILITY**属性设置为 TRUE 传递的消息。</span><span class="sxs-lookup"><span data-stu-id="9347e-170">When the provider completes sufficient processing of a recipient to determine whether it can handle messages for that recipient, it should set that recipient's **PR_RESPONSIBILITY** property to TRUE in the passed message.</span></span> <span data-ttu-id="9347e-171">通常，提供程序进行此项确定邮件传递完成之后。</span><span class="sxs-lookup"><span data-stu-id="9347e-171">Usually, the provider makes this determination after message delivery is complete.</span></span> 
  
<span data-ttu-id="9347e-172">通常，传输提供程序不返回**SubmitMessage**调用直到它完成传输邮件数据。</span><span class="sxs-lookup"><span data-stu-id="9347e-172">Typically, the transport provider does not return from a **SubmitMessage** call until it completes the transfer of message data.</span></span> <span data-ttu-id="9347e-173">如果不返回任何错误，来自 MAPI 后台处理程序向提供程序的下一个呼叫是对[IXPLogon::EndMessage](ixplogon-endmessage.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="9347e-173">If no error is returned, the next call from the MAPI spooler to the provider is a call to the [IXPLogon::EndMessage](ixplogon-endmessage.md) method.</span></span> 
  
<span data-ttu-id="9347e-174">如果**SubmitMessage**将返回错误，MAPI 后台处理程序将释放而不保存更改的过程中的消息。</span><span class="sxs-lookup"><span data-stu-id="9347e-174">If **SubmitMessage** returns an error, the MAPI spooler releases the message in process without saving changes.</span></span> <span data-ttu-id="9347e-175">如果传输提供程序所需的消息将更改保存，它必须返回之前对邮件调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9347e-175">If the transport provider requires message changes to be saved, it must call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the message before returning.</span></span> 
  
<span data-ttu-id="9347e-176">由于传输问题出现的错误，显示 MAPI 后台处理程序保持在原有的邮件，但不是延迟重新提交的邮件传输提供程序基于_lpulReturnParm_中返回的值。</span><span class="sxs-lookup"><span data-stu-id="9347e-176">In case of errors that occur because of transport problems, the MAPI spooler retains the message, but it delays resubmitting the message to the transport provider based on the value returned in  _lpulReturnParm_.</span></span> <span data-ttu-id="9347e-177">如果从**SubmitMessage**其返回值是 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR，传输提供程序必须填写该值。</span><span class="sxs-lookup"><span data-stu-id="9347e-177">The transport provider must fill in that value if its return value from **SubmitMessage** is MAPI_E_WAIT or MAPI_E_NETWORK_ERROR.</span></span> <span data-ttu-id="9347e-178">如果出现严重错误情况，传输提供程序必须调用带 NOTIFY_CRITICAL_ERROR 标志的[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9347e-178">If a severe error condition occurs, the transport provider must call the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method with the NOTIFY_CRITICAL_ERROR flag.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9347e-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9347e-179">See also</span></span>



[<span data-ttu-id="9347e-180">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="9347e-180">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="9347e-181">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="9347e-181">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="9347e-182">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="9347e-182">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md)
  
[<span data-ttu-id="9347e-183">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="9347e-183">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md)
  
[<span data-ttu-id="9347e-184">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="9347e-184">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md)
  
[<span data-ttu-id="9347e-185">IXPLogon: IUnknown</span><span class="sxs-lookup"><span data-stu-id="9347e-185">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

