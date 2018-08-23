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
ms.openlocfilehash: 704a556b97f5fd90989641a17afe5a11d127e51b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577168"
---
# <a name="imapisessionadvise"></a><span data-ttu-id="b8a52-103">IMAPISession::Advise</span><span class="sxs-lookup"><span data-stu-id="b8a52-103">IMAPISession::Advise</span></span>

  
  
<span data-ttu-id="b8a52-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b8a52-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b8a52-105">注册接收影响会话的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="b8a52-105">Registers to receive notification of specified events that affect the session.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="b8a52-106">参数</span><span class="sxs-lookup"><span data-stu-id="b8a52-106">Parameters</span></span>

 <span data-ttu-id="b8a52-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="b8a52-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="b8a52-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="b8a52-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="b8a52-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="b8a52-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="b8a52-110">[in]指向通讯簿有关哪些应生成通知，消息存储对象或空值，指示客户端注册接收有关影响只对会话的事件通知的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b8a52-110">[in] A pointer to the entry identifier of the address book or message store object about which notifications should be generated, or NULL, which indicates that the client is registering to receive notifications about events that affect only the session.</span></span> 
    
 <span data-ttu-id="b8a52-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="b8a52-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="b8a52-112">[in]指示在客户端有兴趣和应包含在注册的通知事件的类型的值的掩码。</span><span class="sxs-lookup"><span data-stu-id="b8a52-112">[in] A mask of values that indicate the types of notification events that the client is interested in and should be included in the registration.</span></span> <span data-ttu-id="b8a52-113">如果_lpEntryID_为 NULL，则 MAPI 自动注册影响只对会话的严重错误事件的客户端。</span><span class="sxs-lookup"><span data-stu-id="b8a52-113">If  _lpEntryID_ is NULL, MAPI automatically registers the client for critical error events that affect only the session.</span></span> <span data-ttu-id="b8a52-114">当_lpEntryID_指向条目标识符时，以下是有效值_ulEventMask_参数：</span><span class="sxs-lookup"><span data-stu-id="b8a52-114">When  _lpEntryID_ points to an entry identifier, the following values are valid for the  _ulEventMask_ parameter:</span></span> 
    
<span data-ttu-id="b8a52-115">fnevCriticalError</span><span class="sxs-lookup"><span data-stu-id="b8a52-115">fnevCriticalError</span></span> 
  
> <span data-ttu-id="b8a52-116">有关严重错误，例如内存不足通知注册。</span><span class="sxs-lookup"><span data-stu-id="b8a52-116">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
<span data-ttu-id="b8a52-117">fnevExtended</span><span class="sxs-lookup"><span data-stu-id="b8a52-117">fnevExtended</span></span> 
  
> <span data-ttu-id="b8a52-118">有关特定于特定的通讯簿或消息的事件通知的 register 存储提供程序和有关会话关闭。</span><span class="sxs-lookup"><span data-stu-id="b8a52-118">Registers for notifications about events specific to a particular address book or message store provider and about session shut down.</span></span>
    
<span data-ttu-id="b8a52-119">fnevNewMail</span><span class="sxs-lookup"><span data-stu-id="b8a52-119">fnevNewMail</span></span> 
  
> <span data-ttu-id="b8a52-120">有关新邮件的到达通知注册。</span><span class="sxs-lookup"><span data-stu-id="b8a52-120">Registers for notifications about the arrival of new messages.</span></span> 
    
<span data-ttu-id="b8a52-121">fnevObjectCreated</span><span class="sxs-lookup"><span data-stu-id="b8a52-121">fnevObjectCreated</span></span> 
  
> <span data-ttu-id="b8a52-122">有关创建新对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b8a52-122">Registers for notifications about the creation of a new object.</span></span>
    
<span data-ttu-id="b8a52-123">fnevObjectCopied</span><span class="sxs-lookup"><span data-stu-id="b8a52-123">fnevObjectCopied</span></span>
  
> <span data-ttu-id="b8a52-124">有关要复制的对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b8a52-124">Registers for notifications about an object being copied.</span></span>
    
<span data-ttu-id="b8a52-125">fnevObjectDeleted</span><span class="sxs-lookup"><span data-stu-id="b8a52-125">fnevObjectDeleted</span></span>
  
> <span data-ttu-id="b8a52-126">有关对象正在删除通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b8a52-126">Registers for notifications about an object being deleted.</span></span>
    
<span data-ttu-id="b8a52-127">fnevObjectModified</span><span class="sxs-lookup"><span data-stu-id="b8a52-127">fnevObjectModified</span></span>
  
