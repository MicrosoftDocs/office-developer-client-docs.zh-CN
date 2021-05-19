---
title: MAPI 子系统中的传输提供程序角色
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7659369a-0952-4f5a-a86b-91958c4c1a3f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7cadb57706e3feec7ed98dd5e4e8d75967036fef
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424054"
---
# <a name="transport-provider-role-in-the-mapi-subsystem"></a><span data-ttu-id="fad5a-103">MAPI 子系统中的传输提供程序角色</span><span class="sxs-lookup"><span data-stu-id="fad5a-103">Transport provider role in the MAPI subsystem</span></span>
  
<span data-ttu-id="fad5a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fad5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fad5a-105">传输提供程序动态链接库 (DLL) 提供了 MAPI 后台处理程序与负责邮件发送和接收的邮件系统部分之间的接口。</span><span class="sxs-lookup"><span data-stu-id="fad5a-105">Transport provider dynamic-link libraries (DLLs) provide the interface between the MAPI spooler and the part of a messaging system responsible for message sending and receiving.</span></span> <span data-ttu-id="fad5a-106">MAPI 后台处理程序和传输提供程序协同工作以处理发送邮件或接收邮件的责任。</span><span class="sxs-lookup"><span data-stu-id="fad5a-106">The MAPI spooler and the transport provider work together to handle the responsibilities of sending a message or receiving a message.</span></span> <span data-ttu-id="fad5a-107">MAPI 后台处理程序在首次使用传输提供程序 DLL 时加载该 DLL，并释放它（当不再需要它时）。</span><span class="sxs-lookup"><span data-stu-id="fad5a-107">The MAPI spooler loads the transport provider DLL when it is first used and releases it when it is no longer needed.</span></span> <span data-ttu-id="fad5a-108">可以在同一系统中安装多个传输提供程序，但 MAPI 提供所需的一个后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="fad5a-108">Multiple transport providers can be installed on the same system, but MAPI supplies the one spooler required.</span></span>
  
<span data-ttu-id="fad5a-109">客户端应用程序通常不直接与传输提供程序通信。</span><span class="sxs-lookup"><span data-stu-id="fad5a-109">Client applications do not typically communicate directly with the transport provider.</span></span> <span data-ttu-id="fad5a-110">相反，客户端通过存储提供程序提交邮件，MAPI 后台处理程序将传出邮件发送到相应的传输提供程序，并将传入邮件发送到相应的邮件存储。</span><span class="sxs-lookup"><span data-stu-id="fad5a-110">Rather, clients submit messages through a store provider and the MAPI spooler sends outgoing messages to the appropriate transport provider and delivers incoming messages to the appropriate message store.</span></span> <span data-ttu-id="fad5a-111">MAPI 后台处理程序执行其工作，在前台应用程序空闲时调用传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fad5a-111">The MAPI spooler does its work and makes its calls to transport providers when foreground applications are idle.</span></span> <span data-ttu-id="fad5a-112">在首次登录传输提供程序时（可选）显示对话框后，除非客户端调用来刷新发送和接收队列，否则传输提供程序将在后台运行。</span><span class="sxs-lookup"><span data-stu-id="fad5a-112">After optionally displaying dialog boxes when the transport provider is first logged on, transport providers operate in the background unless called by the client to flush send and receive queues.</span></span> 
  
<span data-ttu-id="fad5a-113">传输提供程序在 MAPI 邮件系统中承担以下责任：</span><span class="sxs-lookup"><span data-stu-id="fad5a-113">Transport providers have the following responsibilities in a MAPI messaging system:</span></span>
  
- <span data-ttu-id="fad5a-114">使用 MAPI 后台处理程序注册他们可以接受的地址类型，以便 MAPI 后台处理程序可以将邮件提交到相应的传输提供程序，具体取决于邮件的目标地址。</span><span class="sxs-lookup"><span data-stu-id="fad5a-114">Register the address types they can accept with the MAPI spooler so the MAPI spooler can submit messages to the appropriate transport provider depending on the destination address of the messages.</span></span> <span data-ttu-id="fad5a-115">一个传输提供程序可以注册多个地址类型。</span><span class="sxs-lookup"><span data-stu-id="fad5a-115">One transport provider can register more than one address type.</span></span> <span data-ttu-id="fad5a-116">传输提供程序还可以在 MAPI 后台处理程序中注册特定收件人的地址。</span><span class="sxs-lookup"><span data-stu-id="fad5a-116">Transport providers can also register specific recipients' addresses with the MAPI spooler.</span></span> <span data-ttu-id="fad5a-117">发送到其中一个地址的邮件将提交到向 MAPI 后台处理程序注册地址的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fad5a-117">Messages addressed to one of these addresses will be submitted to the transport provider that registered the address with the MAPI spooler.</span></span> <span data-ttu-id="fad5a-118">有关详细信息，请参阅传输 [提供程序和 MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。</span><span class="sxs-lookup"><span data-stu-id="fad5a-118">For more information, see [Transport Provider and MAPI Spooler Operational Model](transport-provider-and-mapi-spooler-operational-model.md).</span></span>
    
