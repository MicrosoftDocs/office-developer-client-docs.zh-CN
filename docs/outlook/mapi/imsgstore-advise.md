---
title: IMsgStoreAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.Advise
api_type:
- COM
ms.assetid: 8c57e743-a798-4e39-a61a-46dff8b1ac7c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b4abef731541e308b2c2ebc6f4aaddf4458e257
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317323"
---
# <a name="imsgstoreadvise"></a><span data-ttu-id="f9801-103">IMsgStore::Advise</span><span class="sxs-lookup"><span data-stu-id="f9801-103">IMsgStore::Advise</span></span>

  
  
<span data-ttu-id="f9801-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f9801-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f9801-105">注册以接收影响邮件存储的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-105">Registers to receive notification of specified events that affect the message store.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="f9801-106">参数</span><span class="sxs-lookup"><span data-stu-id="f9801-106">Parameters</span></span>

 <span data-ttu-id="f9801-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="f9801-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="f9801-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="f9801-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="f9801-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="f9801-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="f9801-110">[in]指向有关应生成通知的文件夹或邮件的条目标识符的指针，或 **null**。</span><span class="sxs-lookup"><span data-stu-id="f9801-110">[in] A pointer to the entry identifier of the folder or message about which notifications should be generated, or **null**.</span></span> <span data-ttu-id="f9801-111">如果  _lpEntryID_ 设置为 NULL， **则 Advise** 将注册整个邮件存储上的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-111">If  _lpEntryID_ is set to NULL, **Advise** registers for notifications on the entire message store.</span></span> 
    
 <span data-ttu-id="f9801-112">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="f9801-112">_ulEventMask_</span></span>
  
> <span data-ttu-id="f9801-113">[in]指示调用方感兴趣的通知事件类型且应包含在注册中的值的掩码。</span><span class="sxs-lookup"><span data-stu-id="f9801-113">[in] A mask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="f9801-114">有一个与 [每种](notification.md) 事件类型关联的相应 NOTIFICATION 结构，用于保存有关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="f9801-114">There is a corresponding [NOTIFICATION](notification.md) structure associated with each type of event that holds information about the event.</span></span> <span data-ttu-id="f9801-115">以下是  _ulEventMask_ 参数的有效值：</span><span class="sxs-lookup"><span data-stu-id="f9801-115">The following are valid values for the  _ulEventMask_ parameter:</span></span> 
    
 <span data-ttu-id="f9801-116">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="f9801-116">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="f9801-117">注册有关严重错误（如内存不足）的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-117">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
 <span data-ttu-id="f9801-118">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="f9801-118">_fnevExtended_</span></span>
  
> <span data-ttu-id="f9801-119">注册有关特定于特定邮件存储提供程序的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-119">Registers for notifications about events specific to the particular message store provider.</span></span>
    
 <span data-ttu-id="f9801-120">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="f9801-120">_fnevNewMail_</span></span>
  
> <span data-ttu-id="f9801-121">注册有关新邮件到达的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-121">Registers for notifications about the arrival of new messages.</span></span> 
    
 <span data-ttu-id="f9801-122">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="f9801-122">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="f9801-123">注册有关新建文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-123">Registers for notifications about the creation of a new folder or message.</span></span>
    
 <span data-ttu-id="f9801-124">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="f9801-124">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="f9801-125">注册有关要复制的文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-125">Registers for notifications about a folder or message being copied.</span></span>
    
 <span data-ttu-id="f9801-126">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="f9801-126">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="f9801-127">注册有关要删除的文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-127">Registers for notifications about a folder or message being deleted.</span></span>
    
 <span data-ttu-id="f9801-128">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="f9801-128">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="f9801-129">注册有关要修改的文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-129">Registers for notifications about a folder or message being modified.</span></span>
    
 <span data-ttu-id="f9801-130">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="f9801-130">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="f9801-131">注册有关要移动的文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-131">Registers for notifications about a folder or message being moved.</span></span>
    
 <span data-ttu-id="f9801-132">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="f9801-132">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="f9801-133">注册有关搜索操作完成的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-133">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="f9801-134">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="f9801-134">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="f9801-135">[in]指向通知接收接收对象以接收后续通知的指针。</span><span class="sxs-lookup"><span data-stu-id="f9801-135">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="f9801-136">此通知接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="f9801-136">This advise sink object must have already been allocated.</span></span>
    
 <span data-ttu-id="f9801-137">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="f9801-137">_lpulConnection_</span></span>
  
