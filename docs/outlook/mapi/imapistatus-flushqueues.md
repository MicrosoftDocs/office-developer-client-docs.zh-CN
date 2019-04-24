---
title: IMAPIStatusFlushQueues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.FlushQueues
api_type:
- COM
ms.assetid: d6b01a91-b452-4b2c-9802-698e7b0f4169
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5f8396ca84192e485d33fb5a96f641361b717584
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328192"
---
# <a name="imapistatusflushqueues"></a><span data-ttu-id="370ab-103">IMAPIStatus::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="370ab-103">IMAPIStatus::FlushQueues</span></span>

  
  
<span data-ttu-id="370ab-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="370ab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="370ab-105">强制立即上载或下载所有等待发送或接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="370ab-105">Forces all messages waiting to be sent or received to be immediately uploaded or downloaded.</span></span> <span data-ttu-id="370ab-106">传输提供程序实现的 MAPI 后台处理程序状态对象和 status 对象支持此方法。</span><span class="sxs-lookup"><span data-stu-id="370ab-106">The MAPI spooler status object and status objects that transport providers implement support this method.</span></span>
  
```cpp
HRESULT FlushQueues(
  ULONG_PTR ulUIParam,
  ULONG cbTargetTransport,
  LPENTRYID lpTargetTransport,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="370ab-107">参数</span><span class="sxs-lookup"><span data-stu-id="370ab-107">Parameters</span></span>

 <span data-ttu-id="370ab-108">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="370ab-108">_ulUIParam_</span></span>
  
> <span data-ttu-id="370ab-109">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="370ab-109">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="370ab-110">_cbTargetTransport_</span><span class="sxs-lookup"><span data-stu-id="370ab-110">_cbTargetTransport_</span></span>
  
> <span data-ttu-id="370ab-111">实时条目标识符中由_lpTargetTransport_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="370ab-111">[in] The byte count in the entry identifier pointed to by the  _lpTargetTransport_ parameter.</span></span> <span data-ttu-id="370ab-112">仅在对 MAPI 后台处理程序的状态对象的调用上设置_cbTargetTransport_参数。</span><span class="sxs-lookup"><span data-stu-id="370ab-112">The  _cbTargetTransport_ parameter is set only on calls to the MAPI spooler's status object.</span></span> <span data-ttu-id="370ab-113">对于传输提供程序的调用, _cbTargetTransport_参数设置为0。</span><span class="sxs-lookup"><span data-stu-id="370ab-113">For calls to a transport provider, the  _cbTargetTransport_ parameter is set to 0.</span></span> 
    
 <span data-ttu-id="370ab-114">_lpTargetTransport_</span><span class="sxs-lookup"><span data-stu-id="370ab-114">_lpTargetTransport_</span></span>
  
> <span data-ttu-id="370ab-115">实时指向传输提供程序的条目标识符的指针, 该传输提供程序将刷新其邮件队列。</span><span class="sxs-lookup"><span data-stu-id="370ab-115">[in] A pointer to the entry identifier of the transport provider that is to flush its message queues.</span></span> <span data-ttu-id="370ab-116">仅在对 MAPI 后台处理程序的状态对象的调用上设置_lpTargetTransport_参数。</span><span class="sxs-lookup"><span data-stu-id="370ab-116">The  _lpTargetTransport_ parameter is set only on calls to the MAPI spooler's status object.</span></span> <span data-ttu-id="370ab-117">对于传输提供程序的调用, _lpTargetTransport_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="370ab-117">For calls to a transport provider, the  _lpTargetTransport_ parameter is set to NULL.</span></span> 
    
 <span data-ttu-id="370ab-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="370ab-118">_ulFlags_</span></span>
  
> <span data-ttu-id="370ab-119">实时控制刷新操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="370ab-119">[in] A bitmask of flags that controls the flush operation.</span></span> <span data-ttu-id="370ab-120">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="370ab-120">The following flags can be set:</span></span>
    
<span data-ttu-id="370ab-121">FLUSH_ASYNC_OK</span><span class="sxs-lookup"><span data-stu-id="370ab-121">FLUSH_ASYNC_OK</span></span> 
  
> <span data-ttu-id="370ab-122">刷新操作可以异步发生。</span><span class="sxs-lookup"><span data-stu-id="370ab-122">The flush operation can occur asynchronously.</span></span> <span data-ttu-id="370ab-123">此标志仅适用于 MAPI 后台处理程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="370ab-123">This flag applies only to the MAPI spooler's status object.</span></span> 
    
<span data-ttu-id="370ab-124">FLUSH_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="370ab-124">FLUSH_DOWNLOAD</span></span> 
  
> <span data-ttu-id="370ab-125">应刷新传入邮件队列。</span><span class="sxs-lookup"><span data-stu-id="370ab-125">The incoming message queues should be flushed.</span></span>
    
<span data-ttu-id="370ab-126">FLUSH_FORCE</span><span class="sxs-lookup"><span data-stu-id="370ab-126">FLUSH_FORCE</span></span> 
  
> <span data-ttu-id="370ab-127">应执行刷新操作, 而不考虑性能降低的可能性。</span><span class="sxs-lookup"><span data-stu-id="370ab-127">The flush operation should occur regardless, in spite of the chance of a decrease in performance.</span></span> <span data-ttu-id="370ab-128">在目标为异步传输提供程序时, 必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="370ab-128">This flag must be set when an asynchronous transport provider is targeted.</span></span>
    
<span data-ttu-id="370ab-129">FLUSH_NO_UI</span><span class="sxs-lookup"><span data-stu-id="370ab-129">FLUSH_NO_UI</span></span> 
  
> <span data-ttu-id="370ab-130">status 对象不应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="370ab-130">The status object should not display a progress indicator.</span></span>
    
<span data-ttu-id="370ab-131">FLUSH_UPLOAD</span><span class="sxs-lookup"><span data-stu-id="370ab-131">FLUSH_UPLOAD</span></span> 
  
> <span data-ttu-id="370ab-132">应刷新传出邮件队列。</span><span class="sxs-lookup"><span data-stu-id="370ab-132">The outgoing message queues should be flushed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="370ab-133">返回值</span><span class="sxs-lookup"><span data-stu-id="370ab-133">Return value</span></span>

<span data-ttu-id="370ab-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="370ab-134">S_OK</span></span> 
  
> <span data-ttu-id="370ab-135">刷新操作成功。</span><span class="sxs-lookup"><span data-stu-id="370ab-135">The flush operation was successful.</span></span>
    
<span data-ttu-id="370ab-136">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="370ab-136">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="370ab-137">正在进行另一个操作;应允许完成此操作, 否则应将其停止, 然后才能启动此操作。</span><span class="sxs-lookup"><span data-stu-id="370ab-137">Another operation is in progress; it should be allowed to complete, or it should be stopped, before this operation can be initiated.</span></span>
    
<span data-ttu-id="370ab-138">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="370ab-138">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="370ab-139">status 对象不支持此操作, 正如 status 对象的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中缺少 STATUS_FLUSH_QUEUES 标志所指示的那样。</span><span class="sxs-lookup"><span data-stu-id="370ab-139">The status object does not support this operation, as indicated by the absence of the STATUS_FLUSH_QUEUES flag in the status object's **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="370ab-140">注解</span><span class="sxs-lookup"><span data-stu-id="370ab-140">Remarks</span></span>

<span data-ttu-id="370ab-141">**IMAPIStatus:: FlushQueues**方法请求 MAPI 后台处理程序或传输提供程序立即发送传出队列中的所有邮件或接收传入队列中的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="370ab-141">The **IMAPIStatus::FlushQueues** method requests that the MAPI spooler or a transport provider immediately send all messages in the outgoing queue or receive all messages from the incoming queue.</span></span> <span data-ttu-id="370ab-142">**FlushQueues**仅由 MAPI 后台处理程序状态对象和传输提供程序提供的 status 对象实现。</span><span class="sxs-lookup"><span data-stu-id="370ab-142">**FlushQueues** is implemented only by the MAPI spooler status object and by status objects that transport providers supply.</span></span> 
  
<span data-ttu-id="370ab-143">应为异步请求返回 MAPI_E_BUSY, 以便客户端可以继续工作。</span><span class="sxs-lookup"><span data-stu-id="370ab-143">MAPI_E_BUSY should be returned for asynchronous requests so that clients can continue work.</span></span> 
  
<span data-ttu-id="370ab-144">默认情况下, **FlushQueues**是同步操作;在刷新完成之前, 控件不会返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="370ab-144">By default, **FlushQueues** is a synchronous operation; control does not return to the caller until the flush has completed.</span></span> <span data-ttu-id="370ab-145">只有 MAPI 后台处理程序执行的刷新操作才可以是异步操作。客户端通过设置 FLUSH_ASYNC_OK 标志来请求此行为。</span><span class="sxs-lookup"><span data-stu-id="370ab-145">Only the flush operation performed by the MAPI spooler can be asynchronous; clients request this behavior by setting the FLUSH_ASYNC_OK flag.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="370ab-146">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="370ab-146">Notes to implementers</span></span>

<span data-ttu-id="370ab-147">远程传输提供程序的**FlushQueues**实现在登录对象的状态行中的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置 bits, 以控制队列的刷新方式。</span><span class="sxs-lookup"><span data-stu-id="370ab-147">A remote transport provider's implementation of **FlushQueues** sets bits in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property in the logon object's status row to control how queues are flushed.</span></span> <span data-ttu-id="370ab-148">如果远程查看器通过 FLUSH_UPLOAD 标志, 则**FlushQueues**方法应设置 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="370ab-148">If a remote viewer passes in the FLUSH_UPLOAD flag, the **FlushQueues** method should set the STATUS_INBOUND_ENABLED and STATUS_INBOUND_ACTIVE bits.</span></span> <span data-ttu-id="370ab-149">如果远程查看器通过 FLUSH_DOWNLOAD 标志, 则**FlushQueues**方法应设置 STATUS_OUTBOUND_ENABLED 和 STATUS_OUTBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="370ab-149">If a remote viewer passes in the FLUSH_DOWNLOAD flag, the **FlushQueues** method should set the STATUS_OUTBOUND_ENABLED and STATUS_OUTBOUND_ACTIVE bits.</span></span> <span data-ttu-id="370ab-150">**FlushQueues**应返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="370ab-150">**FlushQueues** should then return S_OK.</span></span> <span data-ttu-id="370ab-151">然后, MAPI 后台处理程序将启动相应的操作来上载和下载邮件。</span><span class="sxs-lookup"><span data-stu-id="370ab-151">The MAPI spooler will then initiate the appropriate actions to upload and download messages.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="370ab-152">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="370ab-152">Notes to callers</span></span>

<span data-ttu-id="370ab-153">对 MAPI 后台处理程序状态对象的调用是一种将所有邮件传输到相应的传输提供程序或从相应的传输提供程序传输的指令。</span><span class="sxs-lookup"><span data-stu-id="370ab-153">A call to the MAPI spooler status object is a directive to transfer all messages either to or from the appropriate transport provider.</span></span> <span data-ttu-id="370ab-154">当您调用单个传输提供程序的状态对象时, 只有该提供程序的消息会受到影响。</span><span class="sxs-lookup"><span data-stu-id="370ab-154">When you call an individual transport provider's status object, only the messages for that provider are affected.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="370ab-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="370ab-155">See also</span></span>



[<span data-ttu-id="370ab-156">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="370ab-156">PidTagResourceMethods Canonical Property</span></span>](pidtagresourcemethods-canonical-property.md)
  
[<span data-ttu-id="370ab-157">PidTagStatusCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="370ab-157">PidTagStatusCode Canonical Property</span></span>](pidtagstatuscode-canonical-property.md)
  
[<span data-ttu-id="370ab-158">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="370ab-158">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)

