---
title: 实现线程安全对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3c911694-b953-4d35-9a3a-22c17cfd79bc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8c8c89f3626d54f04896ad54de5d7e480dd9b568
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775837"
---
# <a name="implementing-thread-safe-objects"></a>实现线程安全对象

  
  
**适用于**： Outlook 
  
直接从接口方法的调用返回的对象，它是以确保线程安全的提供程序的责任。 回调对象，它是客户端应用程序的责任。
  
客户端可以通过调用 MAPI 实用程序[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)实现线程安全通知回调。 **HrThisThreadAdviseSink**转换一个线程安全的非线程安全通知接收器。 用于进度回调，没有任何此类实用程序。 客户端可以选择使用 MAPI 线程安全进度对象或手动创建一个。 
  
线程安全对象，可能或者也可能线程感知。 线程感知对象维护单独正在使用它的每个线程上下文。 服务提供商不需要在其线程安全对象，支持线程认知虽然线程认知度的支持可在某些情况下有用。 两个 MAPI 表始终提供其自己的上下文定义。 在不同线程上使用的一个表不和不应提供唯一的上下文。
  
客户端可以选择接收通知**MAPIInitialize**时使用的同一线程上调用，在同一线程了用于**Advise**呼叫，或在单独的线程归 MAPI。 若要确保通知到达用于调用**MAPIInitialize**的同一线程，客户端调用[MAPIInitialize](mapiinitialize.md) ，并传递零[MAPIINIT_0](mapiinit_0.md)结构的**ulFlags**成员中。 在主消息循环期间然后传递通知。 
  
要接收通知 MAPI 拥有线程上的，在客户端调用**MAPIInitialize**的设置为 MAPI_MULTITHREAD_NOTIFICATIONS **MAPIINIT_0**结构**ulFlags**成员。 **Advise**调用与客户端的建议接收器对象，而不是包装的版本。 
  
若要确保通知到达用于调用**Advise**的同一线程，客户端调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)并将新创建自动换行建议为**Advise**接收器，而不是原始通知接收器。 任一标志值，可调用**MAPIInitialize** 。 
  

