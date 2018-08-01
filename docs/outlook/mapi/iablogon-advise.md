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
ms.openlocfilehash: 926fef0e1b2f905d510102e69afb667414e6cce3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775224"
---
# <a name="iablogonadvise"></a><span data-ttu-id="edfcb-103">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="edfcb-103">IABLogon::Advise</span></span>

  
  
<span data-ttu-id="edfcb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="edfcb-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="edfcb-105">注册呼叫者接收影响的容器，消息用户或通讯组列表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="edfcb-105">Registers the caller to receive notification of specified events that affect a container, messaging user, or distribution list.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="edfcb-106">参数</span><span class="sxs-lookup"><span data-stu-id="edfcb-106">Parameters</span></span>

 <span data-ttu-id="edfcb-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="edfcb-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="edfcb-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="edfcb-108">[in] The count of bytes in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="edfcb-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="edfcb-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="edfcb-110">[in]指向有关哪些应生成通知的对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="edfcb-110">[in] A pointer to the entry identifier of the object about which notifications should be generated.</span></span>
    
 <span data-ttu-id="edfcb-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="edfcb-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="edfcb-112">[in]指示呼叫者感兴趣，并应包含在注册通知事件的类型的值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="edfcb-112">[in] A bitmask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="edfcb-113">没有相应的[通知](notification.md)结构，每种类型的包含有关事件的信息的事件相关联。</span><span class="sxs-lookup"><span data-stu-id="edfcb-113">There is a corresponding [NOTIFICATION](notification.md) structure associated with each type of event that holds information about the event.</span></span> <span data-ttu-id="edfcb-114">下表列出的有效值_ulEventMask_参数和与每个值的结构。</span><span class="sxs-lookup"><span data-stu-id="edfcb-114">The following table lists the valid values for the  _ulEventMask_ parameter and the structures associated with each value.</span></span> 
    
|<span data-ttu-id="edfcb-115">**通知事件类型**</span><span class="sxs-lookup"><span data-stu-id="edfcb-115">**Notification event type**</span></span>|<span data-ttu-id="edfcb-116">**相应的**通知**结构**</span><span class="sxs-lookup"><span data-stu-id="edfcb-116">**Corresponding **NOTIFICATION** structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="edfcb-117">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="edfcb-117">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="edfcb-118">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="edfcb-118">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="edfcb-119">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="edfcb-119">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="edfcb-120">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="edfcb-120">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="edfcb-121">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="edfcb-121">**fnevObjectDeleted**</span></span> <br/> |<span data-ttu-id="edfcb-122">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="edfcb-122">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="edfcb-123">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="edfcb-123">**fnevObjectModified**</span></span> <br/> |<span data-ttu-id="edfcb-124">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="edfcb-124">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="edfcb-125">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="edfcb-125">**fnevObjectCopied**</span></span> <br/> |<span data-ttu-id="edfcb-126">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="edfcb-126">**OBJECT_NOTIFICATION**</span></span> <br/> |
|<span data-ttu-id="edfcb-127">**fnevObjectMoved**</span><span class="sxs-lookup"><span data-stu-id="edfcb-127">**fnevObjectMoved**</span></span> <br/> |<span data-ttu-id="edfcb-128">**OBJECT_NOTIFICATION**</span><span class="sxs-lookup"><span data-stu-id="edfcb-128">**OBJECT_NOTIFICATION**</span></span> <br/> |
   
 <span data-ttu-id="edfcb-129">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="edfcb-129">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="edfcb-130">[in]指向要接收随后进行通知 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="edfcb-130">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span>
    
 <span data-ttu-id="edfcb-131">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="edfcb-131">_lpulConnection_</span></span>
  
> <span data-ttu-id="edfcb-132">[输出]指向为非零值，该值代表通知注册的指针。</span><span class="sxs-lookup"><span data-stu-id="edfcb-132">[out] A pointer to a nonzero value that represents the notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="edfcb-133">返回值</span><span class="sxs-lookup"><span data-stu-id="edfcb-133">Return value</span></span>

<span data-ttu-id="edfcb-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="edfcb-134">S_OK</span></span> 
  
