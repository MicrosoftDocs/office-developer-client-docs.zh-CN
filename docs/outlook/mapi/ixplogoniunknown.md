---
title: IXPLogon IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon
api_type:
- COM
ms.assetid: 4d24ecaf-11d0-4362-8207-be3407736d7b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ecfbf33641c86d4f162c521466ca2bf0b79a61d5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581403"
---
# <a name="ixplogon--iunknown"></a><span data-ttu-id="bcba9-103">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bcba9-103">IXPLogon : IUnknown</span></span>

  
  
<span data-ttu-id="bcba9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcba9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bcba9-105">MAPI 后台处理程序访问提供传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="bcba9-105">Gives the MAPI spooler access to a transport provider.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bcba9-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="bcba9-106">Header file:</span></span>  <br/> |<span data-ttu-id="bcba9-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="bcba9-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="bcba9-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="bcba9-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="bcba9-109">传输登录对象</span><span class="sxs-lookup"><span data-stu-id="bcba9-109">Transport logon objects</span></span>  <br/> |
|<span data-ttu-id="bcba9-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="bcba9-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="bcba9-111">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="bcba9-111">Transport providers</span></span>  <br/> |
|<span data-ttu-id="bcba9-112">调用：</span><span class="sxs-lookup"><span data-stu-id="bcba9-112">Called by:</span></span>  <br/> |<span data-ttu-id="bcba9-113">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="bcba9-113">The MAPI spooler</span></span>  <br/> |
|<span data-ttu-id="bcba9-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="bcba9-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="bcba9-115">IID_IXPLogon</span><span class="sxs-lookup"><span data-stu-id="bcba9-115">IID_IXPLogon</span></span>  <br/> |
|<span data-ttu-id="bcba9-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="bcba9-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="bcba9-117">LXPLOGON</span><span class="sxs-lookup"><span data-stu-id="bcba9-117">LXPLOGON</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="bcba9-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="bcba9-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="bcba9-119">AddressTypes</span><span class="sxs-lookup"><span data-stu-id="bcba9-119">AddressTypes</span></span>](ixplogon-addresstypes.md) <br/> |<span data-ttu-id="bcba9-120">返回的收件人的传输提供程序处理的类型。</span><span class="sxs-lookup"><span data-stu-id="bcba9-120">Returns the types of recipients that the transport provider handles.</span></span>  <br/> |
|<span data-ttu-id="bcba9-121">**RegisterOptions**</span><span class="sxs-lookup"><span data-stu-id="bcba9-121">**RegisterOptions**</span></span> <br/> | <span data-ttu-id="bcba9-122">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="bcba9-122">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="bcba9-123">TransportNotify</span><span class="sxs-lookup"><span data-stu-id="bcba9-123">TransportNotify</span></span>](ixplogon-transportnotify.md) <br/> |<span data-ttu-id="bcba9-124">信号传输提供程序有关哪些请求发送通知的事件的匹配项。</span><span class="sxs-lookup"><span data-stu-id="bcba9-124">Signals the occurrence of an event about which the transport provider requested notification.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-125">空闲时间</span><span class="sxs-lookup"><span data-stu-id="bcba9-125">Idle</span></span>](ixplogon-idle.md) <br/> |<span data-ttu-id="bcba9-126">指示系统空闲，启用传输提供程序执行低优先级操作。</span><span class="sxs-lookup"><span data-stu-id="bcba9-126">Indicates that the system is idle, enabling the transport provider to perform low-priority operations.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-127">TransportLogoff</span><span class="sxs-lookup"><span data-stu-id="bcba9-127">TransportLogoff</span></span>](ixplogon-transportlogoff.md) <br/> |<span data-ttu-id="bcba9-128">启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="bcba9-128">Initiates the logoff process.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-129">SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="bcba9-129">SubmitMessage</span></span>](ixplogon-submitmessage.md) <br/> |<span data-ttu-id="bcba9-130">指示 MAPI 后台处理程序都有要提供的传输提供程序的消息。</span><span class="sxs-lookup"><span data-stu-id="bcba9-130">Indicates that the MAPI spooler has a message for the transport provider to deliver.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-131">EndMessage</span><span class="sxs-lookup"><span data-stu-id="bcba9-131">EndMessage</span></span>](ixplogon-endmessage.md) <br/> |<span data-ttu-id="bcba9-132">通知传输提供程序 MAPI 后台处理程序完成对出站邮件及其处理。</span><span class="sxs-lookup"><span data-stu-id="bcba9-132">Informs the transport provider that the MAPI spooler completed its processing on an outbound message.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-133">投票</span><span class="sxs-lookup"><span data-stu-id="bcba9-133">Poll</span></span>](ixplogon-poll.md) <br/> |<span data-ttu-id="bcba9-134">指示的传输提供程序是否已接收到一个或多个入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="bcba9-134">Indicates whether the transport provider has received one or more inbound messages.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-135">StartMessage</span><span class="sxs-lookup"><span data-stu-id="bcba9-135">StartMessage</span></span>](ixplogon-startmessage.md) <br/> |<span data-ttu-id="bcba9-136">启动入站邮件传输提供程序传输到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="bcba9-136">Initiates the transfer of an inbound message from the transport provider to the MAPI spooler.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-137">OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="bcba9-137">OpenStatusEntry</span></span>](ixplogon-openstatusentry.md) <br/> |<span data-ttu-id="bcba9-138">打开传输提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="bcba9-138">Opens the transport provider's status object.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-139">ValidateState</span><span class="sxs-lookup"><span data-stu-id="bcba9-139">ValidateState</span></span>](ixplogon-validatestate.md) <br/> |<span data-ttu-id="bcba9-140">检查传输提供程序的外部状态。</span><span class="sxs-lookup"><span data-stu-id="bcba9-140">Checks the transport provider's external status.</span></span>  <br/> |
|[<span data-ttu-id="bcba9-141">FlushQueues</span><span class="sxs-lookup"><span data-stu-id="bcba9-141">FlushQueues</span></span>](ixplogon-flushqueues.md) <br/> |<span data-ttu-id="bcba9-142">传输提供程序立即提供所有挂起的入站或出站消息的请求。</span><span class="sxs-lookup"><span data-stu-id="bcba9-142">Requests that the transport provider immediately deliver all pending inbound or outbound messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bcba9-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcba9-143">See also</span></span>



[<span data-ttu-id="bcba9-144">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="bcba9-144">MAPI Interfaces</span></span>](mapi-interfaces.md)