> <span data-ttu-id="b8a52-128">有关修改对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="b8a52-128">Registers for notifications about an object being modified.</span></span>
    
<span data-ttu-id="b8a52-129">fnevObjectMoved</span><span class="sxs-lookup"><span data-stu-id="b8a52-129">fnevObjectMoved</span></span>
  
> <span data-ttu-id="b8a52-130">有关被移动对象通知注册。</span><span class="sxs-lookup"><span data-stu-id="b8a52-130">Registers for notifications about an object being moved.</span></span>
    
<span data-ttu-id="b8a52-131">fnevSearchComplete</span><span class="sxs-lookup"><span data-stu-id="b8a52-131">fnevSearchComplete</span></span>
  
> <span data-ttu-id="b8a52-132">有关搜索操作完成通知注册。</span><span class="sxs-lookup"><span data-stu-id="b8a52-132">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="b8a52-133">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="b8a52-133">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="b8a52-134">[in]指向要接收随后进行通知 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b8a52-134">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="b8a52-135">此 advise 接收器对象必须具有已分配。</span><span class="sxs-lookup"><span data-stu-id="b8a52-135">This advise sink object must have already been allocated.</span></span>
    
 <span data-ttu-id="b8a52-136">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="b8a52-136">_lpulConnection_</span></span>
  
> <span data-ttu-id="b8a52-137">[输出]为非零值，该值代表呼叫者之间的连接数的指针建议接收器对象和会话。</span><span class="sxs-lookup"><span data-stu-id="b8a52-137">[out] A pointer to a nonzero number that represents the connection between the caller's advise sink object and the session.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b8a52-138">返回值</span><span class="sxs-lookup"><span data-stu-id="b8a52-138">Return value</span></span>

<span data-ttu-id="b8a52-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8a52-139">S_OK</span></span> 
  
> <span data-ttu-id="b8a52-140">注册成功。</span><span class="sxs-lookup"><span data-stu-id="b8a52-140">The registration was successful.</span></span>
    
<span data-ttu-id="b8a52-141">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="b8a52-141">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="b8a52-142">由_lpEntryID_指向的项标识符不代表一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="b8a52-142">The entry identifier pointed to by  _lpEntryID_ does not represent a valid entry identifier.</span></span> 
    
<span data-ttu-id="b8a52-143">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b8a52-143">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="b8a52-144">负责所指的_lpEntryID_的项标识符的服务提供程序不支持的_ulEventMask_参数中指定的事件类型，或不支持通知。</span><span class="sxs-lookup"><span data-stu-id="b8a52-144">The service provider responsible for the entry identifier pointed to by  _lpEntryID_ either does not support the type of events specified in the  _ulEventMask_ parameter or does not support notification.</span></span> 
    
<span data-ttu-id="b8a52-145">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="b8a52-145">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="b8a52-146">配置文件中的服务提供程序的任何无法处理由_lpEntryID_指向的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b8a52-146">The entry identifier pointed to by  _lpEntryID_ cannot be handled by any of the service providers in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b8a52-147">注解</span><span class="sxs-lookup"><span data-stu-id="b8a52-147">Remarks</span></span>

<span data-ttu-id="b8a52-148">**IMAPISession::Advise**方法建立呼叫者之间的连接的建议接收器对象，该会话和 （可选） 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="b8a52-148">The **IMAPISession::Advise** method establishes a connection between the caller's advise sink object, the session and, optionally, a service provider.</span></span> <span data-ttu-id="b8a52-149">此连接用于将通知发送到通知接收器一种或_ulEventMask_参数中指定的多个事件发生指向_lpEntryID_对象。</span><span class="sxs-lookup"><span data-stu-id="b8a52-149">This connection is used to send notifications to the advise sink when one or more events specified in the  _ulEventMask_ parameter occur to the object pointed to by  _lpEntryID_.</span></span> <span data-ttu-id="b8a52-150">如果_lpEntryID_为 NULL，目标对象为会话，并仅为严重错误和扩展的事件发送通知。</span><span class="sxs-lookup"><span data-stu-id="b8a52-150">When  _lpEntryID_ is NULL, the target object is the session and notifications are sent only for critical errors and extended events.</span></span> 
  
