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
ms.openlocfilehash: 6a315cef8263f7e241a815a0f054dc3174d88fa7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775858"
---
# <a name="imsgstoreadvise"></a><span data-ttu-id="b4a22-103">IMsgStore::Advise</span><span class="sxs-lookup"><span data-stu-id="b4a22-103">IMsgStore::Advise</span></span>

  
  
<span data-ttu-id="b4a22-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b4a22-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b4a22-105">注册接收影响消息存储库的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="b4a22-105">Registers to receive notification of specified events that affect the message store.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="b4a22-106">参数</span><span class="sxs-lookup"><span data-stu-id="b4a22-106">Parameters</span></span>

 <span data-ttu-id="b4a22-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="b4a22-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="b4a22-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="b4a22-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="b4a22-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="b4a22-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="b4a22-110">[in]指向有关应生成的通知，则为**null**的邮件的文件夹的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b4a22-110">[in] A pointer to the entry identifier of the folder or message about which notifications should be generated, or **null**.</span></span> <span data-ttu-id="b4a22-111">如果_lpEntryID_设置为 NULL， **Advise**注册整个邮件存储区上的通知。</span><span class="sxs-lookup"><span data-stu-id="b4a22-111">If  _lpEntryID_ is set to NULL, **Advise** registers for notifications on the entire message store.</span></span> 
    
 <span data-ttu-id="b4a22-112">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="b4a22-112">_ulEventMask_</span></span>
  
> <span data-ttu-id="b4a22-113">[in]指示呼叫者感兴趣，并应包含在注册通知事件的类型的值的掩码。</span><span class="sxs-lookup"><span data-stu-id="b4a22-113">[in] A mask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="b4a22-114">没有相应的[通知](notification.md)结构，每种类型的包含有关事件的信息的事件相关联。</span><span class="sxs-lookup"><span data-stu-id="b4a22-114">There is a corresponding [NOTIFICATION](notification.md) structure associated with each type of event that holds information about the event.</span></span> <span data-ttu-id="b4a22-115">_UlEventMask_参数的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="b4a22-115">The following are valid values for the  _ulEventMask_ parameter:</span></span> 
    
 <span data-ttu-id="b4a22-116">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="b4a22-116">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="b4a22-117">有关严重错误，例如内存不足通知注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-117">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
 <span data-ttu-id="b4a22-118">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="b4a22-118">_fnevExtended_</span></span>
  
> <span data-ttu-id="b4a22-119">有关特定于特定邮件的事件通知的 register 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="b4a22-119">Registers for notifications about events specific to the particular message store provider.</span></span>
    
 <span data-ttu-id="b4a22-120">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="b4a22-120">_fnevNewMail_</span></span>
  
> <span data-ttu-id="b4a22-121">有关新邮件的到达通知注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-121">Registers for notifications about the arrival of new messages.</span></span> 
    
 <span data-ttu-id="b4a22-122">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="b4a22-122">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="b4a22-123">有关创建新文件夹或消息的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-123">Registers for notifications about the creation of a new folder or message.</span></span>
    
 <span data-ttu-id="b4a22-124">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="b4a22-124">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="b4a22-125">有关文件夹或复制的消息的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-125">Registers for notifications about a folder or message being copied.</span></span>
    
 <span data-ttu-id="b4a22-126">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="b4a22-126">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="b4a22-127">有关文件夹或正在删除的消息的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-127">Registers for notifications about a folder or message being deleted.</span></span>
    
 <span data-ttu-id="b4a22-128">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="b4a22-128">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="b4a22-129">有关文件夹或要修改的消息的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-129">Registers for notifications about a folder or message being modified.</span></span>
    
 <span data-ttu-id="b4a22-130">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="b4a22-130">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="b4a22-131">有关文件夹或要移动的消息的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-131">Registers for notifications about a folder or message being moved.</span></span>
    
 <span data-ttu-id="b4a22-132">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="b4a22-132">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="b4a22-133">有关搜索操作完成通知注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-133">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="b4a22-134">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="b4a22-134">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="b4a22-135">[in]指向要接收随后进行通知 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b4a22-135">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="b4a22-136">此 advise 接收器对象必须具有已分配。</span><span class="sxs-lookup"><span data-stu-id="b4a22-136">This advise sink object must have already been allocated.</span></span>
    
 <span data-ttu-id="b4a22-137">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="b4a22-137">_lpulConnection_</span></span>
  
