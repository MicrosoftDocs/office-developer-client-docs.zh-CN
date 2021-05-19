---
title: IMAPISessionAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Advise
api_type:
- COM
ms.assetid: a6a6b6b1-31e2-4899-a5fe-74d5d1c2ccfc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d5d87d7be9cb3524445107e975a298d4afd5bf98
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419833"
---
# <a name="imapisessionadvise"></a><span data-ttu-id="d3773-103">IMAPISession::Advise</span><span class="sxs-lookup"><span data-stu-id="d3773-103">IMAPISession::Advise</span></span>

  
  
<span data-ttu-id="d3773-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3773-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3773-105">注册以接收影响会话的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-105">Registers to receive notification of specified events that affect the session.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="d3773-106">参数</span><span class="sxs-lookup"><span data-stu-id="d3773-106">Parameters</span></span>

 <span data-ttu-id="d3773-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="d3773-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="d3773-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="d3773-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="d3773-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="d3773-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="d3773-110">[in]指向有关应生成通知的通讯簿或邮件存储对象的条目标识符的指针或 NULL，指示客户端正在注册以接收有关仅影响会话的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-110">[in] A pointer to the entry identifier of the address book or message store object about which notifications should be generated, or NULL, which indicates that the client is registering to receive notifications about events that affect only the session.</span></span> 
    
 <span data-ttu-id="d3773-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="d3773-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="d3773-112">[in]指示客户端感兴趣的通知事件类型且应包含在注册中的值的掩码。</span><span class="sxs-lookup"><span data-stu-id="d3773-112">[in] A mask of values that indicate the types of notification events that the client is interested in and should be included in the registration.</span></span> <span data-ttu-id="d3773-113">如果  _lpEntryID_ 为 NULL，MAPI 会自动为仅影响会话的关键错误事件注册客户端。</span><span class="sxs-lookup"><span data-stu-id="d3773-113">If  _lpEntryID_ is NULL, MAPI automatically registers the client for critical error events that affect only the session.</span></span> <span data-ttu-id="d3773-114">当  _lpEntryID_ 指向条目标识符时，以下值对  _ulEventMask_ 参数有效：</span><span class="sxs-lookup"><span data-stu-id="d3773-114">When  _lpEntryID_ points to an entry identifier, the following values are valid for the  _ulEventMask_ parameter:</span></span> 
    
<span data-ttu-id="d3773-115">fnevCriticalError</span><span class="sxs-lookup"><span data-stu-id="d3773-115">fnevCriticalError</span></span> 
  
> <span data-ttu-id="d3773-116">注册有关严重错误（如内存不足）的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-116">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
<span data-ttu-id="d3773-117">fnevExtended</span><span class="sxs-lookup"><span data-stu-id="d3773-117">fnevExtended</span></span> 
  
> <span data-ttu-id="d3773-118">注册有关特定于特定通讯簿或邮件存储提供程序的事件以及会话关闭的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-118">Registers for notifications about events specific to a particular address book or message store provider and about session shut down.</span></span>
    
<span data-ttu-id="d3773-119">fnevNewMail</span><span class="sxs-lookup"><span data-stu-id="d3773-119">fnevNewMail</span></span> 
  
> <span data-ttu-id="d3773-120">注册有关新邮件到达的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-120">Registers for notifications about the arrival of new messages.</span></span> 
    
<span data-ttu-id="d3773-121">fnevObjectCreated</span><span class="sxs-lookup"><span data-stu-id="d3773-121">fnevObjectCreated</span></span> 
  
> <span data-ttu-id="d3773-122">注册有关新建对象的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-122">Registers for notifications about the creation of a new object.</span></span>
    
<span data-ttu-id="d3773-123">fnevObjectCopied</span><span class="sxs-lookup"><span data-stu-id="d3773-123">fnevObjectCopied</span></span>
  
> <span data-ttu-id="d3773-124">注册有关正在复制的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-124">Registers for notifications about an object being copied.</span></span>
    
<span data-ttu-id="d3773-125">fnevObjectDeleted</span><span class="sxs-lookup"><span data-stu-id="d3773-125">fnevObjectDeleted</span></span>
  
> <span data-ttu-id="d3773-126">注册有关要删除的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-126">Registers for notifications about an object being deleted.</span></span>
    
<span data-ttu-id="d3773-127">fnevObjectModified</span><span class="sxs-lookup"><span data-stu-id="d3773-127">fnevObjectModified</span></span>
  
