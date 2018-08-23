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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: beeca6ba958c38e12fba7dbc2884c81e58bdf3c4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590118"
---
# <a name="imapisupportsubscribe"></a><span data-ttu-id="e329a-103">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="e329a-103">IMAPISupport::Subscribe</span></span>

  
  
<span data-ttu-id="e329a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e329a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e329a-105">注册以接收通知通过 MAPI 通知接收器。</span><span class="sxs-lookup"><span data-stu-id="e329a-105">Registers an advise sink to receive notifications through MAPI.</span></span>
  
```cpp
HRESULT Subscribe(
LPNOTIFKEY lpKey,
ULONG ulEventMask,
ULONG ulFlags,
LPMAPIADVISESINK lpAdviseSink,
ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="e329a-106">参数</span><span class="sxs-lookup"><span data-stu-id="e329a-106">Parameters</span></span>

 <span data-ttu-id="e329a-107">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="e329a-107">_lpKey_</span></span>
  
> <span data-ttu-id="e329a-108">[in]指向代表 advise 源对象的通知键的指针。</span><span class="sxs-lookup"><span data-stu-id="e329a-108">[in] A pointer to a notification key that represents the advise source object.</span></span> <span data-ttu-id="e329a-109">_LpKey_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e329a-109">The  _lpKey_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="e329a-110">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="e329a-110">_ulEventMask_</span></span>
  
> <span data-ttu-id="e329a-111">[in]指示呼叫者感兴趣，并应包含在注册通知事件的类型的值的掩码。</span><span class="sxs-lookup"><span data-stu-id="e329a-111">[in] A mask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="e329a-112">以下是有效值：</span><span class="sxs-lookup"><span data-stu-id="e329a-112">The following values are valid:</span></span>
    
 <span data-ttu-id="e329a-113">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="e329a-113">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="e329a-114">有关严重错误，例如内存不足通知注册。</span><span class="sxs-lookup"><span data-stu-id="e329a-114">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
 <span data-ttu-id="e329a-115">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="e329a-115">_fnevExtended_</span></span>
  
> <span data-ttu-id="e329a-116">有关特定于特定的通讯簿或消息的事件通知的 register 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="e329a-116">Registers for notifications about events specific to the particular address book or message store provider.</span></span>
    
 <span data-ttu-id="e329a-117">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="e329a-117">_fnevNewMail_</span></span>
  
> <span data-ttu-id="e329a-118">有关新邮件的到达通知注册。</span><span class="sxs-lookup"><span data-stu-id="e329a-118">Registers for notifications about the arrival of new messages.</span></span> 
    
 <span data-ttu-id="e329a-119">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="e329a-119">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="e329a-120">有关创建新对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="e329a-120">Registers for notifications about the creation of a new object.</span></span>
    
 <span data-ttu-id="e329a-121">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="e329a-121">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="e329a-122">有关要复制的对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="e329a-122">Registers for notifications about an object being copied.</span></span>
    
 <span data-ttu-id="e329a-123">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="e329a-123">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="e329a-124">有关对象正在删除通知的注册。</span><span class="sxs-lookup"><span data-stu-id="e329a-124">Registers for notifications about an object being deleted.</span></span>
    
 <span data-ttu-id="e329a-125">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="e329a-125">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="e329a-126">有关修改对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="e329a-126">Registers for notifications about an object being modified.</span></span>
    
 <span data-ttu-id="e329a-127">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="e329a-127">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="e329a-128">有关被移动对象通知注册。</span><span class="sxs-lookup"><span data-stu-id="e329a-128">Registers for notifications about an object being moved.</span></span>
    
 <span data-ttu-id="e329a-129">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="e329a-129">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="e329a-130">有关搜索操作完成通知注册。</span><span class="sxs-lookup"><span data-stu-id="e329a-130">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="e329a-131">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e329a-131">_ulFlags_</span></span>
  
> <span data-ttu-id="e329a-132">[in]位掩码的标志，控制如何将出现通知。</span><span class="sxs-lookup"><span data-stu-id="e329a-132">[in] A bitmask of flags that controls how notification occurs.</span></span> <span data-ttu-id="e329a-133">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="e329a-133">The following flag can be set:</span></span>
    
<span data-ttu-id="e329a-134">NOTIFY_SYNC</span><span class="sxs-lookup"><span data-stu-id="e329a-134">NOTIFY_SYNC</span></span> 
  
> <span data-ttu-id="e329a-135">呼叫者呼叫时要为此通知接收器生成通知的[IMAPISupport::Notify](imapisupport-notify.md)方法， **Notify**应进行所有必需的呼叫告知接收器返回之前。</span><span class="sxs-lookup"><span data-stu-id="e329a-135">When the caller calls the [IMAPISupport::Notify](imapisupport-notify.md) method to generate notifications for this advise sink, **Notify** should make all necessary calls to advise sinks before returning.</span></span> <span data-ttu-id="e329a-136">如果未设置此标志，通知是异步; 回调排队到已订阅并启动时的 CPU 控制这些过程的过程。</span><span class="sxs-lookup"><span data-stu-id="e329a-136">If this flag is not set, notification is asynchronous and callbacks are queued to the processes that have subscribed and started when those processes gain control of the CPU.</span></span> 
    
 <span data-ttu-id="e329a-137">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="e329a-137">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="e329a-138">[in]指向 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e329a-138">[in] A pointer to an advise sink object.</span></span> 
    
 <span data-ttu-id="e329a-139">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="e329a-139">_lpulConnection_</span></span>
  
> <span data-ttu-id="e329a-140">[输出]一个指向代表注册非零值的连接数。</span><span class="sxs-lookup"><span data-stu-id="e329a-140">[out] A pointer to a nonzero connection number that represents the registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e329a-141">返回值</span><span class="sxs-lookup"><span data-stu-id="e329a-141">Return value</span></span>

<span data-ttu-id="e329a-142">S_OK</span><span class="sxs-lookup"><span data-stu-id="e329a-142">S_OK</span></span> 
  
> <span data-ttu-id="e329a-143">通知注册成功。</span><span class="sxs-lookup"><span data-stu-id="e329a-143">The notification registration was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e329a-144">注解</span><span class="sxs-lookup"><span data-stu-id="e329a-144">Remarks</span></span>

<span data-ttu-id="e329a-145">**IMAPISupport::Subscribe**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="e329a-145">The **IMAPISupport::Subscribe** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="e329a-146">服务提供程序从其**Advise**方法之一来允许 MAPI 管理通知调用**订阅**。</span><span class="sxs-lookup"><span data-stu-id="e329a-146">Service providers call **Subscribe** from one of their **Advise** methods to allow MAPI to manage the notifications.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e329a-147">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e329a-147">Notes to callers</span></span>

<span data-ttu-id="e329a-148">若要使用通知 MAPI 支持方法，创建 advise 源应生成有关的通知的对象的键。</span><span class="sxs-lookup"><span data-stu-id="e329a-148">To use the MAPI support methods for notification, create a key for the advise source the object about which notifications should be generated.</span></span> <span data-ttu-id="e329a-149">项的值必须是唯一的并应轻松地重新生成对象更改每次。</span><span class="sxs-lookup"><span data-stu-id="e329a-149">The value of the key must be unique and should be easily regenerated each time the object changes.</span></span> 
  
<span data-ttu-id="e329a-150">MAPI 使用通知密钥来通过相应 advise 源的[HrAllocAdviseSink](hrallocadvisesink.md)函数注册任何回调函数中搜索。</span><span class="sxs-lookup"><span data-stu-id="e329a-150">MAPI uses the notification key to search for any callback functions registered through the [HrAllocAdviseSink](hrallocadvisesink.md) function for the corresponding advise source.</span></span> <span data-ttu-id="e329a-151">无论何时需要生成相应的 advise 源通知，请将此参数传递给**IMAPISupport::Notify** 。</span><span class="sxs-lookup"><span data-stu-id="e329a-151">Pass this key to **IMAPISupport::Notify** whenever you need to generate a notification for the corresponding advise source.</span></span> 
  
<span data-ttu-id="e329a-152">NOTIFY_SYNC 标志会影响后续调用**Notify**的操作。</span><span class="sxs-lookup"><span data-stu-id="e329a-152">The NOTIFY_SYNC flag affects the operation of subsequent calls to **Notify**.</span></span> <span data-ttu-id="e329a-153">NOTIFY_SYNC 设置时，才完发送的所有必要通知会返回**通知**。</span><span class="sxs-lookup"><span data-stu-id="e329a-153">When you set NOTIFY_SYNC, **Notify** does not return until it has finished sending all of the necessary notifications.</span></span> <span data-ttu-id="e329a-154">时不设置 NOTIFY_SYNC，**通知**的操作以异步方式，可能返回之前已发送的所有通知。</span><span class="sxs-lookup"><span data-stu-id="e329a-154">When you do not set NOTIFY_SYNC, **Notify** operates asynchronously, possibly returning before all of the notifications have been sent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e329a-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e329a-155">See also</span></span>



[<span data-ttu-id="e329a-156">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="e329a-156">HrAllocAdviseSink</span></span>](hrallocadvisesink.md)
  
[<span data-ttu-id="e329a-157">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="e329a-157">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="e329a-158">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="e329a-158">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
  
[<span data-ttu-id="e329a-159">通知</span><span class="sxs-lookup"><span data-stu-id="e329a-159">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="e329a-160">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="e329a-160">NOTIFKEY</span></span>](notifkey.md)
  
[<span data-ttu-id="e329a-161">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e329a-161">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

