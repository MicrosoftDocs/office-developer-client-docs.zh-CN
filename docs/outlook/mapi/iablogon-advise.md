---
title: IABLogonAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.Advise
api_type:
- COM
ms.assetid: 375d65b1-607d-4e2a-8052-9bcbf08fc2ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4ab0e4b023e6af19f650abf421aed122dcc21879
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428226"
---
# <a name="iablogonadvise"></a><span data-ttu-id="58ad5-103">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="58ad5-103">IABLogon::Advise</span></span>

  
  
<span data-ttu-id="58ad5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58ad5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58ad5-105">注册呼叫者以接收影响容器、消息传送用户或通讯组列表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="58ad5-105">Registers the caller to receive notification of specified events that affect a container, messaging user, or distribution list.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="58ad5-106">参数</span><span class="sxs-lookup"><span data-stu-id="58ad5-106">Parameters</span></span>

 <span data-ttu-id="58ad5-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="58ad5-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="58ad5-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="58ad5-108">[in] The count of bytes in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="58ad5-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="58ad5-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="58ad5-110">[in]指向应生成通知的对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="58ad5-110">[in] A pointer to the entry identifier of the object about which notifications should be generated.</span></span>
    
 <span data-ttu-id="58ad5-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="58ad5-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="58ad5-112">[in]指示调用方感兴趣的通知事件类型且应包含在注册中的值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="58ad5-112">[in] A bitmask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="58ad5-113">有一个与 [每种](notification.md) 事件类型关联的相应 NOTIFICATION 结构，用于保存有关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="58ad5-113">There is a corresponding [NOTIFICATION](notification.md) structure associated with each type of event that holds information about the event.</span></span> <span data-ttu-id="58ad5-114">下表列出了  _ulEventMask_ 参数的有效值以及与每个值关联的结构。</span><span class="sxs-lookup"><span data-stu-id="58ad5-114">The following table lists the valid values for the  _ulEventMask_ parameter and the structures associated with each value.</span></span> 
    
|<span data-ttu-id="58ad5-115">**通知事件类型**</span><span class="sxs-lookup"><span data-stu-id="58ad5-115">**Notification event type**</span></span>|<span data-ttu-id="58ad5-116">**相应的 **NOTIFICATION** 结构**</span><span class="sxs-lookup"><span data-stu-id="58ad5-116">**Corresponding **NOTIFICATION** structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58ad5-117">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="58ad5-117">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="58ad5-118">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="58ad5-118">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="58ad5-119">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="58ad5-119">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="58ad5-120">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="58ad5-120">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="58ad5-121">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="58ad5-121">**fnevObjectDeleted**</span></span> <br/> |<span data-ttu-id="58ad5-122">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="58ad5-122">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="58ad5-123">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="58ad5-123">**fnevObjectModified**</span></span> <br/> |<span data-ttu-id="58ad5-124">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="58ad5-124">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="58ad5-125">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="58ad5-125">**fnevObjectCopied**</span></span> <br/> |<span data-ttu-id="58ad5-126">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="58ad5-126">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="58ad5-127">**fnevObjectMoved**</span><span class="sxs-lookup"><span data-stu-id="58ad5-127">**fnevObjectMoved**</span></span> <br/> |<span data-ttu-id="58ad5-128">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="58ad5-128">**OBJECT_NOTIFICATION**</span></span> <br/> |
   
 <span data-ttu-id="58ad5-129">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="58ad5-129">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="58ad5-130">[in]指向通知接收接收对象以接收后续通知的指针。</span><span class="sxs-lookup"><span data-stu-id="58ad5-130">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span>
    
 <span data-ttu-id="58ad5-131">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="58ad5-131">_lpulConnection_</span></span>
  
> <span data-ttu-id="58ad5-132">[out]指向表示通知注册的非零值的指针。</span><span class="sxs-lookup"><span data-stu-id="58ad5-132">[out] A pointer to a nonzero value that represents the notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="58ad5-133">返回值</span><span class="sxs-lookup"><span data-stu-id="58ad5-133">Return value</span></span>

<span data-ttu-id="58ad5-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="58ad5-134">S_OK</span></span> 
  
> <span data-ttu-id="58ad5-135">通知注册成功。</span><span class="sxs-lookup"><span data-stu-id="58ad5-135">The notification registration was successful.</span></span>
    
