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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413225"
---
# <a name="tightly-coupled-message-store-providers"></a>紧密耦合的邮件存储区提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序可与传输提供程序紧密结合。 紧密耦合 MAPI 服务提供程序是指实现两个提供程序, 以便存储提供程序和传输提供程序可以进行通信, 以使发送和接收邮件的过程更加有效。 执行此操作的好处在于, 当两个服务提供程序可以直接交互而不是通过 MAPI 后台处理程序交互时, 可能会导致性能改进。 若要将邮件存储提供程序紧密地带到传输提供程序, 传输提供程序必须将邮件存储提供程序的条目标识符放在传输提供程序的**PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性中。MAPI 状态表中的行。 这将使 MAPI 后台处理程序能够将存储提供程序连接到传输提供程序。
  
不要求邮件存储提供程序与任何其他服务提供程序紧密结合。 最常用的服务提供程序是一种传输提供程序, 与邮件存储提供程序紧密耦合。 执行此操作通常是为了能够在不涉及 MAPI 后台处理程序的情况下完成发送和接收邮件。 例如, 当用户提交传出邮件时, 组合的邮件存储提供程序和传输提供程序可以直接发送邮件。 组合服务提供程序无需先通知 mapi 后台处理程序存在要处理的新邮件, 然后等待 mapi 后台处理程序启动将邮件从邮件存储提供程序传输到传输提供程序的过程。 在使用基于服务器的邮件存储区时, 在用户计算机与服务器之间的网络通信最小化时, 这有特定优势。
  
一般情况下, 没有任何明确指定的过程可用于紧密耦合服务提供程序。 但是, 应遵循以下准则:
  
- 如果与服务提供商紧密耦合的原因是性能, 请注意, 耦合会将 MAPI 子系统的一部分从通常涉及这些部件的进程中取出。 这意味着组合服务提供程序中的各个部件应以模拟其通常与未使用的 MAPI 子系统的部件的交互方式相互进行交互。
    
- 当紧密结合的服务提供商与其他 MAPI 组件进行交互时, 它们仍必须与它们的交互方式完全结合。 例如, 如果用户使用组合邮件存储提供程序和传输提供程序作为其默认邮件存储, 但使用单独的传输提供程序发送邮件, 则在用户将计算机放在路上并切换到远程传输 pr 时可能会发生这种情况。ovider —紧耦合服务提供程序的邮件存储区部分仍必须与 MAPI 后台处理程序交互, 就像它是独立的邮件存储提供程序一样。
    
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

