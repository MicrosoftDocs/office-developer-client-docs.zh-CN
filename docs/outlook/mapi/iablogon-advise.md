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
# <a name="iablogonadvise"></a><span data-ttu-id="cd7a7-103">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="cd7a7-103">IABLogon::Advise</span></span>

  
  
<span data-ttu-id="cd7a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cd7a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cd7a7-105">注册调用方, 以接收影响容器、邮件用户或通讯组列表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-105">Registers the caller to receive notification of specified events that affect a container, messaging user, or distribution list.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="cd7a7-106">参数</span><span class="sxs-lookup"><span data-stu-id="cd7a7-106">Parameters</span></span>

 <span data-ttu-id="cd7a7-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="cd7a7-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="cd7a7-108">实时由_lpEntryID_参数指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-108">[in] The count of bytes in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="cd7a7-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="cd7a7-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="cd7a7-110">实时一个指针, 指向有关应生成其通知的对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-110">[in] A pointer to the entry identifier of the object about which notifications should be generated.</span></span>
    
 <span data-ttu-id="cd7a7-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="cd7a7-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="cd7a7-112">实时指示呼叫者感兴趣且应包含在注册中的通知事件类型的值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-112">[in] A bitmask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="cd7a7-113">有与每种类型的事件相关联的相应[通知](notification.md)结构, 其中包含有关该事件的信息。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-113">There is a corresponding [NOTIFICATION](notification.md) structure associated with each type of event that holds information about the event.</span></span> <span data-ttu-id="cd7a7-114">下表列出了_ulEventMask_参数的有效值以及与每个值关联的结构。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-114">The following table lists the valid values for the  _ulEventMask_ parameter and the structures associated with each value.</span></span> 
    
|<span data-ttu-id="cd7a7-115">**通知事件类型**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-115">**Notification event type**</span></span>|<span data-ttu-id="cd7a7-116">**相应的**通知**结构**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-116">**Corresponding **NOTIFICATION** structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cd7a7-117">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-117">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="cd7a7-118">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="cd7a7-118">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="cd7a7-119">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-119">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="cd7a7-120">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="cd7a7-120">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="cd7a7-121">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-121">**fnevObjectDeleted**</span></span> <br/> |<span data-ttu-id="cd7a7-122">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-122">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="cd7a7-123">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-123">**fnevObjectModified**</span></span> <br/> |<span data-ttu-id="cd7a7-124">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-124">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="cd7a7-125">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-125">**fnevObjectCopied**</span></span> <br/> |<span data-ttu-id="cd7a7-126">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-126">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="cd7a7-127">**fnevObjectMoved**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-127">**fnevObjectMoved**</span></span> <br/> |<span data-ttu-id="cd7a7-128">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="cd7a7-128">**OBJECT_NOTIFICATION**</span></span> <br/> |
   
 <span data-ttu-id="cd7a7-129">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="cd7a7-129">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="cd7a7-130">实时指向接收后续通知的通知接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-130">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span>
    
 <span data-ttu-id="cd7a7-131">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="cd7a7-131">_lpulConnection_</span></span>
  
> <span data-ttu-id="cd7a7-132">排除指向表示通知注册的非零值的指针。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-132">[out] A pointer to a nonzero value that represents the notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cd7a7-133">返回值</span><span class="sxs-lookup"><span data-stu-id="cd7a7-133">Return value</span></span>

<span data-ttu-id="cd7a7-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd7a7-134">S_OK</span></span> 
  
> <span data-ttu-id="cd7a7-135">通知注册已成功。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-135">The notification registration was successful.</span></span>
    
<span data-ttu-id="cd7a7-136">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="cd7a7-136">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="cd7a7-137">在_lpEntryID_参数中传递的条目标识符的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-137">The entry identifier passed in the  _lpEntryID_ parameter is not in the appropriate format.</span></span> 
    
<span data-ttu-id="cd7a7-138">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="cd7a7-138">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="cd7a7-139">通讯簿提供程序不支持通知, 可能是因为它不允许对其对象进行更改。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-139">The address book provider does not support notification, possibly because it does not allow changes to be made to its objects.</span></span>
    
<span data-ttu-id="cd7a7-140">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="cd7a7-140">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="cd7a7-141">通讯簿提供程序无法处理在_lpEntryID_中传递的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-141">The address book provider cannot handle the entry identifier passed in  _lpEntryID_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cd7a7-142">说明</span><span class="sxs-lookup"><span data-stu-id="cd7a7-142">Remarks</span></span>

<span data-ttu-id="cd7a7-143">通讯簿提供程序实现**IABLogon:: Advise**方法, 以注册呼叫者在其某个容器中的对象发生更改时收到通知。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-143">Address book providers implement the **IABLogon::Advise** method to register the caller to be notified when a change occurs to an object in one of their containers.</span></span> <span data-ttu-id="cd7a7-144">呼叫者可以注册有关邮件用户、通讯组列表或整个容器的通知。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-144">Callers can register for notifications regarding messaging users, distribution lists, or entire containers.</span></span> 
  
<span data-ttu-id="cd7a7-145">客户端通常调用[IAddrBook:: Advise](iaddrbook-advise.md)方法注册通讯簿通知。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-145">Clients typically call the [IAddrBook::Advise](iaddrbook-advise.md) method to register for address book notifications.</span></span> <span data-ttu-id="cd7a7-146">然后, MAPI 调用通讯簿提供程序的**Advise**方法, 该提供程序负责_lpEntryID_中的条目标识符所代表的对象。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-146">MAPI then calls the **Advise** method of the address book provider that is responsible for the object represented by the entry identifier in  _lpEntryID_.</span></span>
  
