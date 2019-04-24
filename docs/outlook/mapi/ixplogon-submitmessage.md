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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351588"
---
# <a name="ixplogonsubmitmessage"></a><span data-ttu-id="2b770-103">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="2b770-103">IXPLogon::SubmitMessage</span></span>

  
  
<span data-ttu-id="2b770-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2b770-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2b770-105">指示 MAPI 后台处理程序有要传递的传输提供程序的消息。</span><span class="sxs-lookup"><span data-stu-id="2b770-105">Indicates that the MAPI spooler has a message for the transport provider to deliver.</span></span>
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef,
  ULONG FAR * lpulReturnParm
);
```

## <a name="parameters"></a><span data-ttu-id="2b770-106">参数</span><span class="sxs-lookup"><span data-stu-id="2b770-106">Parameters</span></span>

 <span data-ttu-id="2b770-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2b770-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2b770-108">实时用于控制如何提交邮件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2b770-108">[in] A bitmask of flags that controls how the message is submitted.</span></span> <span data-ttu-id="2b770-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2b770-109">The following flag can be set:</span></span>
    
<span data-ttu-id="2b770-110">BEGIN_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="2b770-110">BEGIN_DEFERRED</span></span> 
  
> <span data-ttu-id="2b770-111">MAPI 后台处理程序正在使用以前延迟的邮件调用传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2b770-111">The MAPI spooler is calling a transport provider with a message that was previously deferred.</span></span> <span data-ttu-id="2b770-112">邮件的条目标识符与延迟时相同。</span><span class="sxs-lookup"><span data-stu-id="2b770-112">The entry identifier of the message is the same as when it was deferred.</span></span> <span data-ttu-id="2b770-113">通过使用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法和 NOTIFY_SENTDEFERRED 标志将其条目标识符传递回 MAPI 后台处理程序, 从而推迟了邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-113">The message was deferred by passing its entry identifier back to the MAPI spooler by using the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method with the NOTIFY_SENTDEFERRED flag.</span></span> 
    
 <span data-ttu-id="2b770-114">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="2b770-114">_lpMessage_</span></span>
  
> <span data-ttu-id="2b770-115">实时一个指针, 指向具有读/写权限的邮件对象 (表示要传递的邮件), 传输提供程序使用该对象来访问和操作该邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-115">[in] A pointer to a message object (representing the message to deliver) that has read/write permission, which the transport provider uses to access and manipulate that message.</span></span> <span data-ttu-id="2b770-116">此对象将一直保持有效, 直到传输提供程序从对[IXPLogon:: EndMessage](ixplogon-endmessage.md)方法的后续调用返回。</span><span class="sxs-lookup"><span data-stu-id="2b770-116">This object remains valid until after the transport provider returns from a subsequent call to the [IXPLogon::EndMessage](ixplogon-endmessage.md) method.</span></span> 
    
 <span data-ttu-id="2b770-117">_lpulMsgRef_</span><span class="sxs-lookup"><span data-stu-id="2b770-117">_lpulMsgRef_</span></span>
  
> <span data-ttu-id="2b770-118">排除一个指针, 指向传输提供程序在其中返回其分配给此邮件的引用值的变量。</span><span class="sxs-lookup"><span data-stu-id="2b770-118">[out] A pointer to a variable in which the transport provider returns the reference value it assigned to this message.</span></span> <span data-ttu-id="2b770-119">MAPI 后台处理程序在此邮件的后续调用中传递此引用值。</span><span class="sxs-lookup"><span data-stu-id="2b770-119">The MAPI spooler passes this reference value in subsequent calls for this message.</span></span> <span data-ttu-id="2b770-120">MAPI 后台处理程序将此值初始化为 0, 然后再将其返回到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2b770-120">The MAPI spooler initializes the value to 0 before returning it to the transport provider.</span></span>
    
 <span data-ttu-id="2b770-121">_lpulReturnParm_</span><span class="sxs-lookup"><span data-stu-id="2b770-121">_lpulReturnParm_</span></span>
  
> <span data-ttu-id="2b770-122">排除指向与**SubmitMessage**返回的 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR 错误值相对应的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="2b770-122">[out] A pointer to a variable that corresponds to the MAPI_E_WAIT or MAPI_E_NETWORK_ERROR error value returned by **SubmitMessage**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2b770-123">返回值</span><span class="sxs-lookup"><span data-stu-id="2b770-123">Return value</span></span>

<span data-ttu-id="2b770-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b770-124">S_OK</span></span> 
  
> <span data-ttu-id="2b770-125">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="2b770-125">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="2b770-126">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="2b770-126">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="2b770-127">传输提供程序无法处理邮件, 因为它正在执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="2b770-127">The transport provider cannot handle the message, because it is performing another operation.</span></span> <span data-ttu-id="2b770-128">提供程序应使用此返回值指示未发生任何处理, MAPI 后台处理程序不应调用**EndMessage**。</span><span class="sxs-lookup"><span data-stu-id="2b770-128">A provider should use this return value to indicate that no processing occurred and that the MAPI spooler should not call **EndMessage**.</span></span> <span data-ttu-id="2b770-129">MAPI 后台处理程序将稍后再次尝试**SubmitMessage**调用。</span><span class="sxs-lookup"><span data-stu-id="2b770-129">The MAPI spooler will try the **SubmitMessage** call again later.</span></span> 
    
<span data-ttu-id="2b770-130">MAPI_E_CANCEL</span><span class="sxs-lookup"><span data-stu-id="2b770-130">MAPI_E_CANCEL</span></span> 
  
> <span data-ttu-id="2b770-131">尽管传输提供程序请求 MAPI 后台处理程序重新提交以前的**SpoolerNotify**调用的邮件, 但条件已更改, 不应重发邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-131">Although the transport provider requested that the MAPI spooler resubmit the message on a previous **SpoolerNotify** call, conditions have since changed, and the message should not be resent.</span></span> <span data-ttu-id="2b770-132">MAPI 后台处理程序将继续处理其他内容。</span><span class="sxs-lookup"><span data-stu-id="2b770-132">The MAPI spooler will go on to handle something else.</span></span> 
    
<span data-ttu-id="2b770-133">MAPI_E_NETWORK_ERROR</span><span class="sxs-lookup"><span data-stu-id="2b770-133">MAPI_E_NETWORK_ERROR</span></span> 
  
> <span data-ttu-id="2b770-134">网络错误阻止操作成功完成。</span><span class="sxs-lookup"><span data-stu-id="2b770-134">A network error prevented successful completion of the operation.</span></span> <span data-ttu-id="2b770-135">应将_lpulReturnParm_参数设置为 MAPI 后台处理程序重新提交邮件之前所经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="2b770-135">The  _lpulReturnParm_ parameter should be set to the number of seconds that will elapse before the MAPI spooler resubmits the message.</span></span> 
    
<span data-ttu-id="2b770-136">MAPI_E_NOT_ME</span><span class="sxs-lookup"><span data-stu-id="2b770-136">MAPI_E_NOT_ME</span></span> 
  
> <span data-ttu-id="2b770-137">传输提供程序无法处理此邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-137">The transport provider cannot handle this message.</span></span> <span data-ttu-id="2b770-138">MAPI 后台处理程序应尝试为其查找其他传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2b770-138">The MAPI spooler should try to find another transport provider for it.</span></span> <span data-ttu-id="2b770-139">提供程序应使用此返回值指示未发生任何处理, MAPI 后台处理程序不应调用**EndMessage**。</span><span class="sxs-lookup"><span data-stu-id="2b770-139">A provider should use this return value to indicate that no processing occurred and that the MAPI spooler should not call **EndMessage**.</span></span>
    
<span data-ttu-id="2b770-140">MAPI_E_WAIT</span><span class="sxs-lookup"><span data-stu-id="2b770-140">MAPI_E_WAIT</span></span> 
  
> <span data-ttu-id="2b770-141">临时问题会阻止传输提供程序处理邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-141">A temporary problem prevents the transport provider from handling the message.</span></span> <span data-ttu-id="2b770-142">应将_lpulReturnParm_参数设置为 MAPI 后台处理程序重新提交邮件之前所经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="2b770-142">The  _lpulReturnParm_ parameter should be set to the number of seconds that will elapse before the MAPI spooler resubmits the message.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="2b770-143">注解</span><span class="sxs-lookup"><span data-stu-id="2b770-143">Remarks</span></span>

<span data-ttu-id="2b770-144">MAPI 后台处理程序调用**IXPLogon:: SubmitMessage**方法, 以使传输提供程序能够传递邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-144">The MAPI spooler calls the **IXPLogon::SubmitMessage** method when it has a message for the transport provider to deliver.</span></span> <span data-ttu-id="2b770-145">通过使用_lpMessage_参数将邮件传递给传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2b770-145">The message is passed to the transport provider by using the  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="2b770-146">如果提供程序准备好接受邮件, 则应使用_lpulMsgRef_参数返回一个引用值, 处理传递的对象, 然后返回适当的值 (通常为 S_OK)。</span><span class="sxs-lookup"><span data-stu-id="2b770-146">If the provider is ready to accept the message, it should return a reference value by using the  _lpulMsgRef_ parameter, process the passed object, and return the appropriate value (usually S_OK).</span></span> <span data-ttu-id="2b770-147">如果提供程序未准备好处理传输, 它应返回一个错误值, 也可以返回_lpulReturnParm_中的另一个 MAPI 返回值, 以指示 mapi 后台处理程序在重新提交邮件之前应等待的时间。</span><span class="sxs-lookup"><span data-stu-id="2b770-147">If the provider is not prepared to handle the transfer, it should return an error value and, optionally, another MAPI return value in  _lpulReturnParm_ to indicate how long the MAPI spooler should wait before resubmitting the message.</span></span> 
  
<span data-ttu-id="2b770-148">此方法的传输提供程序的实现可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2b770-148">A transport provider's implementation of this method can do the following:</span></span>
  
- <span data-ttu-id="2b770-149">将邮件放入内部队列以等待传输, 可能将邮件复制到本地存储, 并返回。</span><span class="sxs-lookup"><span data-stu-id="2b770-149">Put the message into an internal queue to wait for transmission, possibly copying the message to local storage, and return.</span></span>
    
- <span data-ttu-id="2b770-150">尝试在传输完成 (无论成功还是失败) 时执行实际传输并返回。</span><span class="sxs-lookup"><span data-stu-id="2b770-150">Attempt to perform the actual transmission and return when the transmission completes, either successfully or unsuccessfully.</span></span>
    
- <span data-ttu-id="2b770-151">确定在检查所涉及的资源后是否发送邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-151">Determine whether to send the message after checking the resource involved.</span></span> <span data-ttu-id="2b770-152">在这种情况下, 如果资源是免费的, 则提供程序可以锁定资源、准备邮件并提交邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-152">In this case, if the resource is free, the provider can lock the resource, prepare the message, and submit it.</span></span> <span data-ttu-id="2b770-153">如果资源处于忙碌状态, 则提供程序可以准备邮件并推迟发送到稍后的时间。</span><span class="sxs-lookup"><span data-stu-id="2b770-153">If the resource is busy, the provider can prepare the message and defer sending to a later time.</span></span>
    
<span data-ttu-id="2b770-154">邮件传输的首选技术取决于传输提供程序和争用系统资源的预期进程数。</span><span class="sxs-lookup"><span data-stu-id="2b770-154">The preferred technique for message transmission depends on the transport provider and the expected number of processes competing for system resources.</span></span> 
  
<span data-ttu-id="2b770-155">在**SubmitMessage**呼叫过程中, 传输提供程序控制邮件对象的邮件数据传输。</span><span class="sxs-lookup"><span data-stu-id="2b770-155">During a **SubmitMessage** call, the transport provider controls the transfer of message data from the message object.</span></span> <span data-ttu-id="2b770-156">但是, 传输提供程序应在_lpulMsgRef_中向其返回指针的消息分配一个引用值, 然后再传输数据。</span><span class="sxs-lookup"><span data-stu-id="2b770-156">However, the transport provider should assign a reference value to the message, to which it returns a pointer in  _lpulMsgRef_, before transferring data.</span></span> <span data-ttu-id="2b770-157">这是因为在过程中的任何时刻, MAPI 后台处理程序都可以调用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法并设置 NOTIFY_CANCEL_MESSAGE 标志, 以向提供程序发出通知, 告知其应释放任何打开的对象并停止邮件传输。</span><span class="sxs-lookup"><span data-stu-id="2b770-157">It does so because at any point during the process, the MAPI spooler can call the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method with the NOTIFY_CANCEL_MESSAGE flag set to signal the provider that it should release any open objects and stop message transfer.</span></span> 
  
<span data-ttu-id="2b770-158">传输提供程序不应发送邮件的任何 nontransmittable 属性。</span><span class="sxs-lookup"><span data-stu-id="2b770-158">The transport provider should not send any nontransmittable properties of the message.</span></span> <span data-ttu-id="2b770-159">当找到此类属性时, 它应继续处理下一个属性。</span><span class="sxs-lookup"><span data-stu-id="2b770-159">When it finds such a property, it should go on to process the next property.</span></span> <span data-ttu-id="2b770-160">提供程序应尽一切努力将 MAPI_P1 收件人信息显示为传输的邮件内容的一部分;提供程序应仅出于寻址目的而使用此收件人信息。</span><span class="sxs-lookup"><span data-stu-id="2b770-160">The provider should make every effort not to display MAPI_P1 recipient information as part of the transmitted message content; the provider should use this recipient information only for addressing purposes.</span></span> <span data-ttu-id="2b770-161">MAPI_P1 收件人是内部生成的用于重新发送邮件的收件人;不应传输它们。</span><span class="sxs-lookup"><span data-stu-id="2b770-161">MAPI_P1 recipients are internally generated recipients that are used for resending messages; they should not be transmitted.</span></span> <span data-ttu-id="2b770-162">而是使用其他收件人传输收件人信息。</span><span class="sxs-lookup"><span data-stu-id="2b770-162">Instead, use the other recipients for transmitting recipient information.</span></span> <span data-ttu-id="2b770-163">这种安排的目的是允许重发收件人查看与原始收件人完全相同的收件人表。</span><span class="sxs-lookup"><span data-stu-id="2b770-163">The purpose of this arrangement is to permit resend recipients to see the exact same recipient table as the original recipients.</span></span>
  
<span data-ttu-id="2b770-164">在**SubmitMessage**呼叫过程中, MAPI 后台处理程序将处理在邮件传输过程中打开的对象的方法, 并处理所有附件。</span><span class="sxs-lookup"><span data-stu-id="2b770-164">During a **SubmitMessage** call, the MAPI spooler processes methods for objects that are opened during the transfer of the message, and it processes any attachments.</span></span> <span data-ttu-id="2b770-165">此处理可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="2b770-165">This processing can take a long time.</span></span> <span data-ttu-id="2b770-166">在此处理过程中, 传输提供程序可以为 MAPI 后台处理程序调用[IMAPISupport:: SpoolerYield](imapisupport-spooleryield.md)方法, 以在其他系统任务中释放 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="2b770-166">Transport providers can call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) method for the MAPI spooler frequently during this processing to release CPU time for other system tasks.</span></span> 
  
<span data-ttu-id="2b770-167">MAPI 后台处理程序最初传递的邮件的收件人表中显示所有邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="2b770-167">All message recipients are visible in the recipient table of the message that the MAPI spooler originally passed.</span></span> <span data-ttu-id="2b770-168">传输提供程序应仅处理其可处理的收件人 (基于条目标识符、地址类型或两者), 且尚未将其**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="2b770-168">The transport provider should process only those recipients that it can handle — based on entry identifier, address type, or both — and that do not already have their **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property set to TRUE.</span></span> <span data-ttu-id="2b770-169">如果**PR_RESPONSIBILITY**已设置为 TRUE, 则另一个传输提供程序已处理该收件人。</span><span class="sxs-lookup"><span data-stu-id="2b770-169">If **PR_RESPONSIBILITY** is already set to TRUE, another transport provider has handled that recipient.</span></span> <span data-ttu-id="2b770-170">当提供程序完成对收件人的足够处理以确定是否可以处理该收件人的邮件时, 应将该收件人的**PR_RESPONSIBILITY**属性设置为 TRUE, 并在传递的邮件中。</span><span class="sxs-lookup"><span data-stu-id="2b770-170">When the provider completes sufficient processing of a recipient to determine whether it can handle messages for that recipient, it should set that recipient's **PR_RESPONSIBILITY** property to TRUE in the passed message.</span></span> <span data-ttu-id="2b770-171">通常, 提供程序在邮件传递完成后进行此确定。</span><span class="sxs-lookup"><span data-stu-id="2b770-171">Usually, the provider makes this determination after message delivery is complete.</span></span> 
  
<span data-ttu-id="2b770-172">通常情况下, 传输提供程序在完成邮件数据的传输之前不会从**SubmitMessage**调用返回。</span><span class="sxs-lookup"><span data-stu-id="2b770-172">Typically, the transport provider does not return from a **SubmitMessage** call until it completes the transfer of message data.</span></span> <span data-ttu-id="2b770-173">如果没有返回错误, 则从 MAPI 后台处理程序到提供程序的下一个调用是对[IXPLogon:: EndMessage](ixplogon-endmessage.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="2b770-173">If no error is returned, the next call from the MAPI spooler to the provider is a call to the [IXPLogon::EndMessage](ixplogon-endmessage.md) method.</span></span> 
  
<span data-ttu-id="2b770-174">如果**SubmitMessage**返回错误, MAPI 后台处理程序将在不保存更改的情况下释放邮件。</span><span class="sxs-lookup"><span data-stu-id="2b770-174">If **SubmitMessage** returns an error, the MAPI spooler releases the message in process without saving changes.</span></span> <span data-ttu-id="2b770-175">如果传输提供程序要求保存邮件更改, 则必须在返回前对邮件调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2b770-175">If the transport provider requires message changes to be saved, it must call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the message before returning.</span></span> 
  
<span data-ttu-id="2b770-176">如果传输问题导致出现错误, MAPI 后台处理程序将保留邮件, 但会根据_lpulReturnParm_中返回的值, 延迟将邮件重新提交到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2b770-176">In case of errors that occur because of transport problems, the MAPI spooler retains the message, but it delays resubmitting the message to the transport provider based on the value returned in  _lpulReturnParm_.</span></span> <span data-ttu-id="2b770-177">如果**SubmitMessage**的返回值是 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR, 则传输提供程序必须填写该值。</span><span class="sxs-lookup"><span data-stu-id="2b770-177">The transport provider must fill in that value if its return value from **SubmitMessage** is MAPI_E_WAIT or MAPI_E_NETWORK_ERROR.</span></span> <span data-ttu-id="2b770-178">如果发生严重错误, 则传输提供程序必须使用 NOTIFY_CRITICAL_ERROR 标记调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2b770-178">If a severe error condition occurs, the transport provider must call the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method with the NOTIFY_CRITICAL_ERROR flag.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2b770-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b770-179">See also</span></span>



[<span data-ttu-id="2b770-180">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="2b770-180">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="2b770-181">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="2b770-181">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="2b770-182">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="2b770-182">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md)
  
[<span data-ttu-id="2b770-183">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="2b770-183">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md)
  
[<span data-ttu-id="2b770-184">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="2b770-184">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md)
  
[<span data-ttu-id="2b770-185">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2b770-185">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

