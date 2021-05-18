---
title: 支持事件通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1e3e49c-8d1d-4f7e-ba5a-be441f0f10ae
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 83c102c25b17b6769c0c676bbadd874224f75cf6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327424"
---
# <a name="supporting-event-notification"></a>支持事件通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
由于支持事件通知可能很复杂，MAPI 提供了三种支持对象方法，用于实现该过程的最困难部分。 这些方法作为一个单元工作，提供程序必须全部使用这三个或全部不使用它们。
  
MAPI 支持方法使用通知键管理通知接收器与生成通知的对象之间的连接。 通知键是 [一个 NOTIFKEY](notifkey.md) 结构，它包含跨进程标识对象的二进制数据。 通知密钥通常从建议源对象的长期条目标识符复制。 如果客户端在调用 **Advise** 时提供了条目标识符，可以将它用于通知密钥。 如果 _Advise 的 lpEntryID_ 参数为 NULL，请使用最外部可能容器对象的条目标识符，如邮件存储。  
  
若要使用支持方法，请在客户端调用 **Advise** 方法以注册通知时调用 [IMAPISupport：：Subscribe。](imapisupport-subscribe.md) 分配 [NOTIFKEY](notifkey.md) 结构，并创建建议源对象的唯一通知密钥。 例如，当邮件接收到特定文件夹时提示通知客户端的邮件存储提供程序会为此文件夹创建通知密钥。 在调用 **Subscribe** 时传递指向 **NOTIFKEY** 结构的指针以及指向客户端的建议接收器的指针。 **Subscribe** 调用通知接收器的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) 方法来增加其引用计数，MAPI 将保留指针，直到注册被取消。 
  
您可以将 NOTIFY_SYNC 标志传递到 **Subscribe** 以请求 Notify同步方式运行，并且直到它调用了已注册的建议接收器的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法后才会返回。 仅为您自己的内部使用设置此标志。 在响应客户端 Advise 调用时不要 **设置** 它。 客户端和提供程序之间的事件通知始终是异步的。 也就是说，MAPI 保证发生事件的调用将在进行任何 **OnNotify** 调用之前返回到客户端。 
  
如果设置 NOTIFY_SYNC 标志，请不要对通知接收器对象的任何更改，并且不要将 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 创建的包装器建议接收器传递给 **Subscribe**。 **HrThisThreadAdviseSink** 创建建议接收器的线程安全版本，以仅用于异步通知。 
  
如果注册为同步通知的通知接收器从设置了 CALLBACK_DISCONTINUE 标志的 **OnNotify** 返回， [则 IMAPISupport：：Notify](imapisupport-notify.md) 将设置 NOTIFY_CANCELED 标志并返回，而不对 **OnNotify** 进行任何调用。 
  
一 **旦** Subscribe 返回，你将不再需要保留客户端建议接收器的副本。 调用其 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法以释放它。 **Subscribe** 返回一个非零连接号，您应返回到客户端。 连接号代表建议源与建议接收器之间的链接。 在客户端成功调用 **Unadvise 之前，它一直有效**。 
  
当客户端准备取消注册时，它将调用 **您的 Unadvise** 方法。 将连接号从 **Unadvise** 调用传递到 [IMAPISupport：：Unsubscribe](imapisupport-unsubscribe.md)。 **Unsubscribe** 调用通知接收器的 **IUnknown：：Release** 方法。 与 **"建议"** 和" **取消订阅**"一样，对 **"订阅** "和 **"取消订阅** "的调用必须配对。 对于对 Subscribe 进行的每一次调用，都必须对 **"** 取消订阅 **"进行一次调用**。 但是，每次调用 **Advise** 方法时，都不需要调用 **Subscribe。** 相反，您可以调用它来设置内部通知。 
  
当事件发生时，分配适用于事件的类型的一个或多个 [NOTIFICATION](notification.md) 结构，并调用 [IMAPISupport：：Notify](imapisupport-notify.md)。 **Notify** 会针对每个注册的通知接收器生成一个通知。 应该将 [NOTIFICATION](notification.md) 结构的所有未使用的成员设置为零。 这种初始化 **NOTIFICATION** 结构的技术可帮助客户端创建更小、更快、更不容易出错的 **OnNotify** 实现。 
  
请注意，每个事件需要单独的 **NOTIFICATION** 结构，即使对于同一类型的多个事件也是必需的。 例如，如果为特定表上的表通知注册了三个客户端，并且向表中添加了五行，则必须为 **Notify** 调用创建 **五** OBJECT_NOTIFICATION通知结构。 与调用通知五次时类似这样的批通知可 **提高性能** 。 对于每个 **Notify** 调用，MAPI 将调用每个注册的建议接收器的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。 如果没有注册的建议接收器，MAPI 将忽略调用。 
  
发送批处理通知的服务提供商必须对它们排序，以便可以从第一个通知解释为最后一个通知。 当通知批处理包含一系列事件（如 TABLE_ROW_ADDED，其中一个事件引用了同一批次中的另一个事件中添加的上一行）时，此排序尤为必要。
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

