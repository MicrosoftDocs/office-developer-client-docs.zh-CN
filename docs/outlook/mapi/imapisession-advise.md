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
# <a name="imapisessionadvise"></a><span data-ttu-id="26963-103">IMAPISession::Advise</span><span class="sxs-lookup"><span data-stu-id="26963-103">IMAPISession::Advise</span></span>

  
  
<span data-ttu-id="26963-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26963-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26963-105">注册以接收影响会话的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-105">Registers to receive notification of specified events that affect the session.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="26963-106">参数</span><span class="sxs-lookup"><span data-stu-id="26963-106">Parameters</span></span>

 <span data-ttu-id="26963-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="26963-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="26963-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="26963-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="26963-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="26963-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="26963-110">实时指向通讯簿或邮件存储对象的条目标识符的指针, 该标识符应生成哪些通知, 或者为 NULL, 这表示客户端正在注册以接收有关仅影响会话的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-110">[in] A pointer to the entry identifier of the address book or message store object about which notifications should be generated, or NULL, which indicates that the client is registering to receive notifications about events that affect only the session.</span></span> 
    
 <span data-ttu-id="26963-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="26963-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="26963-112">实时指示客户端所关注的通知事件类型的值掩码, 应包括在注册中。</span><span class="sxs-lookup"><span data-stu-id="26963-112">[in] A mask of values that indicate the types of notification events that the client is interested in and should be included in the registration.</span></span> <span data-ttu-id="26963-113">如果_lpEntryID_为 NULL, 则 MAPI 会自动为仅影响会话的关键错误事件注册客户端。</span><span class="sxs-lookup"><span data-stu-id="26963-113">If  _lpEntryID_ is NULL, MAPI automatically registers the client for critical error events that affect only the session.</span></span> <span data-ttu-id="26963-114">当_lpEntryID_指向条目标识符时, 以下值对_ulEventMask_参数有效:</span><span class="sxs-lookup"><span data-stu-id="26963-114">When  _lpEntryID_ points to an entry identifier, the following values are valid for the  _ulEventMask_ parameter:</span></span> 
    
<span data-ttu-id="26963-115">fnevCriticalError</span><span class="sxs-lookup"><span data-stu-id="26963-115">fnevCriticalError</span></span> 
  
> <span data-ttu-id="26963-116">注册有关严重错误 (如内存不足) 的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-116">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
<span data-ttu-id="26963-117">fnevExtended</span><span class="sxs-lookup"><span data-stu-id="26963-117">fnevExtended</span></span> 
  
> <span data-ttu-id="26963-118">注册有关特定通讯簿或邮件存储提供程序的特定事件的通知, 以及关于会话关闭的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-118">Registers for notifications about events specific to a particular address book or message store provider and about session shut down.</span></span>
    
<span data-ttu-id="26963-119">fnevNewMail</span><span class="sxs-lookup"><span data-stu-id="26963-119">fnevNewMail</span></span> 
  
> <span data-ttu-id="26963-120">注册有关新邮件到达的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-120">Registers for notifications about the arrival of new messages.</span></span> 
    
<span data-ttu-id="26963-121">fnevObjectCreated</span><span class="sxs-lookup"><span data-stu-id="26963-121">fnevObjectCreated</span></span> 
  
> <span data-ttu-id="26963-122">注册有关创建新对象的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-122">Registers for notifications about the creation of a new object.</span></span>
    
<span data-ttu-id="26963-123">fnevObjectCopied</span><span class="sxs-lookup"><span data-stu-id="26963-123">fnevObjectCopied</span></span>
  
> <span data-ttu-id="26963-124">注册有关要复制的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-124">Registers for notifications about an object being copied.</span></span>
    
<span data-ttu-id="26963-125">fnevObjectDeleted</span><span class="sxs-lookup"><span data-stu-id="26963-125">fnevObjectDeleted</span></span>
  
> <span data-ttu-id="26963-126">注册有关要删除的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-126">Registers for notifications about an object being deleted.</span></span>
    
<span data-ttu-id="26963-127">fnevObjectModified</span><span class="sxs-lookup"><span data-stu-id="26963-127">fnevObjectModified</span></span>
  
> <span data-ttu-id="26963-128">注册有关要修改的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-128">Registers for notifications about an object being modified.</span></span>
    
<span data-ttu-id="26963-129">fnevObjectMoved</span><span class="sxs-lookup"><span data-stu-id="26963-129">fnevObjectMoved</span></span>
  
