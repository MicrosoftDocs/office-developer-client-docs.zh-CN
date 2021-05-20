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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6160b8e75bdc9059965c2358b9fe7d296e1f66d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435934"
---
# <a name="imapisupportnotify"></a><span data-ttu-id="f1eb2-103">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="f1eb2-103">IMAPISupport::Notify</span></span>

<span data-ttu-id="f1eb2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1eb2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1eb2-105">将指定事件的通知发送到最初通过 [IMAPISupport：：Subscribe](imapisupport-subscribe.md) 方法注册的通知源。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-105">Sends a notification of a specified event to an advise source that originally registered for the notification through the [IMAPISupport::Subscribe](imapisupport-subscribe.md) method.</span></span> 
  
```cpp
HRESULT Notify(
LPNOTIFKEY lpKey,
ULONG cNotification,
LPNOTIFICATION lpNotifications,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="f1eb2-106">参数</span><span class="sxs-lookup"><span data-stu-id="f1eb2-106">Parameters</span></span>

<span data-ttu-id="f1eb2-107">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="f1eb2-107">_lpKey_</span></span>
  
> <span data-ttu-id="f1eb2-108">[in]指向建议源对象的通知键的指针。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-108">[in] A pointer to the notification key for the advise source object.</span></span> <span data-ttu-id="f1eb2-109">_lpKey_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-109">The  _lpKey_ parameter cannot be NULL.</span></span> 
    
<span data-ttu-id="f1eb2-110">_cNotification_</span><span class="sxs-lookup"><span data-stu-id="f1eb2-110">_cNotification_</span></span>
  
> <span data-ttu-id="f1eb2-111">[in]  _lpNotifications_ 参数指向的通知结构计数。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-111">[in] The count of notification structures pointed to by the  _lpNotifications_ parameter.</span></span> 
    
<span data-ttu-id="f1eb2-112">_lpNotifications_</span><span class="sxs-lookup"><span data-stu-id="f1eb2-112">_lpNotifications_</span></span>
  
> <span data-ttu-id="f1eb2-113">[in]指向描述挂起通知的 [NOTIFICATION](notification.md) 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-113">[in] A pointer to an array of [NOTIFICATION](notification.md) structures that describe pending notifications.</span></span> 
    
<span data-ttu-id="f1eb2-114">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="f1eb2-114">_lpulFlags_</span></span>
  
> <span data-ttu-id="f1eb2-115">[in， out]控制通知过程的标记位掩码。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-115">[in, out] A bitmask of flags that controls the notification process.</span></span> <span data-ttu-id="f1eb2-116">在输入时，可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f1eb2-116">On input, the following flag can be set:</span></span>
    
  - <span data-ttu-id="f1eb2-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f1eb2-117">MAPI_UNICODE</span></span> 
    
    > <span data-ttu-id="f1eb2-118">_lpNotifications_ 指向的通知结构中字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-118">The strings in the notification structures pointed to by  _lpNotifications_ are in Unicode format.</span></span> <span data-ttu-id="f1eb2-119">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-119">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 

    <span data-ttu-id="f1eb2-120">在输出上，MAPI 可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f1eb2-120">On output, MAPI can set the following flag:</span></span>
        
  - <span data-ttu-id="f1eb2-121">NOTIFY_CANCELED</span><span class="sxs-lookup"><span data-stu-id="f1eb2-121">NOTIFY_CANCELED</span></span> 
    
    > <span data-ttu-id="f1eb2-122">回调函数取消了同步通知。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-122">A callback function canceled a synchronous notification.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f1eb2-123">返回值</span><span class="sxs-lookup"><span data-stu-id="f1eb2-123">Return value</span></span>

<span data-ttu-id="f1eb2-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1eb2-124">S_OK</span></span> 
  
> <span data-ttu-id="f1eb2-125">已成功生成通知。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-125">The notifications were successfully generated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f1eb2-126">备注</span><span class="sxs-lookup"><span data-stu-id="f1eb2-126">Remarks</span></span>

<span data-ttu-id="f1eb2-127">所有 **服务提供商支持对象都实现了 IMAPISupport：：Notify** 方法。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-127">The **IMAPISupport::Notify** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="f1eb2-128">服务提供商调用 **Notify** 以请求 MAPI 为之前通过 **IMAPISupport：：Subscribe** 方法注册的通知接收生成通知。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-128">Service providers call **Notify** to request that MAPI generate a notification for an advise sink that has previously registered for the notification through the **IMAPISupport::Subscribe** method.</span></span> 
  
<span data-ttu-id="f1eb2-129">**Notify** 将  _lpNotifications_ 参数指向的结构复制到内存中，并调用相应的通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-129">**Notify** copies the structures pointed to by the  _lpNotifications_ parameter into memory and calls the appropriate advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="f1eb2-130">当 **OnNotify** 完成通知后，它将释放涉及的内存。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-130">When **OnNotify** is finished with the notification, it releases the memory involved.</span></span> <span data-ttu-id="f1eb2-131">调用方不需要分配内存;MAPI 执行所有必要的内存分配。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-131">The caller does not need to allocate memory; MAPI performs all necessary memory allocation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f1eb2-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f1eb2-132">Notes to callers</span></span>

<span data-ttu-id="f1eb2-133">在  _lpKey_ 参数中传递的通知键应该与  _在 lpKey_ 中传递给 **IMAPISupport：：Subscribe** 方法的键相同。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-133">The notification key passed in the  _lpKey_ parameter should be identical to the key passed in  _lpKey_ to the **IMAPISupport::Subscribe** method.</span></span> <span data-ttu-id="f1eb2-134">许多提供程序使用建议源的条目标识符作为键，但可以使用其他数据（如文件路径）。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-134">Many providers use the entry identifier of the advise source as the key, but other data, such as a file path, can be used.</span></span> <span data-ttu-id="f1eb2-135">MAPI 使用此密钥查找标识的建议源上通知的所有注册。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-135">MAPI uses this key to find all the registrations for notifications on the identified advise source.</span></span> 
  
<span data-ttu-id="f1eb2-136">请确保将通知结构的 **lpEntryID** 成员设置为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-136">Be sure that you set the **lpEntryID** member of the notification structure to a long-term entry identifier.</span></span> 
  
<span data-ttu-id="f1eb2-137">如果在 Subscribe 调用上为任何挂起的通知设置NOTIFY_SYNC 标志 **，Notify** 将在返回之前调用 **IMAPIAdviseSink：：OnNotify** 方法回调函数。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-137">If you set the NOTIFY_SYNC flag on the **Subscribe** call for any of the pending notifications, **Notify** calls the **IMAPIAdviseSink::OnNotify** method callback functions before returning.</span></span> <span data-ttu-id="f1eb2-138">建议接收器可以手动创建，也可以调用 [HrAllocAdviseSink 创建](hrallocadvisesink.md)。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-138">An advise sink can be created manually or by calling [HrAllocAdviseSink](hrallocadvisesink.md).</span></span> <span data-ttu-id="f1eb2-139">**HrAllocAdviseSink** 函数允许其调用方指定一个回调函数，以通知调用作为通知的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-139">The **HrAllocAdviseSink** function allows its caller to specify a callback function that **Notify** calls as part of the notification.</span></span> <span data-ttu-id="f1eb2-140">回调函数符合 [NOTIFCALLBACK](notifcallback.md) 原型。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-140">The callback function conforms to the [NOTIFCALLBACK](notifcallback.md) prototype.</span></span> <span data-ttu-id="f1eb2-141">客户端实现的回调函数始终返回S_OK;由服务提供商实现的回调函数可以返回CALLBACK_DISCONTINUE。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-141">Callback functions implemented by clients always return S_OK; callback functions implemented by service providers can return CALLBACK_DISCONTINUE.</span></span> 
  
<span data-ttu-id="f1eb2-142">如果回调函数返回 CALLBACK_DISCONTINUE，MAPI 将停止发送通知，NOTIFY_CANCELED **Notify** 方法  _的 lpulFlags_ 参数中返回通知。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-142">If a callback function returns CALLBACK_DISCONTINUE, MAPI stops sending notifications and returns NOTIFY_CANCELED in the **Notify** method's  _lpulFlags_ parameter.</span></span> <span data-ttu-id="f1eb2-143">你可以假设进程处于非活动状态，并停止为该进程生成通知。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-143">You can assume that the process is inactive and stop generating notifications for that process.</span></span> <span data-ttu-id="f1eb2-144">如果 **Notify** 在  _lpulFlags_ 中返回 0，则进程仍处于活动状态，您应该继续根据情况发送通知。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-144">If **Notify** returns 0 in  _lpulFlags_, the process is still active and you should continue to send notifications, as appropriate.</span></span>
  
<span data-ttu-id="f1eb2-145">使用同步通知时，请注意避免死锁情况。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-145">When you use synchronous notifications, be careful to avoid deadlock situations.</span></span>
  
<span data-ttu-id="f1eb2-146">有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="f1eb2-146">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f1eb2-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1eb2-147">See also</span></span>

- [<span data-ttu-id="f1eb2-148">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="f1eb2-148">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)  
- [<span data-ttu-id="f1eb2-149">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="f1eb2-149">IMAPISupport::Unsubscribe</span></span>](imapisupport-unsubscribe.md)  
- [<span data-ttu-id="f1eb2-150">NOTIFCALLBACK</span><span class="sxs-lookup"><span data-stu-id="f1eb2-150">NOTIFCALLBACK</span></span>](notifcallback.md) 
- [<span data-ttu-id="f1eb2-151">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="f1eb2-151">NOTIFICATION</span></span>](notification.md)  
- [<span data-ttu-id="f1eb2-152">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="f1eb2-152">NOTIFKEY</span></span>](notifkey.md)  
- [<span data-ttu-id="f1eb2-153">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="f1eb2-153">PidTagRecordKey Canonical Property</span></span>](pidtagrecordkey-canonical-property.md)  
- [<span data-ttu-id="f1eb2-154">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f1eb2-154">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

