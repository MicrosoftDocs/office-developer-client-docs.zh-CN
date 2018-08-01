---
title: 处理通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 451b71da-a888-4d8f-9814-12f9f846de05
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fdd66e4a27209e6b80757bcf52408eb0cea43794
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775052"
---
# <a name="handling-notifications"></a>处理通知

**适用于**： Outlook 
  
通知启用一个对象，告知另一个对象，它已经过更改。 更改类型称为事件。 MAPI 定义为其生成通知的多个事件。 
  
客户端通常与一个或多个对象的一个或多个事件注册。 这些对象被指告知源。 对象的可用作告知源包括 MAPI 的控件或服务提供程序，如一条消息创建对象下的会话对象。 称为通知接收器的明智的对象包含的任一实现[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)界面或[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口，并位于客户端应用程序。 
  
Advise 源对象实现**Advise**方法，由客户端注册通知调用，该方法和**Unadvise**方法，调用取消注册。 向**Advise**参数之一是实现**IMAPIAdviseSink**指针或 * * IMAPIViewAdviseSink * *。 Advise 源缓存此指针，以便它可以调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)或方法之一**IMAPIViewAdviseSink**中发生更改时。 
  
因为接收通知使用户能够查看的最新信息，建议所有客户端注册和处理通知。 但是，它是可选的。
  
## <a name="in-this-section"></a>本节内容

- [注册的通知](registering-for-a-notification.md)： 介绍如何将通知客户端注册为其初始化过程的一部分。
    
- [取消通知](canceling-a-notification.md)： 介绍如何取消订阅通知。
    
- [处理消息存储通知](handling-message-store-notification.md)： 介绍如何注册消息存储通知。
    
- [向通讯簿通知](handing-address-book-notification.md)： 介绍如何注册和处理地址簿通知。
    
- [处理表通知](handling-table-notification.md)： 介绍如何注册层次结构表中的通知。
    
- [实现接收器告知对象](implementing-an-advise-sink-object.md)： 介绍如何实现接收器 advise 对象。
    
- [计时通知](timing-a-notification.md)： 描述服务提供商的客户端通知的执行时间。
    
- [确保线程安全通知](ensuring-a-thread-safe-notification.md)： 介绍如何确保与 MAPI 线程安全通知。
    
- [强制通知](forcing-a-notification.md)： 描述如何强制 MAPI 中的通知。
    

