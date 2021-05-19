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
ms.openlocfilehash: 46f4e3fc8f554f332ab9b1d8a6cb33e9e21dd9a5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432532"
---
# <a name="ixplogon--iunknown"></a><span data-ttu-id="9b673-103">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9b673-103">IXPLogon : IUnknown</span></span>

  
  
<span data-ttu-id="9b673-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b673-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9b673-105">向 MAPI 后台处理程序授予对传输提供程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9b673-105">Gives the MAPI spooler access to a transport provider.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9b673-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="9b673-106">Header file:</span></span>  <br/> |<span data-ttu-id="9b673-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="9b673-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="9b673-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="9b673-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="9b673-109">传输登录对象</span><span class="sxs-lookup"><span data-stu-id="9b673-109">Transport logon objects</span></span>  <br/> |
|<span data-ttu-id="9b673-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="9b673-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="9b673-111">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="9b673-111">Transport providers</span></span>  <br/> |
|<span data-ttu-id="9b673-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="9b673-112">Called by:</span></span>  <br/> |<span data-ttu-id="9b673-113">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="9b673-113">The MAPI spooler</span></span>  <br/> |
|<span data-ttu-id="9b673-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="9b673-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="9b673-115">IID_IXPLogon</span><span class="sxs-lookup"><span data-stu-id="9b673-115">IID_IXPLogon</span></span>  <br/> |
|<span data-ttu-id="9b673-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="9b673-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="9b673-117">LXPLOGON</span><span class="sxs-lookup"><span data-stu-id="9b673-117">LXPLOGON</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="9b673-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="9b673-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="9b673-119">AddressTypes</span><span class="sxs-lookup"><span data-stu-id="9b673-119">AddressTypes</span></span>](ixplogon-addresstypes.md) <br/> |<span data-ttu-id="9b673-120">返回传输提供程序处理的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="9b673-120">Returns the types of recipients that the transport provider handles.</span></span>  <br/> |
|<span data-ttu-id="9b673-121">**RegisterOptions**</span><span class="sxs-lookup"><span data-stu-id="9b673-121">**RegisterOptions**</span></span> <br/> | <span data-ttu-id="9b673-122">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="9b673-122">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="9b673-123">TransportNotify</span><span class="sxs-lookup"><span data-stu-id="9b673-123">TransportNotify</span></span>](ixplogon-transportnotify.md) <br/> |<span data-ttu-id="9b673-124">指示出现传输提供程序请求通知的事件。</span><span class="sxs-lookup"><span data-stu-id="9b673-124">Signals the occurrence of an event about which the transport provider requested notification.</span></span>  <br/> |
|[<span data-ttu-id="9b673-125">空闲</span><span class="sxs-lookup"><span data-stu-id="9b673-125">Idle</span></span>](ixplogon-idle.md) <br/> |<span data-ttu-id="9b673-126">指示系统处于空闲状态，使传输提供程序能够执行低优先级操作。</span><span class="sxs-lookup"><span data-stu-id="9b673-126">Indicates that the system is idle, enabling the transport provider to perform low-priority operations.</span></span>  <br/> |
|[<span data-ttu-id="9b673-127">TransportLogoff</span><span class="sxs-lookup"><span data-stu-id="9b673-127">TransportLogoff</span></span>](ixplogon-transportlogoff.md) <br/> |<span data-ttu-id="9b673-128">启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="9b673-128">Initiates the logoff process.</span></span>  <br/> |
|[<span data-ttu-id="9b673-129">SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="9b673-129">SubmitMessage</span></span>](ixplogon-submitmessage.md) <br/> |<span data-ttu-id="9b673-130">指示 MAPI 后台处理程序具有要传递的传输提供程序的邮件。</span><span class="sxs-lookup"><span data-stu-id="9b673-130">Indicates that the MAPI spooler has a message for the transport provider to deliver.</span></span>  <br/> |
|[<span data-ttu-id="9b673-131">EndMessage</span><span class="sxs-lookup"><span data-stu-id="9b673-131">EndMessage</span></span>](ixplogon-endmessage.md) <br/> |<span data-ttu-id="9b673-132">通知传输提供程序 MAPI 后台处理程序已完成对出站邮件的处理。</span><span class="sxs-lookup"><span data-stu-id="9b673-132">Informs the transport provider that the MAPI spooler completed its processing on an outbound message.</span></span>  <br/> |
|[<span data-ttu-id="9b673-133">投票</span><span class="sxs-lookup"><span data-stu-id="9b673-133">Poll</span></span>](ixplogon-poll.md) <br/> |<span data-ttu-id="9b673-134">指示传输提供程序是否收到一个或多个入站邮件。</span><span class="sxs-lookup"><span data-stu-id="9b673-134">Indicates whether the transport provider has received one or more inbound messages.</span></span>  <br/> |
|[<span data-ttu-id="9b673-135">StartMessage</span><span class="sxs-lookup"><span data-stu-id="9b673-135">StartMessage</span></span>](ixplogon-startmessage.md) <br/> |<span data-ttu-id="9b673-136">启动将入站邮件从传输提供程序转移到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="9b673-136">Initiates the transfer of an inbound message from the transport provider to the MAPI spooler.</span></span>  <br/> |
|[<span data-ttu-id="9b673-137">OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="9b673-137">OpenStatusEntry</span></span>](ixplogon-openstatusentry.md) <br/> |<span data-ttu-id="9b673-138">打开传输提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="9b673-138">Opens the transport provider's status object.</span></span>  <br/> |
|[<span data-ttu-id="9b673-139">ValidateState</span><span class="sxs-lookup"><span data-stu-id="9b673-139">ValidateState</span></span>](ixplogon-validatestate.md) <br/> |<span data-ttu-id="9b673-140">检查传输提供程序的外部状态。</span><span class="sxs-lookup"><span data-stu-id="9b673-140">Checks the transport provider's external status.</span></span>  <br/> |
|[<span data-ttu-id="9b673-141">FlushQueues</span><span class="sxs-lookup"><span data-stu-id="9b673-141">FlushQueues</span></span>](ixplogon-flushqueues.md) <br/> |<span data-ttu-id="9b673-142">请求传输提供程序立即传递所有挂起的入站或出站邮件。</span><span class="sxs-lookup"><span data-stu-id="9b673-142">Requests that the transport provider immediately deliver all pending inbound or outbound messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9b673-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b673-143">See also</span></span>



[<span data-ttu-id="9b673-144">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="9b673-144">MAPI Interfaces</span></span>](mapi-interfaces.md)

