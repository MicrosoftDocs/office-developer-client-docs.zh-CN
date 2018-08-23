---
title: IMSLogonAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Advise
api_type:
- COM
ms.assetid: a3c5d937-642b-463b-b5a0-5d099e651895
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9cd0442a715fb5441ab8efefb9574f09f2e2c1ff
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587857"
---
# <a name="imslogonadvise"></a><span data-ttu-id="db0be-103">IMSLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="db0be-103">IMSLogon::Advise</span></span>

  
  
<span data-ttu-id="db0be-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="db0be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="db0be-105">使用有关邮件存储区中的更改的通知的消息存储提供程序注册的对象。</span><span class="sxs-lookup"><span data-stu-id="db0be-105">Registers an object with a message store provider for notifications about changes in the message store.</span></span> <span data-ttu-id="db0be-106">消息存储然后将对注册对象发送有关更改的通知。</span><span class="sxs-lookup"><span data-stu-id="db0be-106">The message store will then send notifications about changes to the registered object.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="db0be-107">参数</span><span class="sxs-lookup"><span data-stu-id="db0be-107">Parameters</span></span>

 <span data-ttu-id="db0be-108">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="db0be-108">_cbEntryID_</span></span>
  
> <span data-ttu-id="db0be-109">[in]以字节为单位_lpEntryID_参数指向的项标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="db0be-109">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="db0be-110">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="db0be-110">_lpEntryID_</span></span>
  
> <span data-ttu-id="db0be-111">[in]指向有关哪些应生成通知的对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="db0be-111">[in] A pointer to the entry identifier of the object about which notifications should be generated.</span></span> <span data-ttu-id="db0be-112">此对象可以是一个文件夹、 一条消息或消息存储库中的任何其他对象。</span><span class="sxs-lookup"><span data-stu-id="db0be-112">This object can be a folder, a message, or any other object in the message store.</span></span> <span data-ttu-id="db0be-113">此外，如果 MAPI 将_cbEntryID_参数设置为 0，并传递**null** _lpEntryID_，通知接收器提供了有关对整个邮件存储的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="db0be-113">Alternatively, if MAPI sets the  _cbEntryID_ parameter to 0 and passes **null** for  _lpEntryID_, the advise sink provides notifications about changes to the entire message store.</span></span>
    
 <span data-ttu-id="db0be-114">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="db0be-114">_ulEventMask_</span></span>
  
> <span data-ttu-id="db0be-115">[in]有关哪些 MAPI 会生成通知的对象出现通知事件的类型的事件掩码。</span><span class="sxs-lookup"><span data-stu-id="db0be-115">[in] An event mask of the types of notification events occurring for the object about which MAPI will generate notifications.</span></span> <span data-ttu-id="db0be-116">掩码筛选特定情况。</span><span class="sxs-lookup"><span data-stu-id="db0be-116">The mask filters specific cases.</span></span> <span data-ttu-id="db0be-117">每个事件类型都有与之关联的结构，其中包含有关事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="db0be-117">Each event type has a structure associated with it that contains additional information about the event.</span></span> <span data-ttu-id="db0be-118">下表列出了可能的事件类型以及它们对应的结构。</span><span class="sxs-lookup"><span data-stu-id="db0be-118">The following table lists the possible event types along with their corresponding structures.</span></span>
    
