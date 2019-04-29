---
title: 对通知计时
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6981a3b0-96eb-44a2-b051-1c5efc70e9e3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fa3b155820c64ff55e324c5611eed7348cb93e2b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411146"
---
# <a name="timing-a-notification"></a>对通知计时

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
由于事件通知是一个异步过程, 因此您可以随时收到通知, 而不一定会在事件发生后立即收到通知。
  
 对[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的调用的计时取决于实现建议源的服务提供程序。 服务提供商可以通知客户端: 
  
- 同时处理事件。
    
- 直接在事件之后。
    
- 在稍后的事件发生之后, 可能在**Unadvise**调用之后执行此步骤。 
    
大多数服务提供程序在负责事件的 MAPI 方法返回到其调用方之后, 调用**OnNotify** 。 例如, 在保存对邮件的更改时、在[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用之后或在邮件被释放时 ( **IUnknown:: Release**调用之后), 会发送有关邮件的通知。 在发送通知之前, 邮件存储区中不显示任何更改。 
  
在调用**Unadvise**以取消注册后, 可以从建议源接收通知。 请确保仅在其引用计数降到零之后发布通知接收器, 而不是在成功的**Unadvise**调用之后发布。 请勿假定您已调用**Unadvise** , 通知接收器不再需要。 
  