<span data-ttu-id="b8a52-151">当_lpEntryID_指向有效项标识符时，MAPI 调用登录对象属于负责服务提供商的**Advise**方法。</span><span class="sxs-lookup"><span data-stu-id="b8a52-151">When  _lpEntryID_ points to a valid entry identifier, MAPI calls the **Advise** method of the logon object that belongs to the responsible service provider.</span></span> <span data-ttu-id="b8a52-152">例如，如果_lpEntryID_指向通讯组列表的项标识符，MAPI 将调用相应的通讯簿提供程序的[IABLogon::Advise](iablogon-advise.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b8a52-152">For example, if  _lpEntryID_ points to the entry identifier of a distribution list, MAPI calls the appropriate address book provider's [IABLogon::Advise](iablogon-advise.md) method.</span></span> 
  
<span data-ttu-id="b8a52-153">发送通知，服务提供商或 MAPI 调用注册的通知接收器的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b8a52-153">To send a notification, either the service provider or MAPI calls the registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="b8a52-154">向**OnNotify**，通知结构参数之一包含介绍特定事件的信息。</span><span class="sxs-lookup"><span data-stu-id="b8a52-154">One of the parameters to **OnNotify**, a notification structure, contains information that describes the specific event.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="b8a52-155">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b8a52-155">Notes to callers</span></span>

<span data-ttu-id="b8a52-156">支持多个线程的执行系统，在调用**OnNotify**也会发生任何线程上随时。</span><span class="sxs-lookup"><span data-stu-id="b8a52-156">On systems that support multiple threads of execution, the call to **OnNotify** can also occur on any thread at any time.</span></span> <span data-ttu-id="b8a52-157">如果您需要保证通知会发生仅在特定时间上特定线程，调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数生成 advise 接收器对象传递给**Advise**方法。</span><span class="sxs-lookup"><span data-stu-id="b8a52-157">If you need assurance that notifications will occur only at a particular time on a particular thread, call the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to generate the advise sink object that you pass to the **Advise** method.</span></span> 
  
<span data-ttu-id="b8a52-158">若要确定客户端已注销时，请通过_lpEntryID_设置为 NULL 和_cbEntryID_设置为 0 与调用**Advise**注册中服务提供商的通知。</span><span class="sxs-lookup"><span data-stu-id="b8a52-158">To determine when a client has logged off, register for notifications in your service provider by calling **Advise** with  _lpEntryID_ set to NULL and  _cbEntryID_ set to 0.</span></span> <span data-ttu-id="b8a52-159">注销发生时，您将收到 fnevExtended 通知。</span><span class="sxs-lookup"><span data-stu-id="b8a52-159">When the logoff occurs, you will receive an fnevExtended notification.</span></span> 
  
<span data-ttu-id="b8a52-160">调用**Advise**已成功完成后，在调用[IMAPISession::Unadvise](imapisession-unadvise.md)取消注册之前，释放 advise 接收器对象，除非您有特定的长期使用它。</span><span class="sxs-lookup"><span data-stu-id="b8a52-160">After a call to **Advise** has succeeded and before [IMAPISession::Unadvise](imapisession-unadvise.md) has been called to cancel the registration, release your advise sink object unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="b8a52-161">通知过程的概述，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="b8a52-161">For an overview of the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
<span data-ttu-id="b8a52-162">有关处理通知的详细信息，请参阅[处理通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="b8a52-162">For more information about handling notifications, see [Handling Notifications](handling-notifications.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b8a52-163">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="b8a52-163">MFCMAPI reference</span></span>

<span data-ttu-id="b8a52-164">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b8a52-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b8a52-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="b8a52-165">**File**</span></span>|<span data-ttu-id="b8a52-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="b8a52-166">**Function**</span></span>|<span data-ttu-id="b8a52-167">**Comment**</span><span class="sxs-lookup"><span data-stu-id="b8a52-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8a52-168">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="b8a52-168">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="b8a52-169">CBaseDialog::OnNotificationsOn</span><span class="sxs-lookup"><span data-stu-id="b8a52-169">CBaseDialog::OnNotificationsOn</span></span>  <br/> |<span data-ttu-id="b8a52-170">MFCMAPI 使用**IMAPISession::Advise**方法注册针对会话的通知。</span><span class="sxs-lookup"><span data-stu-id="b8a52-170">MFCMAPI uses the **IMAPISession::Advise** method to register for notifications against the session.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b8a52-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8a52-171">See also</span></span>



[<span data-ttu-id="b8a52-172">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="b8a52-172">IABLogon::Advise</span></span>](iablogon-advise.md)
  
[<span data-ttu-id="b8a52-173">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="b8a52-173">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="b8a52-174">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="b8a52-174">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="b8a52-175">IMAPISession::Unadvise</span><span class="sxs-lookup"><span data-stu-id="b8a52-175">IMAPISession::Unadvise</span></span>](imapisession-unadvise.md)
  
[<span data-ttu-id="b8a52-176">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b8a52-176">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="b8a52-177">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b8a52-177">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="b8a52-178">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="b8a52-178">Event Notification in MAPI</span></span>](event-notification-in-mapi.md)

