---
title: 紧密耦合的消息存储提供程序
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
# <a name="tightly-coupled-message-store-providers"></a>紧密耦合的消息存储提供程序

  
  
**适用于**： Outlook 
  
与传输提供程序，为紧密耦合消息存储提供程序。 紧密耦合 MAPI 服务提供程序是指实现两个提供程序，以便的存储提供程序和传输提供程序可以通信，以使发送和接收消息更高效的过程。 此操作的好处是相互直接，而不是通过 MAPI 后台处理程序，可进行交互两个服务提供程序时，会导致性能改进。 以紧密耦合到传输提供程序的消息存储提供程序，传输提供程序必须发出的消息存储提供程序的条目标识符**PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性中的传输提供程序MAPI 状态表中的行。 这样 MAPI 后台处理程序连接到传输提供程序的存储提供程序。
  
没有任何要求的消息存储提供程序以往任何时候都将与紧密耦合任何其他服务提供商。 最常见的服务提供商，以紧密耦合与消息存储提供程序是传输提供程序。 这通常是，以便发送和接收消息可以完成而涉及 MAPI 后台处理程序。 例如，当用户提交的传出邮件时，组合的消息存储提供程序和传输提供程序可以将其发送直接。 组合的服务提供程序没有首先通知 MAPI 后台处理程序存在新消息处理，然后等待 MAPI 后台处理程序启动从消息存储提供程序的邮件传输到传输提供程序的过程。 使用基于服务器的消息存储库时通过尽量减少用户的计算机和服务器之间的网络流量，这有特定的好处。
  
一般情况下，没有为紧密耦合服务提供商合理指定过程。 但是，您应使用以下准则：
  
- 如果为紧密耦合服务提供商的原因是性能，则应注意耦合所需部件这些部件通常会参与的进程不足 MAPI 子系统。 这意味着组合的服务提供程序中的各个部分应相互交互的模拟他们通常必须与未使用的 MAPI 子系统的部件的交互方式。
    
- 紧密耦合的服务提供商进行交互时与其他 MAPI 组件，它们必须仍与之交互完全那样如果它们不紧密结合在一起。 例如，如果用户为其默认邮件存储区使用组合的消息存储提供程序和传输提供程序，但使用不同的传输提供程序将邮件发送 — 为用户在旅途中采用计算机，并将切换到远程传输 pr 时可以执行ovider — 紧密耦合的服务提供商的消息存储部分仍必须与 MAPI 后台处理程序交互就好像它是独立消息存储提供程序。
    
## <a name="see-also"></a>另请参阅



[开发 MAPI 消息存储提供程序](developing-a-mapi-message-store-provider.md)