> <span data-ttu-id="26963-130">注册有关要移动的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-130">Registers for notifications about an object being moved.</span></span>
    
<span data-ttu-id="26963-131">fnevSearchComplete</span><span class="sxs-lookup"><span data-stu-id="26963-131">fnevSearchComplete</span></span>
  
> <span data-ttu-id="26963-132">注册有关搜索操作完成的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-132">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="26963-133">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="26963-133">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="26963-134">实时指向接收后续通知的通知接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="26963-134">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="26963-135">此通知接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="26963-135">This advise sink object must have already been allocated.</span></span>
    
 <span data-ttu-id="26963-136">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="26963-136">_lpulConnection_</span></span>
  
> <span data-ttu-id="26963-137">排除一个指向非零数字的指针, 该数字表示呼叫者的通知接收器对象和会话之间的连接。</span><span class="sxs-lookup"><span data-stu-id="26963-137">[out] A pointer to a nonzero number that represents the connection between the caller's advise sink object and the session.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="26963-138">返回值</span><span class="sxs-lookup"><span data-stu-id="26963-138">Return value</span></span>

<span data-ttu-id="26963-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="26963-139">S_OK</span></span> 
  
> <span data-ttu-id="26963-140">注册成功。</span><span class="sxs-lookup"><span data-stu-id="26963-140">The registration was successful.</span></span>
    
<span data-ttu-id="26963-141">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="26963-141">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="26963-142">_lpEntryID_指向的条目标识符不代表有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="26963-142">The entry identifier pointed to by  _lpEntryID_ does not represent a valid entry identifier.</span></span> 
    
<span data-ttu-id="26963-143">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="26963-143">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="26963-144">负责_lpEntryID_指向的条目标识符的服务提供程序不支持在_ulEventMask_参数中指定的事件类型或不支持通知。</span><span class="sxs-lookup"><span data-stu-id="26963-144">The service provider responsible for the entry identifier pointed to by  _lpEntryID_ either does not support the type of events specified in the  _ulEventMask_ parameter or does not support notification.</span></span> 
    
<span data-ttu-id="26963-145">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="26963-145">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="26963-146">配置文件中的任何服务提供程序都不能处理_lpEntryID_指向的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="26963-146">The entry identifier pointed to by  _lpEntryID_ cannot be handled by any of the service providers in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="26963-147">说明</span><span class="sxs-lookup"><span data-stu-id="26963-147">Remarks</span></span>

<span data-ttu-id="26963-148">**IMAPISession:: Advise**方法在呼叫者的通知接收器对象、会话和服务提供商 (可选) 之间建立连接。</span><span class="sxs-lookup"><span data-stu-id="26963-148">The **IMAPISession::Advise** method establishes a connection between the caller's advise sink object, the session and, optionally, a service provider.</span></span> <span data-ttu-id="26963-149">当在_ulEventMask_参数中指定的一个或多个事件发生于_lpEntryID_指向的对象时, 此连接用于将通知发送到通知接收器。</span><span class="sxs-lookup"><span data-stu-id="26963-149">This connection is used to send notifications to the advise sink when one or more events specified in the  _ulEventMask_ parameter occur to the object pointed to by  _lpEntryID_.</span></span> <span data-ttu-id="26963-150">当_lpEntryID_为 NULL 时, 目标对象为会话, 并且仅发送严重错误和扩展事件的通知。</span><span class="sxs-lookup"><span data-stu-id="26963-150">When  _lpEntryID_ is NULL, the target object is the session and notifications are sent only for critical errors and extended events.</span></span> 
  
<span data-ttu-id="26963-151">当_lpEntryID_指向有效的条目标识符时, MAPI 会调用属于负责服务提供商的 logon 对象的**Advise**方法。</span><span class="sxs-lookup"><span data-stu-id="26963-151">When  _lpEntryID_ points to a valid entry identifier, MAPI calls the **Advise** method of the logon object that belongs to the responsible service provider.</span></span> <span data-ttu-id="26963-152">例如, 如果_lpEntryID_指向通讯组列表的条目标识符, 则 MAPI 会调用相应的通讯簿提供程序的[IABLogon:: Advise](iablogon-advise.md)方法。</span><span class="sxs-lookup"><span data-stu-id="26963-152">For example, if  _lpEntryID_ points to the entry identifier of a distribution list, MAPI calls the appropriate address book provider's [IABLogon::Advise](iablogon-advise.md) method.</span></span> 
  