> <span data-ttu-id="b4a22-138">[输出]为非零值，该值代表呼叫者之间的连接数的指针建议接收器对象和会话。</span><span class="sxs-lookup"><span data-stu-id="b4a22-138">[out] A pointer to a nonzero number that represents the connection between the caller's advise sink object and the session.</span></span> 
    
 <span data-ttu-id="b4a22-139">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="b4a22-139">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="b4a22-140">[in]指向要接收随后进行通知 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b4a22-140">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="b4a22-141">此 advise 接收器对象必须具有已分配。</span><span class="sxs-lookup"><span data-stu-id="b4a22-141">This advise sink object must have already been allocated.</span></span> 
    
 <span data-ttu-id="b4a22-142">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="b4a22-142">_lpulConnection_</span></span>
  
> <span data-ttu-id="b4a22-143">[输出]为非零值的连接数表示呼叫者之间的连接的指针建议接收器对象和消息存储。</span><span class="sxs-lookup"><span data-stu-id="b4a22-143">[out] A pointer to a nonzero connection number that represents the connection between the caller's advise sink object and the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b4a22-144">返回值</span><span class="sxs-lookup"><span data-stu-id="b4a22-144">Return value</span></span>

<span data-ttu-id="b4a22-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4a22-145">S_OK</span></span> 
  
> <span data-ttu-id="b4a22-146">注册成功。</span><span class="sxs-lookup"><span data-stu-id="b4a22-146">The registration was successful.</span></span>
    
<span data-ttu-id="b4a22-147">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b4a22-147">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="b4a22-148">消息存储提供程序不支持的通知消息存储通过注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-148">The message store provider does not support registration for notification through the message store.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b4a22-149">说明</span><span class="sxs-lookup"><span data-stu-id="b4a22-149">Remarks</span></span>

<span data-ttu-id="b4a22-150">**IMsgStore::Advise**方法建立呼叫者之间的连接的建议接收器对象和消息存储库或消息存储库中的对象。</span><span class="sxs-lookup"><span data-stu-id="b4a22-150">The **IMsgStore::Advise** method establishes a connection between the caller's advise sink object and either the message store or an object in the message store.</span></span> <span data-ttu-id="b4a22-151">此连接用于将通知发送到通知接收器当一个或多个事件， _ulEventMask_参数中指定发生 advise 源对象。</span><span class="sxs-lookup"><span data-stu-id="b4a22-151">This connection is used to send notifications to the advise sink when one or more events, as specified in the  _ulEventMask_ parameter, occur to the advise source object.</span></span> <span data-ttu-id="b4a22-152">当_lpEntryID_参数指向的有效条目标识符，advise 源是由此条目标识符标识的对象。</span><span class="sxs-lookup"><span data-stu-id="b4a22-152">When the  _lpEntryID_ parameter points to a valid entry identifier, the advise source is the object identified by this entry identifier.</span></span> <span data-ttu-id="b4a22-153">_LpEntryID_为 NULL，advise 源时消息存储库。</span><span class="sxs-lookup"><span data-stu-id="b4a22-153">When  _lpEntryID_ is NULL, the advise source is the message store.</span></span> 
  
<span data-ttu-id="b4a22-154">发送通知，消息存储提供程序或 MAPI 调用注册的通知接收器的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b4a22-154">To send a notification, either the message store provider or MAPI calls the registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="b4a22-155">向**OnNotify**，通知结构参数之一包含介绍特定事件的信息。</span><span class="sxs-lookup"><span data-stu-id="b4a22-155">One of the parameters to **OnNotify**, a notification structure, contains information that describes the specific event.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="b4a22-156">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="b4a22-156">Notes to implementers</span></span>

<span data-ttu-id="b4a22-157">您可以支持使用或不从 MAPI 帮助的通知。</span><span class="sxs-lookup"><span data-stu-id="b4a22-157">You can support notification with or without help from MAPI.</span></span> <span data-ttu-id="b4a22-158">MAPI 具有三个帮助服务提供商实现通知的支持对象方法： [IMAPISupport::Subscribe](imapisupport-subscribe.md)、 [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)和[IMAPISupport::Notify](imapisupport-notify.md)。</span><span class="sxs-lookup"><span data-stu-id="b4a22-158">MAPI has three support object methods for helping service providers implement notification: [IMAPISupport::Subscribe](imapisupport-subscribe.md), [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md), and [IMAPISupport::Notify](imapisupport-notify.md).</span></span> <span data-ttu-id="b4a22-159">如果您选择使用 MAPI 支持方法，调用**Advise**方法时调用**Subscribe**和释放_lpAdviseSink_指针。</span><span class="sxs-lookup"><span data-stu-id="b4a22-159">If you elect to use the MAPI support methods, call **Subscribe** when your **Advise** method is called and release the  _lpAdviseSink_ pointer.</span></span> 
  
