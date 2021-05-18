---
title: 实现Thread-Safe对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3c911694-b953-4d35-9a3a-22c17cfd79bc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9160136542c7960bad0be2423872171b17d99fe3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413526"
---
# <a name="implementing-thread-safe-objects"></a>实现Thread-Safe对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对于直接从接口方法调用返回的对象，提供程序负责确保线程安全。 对于回调对象，它是客户端应用程序的责任。
  
客户端可以通过调用 MAPI 实用工具 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md)来实现线程安全通知回调。 **HrThisThreadAdviseSink** 将非线程安全建议接收器转换为线程安全建议。 对于进度回调，没有此类实用工具。 客户端可以选择使用 MAPI 线程安全进度对象或手动创建一个。 
  
线程安全对象可能是线程感知对象，也可能不是线程感知对象。 线程感知对象为使用它的每一个线程维护单独的上下文。 服务提供商不需要支持线程安全对象中的线程感知，尽管在某些情况下支持线程感知可能很有用。 两个 MAPI 表始终根据定义提供它们自己的上下文。 用于不同线程的一个表不能且不应提供唯一的上下文。
  
客户端可以选择在 **用于 MAPIInitialize** 调用的同一线程、用于 **Advise** 调用的同一线程上或 MAPI 所拥有的单独线程上接收通知。 为了确保通知到达用于调用 **MAPIInitialize** 的同一线程，客户端调用 [MAPIInitialize，](mapiinitialize.md) 在 MAPIINIT_0 结构的 **ulFlags** 成员中传递 [零](mapiinit_0.md) 。 然后，通知在主邮件循环期间传递。 
  
为了在 MAPI 所拥有的线程上接收通知，客户端调用 **MAPIInitialize，MAPIINIT_0****结构的****ulFlags** 成员设置为 MAPI_MULTITHREAD_NOTIFICATIONS。 使用客户端的建议接收对象（而不是包装的版本）进行 **Advise** 调用。 
  
为了确保通知到达用于调用 **Advise** 的同一线程上，客户端调用 [HrThisThreadAdviseSink，](hrthisthreadadvisesink.md) 将新创建的封装通知接收器传递给 **Advise，** 而不是原始的 advise 接收器。 **可以使用任一标志值调用 MAPIInitialize。** 
  

