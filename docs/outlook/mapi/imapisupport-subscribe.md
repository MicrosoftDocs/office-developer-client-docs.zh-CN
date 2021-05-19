---
title: IMAPISupportSubscribe
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Subscribe
api_type:
- COM
ms.assetid: e6baaff1-446e-431a-a09b-9b529153382b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a8c288e877078ece6ab2da8c6494d96e1714ad7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419924"
---
# <a name="imapisupportsubscribe"></a><span data-ttu-id="8cc37-103">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="8cc37-103">IMAPISupport::Subscribe</span></span>

  
  
<span data-ttu-id="8cc37-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8cc37-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8cc37-105">注册通知接收器以通过 MAPI 接收通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-105">Registers an advise sink to receive notifications through MAPI.</span></span>
  
```cpp
HRESULT Subscribe(
LPNOTIFKEY lpKey,
ULONG ulEventMask,
ULONG ulFlags,
LPMAPIADVISESINK lpAdviseSink,
ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="8cc37-106">参数</span><span class="sxs-lookup"><span data-stu-id="8cc37-106">Parameters</span></span>

 <span data-ttu-id="8cc37-107">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="8cc37-107">_lpKey_</span></span>
  
> <span data-ttu-id="8cc37-108">[in]指向表示建议源对象的通知键的指针。</span><span class="sxs-lookup"><span data-stu-id="8cc37-108">[in] A pointer to a notification key that represents the advise source object.</span></span> <span data-ttu-id="8cc37-109">_lpKey_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8cc37-109">The  _lpKey_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="8cc37-110">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="8cc37-110">_ulEventMask_</span></span>
  
> <span data-ttu-id="8cc37-111">[in]指示调用方感兴趣的通知事件类型且应包含在注册中的值的掩码。</span><span class="sxs-lookup"><span data-stu-id="8cc37-111">[in] A mask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="8cc37-112">以下值有效：</span><span class="sxs-lookup"><span data-stu-id="8cc37-112">The following values are valid:</span></span>
    
 <span data-ttu-id="8cc37-113">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="8cc37-113">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="8cc37-114">注册有关严重错误（如内存不足）的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-114">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
 <span data-ttu-id="8cc37-115">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="8cc37-115">_fnevExtended_</span></span>
  
> <span data-ttu-id="8cc37-116">注册有关特定于特定通讯簿或邮件存储提供程序的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-116">Registers for notifications about events specific to the particular address book or message store provider.</span></span>
    
 <span data-ttu-id="8cc37-117">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="8cc37-117">_fnevNewMail_</span></span>
  
> <span data-ttu-id="8cc37-118">注册有关新邮件到达的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-118">Registers for notifications about the arrival of new messages.</span></span> 
    
 <span data-ttu-id="8cc37-119">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="8cc37-119">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="8cc37-120">注册有关新建对象的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-120">Registers for notifications about the creation of a new object.</span></span>
    
 <span data-ttu-id="8cc37-121">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="8cc37-121">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="8cc37-122">注册有关正在复制的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-122">Registers for notifications about an object being copied.</span></span>
    
 <span data-ttu-id="8cc37-123">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="8cc37-123">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="8cc37-124">注册有关要删除的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-124">Registers for notifications about an object being deleted.</span></span>
    
 <span data-ttu-id="8cc37-125">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="8cc37-125">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="8cc37-126">注册有关要修改的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-126">Registers for notifications about an object being modified.</span></span>
    
 <span data-ttu-id="8cc37-127">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="8cc37-127">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="8cc37-128">注册有关要移动的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-128">Registers for notifications about an object being moved.</span></span>
    
 <span data-ttu-id="8cc37-129">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="8cc37-129">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="8cc37-130">注册有关搜索操作完成的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-130">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="8cc37-131">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8cc37-131">_ulFlags_</span></span>
  
> <span data-ttu-id="8cc37-132">[in]控制通知发生方式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="8cc37-132">[in] A bitmask of flags that controls how notification occurs.</span></span> <span data-ttu-id="8cc37-133">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="8cc37-133">The following flag can be set:</span></span>
    
<span data-ttu-id="8cc37-134">NOTIFY_SYNC</span><span class="sxs-lookup"><span data-stu-id="8cc37-134">NOTIFY_SYNC</span></span> 
  
> <span data-ttu-id="8cc37-135">当调用方调用 [IMAPISupport：：Notify](imapisupport-notify.md) 方法为此通知接收器生成通知时 **，Notify** 应在返回之前执行所有必要的调用来通知接收器。</span><span class="sxs-lookup"><span data-stu-id="8cc37-135">When the caller calls the [IMAPISupport::Notify](imapisupport-notify.md) method to generate notifications for this advise sink, **Notify** should make all necessary calls to advise sinks before returning.</span></span> <span data-ttu-id="8cc37-136">如果未设置此标志，则通知是异步的，当这些进程获得 CPU 控制权时，回调将排队到已订阅和启动的进程。</span><span class="sxs-lookup"><span data-stu-id="8cc37-136">If this flag is not set, notification is asynchronous and callbacks are queued to the processes that have subscribed and started when those processes gain control of the CPU.</span></span> 
    
 <span data-ttu-id="8cc37-137">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="8cc37-137">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="8cc37-138">[in]指向建议接收对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8cc37-138">[in] A pointer to an advise sink object.</span></span> 
    
 <span data-ttu-id="8cc37-139">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="8cc37-139">_lpulConnection_</span></span>
  
> <span data-ttu-id="8cc37-140">[out]指向代表注册的非零连接号的指针。</span><span class="sxs-lookup"><span data-stu-id="8cc37-140">[out] A pointer to a nonzero connection number that represents the registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8cc37-141">返回值</span><span class="sxs-lookup"><span data-stu-id="8cc37-141">Return value</span></span>

<span data-ttu-id="8cc37-142">S_OK</span><span class="sxs-lookup"><span data-stu-id="8cc37-142">S_OK</span></span> 
  
> <span data-ttu-id="8cc37-143">通知注册成功。</span><span class="sxs-lookup"><span data-stu-id="8cc37-143">The notification registration was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8cc37-144">备注</span><span class="sxs-lookup"><span data-stu-id="8cc37-144">Remarks</span></span>

<span data-ttu-id="8cc37-145">**IMAPISupport：：Subscribe** 方法针对所有服务提供商支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="8cc37-145">The **IMAPISupport::Subscribe** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="8cc37-146">服务提供商从 **他们的 Advise** 方法之一调用 **Subscribe，** 以允许 MAPI 管理通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-146">Service providers call **Subscribe** from one of their **Advise** methods to allow MAPI to manage the notifications.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="8cc37-147">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8cc37-147">Notes to callers</span></span>

<span data-ttu-id="8cc37-148">若要使用 MAPI 支持通知方法，请为建议源创建一个键，以通知源应生成有关哪些通知的对象。</span><span class="sxs-lookup"><span data-stu-id="8cc37-148">To use the MAPI support methods for notification, create a key for the advise source the object about which notifications should be generated.</span></span> <span data-ttu-id="8cc37-149">键的值必须是唯一的，并且应轻松地每次对象更改时重新生成。</span><span class="sxs-lookup"><span data-stu-id="8cc37-149">The value of the key must be unique and should be easily regenerated each time the object changes.</span></span> 
  
<span data-ttu-id="8cc37-150">MAPI 使用通知键搜索通过 [HrAllocAdviseSink](hrallocadvisesink.md) 函数注册的任何回调函数，以查找相应的建议源。</span><span class="sxs-lookup"><span data-stu-id="8cc37-150">MAPI uses the notification key to search for any callback functions registered through the [HrAllocAdviseSink](hrallocadvisesink.md) function for the corresponding advise source.</span></span> <span data-ttu-id="8cc37-151">每当需要为相应的建议源生成通知时，将此密钥传递到 **IMAPISupport：：Notify。**</span><span class="sxs-lookup"><span data-stu-id="8cc37-151">Pass this key to **IMAPISupport::Notify** whenever you need to generate a notification for the corresponding advise source.</span></span> 
  
<span data-ttu-id="8cc37-152">the NOTIFY_SYNC flag affects the operation of subsequent calls to **Notify**.</span><span class="sxs-lookup"><span data-stu-id="8cc37-152">The NOTIFY_SYNC flag affects the operation of subsequent calls to **Notify**.</span></span> <span data-ttu-id="8cc37-153">当您设置NOTIFY_SYNC时 **，Notify** 不会返回，直到它发送完所有必需的通知。</span><span class="sxs-lookup"><span data-stu-id="8cc37-153">When you set NOTIFY_SYNC, **Notify** does not return until it has finished sending all of the necessary notifications.</span></span> <span data-ttu-id="8cc37-154">当您未设置NOTIFY_SYNC时 **，Notify** 将异步运行，可能在发送所有通知之前返回。</span><span class="sxs-lookup"><span data-stu-id="8cc37-154">When you do not set NOTIFY_SYNC, **Notify** operates asynchronously, possibly returning before all of the notifications have been sent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8cc37-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cc37-155">See also</span></span>



[<span data-ttu-id="8cc37-156">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="8cc37-156">HrAllocAdviseSink</span></span>](hrallocadvisesink.md)
  
[<span data-ttu-id="8cc37-157">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="8cc37-157">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="8cc37-158">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="8cc37-158">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
  
[<span data-ttu-id="8cc37-159">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="8cc37-159">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="8cc37-160">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="8cc37-160">NOTIFKEY</span></span>](notifkey.md)
  
[<span data-ttu-id="8cc37-161">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8cc37-161">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

