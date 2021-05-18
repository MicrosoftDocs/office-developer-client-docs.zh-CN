---
title: 紧密耦合邮件存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2eb493d7-bbd1-45b2-bd82-2bc452b2deab
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3c9996dad1e9aa8c291f1cd593d9651994d86141
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413225"
---
# <a name="tightly-coupled-message-store-providers"></a><span data-ttu-id="a9d0d-103">紧密耦合邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="a9d0d-103">Tightly Coupled Message Store Providers</span></span>

  
  
<span data-ttu-id="a9d0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a9d0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a9d0d-105">邮件存储提供程序可以与传输提供程序紧密结合。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-105">Message store providers can be tightly coupled with a transport provider.</span></span> <span data-ttu-id="a9d0d-106">紧密结合 MAPI 服务提供商意味着实现两个提供程序，这样存储提供程序和传输提供程序就可以进行通信，使发送和接收邮件的过程更加高效。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-106">Tightly coupling MAPI service providers means implementing the two providers such that the store provider and transport provider can communicate to make the process of sending and receiving messages more efficient.</span></span> <span data-ttu-id="a9d0d-107">这样做的好处是，当两个服务提供商可以直接交互而不是通过 MAPI 后台处理程序进行交互时，性能改进可以产生。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-107">The benefit of doing this is that performance improvements can result when two service providers can interact with each other directly rather than by means of MAPI spooler.</span></span> <span data-ttu-id="a9d0d-108">若要将邮件存储提供程序紧密耦合到传输提供程序，传输提供程序必须将邮件存储提供程序的条目标识符放在 **PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性中的 MAPI 状态表的传输提供程序行中。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-108">To tightly couple a message store provider to a transport provider, the transport provider must place the message store provider's entry identifier in the **PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) property in the transport provider's row in the MAPI status table.</span></span> <span data-ttu-id="a9d0d-109">这使 MAPI 后台处理程序能够将存储提供程序连接到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-109">This enables MAPI spooler to connect the store provider to the transport provider.</span></span>
  
<span data-ttu-id="a9d0d-110">不要求邮件存储提供程序与任何其他服务提供商紧密结合。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-110">There is no requirement that a message store provider ever be tightly coupled with any other service provider.</span></span> <span data-ttu-id="a9d0d-111">与邮件存储提供程序紧密耦合的最常见的服务提供商是传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-111">The most common service provider to tightly couple with a message store provider is a transport provider.</span></span> <span data-ttu-id="a9d0d-112">这通常是为了在不涉及 MAPI 后台处理程序的情况下完成发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-112">This is usually done so that sending and receiving messages can be accomplished without involving the MAPI spooler.</span></span> <span data-ttu-id="a9d0d-113">例如，当用户提交传出邮件时，合并的邮件存储提供程序和传输提供程序可以直接发送它。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-113">For example, when the user submits an outgoing message, the combined message store provider and transport provider can send it directly.</span></span> <span data-ttu-id="a9d0d-114">合并的服务提供商不需要首先通知 MAPI 后台处理程序有要处理的新邮件，然后等待 MAPI 后台处理程序启动将邮件从邮件存储提供程序传输到传输提供程序的过程。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-114">The combined service providers do not have to first notify MAPI spooler that there is a new message to process and then wait for MAPI spooler to initiate the process of transferring the message from the message store provider to the transport provider.</span></span> <span data-ttu-id="a9d0d-115">当使用基于服务器的消息存储时，通过最大程度地减少用户计算机和服务器之间的网络流量，这将具有特定的好处。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-115">This has particular benefits when a server-based message store is being used by minimizing network traffic between the user's computer and the server.</span></span>
  
<span data-ttu-id="a9d0d-116">通常，没有明确指定的过程来紧密耦合服务提供商。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-116">In general, there are no well-specified procedures for tightly coupling service providers.</span></span> <span data-ttu-id="a9d0d-117">但是，您应使用以下准则：</span><span class="sxs-lookup"><span data-stu-id="a9d0d-117">However, you should use the following guidelines:</span></span>
  
- <span data-ttu-id="a9d0d-118">如果紧密耦合服务提供商的原因是性能，请注意，该耦合会从 MAPI 子系统的一部分（通常将涉及这些部件）的进程中排除。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-118">If the reason for tightly coupling service providers is performance, be aware that the coupling takes parts of the MAPI subsystem out of the processes that those parts would normally be involved in.</span></span> <span data-ttu-id="a9d0d-119">这意味着，组合服务提供程序中的单个部件应相互交互，以模拟它们通常与未使用的 MAPI 子系统部分进行交互的方式。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-119">This implies that the individual parts in the combined service provider should interact with each other in a way that simulates the interaction they would normally have with the parts of the MAPI subsystem that are not being used.</span></span>
    
- <span data-ttu-id="a9d0d-120">当紧密耦合的服务提供商与其他 MAPI 组件交互时，它们仍然必须以与它们完全一样的方式（如果未紧密耦合）进行交互。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-120">When tightly coupled service providers do interact with other MAPI components, they must still interact with them in exactly the way they would if they were not tightly coupled.</span></span> <span data-ttu-id="a9d0d-121">例如，如果用户使用组合的邮件存储提供程序和传输提供程序作为其默认邮件存储，但使用单独的传输提供程序发送邮件（当用户在路过一台计算机并切换到远程传输提供程序时，可能会发生这种情况）则紧密耦合的服务提供商的邮件存储部分仍必须与 MAPI 后台处理程序交互，就像它是独立邮件存储提供程序一样。</span><span class="sxs-lookup"><span data-stu-id="a9d0d-121">For example, if a user is using a combined message store provider and transport provider as their default message store but is using a separate transport provider to send messages — as can happen when a user takes a computer on the road and switches to a remote transport provider — the message store portion of the tightly coupled service provider must still interact with MAPI spooler just as if it were a standalone message store provider.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a9d0d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9d0d-122">See also</span></span>



[<span data-ttu-id="a9d0d-123">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="a9d0d-123">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

