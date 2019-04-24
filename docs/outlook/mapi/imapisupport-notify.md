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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326367"
---
# <a name="imapisupportnotify"></a><span data-ttu-id="e5e34-103">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="e5e34-103">IMAPISupport::Notify</span></span>

<span data-ttu-id="e5e34-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e5e34-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e5e34-105">将指定事件的通知发送到最初通过[IMAPISupport:: 订阅](imapisupport-subscribe.md)方法为通知注册的通知源。</span><span class="sxs-lookup"><span data-stu-id="e5e34-105">Sends a notification of a specified event to an advise source that originally registered for the notification through the [IMAPISupport::Subscribe](imapisupport-subscribe.md) method.</span></span> 
  
```cpp
HRESULT Notify(
LPNOTIFKEY lpKey,
ULONG cNotification,
LPNOTIFICATION lpNotifications,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="e5e34-106">参数</span><span class="sxs-lookup"><span data-stu-id="e5e34-106">Parameters</span></span>

<span data-ttu-id="e5e34-107">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="e5e34-107">_lpKey_</span></span>
  
> <span data-ttu-id="e5e34-108">实时一个指针, 指向通知源对象的通知密钥。</span><span class="sxs-lookup"><span data-stu-id="e5e34-108">[in] A pointer to the notification key for the advise source object.</span></span> <span data-ttu-id="e5e34-109">_lpKey_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e5e34-109">The  _lpKey_ parameter cannot be NULL.</span></span> 
    
<span data-ttu-id="e5e34-110">_cNotification_</span><span class="sxs-lookup"><span data-stu-id="e5e34-110">_cNotification_</span></span>
  
> <span data-ttu-id="e5e34-111">实时由_lpNotifications_参数指向的通知结构的计数。</span><span class="sxs-lookup"><span data-stu-id="e5e34-111">[in] The count of notification structures pointed to by the  _lpNotifications_ parameter.</span></span> 
    
<span data-ttu-id="e5e34-112">_lpNotifications_</span><span class="sxs-lookup"><span data-stu-id="e5e34-112">_lpNotifications_</span></span>
  
> <span data-ttu-id="e5e34-113">实时指向描述挂起通知的[通知](notification.md)结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="e5e34-113">[in] A pointer to an array of [NOTIFICATION](notification.md) structures that describe pending notifications.</span></span> 
    
<span data-ttu-id="e5e34-114">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="e5e34-114">_lpulFlags_</span></span>
  
> <span data-ttu-id="e5e34-115">[in, out]控制通知过程的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e5e34-115">[in, out] A bitmask of flags that controls the notification process.</span></span> <span data-ttu-id="e5e34-116">在输入时, 可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="e5e34-116">On input, the following flag can be set:</span></span>
    
  - <span data-ttu-id="e5e34-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e5e34-117">MAPI_UNICODE</span></span> 
    
    > <span data-ttu-id="e5e34-118">由_lpNotifications_指向的通知结构中的字符串是 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="e5e34-118">The strings in the notification structures pointed to by  _lpNotifications_ are in Unicode format.</span></span> <span data-ttu-id="e5e34-119">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="e5e34-119">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 

    <span data-ttu-id="e5e34-120">在输出时, MAPI 可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="e5e34-120">On output, MAPI can set the following flag:</span></span>
        
  - <span data-ttu-id="e5e34-121">NOTIFY_CANCELED</span><span class="sxs-lookup"><span data-stu-id="e5e34-121">NOTIFY_CANCELED</span></span> 
    
    > <span data-ttu-id="e5e34-122">回调函数取消了同步通知。</span><span class="sxs-lookup"><span data-stu-id="e5e34-122">A callback function canceled a synchronous notification.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e5e34-123">返回值</span><span class="sxs-lookup"><span data-stu-id="e5e34-123">Return value</span></span>

<span data-ttu-id="e5e34-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5e34-124">S_OK</span></span> 
  
> <span data-ttu-id="e5e34-125">已成功生成通知。</span><span class="sxs-lookup"><span data-stu-id="e5e34-125">The notifications were successfully generated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e5e34-126">注解</span><span class="sxs-lookup"><span data-stu-id="e5e34-126">Remarks</span></span>

<span data-ttu-id="e5e34-127">为所有服务提供程序支持对象实现了**IMAPISupport:: Notify**方法。</span><span class="sxs-lookup"><span data-stu-id="e5e34-127">The **IMAPISupport::Notify** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="e5e34-128">服务提供程序调用**通知**请求 MAPI 为已通过**IMAPISupport:: 订阅**方法注册通知的通知接收器生成通知。</span><span class="sxs-lookup"><span data-stu-id="e5e34-128">Service providers call **Notify** to request that MAPI generate a notification for an advise sink that has previously registered for the notification through the **IMAPISupport::Subscribe** method.</span></span> 
  
<span data-ttu-id="e5e34-129">**通知**将_lpNotifications_参数指向的结构复制到内存中, 并调用相应的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e5e34-129">**Notify** copies the structures pointed to by the  _lpNotifications_ parameter into memory and calls the appropriate advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="e5e34-130">当**OnNotify**完成通知后, 它会释放涉及的内存。</span><span class="sxs-lookup"><span data-stu-id="e5e34-130">When **OnNotify** is finished with the notification, it releases the memory involved.</span></span> <span data-ttu-id="e5e34-131">调用方不需要分配内存;MAPI 执行所有必要的内存分配。</span><span class="sxs-lookup"><span data-stu-id="e5e34-131">The caller does not need to allocate memory; MAPI performs all necessary memory allocation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e5e34-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e5e34-132">Notes to callers</span></span>

<span data-ttu-id="e5e34-133">在_lpKey_参数中传递的通知密钥应与在_lpKey_中传递给**IMAPISupport:: 订阅**方法的密钥相同。</span><span class="sxs-lookup"><span data-stu-id="e5e34-133">The notification key passed in the  _lpKey_ parameter should be identical to the key passed in  _lpKey_ to the **IMAPISupport::Subscribe** method.</span></span> <span data-ttu-id="e5e34-134">许多提供程序将建议源的条目标识符用作密钥, 但可以使用其他数据 (如文件路径)。</span><span class="sxs-lookup"><span data-stu-id="e5e34-134">Many providers use the entry identifier of the advise source as the key, but other data, such as a file path, can be used.</span></span> <span data-ttu-id="e5e34-135">MAPI 使用此密钥在确定的建议源上查找所有通知注册。</span><span class="sxs-lookup"><span data-stu-id="e5e34-135">MAPI uses this key to find all the registrations for notifications on the identified advise source.</span></span> 
  
<span data-ttu-id="e5e34-136">确保将通知结构的**lpEntryID**成员设置为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e5e34-136">Be sure that you set the **lpEntryID** member of the notification structure to a long-term entry identifier.</span></span> 
  
<span data-ttu-id="e5e34-137">如果您在**订阅**呼叫中为任何挂起的通知设置 NOTIFY_SYNC 标志, 请在返回之前**通知**调用**IMAPIAdviseSink:: OnNotify**方法回调函数。</span><span class="sxs-lookup"><span data-stu-id="e5e34-137">If you set the NOTIFY_SYNC flag on the **Subscribe** call for any of the pending notifications, **Notify** calls the **IMAPIAdviseSink::OnNotify** method callback functions before returning.</span></span> <span data-ttu-id="e5e34-138">可以手动或通过调用[HrAllocAdviseSink](hrallocadvisesink.md)创建通知接收器。</span><span class="sxs-lookup"><span data-stu-id="e5e34-138">An advise sink can be created manually or by calling [HrAllocAdviseSink](hrallocadvisesink.md).</span></span> <span data-ttu-id="e5e34-139">**HrAllocAdviseSink**函数允许其调用方指定一个回调函数, 用于将调用作为通知的一部分进行**通知**。</span><span class="sxs-lookup"><span data-stu-id="e5e34-139">The **HrAllocAdviseSink** function allows its caller to specify a callback function that **Notify** calls as part of the notification.</span></span> <span data-ttu-id="e5e34-140">回调函数符合[NOTIFCALLBACK](notifcallback.md)原型。</span><span class="sxs-lookup"><span data-stu-id="e5e34-140">The callback function conforms to the [NOTIFCALLBACK](notifcallback.md) prototype.</span></span> <span data-ttu-id="e5e34-141">客户端实现的回调函数始终返回 S_OK;服务提供程序实现的回调函数可返回 CALLBACK_DISCONTINUE。</span><span class="sxs-lookup"><span data-stu-id="e5e34-141">Callback functions implemented by clients always return S_OK; callback functions implemented by service providers can return CALLBACK_DISCONTINUE.</span></span> 
  
<span data-ttu-id="e5e34-142">如果回调函数返回 CALLBACK_DISCONTINUE, MAPI 将停止发送通知, 并在**NOTIFY**方法的_lpulFlags_参数中返回 NOTIFY_CANCELED。</span><span class="sxs-lookup"><span data-stu-id="e5e34-142">If a callback function returns CALLBACK_DISCONTINUE, MAPI stops sending notifications and returns NOTIFY_CANCELED in the **Notify** method's  _lpulFlags_ parameter.</span></span> <span data-ttu-id="e5e34-143">您可以假定该进程处于非活动状态, 并停止为该进程生成通知。</span><span class="sxs-lookup"><span data-stu-id="e5e34-143">You can assume that the process is inactive and stop generating notifications for that process.</span></span> <span data-ttu-id="e5e34-144">如果**通知**在_lpulFlags_中返回 0, 则该进程仍处于活动状态, 应根据需要继续发送通知。</span><span class="sxs-lookup"><span data-stu-id="e5e34-144">If **Notify** returns 0 in  _lpulFlags_, the process is still active and you should continue to send notifications, as appropriate.</span></span>
  
<span data-ttu-id="e5e34-145">使用同步通知时, 请注意避免死锁情况。</span><span class="sxs-lookup"><span data-stu-id="e5e34-145">When you use synchronous notifications, be careful to avoid deadlock situations.</span></span>
  
<span data-ttu-id="e5e34-146">有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="e5e34-146">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e5e34-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5e34-147">See also</span></span>

- [<span data-ttu-id="e5e34-148">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="e5e34-148">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)  
- [<span data-ttu-id="e5e34-149">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="e5e34-149">IMAPISupport::Unsubscribe</span></span>](imapisupport-unsubscribe.md)  
- [<span data-ttu-id="e5e34-150">NOTIFCALLBACK</span><span class="sxs-lookup"><span data-stu-id="e5e34-150">NOTIFCALLBACK</span></span>](notifcallback.md) 
- [<span data-ttu-id="e5e34-151">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e5e34-151">NOTIFICATION</span></span>](notification.md)  
- [<span data-ttu-id="e5e34-152">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="e5e34-152">NOTIFKEY</span></span>](notifkey.md)  
- [<span data-ttu-id="e5e34-153">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="e5e34-153">PidTagRecordKey Canonical Property</span></span>](pidtagrecordkey-canonical-property.md)  
- [<span data-ttu-id="e5e34-154">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e5e34-154">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

