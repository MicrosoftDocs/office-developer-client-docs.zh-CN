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
# <a name="imapisupportspoolernotify"></a><span data-ttu-id="2e457-103">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="2e457-103">IMAPISupport::SpoolerNotify</span></span>

  
  
<span data-ttu-id="2e457-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e457-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e457-105">通知 MAPI 后台处理程序状态更改或服务请求。</span><span class="sxs-lookup"><span data-stu-id="2e457-105">Notifies the MAPI spooler of a change in status or a request for service.</span></span> 
  
```cpp
HRESULT SpoolerNotify(
ULONG ulFlags,
LPVOID lpvData
);
```

## <a name="parameters"></a><span data-ttu-id="2e457-106">参数</span><span class="sxs-lookup"><span data-stu-id="2e457-106">Parameters</span></span>

 <span data-ttu-id="2e457-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2e457-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2e457-108">[in]指示通知类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="2e457-108">[in] A bitmask of flags that indicates the type of notification.</span></span> <span data-ttu-id="2e457-109">传输提供程序可以设置除其他所有标志NOTIFY_NEWMAIL_RECEIVED;只有 NOTIFY_NEWMAIL_RECEIVED 和 NOTIFY_READTOSEND 对邮件存储提供程序有效。</span><span class="sxs-lookup"><span data-stu-id="2e457-109">Transport providers can set all of the flags except for NOTIFY_NEWMAIL_RECEIVED; only NOTIFY_NEWMAIL_RECEIVED and NOTIFY_READTOSEND are valid for message store providers.</span></span> <span data-ttu-id="2e457-110">以下标志对  _ulFlags_ 参数有效：</span><span class="sxs-lookup"><span data-stu-id="2e457-110">The following flags are valid for the  _ulFlags_ parameter:</span></span> 
    
<span data-ttu-id="2e457-111">NOTIFY_CONFIG_CHANGE</span><span class="sxs-lookup"><span data-stu-id="2e457-111">NOTIFY_CONFIG_CHANGE</span></span> 
  
> <span data-ttu-id="2e457-112">注册更改传输提供程序配置的请求。</span><span class="sxs-lookup"><span data-stu-id="2e457-112">Registers a request to change the transport provider's configuration.</span></span> 
    
<span data-ttu-id="2e457-113">NOTIFY_CRITICAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="2e457-113">NOTIFY_CRITICAL_ERROR</span></span> 
  
> <span data-ttu-id="2e457-114">传输提供程序发生了不可恢复的错误。</span><span class="sxs-lookup"><span data-stu-id="2e457-114">An unrecoverable error has occurred to the transport provider.</span></span> <span data-ttu-id="2e457-115">由于NOTIFY_SENTDEFERRED和NOTIFY_CRITICAL_ERROR都使用  _lpvData_ 参数进行传输提供程序调用，因此这些标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="2e457-115">Because both NOTIFY_SENTDEFERRED and NOTIFY_CRITICAL_ERROR use the  _lpvData_ parameter for transport provider calls, these flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="2e457-116">NOTIFY_CRITSEC</span><span class="sxs-lookup"><span data-stu-id="2e457-116">NOTIFY_CRITSEC</span></span> 
  
> <span data-ttu-id="2e457-117">请求传输提供程序的关键部分。</span><span class="sxs-lookup"><span data-stu-id="2e457-117">Requests a critical section for the transport provider.</span></span> <span data-ttu-id="2e457-118">_lpvData_ 参数未定义，应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2e457-118">The  _lpvData_ parameter is undefined and should be NULL.</span></span> 
    
<span data-ttu-id="2e457-119">NOTIFY_NEWMAIL</span><span class="sxs-lookup"><span data-stu-id="2e457-119">NOTIFY_NEWMAIL</span></span> 
  
> <span data-ttu-id="2e457-120">MAPI 后台处理程序应在下一个可用时间下载任何新收到的消息。</span><span class="sxs-lookup"><span data-stu-id="2e457-120">The MAPI spooler should download any newly received messages at the next available time.</span></span> <span data-ttu-id="2e457-121">_lpvData_ 参数未定义，应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2e457-121">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="2e457-122">NOTIFY_NEWMAIL_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="2e457-122">NOTIFY_NEWMAIL_RECEIVED</span></span> 
  
