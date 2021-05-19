---
title: MAPI 后台处理程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5866b202-883e-454e-aeb1-61526c43dae9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 162957ea17b5a82d4da68340e971d328c85cd9f7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432714"
---
# <a name="mapi-spooler-overview"></a><span data-ttu-id="fef98-103">MAPI 后台处理程序概述</span><span class="sxs-lookup"><span data-stu-id="fef98-103">MAPI spooler overview</span></span>
  
<span data-ttu-id="fef98-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fef98-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fef98-105">MAPI 后台处理程序是邮件Microsoft Office Outlook的一个功能，该过程负责向邮件系统发送邮件和从邮件系统接收邮件。</span><span class="sxs-lookup"><span data-stu-id="fef98-105">MAPI spooler is a function of the Microsoft Office Outlook process that is responsible for sending messages to and receiving messages from a messaging system.</span></span> <span data-ttu-id="fef98-106">MAPI 后台处理程序在邮件接收和传递中起到重要作用。</span><span class="sxs-lookup"><span data-stu-id="fef98-106">MAPI spooler plays a vital role in message receipt and delivery.</span></span> <span data-ttu-id="fef98-107">当邮件系统不可用时，MAPI 后台处理程序将存储邮件，并稍后自动转发这些邮件。</span><span class="sxs-lookup"><span data-stu-id="fef98-107">When a messaging system is unavailable, MAPI spooler stores the messages and automatically forwards them at a later time.</span></span> <span data-ttu-id="fef98-108">这种在必要时保留或发送数据的功能称为存储和转发，这是远程连接很常见且网络流量高的环境中的一项关键功能。</span><span class="sxs-lookup"><span data-stu-id="fef98-108">This ability to hold on to or send data when necessary is known as store and forward, a critical feature in environments where remote connections are common and network traffic is high.</span></span> <span data-ttu-id="fef98-109">MAPI 后台处理程序作为后台线程在 Outlook。</span><span class="sxs-lookup"><span data-stu-id="fef98-109">MAPI spooler runs as a background thread within Outlook.</span></span>
  
<span data-ttu-id="fef98-110">MAPI 后台处理程序具有与邮件分发相关的其他责任。</span><span class="sxs-lookup"><span data-stu-id="fef98-110">MAPI spooler has additional responsibilities related to message distribution.</span></span> <span data-ttu-id="fef98-111">这些额外职责包括：</span><span class="sxs-lookup"><span data-stu-id="fef98-111">These extra duties include the following:</span></span>
  
- <span data-ttu-id="fef98-112">跟踪由特定传输提供程序处理的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="fef98-112">Keeping track of the recipient types that are handled by specific transport providers.</span></span>
    
- <span data-ttu-id="fef98-113">在传递新邮件时通知客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="fef98-113">Informing a client application when a new message has been delivered.</span></span>
    
- <span data-ttu-id="fef98-114">调用邮件预处理和后处理。</span><span class="sxs-lookup"><span data-stu-id="fef98-114">Invoking message preprocessing and postprocessing.</span></span>
    
- <span data-ttu-id="fef98-115">生成指示已发生邮件传递的报告。</span><span class="sxs-lookup"><span data-stu-id="fef98-115">Generating reports that indicate that message delivery has occurred.</span></span>
    
- <span data-ttu-id="fef98-116">维护已处理收件人的状态。</span><span class="sxs-lookup"><span data-stu-id="fef98-116">Maintaining status on processed recipients.</span></span>
    
<span data-ttu-id="fef98-117">下图在高级别显示了邮件如何从客户端流动到邮件系统。</span><span class="sxs-lookup"><span data-stu-id="fef98-117">The following illustration shows at a high level how a message flows from a client to the messaging system.</span></span>
  
<span data-ttu-id="fef98-118">**传出消息流**</span><span class="sxs-lookup"><span data-stu-id="fef98-118">**Outgoing message flow**</span></span>
  
<span data-ttu-id="fef98-119">![传出邮件流](media/amapi_46.gif "传出邮件流")</span><span class="sxs-lookup"><span data-stu-id="fef98-119">![Outgoing message flow](media/amapi_46.gif "Outgoing message flow")</span></span>
  
<span data-ttu-id="fef98-120">客户端应用程序的用户向一个或多个收件人发送邮件。</span><span class="sxs-lookup"><span data-stu-id="fef98-120">The user of a client application sends a message to one or more recipients.</span></span> <span data-ttu-id="fef98-121">邮件存储提供程序启动发送过程，使用传输所需的其他信息设置邮件的格式。</span><span class="sxs-lookup"><span data-stu-id="fef98-121">The message store provider initiates the sending process, formatting the message with additional information needed for transmission.</span></span>
  
<span data-ttu-id="fef98-122">如果发生以下任一情况，MAPI 后台处理程序将接收要处理的消息：</span><span class="sxs-lookup"><span data-stu-id="fef98-122">MAPI spooler receives the message to process if any of the following conditions occur:</span></span>
  
- <span data-ttu-id="fef98-123">邮件存储提供程序不会与传输提供程序紧密结合。</span><span class="sxs-lookup"><span data-stu-id="fef98-123">The message store provider is not tightly coupled with a transport provider.</span></span>
    
- <span data-ttu-id="fef98-124">邮件需要预处理。</span><span class="sxs-lookup"><span data-stu-id="fef98-124">The message requires preprocessing.</span></span>
    
- <span data-ttu-id="fef98-125">邮件存储和传输提供程序是紧密耦合的，但它们无法处理邮件发送到的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="fef98-125">The message store and transport provider are tightly coupled, but they cannot handle all the recipients to whom the message is addressed.</span></span>
    
<span data-ttu-id="fef98-126">如果 MAPI 后台处理程序收到邮件，它将执行任何所需的预处理，将邮件传递至相应的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fef98-126">If MAPI spooler receives the message, it performs any required preprocessing and delivers the message to the appropriate transport provider.</span></span> <span data-ttu-id="fef98-127">传输提供程序将邮件发送到其邮件系统，邮件系统会将其发送给预期收件人。</span><span class="sxs-lookup"><span data-stu-id="fef98-127">The transport provider gives the message to its messaging system, which sends it to its intended recipient.</span></span>
  
<span data-ttu-id="fef98-128">对于传入的邮件，流将反转。</span><span class="sxs-lookup"><span data-stu-id="fef98-128">With incoming messages, the flow is reversed.</span></span> <span data-ttu-id="fef98-129">传输提供程序接收来自其邮件系统的邮件，并通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="fef98-129">The transport provider receives a message from its messaging system and notifies MAPI spooler.</span></span> <span data-ttu-id="fef98-130">后台处理程序执行任何必要的后处理，并通知邮件存储提供程序新邮件已到达。</span><span class="sxs-lookup"><span data-stu-id="fef98-130">Spooler performs any necessary postprocessing and informs the message store provider that a new message has arrived.</span></span> <span data-ttu-id="fef98-131">此通知使客户端刷新其消息显示，使用户可以阅读新邮件。</span><span class="sxs-lookup"><span data-stu-id="fef98-131">This notification causes the client to refresh its message display, enabling the user to read the new message.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fef98-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fef98-132">See also</span></span>

- [<span data-ttu-id="fef98-133">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="fef98-133">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