> <span data-ttu-id="d3773-128">注册有关要修改的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-128">Registers for notifications about an object being modified.</span></span>
    
<span data-ttu-id="d3773-129">fnevObjectMoved</span><span class="sxs-lookup"><span data-stu-id="d3773-129">fnevObjectMoved</span></span>
  
> <span data-ttu-id="d3773-130">注册有关要移动的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-130">Registers for notifications about an object being moved.</span></span>
    
<span data-ttu-id="d3773-131">fnevSearchComplete</span><span class="sxs-lookup"><span data-stu-id="d3773-131">fnevSearchComplete</span></span>
  
> <span data-ttu-id="d3773-132">注册有关搜索操作完成的通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-132">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="d3773-133">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="d3773-133">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="d3773-134">[in]指向通知接收接收对象以接收后续通知的指针。</span><span class="sxs-lookup"><span data-stu-id="d3773-134">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="d3773-135">此通知接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="d3773-135">This advise sink object must have already been allocated.</span></span>
    
 <span data-ttu-id="d3773-136">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="d3773-136">_lpulConnection_</span></span>
  
> <span data-ttu-id="d3773-137">[out]指向非零数字的指针，该数字代表呼叫者的建议接收对象和会话之间的连接。</span><span class="sxs-lookup"><span data-stu-id="d3773-137">[out] A pointer to a nonzero number that represents the connection between the caller's advise sink object and the session.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d3773-138">返回值</span><span class="sxs-lookup"><span data-stu-id="d3773-138">Return value</span></span>

<span data-ttu-id="d3773-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3773-139">S_OK</span></span> 
  
> <span data-ttu-id="d3773-140">注册成功。</span><span class="sxs-lookup"><span data-stu-id="d3773-140">The registration was successful.</span></span>
    
<span data-ttu-id="d3773-141">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d3773-141">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="d3773-142">_lpEntryID_ 指向的条目标识符不表示有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d3773-142">The entry identifier pointed to by  _lpEntryID_ does not represent a valid entry identifier.</span></span> 
    
<span data-ttu-id="d3773-143">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d3773-143">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="d3773-144">负责  _lpEntryID_ 指向的条目标识符的服务提供商要么不支持  _ulEventMask_ 参数中指定的事件类型，要么不支持通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-144">The service provider responsible for the entry identifier pointed to by  _lpEntryID_ either does not support the type of events specified in the  _ulEventMask_ parameter or does not support notification.</span></span> 
    
<span data-ttu-id="d3773-145">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d3773-145">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="d3773-146">_lpEntryID_ 指向的条目标识符无法由配置文件中的任一服务提供商处理。</span><span class="sxs-lookup"><span data-stu-id="d3773-146">The entry identifier pointed to by  _lpEntryID_ cannot be handled by any of the service providers in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d3773-147">备注</span><span class="sxs-lookup"><span data-stu-id="d3773-147">Remarks</span></span>

<span data-ttu-id="d3773-148">**IMAPISession：：Advise** 方法在调用方的 advise 接收器对象、会话和（可选）服务提供商之间建立连接。</span><span class="sxs-lookup"><span data-stu-id="d3773-148">The **IMAPISession::Advise** method establishes a connection between the caller's advise sink object, the session and, optionally, a service provider.</span></span> <span data-ttu-id="d3773-149">当  _ulEventMask_ 参数中指定的一个或多个事件发生到  _lpEntryID_ 指向的对象时，此连接用于向通知接收器发送通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-149">This connection is used to send notifications to the advise sink when one or more events specified in the  _ulEventMask_ parameter occur to the object pointed to by  _lpEntryID_.</span></span> <span data-ttu-id="d3773-150">当  _lpEntryID 为_ NULL 时，目标对象为会话，并且仅针对关键错误和扩展事件发送通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-150">When  _lpEntryID_ is NULL, the target object is the session and notifications are sent only for critical errors and extended events.</span></span> 
  
