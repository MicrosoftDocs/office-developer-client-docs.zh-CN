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
  
由于支持事件通知可能很复杂, 因此 MAPI 提供了三个支持对象方法来实现过程中最困难的部分。 这些方法可用作一个单元, 提供程序必须使用全部三个或全部三个。
  
MAPI 支持方法使用通知密钥来管理通知接收器与生成通知的对象之间的连接。 通知密钥是一个[NOTIFKEY](notifkey.md)结构, 其中包含用于在各个进程之间标识对象的二进制数据。 通知密钥通常是从通知源对象的长期条目标识符中复制的。 如果客户端在调用中提供了一个条目标识符, **** 则可以将其用于通知密钥。 如果**建议**的_lpEntryID_参数为 NULL, 则使用最外面的容器对象 (如邮件存储) 的条目标识符。 
  
若要使用支持方法, 请在客户端呼叫您的**Advise**方法以注册通知时, 调用[IMAPISupport:: 订阅](imapisupport-subscribe.md)。 为您的通知源对象分配一个[NOTIFKEY](notifkey.md)结构并创建一个唯一的通知密钥。 例如, 接收到特定文件夹中的邮件时, 系统会提示通知客户端的邮件存储提供程序会为该文件夹创建一个通知密钥。 在要**订阅**的调用中传递指向**NOTIFKEY**结构的指针, 并将指针指向客户端的通知接收器。 **订阅**呼叫通知接收器的[IUnknown:: AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法增加其引用计数和 MAPI 将保留指针, 直到取消注册。 
  
您可以传递 NOTIFY_SYNC 标志来**订阅****通知**同步运行的请求, 而不会返回, 直到对已注册的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法进行了所有调用。 仅为自己的内部使用设置此标志。 当您响应客户端**通知**调用时, 请不要设置它。 客户端和提供程序之间的事件通知始终是异步的。 也就是说, MAPI 可确保发生事件时的调用在发出任何**OnNotify**调用之前返回到客户端。 
  
如果设置了 NOTIFY_SYNC 标志, 请勿对任何建议接收器对象进行任何更改, 并且不会传递由[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)创建的包装建议接收器来进行**订阅**。 **HrThisThreadAdviseSink**创建建议接收器的线程安全版本, 仅用于异步通知。 
  
如果为同步通知注册的通知接收器从设置了 CALLBACK_DISCONTINUE 标志的**OnNotify**返回, 则[IMAPISupport:: Notify](imapisupport-notify.md)将设置 NOTIFY_CANCELED 标志并返回, 而不会对**OnNotify**进行任何调用。 
  
**订阅**返回后, 您将不再需要在客户端的通知接收器副本上保留。 调用其[IUnknown:: release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法将其释放。 **订阅**返回应返回到客户端的非零连接号码。 连接号码代表通知源和通知接收器之间的链接。 在客户端成功调用**Unadvise**之前, 它将一直保持有效。 
  
当客户端准备好取消注册时, 它会调用您的**Unadvise**方法。 将连接号码从**Unadvise**调用传递到[IMAPISupport:: 退订](imapisupport-unsubscribe.md)。 **取消订阅**将呼叫通知接收器的**IUnknown:: Release**方法。 与**建议**和**Unadvise**一样,**订阅**和**取消订阅**的呼叫必须配对。 您必须对要**订阅**的每个呼叫发出一个**取消订阅**的调用。 但是, 每次调用您的**Advise**方法时, 不必调用**订阅**。 相反, 您可以调用它来设置内部通知。 
  
在事件发生时, 分配适用于事件的类型的一个或多个[通知](notification.md)结构, 并调用[IMAPISupport:: Notify](imapisupport-notify.md)。 **通知**为每个已注册的建议接收器生成一个通知。 应将[通知](notification.md)结构的所有未使用成员设置为零。 这种初始化**通知**结构的技术可以帮助客户端创建更小、更快速且不易出错的**OnNotify**实现。 
  
请注意, 每个事件都需要单独的**通知**结构, 即使是同一类型的多个事件也是如此。 例如, 如果为特定表上的表通知注册了三个客户端, 并且向表中添加了五行, 则必须为**通知**调用创建五个**OBJECT_NOTIFICATION**结构。 这样的批处理通知导致性能优于呼叫**通知**五次。 对于每个**通知**呼叫, MAPI 都会调用每个已注册的建议接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。 如果没有已注册的建议接收器, MAPI 将忽略该呼叫。 
  
发送成批通知的服务提供程序必须对其进行排序, 以便可以将其从第一个通知解释为最后一个通知。 当通知批处理包含一系列事件 (如 TABLE_ROW_ADDED) 时, 尤其需要此排序, 该事件引用在同一批次中的另一个事件中添加的之前的行。
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

