---
title: IMsgStoreStoreLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.StoreLogoff
api_type:
- COM
ms.assetid: 3773c98e-531e-4bdc-a39a-2c3bb7378cd3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: be11c536804682d1baec8188b6d7487c71d411e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348739"
---
# <a name="imsgstorestorelogoff"></a><span data-ttu-id="fc931-103">IMsgStore::StoreLogoff</span><span class="sxs-lookup"><span data-stu-id="fc931-103">IMsgStore::StoreLogoff</span></span>

  
  
<span data-ttu-id="fc931-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fc931-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fc931-105">启用邮件存储的有序注销。</span><span class="sxs-lookup"><span data-stu-id="fc931-105">Enables the orderly logoff of the message store.</span></span>
  
```cpp
HRESULT StoreLogoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="fc931-106">参数</span><span class="sxs-lookup"><span data-stu-id="fc931-106">Parameters</span></span>

 <span data-ttu-id="fc931-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="fc931-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="fc931-108">[in, out]从邮件存储控制注销的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="fc931-108">[in, out] A bitmask of flags that controls logoff from the message store.</span></span> <span data-ttu-id="fc931-109">在输入时, 此参数设置的所有标志都是相互排斥的;呼叫者必须为每个呼叫指定一个标志。</span><span class="sxs-lookup"><span data-stu-id="fc931-109">On input, all flags set for this parameter are mutually exclusive; a caller must specify only one flag per call.</span></span> <span data-ttu-id="fc931-110">以下标志对输入有效:</span><span class="sxs-lookup"><span data-stu-id="fc931-110">The following flags are valid on input:</span></span>
    
<span data-ttu-id="fc931-111">LOGOFF_ABORT</span><span class="sxs-lookup"><span data-stu-id="fc931-111">LOGOFF_ABORT</span></span> 
  
> <span data-ttu-id="fc931-112">在注销之前, 应停止此邮件存储的任何传输提供程序活动。</span><span class="sxs-lookup"><span data-stu-id="fc931-112">Any transport provider activity for this message store should be stopped before logoff.</span></span> <span data-ttu-id="fc931-113">停止活动后, 控件将返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="fc931-113">Control is returned to the caller after activity is stopped.</span></span> <span data-ttu-id="fc931-114">如果发生任何传输提供程序活动, 则不会发生注销, 且在 MAPI 后台处理程序或传输提供程序的行为中不会发生任何变化。</span><span class="sxs-lookup"><span data-stu-id="fc931-114">If any transport provider activity is taking place, the logoff does not occur and no change in the behavior of the MAPI spooler or transport providers occurs.</span></span> <span data-ttu-id="fc931-115">如果传输提供程序活动处于空闲状态, MAPI 后台处理程序将释放该存储区。</span><span class="sxs-lookup"><span data-stu-id="fc931-115">If transport provider activity is idle, the MAPI spooler releases the store.</span></span> 
    
<span data-ttu-id="fc931-116">LOGOFF_NO_WAIT</span><span class="sxs-lookup"><span data-stu-id="fc931-116">LOGOFF_NO_WAIT</span></span> 
  
> <span data-ttu-id="fc931-117">在关闭之前, 邮件存储不应等待传输提供程序中的邮件。</span><span class="sxs-lookup"><span data-stu-id="fc931-117">The message store should not wait for messages from transport providers before closing.</span></span> <span data-ttu-id="fc931-118">发送已准备好发送的出站邮件。</span><span class="sxs-lookup"><span data-stu-id="fc931-118">Outbound messages that are ready to be sent are sent.</span></span> <span data-ttu-id="fc931-119">如果此存储区包含默认收件箱, 则接收任何进程内邮件, 然后禁用进一步的接收。</span><span class="sxs-lookup"><span data-stu-id="fc931-119">If this store contains the default Inbox, any in-process messages are received, and then further reception is disabled.</span></span> <span data-ttu-id="fc931-120">所有活动完成后, MAPI 后台处理程序将释放该存储, 并立即将控制权返回给呼叫者。</span><span class="sxs-lookup"><span data-stu-id="fc931-120">When all activity is complete, the MAPI spooler releases the store, and control is immediately returned to the caller.</span></span> 
    
<span data-ttu-id="fc931-121">LOGOFF_ORDERLY</span><span class="sxs-lookup"><span data-stu-id="fc931-121">LOGOFF_ORDERLY</span></span> 
  
> <span data-ttu-id="fc931-122">在关闭之前, 邮件存储不应等待传输提供程序中的信息。</span><span class="sxs-lookup"><span data-stu-id="fc931-122">The message store should not wait for information from transport providers before closing.</span></span> <span data-ttu-id="fc931-123">当前正在处理的邮件已完成, 但不处理新邮件。</span><span class="sxs-lookup"><span data-stu-id="fc931-123">Messages that are currently being processed are completed, but no new messages are processed.</span></span> <span data-ttu-id="fc931-124">所有活动完成后, MAPI 后台处理程序将释放该存储, 并立即将控制返回到存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="fc931-124">When all activity is complete, the MAPI spooler releases the store, and control is immediately returned to the store provider.</span></span> 
    
<span data-ttu-id="fc931-125">LOGOFF_PURGE</span><span class="sxs-lookup"><span data-stu-id="fc931-125">LOGOFF_PURGE</span></span> 
  
> <span data-ttu-id="fc931-126">注销的工作方式应与设置 LOGOFF_NO_WAIT 标志相同, 但应调用适当的传输提供程序的[IXPLogon:: FlushQueues](ixplogon-flushqueues.md)或[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fc931-126">The logoff should work the same as if the LOGOFF_NO_WAIT flag is set, but either the [IXPLogon::FlushQueues](ixplogon-flushqueues.md) or [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method for the appropriate transport providers should be called.</span></span> <span data-ttu-id="fc931-127">完成后, LOGOFF_PURGE 标志将控制权返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="fc931-127">The LOGOFF_PURGE flag returns control to the caller after completion.</span></span> 
    
<span data-ttu-id="fc931-128">LOGOFF_QUIET</span><span class="sxs-lookup"><span data-stu-id="fc931-128">LOGOFF_QUIET</span></span> 
  
> <span data-ttu-id="fc931-129">如果发生任何传输提供程序活动, 则不应发生注销。</span><span class="sxs-lookup"><span data-stu-id="fc931-129">If any transport provider activity is taking place, the logoff should not occur.</span></span>
    
    The following flags are valid on output:
    
<span data-ttu-id="fc931-130">LOGOFF_INBOUND</span><span class="sxs-lookup"><span data-stu-id="fc931-130">LOGOFF_INBOUND</span></span> 
  
> <span data-ttu-id="fc931-131">入站邮件当前正在到达。</span><span class="sxs-lookup"><span data-stu-id="fc931-131">Inbound messages are currently arriving.</span></span>
    
<span data-ttu-id="fc931-132">LOGOFF_OUTBOUND</span><span class="sxs-lookup"><span data-stu-id="fc931-132">LOGOFF_OUTBOUND</span></span> 
  
> <span data-ttu-id="fc931-133">出站邮件正处于发送过程中。</span><span class="sxs-lookup"><span data-stu-id="fc931-133">Outbound messages are in the process of being sent.</span></span>
    
<span data-ttu-id="fc931-134">LOGOFF_OUTBOUND_QUEUE</span><span class="sxs-lookup"><span data-stu-id="fc931-134">LOGOFF_OUTBOUND_QUEUE</span></span> 
  
> <span data-ttu-id="fc931-135">出站邮件挂起 (即它们位于 "发件箱" 中)。</span><span class="sxs-lookup"><span data-stu-id="fc931-135">Outbound messages are pending (that is, they are in the Outbox).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fc931-136">返回值</span><span class="sxs-lookup"><span data-stu-id="fc931-136">Return value</span></span>

<span data-ttu-id="fc931-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc931-137">S_OK</span></span> 
  
> <span data-ttu-id="fc931-138">已成功完成注销。</span><span class="sxs-lookup"><span data-stu-id="fc931-138">The logoff completed successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fc931-139">注解</span><span class="sxs-lookup"><span data-stu-id="fc931-139">Remarks</span></span>

<span data-ttu-id="fc931-140">**IMsgStore:: StoreLogoff**方法 exerts 控制邮件存储和传输提供程序在注销过程中的交互。</span><span class="sxs-lookup"><span data-stu-id="fc931-140">The **IMsgStore::StoreLogoff** method exerts control over the interaction of the message store and transport providers during the logoff process.</span></span> <span data-ttu-id="fc931-141">调用**StoreLogoff**仅对仅由呼叫者使用的邮件存储区有效。</span><span class="sxs-lookup"><span data-stu-id="fc931-141">Calling **StoreLogoff** is valid only for message stores that are being used only by the caller.</span></span> <span data-ttu-id="fc931-142">例如, 当两个客户端使用相同的邮件存储库, 并且其中一个调用**StoreLogoff**时, 邮件存储将立即发布, 并将控制权返回给呼叫客户端。</span><span class="sxs-lookup"><span data-stu-id="fc931-142">For example, when two clients are using the same message store and one of them calls **StoreLogoff**, the message store is immediately released and control is returned to the calling client.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="fc931-143">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="fc931-143">Notes to implementers</span></span>

<span data-ttu-id="fc931-144">保存传递给**StoreLogoff**的标志, 并在调用[IMAPISupport:: StoreLogoffTransports](imapisupport-storelogofftransports.md)方法时传递这些标志。</span><span class="sxs-lookup"><span data-stu-id="fc931-144">Save the flags that are passed to **StoreLogoff** and pass them when you call the [IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md) method.</span></span> <span data-ttu-id="fc931-145">在邮件存储区的引用计数降至0时, 不要调用**StoreLogoffTransports** 。</span><span class="sxs-lookup"><span data-stu-id="fc931-145">Do not call **StoreLogoffTransports** until the message store's reference count drops to zero.</span></span> <span data-ttu-id="fc931-146">对**StoreLogoffTransports**的多个调用只是覆盖已保存的标志。</span><span class="sxs-lookup"><span data-stu-id="fc931-146">Multiple calls to **StoreLogoffTransports** simply overwrite the saved flags.</span></span> 
  
<span data-ttu-id="fc931-147">如果在邮件存储区的引用计数达到零之前未对**StoreLogoff**进行任何调用, 请在传递给**StoreLogoffTransports**的_ulFlags_参数中设置 LOGOFF_ABORT 标志。</span><span class="sxs-lookup"><span data-stu-id="fc931-147">If no call has been made to **StoreLogoff** before the message store's reference count reaches zero, set the LOGOFF_ABORT flag in the  _ulFlags_ parameter that you pass to **StoreLogoffTransports**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc931-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc931-148">See also</span></span>



[<span data-ttu-id="fc931-149">IMAPIStatus::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="fc931-149">IMAPIStatus::FlushQueues</span></span>](imapistatus-flushqueues.md)
  
[<span data-ttu-id="fc931-150">IMAPISupport::StoreLogoffTransports</span><span class="sxs-lookup"><span data-stu-id="fc931-150">IMAPISupport::StoreLogoffTransports</span></span>](imapisupport-storelogofftransports.md)
  
[<span data-ttu-id="fc931-151">IXPLogon::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="fc931-151">IXPLogon::FlushQueues</span></span>](ixplogon-flushqueues.md)
  
[<span data-ttu-id="fc931-152">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fc931-152">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