> <span data-ttu-id="edfcb-135">通知注册成功。</span><span class="sxs-lookup"><span data-stu-id="edfcb-135">The notification registration was successful.</span></span>
    
<span data-ttu-id="edfcb-136">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="edfcb-136">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="edfcb-137">_LpEntryID_参数中传递的项标识符不在适当的格式。</span><span class="sxs-lookup"><span data-stu-id="edfcb-137">The entry identifier passed in the  _lpEntryID_ parameter is not in the appropriate format.</span></span> 
    
<span data-ttu-id="edfcb-138">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="edfcb-138">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="edfcb-139">通讯簿提供程序不支持通知，原因可能是因为它不允许将对其对象进行更改。</span><span class="sxs-lookup"><span data-stu-id="edfcb-139">The address book provider does not support notification, possibly because it does not allow changes to be made to its objects.</span></span>
    
<span data-ttu-id="edfcb-140">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="edfcb-140">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="edfcb-141">通讯簿提供程序无法处理_lpEntryID_中传递的项标识符。</span><span class="sxs-lookup"><span data-stu-id="edfcb-141">The address book provider cannot handle the entry identifier passed in  _lpEntryID_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="edfcb-142">说明</span><span class="sxs-lookup"><span data-stu-id="edfcb-142">Remarks</span></span>

<span data-ttu-id="edfcb-143">通讯簿提供程序实现**IABLogon::Advise**方法注册呼叫者到其容器之一对象发生更改时收到通知。</span><span class="sxs-lookup"><span data-stu-id="edfcb-143">Address book providers implement the **IABLogon::Advise** method to register the caller to be notified when a change occurs to an object in one of their containers.</span></span> <span data-ttu-id="edfcb-144">呼叫者可以注册通知消息的用户、 通讯组列表，或整个容器。</span><span class="sxs-lookup"><span data-stu-id="edfcb-144">Callers can register for notifications regarding messaging users, distribution lists, or entire containers.</span></span> 
  
<span data-ttu-id="edfcb-145">客户端通常调用[IAddrBook::Advise](iaddrbook-advise.md)方法注册地址簿通知。</span><span class="sxs-lookup"><span data-stu-id="edfcb-145">Clients typically call the [IAddrBook::Advise](iaddrbook-advise.md) method to register for address book notifications.</span></span> <span data-ttu-id="edfcb-146">MAPI 然后调用**Advise**方法的地址簿提供程序负责_lpEntryID_中的项标识符所表示的对象。</span><span class="sxs-lookup"><span data-stu-id="edfcb-146">MAPI then calls the **Advise** method of the address book provider that is responsible for the object represented by the entry identifier in  _lpEntryID_.</span></span>
  
<span data-ttu-id="edfcb-147">对指定对象中_ulEventMask_表示的类型发生更改时, 调用了通知接收器所指的_lpAdviseSink_ **OnNotify**方法。</span><span class="sxs-lookup"><span data-stu-id="edfcb-147">When a change occurs to the indicated object of the type represented in  _ulEventMask_, a call is made to the **OnNotify** method of the advise sink pointed to by  _lpAdviseSink_.</span></span> <span data-ttu-id="edfcb-148">数据传递给**OnNotify**例程**通知**结构中介绍的事件。</span><span class="sxs-lookup"><span data-stu-id="edfcb-148">Data passed in the **NOTIFICATION** structure to the **OnNotify** routine describes the event.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="edfcb-149">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="edfcb-149">Notes to implementers</span></span>

<span data-ttu-id="edfcb-150">您可以支持使用或不从 MAPI 帮助的通知。</span><span class="sxs-lookup"><span data-stu-id="edfcb-150">You can support notification with or without help from MAPI.</span></span> <span data-ttu-id="edfcb-151">MAPI 具有三个支持对象方法，以帮助服务提供商实现通知：</span><span class="sxs-lookup"><span data-stu-id="edfcb-151">MAPI has three support object methods to help service providers implement notification:</span></span>
  
- [<span data-ttu-id="edfcb-152">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="edfcb-152">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)
    
- [<span data-ttu-id="edfcb-153">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="edfcb-153">IMAPISupport::Unsubscribe</span></span>](imapisupport-unsubscribe.md)
    