> <span data-ttu-id="f9801-138">[out]指向非零数字的指针，该数字代表呼叫者的建议接收对象和会话之间的连接。</span><span class="sxs-lookup"><span data-stu-id="f9801-138">[out] A pointer to a nonzero number that represents the connection between the caller's advise sink object and the session.</span></span> 
    
 <span data-ttu-id="f9801-139">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="f9801-139">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="f9801-140">[in]指向通知接收接收对象以接收后续通知的指针。</span><span class="sxs-lookup"><span data-stu-id="f9801-140">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="f9801-141">此通知接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="f9801-141">This advise sink object must have already been allocated.</span></span> 
    
 <span data-ttu-id="f9801-142">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="f9801-142">_lpulConnection_</span></span>
  
> <span data-ttu-id="f9801-143">[out]指向非零连接号的指针，该连接号代表呼叫者的建议接收对象与消息存储之间的连接。</span><span class="sxs-lookup"><span data-stu-id="f9801-143">[out] A pointer to a nonzero connection number that represents the connection between the caller's advise sink object and the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f9801-144">返回值</span><span class="sxs-lookup"><span data-stu-id="f9801-144">Return value</span></span>

<span data-ttu-id="f9801-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9801-145">S_OK</span></span> 
  
> <span data-ttu-id="f9801-146">注册成功。</span><span class="sxs-lookup"><span data-stu-id="f9801-146">The registration was successful.</span></span>
    
<span data-ttu-id="f9801-147">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="f9801-147">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="f9801-148">邮件存储提供程序不支持通过邮件存储注册通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-148">The message store provider does not support registration for notification through the message store.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f9801-149">备注</span><span class="sxs-lookup"><span data-stu-id="f9801-149">Remarks</span></span>

<span data-ttu-id="f9801-150">**IMsgStore：：Advise** 方法在调用方的 advise 接收器对象与邮件存储或邮件存储中的对象之间建立连接。</span><span class="sxs-lookup"><span data-stu-id="f9801-150">The **IMsgStore::Advise** method establishes a connection between the caller's advise sink object and either the message store or an object in the message store.</span></span> <span data-ttu-id="f9801-151">当通知源对象发生  _ulEventMask_ 参数中指定的一个或多个事件时，此连接用于向通知接收器发送通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-151">This connection is used to send notifications to the advise sink when one or more events, as specified in the  _ulEventMask_ parameter, occur to the advise source object.</span></span> <span data-ttu-id="f9801-152">当  _lpEntryID_ 参数指向有效的条目标识符时，建议源是此条目标识符标识的对象。</span><span class="sxs-lookup"><span data-stu-id="f9801-152">When the  _lpEntryID_ parameter points to a valid entry identifier, the advise source is the object identified by this entry identifier.</span></span> <span data-ttu-id="f9801-153">当  _lpEntryID 为_ NULL 时，建议源是邮件存储。</span><span class="sxs-lookup"><span data-stu-id="f9801-153">When  _lpEntryID_ is NULL, the advise source is the message store.</span></span> 
  
<span data-ttu-id="f9801-154">若要发送通知，消息存储提供程序或 MAPI 调用注册的通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="f9801-154">To send a notification, either the message store provider or MAPI calls the registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="f9801-155">通知结构 **OnNotify** 的参数之一包含描述特定事件的信息。</span><span class="sxs-lookup"><span data-stu-id="f9801-155">One of the parameters to **OnNotify**, a notification structure, contains information that describes the specific event.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f9801-156">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="f9801-156">Notes to implementers</span></span>

<span data-ttu-id="f9801-157">在 MAPI 的帮助下，你都可以支持通知，也可以不提供帮助。</span><span class="sxs-lookup"><span data-stu-id="f9801-157">You can support notification with or without help from MAPI.</span></span> <span data-ttu-id="f9801-158">MAPI 具有三种支持对象方法，用于帮助服务提供商实现通知[：IMAPISupport：：Subscribe、IMAPISupport：：Unsubscribe](imapisupport-subscribe.md)和[IMAPISupport：：Notify](imapisupport-notify.md)。 [](imapisupport-unsubscribe.md)</span><span class="sxs-lookup"><span data-stu-id="f9801-158">MAPI has three support object methods for helping service providers implement notification: [IMAPISupport::Subscribe](imapisupport-subscribe.md), [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md), and [IMAPISupport::Notify](imapisupport-notify.md).</span></span> <span data-ttu-id="f9801-159">如果选择使用 MAPI 支持方法，在 **调用 Advise** 方法时调用 **Subscribe** 并释放 _lpAdviseSink_ 指针。</span><span class="sxs-lookup"><span data-stu-id="f9801-159">If you elect to use the MAPI support methods, call **Subscribe** when your **Advise** method is called and release the  _lpAdviseSink_ pointer.</span></span> 
  
