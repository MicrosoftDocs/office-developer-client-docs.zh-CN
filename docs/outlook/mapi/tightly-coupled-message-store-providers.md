---
title: 紧密耦合的邮件存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2eb493d7-bbd1-45b2-bd82-2bc452b2deab
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3c9996dad1e9aa8c291f1cd593d9651994d86141
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330056"
---
# <a name="tightly-coupled-message-store-providers"></a><span data-ttu-id="23f14-103">紧密耦合的邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="23f14-103">Tightly Coupled Message Store Providers</span></span>

  
  
<span data-ttu-id="23f14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23f14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23f14-105">邮件存储提供程序可与传输提供程序紧密结合。</span><span class="sxs-lookup"><span data-stu-id="23f14-105">Message store providers can be tightly coupled with a transport provider.</span></span> <span data-ttu-id="23f14-106">紧密耦合 MAPI 服务提供程序是指实现两个提供程序, 以便存储提供程序和传输提供程序可以进行通信, 以使发送和接收邮件的过程更加有效。</span><span class="sxs-lookup"><span data-stu-id="23f14-106">Tightly coupling MAPI service providers means implementing the two providers such that the store provider and transport provider can communicate to make the process of sending and receiving messages more efficient.</span></span> <span data-ttu-id="23f14-107">执行此操作的好处在于, 当两个服务提供程序可以直接交互而不是通过 MAPI 后台处理程序交互时, 可能会导致性能改进。</span><span class="sxs-lookup"><span data-stu-id="23f14-107">The benefit of doing this is that performance improvements can result when two service providers can interact with each other directly rather than by means of MAPI spooler.</span></span> <span data-ttu-id="23f14-108">若要将邮件存储提供程序紧密地带到传输提供程序, 传输提供程序必须将邮件存储提供程序的条目标识符放在传输提供程序的**PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性中。MAPI 状态表中的行。</span><span class="sxs-lookup"><span data-stu-id="23f14-108">To tightly couple a message store provider to a transport provider, the transport provider must place the message store provider's entry identifier in the **PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) property in the transport provider's row in the MAPI status table.</span></span> <span data-ttu-id="23f14-109">这将使 MAPI 后台处理程序能够将存储提供程序连接到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="23f14-109">This enables MAPI spooler to connect the store provider to the transport provider.</span></span>
  
<span data-ttu-id="23f14-110">不要求邮件存储提供程序与任何其他服务提供程序紧密结合。</span><span class="sxs-lookup"><span data-stu-id="23f14-110">There is no requirement that a message store provider ever be tightly coupled with any other service provider.</span></span> <span data-ttu-id="23f14-111">最常用的服务提供程序是一种传输提供程序, 与邮件存储提供程序紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="23f14-111">The most common service provider to tightly couple with a message store provider is a transport provider.</span></span> <span data-ttu-id="23f14-112">执行此操作通常是为了能够在不涉及 MAPI 后台处理程序的情况下完成发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="23f14-112">This is usually done so that sending and receiving messages can be accomplished without involving the MAPI spooler.</span></span> <span data-ttu-id="23f14-113">例如, 当用户提交传出邮件时, 组合的邮件存储提供程序和传输提供程序可以直接发送邮件。</span><span class="sxs-lookup"><span data-stu-id="23f14-113">For example, when the user submits an outgoing message, the combined message store provider and transport provider can send it directly.</span></span> <span data-ttu-id="23f14-114">组合服务提供程序无需先通知 mapi 后台处理程序存在要处理的新邮件, 然后等待 mapi 后台处理程序启动将邮件从邮件存储提供程序传输到传输提供程序的过程。</span><span class="sxs-lookup"><span data-stu-id="23f14-114">The combined service providers do not have to first notify MAPI spooler that there is a new message to process and then wait for MAPI spooler to initiate the process of transferring the message from the message store provider to the transport provider.</span></span> <span data-ttu-id="23f14-115">在使用基于服务器的邮件存储区时, 在用户计算机与服务器之间的网络通信最小化时, 这有特定优势。</span><span class="sxs-lookup"><span data-stu-id="23f14-115">This has particular benefits when a server-based message store is being used by minimizing network traffic between the user's computer and the server.</span></span>
  
<span data-ttu-id="23f14-116">一般情况下, 没有任何明确指定的过程可用于紧密耦合服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="23f14-116">In general, there are no well-specified procedures for tightly coupling service providers.</span></span> <span data-ttu-id="23f14-117">但是, 应遵循以下准则:</span><span class="sxs-lookup"><span data-stu-id="23f14-117">However, you should use the following guidelines:</span></span>
  
- <span data-ttu-id="23f14-118">如果与服务提供商紧密耦合的原因是性能, 请注意, 耦合会将 MAPI 子系统的一部分从通常涉及这些部件的进程中取出。</span><span class="sxs-lookup"><span data-stu-id="23f14-118">If the reason for tightly coupling service providers is performance, be aware that the coupling takes parts of the MAPI subsystem out of the processes that those parts would normally be involved in.</span></span> <span data-ttu-id="23f14-119">这意味着组合服务提供程序中的各个部件应以模拟其通常与未使用的 MAPI 子系统的部件的交互方式相互进行交互。</span><span class="sxs-lookup"><span data-stu-id="23f14-119">This implies that the individual parts in the combined service provider should interact with each other in a way that simulates the interaction they would normally have with the parts of the MAPI subsystem that are not being used.</span></span>
    
- <span data-ttu-id="23f14-120">当紧密结合的服务提供商与其他 MAPI 组件进行交互时, 它们仍必须与它们的交互方式完全结合。</span><span class="sxs-lookup"><span data-stu-id="23f14-120">When tightly coupled service providers do interact with other MAPI components, they must still interact with them in exactly the way they would if they were not tightly coupled.</span></span> <span data-ttu-id="23f14-121">例如, 如果用户使用组合邮件存储提供程序和传输提供程序作为其默认邮件存储, 但使用单独的传输提供程序发送邮件, 则在用户将计算机放在路上并切换到远程传输 pr 时可能会发生这种情况。ovider —紧耦合服务提供程序的邮件存储区部分仍必须与 MAPI 后台处理程序交互, 就像它是独立的邮件存储提供程序一样。</span><span class="sxs-lookup"><span data-stu-id="23f14-121">For example, if a user is using a combined message store provider and transport provider as their default message store but is using a separate transport provider to send messages — as can happen when a user takes a computer on the road and switches to a remote transport provider — the message store portion of the tightly coupled service provider must still interact with MAPI spooler just as if it were a standalone message store provider.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="23f14-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23f14-122">See also</span></span>



[<span data-ttu-id="23f14-123">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="23f14-123">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

