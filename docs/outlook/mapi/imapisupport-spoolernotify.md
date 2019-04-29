---
title: IMAPISupportSpoolerNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.SpoolerNotify
api_type:
- COM
ms.assetid: d4f153b2-939f-4153-85fb-dc510193848c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 99377d63b4b5cf8731809446b70770f0c24231ed
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423767"
---
# <a name="imapisupportspoolernotify"></a><span data-ttu-id="82470-103">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="82470-103">IMAPISupport::SpoolerNotify</span></span>

  
  
<span data-ttu-id="82470-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82470-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82470-105">通知 MAPI 后台处理程序的状态更改或服务请求。</span><span class="sxs-lookup"><span data-stu-id="82470-105">Notifies the MAPI spooler of a change in status or a request for service.</span></span> 
  
```cpp
HRESULT SpoolerNotify(
ULONG ulFlags,
LPVOID lpvData
);
```

## <a name="parameters"></a><span data-ttu-id="82470-106">参数</span><span class="sxs-lookup"><span data-stu-id="82470-106">Parameters</span></span>

 <span data-ttu-id="82470-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="82470-107">_ulFlags_</span></span>
  
> <span data-ttu-id="82470-108">实时指示通知类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="82470-108">[in] A bitmask of flags that indicates the type of notification.</span></span> <span data-ttu-id="82470-109">传输提供程序可以设置除 NOTIFY_NEWMAIL_RECEIVED 之外的所有标志;只有 NOTIFY_NEWMAIL_RECEIVED 和 NOTIFY_READTOSEND 对邮件存储提供程序有效。</span><span class="sxs-lookup"><span data-stu-id="82470-109">Transport providers can set all of the flags except for NOTIFY_NEWMAIL_RECEIVED; only NOTIFY_NEWMAIL_RECEIVED and NOTIFY_READTOSEND are valid for message store providers.</span></span> <span data-ttu-id="82470-110">以下标志对_ulFlags_参数有效:</span><span class="sxs-lookup"><span data-stu-id="82470-110">The following flags are valid for the  _ulFlags_ parameter:</span></span> 
    
<span data-ttu-id="82470-111">NOTIFY_CONFIG_CHANGE</span><span class="sxs-lookup"><span data-stu-id="82470-111">NOTIFY_CONFIG_CHANGE</span></span> 
  
> <span data-ttu-id="82470-112">注册更改传输提供程序配置的请求。</span><span class="sxs-lookup"><span data-stu-id="82470-112">Registers a request to change the transport provider's configuration.</span></span> 
    
<span data-ttu-id="82470-113">NOTIFY_CRITICAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="82470-113">NOTIFY_CRITICAL_ERROR</span></span> 
  
> <span data-ttu-id="82470-114">传输提供程序发生不可恢复的错误。</span><span class="sxs-lookup"><span data-stu-id="82470-114">An unrecoverable error has occurred to the transport provider.</span></span> <span data-ttu-id="82470-115">由于 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR 将_lpvData_参数用于传输提供程序调用, 因此这些标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="82470-115">Because both NOTIFY_SENTDEFERRED and NOTIFY_CRITICAL_ERROR use the  _lpvData_ parameter for transport provider calls, these flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="82470-116">NOTIFY_CRITSEC</span><span class="sxs-lookup"><span data-stu-id="82470-116">NOTIFY_CRITSEC</span></span> 
  
> <span data-ttu-id="82470-117">请求传输提供程序的临界区。</span><span class="sxs-lookup"><span data-stu-id="82470-117">Requests a critical section for the transport provider.</span></span> <span data-ttu-id="82470-118">_lpvData_参数未定义, 应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="82470-118">The  _lpvData_ parameter is undefined and should be NULL.</span></span> 
    
<span data-ttu-id="82470-119">NOTIFY_NEWMAIL</span><span class="sxs-lookup"><span data-stu-id="82470-119">NOTIFY_NEWMAIL</span></span> 
  