<span data-ttu-id="b4a22-160">如果您选择自己支持通知，呼叫通知接收器由_lpAdviseSink_参数保留一份此指针的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="b4a22-160">If you elect to support notification yourself, call the [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx) method of the advise sink represented by the  _lpAdviseSink_ parameter to keep a copy of this pointer.</span></span> <span data-ttu-id="b4a22-161">维护此副本，直到您[IMsgStore::Unadvise](imsgstore-unadvise.md)方法调用取消注册。</span><span class="sxs-lookup"><span data-stu-id="b4a22-161">Maintain this copy until your [IMsgStore::Unadvise](imsgstore-unadvise.md) method is called to cancel the registration.</span></span> 
  
<span data-ttu-id="b4a22-162">无论如何支持通知，分配给通知注册的非零值的连接数并返回_lpulConnection_参数中。</span><span class="sxs-lookup"><span data-stu-id="b4a22-162">Regardless of how you support notification, assign a nonzero connection number to the notification registration and return it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="b4a22-163">直到**Unadvise**已调用，并且已完成，则不释放此连接数。</span><span class="sxs-lookup"><span data-stu-id="b4a22-163">Do not release this connection number until **Unadvise** has been called and has completed.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b4a22-164">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b4a22-164">Notes to callers</span></span>

<span data-ttu-id="b4a22-165">支持多个线程的执行系统，在调用**OnNotify**也会发生任何线程上随时。</span><span class="sxs-lookup"><span data-stu-id="b4a22-165">On systems that support multiple threads of execution, the call to **OnNotify** can also occur on any thread at any time.</span></span> <span data-ttu-id="b4a22-166">如果您必须确保仅在特定时间在特定的线程上发生通知，调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数生成传递给**Advise**advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="b4a22-166">If you must be assured that notifications occur only at a particular time on a particular thread, call the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to generate the advise sink object that you pass to **Advise**.</span></span> 
  
<span data-ttu-id="b4a22-167">后调用**Advise**已经完成并且在调用**Unadvise**取消注册之前，先为 advise 接收器对象，必须释放准备。</span><span class="sxs-lookup"><span data-stu-id="b4a22-167">After a call to **Advise** has succeeded and before **Unadvise** has been called to cancel the registration, be prepared for the advise sink object to be released.</span></span> <span data-ttu-id="b4a22-168">**Advise**返回除非您有特定的长期使用为其后，您应释放 advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="b4a22-168">You should release your advise sink object after **Advise** returns unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="b4a22-169">有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="b4a22-169">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
<span data-ttu-id="b4a22-170">有关处理通知的详细信息，请参阅[处理通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="b4a22-170">For more information about handling notifications, see [Handling Notifications](handling-notifications.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b4a22-171">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="b4a22-171">MFCMAPI reference</span></span>

<span data-ttu-id="b4a22-172">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b4a22-172">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b4a22-173">**文件**</span><span class="sxs-lookup"><span data-stu-id="b4a22-173">**File**</span></span>|<span data-ttu-id="b4a22-174">**函数**</span><span class="sxs-lookup"><span data-stu-id="b4a22-174">**Function**</span></span>|<span data-ttu-id="b4a22-175">**Comment**</span><span class="sxs-lookup"><span data-stu-id="b4a22-175">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4a22-176">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="b4a22-176">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="b4a22-177">CBaseDialog::OnNotificationsOn</span><span class="sxs-lookup"><span data-stu-id="b4a22-177">CBaseDialog::OnNotificationsOn</span></span>  <br/> |<span data-ttu-id="b4a22-178">MFCMAPI 使用**IMsgStore::Advise**方法注册整个邮件存储区上的通知。</span><span class="sxs-lookup"><span data-stu-id="b4a22-178">MFCMAPI uses the **IMsgStore::Advise** method to register for notifications on the entire message store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b4a22-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4a22-179">See also</span></span>



[<span data-ttu-id="b4a22-180">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="b4a22-180">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="b4a22-181">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="b4a22-181">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="b4a22-182">IMsgStore::Unadvise</span><span class="sxs-lookup"><span data-stu-id="b4a22-182">IMsgStore::Unadvise</span></span>](imsgstore-unadvise.md)
  
[<span data-ttu-id="b4a22-183">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="b4a22-183">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="b4a22-184">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b4a22-184">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="b4a22-185">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b4a22-185">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