<span data-ttu-id="f9801-160">如果选择自己支持通知，请调用 _由 lpAdviseSink_ 参数表示的建议接收器的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法，以保留此指针的副本。</span><span class="sxs-lookup"><span data-stu-id="f9801-160">If you elect to support notification yourself, call the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method of the advise sink represented by the  _lpAdviseSink_ parameter to keep a copy of this pointer.</span></span> <span data-ttu-id="f9801-161">保留此副本，直到 [调用 IMsgStore：：Unadvise](imsgstore-unadvise.md) 方法来取消注册。</span><span class="sxs-lookup"><span data-stu-id="f9801-161">Maintain this copy until your [IMsgStore::Unadvise](imsgstore-unadvise.md) method is called to cancel the registration.</span></span> 
  
<span data-ttu-id="f9801-162">无论您如何支持通知，都将非零连接号分配给通知注册，并将其返回到  _lpulConnection_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="f9801-162">Regardless of how you support notification, assign a nonzero connection number to the notification registration and return it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="f9801-163">在调用 **Unadvise** 并完成之前，不要释放此连接号。</span><span class="sxs-lookup"><span data-stu-id="f9801-163">Do not release this connection number until **Unadvise** has been called and has completed.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f9801-164">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f9801-164">Notes to callers</span></span>

<span data-ttu-id="f9801-165">在支持多个执行线程的系统上， **对 OnNotify** 的调用也随时可以在任何线程上发生。</span><span class="sxs-lookup"><span data-stu-id="f9801-165">On systems that support multiple threads of execution, the call to **OnNotify** can also occur on any thread at any time.</span></span> <span data-ttu-id="f9801-166">如果必须确保通知仅在特定线程上的某个特定时间发生，请调用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数以生成传递给 Advise 的建议接收器 **对象**。</span><span class="sxs-lookup"><span data-stu-id="f9801-166">If you must be assured that notifications occur only at a particular time on a particular thread, call the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to generate the advise sink object that you pass to **Advise**.</span></span> 
  
<span data-ttu-id="f9801-167">在成功调用 **Advise** 之后，在调用 **Unadvise** 以取消注册之前，请准备通知接收器对象以释放。</span><span class="sxs-lookup"><span data-stu-id="f9801-167">After a call to **Advise** has succeeded and before **Unadvise** has been called to cancel the registration, be prepared for the advise sink object to be released.</span></span> <span data-ttu-id="f9801-168">在 Advise 返回后，您应释放通知接收器对象，除非您具有特定的长期用途。</span><span class="sxs-lookup"><span data-stu-id="f9801-168">You should release your advise sink object after **Advise** returns unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="f9801-169">有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="f9801-169">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
<span data-ttu-id="f9801-170">有关处理通知的信息，请参阅处理 [通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="f9801-170">For more information about handling notifications, see [Handling Notifications](handling-notifications.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f9801-171">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f9801-171">MFCMAPI reference</span></span>

<span data-ttu-id="f9801-172">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f9801-172">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f9801-173">**文件**</span><span class="sxs-lookup"><span data-stu-id="f9801-173">**File**</span></span>|<span data-ttu-id="f9801-174">**函数**</span><span class="sxs-lookup"><span data-stu-id="f9801-174">**Function**</span></span>|<span data-ttu-id="f9801-175">**备注**</span><span class="sxs-lookup"><span data-stu-id="f9801-175">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f9801-176">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="f9801-176">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="f9801-177">CBaseDialog：：OnNotificationsOn</span><span class="sxs-lookup"><span data-stu-id="f9801-177">CBaseDialog::OnNotificationsOn</span></span>  <br/> |<span data-ttu-id="f9801-178">MFCMAPI 使用 **IMsgStore：：Advise** 方法注册整个邮件存储上的通知。</span><span class="sxs-lookup"><span data-stu-id="f9801-178">MFCMAPI uses the **IMsgStore::Advise** method to register for notifications on the entire message store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f9801-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9801-179">See also</span></span>



[<span data-ttu-id="f9801-180">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="f9801-180">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="f9801-181">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="f9801-181">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="f9801-182">IMsgStore::Unadvise</span><span class="sxs-lookup"><span data-stu-id="f9801-182">IMsgStore::Unadvise</span></span>](imsgstore-unadvise.md)
  
[<span data-ttu-id="f9801-183">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="f9801-183">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="f9801-184">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="f9801-184">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="f9801-185">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f9801-185">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

