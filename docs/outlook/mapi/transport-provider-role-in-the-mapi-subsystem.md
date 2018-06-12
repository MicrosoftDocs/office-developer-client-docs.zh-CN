---
title: MAPI 子系统中的传输提供程序角色
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7659369a-0952-4f5a-a86b-91958c4c1a3f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7ea60b73fb1abe32b6db5e3c73d6ef3fac53d35d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779000"
---
# <a name="transport-provider-role-in-the-mapi-subsystem"></a><span data-ttu-id="3776c-103">MAPI 子系统中的传输提供程序角色</span><span class="sxs-lookup"><span data-stu-id="3776c-103">Transport provider role in the MAPI subsystem</span></span>
  
<span data-ttu-id="3776c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3776c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3776c-105">传输提供程序动态链接库 (Dll) 提供了 MAPI 后台处理程序和负责邮件发送和接收的邮件系统的一部分之间的接口。</span><span class="sxs-lookup"><span data-stu-id="3776c-105">Transport provider dynamic-link libraries (DLLs) provide the interface between the MAPI spooler and the part of a messaging system responsible for message sending and receiving.</span></span> <span data-ttu-id="3776c-106">MAPI 后台处理程序和传输提供程序一起工作以处理发送邮件还是接收邮件的职责。</span><span class="sxs-lookup"><span data-stu-id="3776c-106">The MAPI spooler and the transport provider work together to handle the responsibilities of sending a message or receiving a message.</span></span> <span data-ttu-id="3776c-107">MAPI 后台处理程序在首次使用并将其发布当不再需要时对其时加载传输提供程序 DLL。</span><span class="sxs-lookup"><span data-stu-id="3776c-107">The MAPI spooler loads the transport provider DLL when it is first used and releases it when it is no longer needed.</span></span> <span data-ttu-id="3776c-108">多个传输提供程序可以安装在相同的系统，但 MAPI 提供所需一个后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="3776c-108">Multiple transport providers can be installed on the same system, but MAPI supplies the one spooler required.</span></span>
  
<span data-ttu-id="3776c-109">客户端应用程序通常不能直接与传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="3776c-109">Client applications do not typically communicate directly with the transport provider.</span></span> <span data-ttu-id="3776c-110">相反，客户端将通过存储提供程序的邮件提交和 MAPI 后台处理程序将传出邮件发送到适当的传输提供程序，并将传入消息传送到相应的消息存储。</span><span class="sxs-lookup"><span data-stu-id="3776c-110">Rather, clients submit messages through a store provider and the MAPI spooler sends outgoing messages to the appropriate transport provider and delivers incoming messages to the appropriate message store.</span></span> <span data-ttu-id="3776c-111">MAPI 后台处理程序自己的工作，并使其传输提供程序，当前景色的应用程序处于空闲状态的呼叫。</span><span class="sxs-lookup"><span data-stu-id="3776c-111">The MAPI spooler does its work and makes its calls to transport providers when foreground applications are idle.</span></span> <span data-ttu-id="3776c-112">（可选） 在第一个传输提供程序时显示对话框登录后，传输提供程序在后台运行，除非由客户端刷新发送和接收队列中调用。</span><span class="sxs-lookup"><span data-stu-id="3776c-112">After optionally displaying dialog boxes when the transport provider is first logged on, transport providers operate in the background unless called by the client to flush send and receive queues.</span></span> 
  
<span data-ttu-id="3776c-113">传输提供程序的 MAPI 邮件系统中有以下责任：</span><span class="sxs-lookup"><span data-stu-id="3776c-113">Transport providers have the following responsibilities in a MAPI messaging system:</span></span>
  
- <span data-ttu-id="3776c-114">参与者可以接受的地址类型注册 MAPI 后台处理程序，以便 MAPI 后台处理程序可以将邮件提交到适当的传输提供程序根据邮件的目标地址。</span><span class="sxs-lookup"><span data-stu-id="3776c-114">Register the address types they can accept with the MAPI spooler so the MAPI spooler can submit messages to the appropriate transport provider depending on the destination address of the messages.</span></span> <span data-ttu-id="3776c-115">一个传输提供程序可以注册多个地址类型。</span><span class="sxs-lookup"><span data-stu-id="3776c-115">One transport provider can register more than one address type.</span></span> <span data-ttu-id="3776c-116">传输提供程序还可以使用 MAPI 后台处理程序注册特定收件人的地址。</span><span class="sxs-lookup"><span data-stu-id="3776c-116">Transport providers can also register specific recipients' addresses with the MAPI spooler.</span></span> <span data-ttu-id="3776c-117">邮件发送到这些地址之一将提交到传输提供程序注册 MAPI 后台处理程序的地址。</span><span class="sxs-lookup"><span data-stu-id="3776c-117">Messages addressed to one of these addresses will be submitted to the transport provider that registered the address with the MAPI spooler.</span></span> <span data-ttu-id="3776c-118">有关详细信息，请参阅[传输提供程序和 MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。</span><span class="sxs-lookup"><span data-stu-id="3776c-118">For more information, see [Transport Provider and MAPI Spooler Operational Model](transport-provider-and-mapi-spooler-operational-model.md).</span></span>
    
