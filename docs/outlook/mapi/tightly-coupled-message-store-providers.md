---
title: 紧密耦合邮件存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2eb493d7-bbd1-45b2-bd82-2bc452b2deab
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 83ebb739302ca0e12604b9eaf854f273554826ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778970"
---
# <a name="tightly-coupled-message-store-providers"></a><span data-ttu-id="4cad5-103">紧密耦合邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="4cad5-103">Tightly Coupled Message Store Providers</span></span>

  
  
<span data-ttu-id="4cad5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4cad5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4cad5-105">与传输提供程序，为紧密耦合消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="4cad5-105">Message store providers can be tightly coupled with a transport provider.</span></span> <span data-ttu-id="4cad5-106">紧密耦合 MAPI 服务提供程序是指实现两个提供程序，以便的存储提供程序和传输提供程序可以通信，以使发送和接收消息更高效的过程。</span><span class="sxs-lookup"><span data-stu-id="4cad5-106">Tightly coupling MAPI service providers means implementing the two providers such that the store provider and transport provider can communicate to make the process of sending and receiving messages more efficient.</span></span> <span data-ttu-id="4cad5-107">此操作的好处是相互直接，而不是通过 MAPI 后台处理程序，可进行交互两个服务提供程序时，会导致性能改进。</span><span class="sxs-lookup"><span data-stu-id="4cad5-107">The benefit of doing this is that performance improvements can result when two service providers can interact with each other directly rather than by means of MAPI spooler.</span></span> <span data-ttu-id="4cad5-108">以紧密耦合到传输提供程序的消息存储提供程序，传输提供程序必须发出的消息存储提供程序的条目标识符**PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性中的传输提供程序MAPI 状态表中的行。</span><span class="sxs-lookup"><span data-stu-id="4cad5-108">To tightly couple a message store provider to a transport provider, the transport provider must place the message store provider's entry identifier in the **PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) property in the transport provider's row in the MAPI status table.</span></span> <span data-ttu-id="4cad5-109">这样 MAPI 后台处理程序连接到传输提供程序的存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="4cad5-109">This enables MAPI spooler to connect the store provider to the transport provider.</span></span>
  
<span data-ttu-id="4cad5-110">没有任何要求的消息存储提供程序以往任何时候都将与紧密耦合任何其他服务提供商。</span><span class="sxs-lookup"><span data-stu-id="4cad5-110">There is no requirement that a message store provider ever be tightly coupled with any other service provider.</span></span> <span data-ttu-id="4cad5-111">最常见的服务提供商，以紧密耦合与消息存储提供程序是传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="4cad5-111">The most common service provider to tightly couple with a message store provider is a transport provider.</span></span> <span data-ttu-id="4cad5-112">这通常是，以便发送和接收消息可以完成而涉及 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="4cad5-112">This is usually done so that sending and receiving messages can be accomplished without involving the MAPI spooler.</span></span> <span data-ttu-id="4cad5-113">例如，当用户提交的传出邮件时，组合的消息存储提供程序和传输提供程序可以将其发送直接。</span><span class="sxs-lookup"><span data-stu-id="4cad5-113">For example, when the user submits an outgoing message, the combined message store provider and transport provider can send it directly.</span></span> <span data-ttu-id="4cad5-114">组合的服务提供程序没有首先通知 MAPI 后台处理程序存在新消息处理，然后等待 MAPI 后台处理程序启动从消息存储提供程序的邮件传输到传输提供程序的过程。</span><span class="sxs-lookup"><span data-stu-id="4cad5-114">The combined service providers do not have to first notify MAPI spooler that there is a new message to process and then wait for MAPI spooler to initiate the process of transferring the message from the message store provider to the transport provider.</span></span> <span data-ttu-id="4cad5-115">使用基于服务器的消息存储库时通过尽量减少用户的计算机和服务器之间的网络流量，这有特定的好处。</span><span class="sxs-lookup"><span data-stu-id="4cad5-115">This has particular benefits when a server-based message store is being used by minimizing network traffic between the user's computer and the server.</span></span>
  
<span data-ttu-id="4cad5-116">一般情况下，没有为紧密耦合服务提供商合理指定过程。</span><span class="sxs-lookup"><span data-stu-id="4cad5-116">In general, there are no well-specified procedures for tightly coupling service providers.</span></span> <span data-ttu-id="4cad5-117">但是，您应使用以下准则：</span><span class="sxs-lookup"><span data-stu-id="4cad5-117">However, you should use the following guidelines:</span></span>
  
- <span data-ttu-id="4cad5-118">如果为紧密耦合服务提供商的原因是性能，则应注意耦合所需部件这些部件通常会参与的进程不足 MAPI 子系统。</span><span class="sxs-lookup"><span data-stu-id="4cad5-118">If the reason for tightly coupling service providers is performance, be aware that the coupling takes parts of the MAPI subsystem out of the processes that those parts would normally be involved in.</span></span> <span data-ttu-id="4cad5-119">这意味着组合的服务提供程序中的各个部分应相互交互的模拟他们通常必须与未使用的 MAPI 子系统的部件的交互方式。</span><span class="sxs-lookup"><span data-stu-id="4cad5-119">This implies that the individual parts in the combined service provider should interact with each other in a way that simulates the interaction they would normally have with the parts of the MAPI subsystem that are not being used.</span></span>
    
- <span data-ttu-id="4cad5-120">紧密耦合的服务提供商进行交互时与其他 MAPI 组件，它们必须仍与之交互完全那样如果它们不紧密结合在一起。</span><span class="sxs-lookup"><span data-stu-id="4cad5-120">When tightly coupled service providers do interact with other MAPI components, they must still interact with them in exactly the way they would if they were not tightly coupled.</span></span> <span data-ttu-id="4cad5-121">例如，如果用户为其默认邮件存储区使用组合的消息存储提供程序和传输提供程序，但使用不同的传输提供程序将邮件发送 — 为用户在旅途中采用计算机，并将切换到远程传输 pr 时可以执行ovider — 紧密耦合的服务提供商的消息存储部分仍必须与 MAPI 后台处理程序交互就好像它是独立消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="4cad5-121">For example, if a user is using a combined message store provider and transport provider as their default message store but is using a separate transport provider to send messages — as can happen when a user takes a computer on the road and switches to a remote transport provider — the message store portion of the tightly coupled service provider must still interact with MAPI spooler just as if it were a standalone message store provider.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4cad5-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cad5-122">See also</span></span>



[<span data-ttu-id="4cad5-123">开发 MAPI 邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="4cad5-123">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