<span data-ttu-id="d3773-151">当  _lpEntryID_ 指向有效的条目标识符时，MAPI 将调用属于负责服务提供商的登录对象的 **Advise** 方法。</span><span class="sxs-lookup"><span data-stu-id="d3773-151">When  _lpEntryID_ points to a valid entry identifier, MAPI calls the **Advise** method of the logon object that belongs to the responsible service provider.</span></span> <span data-ttu-id="d3773-152">例如，如果  _lpEntryID_ 指向通讯组列表的条目标识符，MAPI 将调用相应的通讯簿提供程序的 [IABLogon：：Advise](iablogon-advise.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="d3773-152">For example, if  _lpEntryID_ points to the entry identifier of a distribution list, MAPI calls the appropriate address book provider's [IABLogon::Advise](iablogon-advise.md) method.</span></span> 
  
<span data-ttu-id="d3773-153">若要发送通知，服务提供商或 MAPI 调用注册的通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="d3773-153">To send a notification, either the service provider or MAPI calls the registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="d3773-154">通知结构 **OnNotify** 的参数之一包含描述特定事件的信息。</span><span class="sxs-lookup"><span data-stu-id="d3773-154">One of the parameters to **OnNotify**, a notification structure, contains information that describes the specific event.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="d3773-155">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d3773-155">Notes to callers</span></span>

<span data-ttu-id="d3773-156">在支持多个执行线程的系统上， **对 OnNotify** 的调用也随时可以在任何线程上发生。</span><span class="sxs-lookup"><span data-stu-id="d3773-156">On systems that support multiple threads of execution, the call to **OnNotify** can also occur on any thread at any time.</span></span> <span data-ttu-id="d3773-157">如果你需要保证通知将仅在特定线程上的某个特定时间发生，请调用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数以生成传递给 **Advise** 方法的建议接收器对象。</span><span class="sxs-lookup"><span data-stu-id="d3773-157">If you need assurance that notifications will occur only at a particular time on a particular thread, call the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to generate the advise sink object that you pass to the **Advise** method.</span></span> 
  
<span data-ttu-id="d3773-158">若要确定客户端何时注销，请通过调用 _lpEntryID_ 设置为 NULL 且 _cbEntryID_ 设置为 0 的 **Advise** 在服务提供商中注册通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-158">To determine when a client has logged off, register for notifications in your service provider by calling **Advise** with  _lpEntryID_ set to NULL and  _cbEntryID_ set to 0.</span></span> <span data-ttu-id="d3773-159">注销时，你将收到 fnevExtended 通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-159">When the logoff occurs, you will receive an fnevExtended notification.</span></span> 
  
<span data-ttu-id="d3773-160">在成功调用 **Advise** 之后，在 [调用 IMAPISession：：Unadvise](imapisession-unadvise.md) 以取消注册之前，请释放通知接收器对象，除非你具有特定的长期用途。</span><span class="sxs-lookup"><span data-stu-id="d3773-160">After a call to **Advise** has succeeded and before [IMAPISession::Unadvise](imapisession-unadvise.md) has been called to cancel the registration, release your advise sink object unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="d3773-161">有关通知过程的概述，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="d3773-161">For an overview of the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
<span data-ttu-id="d3773-162">有关处理通知的信息，请参阅处理 [通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="d3773-162">For more information about handling notifications, see [Handling Notifications](handling-notifications.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d3773-163">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="d3773-163">MFCMAPI reference</span></span>

<span data-ttu-id="d3773-164">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d3773-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d3773-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="d3773-165">**File**</span></span>|<span data-ttu-id="d3773-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="d3773-166">**Function**</span></span>|<span data-ttu-id="d3773-167">**备注**</span><span class="sxs-lookup"><span data-stu-id="d3773-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3773-168">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="d3773-168">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="d3773-169">CBaseDialog：：OnNotificationsOn</span><span class="sxs-lookup"><span data-stu-id="d3773-169">CBaseDialog::OnNotificationsOn</span></span>  <br/> |<span data-ttu-id="d3773-170">MFCMAPI 使用 **IMAPISession：：Advise** 方法针对会话注册通知。</span><span class="sxs-lookup"><span data-stu-id="d3773-170">MFCMAPI uses the **IMAPISession::Advise** method to register for notifications against the session.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d3773-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3773-171">See also</span></span>



[<span data-ttu-id="d3773-172">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="d3773-172">IABLogon::Advise</span></span>](iablogon-advise.md)
  
[<span data-ttu-id="d3773-173">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="d3773-173">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="d3773-174">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="d3773-174">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="d3773-175">IMAPISession::Unadvise</span><span class="sxs-lookup"><span data-stu-id="d3773-175">IMAPISession::Unadvise</span></span>](imapisession-unadvise.md)
  
[<span data-ttu-id="d3773-176">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d3773-176">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="d3773-177">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d3773-177">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="d3773-178">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="d3773-178">Event Notification in MAPI</span></span>](event-notification-in-mapi.md)

