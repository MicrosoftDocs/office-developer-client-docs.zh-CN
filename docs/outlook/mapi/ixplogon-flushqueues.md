---
title: IXPLogonFlushQueues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.FlushQueues
api_type:
- COM
ms.assetid: c1f630c6-9e95-49c0-9757-4685c98184dc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fb26c7f366ce6a262362001773e825c60d0e4ec3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421968"
---
# <a name="ixplogonflushqueues"></a><span data-ttu-id="ec7b5-103">IXPLogon::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="ec7b5-103">IXPLogon::FlushQueues</span></span>

  
  
<span data-ttu-id="ec7b5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec7b5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec7b5-105">请求传输提供程序立即传递所有挂起的入站或出站邮件。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-105">Requests that the transport provider immediately deliver all pending inbound or outbound messages.</span></span>
  
```cpp
HRESULT FlushQueues(
  ULONG_PTR ulUIParam,
  ULONG cbTargetTransport,
  LPENTRYID lpTargetTransport,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="ec7b5-106">参数</span><span class="sxs-lookup"><span data-stu-id="ec7b5-106">Parameters</span></span>

 <span data-ttu-id="ec7b5-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ec7b5-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="ec7b5-108">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-108">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="ec7b5-109">_cbTargetTransport_</span><span class="sxs-lookup"><span data-stu-id="ec7b5-109">_cbTargetTransport_</span></span>
  
> <span data-ttu-id="ec7b5-110">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="ec7b5-111">_lpTargetTransport_</span><span class="sxs-lookup"><span data-stu-id="ec7b5-111">_lpTargetTransport_</span></span>
  
> <span data-ttu-id="ec7b5-112">实时保留必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-112">[in] Reserved; must be NULL.</span></span>
    
 <span data-ttu-id="ec7b5-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ec7b5-113">_ulFlags_</span></span>
  
> <span data-ttu-id="ec7b5-114">实时用于控制如何完成邮件队列刷新的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-114">[in] A bitmask of flags that controls how message queue flushing is accomplished.</span></span> <span data-ttu-id="ec7b5-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ec7b5-115">The following flags can be set:</span></span>
    
<span data-ttu-id="ec7b5-116">FLUSH_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="ec7b5-116">FLUSH_DOWNLOAD</span></span> 
  
> <span data-ttu-id="ec7b5-117">应刷新入站邮件队列或队列。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-117">The inbound message queue or queues should be flushed.</span></span>
    
<span data-ttu-id="ec7b5-118">FLUSH_FORCE</span><span class="sxs-lookup"><span data-stu-id="ec7b5-118">FLUSH_FORCE</span></span> 
  
> <span data-ttu-id="ec7b5-119">如果可能, 传输提供程序应处理此请求 (如果可能), 即使这样做很耗时。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-119">The transport provider should process this request, if possible, even if doing so is time consuming.</span></span> 
    
<span data-ttu-id="ec7b5-120">FLUSH_NO_UI</span><span class="sxs-lookup"><span data-stu-id="ec7b5-120">FLUSH_NO_UI</span></span> 
  
> <span data-ttu-id="ec7b5-121">传输提供程序不应显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-121">The transport provider should not display a user interface.</span></span>
    
<span data-ttu-id="ec7b5-122">FLUSH_UPLOAD</span><span class="sxs-lookup"><span data-stu-id="ec7b5-122">FLUSH_UPLOAD</span></span> 
  
> <span data-ttu-id="ec7b5-123">应刷新出站邮件队列或队列。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-123">The outbound message queue or queues should be flushed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ec7b5-124">返回值</span><span class="sxs-lookup"><span data-stu-id="ec7b5-124">Return value</span></span>

<span data-ttu-id="ec7b5-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec7b5-125">S_OK</span></span> 
  
> <span data-ttu-id="ec7b5-126">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-126">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ec7b5-127">说明</span><span class="sxs-lookup"><span data-stu-id="ec7b5-127">Remarks</span></span>

<span data-ttu-id="ec7b5-128">mapi 后台处理程序调用**IXPLogon:: FlushQueues**方法, 以告知 MAPI 后台处理程序即将开始处理邮件的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-128">The MAPI spooler calls the **IXPLogon::FlushQueues** method to advise the transport provider that the MAPI spooler is about to begin processing messages.</span></span> <span data-ttu-id="ec7b5-129">传输提供程序应调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法, 以在其状态行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中为其状态设置一个适当的位。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-129">The transport provider should call the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method to set an appropriate bit for its state in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property of its status row.</span></span> <span data-ttu-id="ec7b5-130">更新其状态行后, 传输提供程序应返回**FlushQueues**调用的 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-130">After updating its status row, the transport provider should return S_OK for the **FlushQueues** call.</span></span> <span data-ttu-id="ec7b5-131">mapi 后台处理程序随后开始发送邮件, 并将操作同步到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-131">The MAPI spooler then starts sending messages, with the operation being synchronous to the MAPI spooler.</span></span> 
  
<span data-ttu-id="ec7b5-132">若要支持其[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法的实现, MAPI 后台处理程序会调用在配置文件会话中运行的活动传输提供程序的所有登录对象的**IXPLogon:: FlushQueues** 。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-132">To support its implementation of the [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method, the MAPI spooler calls **IXPLogon::FlushQueues** for all logon objects for active transport providers that are running in a profile session.</span></span> <span data-ttu-id="ec7b5-133">当传输提供程序的**FlushQueues**方法作为客户端应用程序调用**IMAPIStatus:: FlushQueues**时调用时, 邮件处理将异步发生到客户端。</span><span class="sxs-lookup"><span data-stu-id="ec7b5-133">When a transport provider's **FlushQueues** method is called as a result of a client application call to **IMAPIStatus::FlushQueues**, the message processing occurs asynchronously to the client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec7b5-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec7b5-134">See also</span></span>



[<span data-ttu-id="ec7b5-135">IMAPIStatus::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="ec7b5-135">IMAPIStatus::FlushQueues</span></span>](imapistatus-flushqueues.md)
  
[<span data-ttu-id="ec7b5-136">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ec7b5-136">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

