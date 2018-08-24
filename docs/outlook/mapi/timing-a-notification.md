---
title: 为通知计时
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6981a3b0-96eb-44a2-b051-1c5efc70e9e3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b4b0292ab16eabe30755fe84885a29fb8e3ce295
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595193"
---
# <a name="timing-a-notification"></a>为通知计时

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
因为事件通知是一个异步过程，可以通知您在任何时候，不必在事件发生后立即。
  
 [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法调用的计时服务提供商实现 advise 源而异。 服务提供商可以也通知您的客户端： 
  
- 同时与该事件。
    
- 直接后事件。
    
- 某些更高版本指向该事件，以下可能后**Unadvise**呼叫。 
    
大多数服务提供商调用**OnNotify**后负责事件 MAPI 方法已返回到其呼叫者。 例如，通知邮件发送到邮件将更改保存之后[IMAPIProp::SaveChanges](imapiprop-savechanges.md)呼叫, 时或释放邮件时， **IUnknown::Release**呼叫之后。 发送通知，直到不是可见消息存储库中的任何更改。 
  
在调用**Unadvise**取消注册后，您可以从 advise 源收到通知。 请务必仅后引用计数具有不为零，没有关注成功**Unadvise**调用释放通知接收器。 不要假定，因为您以前呼叫过**Unadvise**的通知接收器不再需要。 
  

