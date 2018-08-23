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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 961ac2d26cd58e625c35d00bd1216cdee2ce57a0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584728"
---
# <a name="ixplogonflushqueues"></a><span data-ttu-id="db76a-103">IXPLogon::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="db76a-103">IXPLogon::FlushQueues</span></span>

  
  
<span data-ttu-id="db76a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="db76a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="db76a-105">传输提供程序立即提供所有挂起的入站或出站消息的请求。</span><span class="sxs-lookup"><span data-stu-id="db76a-105">Requests that the transport provider immediately deliver all pending inbound or outbound messages.</span></span>
  
```cpp
HRESULT FlushQueues(
  ULONG_PTR ulUIParam,
  ULONG cbTargetTransport,
  LPENTRYID lpTargetTransport,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="db76a-106">参数</span><span class="sxs-lookup"><span data-stu-id="db76a-106">Parameters</span></span>

 <span data-ttu-id="db76a-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="db76a-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="db76a-108">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="db76a-108">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="db76a-109">_cbTargetTransport_</span><span class="sxs-lookup"><span data-stu-id="db76a-109">_cbTargetTransport_</span></span>
  
> <span data-ttu-id="db76a-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="db76a-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="db76a-111">_lpTargetTransport_</span><span class="sxs-lookup"><span data-stu-id="db76a-111">_lpTargetTransport_</span></span>
  
> <span data-ttu-id="db76a-112">[in]保留;必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="db76a-112">[in] Reserved; must be NULL.</span></span>
    
 <span data-ttu-id="db76a-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="db76a-113">_ulFlags_</span></span>
  
> <span data-ttu-id="db76a-114">[in]位掩码的标志，控制如何完成消息队列刷新。</span><span class="sxs-lookup"><span data-stu-id="db76a-114">[in] A bitmask of flags that controls how message queue flushing is accomplished.</span></span> <span data-ttu-id="db76a-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="db76a-115">The following flags can be set:</span></span>
    
<span data-ttu-id="db76a-116">FLUSH_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="db76a-116">FLUSH_DOWNLOAD</span></span> 
  
> <span data-ttu-id="db76a-117">应刷新的入站的消息队列。</span><span class="sxs-lookup"><span data-stu-id="db76a-117">The inbound message queue or queues should be flushed.</span></span>
    
<span data-ttu-id="db76a-118">FLUSH_FORCE</span><span class="sxs-lookup"><span data-stu-id="db76a-118">FLUSH_FORCE</span></span> 
  
> <span data-ttu-id="db76a-119">传输提供程序应处理此请求中，如果可能，即使这样做，以便为较长时间。</span><span class="sxs-lookup"><span data-stu-id="db76a-119">The transport provider should process this request, if possible, even if doing so is time consuming.</span></span> 
    
<span data-ttu-id="db76a-120">FLUSH_NO_UI</span><span class="sxs-lookup"><span data-stu-id="db76a-120">FLUSH_NO_UI</span></span> 
  
> <span data-ttu-id="db76a-121">传输提供程序不应显示的用户界面。</span><span class="sxs-lookup"><span data-stu-id="db76a-121">The transport provider should not display a user interface.</span></span>
    
<span data-ttu-id="db76a-122">FLUSH_UPLOAD</span><span class="sxs-lookup"><span data-stu-id="db76a-122">FLUSH_UPLOAD</span></span> 
  
> <span data-ttu-id="db76a-123">应刷新的出站消息队列。</span><span class="sxs-lookup"><span data-stu-id="db76a-123">The outbound message queue or queues should be flushed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="db76a-124">返回值</span><span class="sxs-lookup"><span data-stu-id="db76a-124">Return value</span></span>

<span data-ttu-id="db76a-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="db76a-125">S_OK</span></span> 
  
> <span data-ttu-id="db76a-126">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="db76a-126">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="db76a-127">注解</span><span class="sxs-lookup"><span data-stu-id="db76a-127">Remarks</span></span>

<span data-ttu-id="db76a-128">MAPI 后台处理程序调用**IXPLogon::FlushQueues**方法以指出 MAPI 后台处理程序即将开始处理邮件的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="db76a-128">The MAPI spooler calls the **IXPLogon::FlushQueues** method to advise the transport provider that the MAPI spooler is about to begin processing messages.</span></span> <span data-ttu-id="db76a-129">传输提供程序应调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法，以便其状态的行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置其状态的适当的位。</span><span class="sxs-lookup"><span data-stu-id="db76a-129">The transport provider should call the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method to set an appropriate bit for its state in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property of its status row.</span></span> <span data-ttu-id="db76a-130">更新其状态的行之后, 传输提供程序应**FlushQueues**呼叫返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="db76a-130">After updating its status row, the transport provider should return S_OK for the **FlushQueues** call.</span></span> <span data-ttu-id="db76a-131">MAPI 后台处理程序然后启动发送消息，与正在同步到 MAPI 后台处理程序的操作。</span><span class="sxs-lookup"><span data-stu-id="db76a-131">The MAPI spooler then starts sending messages, with the operation being synchronous to the MAPI spooler.</span></span> 
  
<span data-ttu-id="db76a-132">若要支持其[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法的实现，MAPI 后台处理程序调用**IXPLogon::FlushQueues**所有登录对象的为配置文件会话中运行的活动传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="db76a-132">To support its implementation of the [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method, the MAPI spooler calls **IXPLogon::FlushQueues** for all logon objects for active transport providers that are running in a profile session.</span></span> <span data-ttu-id="db76a-133">由于客户端应用程序调用**IMAPIStatus::FlushQueues**调用传输提供程序的**FlushQueues**方法时，消息处理发生异步到客户端。</span><span class="sxs-lookup"><span data-stu-id="db76a-133">When a transport provider's **FlushQueues** method is called as a result of a client application call to **IMAPIStatus::FlushQueues**, the message processing occurs asynchronously to the client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db76a-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db76a-134">See also</span></span>



[<span data-ttu-id="db76a-135">IMAPIStatus::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="db76a-135">IMAPIStatus::FlushQueues</span></span>](imapistatus-flushqueues.md)
  
[<span data-ttu-id="db76a-136">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="db76a-136">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