> <span data-ttu-id="2e457-123">已在邮件存储中收到新邮件。</span><span class="sxs-lookup"><span data-stu-id="2e457-123">A new message has been received in the message store.</span></span> <span data-ttu-id="2e457-124">_lpvData_ 参数指向一 [个NEWMAIL_NOTIFICATION](newmail_notification.md)消息的变量结构。</span><span class="sxs-lookup"><span data-stu-id="2e457-124">The  _lpvData_ parameter points to a [NEWMAIL_NOTIFICATION](newmail_notification.md) structure that describes the message.</span></span> <span data-ttu-id="2e457-125">此标志用于与传输提供程序紧密结合的邮件存储提供程序，如果存储提供程序使用设置的邮件存储MAPI_NO_MAIL忽略。</span><span class="sxs-lookup"><span data-stu-id="2e457-125">This flag is used for message store providers that are tightly coupled with transport providers and is ignored if the store provider is logged on with the MAPI_NO_MAIL flag set.</span></span> 
    
<span data-ttu-id="2e457-126">NOTIFY_NONCRIT</span><span class="sxs-lookup"><span data-stu-id="2e457-126">NOTIFY_NONCRIT</span></span> 
  
> <span data-ttu-id="2e457-127">释放上一次调用 **SpoolerNotify** 时获取的关键节  _，ulFlags_ 设置为 NOTIFY_CRITSEC。</span><span class="sxs-lookup"><span data-stu-id="2e457-127">Releases a critical section that was obtained with a previous call to **SpoolerNotify** with  _ulFlags_ set to NOTIFY_CRITSEC.</span></span> <span data-ttu-id="2e457-128">_lpvData_ 参数未定义，应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2e457-128">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="2e457-129">NOTIFY_READYTOSEND</span><span class="sxs-lookup"><span data-stu-id="2e457-129">NOTIFY_READYTOSEND</span></span> 
  
> <span data-ttu-id="2e457-130">传输或邮件存储提供程序已准备好发送邮件。</span><span class="sxs-lookup"><span data-stu-id="2e457-130">The transport or message store provider is ready to send messages.</span></span> <span data-ttu-id="2e457-131">_lpvData_ 参数未定义，应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2e457-131">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="2e457-132">NOTIFY_SENTDEFERRED</span><span class="sxs-lookup"><span data-stu-id="2e457-132">NOTIFY_SENTDEFERRED</span></span> 
  
> <span data-ttu-id="2e457-133">现在应发送以前延迟的邮件，并且应在准备好使用 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md) 方法传递邮件时通知传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2e457-133">A previously deferred message should now be sent, and the transport provider should be notified when the message is ready to be delivered by using a call to the [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) method.</span></span> <span data-ttu-id="2e457-134">延迟邮件的条目标识符包含在 _lpvData_ 指向的 [SBinary](sbinary.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="2e457-134">The entry identifier of the deferred message is contained in an [SBinary](sbinary.md) structure pointed to by  _lpvData_.</span></span> <span data-ttu-id="2e457-135">由于 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR都使用  _lpvData_ 参数，因此这些标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="2e457-135">Because both NOTIFY_SENTDEFERRED and NOTIFY_CRITICAL_ERROR use the  _lpvData_ parameter, these flags are mutually exclusive.</span></span> 
    
 <span data-ttu-id="2e457-136">_lpvData_</span><span class="sxs-lookup"><span data-stu-id="2e457-136">_lpvData_</span></span>
  
> <span data-ttu-id="2e457-137">[in]指向适用于通知的关联数据的指针。</span><span class="sxs-lookup"><span data-stu-id="2e457-137">[in] A pointer to associated data applicable to a notification.</span></span> <span data-ttu-id="2e457-138">_只有在将 ulFlags_ 设置为其他通知类型时，lpvData 参数才 (设置为 NULL 时 _，lpvData_ 参数才指向有效) ： </span><span class="sxs-lookup"><span data-stu-id="2e457-138">The  _lpvData_ parameter points to valid data only when the following flags are set (_lpvData_ is NULL when  _ulFlags_ is set to the other notification types):</span></span> 
    