- <span data-ttu-id="fad5a-119">将传入邮件传递至 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="fad5a-119">Deliver incoming messages to the MAPI spooler.</span></span> <span data-ttu-id="fad5a-120">根据邮件系统的性质，传输提供程序可以在新邮件到达时直接通知 MAPI 后台处理程序，也可以请求 MAPI 后台处理程序定期轮询传输提供程序以检查新邮件。</span><span class="sxs-lookup"><span data-stu-id="fad5a-120">Depending on the nature of the messaging system, a transport provider can either directly notify the MAPI spooler when a new message arrives, or it can request that the MAPI spooler poll the transport provider periodically to check for new messages.</span></span>
    
- <span data-ttu-id="fad5a-121">将 MAPI 邮件属性转换为邮件系统本机的邮件属性，以及从邮件属性转换邮件属性。</span><span class="sxs-lookup"><span data-stu-id="fad5a-121">Convert MAPI message properties to and from message properties native to the messaging system.</span></span> <span data-ttu-id="fad5a-122">例如，传输提供程序可能必须将传出邮件中的发件人和收件人地址转换为邮件系统可接受的格式。</span><span class="sxs-lookup"><span data-stu-id="fad5a-122">For example, the transport provider might have to convert the sender's and recipient's addresses in an outgoing message to a form that is acceptable to the messaging system.</span></span> <span data-ttu-id="fad5a-123">某些邮件系统不支持所有 MAPI 邮件属性。</span><span class="sxs-lookup"><span data-stu-id="fad5a-123">Some messaging systems do not support all of the MAPI message properties.</span></span> <span data-ttu-id="fad5a-124">有关在将邮件传递至邮件系统时保留 MAPI 邮件属性的信息，请参阅 Developing [a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="fad5a-124">For more information about preserving MAPI message properties when delivering messages to a messaging system, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span>
    
- <span data-ttu-id="fad5a-125">注册特定于传输提供程序的邮件和收件人选项。</span><span class="sxs-lookup"><span data-stu-id="fad5a-125">Register message and recipient options specific to the transport provider.</span></span>
    
- <span data-ttu-id="fad5a-126">对邮件系统所需的凭据执行任何验证。</span><span class="sxs-lookup"><span data-stu-id="fad5a-126">Perform any verification of credentials required by the messaging system.</span></span>
    
- <span data-ttu-id="fad5a-127">使用 MAPI 后台处理程序传递给它的 message 对象访问出站邮件。</span><span class="sxs-lookup"><span data-stu-id="fad5a-127">Access outbound messages using the message object passed to it by the MAPI spooler.</span></span>
    
- <span data-ttu-id="fad5a-128">根据基础邮件系统要求转换邮件格式。</span><span class="sxs-lookup"><span data-stu-id="fad5a-128">Translate message format as required by the underlying messaging system.</span></span>
    
- <span data-ttu-id="fad5a-129">通过为这些收件人设置 **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性，通知 MAPI 后台处理程序传输提供程序已接受处理传出邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="fad5a-129">Notify the MAPI spooler which recipients of an outgoing message the transport provider has accepted responsibility for handling by setting the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property for those recipients.</span></span>
    
- <span data-ttu-id="fad5a-130">需要处理传入邮件时通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="fad5a-130">Inform the MAPI spooler when an incoming message needs to be handled.</span></span>
    
- <span data-ttu-id="fad5a-131">使用 message 对象将传入邮件数据传递到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="fad5a-131">Pass incoming message data to the MAPI spooler by using message objects.</span></span>
    
- <span data-ttu-id="fad5a-132">将值分配给传入邮件上所有必需的 MAPI 邮件属性。</span><span class="sxs-lookup"><span data-stu-id="fad5a-132">Assign values to all required MAPI message properties on incoming messages.</span></span>
    
- <span data-ttu-id="fad5a-133">如有必要，在传递之后从基础邮件系统中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="fad5a-133">Delete the message from the underlying messaging system after delivery, if necessary.</span></span>
    
- <span data-ttu-id="fad5a-134">提供 MAPI 后台处理程序和客户端应用程序的状态信息。</span><span class="sxs-lookup"><span data-stu-id="fad5a-134">Provide status information for the MAPI spooler and client applications.</span></span>
    
<span data-ttu-id="fad5a-135">下图显示了传输提供程序在 MAPI 体系结构的其他组件方面的角色。</span><span class="sxs-lookup"><span data-stu-id="fad5a-135">The following illustration shows a transport provider's role with respect to the other components of the MAPI architecture.</span></span>
  
<span data-ttu-id="fad5a-136">**在消息系统传输提供程序角色**</span><span class="sxs-lookup"><span data-stu-id="fad5a-136">**Transport provider role in a messaging system**</span></span>
  
<span data-ttu-id="fad5a-137">![邮件系统中邮件系统传输](media/xp01.gif "提供程序角色中的传输提供程序角色")</span><span class="sxs-lookup"><span data-stu-id="fad5a-137">![Transport provider role in a messaging system](media/xp01.gif "Transport provider role in a messaging system")</span></span>
  