<span data-ttu-id="58ad5-136">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="58ad5-136">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="58ad5-137">在  _lpEntryID_ 参数中传递的条目标识符格式不适当。</span><span class="sxs-lookup"><span data-stu-id="58ad5-137">The entry identifier passed in the  _lpEntryID_ parameter is not in the appropriate format.</span></span> 
    
<span data-ttu-id="58ad5-138">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="58ad5-138">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="58ad5-139">通讯簿提供程序不支持通知，可能是因为它不允许更改其对象。</span><span class="sxs-lookup"><span data-stu-id="58ad5-139">The address book provider does not support notification, possibly because it does not allow changes to be made to its objects.</span></span>
    
<span data-ttu-id="58ad5-140">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="58ad5-140">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="58ad5-141">通讯簿提供程序无法处理在  _lpEntryID 中传递的条目标识符_。</span><span class="sxs-lookup"><span data-stu-id="58ad5-141">The address book provider cannot handle the entry identifier passed in  _lpEntryID_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="58ad5-142">备注</span><span class="sxs-lookup"><span data-stu-id="58ad5-142">Remarks</span></span>

<span data-ttu-id="58ad5-143">通讯簿提供程序实现 **IABLogon：：Advise** 方法，以注册呼叫者，以在对象其中一个容器中发生更改时收到通知。</span><span class="sxs-lookup"><span data-stu-id="58ad5-143">Address book providers implement the **IABLogon::Advise** method to register the caller to be notified when a change occurs to an object in one of their containers.</span></span> <span data-ttu-id="58ad5-144">呼叫者可以注册有关邮件用户、通讯组列表或整个容器的通知。</span><span class="sxs-lookup"><span data-stu-id="58ad5-144">Callers can register for notifications regarding messaging users, distribution lists, or entire containers.</span></span> 
  
<span data-ttu-id="58ad5-145">客户端通常调用 [IAddrBook：：Advise](iaddrbook-advise.md) 方法来注册通讯簿通知。</span><span class="sxs-lookup"><span data-stu-id="58ad5-145">Clients typically call the [IAddrBook::Advise](iaddrbook-advise.md) method to register for address book notifications.</span></span> <span data-ttu-id="58ad5-146">然后，MAPI 调用通讯簿提供程序的 **Advise** 方法，该通讯簿提供程序负责  _由 lpEntryID_ 中的条目标识符表示的对象。</span><span class="sxs-lookup"><span data-stu-id="58ad5-146">MAPI then calls the **Advise** method of the address book provider that is responsible for the object represented by the entry identifier in  _lpEntryID_.</span></span>
  
<span data-ttu-id="58ad5-147">当 _对 ulEventMask_ 中表示的类型所指示的对象发生更改时，将调用 _lpAdviseSink_ 指向的建议接收器的 **OnNotify** 方法。</span><span class="sxs-lookup"><span data-stu-id="58ad5-147">When a change occurs to the indicated object of the type represented in  _ulEventMask_, a call is made to the **OnNotify** method of the advise sink pointed to by  _lpAdviseSink_.</span></span> <span data-ttu-id="58ad5-148">在 NOTIFICATION **结构中传递给** **OnNotify** 例程的数据描述事件。</span><span class="sxs-lookup"><span data-stu-id="58ad5-148">Data passed in the **NOTIFICATION** structure to the **OnNotify** routine describes the event.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="58ad5-149">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="58ad5-149">Notes to implementers</span></span>

<span data-ttu-id="58ad5-150">在 MAPI 的帮助下，你都可以支持通知，也可以不提供帮助。</span><span class="sxs-lookup"><span data-stu-id="58ad5-150">You can support notification with or without help from MAPI.</span></span> <span data-ttu-id="58ad5-151">MAPI 具有三种支持对象方法，可帮助服务提供商实现通知：</span><span class="sxs-lookup"><span data-stu-id="58ad5-151">MAPI has three support object methods to help service providers implement notification:</span></span>
  
- [<span data-ttu-id="58ad5-152">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="58ad5-152">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)
    
- [<span data-ttu-id="58ad5-153">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="58ad5-153">IMAPISupport::Unsubscribe</span></span>](imapisupport-unsubscribe.md)
    