|<span data-ttu-id="2e457-139">**_ulFlags_ 设置**</span><span class="sxs-lookup"><span data-stu-id="2e457-139">**_ulFlags_ setting**</span></span>|<span data-ttu-id="2e457-140">**_lpvData_ 值**</span><span class="sxs-lookup"><span data-stu-id="2e457-140">**_lpvData_ value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e457-141">NOTIFY_CRITICAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="2e457-141">NOTIFY_CRITICAL_ERROR</span></span>  <br/> |<span data-ttu-id="2e457-142">有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="2e457-142">Information about the error.</span></span>  <br/> |
|<span data-ttu-id="2e457-143">NOTIFY_NEWMAIL_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="2e457-143">NOTIFY_NEWMAIL_RECEIVED</span></span>  <br/> |<span data-ttu-id="2e457-144">一 **NEWMAIL_NOTIFICATION** 包含有关新传递的邮件的信息的一个安全结构。</span><span class="sxs-lookup"><span data-stu-id="2e457-144">A **NEWMAIL_NOTIFICATION** structure that contains information about the newly delivered message.</span></span>  <br/> |
|<span data-ttu-id="2e457-145">NOTIFY_SENTDEFERRED</span><span class="sxs-lookup"><span data-stu-id="2e457-145">NOTIFY_SENTDEFERRED</span></span>  <br/> |<span data-ttu-id="2e457-146">包含延迟邮件的条目标识符的 **SBinary** 结构。</span><span class="sxs-lookup"><span data-stu-id="2e457-146">An **SBinary** structure that contains the entry identifier of deferred message.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="2e457-147">返回值</span><span class="sxs-lookup"><span data-stu-id="2e457-147">Return value</span></span>

<span data-ttu-id="2e457-148">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e457-148">S_OK</span></span> 
  
> <span data-ttu-id="2e457-149">通知成功。</span><span class="sxs-lookup"><span data-stu-id="2e457-149">The notification was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2e457-150">备注</span><span class="sxs-lookup"><span data-stu-id="2e457-150">Remarks</span></span>

<span data-ttu-id="2e457-151">**IMAPISupport：：SpoolerNotify** 方法为邮件存储和传输提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="2e457-151">The **IMAPISupport::SpoolerNotify** method is implemented for message store and transport provider support objects.</span></span> <span data-ttu-id="2e457-152">这些提供程序调用 **SpoolerNotify** 以通知 MAPI 后台处理程序状态更改或服务请求。</span><span class="sxs-lookup"><span data-stu-id="2e457-152">These providers call **SpoolerNotify** to notify the MAPI spooler of a change in status or a request for service.</span></span> <span data-ttu-id="2e457-153">**SpoolerNotify** 主要由传输提供程序调用，并且可能在会话期间随时调用。</span><span class="sxs-lookup"><span data-stu-id="2e457-153">**SpoolerNotify** is called primarily by transport providers and may be called at any time during the session.</span></span> 
  
## <a name="notes-to-transport-providers"></a><span data-ttu-id="2e457-154">对传输提供程序的注释</span><span class="sxs-lookup"><span data-stu-id="2e457-154">Notes to Transport Providers</span></span>

<span data-ttu-id="2e457-155">如果已更改传输提供程序配置，请调用 **SpoolerNotify，** 将  _ulFlags_ 设置为 NOTIFY_CONFIG_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="2e457-155">If you have changed your transport provider configuration, call **SpoolerNotify** and set  _ulFlags_ to NOTIFY_CONFIG_CHANGED.</span></span> <span data-ttu-id="2e457-156">**SpoolerNotify** 通过调用 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) 方法来查询受支持的地址类型中的更改来做出响应。</span><span class="sxs-lookup"><span data-stu-id="2e457-156">**SpoolerNotify** responds by calling the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method to query for a change in supported address types.</span></span> 
  
