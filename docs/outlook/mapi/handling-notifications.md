---
title: 处理通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 451b71da-a888-4d8f-9814-12f9f846de05
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e261b71a8e94d9db3b1b17168d84798dfe18955d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429157"
---
# <a name="handling-notifications"></a>处理通知

**适用于**：Outlook 2013 | Outlook 2016 
  
通知使一个对象能够通知另一个对象它已进行了更改。 更改类型称为事件。 MAPI 定义多个生成通知的事件。 
  
客户端通常使用一个或多个对象注册一个或多个事件。 这些对象称为建议源。 可以充当建议源的对象包括 MAPI 控制下的会话对象或服务提供商创建的对象（如消息）。 通知对象（称为建议接收器）包含 [IMAPIAdviseSink ： IUnknown](imapiadvisesinkiunknown.md) 接口或 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md) 接口的实现，并且位于客户端应用程序中。 
  
建议源对象实现 **一个 Advise** 方法（由客户端调用以注册通知）和一个 **Unadvise** 方法（用于取消注册）。 **Advise** 的参数之一是指向 **IMAPIAdviseSink** 或 ** IMAPIViewAdviseSink ** 的实现。 建议源缓存此指针，以便它可以在更改发生时调用 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 或 **IMAPIViewAdviseSink** 中的方法之一。 
  
由于接收通知使用户能够查看最新信息，因此建议所有客户端注册并处理通知。 但是，它是可选的。
  
## <a name="in-this-section"></a>本节内容

- [注册通知](registering-for-a-notification.md)：介绍如何将客户端注册为通知，作为初始化过程的一部分。
    
- [取消通知](canceling-a-notification.md)：介绍如何取消对通知的订阅。
    
- [处理邮件存储通知](handling-message-store-notification.md)：介绍如何注册邮件存储通知。
    
- [处理通讯簿通知](handing-address-book-notification.md)：介绍如何注册和处理通讯簿通知。
    
- [处理表通知](handling-table-notification.md)：介绍如何注册层次结构表中的通知。
    
- [Implementing an Advise Sink Object](implementing-an-advise-sink-object.md)： Describes how to implement an advise sink object.
    
- [通知计时](timing-a-notification.md)：描述服务提供商发送客户端通知的时间。
    
- [Ensure a Thread-Safe Notification](ensuring-a-thread-safe-notification.md)： Describes how to ensure thread-safe notification with MAPI.
    
- [强制通知](forcing-a-notification.md)：介绍如何在 MAPI 中强制发送通知。
    

