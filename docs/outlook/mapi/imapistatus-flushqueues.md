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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d6c221ae307edb9d84cfcc0026660ea4bce7fadd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775582"
---
# <a name="imapistatusflushqueues"></a><span data-ttu-id="057ba-103">IMAPIStatus::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="057ba-103">IMAPIStatus::FlushQueues</span></span>

  
  
<span data-ttu-id="057ba-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="057ba-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="057ba-105">强制等待发送或接收立即上载或下载的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="057ba-105">Forces all messages waiting to be sent or received to be immediately uploaded or downloaded.</span></span> <span data-ttu-id="057ba-106">MAPI 后台处理程序状态对象和传输提供程序实现的状态对象支持此方法。</span><span class="sxs-lookup"><span data-stu-id="057ba-106">The MAPI spooler status object and status objects that transport providers implement support this method.</span></span>
  
```cpp
HRESULT FlushQueues(
  ULONG_PTR ulUIParam,
  ULONG cbTargetTransport,
  LPENTRYID lpTargetTransport,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="057ba-107">参数</span><span class="sxs-lookup"><span data-stu-id="057ba-107">Parameters</span></span>

 <span data-ttu-id="057ba-108">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="057ba-108">_ulUIParam_</span></span>
  
> <span data-ttu-id="057ba-109">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="057ba-109">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="057ba-110">_cbTargetTransport_</span><span class="sxs-lookup"><span data-stu-id="057ba-110">_cbTargetTransport_</span></span>
  
> <span data-ttu-id="057ba-111">[in]在_lpTargetTransport_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="057ba-111">[in] The byte count in the entry identifier pointed to by the  _lpTargetTransport_ parameter.</span></span> <span data-ttu-id="057ba-112">_CbTargetTransport_参数仅在调用 MAPI 后台处理程序的状态对象上设置。</span><span class="sxs-lookup"><span data-stu-id="057ba-112">The  _cbTargetTransport_ parameter is set only on calls to the MAPI spooler's status object.</span></span> <span data-ttu-id="057ba-113">对于到传输提供程序的调用， _cbTargetTransport_参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="057ba-113">For calls to a transport provider, the  _cbTargetTransport_ parameter is set to 0.</span></span> 
    
 <span data-ttu-id="057ba-114">_lpTargetTransport_</span><span class="sxs-lookup"><span data-stu-id="057ba-114">_lpTargetTransport_</span></span>
  
> <span data-ttu-id="057ba-115">[in]指向的传输提供程序刷新其消息队列的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="057ba-115">[in] A pointer to the entry identifier of the transport provider that is to flush its message queues.</span></span> <span data-ttu-id="057ba-116">_LpTargetTransport_参数仅在调用 MAPI 后台处理程序的状态对象上设置。</span><span class="sxs-lookup"><span data-stu-id="057ba-116">The  _lpTargetTransport_ parameter is set only on calls to the MAPI spooler's status object.</span></span> <span data-ttu-id="057ba-117">对于到传输提供程序的调用， _lpTargetTransport_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="057ba-117">For calls to a transport provider, the  _lpTargetTransport_ parameter is set to NULL.</span></span> 
    
 <span data-ttu-id="057ba-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="057ba-118">_ulFlags_</span></span>
  
> <span data-ttu-id="057ba-119">[in]位掩码的标志的控件的刷新操作。</span><span class="sxs-lookup"><span data-stu-id="057ba-119">[in] A bitmask of flags that controls the flush operation.</span></span> <span data-ttu-id="057ba-120">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="057ba-120">The following flags can be set:</span></span>
    
<span data-ttu-id="057ba-121">FLUSH_ASYNC_OK</span><span class="sxs-lookup"><span data-stu-id="057ba-121">FLUSH_ASYNC_OK</span></span> 
  
> <span data-ttu-id="057ba-122">异步出现的刷新操作。</span><span class="sxs-lookup"><span data-stu-id="057ba-122">The flush operation can occur asynchronously.</span></span> <span data-ttu-id="057ba-123">此标志仅适用于 MAPI 后台处理程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="057ba-123">This flag applies only to the MAPI spooler's status object.</span></span> 
    
<span data-ttu-id="057ba-124">FLUSH_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="057ba-124">FLUSH_DOWNLOAD</span></span> 
  
> <span data-ttu-id="057ba-125">应刷新传入的消息队列。</span><span class="sxs-lookup"><span data-stu-id="057ba-125">The incoming message queues should be flushed.</span></span>
    
<span data-ttu-id="057ba-126">FLUSH_FORCE</span><span class="sxs-lookup"><span data-stu-id="057ba-126">FLUSH_FORCE</span></span> 
  
> <span data-ttu-id="057ba-127">刷新操作应无论如何，而不考虑的性能降低进行。</span><span class="sxs-lookup"><span data-stu-id="057ba-127">The flush operation should occur regardless, in spite of the chance of a decrease in performance.</span></span> <span data-ttu-id="057ba-128">目标异步传输提供程序时，必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="057ba-128">This flag must be set when an asynchronous transport provider is targeted.</span></span>
    
<span data-ttu-id="057ba-129">FLUSH_NO_UI</span><span class="sxs-lookup"><span data-stu-id="057ba-129">FLUSH_NO_UI</span></span> 
  
> <span data-ttu-id="057ba-130">状态对象不应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="057ba-130">The status object should not display a progress indicator.</span></span>
    
<span data-ttu-id="057ba-131">FLUSH_UPLOAD</span><span class="sxs-lookup"><span data-stu-id="057ba-131">FLUSH_UPLOAD</span></span> 
  
> <span data-ttu-id="057ba-132">应刷新的传出消息队列。</span><span class="sxs-lookup"><span data-stu-id="057ba-132">The outgoing message queues should be flushed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="057ba-133">返回值</span><span class="sxs-lookup"><span data-stu-id="057ba-133">Return value</span></span>

<span data-ttu-id="057ba-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="057ba-134">S_OK</span></span> 
  
> <span data-ttu-id="057ba-135">刷新操作已成功。</span><span class="sxs-lookup"><span data-stu-id="057ba-135">The flush operation was successful.</span></span>
    
<span data-ttu-id="057ba-136">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="057ba-136">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="057ba-137">正在进行; 另一个操作应允许其完成，或者它应停止，可以启动此操作之前。</span><span class="sxs-lookup"><span data-stu-id="057ba-137">Another operation is in progress; it should be allowed to complete, or it should be stopped, before this operation can be initiated.</span></span>
    
<span data-ttu-id="057ba-138">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="057ba-138">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="057ba-139">状态对象不支持此操作，如缺少 STATUS_FLUSH_QUEUES 标志状态对象的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中所示。</span><span class="sxs-lookup"><span data-stu-id="057ba-139">The status object does not support this operation, as indicated by the absence of the STATUS_FLUSH_QUEUES flag in the status object's **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="057ba-140">说明</span><span class="sxs-lookup"><span data-stu-id="057ba-140">Remarks</span></span>

<span data-ttu-id="057ba-141">**IMAPIStatus::FlushQueues**方法请求的 MAPI 后台处理程序传输提供程序立即发送传出队列中的所有邮件或从传入的队列接收所有的消息。</span><span class="sxs-lookup"><span data-stu-id="057ba-141">The **IMAPIStatus::FlushQueues** method requests that the MAPI spooler or a transport provider immediately send all messages in the outgoing queue or receive all messages from the incoming queue.</span></span> <span data-ttu-id="057ba-142">**FlushQueues**是只能通过 MAPI 后台处理程序状态对象和由传输提供程序提供的状态对象实现的。</span><span class="sxs-lookup"><span data-stu-id="057ba-142">**FlushQueues** is implemented only by the MAPI spooler status object and by status objects that transport providers supply.</span></span> 
  
<span data-ttu-id="057ba-143">应异步请求返回 MAPI_E_BUSY，以便客户端可以继续工作。</span><span class="sxs-lookup"><span data-stu-id="057ba-143">MAPI_E_BUSY should be returned for asynchronous requests so that clients can continue work.</span></span> 
  
<span data-ttu-id="057ba-144">默认情况下**FlushQueues**是同步操作;刷新已完成，直到控件不返回到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="057ba-144">By default, **FlushQueues** is a synchronous operation; control does not return to the caller until the flush has completed.</span></span> <span data-ttu-id="057ba-145">仅由 MAPI 后台处理程序执行的刷新操作可以是异步的;客户端通过设置 FLUSH_ASYNC_OK 标志请求此行为。</span><span class="sxs-lookup"><span data-stu-id="057ba-145">Only the flush operation performed by the MAPI spooler can be asynchronous; clients request this behavior by setting the FLUSH_ASYNC_OK flag.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="057ba-146">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="057ba-146">Notes to implementers</span></span>

<span data-ttu-id="057ba-147">远程传输提供程序的实现**FlushQueues**登录对象的状态行来控制如何刷新队列中的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置了位。</span><span class="sxs-lookup"><span data-stu-id="057ba-147">A remote transport provider's implementation of **FlushQueues** sets bits in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property in the logon object's status row to control how queues are flushed.</span></span> <span data-ttu-id="057ba-148">如果远程查看器传入 FLUSH_UPLOAD 标志， **FlushQueues**方法应设置 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="057ba-148">If a remote viewer passes in the FLUSH_UPLOAD flag, the **FlushQueues** method should set the STATUS_INBOUND_ENABLED and STATUS_INBOUND_ACTIVE bits.</span></span> <span data-ttu-id="057ba-149">如果远程查看器传入 FLUSH_DOWNLOAD 标志， **FlushQueues**方法应设置 STATUS_OUTBOUND_ENABLED 和 STATUS_OUTBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="057ba-149">If a remote viewer passes in the FLUSH_DOWNLOAD flag, the **FlushQueues** method should set the STATUS_OUTBOUND_ENABLED and STATUS_OUTBOUND_ACTIVE bits.</span></span> <span data-ttu-id="057ba-150">**FlushQueues**然后应返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="057ba-150">**FlushQueues** should then return S_OK.</span></span> <span data-ttu-id="057ba-151">然后，MAPI 后台处理程序将启动上载和下载邮件的相应操作。</span><span class="sxs-lookup"><span data-stu-id="057ba-151">The MAPI spooler will then initiate the appropriate actions to upload and download messages.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="057ba-152">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="057ba-152">Notes to callers</span></span>

<span data-ttu-id="057ba-153">MAPI 后台处理程序状态对象调用是指令传输到或从适当的传输提供程序的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="057ba-153">A call to the MAPI spooler status object is a directive to transfer all messages either to or from the appropriate transport provider.</span></span> <span data-ttu-id="057ba-154">在调用的单个传输提供程序的状态对象时，会影响只有该提供程序的邮件。</span><span class="sxs-lookup"><span data-stu-id="057ba-154">When you call an individual transport provider's status object, only the messages for that provider are affected.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="057ba-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="057ba-155">See also</span></span>



[<span data-ttu-id="057ba-156">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="057ba-156">PidTagResourceMethods Canonical Property</span></span>](pidtagresourcemethods-canonical-property.md)
  
[<span data-ttu-id="057ba-157">PidTagStatusCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="057ba-157">PidTagStatusCode Canonical Property</span></span>](pidtagstatuscode-canonical-property.md)
  
[<span data-ttu-id="057ba-158">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="057ba-158">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)

