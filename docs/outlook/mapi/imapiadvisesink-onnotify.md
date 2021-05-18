---
title: IMAPIAdviseSinkOnNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIAdviseSink.OnNotify
api_type:
- COM
ms.assetid: 9eec90d3-2369-4340-86ed-0efa58918ed5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5983ed3229f6b0053f15a614116cf5680e942587
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407359"
---
# <a name="imapiadvisesinkonnotify"></a><span data-ttu-id="22223-103">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="22223-103">IMAPIAdviseSink::OnNotify</span></span>

  
  
<span data-ttu-id="22223-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22223-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="22223-105">通过执行一个或多个任务来响应通知。</span><span class="sxs-lookup"><span data-stu-id="22223-105">Responds to a notification by performing one or more tasks.</span></span> <span data-ttu-id="22223-106">执行的任务取决于事件的类型和生成通知的对象。</span><span class="sxs-lookup"><span data-stu-id="22223-106">The tasks performed depend on the type of event and the object that generates the notification.</span></span> 
  
```cpp
ULONG OnNotify(
  ULONG cNotif,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a><span data-ttu-id="22223-107">参数</span><span class="sxs-lookup"><span data-stu-id="22223-107">Parameters</span></span>

 <span data-ttu-id="22223-108">_cNotif_</span><span class="sxs-lookup"><span data-stu-id="22223-108">_cNotif_</span></span>
  
> <span data-ttu-id="22223-109">[in]_lpNotifications_ 参数指向的 [NOTIFICATION](notification.md)结构计数。</span><span class="sxs-lookup"><span data-stu-id="22223-109">[in] The count of [NOTIFICATION](notification.md) structures pointed to by the  _lpNotifications_ parameter.</span></span> 
    
 <span data-ttu-id="22223-110">_lpNotifications_</span><span class="sxs-lookup"><span data-stu-id="22223-110">_lpNotifications_</span></span>
  
> <span data-ttu-id="22223-111">[in]指向一个或多个 **NOTIFICATION** 结构的指针，该结构提供有关已发生事件的信息。</span><span class="sxs-lookup"><span data-stu-id="22223-111">[in] A pointer to one or more **NOTIFICATION** structures that provide information about the events that have occurred.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="22223-112">返回值</span><span class="sxs-lookup"><span data-stu-id="22223-112">Return value</span></span>

<span data-ttu-id="22223-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="22223-113">S_OK</span></span> 
  
> <span data-ttu-id="22223-114">通知已成功处理。</span><span class="sxs-lookup"><span data-stu-id="22223-114">The notification was processed successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="22223-115">备注</span><span class="sxs-lookup"><span data-stu-id="22223-115">Remarks</span></span>

<span data-ttu-id="22223-116">当客户端或 MAPI 调用服务提供商的 **Advise** 方法以注册以接收特定对象的特定类型通知时，通知过程将启动。</span><span class="sxs-lookup"><span data-stu-id="22223-116">The notification process starts when a client or MAPI makes a call to a service provider's **Advise** method to register to receive a notification of a particular type for a particular object.</span></span> <span data-ttu-id="22223-117">**Advise** 方法的参数之一是指向实现 [IMAPIAdviseSink](imapiadvisesinkiunknown.md)接口的 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="22223-117">One of the parameters to the **Advise** method is a pointer to an advise sink object that implements the [IMAPIAdviseSink](imapiadvisesinkiunknown.md) interface.</span></span> <span data-ttu-id="22223-118">当对应于已注册的通知的目标对象发生事件时，服务提供商会直接或间接通过 MAPI 调用通知接收器 **的 OnNotify** 方法。</span><span class="sxs-lookup"><span data-stu-id="22223-118">When an event occurs to the target object that corresponds to the registered notification, the service provider, either directly or indirectly through MAPI, calls the advise sink's **OnNotify** method.</span></span> 
  
<span data-ttu-id="22223-119">对 **OnNotify** 的调用可以在导致事件的 MAPI 调用期间或稍后发生。</span><span class="sxs-lookup"><span data-stu-id="22223-119">The call to **OnNotify** can occur either during the MAPI call that is causing the event or at some later time.</span></span> <span data-ttu-id="22223-120">在支持多个执行线程的系统上，可以在用于注册的同一线程上或其他线程上调用 **OnNotify。**</span><span class="sxs-lookup"><span data-stu-id="22223-120">On systems that support multiple threads of execution, **OnNotify** can be called either on the same thread that was used for registration or on a different thread.</span></span> <span data-ttu-id="22223-121">客户端可以通过创建使用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数传递给 **Advise** 的建议接收器，确保在用于调用 **Advise** 的同一线程上执行 **OnNotify** 调用。</span><span class="sxs-lookup"><span data-stu-id="22223-121">Clients can make sure that the **OnNotify** call is made on the same thread used to call **Advise** by creating the advise sink that they pass to **Advise** with the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> 
  
<span data-ttu-id="22223-122">_lpNotifications_ 参数指向一个或多个 **NOTIFICATION** 结构，用于描述事件期间发生了哪些变化。</span><span class="sxs-lookup"><span data-stu-id="22223-122">The  _lpNotifications_ parameter points to one or more **NOTIFICATION** structures that describe what has changed during the event.</span></span> <span data-ttu-id="22223-123">每种事件类型都有不同类型的 **NOTIFICATION** 结构。</span><span class="sxs-lookup"><span data-stu-id="22223-123">There is a different type of **NOTIFICATION** structure for each type of event.</span></span> 
  
<span data-ttu-id="22223-124">下表列出了用于表示可能类型的事件的值以及与每个值关联的结构：</span><span class="sxs-lookup"><span data-stu-id="22223-124">The following table lists the values that are used to represent the possible types of events and the structures associated with each value:</span></span>
  
|<span data-ttu-id="22223-125">**通知事件类型**</span><span class="sxs-lookup"><span data-stu-id="22223-125">**Notification event type**</span></span>|<span data-ttu-id="22223-126">**相应的结构**</span><span class="sxs-lookup"><span data-stu-id="22223-126">**Corresponding structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22223-127">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="22223-127">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="22223-128">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-128">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="22223-129">**fnevNewMail**</span><span class="sxs-lookup"><span data-stu-id="22223-129">**fnevNewMail**</span></span> <br/> |[<span data-ttu-id="22223-130">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-130">NEWMAIL_NOTIFICATION</span></span>](newmail_notification.md) <br/> |
|<span data-ttu-id="22223-131">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="22223-131">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="22223-132">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-132">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="22223-133">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="22223-133">**fnevObjectDeleted**</span></span> <br/> |[<span data-ttu-id="22223-134">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-134">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="22223-135">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="22223-135">**fnevObjectModified**</span></span> <br/> |[<span data-ttu-id="22223-136">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-136">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="22223-137">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="22223-137">**fnevObjectCopied**</span></span> <br/> |[<span data-ttu-id="22223-138">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-138">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="22223-139">**fnevSearchComplete**</span><span class="sxs-lookup"><span data-stu-id="22223-139">**fnevSearchComplete**</span></span> <br/> |[<span data-ttu-id="22223-140">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-140">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="22223-141">**fnevTableModified**</span><span class="sxs-lookup"><span data-stu-id="22223-141">**fnevTableModified**</span></span> <br/> |[<span data-ttu-id="22223-142">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-142">TABLE_NOTIFICATION</span></span>](table_notification.md) <br/> |
|<span data-ttu-id="22223-143">**fnevStatusObjectModified**</span><span class="sxs-lookup"><span data-stu-id="22223-143">**fnevStatusObjectModified**</span></span> <br/> |[<span data-ttu-id="22223-144">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-144">STATUS_OBJECT_NOTIFICATION</span></span>](status_object_notification.md) <br/> |
|<span data-ttu-id="22223-145">**fnevExtended**</span><span class="sxs-lookup"><span data-stu-id="22223-145">**fnevExtended**</span></span> <br/> |[<span data-ttu-id="22223-146">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-146">EXTENDED_NOTIFICATION</span></span>](extended_notification.md) <br/> |
   
<span data-ttu-id="22223-147">若要详细了解如何设置和停止通知，请参阅以下任一接口的 **Advise** 和 **Unadvise** 方法的参考条目：IABLogon、IAddrBook、IMAPIForm、IMAPISession、IMAPITable、IMsgStore [](imsgstoreimapiprop.md)和 [](imapisessioniunknown.md)[](iaddrbookimapiprop.md)[IMSLogon。](imslogoniunknown.md) [](iablogoniunknown.md) [](imapiformiunknown.md) [](imapitableiunknown.md)</span><span class="sxs-lookup"><span data-stu-id="22223-147">For more information about how to set up and stop notifications, see the reference entries for the **Advise** and **Unadvise** methods for any of the following interfaces: [IABLogon](iablogoniunknown.md), [IAddrBook](iaddrbookimapiprop.md), [IMAPIForm](imapiformiunknown.md), [IMAPISession](imapisessioniunknown.md), [IMAPITable](imapitableiunknown.md), [IMsgStore](imsgstoreimapiprop.md), and [IMSLogon](imslogoniunknown.md).</span></span> 
  
<span data-ttu-id="22223-148">有关通知过程的常规信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="22223-148">For general information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="22223-149">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="22223-149">Notes to implementers</span></span>

<span data-ttu-id="22223-150">**OnNotify** 实现通常包含预期接收的每种类型的通知的一个或多个代码块。</span><span class="sxs-lookup"><span data-stu-id="22223-150">Your **OnNotify** implementation will typically consist of one or more blocks of code for each type of notification you expect to receive.</span></span> <span data-ttu-id="22223-151">在这些代码块内，执行你认为作为通知响应所必需的任何任务。</span><span class="sxs-lookup"><span data-stu-id="22223-151">Within these blocks of code, perform any tasks that you consider necessary as a response to the notification.</span></span> <span data-ttu-id="22223-152">例如，假设您注册以接收对话框显示中包括的文件夹上的 **fnevObjectModified** 通知。</span><span class="sxs-lookup"><span data-stu-id="22223-152">For example, suppose you register to receive **fnevObjectModified** notifications on a folder that is included in a dialog box display.</span></span> <span data-ttu-id="22223-153">在 **OnNotify** 方法中用于处理 **fnevObjectModified** 通知的代码块中，你可以向对话框发送 Windows 消息以请求更新的显示。</span><span class="sxs-lookup"><span data-stu-id="22223-153">In the block of code that you include in your **OnNotify** method to handle **fnevObjectModified** notifications, you might send a Windows message to the dialog box to request an updated display.</span></span> 
  
<span data-ttu-id="22223-154">不要修改或释放传递给 **OnNotify** 的 **NOTIFICATION** 结构。</span><span class="sxs-lookup"><span data-stu-id="22223-154">Do not modify or free the **NOTIFICATION** structure passed to **OnNotify**.</span></span> <span data-ttu-id="22223-155">结构中的数据仅在 **OnNotify 返回之前有效** 。</span><span class="sxs-lookup"><span data-stu-id="22223-155">The data in the structure is valid only until **OnNotify** returns.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="22223-156">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="22223-156">Notes to callers</span></span>

<span data-ttu-id="22223-157">当对多个对象进行更改时，您可以通知注册的通知接收器，该通知接收在 **OnNotify** 的单个调用中或根据内存限制的多个调用中。</span><span class="sxs-lookup"><span data-stu-id="22223-157">When changes occur to multiple objects, you can notify a registered advise sink in a single call to **OnNotify** or in multiple calls depending on memory constraints.</span></span> <span data-ttu-id="22223-158">无论更改是一个方法调用还是多个方法调用的结果，都是如此。</span><span class="sxs-lookup"><span data-stu-id="22223-158">This is true regardless of whether the changes are the result of one method call or several.</span></span> <span data-ttu-id="22223-159">例如，对 [IMAPIFolder：：CopyMessages](imapifolder-copymessages.md) 的调用可能会影响多个邮件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="22223-159">For example, a call to [IMAPIFolder::CopyMessages](imapifolder-copymessages.md) can affect multiple messages and folders.</span></span> <span data-ttu-id="22223-160">作为邮件存储提供程序，可以使用目标文件夹的 **fnevObjectModified** 事件类型对 **OnNotify** 进行一次调用，或多次调用，每个调用一个影响邮件。</span><span class="sxs-lookup"><span data-stu-id="22223-160">As a message store provider, you can make one call to **OnNotify** with an **fnevObjectModified** event type for the target folder or many calls, one for each affect messages.</span></span> <span data-ttu-id="22223-161">同样，如果客户端对 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md)进行重复调用，这些调用可以组合到文件夹的一个 **fnevObjectModified** 事件，也可以分隔为每个新邮件的单个 **fnevObjectCreated** 事件。</span><span class="sxs-lookup"><span data-stu-id="22223-161">Similarly, if a client makes repeated calls to [IMAPIFolder::CreateMessage](imapifolder-createmessage.md), these calls can be combined into one **fnevObjectModified** event for the folder or separated into individual **fnevObjectCreated** events for each new message.</span></span> 
  
<span data-ttu-id="22223-162">若要详细了解如何以及何时生成通知，请参阅 [MAPI](event-notification-in-mapi.md) 中的事件通知 [和支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="22223-162">For more information about how and when to generate notifications, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Supporting Event Notification](supporting-event-notification.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="22223-163">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="22223-163">MFCMAPI reference</span></span>

<span data-ttu-id="22223-164">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="22223-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="22223-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="22223-165">**File**</span></span>|<span data-ttu-id="22223-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="22223-166">**Function**</span></span>|<span data-ttu-id="22223-167">**备注**</span><span class="sxs-lookup"><span data-stu-id="22223-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22223-168">AdviseSink.h 和 AdviseSink.cpp</span><span class="sxs-lookup"><span data-stu-id="22223-168">AdviseSink.h and AdviseSink.cpp</span></span>  <br/> |<span data-ttu-id="22223-169">CAdviseSink：：OnNotifyDesc</span><span class="sxs-lookup"><span data-stu-id="22223-169">CAdviseSink::OnNotifyDesc</span></span>  <br/> |<span data-ttu-id="22223-170">实现 CAdviseSink 类以处理 MFCMAPI 中的所有通知。</span><span class="sxs-lookup"><span data-stu-id="22223-170">The CAdviseSink class is implemented to handle all notifications in MFCMAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="22223-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22223-171">See also</span></span>



[<span data-ttu-id="22223-172">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="22223-172">HrAllocAdviseSink</span></span>](hrallocadvisesink.md)
  
[<span data-ttu-id="22223-173">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="22223-173">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="22223-174">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="22223-174">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
  
[<span data-ttu-id="22223-175">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="22223-175">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="22223-176">IMAPIAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="22223-176">IMAPIAdviseSink : IUnknown</span></span>](imapiadvisesinkiunknown.md)


[<span data-ttu-id="22223-177">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="22223-177">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

