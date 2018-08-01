---
title: IMAPISupportNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Notify
api_type:
- COM
ms.assetid: c16c668e-2c8b-4759-bbca-d0c5662b62e9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: db23d1801bf32fd947a77dfd887c56f75ded5681
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775634"
---
# <a name="imapisupportnotify"></a><span data-ttu-id="09f77-103">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="09f77-103">IMAPISupport::Notify</span></span>

<span data-ttu-id="09f77-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="09f77-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="09f77-105">将指定的事件的通知发送到最初通过[IMAPISupport::Subscribe](imapisupport-subscribe.md)方法通知注册的 advise 源。</span><span class="sxs-lookup"><span data-stu-id="09f77-105">Sends a notification of a specified event to an advise source that originally registered for the notification through the [IMAPISupport::Subscribe](imapisupport-subscribe.md) method.</span></span> 
  
```cpp
HRESULT Notify(
LPNOTIFKEY lpKey,
ULONG cNotification,
LPNOTIFICATION lpNotifications,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="09f77-106">参数</span><span class="sxs-lookup"><span data-stu-id="09f77-106">Parameters</span></span>

<span data-ttu-id="09f77-107">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="09f77-107">_lpKey_</span></span>
  
> <span data-ttu-id="09f77-108">[in]指向 advise 源对象的通知键的指针。</span><span class="sxs-lookup"><span data-stu-id="09f77-108">[in] A pointer to the notification key for the advise source object.</span></span> <span data-ttu-id="09f77-109">_LpKey_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="09f77-109">The  _lpKey_ parameter cannot be NULL.</span></span> 
    
<span data-ttu-id="09f77-110">_cNotification_</span><span class="sxs-lookup"><span data-stu-id="09f77-110">_cNotification_</span></span>
  
> <span data-ttu-id="09f77-111">[in]通知结构_lpNotifications_参数指向的计数。</span><span class="sxs-lookup"><span data-stu-id="09f77-111">[in] The count of notification structures pointed to by the  _lpNotifications_ parameter.</span></span> 
    
<span data-ttu-id="09f77-112">_lpNotifications_</span><span class="sxs-lookup"><span data-stu-id="09f77-112">_lpNotifications_</span></span>
  
> <span data-ttu-id="09f77-113">[in]一个指向介绍挂起的通知的[通知](notification.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="09f77-113">[in] A pointer to an array of [NOTIFICATION](notification.md) structures that describe pending notifications.</span></span> 
    
<span data-ttu-id="09f77-114">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="09f77-114">_lpulFlags_</span></span>
  
> <span data-ttu-id="09f77-115">[传入、 传出]位掩码的标志，用于控制通知过程。</span><span class="sxs-lookup"><span data-stu-id="09f77-115">[in, out] A bitmask of flags that controls the notification process.</span></span> <span data-ttu-id="09f77-116">在输入时，可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="09f77-116">On input, the following flag can be set:</span></span>
    
  - <span data-ttu-id="09f77-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="09f77-117">MAPI_UNICODE</span></span> 
    
    > <span data-ttu-id="09f77-118">由_lpNotifications_指向的通知结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="09f77-118">The strings in the notification structures pointed to by  _lpNotifications_ are in Unicode format.</span></span> <span data-ttu-id="09f77-119">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="09f77-119">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 

    <span data-ttu-id="09f77-120">输出，MAPI 可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="09f77-120">On output, MAPI can set the following flag:</span></span>
        
  - <span data-ttu-id="09f77-121">NOTIFY_CANCELED</span><span class="sxs-lookup"><span data-stu-id="09f77-121">NOTIFY_CANCELED</span></span> 
    
    > <span data-ttu-id="09f77-122">回调函数取消同步的通知。</span><span class="sxs-lookup"><span data-stu-id="09f77-122">A callback function canceled a synchronous notification.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="09f77-123">返回值</span><span class="sxs-lookup"><span data-stu-id="09f77-123">Return value</span></span>

<span data-ttu-id="09f77-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="09f77-124">S_OK</span></span> 
  
> <span data-ttu-id="09f77-125">已成功生成通知。</span><span class="sxs-lookup"><span data-stu-id="09f77-125">The notifications were successfully generated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="09f77-126">说明</span><span class="sxs-lookup"><span data-stu-id="09f77-126">Remarks</span></span>

<span data-ttu-id="09f77-127">**IMAPISupport::Notify**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="09f77-127">The **IMAPISupport::Notify** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="09f77-128">服务提供商调用**Notify**请求 MAPI 生成**IMAPISupport::Subscribe**方法通过以前通知注册通知接收器的通知。</span><span class="sxs-lookup"><span data-stu-id="09f77-128">Service providers call **Notify** to request that MAPI generate a notification for an advise sink that has previously registered for the notification through the **IMAPISupport::Subscribe** method.</span></span> 
  
<span data-ttu-id="09f77-129">**Notify**副本结构到内存_lpNotifications_参数指向和调用适当通知接收器的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="09f77-129">**Notify** copies the structures pointed to by the  _lpNotifications_ parameter into memory and calls the appropriate advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="09f77-130">当**OnNotify**与通知完成后时，将释放所涉及的内存。</span><span class="sxs-lookup"><span data-stu-id="09f77-130">When **OnNotify** is finished with the notification, it releases the memory involved.</span></span> <span data-ttu-id="09f77-131">呼叫者不需要分配内存;MAPI 执行所有必要的内存分配。</span><span class="sxs-lookup"><span data-stu-id="09f77-131">The caller does not need to allocate memory; MAPI performs all necessary memory allocation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="09f77-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="09f77-132">Notes to callers</span></span>

<span data-ttu-id="09f77-133">_LpKey_参数中传递的通知密钥应为到项中_lpKey_传递给**IMAPISupport::Subscribe**方法相同。</span><span class="sxs-lookup"><span data-stu-id="09f77-133">The notification key passed in the  _lpKey_ parameter should be identical to the key passed in  _lpKey_ to the **IMAPISupport::Subscribe** method.</span></span> <span data-ttu-id="09f77-134">多个提供程序将 advise 源的项标识符用作键，但可使用其他数据，例如文件的路径。</span><span class="sxs-lookup"><span data-stu-id="09f77-134">Many providers use the entry identifier of the advise source as the key, but other data, such as a file path, can be used.</span></span> <span data-ttu-id="09f77-135">MAPI 使用此项查找所有注册的标识的 advise 源上的通知。</span><span class="sxs-lookup"><span data-stu-id="09f77-135">MAPI uses this key to find all the registrations for notifications on the identified advise source.</span></span> 
  
<span data-ttu-id="09f77-136">确保将通知结构的**lpEntryID**成员设置为长期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="09f77-136">Be sure that you set the **lpEntryID** member of the notification structure to a long-term entry identifier.</span></span> 
  
<span data-ttu-id="09f77-137">如果您设置**Subscribe**的 NOTIFY_SYNC 标志调用的任何挂起的通知，**通知**调用**IMAPIAdviseSink::OnNotify**方法的回调函数返回之前。</span><span class="sxs-lookup"><span data-stu-id="09f77-137">If you set the NOTIFY_SYNC flag on the **Subscribe** call for any of the pending notifications, **Notify** calls the **IMAPIAdviseSink::OnNotify** method callback functions before returning.</span></span> <span data-ttu-id="09f77-138">手动方式或通过调用[HrAllocAdviseSink](hrallocadvisesink.md)，可以创建通知接收器。</span><span class="sxs-lookup"><span data-stu-id="09f77-138">An advise sink can be created manually or by calling [HrAllocAdviseSink](hrallocadvisesink.md).</span></span> <span data-ttu-id="09f77-139">使用**HrAllocAdviseSink**功能，其调用方指定一个回调函数的**Notify**呼叫通知的一部分。</span><span class="sxs-lookup"><span data-stu-id="09f77-139">The **HrAllocAdviseSink** function allows its caller to specify a callback function that **Notify** calls as part of the notification.</span></span> <span data-ttu-id="09f77-140">符合[NOTIFCALLBACK](notifcallback.md)原型的回调函数。</span><span class="sxs-lookup"><span data-stu-id="09f77-140">The callback function conforms to the [NOTIFCALLBACK](notifcallback.md) prototype.</span></span> <span data-ttu-id="09f77-141">始终由客户端实现的回调函数将返回 S_OK;服务提供程序实现的回调函数可以返回 CALLBACK_DISCONTINUE。</span><span class="sxs-lookup"><span data-stu-id="09f77-141">Callback functions implemented by clients always return S_OK; callback functions implemented by service providers can return CALLBACK_DISCONTINUE.</span></span> 
  
<span data-ttu-id="09f77-142">如果回调函数返回 CALLBACK_DISCONTINUE，MAPI 停止发送通知，并返回 NOTIFY_CANCELED 中**Notify**方法的_lpulFlags_参数。</span><span class="sxs-lookup"><span data-stu-id="09f77-142">If a callback function returns CALLBACK_DISCONTINUE, MAPI stops sending notifications and returns NOTIFY_CANCELED in the **Notify** method's  _lpulFlags_ parameter.</span></span> <span data-ttu-id="09f77-143">您可以假定过程已停用，停止生成通知的过程。</span><span class="sxs-lookup"><span data-stu-id="09f77-143">You can assume that the process is inactive and stop generating notifications for that process.</span></span> <span data-ttu-id="09f77-144">如果**Notify**中_lpulFlags_返回 0，则过程仍处于活动状态并根据需要发送通知，您应继续。</span><span class="sxs-lookup"><span data-stu-id="09f77-144">If **Notify** returns 0 in  _lpulFlags_, the process is still active and you should continue to send notifications, as appropriate.</span></span>
  
<span data-ttu-id="09f77-145">当您使用同步的通知时，请注意避免出现死锁的情况。</span><span class="sxs-lookup"><span data-stu-id="09f77-145">When you use synchronous notifications, be careful to avoid deadlock situations.</span></span>
  
<span data-ttu-id="09f77-146">有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="09f77-146">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="09f77-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09f77-147">See also</span></span>

- [<span data-ttu-id="09f77-148">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="09f77-148">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)  
- [<span data-ttu-id="09f77-149">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="09f77-149">IMAPISupport::Unsubscribe</span></span>](imapisupport-unsubscribe.md)  
- [<span data-ttu-id="09f77-150">NOTIFCALLBACK</span><span class="sxs-lookup"><span data-stu-id="09f77-150">NOTIFCALLBACK</span></span>](notifcallback.md) 
- [<span data-ttu-id="09f77-151">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="09f77-151">NOTIFICATION</span></span>](notification.md)  
- [<span data-ttu-id="09f77-152">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="09f77-152">NOTIFKEY</span></span>](notifkey.md)  
- [<span data-ttu-id="09f77-153">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="09f77-153">PidTagRecordKey Canonical Property</span></span>](pidtagrecordkey-canonical-property.md)  
- [<span data-ttu-id="09f77-154">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="09f77-154">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