> <span data-ttu-id="82470-120">MAPI 后台处理程序应在下一个可用时间下载所有新近收到的邮件。</span><span class="sxs-lookup"><span data-stu-id="82470-120">The MAPI spooler should download any newly received messages at the next available time.</span></span> <span data-ttu-id="82470-121">_lpvData_参数未定义, 应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="82470-121">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="82470-122">NOTIFY_NEWMAIL_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="82470-122">NOTIFY_NEWMAIL_RECEIVED</span></span> 
  
> <span data-ttu-id="82470-123">邮件存储区中已收到新邮件。</span><span class="sxs-lookup"><span data-stu-id="82470-123">A new message has been received in the message store.</span></span> <span data-ttu-id="82470-124">_lpvData_参数指向描述邮件的[NEWMAIL_NOTIFICATION](newmail_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="82470-124">The  _lpvData_ parameter points to a [NEWMAIL_NOTIFICATION](newmail_notification.md) structure that describes the message.</span></span> <span data-ttu-id="82470-125">此标志用于与传输提供程序紧密结合的邮件存储提供程序, 如果存储提供程序使用 MAPI_NO_MAIL 标志集登录, 则将被忽略。</span><span class="sxs-lookup"><span data-stu-id="82470-125">This flag is used for message store providers that are tightly coupled with transport providers and is ignored if the store provider is logged on with the MAPI_NO_MAIL flag set.</span></span> 
    
<span data-ttu-id="82470-126">NOTIFY_NONCRIT</span><span class="sxs-lookup"><span data-stu-id="82470-126">NOTIFY_NONCRIT</span></span> 
  
> <span data-ttu-id="82470-127">释放以前调用**SpoolerNotify**时获取的临界区, _ulFlags_设置为 NOTIFY_CRITSEC。</span><span class="sxs-lookup"><span data-stu-id="82470-127">Releases a critical section that was obtained with a previous call to **SpoolerNotify** with  _ulFlags_ set to NOTIFY_CRITSEC.</span></span> <span data-ttu-id="82470-128">_lpvData_参数未定义, 应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="82470-128">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="82470-129">NOTIFY_READYTOSEND</span><span class="sxs-lookup"><span data-stu-id="82470-129">NOTIFY_READYTOSEND</span></span> 
  
> <span data-ttu-id="82470-130">传输或邮件存储提供程序已准备好发送邮件。</span><span class="sxs-lookup"><span data-stu-id="82470-130">The transport or message store provider is ready to send messages.</span></span> <span data-ttu-id="82470-131">_lpvData_参数未定义, 应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="82470-131">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="82470-132">NOTIFY_SENTDEFERRED</span><span class="sxs-lookup"><span data-stu-id="82470-132">NOTIFY_SENTDEFERRED</span></span> 
  
> <span data-ttu-id="82470-133">应立即发送以前延迟的邮件, 并在可以通过调用[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)方法来传递邮件时, 应通知传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="82470-133">A previously deferred message should now be sent, and the transport provider should be notified when the message is ready to be delivered by using a call to the [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) method.</span></span> <span data-ttu-id="82470-134">延迟邮件的条目标识符包含在由_lpvData_指向的[SBinary](sbinary.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="82470-134">The entry identifier of the deferred message is contained in an [SBinary](sbinary.md) structure pointed to by  _lpvData_.</span></span> <span data-ttu-id="82470-135">由于 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR 都使用_lpvData_参数, 因此这些标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="82470-135">Because both NOTIFY_SENTDEFERRED and NOTIFY_CRITICAL_ERROR use the  _lpvData_ parameter, these flags are mutually exclusive.</span></span> 
    
 <span data-ttu-id="82470-136">_lpvData_</span><span class="sxs-lookup"><span data-stu-id="82470-136">_lpvData_</span></span>
  
> <span data-ttu-id="82470-137">实时指向适用于通知的关联数据的指针。</span><span class="sxs-lookup"><span data-stu-id="82470-137">[in] A pointer to associated data applicable to a notification.</span></span> <span data-ttu-id="82470-138">仅当设置了以下标志时, _lpvData_参数才指向有效数据 (当_ulFlags_设置为其他通知类型时,_lpvData_为 NULL):</span><span class="sxs-lookup"><span data-stu-id="82470-138">The  _lpvData_ parameter points to valid data only when the following flags are set (_lpvData_ is NULL when  _ulFlags_ is set to the other notification types):</span></span> 
    
|<span data-ttu-id="82470-139">**_ulFlags_设置**</span><span class="sxs-lookup"><span data-stu-id="82470-139">**_ulFlags_ setting**</span></span>|<span data-ttu-id="82470-140">**_lpvData_值**</span><span class="sxs-lookup"><span data-stu-id="82470-140">**_lpvData_ value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82470-141">NOTIFY_CRITICAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="82470-141">NOTIFY_CRITICAL_ERROR</span></span>  <br/> |<span data-ttu-id="82470-142">有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="82470-142">Information about the error.</span></span>  <br/> |
|<span data-ttu-id="82470-143">NOTIFY_NEWMAIL_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="82470-143">NOTIFY_NEWMAIL_RECEIVED</span></span>  <br/> |<span data-ttu-id="82470-144">包含有关新传递的邮件的信息的**NEWMAIL_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="82470-144">A **NEWMAIL_NOTIFICATION** structure that contains information about the newly delivered message.</span></span>  <br/> |
|<span data-ttu-id="82470-145">NOTIFY_SENTDEFERRED</span><span class="sxs-lookup"><span data-stu-id="82470-145">NOTIFY_SENTDEFERRED</span></span>  <br/> |<span data-ttu-id="82470-146">包含延迟邮件的条目标识符的**SBinary**结构。</span><span class="sxs-lookup"><span data-stu-id="82470-146">An **SBinary** structure that contains the entry identifier of deferred message.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="82470-147">返回值</span><span class="sxs-lookup"><span data-stu-id="82470-147">Return value</span></span>

<span data-ttu-id="82470-148">S_OK</span><span class="sxs-lookup"><span data-stu-id="82470-148">S_OK</span></span> 
  
> <span data-ttu-id="82470-149">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="82470-149">The notification was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="82470-150">说明</span><span class="sxs-lookup"><span data-stu-id="82470-150">Remarks</span></span>

<span data-ttu-id="82470-151">为邮件存储和传输提供程序支持对象实现了**IMAPISupport:: SpoolerNotify**方法。</span><span class="sxs-lookup"><span data-stu-id="82470-151">The **IMAPISupport::SpoolerNotify** method is implemented for message store and transport provider support objects.</span></span> <span data-ttu-id="82470-152">这些提供程序调用**SpoolerNotify**以通知 MAPI 后台处理程序的状态更改或服务请求。</span><span class="sxs-lookup"><span data-stu-id="82470-152">These providers call **SpoolerNotify** to notify the MAPI spooler of a change in status or a request for service.</span></span> <span data-ttu-id="82470-153">**SpoolerNotify**主要由传输提供程序调用, 并可在会话期间的任何时间调用。</span><span class="sxs-lookup"><span data-stu-id="82470-153">**SpoolerNotify** is called primarily by transport providers and may be called at any time during the session.</span></span> 
  
## <a name="notes-to-transport-providers"></a><span data-ttu-id="82470-154">传输提供程序注意事项</span><span class="sxs-lookup"><span data-stu-id="82470-154">Notes to Transport Providers</span></span>

<span data-ttu-id="82470-155">如果你更改了传输提供程序配置, 请调用**SpoolerNotify**并将_ulFlags_设置为 NOTIFY_CONFIG_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="82470-155">If you have changed your transport provider configuration, call **SpoolerNotify** and set  _ulFlags_ to NOTIFY_CONFIG_CHANGED.</span></span> <span data-ttu-id="82470-156">**SpoolerNotify**通过调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法来查询受支持的地址类型中的更改, 从而做出响应。</span><span class="sxs-lookup"><span data-stu-id="82470-156">**SpoolerNotify** responds by calling the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method to query for a change in supported address types.</span></span> 
  
<span data-ttu-id="82470-157">如果您需要一个临界区来确保不间断地进行处理, 请调用**SpoolerNotify** , 并将_ulFlags_设置为 NOTIFY_CRITSEC。</span><span class="sxs-lookup"><span data-stu-id="82470-157">If you need a critical section to ensure uninterrupted processing, call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_CRITSEC.</span></span> <span data-ttu-id="82470-158">设置此标志将通知 MAPI 后台处理程序不应调用[IXPLogon:: Idle](ixplogon-idle.md) and [IXPLogon::P oll](ixplogon-poll.md)方法。</span><span class="sxs-lookup"><span data-stu-id="82470-158">Setting this flag informs the MAPI spooler that it should not call the [IXPLogon::Idle](ixplogon-idle.md) and [IXPLogon::Poll](ixplogon-poll.md) methods.</span></span> <span data-ttu-id="82470-159">当您打开一个关键部分时, 请在调用[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法时返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="82470-159">While you have a critical section open, return MAPI_E_BUSY whenever the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method is called.</span></span> <span data-ttu-id="82470-160">完成 "临界" 部分后, 再次调用**SpoolerNotify** , 将_ulFlags_设置为 NOTIFY_NONCRIT。</span><span class="sxs-lookup"><span data-stu-id="82470-160">When you are finished with the critical section, make another call to **SpoolerNotify** with  _ulFlags_ set to NOTIFY_NONCRIT.</span></span> 
  
<span data-ttu-id="82470-161">例如, 如果您的远程传输提供程序正在上载邮件, 则可能需要允许用户输入电话号码以建立远程连接。</span><span class="sxs-lookup"><span data-stu-id="82470-161">For example, if your remote transport provider is in the process of uploading messages, you might need to allow a user to enter a telephone number to establish the remote connection.</span></span> <span data-ttu-id="82470-162">在对话框过程中循环之前, 应声明一个临界区。</span><span class="sxs-lookup"><span data-stu-id="82470-162">Before you loop through the dialog box procedure, you should declare a critical section.</span></span> <span data-ttu-id="82470-163">当用户关闭对话框时, 终止对话框过程, 应释放临界区。</span><span class="sxs-lookup"><span data-stu-id="82470-163">When the user closes the dialog box, terminating the dialog box procedure, you should release the critical section.</span></span>
  
<span data-ttu-id="82470-164">当您将_ulFlags_设置为 NOTIFY_CRITICAL_ERROR 时, MAPI 后台处理程序将不会再对提供程序进行任何调用, 除非将其释放。</span><span class="sxs-lookup"><span data-stu-id="82470-164">When you set  _ulFlags_ to NOTIFY_CRITICAL_ERROR, the MAPI spooler makes no further calls to the provider except to release it.</span></span> <span data-ttu-id="82470-165">如果使用 NOTIFY_CRITICAL_ERROR ( [IXPLogon:: StartMessage](ixplogon-startmessage.md)或[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)方法) 中的设置调用**SpoolerNotify** , 则会从**StartMessage**或 \* \* SubmitMessage \* \* 调用中返回适当的错误值紧跟在**SpoolerNotify**调用之后。</span><span class="sxs-lookup"><span data-stu-id="82470-165">If you call **SpoolerNotify** with NOTIFY_CRITICAL_ERROR set from the [IXPLogon::StartMessage](ixplogon-startmessage.md) or [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) methods, return with an appropriate error value from the **StartMessage** or \*\* SubmitMessage \*\* call immediately after the **SpoolerNotify** call.</span></span> 
  
<span data-ttu-id="82470-166">如果您的传输提供程序从以前导致它失败的条件中恢复, 请调用**SpoolerNotify** with _ulFlags_设置为 NOTIFY_READYTOSEND。</span><span class="sxs-lookup"><span data-stu-id="82470-166">If your transport provider recovered from a condition that previously caused it to fail, call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_READYTOSEND.</span></span> <span data-ttu-id="82470-167">此标志指示提供程序可再次准备好处理邮件。</span><span class="sxs-lookup"><span data-stu-id="82470-167">This flag indicates that the provider is again ready to handle messages.</span></span> 
  
## <a name="notes-to-message-store-providers"></a><span data-ttu-id="82470-168">邮件存储提供程序注意事项</span><span class="sxs-lookup"><span data-stu-id="82470-168">Notes to Message Store Providers</span></span>

<span data-ttu-id="82470-169">先调用**SpoolerNotify**, 在_ulFlags_中传递 NOTIFY_READYTOSEND 标志, 然后再调用 IMAPISupport: reparesubmit **:: IMessage**中的[:P SubmitMessage](imapisupport-preparesubmit.md) 。</span><span class="sxs-lookup"><span data-stu-id="82470-169">Call **SpoolerNotify**, passing the NOTIFY_READYTOSEND flag in  _ulFlags_, before you make your first call to [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md) in **IMessage::SubmitMessage**.</span></span> <span data-ttu-id="82470-170">对**SpoolerNotify**的此调用在每次会话中需要进行一次。</span><span class="sxs-lookup"><span data-stu-id="82470-170">This call to **SpoolerNotify** needs to be made only once per session.</span></span> 
  
<span data-ttu-id="82470-171">如果您的邮件存储提供程序与传输提供程序紧密结合, 并且您调用**SpoolerNotify** _ulFlags_设置为 NOTIFY_NEWMAIL_RECEIVED, MAPI 后台处理程序将打开新邮件并开始处理新的邮件挂钩函数。</span><span class="sxs-lookup"><span data-stu-id="82470-171">If your message store provider is tightly coupled with a transport provider and you call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_NEWMAIL_RECEIVED, the MAPI spooler opens the new message and begins processing the new message hook function.</span></span> <span data-ttu-id="82470-172">处理完成后, MAPI 后台处理程序将调用[IMsgStore:: NotifyNewMail](imsgstore-notifynewmail.md)方法来通知您自己的新邮件。</span><span class="sxs-lookup"><span data-stu-id="82470-172">When processing is complete, the MAPI spooler calls the [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md) method to inform you of your own new message.</span></span> 
  
<span data-ttu-id="82470-173">有关调用**SpoolerNotify**的详细信息, 请参阅以下任一主题:</span><span class="sxs-lookup"><span data-stu-id="82470-173">For more information about calling **SpoolerNotify**, see any of the following topics:</span></span>
  
- [<span data-ttu-id="82470-174">实现 FlushQueues 方法</span><span class="sxs-lookup"><span data-stu-id="82470-174">Implementing the FlushQueues Method</span></span>](implementing-the-flushqueues-method.md)
    
- [<span data-ttu-id="82470-175">与 MAPI 后台处理程序交互</span><span class="sxs-lookup"><span data-stu-id="82470-175">Interacting with the MAPI Spooler</span></span>](interacting-with-the-mapi-spooler.md)
    
- [<span data-ttu-id="82470-176">邮件接收模型</span><span class="sxs-lookup"><span data-stu-id="82470-176">Message Reception Model</span></span>](message-reception-model.md)
    
## <a name="see-also"></a><span data-ttu-id="82470-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82470-177">See also</span></span>



[<span data-ttu-id="82470-178">IMsgStore::NotifyNewMail</span><span class="sxs-lookup"><span data-stu-id="82470-178">IMsgStore::NotifyNewMail</span></span>](imsgstore-notifynewmail.md)
  
[<span data-ttu-id="82470-179">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="82470-179">IXPLogon::StartMessage</span></span>](ixplogon-startmessage.md)
  
[<span data-ttu-id="82470-180">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="82470-180">IXPLogon::SubmitMessage</span></span>](ixplogon-submitmessage.md)
  
[<span data-ttu-id="82470-181">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="82470-181">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