<span data-ttu-id="2e457-157">如果需要一个关键部分以确保不中断处理，请调用 **SpoolerNotify，** 将  _ulFlags_ 设置为 NOTIFY_CRITSEC。</span><span class="sxs-lookup"><span data-stu-id="2e457-157">If you need a critical section to ensure uninterrupted processing, call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_CRITSEC.</span></span> <span data-ttu-id="2e457-158">设置此标志将通知 MAPI 后台处理程序不应调用 [IXPLogon：：Idle](ixplogon-idle.md) 和 [IXPLogon：:P oll](ixplogon-poll.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="2e457-158">Setting this flag informs the MAPI spooler that it should not call the [IXPLogon::Idle](ixplogon-idle.md) and [IXPLogon::Poll](ixplogon-poll.md) methods.</span></span> <span data-ttu-id="2e457-159">在打开关键节时，每当MAPI_E_BUSY [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法时，都会返回一个返回值。</span><span class="sxs-lookup"><span data-stu-id="2e457-159">While you have a critical section open, return MAPI_E_BUSY whenever the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method is called.</span></span> <span data-ttu-id="2e457-160">完成关键部分后，请再次调用 **SpoolerNotify，** 将  _ulFlags_ 设置为 NOTIFY_NONCRIT。</span><span class="sxs-lookup"><span data-stu-id="2e457-160">When you are finished with the critical section, make another call to **SpoolerNotify** with  _ulFlags_ set to NOTIFY_NONCRIT.</span></span> 
  
<span data-ttu-id="2e457-161">例如，如果您的远程传输提供商正在上载邮件，您可能需要允许用户输入电话号码以建立远程连接。</span><span class="sxs-lookup"><span data-stu-id="2e457-161">For example, if your remote transport provider is in the process of uploading messages, you might need to allow a user to enter a telephone number to establish the remote connection.</span></span> <span data-ttu-id="2e457-162">在循环访问对话框过程之前，应声明一个关键部分。</span><span class="sxs-lookup"><span data-stu-id="2e457-162">Before you loop through the dialog box procedure, you should declare a critical section.</span></span> <span data-ttu-id="2e457-163">当用户关闭对话框并终止对话框过程时，应释放关键部分。</span><span class="sxs-lookup"><span data-stu-id="2e457-163">When the user closes the dialog box, terminating the dialog box procedure, you should release the critical section.</span></span>
  
<span data-ttu-id="2e457-164">将  _ulFlags_ 设置为 NOTIFY_CRITICAL_ERROR时，MAPI 后台处理程序不会进一步调用提供程序，除非释放它。</span><span class="sxs-lookup"><span data-stu-id="2e457-164">When you set  _ulFlags_ to NOTIFY_CRITICAL_ERROR, the MAPI spooler makes no further calls to the provider except to release it.</span></span> <span data-ttu-id="2e457-165">如果使用 [IXPLogon：：StartMessage](ixplogon-startmessage.md)或 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md)方法中设置的 NOTIFY_CRITICAL_ERROR 调用 **SpoolerNotify，** 则返回 **SpoolerNotify** 调用后立即 **从 StartMessage** 或 \*\* SubmitMessage \*\* 调用中返回相应的错误值。</span><span class="sxs-lookup"><span data-stu-id="2e457-165">If you call **SpoolerNotify** with NOTIFY_CRITICAL_ERROR set from the [IXPLogon::StartMessage](ixplogon-startmessage.md) or [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) methods, return with an appropriate error value from the **StartMessage** or \*\* SubmitMessage \*\* call immediately after the **SpoolerNotify** call.</span></span> 
  
<span data-ttu-id="2e457-166">如果传输提供程序从之前导致其失败的条件中恢复，请调用 **spoolerNotify，** 将  _ulFlags_ 设置为 NOTIFY_READYTOSEND。</span><span class="sxs-lookup"><span data-stu-id="2e457-166">If your transport provider recovered from a condition that previously caused it to fail, call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_READYTOSEND.</span></span> <span data-ttu-id="2e457-167">此标志指示提供程序已再次准备好处理邮件。</span><span class="sxs-lookup"><span data-stu-id="2e457-167">This flag indicates that the provider is again ready to handle messages.</span></span> 
  
## <a name="notes-to-message-store-providers"></a><span data-ttu-id="2e457-168">邮件存储提供程序说明</span><span class="sxs-lookup"><span data-stu-id="2e457-168">Notes to Message Store Providers</span></span>

<span data-ttu-id="2e457-169">调用 **SpoolerNotify**，在 _ulFlags_ 中传递 NOTIFY_READYTOSEND 标志，然后再在 **IMessage：：SubmitMessage** 中首次调用 [IMAPISupport：:P repareSubmit。](imapisupport-preparesubmit.md)</span><span class="sxs-lookup"><span data-stu-id="2e457-169">Call **SpoolerNotify**, passing the NOTIFY_READYTOSEND flag in  _ulFlags_, before you make your first call to [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md) in **IMessage::SubmitMessage**.</span></span> <span data-ttu-id="2e457-170">每个会话 **只需调用一次 SpoolerNotify。**</span><span class="sxs-lookup"><span data-stu-id="2e457-170">This call to **SpoolerNotify** needs to be made only once per session.</span></span> 
  
<span data-ttu-id="2e457-171">如果邮件存储提供程序与传输提供程序紧密结合，并且调用 **SpoolerNotify** 且  _ulFlags_ 设置为 NOTIFY_NEWMAIL_RECEIVED，则 MAPI 后台处理程序将打开新邮件并开始处理新邮件挂钩函数。</span><span class="sxs-lookup"><span data-stu-id="2e457-171">If your message store provider is tightly coupled with a transport provider and you call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_NEWMAIL_RECEIVED, the MAPI spooler opens the new message and begins processing the new message hook function.</span></span> <span data-ttu-id="2e457-172">处理完成后，MAPI 后台处理程序将调用 [IMsgStore：：NotifyNewMail](imsgstore-notifynewmail.md) 方法，以通知您自己的新邮件。</span><span class="sxs-lookup"><span data-stu-id="2e457-172">When processing is complete, the MAPI spooler calls the [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md) method to inform you of your own new message.</span></span> 
  
<span data-ttu-id="2e457-173">有关调用 **SpoolerNotify 的信息，** 请参阅以下任何主题：</span><span class="sxs-lookup"><span data-stu-id="2e457-173">For more information about calling **SpoolerNotify**, see any of the following topics:</span></span>
  
- [<span data-ttu-id="2e457-174">实现 FlushQueues 方法</span><span class="sxs-lookup"><span data-stu-id="2e457-174">Implementing the FlushQueues Method</span></span>](implementing-the-flushqueues-method.md)
    
- [<span data-ttu-id="2e457-175">与 MAPI 后台处理程序交互</span><span class="sxs-lookup"><span data-stu-id="2e457-175">Interacting with the MAPI Spooler</span></span>](interacting-with-the-mapi-spooler.md)
    
- [<span data-ttu-id="2e457-176">邮件接收模型</span><span class="sxs-lookup"><span data-stu-id="2e457-176">Message Reception Model</span></span>](message-reception-model.md)
    
## <a name="see-also"></a><span data-ttu-id="2e457-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e457-177">See also</span></span>



[<span data-ttu-id="2e457-178">IMsgStore::NotifyNewMail</span><span class="sxs-lookup"><span data-stu-id="2e457-178">IMsgStore::NotifyNewMail</span></span>](imsgstore-notifynewmail.md)
  
[<span data-ttu-id="2e457-179">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="2e457-179">IXPLogon::StartMessage</span></span>](ixplogon-startmessage.md)
  
[<span data-ttu-id="2e457-180">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="2e457-180">IXPLogon::SubmitMessage</span></span>](ixplogon-submitmessage.md)
  
[<span data-ttu-id="2e457-181">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2e457-181">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