- [<span data-ttu-id="edfcb-154">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="edfcb-154">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
    
<span data-ttu-id="edfcb-155">如果您选择使用 MAPI 支持方法，调用**Advise**方法时调用**Subscribe**和释放_lpAdviseSink_指针。</span><span class="sxs-lookup"><span data-stu-id="edfcb-155">If you elect to use the MAPI support methods, call **Subscribe** when your **Advise** method is called and release the  _lpAdviseSink_ pointer.</span></span> 
  
<span data-ttu-id="edfcb-156">如果您选择自己支持通知，呼叫通知接收器由_lpAdviseSink_参数保留一份此指针的**AddRef**方法。</span><span class="sxs-lookup"><span data-stu-id="edfcb-156">If you elect to support notification yourself, call the **AddRef** method of the advise sink represented by the  _lpAdviseSink_ parameter to keep a copy of this pointer.</span></span> <span data-ttu-id="edfcb-157">维护此副本，直到您[IABLogon::Unadvise](iablogon-unadvise.md)方法调用取消注册。</span><span class="sxs-lookup"><span data-stu-id="edfcb-157">Maintain this copy until your [IABLogon::Unadvise](iablogon-unadvise.md) method is called to cancel the registration.</span></span> 
  
<span data-ttu-id="edfcb-158">无论如何支持通知，分配给通知注册的非零值的连接数并返回_lpulConnection_参数中。</span><span class="sxs-lookup"><span data-stu-id="edfcb-158">Regardless of how you support notification, assign a nonzero connection number to the notification registration and return it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="edfcb-159">被调用**Unadvise**方法之前不释放此连接数。</span><span class="sxs-lookup"><span data-stu-id="edfcb-159">Do not release this connection number until the **Unadvise** method has been called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="edfcb-160">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="edfcb-160">Notes to callers</span></span>

<span data-ttu-id="edfcb-161">_LpAdviseSink_参数中传递到**Advise** advise 接收器指针可以指向已创建或通过[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数创建 MAPI 的对象。</span><span class="sxs-lookup"><span data-stu-id="edfcb-161">The advise sink pointer that you pass in the  _lpAdviseSink_ parameter to **Advise** can point to an object that you have created or that MAPI has created through the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> <span data-ttu-id="edfcb-162">您可能需要使用**HrThisThreadAdviseSink** ，如果您支持多个线程的执行，并且想要确保您**OnNotify**方法的后续呼叫发生在相应的线程上适当的时间。</span><span class="sxs-lookup"><span data-stu-id="edfcb-162">You might want to use **HrThisThreadAdviseSink** if you support multiple threads of execution and want to be sure that that subsequent calls to your **OnNotify** method occur at an appropriate time on an appropriate thread.</span></span> 
  
<span data-ttu-id="edfcb-163">为您 advise 接收器对象，必须释放到**Advise**和到**Unadvise**呼叫之前呼叫后随时准备。</span><span class="sxs-lookup"><span data-stu-id="edfcb-163">Be prepared for your advise sink object to be released any time after your call to **Advise** and before your call to **Unadvise**.</span></span> <span data-ttu-id="edfcb-164">因此，您应释放 advise 接收器对象后**Advise**返回，除非您有特定的长期使用它。</span><span class="sxs-lookup"><span data-stu-id="edfcb-164">Therefore, you should release your advise sink object after **Advise** returns, unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="edfcb-165">有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="edfcb-165">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="edfcb-166">有关如何使用**IMAPISupport**方法以支持通知的信息，请参阅[支持的事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="edfcb-166">For information about how to use the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span> <span data-ttu-id="edfcb-167">有关详细信息多线程和 MAPI，请参阅[MAPI 中的线程](threading-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="edfcb-167">For more information about multithreading and MAPI, see [Threading in MAPI](threading-in-mapi.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="edfcb-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edfcb-168">See also</span></span>



[<span data-ttu-id="edfcb-169">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="edfcb-169">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="edfcb-170">IABLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="edfcb-170">IABLogon::Unadvise</span></span>](iablogon-unadvise.md)
  
[<span data-ttu-id="edfcb-171">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="edfcb-171">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="edfcb-172">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="edfcb-172">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="edfcb-173">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="edfcb-173">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

