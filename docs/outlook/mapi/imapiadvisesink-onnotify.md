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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351441"
---
# <a name="imapiadvisesinkonnotify"></a><span data-ttu-id="2facf-103">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="2facf-103">IMAPIAdviseSink::OnNotify</span></span>

  
  
<span data-ttu-id="2facf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2facf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2facf-105">通过执行一个或多个任务来响应通知。</span><span class="sxs-lookup"><span data-stu-id="2facf-105">Responds to a notification by performing one or more tasks.</span></span> <span data-ttu-id="2facf-106">执行的任务取决于事件的类型和生成通知的对象。</span><span class="sxs-lookup"><span data-stu-id="2facf-106">The tasks performed depend on the type of event and the object that generates the notification.</span></span> 
  
```cpp
ULONG OnNotify(
  ULONG cNotif,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a><span data-ttu-id="2facf-107">参数</span><span class="sxs-lookup"><span data-stu-id="2facf-107">Parameters</span></span>

 <span data-ttu-id="2facf-108">_cNotif_</span><span class="sxs-lookup"><span data-stu-id="2facf-108">_cNotif_</span></span>
  
> <span data-ttu-id="2facf-109">实时由_lpNotifications_参数指向的[通知](notification.md)结构的计数。</span><span class="sxs-lookup"><span data-stu-id="2facf-109">[in] The count of [NOTIFICATION](notification.md) structures pointed to by the  _lpNotifications_ parameter.</span></span> 
    
 <span data-ttu-id="2facf-110">_lpNotifications_</span><span class="sxs-lookup"><span data-stu-id="2facf-110">_lpNotifications_</span></span>
  
> <span data-ttu-id="2facf-111">实时指向一个或多个通知结构的指针, 这些**通知**结构提供有关已发生事件的信息。</span><span class="sxs-lookup"><span data-stu-id="2facf-111">[in] A pointer to one or more **NOTIFICATION** structures that provide information about the events that have occurred.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2facf-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2facf-112">Return value</span></span>

<span data-ttu-id="2facf-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2facf-113">S_OK</span></span> 
  
> <span data-ttu-id="2facf-114">已成功处理通知。</span><span class="sxs-lookup"><span data-stu-id="2facf-114">The notification was processed successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2facf-115">注解</span><span class="sxs-lookup"><span data-stu-id="2facf-115">Remarks</span></span>

<span data-ttu-id="2facf-116">当客户端或 MAPI 对服务提供商的**建议**方法进行注册以接收特定对象的特定类型通知时, 将启动通知过程。</span><span class="sxs-lookup"><span data-stu-id="2facf-116">The notification process starts when a client or MAPI makes a call to a service provider's **Advise** method to register to receive a notification of a particular type for a particular object.</span></span> <span data-ttu-id="2facf-117">**advise**方法的一个参数是指向实现[IMAPIAdviseSink](imapiadvisesinkiunknown.md)接口的通知接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2facf-117">One of the parameters to the **Advise** method is a pointer to an advise sink object that implements the [IMAPIAdviseSink](imapiadvisesinkiunknown.md) interface.</span></span> <span data-ttu-id="2facf-118">当与已注册的通知相对应的目标对象发生事件时, 服务提供程序可以通过 MAPI 直接或间接地调用通知接收器的**OnNotify**方法。</span><span class="sxs-lookup"><span data-stu-id="2facf-118">When an event occurs to the target object that corresponds to the registered notification, the service provider, either directly or indirectly through MAPI, calls the advise sink's **OnNotify** method.</span></span> 
  
<span data-ttu-id="2facf-119">对**OnNotify**的调用可能发生在导致事件的 MAPI 调用过程中或稍后某个时候。</span><span class="sxs-lookup"><span data-stu-id="2facf-119">The call to **OnNotify** can occur either during the MAPI call that is causing the event or at some later time.</span></span> <span data-ttu-id="2facf-120">在支持多个执行线程的系统上, 可以在用于注册的同一线程或在不同的线程上调用**OnNotify** 。</span><span class="sxs-lookup"><span data-stu-id="2facf-120">On systems that support multiple threads of execution, **OnNotify** can be called either on the same thread that was used for registration or on a different thread.</span></span> <span data-ttu-id="2facf-121">客户端可以通过创建其传递给**建议**使用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数的通知接收器来确保对用于呼叫**通知**的同一线程进行**OnNotify**调用。</span><span class="sxs-lookup"><span data-stu-id="2facf-121">Clients can make sure that the **OnNotify** call is made on the same thread used to call **Advise** by creating the advise sink that they pass to **Advise** with the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> 
  
<span data-ttu-id="2facf-122">_lpNotifications_参数指向一个或多个**通知**结构, 用于描述事件过程中发生了更改的内容。</span><span class="sxs-lookup"><span data-stu-id="2facf-122">The  _lpNotifications_ parameter points to one or more **NOTIFICATION** structures that describe what has changed during the event.</span></span> <span data-ttu-id="2facf-123">每种类型的事件都有不同类型的**通知**结构。</span><span class="sxs-lookup"><span data-stu-id="2facf-123">There is a different type of **NOTIFICATION** structure for each type of event.</span></span> 
  
<span data-ttu-id="2facf-124">下表列出了用于表示可能的事件类型的值, 以及与每个值关联的结构:</span><span class="sxs-lookup"><span data-stu-id="2facf-124">The following table lists the values that are used to represent the possible types of events and the structures associated with each value:</span></span>
  
|<span data-ttu-id="2facf-125">**通知事件类型**</span><span class="sxs-lookup"><span data-stu-id="2facf-125">**Notification event type**</span></span>|<span data-ttu-id="2facf-126">**对应的结构**</span><span class="sxs-lookup"><span data-stu-id="2facf-126">**Corresponding structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2facf-127">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="2facf-127">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="2facf-128">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-128">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="2facf-129">**fnevNewMail**</span><span class="sxs-lookup"><span data-stu-id="2facf-129">**fnevNewMail**</span></span> <br/> |[<span data-ttu-id="2facf-130">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-130">NEWMAIL_NOTIFICATION</span></span>](newmail_notification.md) <br/> |
|<span data-ttu-id="2facf-131">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="2facf-131">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="2facf-132">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-132">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="2facf-133">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="2facf-133">**fnevObjectDeleted**</span></span> <br/> |[<span data-ttu-id="2facf-134">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-134">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="2facf-135">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="2facf-135">**fnevObjectModified**</span></span> <br/> |[<span data-ttu-id="2facf-136">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-136">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="2facf-137">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="2facf-137">**fnevObjectCopied**</span></span> <br/> |[<span data-ttu-id="2facf-138">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-138">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="2facf-139">**fnevSearchComplete**</span><span class="sxs-lookup"><span data-stu-id="2facf-139">**fnevSearchComplete**</span></span> <br/> |[<span data-ttu-id="2facf-140">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-140">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="2facf-141">**fnevTableModified**</span><span class="sxs-lookup"><span data-stu-id="2facf-141">**fnevTableModified**</span></span> <br/> |[<span data-ttu-id="2facf-142">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-142">TABLE_NOTIFICATION</span></span>](table_notification.md) <br/> |
|<span data-ttu-id="2facf-143">**fnevStatusObjectModified**</span><span class="sxs-lookup"><span data-stu-id="2facf-143">**fnevStatusObjectModified**</span></span> <br/> |[<span data-ttu-id="2facf-144">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-144">STATUS_OBJECT_NOTIFICATION</span></span>](status_object_notification.md) <br/> |
|<span data-ttu-id="2facf-145">**fnevExtended**</span><span class="sxs-lookup"><span data-stu-id="2facf-145">**fnevExtended**</span></span> <br/> |[<span data-ttu-id="2facf-146">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-146">EXTENDED_NOTIFICATION</span></span>](extended_notification.md) <br/> |
   
<span data-ttu-id="2facf-147">有关如何设置和停止通知的详细信息, 请参阅适用于以下任何接口的**Advise**和**Unadvise**方法的引用条目: [IABLogon](iablogoniunknown.md)、 [IAddrBook](iaddrbookimapiprop.md)、 [IMAPIForm](imapiformiunknown.md)、 [IMAPISession](imapisessioniunknown.md)、 [IMAPITable](imapitableiunknown.md)、 [IMsgStore](imsgstoreimapiprop.md)和[IMSLogon](imslogoniunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="2facf-147">For more information about how to set up and stop notifications, see the reference entries for the **Advise** and **Unadvise** methods for any of the following interfaces: [IABLogon](iablogoniunknown.md), [IAddrBook](iaddrbookimapiprop.md), [IMAPIForm](imapiformiunknown.md), [IMAPISession](imapisessioniunknown.md), [IMAPITable](imapitableiunknown.md), [IMsgStore](imsgstoreimapiprop.md), and [IMSLogon](imslogoniunknown.md).</span></span> 
  
<span data-ttu-id="2facf-148">有关通知过程的一般信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="2facf-148">For general information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2facf-149">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="2facf-149">Notes to implementers</span></span>

<span data-ttu-id="2facf-150">您的**OnNotify**实现通常由您预期收到的每种类型的通知的一个或多个代码块组成。</span><span class="sxs-lookup"><span data-stu-id="2facf-150">Your **OnNotify** implementation will typically consist of one or more blocks of code for each type of notification you expect to receive.</span></span> <span data-ttu-id="2facf-151">在这些代码块中, 执行您认为是对通知的响应所需的任何任务。</span><span class="sxs-lookup"><span data-stu-id="2facf-151">Within these blocks of code, perform any tasks that you consider necessary as a response to the notification.</span></span> <span data-ttu-id="2facf-152">例如, 假设您注册接收在对话框显示中包含的文件夹上的**fnevObjectModified**通知。</span><span class="sxs-lookup"><span data-stu-id="2facf-152">For example, suppose you register to receive **fnevObjectModified** notifications on a folder that is included in a dialog box display.</span></span> <span data-ttu-id="2facf-153">在**OnNotify**方法中包含的代码块中, 若要处理**fnevObjectModified**通知, 您可能会将 Windows 消息发送到对话框, 以请求更新的显示。</span><span class="sxs-lookup"><span data-stu-id="2facf-153">In the block of code that you include in your **OnNotify** method to handle **fnevObjectModified** notifications, you might send a Windows message to the dialog box to request an updated display.</span></span> 
  
<span data-ttu-id="2facf-154">请勿修改或释放传递给**OnNotify**的**通知**结构。</span><span class="sxs-lookup"><span data-stu-id="2facf-154">Do not modify or free the **NOTIFICATION** structure passed to **OnNotify**.</span></span> <span data-ttu-id="2facf-155">结构中的数据仅在**OnNotify**返回之前有效。</span><span class="sxs-lookup"><span data-stu-id="2facf-155">The data in the structure is valid only until **OnNotify** returns.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="2facf-156">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2facf-156">Notes to callers</span></span>

<span data-ttu-id="2facf-157">当多个对象发生更改时, 您可以在对**OnNotify**或多个调用中的一次调用中通知已注册的通知接收器, 具体取决于内存约束。</span><span class="sxs-lookup"><span data-stu-id="2facf-157">When changes occur to multiple objects, you can notify a registered advise sink in a single call to **OnNotify** or in multiple calls depending on memory constraints.</span></span> <span data-ttu-id="2facf-158">无论更改是一个方法调用的结果还是多个, 都是如此。</span><span class="sxs-lookup"><span data-stu-id="2facf-158">This is true regardless of whether the changes are the result of one method call or several.</span></span> <span data-ttu-id="2facf-159">例如, 对[IMAPIFolder:: CopyMessages](imapifolder-copymessages.md)的调用可能会影响多个邮件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="2facf-159">For example, a call to [IMAPIFolder::CopyMessages](imapifolder-copymessages.md) can affect multiple messages and folders.</span></span> <span data-ttu-id="2facf-160">作为邮件存储提供程序, 您可以使用目标文件夹的**fnevObjectModified**事件类型或多个调用 (一个针对每个邮件的影响) 对**OnNotify**调用一个调用。</span><span class="sxs-lookup"><span data-stu-id="2facf-160">As a message store provider, you can make one call to **OnNotify** with an **fnevObjectModified** event type for the target folder or many calls, one for each affect messages.</span></span> <span data-ttu-id="2facf-161">同样, 如果客户端再次调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md), 则这些调用可以合并到文件夹的一个**fnevObjectModified**事件中, 也可以分隔到每个新邮件的单个**fnevObjectCreated**事件中。</span><span class="sxs-lookup"><span data-stu-id="2facf-161">Similarly, if a client makes repeated calls to [IMAPIFolder::CreateMessage](imapifolder-createmessage.md), these calls can be combined into one **fnevObjectModified** event for the folder or separated into individual **fnevObjectCreated** events for each new message.</span></span> 
  
<span data-ttu-id="2facf-162">有关如何以及何时生成通知的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="2facf-162">For more information about how and when to generate notifications, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Supporting Event Notification](supporting-event-notification.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2facf-163">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="2facf-163">MFCMAPI reference</span></span>

<span data-ttu-id="2facf-164">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2facf-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2facf-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="2facf-165">**File**</span></span>|<span data-ttu-id="2facf-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="2facf-166">**Function**</span></span>|<span data-ttu-id="2facf-167">**备注**</span><span class="sxs-lookup"><span data-stu-id="2facf-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2facf-168">AdviseSink 和 AdviseSink</span><span class="sxs-lookup"><span data-stu-id="2facf-168">AdviseSink.h and AdviseSink.cpp</span></span>  <br/> |<span data-ttu-id="2facf-169">CAdviseSink:: OnNotifyDesc</span><span class="sxs-lookup"><span data-stu-id="2facf-169">CAdviseSink::OnNotifyDesc</span></span>  <br/> |<span data-ttu-id="2facf-170">实现 CAdviseSink 类以处理 MFCMAPI 中的所有通知。</span><span class="sxs-lookup"><span data-stu-id="2facf-170">The CAdviseSink class is implemented to handle all notifications in MFCMAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2facf-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2facf-171">See also</span></span>



[<span data-ttu-id="2facf-172">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="2facf-172">HrAllocAdviseSink</span></span>](hrallocadvisesink.md)
  
[<span data-ttu-id="2facf-173">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="2facf-173">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="2facf-174">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="2facf-174">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
  
[<span data-ttu-id="2facf-175">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="2facf-175">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="2facf-176">IMAPIAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2facf-176">IMAPIAdviseSink : IUnknown</span></span>](imapiadvisesinkiunknown.md)


[<span data-ttu-id="2facf-177">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2facf-177">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