- <span data-ttu-id="3776c-119">将传入邮件传递到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="3776c-119">Deliver incoming messages to the MAPI spooler.</span></span> <span data-ttu-id="3776c-120">根据邮件系统的性质，传输提供程序可以也直接通知 MAPI 后台处理程序时收到新邮件，或它可以请求 MAPI 后台处理程序轮询定期要检查新邮件的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="3776c-120">Depending on the nature of the messaging system, a transport provider can either directly notify the MAPI spooler when a new message arrives, or it can request that the MAPI spooler poll the transport provider periodically to check for new messages.</span></span>
    
- <span data-ttu-id="3776c-121">将邮件系统的本机的邮件属性与 MAPI 邮件属性相互转换。</span><span class="sxs-lookup"><span data-stu-id="3776c-121">Convert MAPI message properties to and from message properties native to the messaging system.</span></span> <span data-ttu-id="3776c-122">例如，传输提供程序可能需要转换为邮件系统可接受的窗体中的传出邮件的发件人和收件人的地址。</span><span class="sxs-lookup"><span data-stu-id="3776c-122">For example, the transport provider might have to convert the sender's and recipient's addresses in an outgoing message to a form that is acceptable to the messaging system.</span></span> <span data-ttu-id="3776c-123">某些消息系统不支持的所有 MAPI 邮件属性。</span><span class="sxs-lookup"><span data-stu-id="3776c-123">Some messaging systems do not support all of the MAPI message properties.</span></span> <span data-ttu-id="3776c-124">有关时邮件传递到邮件系统保留 MAPI 邮件属性的详细信息，请参阅[开发 TNEF-Enabled 传输提供程序](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="3776c-124">For more information about preserving MAPI message properties when delivering messages to a messaging system, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span>
    
- <span data-ttu-id="3776c-125">注册到传输提供程序特定的邮件和收件人选项。</span><span class="sxs-lookup"><span data-stu-id="3776c-125">Register message and recipient options specific to the transport provider.</span></span>
    
- <span data-ttu-id="3776c-126">执行任何的所需的邮件系统的凭据进行验证。</span><span class="sxs-lookup"><span data-stu-id="3776c-126">Perform any verification of credentials required by the messaging system.</span></span>
    
- <span data-ttu-id="3776c-127">使用 message 对象的访问出站邮件传递给它的 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="3776c-127">Access outbound messages using the message object passed to it by the MAPI spooler.</span></span>
    
- <span data-ttu-id="3776c-128">翻译所需的基础邮件系统的邮件格式。</span><span class="sxs-lookup"><span data-stu-id="3776c-128">Translate message format as required by the underlying messaging system.</span></span>
    
- <span data-ttu-id="3776c-129">通知 MAPI 后台处理程序的传输提供程序已接受负责处理通过**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为这些收件人的传出邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="3776c-129">Notify the MAPI spooler which recipients of an outgoing message the transport provider has accepted responsibility for handling by setting the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property for those recipients.</span></span>
    
- <span data-ttu-id="3776c-130">当需要处理传入消息通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="3776c-130">Inform the MAPI spooler when an incoming message needs to be handled.</span></span>
    
- <span data-ttu-id="3776c-131">通过使用消息对象，将传入消息数据传递到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="3776c-131">Pass incoming message data to the MAPI spooler by using message objects.</span></span>
    
- <span data-ttu-id="3776c-132">将值分配给所有必需的 MAPI 邮件属性对传入邮件。</span><span class="sxs-lookup"><span data-stu-id="3776c-132">Assign values to all required MAPI message properties on incoming messages.</span></span>
    
- <span data-ttu-id="3776c-133">邮件从系统中删除基础消息后传递，如有必要。</span><span class="sxs-lookup"><span data-stu-id="3776c-133">Delete the message from the underlying messaging system after delivery, if necessary.</span></span>
    
- <span data-ttu-id="3776c-134">提供 MAPI 后台处理程序和客户端应用程序的状态的信息。</span><span class="sxs-lookup"><span data-stu-id="3776c-134">Provide status information for the MAPI spooler and client applications.</span></span>
    
<span data-ttu-id="3776c-135">下图显示与 MAPI 体系结构的其他组件的传输提供程序的角色。</span><span class="sxs-lookup"><span data-stu-id="3776c-135">The following illustration shows a transport provider's role with respect to the other components of the MAPI architecture.</span></span>
  
<span data-ttu-id="3776c-136">**在消息系统传输提供程序角色**</span><span class="sxs-lookup"><span data-stu-id="3776c-136">**Transport provider role in a messaging system**</span></span>
  
<span data-ttu-id="3776c-137">![在消息系统传输提供程序角色](media/xp01.gif "在消息系统传输提供程序角色")</span><span class="sxs-lookup"><span data-stu-id="3776c-137">![Transport provider role in a messaging system](media/xp01.gif "Transport provider role in a messaging system")</span></span>
  

