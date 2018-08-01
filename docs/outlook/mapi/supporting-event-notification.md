---
title: 支持事件通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1e3e49c-8d1d-4f7e-ba5a-be441f0f10ae
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 45bfe9f9314a154bd5f096ac20f76f6bf4f259c3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778889"
---
# <a name="supporting-event-notification"></a>支持事件通知

  
  
**适用于**： Outlook 
  
支持事件通知可能非常复杂，因为 MAPI 提供三种支持对象方法的实现过程的最刁钻部分。 这些方法都作为一个单元，并提供程序必须使用所有这三个或其中任何一个。
  
MAPI 支持方法使用通知键管理 advise 接收器生成通知的对象之间的连接。 通知密钥是包含跨进程标识对象的二进制数据的[NOTIFKEY](notifkey.md)结构。 从 advise 源对象的长期条目标识符通常复制通知键。 如果客户端有提供对**Advise**的调用中的项标识符，您可以将其用于通知键。 如果**Advise** _lpEntryID_参数为 NULL，则使用条目标识符圆周可能容器对象，如消息存储库。 
  
若要使用的支持方法，调用[IMAPISupport::Subscribe](imapisupport-subscribe.md)每当客户端调用注册通知您**Advise**方法。 分配[NOTIFKEY](notifkey.md)结构并创建 advise 源对象的唯一通知键。 例如，提示到特定文件夹时收到一条消息，通知客户端的消息存储提供程序创建该文件夹的通知键。 **NOTIFKEY**结构以及指向客户端的**Subscribe**的调用中传递一个指针建议接收器。 **Subscribe**调用通知接收器[IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法来增加引用计数和 MAPI 保留指针，直到被取消注册。 
  
您可以传递 NOTIFY_SYNC 标志给**Subscribe**请求**Notify**行为同步，而不返回直到它所做的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法的所有呼叫注册告知接收器。 设置仅供内部使用此标志。 响应客户端**Advise**呼叫时，不要设置它。 客户端和提供程序之间的事件通知始终是异步的。 即 MAPI 保证的呼叫期间事件发生之前所做的任何**OnNotify**呼叫将返回到客户端。 
  
如果您设置 NOTIFY_SYNC 标志，不到任何 advise 接收器对象，进行任何更改，并且不向传递到**Subscribe** [HrThisThreadAdviseSink](hrthisthreadadvisesink.md)创建包装通知接收器。 **HrThisThreadAdviseSink**创建通知接收器用于仅异步通知的线程安全版本。 
  
如果设置了 CALLBACK_DISCONTINUE 标志情况下，为同步通知注册通知接收器返回从**OnNotify** ， [IMAPISupport::Notify](imapisupport-notify.md)设置 NOTIFY_CANCELED 标志，并返回不做任何调用**OnNotify**。 
  
一旦返回了**订阅**，将不再能够留副本的任何需要客户端的建议接收器。 调用其释放其[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法。 **Subscribe**返回非零值的连接数应返回到客户端。 连接的编号代表 advise 源和通知接收器之间的链接。 它在客户端调用成功**Unadvise**才有效。 
  
已准备好取消注册客户端时，它将调用您**Unadvise**方法。 从[IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md) **Unadvise**调用传递连接数。 **取消**呼叫通知接收器**IUnknown::Release**方法。 如同**Advise**和**Unadvise**，必须配对**Subscribe**和**Unsubscribe**调用。 您必须进行一次调用**取消**对**订阅**每个呼叫。 但是，不需要每次调用**Advise**方法调用**订阅**。 相反，您可以设置内部通知调用它。 
  
事件发生时，分配适当的事件类型的一个或多个[通知](notification.md)结构，并调用[IMAPISupport::Notify](imapisupport-notify.md)。 **Notify**生成通知的每个已注册的通知接收器。 应设置未使用的所有成员的[通知](notification.md)结构为零。 此方法用于初始化**通知**结构可帮助更快，并减少出错**OnNotify**实现创建较短的客户端。 
  
请注意，单独的**通知**结构所必需的每个事件，即使的相同类型的多个事件。 例如，如果五个行添加到表三个客户端注册的特定表的表通知，您必须为**Notify**呼叫创建五个**OBJECT_NOTIFICATION**结构。 批处理通知如这比调用**Notify**五次更好的性能结果。 对于每个**通知**调用，MAPI 调用的每个已注册的通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。 如果有无注册告知接收器，MAPI 忽略呼叫。 
  
发送批处理的通知的服务提供商必须订购它们，以便他们可以到最后一解释从第一个通知。 这种排序时，尤其是必要通知批处理包含一系列事件，如 TABLE_ROW_ADDED 与指的是以前行中的同一批次中的另一个事件已添加的一个事件。
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