<span data-ttu-id="cd7a7-147">当_ulEventMask_中表示的类型的指定对象发生更改时, 将对_lpAdviseSink_所指向的通知接收器的**OnNotify**方法进行调用。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-147">When a change occurs to the indicated object of the type represented in  _ulEventMask_, a call is made to the **OnNotify** method of the advise sink pointed to by  _lpAdviseSink_.</span></span> <span data-ttu-id="cd7a7-148">**通知**结构中传递给**OnNotify**例程的数据描述了该事件。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-148">Data passed in the **NOTIFICATION** structure to the **OnNotify** routine describes the event.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="cd7a7-149">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="cd7a7-149">Notes to implementers</span></span>

<span data-ttu-id="cd7a7-150">你可以在 MAPI 中支持带有或没有帮助的通知。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-150">You can support notification with or without help from MAPI.</span></span> <span data-ttu-id="cd7a7-151">MAPI 具有三个用于帮助服务提供程序实现通知的支持对象方法:</span><span class="sxs-lookup"><span data-stu-id="cd7a7-151">MAPI has three support object methods to help service providers implement notification:</span></span>
  
- [<span data-ttu-id="cd7a7-152">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="cd7a7-152">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)
    
- [<span data-ttu-id="cd7a7-153">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="cd7a7-153">IMAPISupport::Unsubscribe</span></span>](imapisupport-unsubscribe.md)
    
- [<span data-ttu-id="cd7a7-154">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="cd7a7-154">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
    
<span data-ttu-id="cd7a7-155">如果选择使用 MAPI 支持方法, 请在调用**Advise**方法时呼叫**订阅**, 并释放_lpAdviseSink_指针。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-155">If you elect to use the MAPI support methods, call **Subscribe** when your **Advise** method is called and release the  _lpAdviseSink_ pointer.</span></span> 
  
<span data-ttu-id="cd7a7-156">如果选择自己支持通知, 请调用由_lpAdviseSink_参数表示的通知接收器的**AddRef**方法, 以保留此指针的副本。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-156">If you elect to support notification yourself, call the **AddRef** method of the advise sink represented by the  _lpAdviseSink_ parameter to keep a copy of this pointer.</span></span> <span data-ttu-id="cd7a7-157">维护此副本, 直到调用[IABLogon:: Unadvise](iablogon-unadvise.md)方法以取消注册。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-157">Maintain this copy until your [IABLogon::Unadvise](iablogon-unadvise.md) method is called to cancel the registration.</span></span> 
  
<span data-ttu-id="cd7a7-158">无论您如何支持通知, 请为通知注册分配非零连接号码, 并将其返回到_lpulConnection_参数中。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-158">Regardless of how you support notification, assign a nonzero connection number to the notification registration and return it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="cd7a7-159">在调用**Unadvise**方法之前, 请勿释放此连接号码。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-159">Do not release this connection number until the **Unadvise** method has been called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="cd7a7-160">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="cd7a7-160">Notes to callers</span></span>

<span data-ttu-id="cd7a7-161">您在_lpAdviseSink_参数中传递给**建议**的建议接收器指针可指向您创建的对象, 或者 MAPI 已通过[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数创建。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-161">The advise sink pointer that you pass in the  _lpAdviseSink_ parameter to **Advise** can point to an object that you have created or that MAPI has created through the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> <span data-ttu-id="cd7a7-162">如果您支持多个执行线程, 并且想确保对您的**OnNotify**方法的后续调用在适当的线程上的适当时间发生, 则您可能需要使用**HrThisThreadAdviseSink** 。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-162">You might want to use **HrThisThreadAdviseSink** if you support multiple threads of execution and want to be sure that that subsequent calls to your **OnNotify** method occur at an appropriate time on an appropriate thread.</span></span> 
  
<span data-ttu-id="cd7a7-163">在调用 " **Unadvise**" 之前, 请先为您的建议接收器对象做好\*\*\*\* 准备, 以随时释放通知对象。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-163">Be prepared for your advise sink object to be released any time after your call to **Advise** and before your call to **Unadvise**.</span></span> <span data-ttu-id="cd7a7-164">因此, 您应在**建议**返回后释放您的建议接收器对象, 除非您对其有特定的长期使用。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-164">Therefore, you should release your advise sink object after **Advise** returns, unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="cd7a7-165">有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-165">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="cd7a7-166">有关如何使用**IMAPISupport**方法支持通知的信息, 请参阅[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-166">For information about how to use the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span> <span data-ttu-id="cd7a7-167">有关多线程和 MAPI 的详细信息, 请参阅[MAPI 中的线程处理](threading-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7a7-167">For more information about multithreading and MAPI, see [Threading in MAPI](threading-in-mapi.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cd7a7-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd7a7-168">See also</span></span>



[<span data-ttu-id="cd7a7-169">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="cd7a7-169">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="cd7a7-170">IABLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="cd7a7-170">IABLogon::Unadvise</span></span>](iablogon-unadvise.md)
  
[<span data-ttu-id="cd7a7-171">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="cd7a7-171">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="cd7a7-172">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="cd7a7-172">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="cd7a7-173">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="cd7a7-173">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