|<span data-ttu-id="db0be-119">**通知事件类型**</span><span class="sxs-lookup"><span data-stu-id="db0be-119">**Notification event type**</span></span>|<span data-ttu-id="db0be-120">**相应的结构**</span><span class="sxs-lookup"><span data-stu-id="db0be-120">**Corresponding structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db0be-121">fnevCriticalError</span><span class="sxs-lookup"><span data-stu-id="db0be-121">fnevCriticalError</span></span>  <br/> |[<span data-ttu-id="db0be-122">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-122">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="db0be-123">fnevNewMail</span><span class="sxs-lookup"><span data-stu-id="db0be-123">fnevNewMail</span></span>  <br/> |[<span data-ttu-id="db0be-124">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-124">NEWMAIL_NOTIFICATION</span></span>](newmail_notification.md) <br/> |
|<span data-ttu-id="db0be-125">fnevObjectCreated</span><span class="sxs-lookup"><span data-stu-id="db0be-125">fnevObjectCreated</span></span>  <br/> |[<span data-ttu-id="db0be-126">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-126">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="db0be-127">fnevObjectDeleted</span><span class="sxs-lookup"><span data-stu-id="db0be-127">fnevObjectDeleted</span></span>  <br/> |[<span data-ttu-id="db0be-128">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-128">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="db0be-129">fnevObjectModified</span><span class="sxs-lookup"><span data-stu-id="db0be-129">fnevObjectModified</span></span>  <br/> |[<span data-ttu-id="db0be-130">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-130">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="db0be-131">fnevObjectCopied</span><span class="sxs-lookup"><span data-stu-id="db0be-131">fnevObjectCopied</span></span>  <br/> |[<span data-ttu-id="db0be-132">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-132">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="db0be-133">fnevObjectMoved</span><span class="sxs-lookup"><span data-stu-id="db0be-133">fnevObjectMoved</span></span>  <br/> |[<span data-ttu-id="db0be-134">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-134">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="db0be-135">fnevSearchComplete</span><span class="sxs-lookup"><span data-stu-id="db0be-135">fnevSearchComplete</span></span>  <br/> |[<span data-ttu-id="db0be-136">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-136">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="db0be-137">fnevStatusObjectModified</span><span class="sxs-lookup"><span data-stu-id="db0be-137">fnevStatusObjectModified</span></span>  <br/> |[<span data-ttu-id="db0be-138">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="db0be-138">STATUS_OBJECT_NOTIFICATION</span></span>](status_object_notification.md) <br/> |
   
 <span data-ttu-id="db0be-139">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="db0be-139">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="db0be-140">[in]指向有关哪些请求通知会话对象发生事件时调用 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="db0be-140">[in] A pointer to an advise sink object to be called when an event occurs for the session object about which notification has been requested.</span></span> <span data-ttu-id="db0be-141">此 advise 接收器对象必须已经存在。</span><span class="sxs-lookup"><span data-stu-id="db0be-141">This advise sink object must already exist.</span></span>
    
 <span data-ttu-id="db0be-142">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="db0be-142">_lpulConnection_</span></span>
  
> <span data-ttu-id="db0be-143">[输出]指向的成功返回时保留通知注册的连接数变量的指针。</span><span class="sxs-lookup"><span data-stu-id="db0be-143">[out] A pointer to a variable that upon a successful return holds the connection number for the notification registration.</span></span> <span data-ttu-id="db0be-144">连接数必须非零值。</span><span class="sxs-lookup"><span data-stu-id="db0be-144">The connection number must be nonzero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="db0be-145">返回值</span><span class="sxs-lookup"><span data-stu-id="db0be-145">Return value</span></span>

<span data-ttu-id="db0be-146">S_OK</span><span class="sxs-lookup"><span data-stu-id="db0be-146">S_OK</span></span> 
  
> <span data-ttu-id="db0be-147">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="db0be-147">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="db0be-148">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="db0be-148">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="db0be-149">通过 MAPI 或一个或多个服务提供程序不支持此操作。</span><span class="sxs-lookup"><span data-stu-id="db0be-149">The operation is not supported by MAPI or by one or more service providers.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="db0be-150">注解</span><span class="sxs-lookup"><span data-stu-id="db0be-150">Remarks</span></span>

<span data-ttu-id="db0be-151">消息存储提供程序实现**IMSLogon::Advise**方法注册通知回调对象。</span><span class="sxs-lookup"><span data-stu-id="db0be-151">Message store providers implement the **IMSLogon::Advise** method to register an object for notification callbacks.</span></span> <span data-ttu-id="db0be-152">当指定对象发生更改时，提供程序检查哪些事件掩码位设置_ulEventMask_参数中，因此，发生更改的类型。</span><span class="sxs-lookup"><span data-stu-id="db0be-152">Whenever a change occurs to the indicated object, the provider checks to see what event mask bit was set in the  _ulEventMask_ parameter and, therefore, what type of change occurred.</span></span> <span data-ttu-id="db0be-153">如果设置了位，提供程序由_lpAdviseSink_参数来报告事件 advise 接收器对象调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="db0be-153">If a bit is set, the provider calls the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object indicated by the  _lpAdviseSink_ parameter to report the event.</span></span> <span data-ttu-id="db0be-154">数据传递给**OnNotify**例程通知结构中介绍的事件。</span><span class="sxs-lookup"><span data-stu-id="db0be-154">Data passed in the notification structure to the **OnNotify** routine describes the event.</span></span> 
  
<span data-ttu-id="db0be-155">更改该对象，该调用期间或任何更高版本时，可能会发生**OnNotify**调用。</span><span class="sxs-lookup"><span data-stu-id="db0be-155">The call to **OnNotify** can occur during the call that changes the object, or at any later time.</span></span> <span data-ttu-id="db0be-156">支持多个线程的执行系统，在调用**OnNotify**可以发生任何线程上。</span><span class="sxs-lookup"><span data-stu-id="db0be-156">On systems that support multiple threads of execution, the call to **OnNotify** can occur on any thread.</span></span> <span data-ttu-id="db0be-157">若要安全地处理**OnNotify**可能发生在时机的调用，客户端应用程序应使用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数。</span><span class="sxs-lookup"><span data-stu-id="db0be-157">To safely handle a call to **OnNotify** that might happen at an inopportune time, a client application should use the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> 
  
<span data-ttu-id="db0be-158">若要提供通知，实现**Advise**需要保持_lpAdviseSink_指针的副本的消息存储提供程序告知接收器对象;为此，请提供程序，请调用通知接收器来维护其对象的指针，直到[IMSLogon::Unadvise](imslogon-unadvise.md)方法的调用被取消通知注册的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="db0be-158">To provide notifications, the message store provider that implements **Advise** needs to keep a copy of the pointer to the  _lpAdviseSink_ advise sink object; to do so, the provider calls the [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx) method for the advise sink to maintain its object pointer until notification registration is canceled with a call to the [IMSLogon::Unadvise](imslogon-unadvise.md) method.</span></span> <span data-ttu-id="db0be-159">**Advise**实现应分配的通知注册的连接数并返回_lpulConnection_参数中之前调用此连接号码**AddRef** 。</span><span class="sxs-lookup"><span data-stu-id="db0be-159">The **Advise** implementation should assign a connection number to the notification registration and call **AddRef** on this connection number before returning it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="db0be-160">服务提供商可以释放 advise 接收器对象之前注册被取消，但他们必须在被调用**Unadvise**之前不释放连接数。</span><span class="sxs-lookup"><span data-stu-id="db0be-160">Service providers can release the advise sink object before the registration is canceled, but they must not release the connection number until **Unadvise** has been called.</span></span> 
  
<span data-ttu-id="db0be-161">调用**Advise**已成功完成后，在调用**Unadvise**之前，必须先为 advise 接收器对象，必须释放准备提供程序。</span><span class="sxs-lookup"><span data-stu-id="db0be-161">After a call to **Advise** has succeeded and before **Unadvise** has been called, providers must be prepared for the advise sink object to be released.</span></span> <span data-ttu-id="db0be-162">因此，提供程序应释放其 advise 接收器对象后**Advise**返回，除非它具有特定的长期使用它。</span><span class="sxs-lookup"><span data-stu-id="db0be-162">Therefore, a provider should release its advise sink object after **Advise** returns, unless it has a specific long-term use for it.</span></span> 
  
<span data-ttu-id="db0be-163">有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="db0be-163">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="db0be-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db0be-164">See also</span></span>



[<span data-ttu-id="db0be-165">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="db0be-165">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="db0be-166">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="db0be-166">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="db0be-167">IMSLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="db0be-167">IMSLogon::Unadvise</span></span>](imslogon-unadvise.md)
  
[<span data-ttu-id="db0be-168">通知</span><span class="sxs-lookup"><span data-stu-id="db0be-168">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="db0be-169">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="db0be-169">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

