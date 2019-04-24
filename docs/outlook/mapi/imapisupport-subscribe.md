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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328956"
---
# <a name="imapisupportsubscribe"></a><span data-ttu-id="3e1da-103">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="3e1da-103">IMAPISupport::Subscribe</span></span>

  
  
<span data-ttu-id="3e1da-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e1da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e1da-105">注册通知接收器以通过 MAPI 接收通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-105">Registers an advise sink to receive notifications through MAPI.</span></span>
  
```cpp
HRESULT Subscribe(
LPNOTIFKEY lpKey,
ULONG ulEventMask,
ULONG ulFlags,
LPMAPIADVISESINK lpAdviseSink,
ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="3e1da-106">参数</span><span class="sxs-lookup"><span data-stu-id="3e1da-106">Parameters</span></span>

 <span data-ttu-id="3e1da-107">_lpKey_</span><span class="sxs-lookup"><span data-stu-id="3e1da-107">_lpKey_</span></span>
  
> <span data-ttu-id="3e1da-108">实时指向表示 "通知源" 对象的通知密钥的指针。</span><span class="sxs-lookup"><span data-stu-id="3e1da-108">[in] A pointer to a notification key that represents the advise source object.</span></span> <span data-ttu-id="3e1da-109">_lpKey_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e1da-109">The  _lpKey_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="3e1da-110">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="3e1da-110">_ulEventMask_</span></span>
  
> <span data-ttu-id="3e1da-111">实时指示呼叫者感兴趣且应包含在注册中的通知事件类型的值掩码。</span><span class="sxs-lookup"><span data-stu-id="3e1da-111">[in] A mask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="3e1da-112">以下值是有效的:</span><span class="sxs-lookup"><span data-stu-id="3e1da-112">The following values are valid:</span></span>
    
 <span data-ttu-id="3e1da-113">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="3e1da-113">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="3e1da-114">注册有关严重错误 (如内存不足) 的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-114">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
 <span data-ttu-id="3e1da-115">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="3e1da-115">_fnevExtended_</span></span>
  
> <span data-ttu-id="3e1da-116">注册有关特定通讯簿或邮件存储提供程序特定的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-116">Registers for notifications about events specific to the particular address book or message store provider.</span></span>
    
 <span data-ttu-id="3e1da-117">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="3e1da-117">_fnevNewMail_</span></span>
  
> <span data-ttu-id="3e1da-118">注册有关新邮件到达的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-118">Registers for notifications about the arrival of new messages.</span></span> 
    
 <span data-ttu-id="3e1da-119">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="3e1da-119">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="3e1da-120">注册有关创建新对象的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-120">Registers for notifications about the creation of a new object.</span></span>
    
 <span data-ttu-id="3e1da-121">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="3e1da-121">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="3e1da-122">注册有关要复制的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-122">Registers for notifications about an object being copied.</span></span>
    
 <span data-ttu-id="3e1da-123">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="3e1da-123">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="3e1da-124">注册有关要删除的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-124">Registers for notifications about an object being deleted.</span></span>
    
 <span data-ttu-id="3e1da-125">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="3e1da-125">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="3e1da-126">注册有关要修改的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-126">Registers for notifications about an object being modified.</span></span>
    
 <span data-ttu-id="3e1da-127">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="3e1da-127">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="3e1da-128">注册有关要移动的对象的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-128">Registers for notifications about an object being moved.</span></span>
    
 <span data-ttu-id="3e1da-129">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="3e1da-129">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="3e1da-130">注册有关搜索操作完成的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-130">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="3e1da-131">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3e1da-131">_ulFlags_</span></span>
  
> <span data-ttu-id="3e1da-132">实时用于控制通知发生方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="3e1da-132">[in] A bitmask of flags that controls how notification occurs.</span></span> <span data-ttu-id="3e1da-133">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="3e1da-133">The following flag can be set:</span></span>
    
<span data-ttu-id="3e1da-134">NOTIFY_SYNC</span><span class="sxs-lookup"><span data-stu-id="3e1da-134">NOTIFY_SYNC</span></span> 
  
> <span data-ttu-id="3e1da-135">当呼叫者调用[IMAPISupport:: Notify](imapisupport-notify.md)方法为此通知接收器生成通知时, **Notify**应在返回之前进行所有必要的调用来通知接收器。</span><span class="sxs-lookup"><span data-stu-id="3e1da-135">When the caller calls the [IMAPISupport::Notify](imapisupport-notify.md) method to generate notifications for this advise sink, **Notify** should make all necessary calls to advise sinks before returning.</span></span> <span data-ttu-id="3e1da-136">如果未设置此标志, 则通知是异步的, 并且回调会在这些进程获得对 CPU 的控制时订阅并启动的进程进行排队。</span><span class="sxs-lookup"><span data-stu-id="3e1da-136">If this flag is not set, notification is asynchronous and callbacks are queued to the processes that have subscribed and started when those processes gain control of the CPU.</span></span> 
    
 <span data-ttu-id="3e1da-137">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="3e1da-137">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="3e1da-138">实时指向建议接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3e1da-138">[in] A pointer to an advise sink object.</span></span> 
    
 <span data-ttu-id="3e1da-139">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="3e1da-139">_lpulConnection_</span></span>
  
> <span data-ttu-id="3e1da-140">排除指向代表注册的非零连接号码的指针。</span><span class="sxs-lookup"><span data-stu-id="3e1da-140">[out] A pointer to a nonzero connection number that represents the registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3e1da-141">返回值</span><span class="sxs-lookup"><span data-stu-id="3e1da-141">Return value</span></span>

<span data-ttu-id="3e1da-142">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e1da-142">S_OK</span></span> 
  
> <span data-ttu-id="3e1da-143">通知注册已成功。</span><span class="sxs-lookup"><span data-stu-id="3e1da-143">The notification registration was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3e1da-144">注解</span><span class="sxs-lookup"><span data-stu-id="3e1da-144">Remarks</span></span>

<span data-ttu-id="3e1da-145">**IMAPISupport:: 订阅**方法是为所有服务提供程序支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="3e1da-145">The **IMAPISupport::Subscribe** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="3e1da-146">服务提供商从他们的一种**建议**方法中调用**订阅**, 以允许 MAPI 管理通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-146">Service providers call **Subscribe** from one of their **Advise** methods to allow MAPI to manage the notifications.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3e1da-147">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3e1da-147">Notes to callers</span></span>

<span data-ttu-id="3e1da-148">若要将 MAPI 支持方法用于通知, 请为建议源创建一个注册表项, 以了解应生成的通知的对象。</span><span class="sxs-lookup"><span data-stu-id="3e1da-148">To use the MAPI support methods for notification, create a key for the advise source the object about which notifications should be generated.</span></span> <span data-ttu-id="3e1da-149">键的值必须是唯一的, 并且应在每次对象更改时轻松地重新生成。</span><span class="sxs-lookup"><span data-stu-id="3e1da-149">The value of the key must be unique and should be easily regenerated each time the object changes.</span></span> 
  
<span data-ttu-id="3e1da-150">MAPI 使用通知密钥搜索通过[HrAllocAdviseSink](hrallocadvisesink.md)函数为相应的建议源注册的任何回调函数。</span><span class="sxs-lookup"><span data-stu-id="3e1da-150">MAPI uses the notification key to search for any callback functions registered through the [HrAllocAdviseSink](hrallocadvisesink.md) function for the corresponding advise source.</span></span> <span data-ttu-id="3e1da-151">将此项传递给**IMAPISupport::** 无论何时需要为相应的建议源生成通知, 都会发出通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-151">Pass this key to **IMAPISupport::Notify** whenever you need to generate a notification for the corresponding advise source.</span></span> 
  
<span data-ttu-id="3e1da-152">NOTIFY_SYNC 标志将影响后续调用以进行**通知**的操作。</span><span class="sxs-lookup"><span data-stu-id="3e1da-152">The NOTIFY_SYNC flag affects the operation of subsequent calls to **Notify**.</span></span> <span data-ttu-id="3e1da-153">设置 NOTIFY_SYNC 时,**通知**不会返回, 直到发送完所有必需的通知。</span><span class="sxs-lookup"><span data-stu-id="3e1da-153">When you set NOTIFY_SYNC, **Notify** does not return until it has finished sending all of the necessary notifications.</span></span> <span data-ttu-id="3e1da-154">如果不设置 NOTIFY_SYNC, 则在\*\*\*\* 发送所有通知之前, 以异步方式运行 (可能返回)。</span><span class="sxs-lookup"><span data-stu-id="3e1da-154">When you do not set NOTIFY_SYNC, **Notify** operates asynchronously, possibly returning before all of the notifications have been sent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3e1da-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e1da-155">See also</span></span>



[<span data-ttu-id="3e1da-156">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="3e1da-156">HrAllocAdviseSink</span></span>](hrallocadvisesink.md)
  
[<span data-ttu-id="3e1da-157">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="3e1da-157">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="3e1da-158">IMAPISupport::Notify</span><span class="sxs-lookup"><span data-stu-id="3e1da-158">IMAPISupport::Notify</span></span>](imapisupport-notify.md)
  
[<span data-ttu-id="3e1da-159">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="3e1da-159">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="3e1da-160">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="3e1da-160">NOTIFKEY</span></span>](notifkey.md)
  
[<span data-ttu-id="3e1da-161">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3e1da-161">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

