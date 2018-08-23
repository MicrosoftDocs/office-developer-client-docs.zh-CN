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
ms.openlocfilehash: a2837e5470729ae3cdd0b83e17d0342620c986e8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592113"
---
# <a name="imapisupportspoolernotify"></a><span data-ttu-id="851f7-103">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="851f7-103">IMAPISupport::SpoolerNotify</span></span>

  
  
<span data-ttu-id="851f7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="851f7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="851f7-105">通知状态或服务的请求中的更改 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="851f7-105">Notifies the MAPI spooler of a change in status or a request for service.</span></span> 
  
```cpp
HRESULT SpoolerNotify(
ULONG ulFlags,
LPVOID lpvData
);
```

## <a name="parameters"></a><span data-ttu-id="851f7-106">参数</span><span class="sxs-lookup"><span data-stu-id="851f7-106">Parameters</span></span>

 <span data-ttu-id="851f7-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="851f7-107">_ulFlags_</span></span>
  
> <span data-ttu-id="851f7-108">[in]位掩码的标志，指示通知的类型。</span><span class="sxs-lookup"><span data-stu-id="851f7-108">[in] A bitmask of flags that indicates the type of notification.</span></span> <span data-ttu-id="851f7-109">传输提供程序可以设置的所有除外 NOTIFY_NEWMAIL_RECEIVED; 标志只有 NOTIFY_NEWMAIL_RECEIVED 和 NOTIFY_READTOSEND 是有效的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="851f7-109">Transport providers can set all of the flags except for NOTIFY_NEWMAIL_RECEIVED; only NOTIFY_NEWMAIL_RECEIVED and NOTIFY_READTOSEND are valid for message store providers.</span></span> <span data-ttu-id="851f7-110">以下标志可用于_ulFlags_参数：</span><span class="sxs-lookup"><span data-stu-id="851f7-110">The following flags are valid for the  _ulFlags_ parameter:</span></span> 
    
<span data-ttu-id="851f7-111">NOTIFY_CONFIG_CHANGE</span><span class="sxs-lookup"><span data-stu-id="851f7-111">NOTIFY_CONFIG_CHANGE</span></span> 
  
> <span data-ttu-id="851f7-112">注册请求更改传输提供程序的配置。</span><span class="sxs-lookup"><span data-stu-id="851f7-112">Registers a request to change the transport provider's configuration.</span></span> 
    
<span data-ttu-id="851f7-113">NOTIFY_CRITICAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="851f7-113">NOTIFY_CRITICAL_ERROR</span></span> 
  
> <span data-ttu-id="851f7-114">传输提供程序已发生不可恢复的错误。</span><span class="sxs-lookup"><span data-stu-id="851f7-114">An unrecoverable error has occurred to the transport provider.</span></span> <span data-ttu-id="851f7-115">因为 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR 用于传输提供程序调用_lpvData_参数，这些标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="851f7-115">Because both NOTIFY_SENTDEFERRED and NOTIFY_CRITICAL_ERROR use the  _lpvData_ parameter for transport provider calls, these flags are mutually exclusive.</span></span> 
    
<span data-ttu-id="851f7-116">NOTIFY_CRITSEC</span><span class="sxs-lookup"><span data-stu-id="851f7-116">NOTIFY_CRITSEC</span></span> 
  
> <span data-ttu-id="851f7-117">传输提供程序请求的关键部分。</span><span class="sxs-lookup"><span data-stu-id="851f7-117">Requests a critical section for the transport provider.</span></span> <span data-ttu-id="851f7-118">_LpvData_参数未定义，并且应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="851f7-118">The  _lpvData_ parameter is undefined and should be NULL.</span></span> 
    
<span data-ttu-id="851f7-119">NOTIFY_NEWMAIL</span><span class="sxs-lookup"><span data-stu-id="851f7-119">NOTIFY_NEWMAIL</span></span> 
  
