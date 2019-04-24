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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299383"
---
# <a name="handling-notifications"></a>处理通知

**适用于**：Outlook 2013 | Outlook 2016 
  
通知使一个对象可以通知另一个对象它已完成更改。 更改类型称为事件。 MAPI 定义了将为其生成通知的多个事件。 
  
客户端通常为一个或多个对象注册一个或多个事件。 这些对象称为 "建议源"。 可充当通知源的对象包括 session 对象、MAPI 的控制或服务提供商创建的对象 (如邮件)。 被告知的对象 (称为 "通知接收器") 包含[IMAPIAdviseSink: iunknown](imapiadvisesinkiunknown.md)接口或[IMAPIViewAdviseSink: iunknown](imapiviewadvisesinkiunknown.md)接口的实现, 并且在客户端应用程序中。 
  
建议源对象实现一个由客户端调用以注册通知的**advise**方法和一个**Unadvise**方法, 该方法将被调用以取消注册。 **建议**的参数之一是指向**IMAPIAdviseSink**或 * * IMAPIViewAdviseSink * * 的实现的指针。 建议源缓存此指针, 以便在发生更改时可以调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)或**IMAPIViewAdviseSink**中的一个方法。 
  
由于接收通知使用户能够查看最新信息, 因此建议所有客户端都注册并处理通知。 但是, 它是可选的。
  
## <a name="in-this-section"></a>本节内容

- [注册通知](registering-for-a-notification.md): 介绍如何在初始化过程中将客户端注册为通知。
    
- [取消通知](canceling-a-notification.md): 介绍如何取消对通知的订阅。
    
- [处理邮件存储区通知](handling-message-store-notification.md): 介绍如何注册邮件存储通知。
    
- [处理通讯簿通知](handing-address-book-notification.md): 介绍如何注册和处理通讯簿通知。
    
- [处理表通知](handling-table-notification.md): 介绍如何注册来自层次结构表的通知。
    
- [实现 "建议接收器" 对象](implementing-an-advise-sink-object.md): 介绍如何实现建议接收器对象。
    
- [对通知计时](timing-a-notification.md): 描述服务提供程序的客户端通知的计时。
    
- [确保线程安全通知](ensuring-a-thread-safe-notification.md): 介绍了如何确保 MAPI 的线程安全通知。
    
- [强制通知](forcing-a-notification.md): 介绍如何在 MAPI 中强制发出通知。
    

