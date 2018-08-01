---
title: MAPI 后台处理程序概述 （英文)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5866b202-883e-454e-aeb1-61526c43dae9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5e4bd4f6038db3dbb33ec3511d953448fea7a6c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776337"
---
# <a name="mapi-spooler-overview"></a><span data-ttu-id="435ef-103">MAPI 后台处理程序概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="435ef-103">MAPI spooler overview</span></span>
  
<span data-ttu-id="435ef-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="435ef-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="435ef-105">MAPI 后台处理程序是一个函数，负责向发送消息和接收消息从邮件系统的 Microsoft Office Outlook 进程。</span><span class="sxs-lookup"><span data-stu-id="435ef-105">MAPI spooler is a function of the Microsoft Office Outlook process that is responsible for sending messages to and receiving messages from a messaging system.</span></span> <span data-ttu-id="435ef-106">MAPI 后台处理程序播放消息接收和发送中的一个重要的角色。</span><span class="sxs-lookup"><span data-stu-id="435ef-106">MAPI spooler plays a vital role in message receipt and delivery.</span></span> <span data-ttu-id="435ef-107">当邮件系统不可用时，MAPI 后台处理程序存储消息，并自动将它们转发在以后。</span><span class="sxs-lookup"><span data-stu-id="435ef-107">When a messaging system is unavailable, MAPI spooler stores the messages and automatically forwards them at a later time.</span></span> <span data-ttu-id="435ef-108">保留到或发送数据在必要时，此功能称为存储和转发，其中远程连接共有和网络流量较高的环境中的关键功能。</span><span class="sxs-lookup"><span data-stu-id="435ef-108">This ability to hold on to or send data when necessary is known as store and forward, a critical feature in environments where remote connections are common and network traffic is high.</span></span> <span data-ttu-id="435ef-109">MAPI 后台处理程序作为后台线程在 Outlook 中运行。</span><span class="sxs-lookup"><span data-stu-id="435ef-109">MAPI spooler runs as a background thread within Outlook.</span></span>
  
<span data-ttu-id="435ef-110">MAPI 后台处理程序都有与邮件分布相关的其他责任。</span><span class="sxs-lookup"><span data-stu-id="435ef-110">MAPI spooler has additional responsibilities related to message distribution.</span></span> <span data-ttu-id="435ef-111">以下这些额外的职责：</span><span class="sxs-lookup"><span data-stu-id="435ef-111">These extra duties include the following:</span></span>
  
- <span data-ttu-id="435ef-112">跟踪的由特定传输提供程序处理的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="435ef-112">Keeping track of the recipient types that are handled by specific transport providers.</span></span>
    
- <span data-ttu-id="435ef-113">当新邮件已送达告知客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="435ef-113">Informing a client application when a new message has been delivered.</span></span>
    
- <span data-ttu-id="435ef-114">预处理和后处理调用消息。</span><span class="sxs-lookup"><span data-stu-id="435ef-114">Invoking message preprocessing and postprocessing.</span></span>
    
- <span data-ttu-id="435ef-115">生成报告指示该邮件传递的发生。</span><span class="sxs-lookup"><span data-stu-id="435ef-115">Generating reports that indicate that message delivery has occurred.</span></span>
    
- <span data-ttu-id="435ef-116">维护的处理收件人的状态。</span><span class="sxs-lookup"><span data-stu-id="435ef-116">Maintaining status on processed recipients.</span></span>
    
<span data-ttu-id="435ef-117">下图显示了在高级别邮件流动的方式从客户端消息的系统。</span><span class="sxs-lookup"><span data-stu-id="435ef-117">The following illustration shows at a high level how a message flows from a client to the messaging system.</span></span>
  
<span data-ttu-id="435ef-118">**传出消息流**</span><span class="sxs-lookup"><span data-stu-id="435ef-118">**Outgoing message flow**</span></span>
  
<span data-ttu-id="435ef-119">![传出消息流](media/amapi_46.gif "传出消息流")</span><span class="sxs-lookup"><span data-stu-id="435ef-119">![Outgoing message flow](media/amapi_46.gif "Outgoing message flow")</span></span>
  
<span data-ttu-id="435ef-120">客户端应用程序的用户向一个或多个收件人发送邮件。</span><span class="sxs-lookup"><span data-stu-id="435ef-120">The user of a client application sends a message to one or more recipients.</span></span> <span data-ttu-id="435ef-121">消息存储提供程序启动发送的过程中，设置消息格式与所需的传输的其他信息。</span><span class="sxs-lookup"><span data-stu-id="435ef-121">The message store provider initiates the sending process, formatting the message with additional information needed for transmission.</span></span>
  
<span data-ttu-id="435ef-122">MAPI 后台处理程序接收的消息处理如果发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="435ef-122">MAPI spooler receives the message to process if any of the following conditions occur:</span></span>
  
- <span data-ttu-id="435ef-123">消息存储提供程序未紧密耦合与传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="435ef-123">The message store provider is not tightly coupled with a transport provider.</span></span>
    
- <span data-ttu-id="435ef-124">邮件需要预处理。</span><span class="sxs-lookup"><span data-stu-id="435ef-124">The message requires preprocessing.</span></span>
    
- <span data-ttu-id="435ef-125">消息存储和传输提供程序紧密，但不能处理，向其发送邮件的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="435ef-125">The message store and transport provider are tightly coupled, but they cannot handle all the recipients to whom the message is addressed.</span></span>
    
<span data-ttu-id="435ef-126">如果 MAPI 后台处理程序接收的消息，它会执行任何所需预处理，并将邮件传递到适当的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="435ef-126">If MAPI spooler receives the message, it performs any required preprocessing and delivers the message to the appropriate transport provider.</span></span> <span data-ttu-id="435ef-127">传输提供程序给其消息的系统，将其发送到其预期接收人的邮件。</span><span class="sxs-lookup"><span data-stu-id="435ef-127">The transport provider gives the message to its messaging system, which sends it to its intended recipient.</span></span>
  
<span data-ttu-id="435ef-128">与传入的消息将被颠倒流。</span><span class="sxs-lookup"><span data-stu-id="435ef-128">With incoming messages, the flow is reversed.</span></span> <span data-ttu-id="435ef-129">传输提供程序从其邮件系统中收到一条消息，并通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="435ef-129">The transport provider receives a message from its messaging system and notifies MAPI spooler.</span></span> <span data-ttu-id="435ef-130">后台处理程序执行任何所需的后处理，并通知的消息存储提供程序已到达一个新的邮件。</span><span class="sxs-lookup"><span data-stu-id="435ef-130">Spooler performs any necessary postprocessing and informs the message store provider that a new message has arrived.</span></span> <span data-ttu-id="435ef-131">此通知使客户端刷新其消息显示，使用户可以读取新邮件。</span><span class="sxs-lookup"><span data-stu-id="435ef-131">This notification causes the client to refresh its message display, enabling the user to read the new message.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="435ef-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="435ef-132">See also</span></span>

- [<span data-ttu-id="435ef-133">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="435ef-133">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