> <span data-ttu-id="851f7-120">MAPI 后台处理程序应在下一可用时间下载任何新接收的消息。</span><span class="sxs-lookup"><span data-stu-id="851f7-120">The MAPI spooler should download any newly received messages at the next available time.</span></span> <span data-ttu-id="851f7-121">_LpvData_参数不确定，应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="851f7-121">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="851f7-122">NOTIFY_NEWMAIL_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="851f7-122">NOTIFY_NEWMAIL_RECEIVED</span></span> 
  
> <span data-ttu-id="851f7-123">消息存储库中已收到新消息。</span><span class="sxs-lookup"><span data-stu-id="851f7-123">A new message has been received in the message store.</span></span> <span data-ttu-id="851f7-124">_LpvData_参数指向介绍邮件[NEWMAIL_NOTIFICATION](newmail_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="851f7-124">The  _lpvData_ parameter points to a [NEWMAIL_NOTIFICATION](newmail_notification.md) structure that describes the message.</span></span> <span data-ttu-id="851f7-125">此标志用于与传输提供程序紧密耦合的消息存储提供程序，并且如果设置了 MAPI_NO_MAIL 标志登录的存储提供程序，则忽略。</span><span class="sxs-lookup"><span data-stu-id="851f7-125">This flag is used for message store providers that are tightly coupled with transport providers and is ignored if the store provider is logged on with the MAPI_NO_MAIL flag set.</span></span> 
    
<span data-ttu-id="851f7-126">NOTIFY_NONCRIT</span><span class="sxs-lookup"><span data-stu-id="851f7-126">NOTIFY_NONCRIT</span></span> 
  
> <span data-ttu-id="851f7-127">释放与_ulFlags_设置为 NOTIFY_CRITSEC 获取与以前调用**SpoolerNotify**关键部分。</span><span class="sxs-lookup"><span data-stu-id="851f7-127">Releases a critical section that was obtained with a previous call to **SpoolerNotify** with  _ulFlags_ set to NOTIFY_CRITSEC.</span></span> <span data-ttu-id="851f7-128">_LpvData_参数不确定，应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="851f7-128">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="851f7-129">NOTIFY_READYTOSEND</span><span class="sxs-lookup"><span data-stu-id="851f7-129">NOTIFY_READYTOSEND</span></span> 
  
> <span data-ttu-id="851f7-130">传输或消息存储提供程序已准备好发送消息。</span><span class="sxs-lookup"><span data-stu-id="851f7-130">The transport or message store provider is ready to send messages.</span></span> <span data-ttu-id="851f7-131">_LpvData_参数不确定，应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="851f7-131">The  _lpvData_ parameter is undefined and should be set to NULL.</span></span> 
    
<span data-ttu-id="851f7-132">NOTIFY_SENTDEFERRED</span><span class="sxs-lookup"><span data-stu-id="851f7-132">NOTIFY_SENTDEFERRED</span></span> 
  
> <span data-ttu-id="851f7-133">现在应发送之前延迟的邮件，并已准备好使用[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法调用传递邮件时，应通知传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="851f7-133">A previously deferred message should now be sent, and the transport provider should be notified when the message is ready to be delivered by using a call to the [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) method.</span></span> <span data-ttu-id="851f7-134">延迟的邮件的项标识符包含在由_lpvData_指向[SBinary](sbinary.md)结构。</span><span class="sxs-lookup"><span data-stu-id="851f7-134">The entry identifier of the deferred message is contained in an [SBinary](sbinary.md) structure pointed to by  _lpvData_.</span></span> <span data-ttu-id="851f7-135">因为 NOTIFY_SENTDEFERRED 和 NOTIFY_CRITICAL_ERROR 使用_lpvData_参数，这些标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="851f7-135">Because both NOTIFY_SENTDEFERRED and NOTIFY_CRITICAL_ERROR use the  _lpvData_ parameter, these flags are mutually exclusive.</span></span> 
    
 <span data-ttu-id="851f7-136">_lpvData_</span><span class="sxs-lookup"><span data-stu-id="851f7-136">_lpvData_</span></span>
  
> <span data-ttu-id="851f7-137">[in]指向适用于通知关联的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="851f7-137">[in] A pointer to associated data applicable to a notification.</span></span> <span data-ttu-id="851f7-138">_LpvData_参数仅在设置了以下标志时指向有效的数据 （_lpvData_ _ulFlags_设置为其他通知类型时为 NULL）：</span><span class="sxs-lookup"><span data-stu-id="851f7-138">The  _lpvData_ parameter points to valid data only when the following flags are set (_lpvData_ is NULL when  _ulFlags_ is set to the other notification types):</span></span> 
    
|<span data-ttu-id="851f7-139">**_ulFlags_设置**</span><span class="sxs-lookup"><span data-stu-id="851f7-139">**_ulFlags_ setting**</span></span>|<span data-ttu-id="851f7-140">**_lpvData_值**</span><span class="sxs-lookup"><span data-stu-id="851f7-140">**_lpvData_ value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="851f7-141">NOTIFY_CRITICAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="851f7-141">NOTIFY_CRITICAL_ERROR</span></span>  <br/> |<span data-ttu-id="851f7-142">有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="851f7-142">Information about the error.</span></span>  <br/> |
|<span data-ttu-id="851f7-143">NOTIFY_NEWMAIL_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="851f7-143">NOTIFY_NEWMAIL_RECEIVED</span></span>  <br/> |<span data-ttu-id="851f7-144">**NEWMAIL_NOTIFICATION**结构，其中包含有关在新的已发送邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="851f7-144">A **NEWMAIL_NOTIFICATION** structure that contains information about the newly delivered message.</span></span>  <br/> |
|<span data-ttu-id="851f7-145">NOTIFY_SENTDEFERRED</span><span class="sxs-lookup"><span data-stu-id="851f7-145">NOTIFY_SENTDEFERRED</span></span>  <br/> |<span data-ttu-id="851f7-146">**SBinary**结构，其中包含延迟消息的项标识符。</span><span class="sxs-lookup"><span data-stu-id="851f7-146">An **SBinary** structure that contains the entry identifier of deferred message.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="851f7-147">返回值</span><span class="sxs-lookup"><span data-stu-id="851f7-147">Return value</span></span>

<span data-ttu-id="851f7-148">S_OK</span><span class="sxs-lookup"><span data-stu-id="851f7-148">S_OK</span></span> 
  
> <span data-ttu-id="851f7-149">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="851f7-149">The notification was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="851f7-150">注解</span><span class="sxs-lookup"><span data-stu-id="851f7-150">Remarks</span></span>

<span data-ttu-id="851f7-151">**IMAPISupport::SpoolerNotify**方法已实现的消息存储和传输提供程序支持对象。</span><span class="sxs-lookup"><span data-stu-id="851f7-151">The **IMAPISupport::SpoolerNotify** method is implemented for message store and transport provider support objects.</span></span> <span data-ttu-id="851f7-152">这些提供程序调用**SpoolerNotify**以通知状态或服务的请求中的更改 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="851f7-152">These providers call **SpoolerNotify** to notify the MAPI spooler of a change in status or a request for service.</span></span> <span data-ttu-id="851f7-153">**SpoolerNotify**主要由传输提供程序，可能在会话期间随时调用。</span><span class="sxs-lookup"><span data-stu-id="851f7-153">**SpoolerNotify** is called primarily by transport providers and may be called at any time during the session.</span></span> 
  
## <a name="notes-to-transport-providers"></a><span data-ttu-id="851f7-154">Notes 传输提供程序</span><span class="sxs-lookup"><span data-stu-id="851f7-154">Notes to Transport Providers</span></span>

<span data-ttu-id="851f7-155">如果更改了传输提供程序配置后，调用**SpoolerNotify**并设置_ulFlags_为 NOTIFY_CONFIG_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="851f7-155">If you have changed your transport provider configuration, call **SpoolerNotify** and set  _ulFlags_ to NOTIFY_CONFIG_CHANGED.</span></span> <span data-ttu-id="851f7-156">**SpoolerNotify**响应通过调用[IXPLogon::AddressTypes](ixplogon-addresstypes.md)查询中支持的地址类型的更改。</span><span class="sxs-lookup"><span data-stu-id="851f7-156">**SpoolerNotify** responds by calling the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method to query for a change in supported address types.</span></span> 
  
<span data-ttu-id="851f7-157">如果您需要以确保不中断的处理的关键部分，设置为 NOTIFY_CRITSEC _ulFlags_呼叫**SpoolerNotify** 。</span><span class="sxs-lookup"><span data-stu-id="851f7-157">If you need a critical section to ensure uninterrupted processing, call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_CRITSEC.</span></span> <span data-ttu-id="851f7-158">设置此标志通知 MAPI 后台处理程序，它不应调用的[IXPLogon::Idle](ixplogon-idle.md)和[IXPLogon::Poll](ixplogon-poll.md)方法。</span><span class="sxs-lookup"><span data-stu-id="851f7-158">Setting this flag informs the MAPI spooler that it should not call the [IXPLogon::Idle](ixplogon-idle.md) and [IXPLogon::Poll](ixplogon-poll.md) methods.</span></span> <span data-ttu-id="851f7-159">在您已经打开，只要调用[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法返回 MAPI_E_BUSY 的关键部分。</span><span class="sxs-lookup"><span data-stu-id="851f7-159">While you have a critical section open, return MAPI_E_BUSY whenever the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method is called.</span></span> <span data-ttu-id="851f7-160">当您已完成关键部分时，进行_ulFlags_设置为 NOTIFY_NONCRIT **SpoolerNotify**到另一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="851f7-160">When you are finished with the critical section, make another call to **SpoolerNotify** with  _ulFlags_ set to NOTIFY_NONCRIT.</span></span> 
  
<span data-ttu-id="851f7-161">例如，如果您的远程传输提供程序的过程中上载邮件，您可能需要允许用户输入要建立远程连接的电话号码。</span><span class="sxs-lookup"><span data-stu-id="851f7-161">For example, if your remote transport provider is in the process of uploading messages, you might need to allow a user to enter a telephone number to establish the remote connection.</span></span> <span data-ttu-id="851f7-162">循环访问的对话框过程之前，您应声明的关键部分。</span><span class="sxs-lookup"><span data-stu-id="851f7-162">Before you loop through the dialog box procedure, you should declare a critical section.</span></span> <span data-ttu-id="851f7-163">当用户关闭对话框时，终止的对话框过程，您应释放关键部分。</span><span class="sxs-lookup"><span data-stu-id="851f7-163">When the user closes the dialog box, terminating the dialog box procedure, you should release the critical section.</span></span>
  
<span data-ttu-id="851f7-164">当到 NOTIFY_CRITICAL_ERROR 设置_ulFlags_时，MAPI 后台处理程序调用没有进一步除若要释放其提供程序。</span><span class="sxs-lookup"><span data-stu-id="851f7-164">When you set  _ulFlags_ to NOTIFY_CRITICAL_ERROR, the MAPI spooler makes no further calls to the provider except to release it.</span></span> <span data-ttu-id="851f7-165">如果您调用**SpoolerNotify**与 NOTIFY_CRITICAL_ERROR 设置从[IXPLogon::StartMessage](ixplogon-startmessage.md)或[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法，返回与相应的错误值从**StartMessage**或 * * SubmitMessage * * 呼叫紧接着**SpoolerNotify**呼叫。</span><span class="sxs-lookup"><span data-stu-id="851f7-165">If you call **SpoolerNotify** with NOTIFY_CRITICAL_ERROR set from the [IXPLogon::StartMessage](ixplogon-startmessage.md) or [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) methods, return with an appropriate error value from the **StartMessage** or ** SubmitMessage ** call immediately after the **SpoolerNotify** call.</span></span> 
  
<span data-ttu-id="851f7-166">如果您传输提供程序恢复从先前导致失败的情况，呼叫将设置为 NOTIFY_READYTOSEND _ulFlags_ **SpoolerNotify** 。</span><span class="sxs-lookup"><span data-stu-id="851f7-166">If your transport provider recovered from a condition that previously caused it to fail, call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_READYTOSEND.</span></span> <span data-ttu-id="851f7-167">此标志指示提供程序再次已准备好处理的消息。</span><span class="sxs-lookup"><span data-stu-id="851f7-167">This flag indicates that the provider is again ready to handle messages.</span></span> 
  
## <a name="notes-to-message-store-providers"></a><span data-ttu-id="851f7-168">对消息存储提供程序的说明</span><span class="sxs-lookup"><span data-stu-id="851f7-168">Notes to Message Store Providers</span></span>

<span data-ttu-id="851f7-169">调用**SpoolerNotify**之前在**IMessage::SubmitMessage**使[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md)您首次调用, 中_ulFlags_，传递 NOTIFY_READYTOSEND 标志。</span><span class="sxs-lookup"><span data-stu-id="851f7-169">Call **SpoolerNotify**, passing the NOTIFY_READYTOSEND flag in  _ulFlags_, before you make your first call to [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md) in **IMessage::SubmitMessage**.</span></span> <span data-ttu-id="851f7-170">此呼叫到**SpoolerNotify**需要对每个会话仅执行一次进行。</span><span class="sxs-lookup"><span data-stu-id="851f7-170">This call to **SpoolerNotify** needs to be made only once per session.</span></span> 
  
<span data-ttu-id="851f7-171">如果紧密耦合消息存储提供程序与传输提供程序并调用**SpoolerNotify** _ulFlags_设置为 NOTIFY_NEWMAIL_RECEIVED，MAPI 后台处理程序中打开新的邮件并开始处理新消息挂钩函数。</span><span class="sxs-lookup"><span data-stu-id="851f7-171">If your message store provider is tightly coupled with a transport provider and you call **SpoolerNotify** with  _ulFlags_ set to NOTIFY_NEWMAIL_RECEIVED, the MAPI spooler opens the new message and begins processing the new message hook function.</span></span> <span data-ttu-id="851f7-172">处理完成后，MAPI 后台处理程序调用[IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)方法来通知您自己的新消息。</span><span class="sxs-lookup"><span data-stu-id="851f7-172">When processing is complete, the MAPI spooler calls the [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md) method to inform you of your own new message.</span></span> 
  
<span data-ttu-id="851f7-173">有关调用**SpoolerNotify**的详细信息，请参阅以下主题中的任意：</span><span class="sxs-lookup"><span data-stu-id="851f7-173">For more information about calling **SpoolerNotify**, see any of the following topics:</span></span>
  
- [<span data-ttu-id="851f7-174">实现 FlushQueues 方法</span><span class="sxs-lookup"><span data-stu-id="851f7-174">Implementing the FlushQueues Method</span></span>](implementing-the-flushqueues-method.md)
    
- [<span data-ttu-id="851f7-175">与 MAPI 后台处理程序交互</span><span class="sxs-lookup"><span data-stu-id="851f7-175">Interacting with the MAPI Spooler</span></span>](interacting-with-the-mapi-spooler.md)
    
- [<span data-ttu-id="851f7-176">邮件接收模型</span><span class="sxs-lookup"><span data-stu-id="851f7-176">Message Reception Model</span></span>](message-reception-model.md)
    
## <a name="see-also"></a><span data-ttu-id="851f7-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="851f7-177">See also</span></span>



[<span data-ttu-id="851f7-178">IMsgStore::NotifyNewMail</span><span class="sxs-lookup"><span data-stu-id="851f7-178">IMsgStore::NotifyNewMail</span></span>](imsgstore-notifynewmail.md)
  
[<span data-ttu-id="851f7-179">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="851f7-179">IXPLogon::StartMessage</span></span>](ixplogon-startmessage.md)
  
[<span data-ttu-id="851f7-180">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="851f7-180">IXPLogon::SubmitMessage</span></span>](ixplogon-submitmessage.md)
  
[<span data-ttu-id="851f7-181">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="851f7-181">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