<span data-ttu-id="26963-153">若要发送通知, 服务提供商或 MAPI 将调用已注册的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="26963-153">To send a notification, either the service provider or MAPI calls the registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="26963-154">**OnNotify**的参数之一是通知结构, 它包含描述特定事件的信息。</span><span class="sxs-lookup"><span data-stu-id="26963-154">One of the parameters to **OnNotify**, a notification structure, contains information that describes the specific event.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="26963-155">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="26963-155">Notes to callers</span></span>

<span data-ttu-id="26963-156">在支持多个执行线程的系统上, 也可以随时在任何线程上对**OnNotify**进行调用。</span><span class="sxs-lookup"><span data-stu-id="26963-156">On systems that support multiple threads of execution, the call to **OnNotify** can also occur on any thread at any time.</span></span> <span data-ttu-id="26963-157">如果您需要确保仅在特定的线程上的特定时间发生通知, 请调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数来生成您传递给**advise**方法的建议接收器对象。</span><span class="sxs-lookup"><span data-stu-id="26963-157">If you need assurance that notifications will occur only at a particular time on a particular thread, call the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to generate the advise sink object that you pass to the **Advise** method.</span></span> 
  
<span data-ttu-id="26963-158">若要确定客户端注销的时间, 请通过调用_lpEntryID_设置为 NULL 并将_cbEntryID_设置为0的**建议**, 在服务提供程序中注册通知。</span><span class="sxs-lookup"><span data-stu-id="26963-158">To determine when a client has logged off, register for notifications in your service provider by calling **Advise** with  _lpEntryID_ set to NULL and  _cbEntryID_ set to 0.</span></span> <span data-ttu-id="26963-159">当注销发生时, 您将收到 fnevExtended 通知。</span><span class="sxs-lookup"><span data-stu-id="26963-159">When the logoff occurs, you will receive an fnevExtended notification.</span></span> 
  
<span data-ttu-id="26963-160">在已成功调用**建议**之后且[IMAPISession:: Unadvise](imapisession-unadvise.md)已被调用以取消注册之前, 请释放您的建议接收器对象, 除非您有特定的长期用途。</span><span class="sxs-lookup"><span data-stu-id="26963-160">After a call to **Advise** has succeeded and before [IMAPISession::Unadvise](imapisession-unadvise.md) has been called to cancel the registration, release your advise sink object unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="26963-161">有关通知过程的概述, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="26963-161">For an overview of the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
<span data-ttu-id="26963-162">有关处理通知的详细信息, 请参阅[处理通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="26963-162">For more information about handling notifications, see [Handling Notifications](handling-notifications.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="26963-163">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="26963-163">MFCMAPI reference</span></span>

<span data-ttu-id="26963-164">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="26963-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="26963-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="26963-165">**File**</span></span>|<span data-ttu-id="26963-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="26963-166">**Function**</span></span>|<span data-ttu-id="26963-167">**备注**</span><span class="sxs-lookup"><span data-stu-id="26963-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="26963-168">BaseDialog</span><span class="sxs-lookup"><span data-stu-id="26963-168">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="26963-169">CBaseDialog:: OnNotificationsOn</span><span class="sxs-lookup"><span data-stu-id="26963-169">CBaseDialog::OnNotificationsOn</span></span>  <br/> |<span data-ttu-id="26963-170">MFCMAPI 使用**IMAPISession:: Advise**方法为会话注册通知。</span><span class="sxs-lookup"><span data-stu-id="26963-170">MFCMAPI uses the **IMAPISession::Advise** method to register for notifications against the session.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="26963-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26963-171">See also</span></span>



[<span data-ttu-id="26963-172">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="26963-172">IABLogon::Advise</span></span>](iablogon-advise.md)
  
[<span data-ttu-id="26963-173">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="26963-173">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="26963-174">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="26963-174">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="26963-175">IMAPISession::Unadvise</span><span class="sxs-lookup"><span data-stu-id="26963-175">IMAPISession::Unadvise</span></span>](imapisession-unadvise.md)
  
[<span data-ttu-id="26963-176">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="26963-176">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="26963-177">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="26963-177">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="26963-178">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="26963-178">Event Notification in MAPI</span></span>](event-notification-in-mapi.md)

