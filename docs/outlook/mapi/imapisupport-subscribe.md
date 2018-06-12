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
ms.openlocfilehash: 6658f1c4bcfaf7557d9b53c5e70d87e124475580
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775694"
---
# <a name="imapisupportsubscribe"></a><span data-ttu-id="77860-103">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="77860-103">IMAPISupport::Subscribe</span></span>

  
  
<span data-ttu-id="77860-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="77860-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="77860-105">注册以接收通知通过 MAPI 通知接收器。</span><span class="sxs-lookup"><span data-stu-id="77860-105">Registers an advise sink to receive notifications through MAPI.</span></span>
  
```cpp
HRESULT Subscribe(
LPNOTIFKEY lpKey,
ULONG ulEventMask,
ULONG ulFlags,
LPMAPIADVISESINK lpAdviseSink,
ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="77860-106">参数</span><span class="sxs-lookup"><span data-stu-id="77860-106">Parameters</span></span>

 <span data-ttu-id="77860-107">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="77860-107">_lpKey_</span></span>
  
> <span data-ttu-id="77860-108">[in]指向代表 advise 源对象的通知键的指针。</span><span class="sxs-lookup"><span data-stu-id="77860-108">[in] A pointer to a notification key that represents the advise source object.</span></span> <span data-ttu-id="77860-109">_LpKey_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="77860-109">The  _lpKey_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="77860-110">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="77860-110">_ulEventMask_</span></span>
  
> <span data-ttu-id="77860-111">[in]指示呼叫者感兴趣，并应包含在注册通知事件的类型的值的掩码。</span><span class="sxs-lookup"><span data-stu-id="77860-111">[in] A mask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="77860-112">以下是有效值：</span><span class="sxs-lookup"><span data-stu-id="77860-112">The following values are valid:</span></span>
    
 <span data-ttu-id="77860-113">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="77860-113">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="77860-114">有关严重错误，例如内存不足通知注册。</span><span class="sxs-lookup"><span data-stu-id="77860-114">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
 <span data-ttu-id="77860-115">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="77860-115">_fnevExtended_</span></span>
  
> <span data-ttu-id="77860-116">有关特定于特定的通讯簿或消息的事件通知的 register 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="77860-116">Registers for notifications about events specific to the particular address book or message store provider.</span></span>
    
 <span data-ttu-id="77860-117">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="77860-117">_fnevNewMail_</span></span>
  
> <span data-ttu-id="77860-118">有关新邮件的到达通知注册。</span><span class="sxs-lookup"><span data-stu-id="77860-118">Registers for notifications about the arrival of new messages.</span></span> 
    
 <span data-ttu-id="77860-119">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="77860-119">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="77860-120">有关创建新对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="77860-120">Registers for notifications about the creation of a new object.</span></span>
    
 <span data-ttu-id="77860-121">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="77860-121">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="77860-122">有关要复制的对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="77860-122">Registers for notifications about an object being copied.</span></span>
    
 <span data-ttu-id="77860-123">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="77860-123">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="77860-124">有关对象正在删除通知的注册。</span><span class="sxs-lookup"><span data-stu-id="77860-124">Registers for notifications about an object being deleted.</span></span>
    
 <span data-ttu-id="77860-125">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="77860-125">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="77860-126">有关修改对象的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="77860-126">Registers for notifications about an object being modified.</span></span>
    
 <span data-ttu-id="77860-127">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="77860-127">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="77860-128">有关被移动对象通知注册。</span><span class="sxs-lookup"><span data-stu-id="77860-128">Registers for notifications about an object being moved.</span></span>
    
 <span data-ttu-id="77860-129">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="77860-129">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="77860-130">有关搜索操作完成通知注册。</span><span class="sxs-lookup"><span data-stu-id="77860-130">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="77860-131">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="77860-131">_ulFlags_</span></span>
  
> <span data-ttu-id="77860-132">[in]位掩码的标志，控制如何将出现通知。</span><span class="sxs-lookup"><span data-stu-id="77860-132">[in] A bitmask of flags that controls how notification occurs.</span></span> <span data-ttu-id="77860-133">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="77860-133">The following flag can be set:</span></span>
    
<span data-ttu-id="77860-134">NOTIFY_SYNC</span><span class="sxs-lookup"><span data-stu-id="77860-134">NOTIFY_SYNC</span></span> 
  
> <span data-ttu-id="77860-135">呼叫者呼叫时要为此通知接收器生成通知的[IMAPISupport::Notify](imapisupport-notify.md)方法， **Notify**应进行所有必需的呼叫告知接收器返回之前。</span><span class="sxs-lookup"><span data-stu-id="77860-135">When the caller calls the [IMAPISupport::Notify](imapisupport-notify.md) method to generate notifications for this advise sink, **Notify** should make all necessary calls to advise sinks before returning.</span></span> <span data-ttu-id="77860-136">如果未设置此标志，通知是异步; 回调排队到已订阅并启动时的 CPU 控制这些过程的过程。</span><span class="sxs-lookup"><span data-stu-id="77860-136">If this flag is not set, notification is asynchronous and callbacks are queued to the processes that have subscribed and started when those processes gain control of the CPU.</span></span> 
    
 <span data-ttu-id="77860-137">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="77860-137">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="77860-138">[in]指向 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="77860-138">[in] A pointer to an advise sink object.</span></span> 
    
 <span data-ttu-id="77860-139">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="77860-139">_lpulConnection_</span></span>
  
> <span data-ttu-id="77860-140">[输出]一个指向代表注册非零值的连接数。</span><span class="sxs-lookup"><span data-stu-id="77860-140">[out] A pointer to a nonzero connection number that represents the registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="77860-141">返回值</span><span class="sxs-lookup"><span data-stu-id="77860-141">Return value</span></span>

<span data-ttu-id="77860-142">S_OK</span><span class="sxs-lookup"><span data-stu-id="77860-142">S_OK</span></span> 
  
> <span data-ttu-id="77860-143">通知注册成功。</span><span class="sxs-lookup"><span data-stu-id="77860-143">The notification registration was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="77860-144">备注</span><span class="sxs-lookup"><span data-stu-id="77860-144">Remarks</span></span>

<span data-ttu-id="77860-145">**IMAPISupport::Subscribe**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="77860-145">The **IMAPISupport::Subscribe** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="77860-146">服务提供程序从其**Advise**方法之一来允许 MAPI 管理通知调用**订阅**。</span><span class="sxs-lookup"><span data-stu-id="77860-146">Service providers call **Subscribe** from one of their **Advise** methods to allow MAPI to manage the notifications.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="77860-147">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="77860-147">Notes to callers</span></span>

<span data-ttu-id="77860-148">若要使用通知 MAPI 支持方法，创建 advise 源应生成有关的通知的对象的键。</span><span class="sxs-lookup"><span data-stu-id="77860-148">To use the MAPI support methods for notification, create a key for the advise source the object about which notifications should be generated.</span></span> <span data-ttu-id="77860-149">项的值必须是唯一的并应轻松地重新生成对象更改每次。</span><span class="sxs-lookup"><span data-stu-id="77860-149">The value of the key must be unique and should be easily regenerated each time the object changes.</span></span> 
  
<span data-ttu-id="77860-150">MAPI 使用通知密钥来通过相应 advise 源的[HrAllocAdviseSink](hrallocadvisesink.md)函数注册任何回调函数中搜索。</span><span class="sxs-lookup"><span data-stu-id="77860-150">MAPI uses the notification key to search for any callback functions registered through the [HrAllocAdviseSink](hrallocadvisesink.md) function for the corresponding advise source.</span></span> <span data-ttu-id="77860-151">无论何时需要生成相应的 advise 源通知，请将此参数传递给**IMAPISupport::Notify** 。</span><span class="sxs-lookup"><span data-stu-id="77860-151">Pass this key to **IMAPISupport::Notify** whenever you need to generate a notification for the corresponding advise source.</span></span> 
  
<span data-ttu-id="77860-152">NOTIFY_SYNC 标志会影响后续调用**Notify**的操作。</span><span class="sxs-lookup"><span data-stu-id="77860-152">The NOTIFY_SYNC flag affects the operation of subsequent calls to **Notify**.</span></span> <span data-ttu-id="77860-153">NOTIFY_SYNC 设置时，才完发送的所有必要通知会返回**通知**。</span><span class="sxs-lookup"><span data-stu-id="77860-153">When you set NOTIFY_SYNC, **Notify** does not return until it has finished sending all of the necessary notifications.</span></span> <span data-ttu-id="77860-154">时不设置 NOTIFY_SYNC，**通知**的操作以异步方式，可能返回之前已发送的所有通知。</span><span class="sxs-lookup"><span data-stu-id="77860-154">When you do not set NOTIFY_SYNC, **Notify** operates asynchronously, possibly returning before all of the notifications have been sent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="77860-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77860-155">See also</span></span>



[<span data-ttu-id="77860-156">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="77860-156">HrAllocAdviseSink</span></span>](hrallocadvisesink.md)
  
[<span data-ttu-id="77860-157">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="77860-157">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="77860-158">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="77860-158">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
  
[<span data-ttu-id="77860-159">通知</span><span class="sxs-lookup"><span data-stu-id="77860-159">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="77860-160">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="77860-160">NOTIFKEY</span></span>](notifkey.md)
  
[<span data-ttu-id="77860-161">IMAPISupport: IUnknown</span><span class="sxs-lookup"><span data-stu-id="77860-161">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

