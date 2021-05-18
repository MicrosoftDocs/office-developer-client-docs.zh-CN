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
# <a name="tightly-coupled-message-store-providers"></a>紧密耦合邮件存储提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序可以与传输提供程序紧密结合。 紧密结合 MAPI 服务提供商意味着实现两个提供程序，这样存储提供程序和传输提供程序就可以进行通信，使发送和接收邮件的过程更加高效。 这样做的好处是，当两个服务提供商可以直接交互而不是通过 MAPI 后台处理程序进行交互时，性能改进可以产生。 若要将邮件存储提供程序紧密耦合到传输提供程序，传输提供程序必须将邮件存储提供程序的条目标识符放在 **PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性中的 MAPI 状态表的传输提供程序行中。 这使 MAPI 后台处理程序能够将存储提供程序连接到传输提供程序。
  
不要求邮件存储提供程序与任何其他服务提供商紧密结合。 与邮件存储提供程序紧密耦合的最常见的服务提供商是传输提供程序。 这通常是为了在不涉及 MAPI 后台处理程序的情况下完成发送和接收邮件。 例如，当用户提交传出邮件时，合并的邮件存储提供程序和传输提供程序可以直接发送它。 合并的服务提供商不需要首先通知 MAPI 后台处理程序有要处理的新邮件，然后等待 MAPI 后台处理程序启动将邮件从邮件存储提供程序传输到传输提供程序的过程。 当使用基于服务器的消息存储时，通过最大程度地减少用户计算机和服务器之间的网络流量，这将具有特定的好处。
  
通常，没有明确指定的过程来紧密耦合服务提供商。 但是，您应使用以下准则：
  
- 如果紧密耦合服务提供商的原因是性能，请注意，该耦合会从 MAPI 子系统的一部分（通常将涉及这些部件）的进程中排除。 这意味着，组合服务提供程序中的单个部件应相互交互，以模拟它们通常与未使用的 MAPI 子系统部分进行交互的方式。
    
- 当紧密耦合的服务提供商与其他 MAPI 组件交互时，它们仍然必须以与它们完全一样的方式（如果未紧密耦合）进行交互。 例如，如果用户使用组合的邮件存储提供程序和传输提供程序作为其默认邮件存储，但使用单独的传输提供程序发送邮件（当用户在路过一台计算机并切换到远程传输提供程序时，可能会发生这种情况）则紧密耦合的服务提供商的邮件存储部分仍必须与 MAPI 后台处理程序交互，就像它是独立邮件存储提供程序一样。
    
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

