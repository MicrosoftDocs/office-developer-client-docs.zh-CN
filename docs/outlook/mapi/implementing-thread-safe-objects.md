---
title: 实现线程安全对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3c911694-b953-4d35-9a3a-22c17cfd79bc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9160136542c7960bad0be2423872171b17d99fe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310036"
---
# <a name="implementing-thread-safe-objects"></a>实现线程安全对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过直接从接口方法调用返回的对象, 提供程序负责确保线程安全。 使用 callback 对象时, 客户端应用程序的责任是客户端应用程序的责任。
  
客户端可以通过调用 MAPI 实用工具[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)来实现线程安全的通知回调。 **HrThisThreadAdviseSink**将非线程安全的通知接收器转换为线程安全的通知接收器。 对于进度回调, 没有这样的实用工具。 客户端可以选择使用 MAPI 线程安全的进度对象或手动创建一个。 
  
线程安全对象可能也可能不会有线程感知。 线程感知对象为使用它的每个线程维护单独的上下文。 服务提供程序不需要在其线程安全对象中支持线程感知, 但在某些情况下支持线程感知非常有用。 两个 MAPI 表始终按定义提供自己的上下文。 一个表在不同的线程中使用并不应提供唯一的上下文。
  
客户端可以选择在用于**MAPIInitialize**呼叫的同一线程上接收通知, 在用于**通知**调用的同一线程上, 或在 MAPI 拥有的单独线程上接收通知。 若要确保通知到达用于调用**MAPIInitialize**的同一线程, 客户端将调用[MAPIInitialize](mapiinitialize.md)并在[MAPIINIT_0](mapiinit_0.md)结构的**ulFlags**成员中传递零。 然后, 在主邮件循环期间传递通知。 
  
若要在 MAPI 拥有的线程上接收通知, 客户端将调用**MAPIInitialize** , 并将**MAPIINIT_0**结构的**ulFlags**成员设置为 MAPI_MULTITHREAD_NOTIFICATIONS。 使用客户端的建议接收器对象 (而不是包装版本) 发出**通知**调用。 
  
为了确保通知到达用于呼叫**通知**的同一线程, 客户端会调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)并将新创建的包装建议接收器传递给**通知**, 而不是原始的通知接收器。 可以使用任意一个标志值调用**MAPIInitialize** 。 
  

