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
ms.openlocfilehash: d052e7590ee502b55f2076d698587ab68820ca56
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576699"
---
# <a name="imapiadvisesinkonnotify"></a><span data-ttu-id="e91fb-103">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="e91fb-103">IMAPIAdviseSink::OnNotify</span></span>

  
  
<span data-ttu-id="e91fb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e91fb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e91fb-105">通过执行一个或多个任务响应通知。</span><span class="sxs-lookup"><span data-stu-id="e91fb-105">Responds to a notification by performing one or more tasks.</span></span> <span data-ttu-id="e91fb-106">执行的任务取决于事件以及生成通知的对象类型。</span><span class="sxs-lookup"><span data-stu-id="e91fb-106">The tasks performed depend on the type of event and the object that generates the notification.</span></span> 
  
```cpp
ULONG OnNotify(
  ULONG cNotif,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a><span data-ttu-id="e91fb-107">参数</span><span class="sxs-lookup"><span data-stu-id="e91fb-107">Parameters</span></span>

 <span data-ttu-id="e91fb-108">_cNotif_</span><span class="sxs-lookup"><span data-stu-id="e91fb-108">_cNotif_</span></span>
  
> <span data-ttu-id="e91fb-109">[in][通知](notification.md)结构_lpNotifications_参数指向的计数。</span><span class="sxs-lookup"><span data-stu-id="e91fb-109">[in] The count of [NOTIFICATION](notification.md) structures pointed to by the  _lpNotifications_ parameter.</span></span> 
    
 <span data-ttu-id="e91fb-110">_lpNotifications_</span><span class="sxs-lookup"><span data-stu-id="e91fb-110">_lpNotifications_</span></span>
  
> <span data-ttu-id="e91fb-111">[in]一个指向一个或多个**通知**结构，并提供有关发生的事件的信息。</span><span class="sxs-lookup"><span data-stu-id="e91fb-111">[in] A pointer to one or more **NOTIFICATION** structures that provide information about the events that have occurred.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e91fb-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e91fb-112">Return value</span></span>

<span data-ttu-id="e91fb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e91fb-113">S_OK</span></span> 
  
> <span data-ttu-id="e91fb-114">通知已成功处理。</span><span class="sxs-lookup"><span data-stu-id="e91fb-114">The notification was processed successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e91fb-115">注解</span><span class="sxs-lookup"><span data-stu-id="e91fb-115">Remarks</span></span>

<span data-ttu-id="e91fb-116">当客户端或 MAPI 服务提供商的**Advise**方法的调用，以注册，以接收通知的特定对象的特定类型时，将启动通知过程。</span><span class="sxs-lookup"><span data-stu-id="e91fb-116">The notification process starts when a client or MAPI makes a call to a service provider's **Advise** method to register to receive a notification of a particular type for a particular object.</span></span> <span data-ttu-id="e91fb-117">**Advise**方法的参数之一是指向实现[IMAPIAdviseSink](imapiadvisesinkiunknown.md)接口 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e91fb-117">One of the parameters to the **Advise** method is a pointer to an advise sink object that implements the [IMAPIAdviseSink](imapiadvisesinkiunknown.md) interface.</span></span> <span data-ttu-id="e91fb-118">对目标对象对应于已注册的通知中，服务提供商，直接或间接通过 MAPI，事件发生时调用通知接收器**OnNotify**方法。</span><span class="sxs-lookup"><span data-stu-id="e91fb-118">When an event occurs to the target object that corresponds to the registered notification, the service provider, either directly or indirectly through MAPI, calls the advise sink's **OnNotify** method.</span></span> 
  
<span data-ttu-id="e91fb-119">MAPI 呼叫导致该事件期间，也可以在某些更高版本时，会发生**OnNotify**调用。</span><span class="sxs-lookup"><span data-stu-id="e91fb-119">The call to **OnNotify** can occur either during the MAPI call that is causing the event or at some later time.</span></span> <span data-ttu-id="e91fb-120">在系统上支持多个线程的执行， **OnNotify**可在同一线程了用于注册或在不同线程上调用。</span><span class="sxs-lookup"><span data-stu-id="e91fb-120">On systems that support multiple threads of execution, **OnNotify** can be called either on the same thread that was used for registration or on a different thread.</span></span> <span data-ttu-id="e91fb-121">客户端可以确保**OnNotify**呼叫由用于通过创建它们与[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数传递给**Advise**通知接收器调用**Advise**对同一线程。</span><span class="sxs-lookup"><span data-stu-id="e91fb-121">Clients can make sure that the **OnNotify** call is made on the same thread used to call **Advise** by creating the advise sink that they pass to **Advise** with the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> 
  
<span data-ttu-id="e91fb-122">_LpNotifications_参数指向介绍事件过程中更改内容的一个或多个**通知**结构。</span><span class="sxs-lookup"><span data-stu-id="e91fb-122">The  _lpNotifications_ parameter points to one or more **NOTIFICATION** structures that describe what has changed during the event.</span></span> <span data-ttu-id="e91fb-123">没有其他类型的每种类型的事件**通知**结构。</span><span class="sxs-lookup"><span data-stu-id="e91fb-123">There is a different type of **NOTIFICATION** structure for each type of event.</span></span> 
  
<span data-ttu-id="e91fb-124">下表列出了用于表示可能的事件和与每个值的结构类型的值：</span><span class="sxs-lookup"><span data-stu-id="e91fb-124">The following table lists the values that are used to represent the possible types of events and the structures associated with each value:</span></span>
  
|<span data-ttu-id="e91fb-125">**通知事件类型**</span><span class="sxs-lookup"><span data-stu-id="e91fb-125">**Notification event type**</span></span>|<span data-ttu-id="e91fb-126">**相应的结构**</span><span class="sxs-lookup"><span data-stu-id="e91fb-126">**Corresponding structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e91fb-127">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="e91fb-127">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="e91fb-128">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-128">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="e91fb-129">**fnevNewMail**</span><span class="sxs-lookup"><span data-stu-id="e91fb-129">**fnevNewMail**</span></span> <br/> |[<span data-ttu-id="e91fb-130">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-130">NEWMAIL_NOTIFICATION</span></span>](newmail_notification.md) <br/> |
|<span data-ttu-id="e91fb-131">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="e91fb-131">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="e91fb-132">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-132">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e91fb-133">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="e91fb-133">**fnevObjectDeleted**</span></span> <br/> |[<span data-ttu-id="e91fb-134">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-134">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e91fb-135">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="e91fb-135">**fnevObjectModified**</span></span> <br/> |[<span data-ttu-id="e91fb-136">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-136">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e91fb-137">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="e91fb-137">**fnevObjectCopied**</span></span> <br/> |[<span data-ttu-id="e91fb-138">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-138">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e91fb-139">**fnevSearchComplete**</span><span class="sxs-lookup"><span data-stu-id="e91fb-139">**fnevSearchComplete**</span></span> <br/> |[<span data-ttu-id="e91fb-140">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-140">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e91fb-141">**fnevTableModified**</span><span class="sxs-lookup"><span data-stu-id="e91fb-141">**fnevTableModified**</span></span> <br/> |[<span data-ttu-id="e91fb-142">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-142">TABLE_NOTIFICATION</span></span>](table_notification.md) <br/> |
|<span data-ttu-id="e91fb-143">**fnevStatusObjectModified**</span><span class="sxs-lookup"><span data-stu-id="e91fb-143">**fnevStatusObjectModified**</span></span> <br/> |[<span data-ttu-id="e91fb-144">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-144">STATUS_OBJECT_NOTIFICATION</span></span>](status_object_notification.md) <br/> |
|<span data-ttu-id="e91fb-145">**fnevExtended**</span><span class="sxs-lookup"><span data-stu-id="e91fb-145">**fnevExtended**</span></span> <br/> |[<span data-ttu-id="e91fb-146">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e91fb-146">EXTENDED_NOTIFICATION</span></span>](extended_notification.md) <br/> |
   
<span data-ttu-id="e91fb-147">有关如何设置和停止通知的详细信息，请参阅以下接口的任何**Advise**和**Unadvise**方法的参考条目： [IABLogon](iablogoniunknown.md) [IAddrBook](iaddrbookimapiprop.md)、 [IMAPIForm](imapiformiunknown.md)、 [IMAPISession](imapisessioniunknown.md)， [IMAPITable](imapitableiunknown.md)、 [IMsgStore](imsgstoreimapiprop.md)和[IMSLogon](imslogoniunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="e91fb-147">For more information about how to set up and stop notifications, see the reference entries for the **Advise** and **Unadvise** methods for any of the following interfaces: [IABLogon](iablogoniunknown.md), [IAddrBook](iaddrbookimapiprop.md), [IMAPIForm](imapiformiunknown.md), [IMAPISession](imapisessioniunknown.md), [IMAPITable](imapitableiunknown.md), [IMsgStore](imsgstoreimapiprop.md), and [IMSLogon](imslogoniunknown.md).</span></span> 
  
<span data-ttu-id="e91fb-148">有关通知过程的一般信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="e91fb-148">For general information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e91fb-149">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="e91fb-149">Notes to implementers</span></span>

<span data-ttu-id="e91fb-150">**OnNotify**实现通常包含一个或多个您希望接收的通知的每种类型的代码块。</span><span class="sxs-lookup"><span data-stu-id="e91fb-150">Your **OnNotify** implementation will typically consist of one or more blocks of code for each type of notification you expect to receive.</span></span> <span data-ttu-id="e91fb-151">这些的代码块内, 执行考虑作为对通知的响应所需的任何任务。</span><span class="sxs-lookup"><span data-stu-id="e91fb-151">Within these blocks of code, perform any tasks that you consider necessary as a response to the notification.</span></span> <span data-ttu-id="e91fb-152">例如，假设您注册，以接收**fnevObjectModified**通知中显示一个对话框，包含的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e91fb-152">For example, suppose you register to receive **fnevObjectModified** notifications on a folder that is included in a dialog box display.</span></span> <span data-ttu-id="e91fb-153">在包含在**OnNotify**方法来处理**fnevObjectModified**通知中的代码块中，您可能向对话框以请求更新的显示发送 Windows 消息。</span><span class="sxs-lookup"><span data-stu-id="e91fb-153">In the block of code that you include in your **OnNotify** method to handle **fnevObjectModified** notifications, you might send a Windows message to the dialog box to request an updated display.</span></span> 
  
<span data-ttu-id="e91fb-154">无法修改或释放传递给**OnNotify****通知**结构。</span><span class="sxs-lookup"><span data-stu-id="e91fb-154">Do not modify or free the **NOTIFICATION** structure passed to **OnNotify**.</span></span> <span data-ttu-id="e91fb-155">仅**OnNotify**返回之前，结构中的数据有效。</span><span class="sxs-lookup"><span data-stu-id="e91fb-155">The data in the structure is valid only until **OnNotify** returns.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e91fb-156">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e91fb-156">Notes to callers</span></span>

<span data-ttu-id="e91fb-157">与多个对象更改时，您可以通知或多个呼叫，具体取决于内存限制对**OnNotify**的单个调用中注册的通知接收器。</span><span class="sxs-lookup"><span data-stu-id="e91fb-157">When changes occur to multiple objects, you can notify a registered advise sink in a single call to **OnNotify** or in multiple calls depending on memory constraints.</span></span> <span data-ttu-id="e91fb-158">这种情况而不考虑所做的更改是否是一个方法调用或多个结果。</span><span class="sxs-lookup"><span data-stu-id="e91fb-158">This is true regardless of whether the changes are the result of one method call or several.</span></span> <span data-ttu-id="e91fb-159">例如，对[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)调用可影响多个邮件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="e91fb-159">For example, a call to [IMAPIFolder::CopyMessages](imapifolder-copymessages.md) can affect multiple messages and folders.</span></span> <span data-ttu-id="e91fb-160">为消息存储提供程序，您可以一次调用**OnNotify**与**fnevObjectModified**事件类型的目标文件夹或多次调用，一个用于每个影响消息。</span><span class="sxs-lookup"><span data-stu-id="e91fb-160">As a message store provider, you can make one call to **OnNotify** with an **fnevObjectModified** event type for the target folder or many calls, one for each affect messages.</span></span> <span data-ttu-id="e91fb-161">同样，如果客户端发出[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)重复的调用，这些呼叫可以组合到一个**fnevObjectModified**事件文件夹或划分为单个**fnevObjectCreated**事件为每个新消息。</span><span class="sxs-lookup"><span data-stu-id="e91fb-161">Similarly, if a client makes repeated calls to [IMAPIFolder::CreateMessage](imapifolder-createmessage.md), these calls can be combined into one **fnevObjectModified** event for the folder or separated into individual **fnevObjectCreated** events for each new message.</span></span> 
  
<span data-ttu-id="e91fb-162">有关详细了解如何以及何时生成通知，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="e91fb-162">For more information about how and when to generate notifications, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Supporting Event Notification](supporting-event-notification.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e91fb-163">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="e91fb-163">MFCMAPI reference</span></span>

<span data-ttu-id="e91fb-164">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e91fb-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e91fb-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="e91fb-165">**File**</span></span>|<span data-ttu-id="e91fb-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="e91fb-166">**Function**</span></span>|<span data-ttu-id="e91fb-167">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e91fb-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e91fb-168">AdviseSink.h 和 AdviseSink.cpp</span><span class="sxs-lookup"><span data-stu-id="e91fb-168">AdviseSink.h and AdviseSink.cpp</span></span>  <br/> |<span data-ttu-id="e91fb-169">CAdviseSink::OnNotifyDesc</span><span class="sxs-lookup"><span data-stu-id="e91fb-169">CAdviseSink::OnNotifyDesc</span></span>  <br/> |<span data-ttu-id="e91fb-170">CAdviseSink 类实现处理 MFCMAPI 中的所有通知。</span><span class="sxs-lookup"><span data-stu-id="e91fb-170">The CAdviseSink class is implemented to handle all notifications in MFCMAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e91fb-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e91fb-171">See also</span></span>



[<span data-ttu-id="e91fb-172">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="e91fb-172">HrAllocAdviseSink</span></span>](hrallocadvisesink.md)
  
[<span data-ttu-id="e91fb-173">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="e91fb-173">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="e91fb-174">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="e91fb-174">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
  
[<span data-ttu-id="e91fb-175">通知</span><span class="sxs-lookup"><span data-stu-id="e91fb-175">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="e91fb-176">IMAPIAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e91fb-176">IMAPIAdviseSink : IUnknown</span></span>](imapiadvisesinkiunknown.md)


[<span data-ttu-id="e91fb-177">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e91fb-177">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