- [<span data-ttu-id="58ad5-154">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="58ad5-154">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
    
<span data-ttu-id="58ad5-155">如果选择使用 MAPI 支持方法，在 **调用 Advise** 方法时调用 **Subscribe** 并释放 _lpAdviseSink_ 指针。</span><span class="sxs-lookup"><span data-stu-id="58ad5-155">If you elect to use the MAPI support methods, call **Subscribe** when your **Advise** method is called and release the  _lpAdviseSink_ pointer.</span></span> 
  
<span data-ttu-id="58ad5-156">如果选择自己支持通知，请调用 _由 lpAdviseSink_ 参数表示的建议接收器的 **AddRef** 方法以保留此指针的副本。</span><span class="sxs-lookup"><span data-stu-id="58ad5-156">If you elect to support notification yourself, call the **AddRef** method of the advise sink represented by the  _lpAdviseSink_ parameter to keep a copy of this pointer.</span></span> <span data-ttu-id="58ad5-157">保留此副本， [直到调用 IABLogon：：Unadvise](iablogon-unadvise.md) 方法来取消注册。</span><span class="sxs-lookup"><span data-stu-id="58ad5-157">Maintain this copy until your [IABLogon::Unadvise](iablogon-unadvise.md) method is called to cancel the registration.</span></span> 
  
<span data-ttu-id="58ad5-158">无论您如何支持通知，都将非零连接号分配给通知注册，并将其返回到  _lpulConnection_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="58ad5-158">Regardless of how you support notification, assign a nonzero connection number to the notification registration and return it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="58ad5-159">在调用 **Unadvise** 方法之前不要释放此连接号。</span><span class="sxs-lookup"><span data-stu-id="58ad5-159">Do not release this connection number until the **Unadvise** method has been called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="58ad5-160">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="58ad5-160">Notes to callers</span></span>

<span data-ttu-id="58ad5-161">将  _lpAdviseSink_ 参数传递给 **Advise** 的建议接收器指针可以指向已创建的对象或 MAPI 通过 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数创建的对象。</span><span class="sxs-lookup"><span data-stu-id="58ad5-161">The advise sink pointer that you pass in the  _lpAdviseSink_ parameter to **Advise** can point to an object that you have created or that MAPI has created through the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> <span data-ttu-id="58ad5-162">如果您支持多个执行线程，并且希望确保对 **OnNotify** 方法的后续调用在相应线程上的合适时间发生，您可能需要使用 **HrThisThreadAdviseSink。**</span><span class="sxs-lookup"><span data-stu-id="58ad5-162">You might want to use **HrThisThreadAdviseSink** if you support multiple threads of execution and want to be sure that that subsequent calls to your **OnNotify** method occur at an appropriate time on an appropriate thread.</span></span> 
  
<span data-ttu-id="58ad5-163">准备好在调用 **Advise** 之后和调用 **Unadvise** 之前随时释放建议接收对象。</span><span class="sxs-lookup"><span data-stu-id="58ad5-163">Be prepared for your advise sink object to be released any time after your call to **Advise** and before your call to **Unadvise**.</span></span> <span data-ttu-id="58ad5-164">因此，您应在 **Advise** 返回后释放通知接收器对象，除非您具有特定的长期用途。</span><span class="sxs-lookup"><span data-stu-id="58ad5-164">Therefore, you should release your advise sink object after **Advise** returns, unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="58ad5-165">有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="58ad5-165">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="58ad5-166">有关如何使用 **IMAPISupport** 方法支持通知的信息，请参阅 [Supporting Event Notification。](supporting-event-notification.md)</span><span class="sxs-lookup"><span data-stu-id="58ad5-166">For information about how to use the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span> <span data-ttu-id="58ad5-167">有关多线程和 MAPI 的信息，请参阅 [MAPI 中的线程](threading-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="58ad5-167">For more information about multithreading and MAPI, see [Threading in MAPI](threading-in-mapi.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58ad5-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58ad5-168">See also</span></span>



[<span data-ttu-id="58ad5-169">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="58ad5-169">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="58ad5-170">IABLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="58ad5-170">IABLogon::Unadvise</span></span>](iablogon-unadvise.md)
  
[<span data-ttu-id="58ad5-171">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="58ad5-171">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="58ad5-172">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="58ad5-172">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="58ad5-173">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="58ad5-173">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

