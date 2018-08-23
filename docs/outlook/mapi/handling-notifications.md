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
ms.openlocfilehash: 4c19e88ac1cfb29a9841ec78516410e23b3e5403
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567578"
---
# <a name="handling-notifications"></a><span data-ttu-id="8bdba-103">处理通知</span><span class="sxs-lookup"><span data-stu-id="8bdba-103">Handling notifications</span></span>

<span data-ttu-id="8bdba-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8bdba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8bdba-105">通知启用一个对象，告知另一个对象，它已经过更改。</span><span class="sxs-lookup"><span data-stu-id="8bdba-105">Notifications enable one object to inform another object that it has undergone a change.</span></span> <span data-ttu-id="8bdba-106">更改类型称为事件。</span><span class="sxs-lookup"><span data-stu-id="8bdba-106">The type of change is referred to as an event.</span></span> <span data-ttu-id="8bdba-107">MAPI 定义为其生成通知的多个事件。</span><span class="sxs-lookup"><span data-stu-id="8bdba-107">MAPI defines several events for which notifications are generated.</span></span> 
  
<span data-ttu-id="8bdba-108">客户端通常与一个或多个对象的一个或多个事件注册。</span><span class="sxs-lookup"><span data-stu-id="8bdba-108">Clients typically register for one or more events with one or more objects.</span></span> <span data-ttu-id="8bdba-109">这些对象被指告知源。</span><span class="sxs-lookup"><span data-stu-id="8bdba-109">These objects are referred to as advise sources.</span></span> <span data-ttu-id="8bdba-110">对象的可用作告知源包括 MAPI 的控件或服务提供程序，如一条消息创建对象下的会话对象。</span><span class="sxs-lookup"><span data-stu-id="8bdba-110">Objects that can act as advise sources include the session object, under MAPI's control, or an object created by a service provider, such as a message.</span></span> <span data-ttu-id="8bdba-111">称为通知接收器的明智的对象包含的任一实现[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)界面或[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口，并位于客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="8bdba-111">The informed object, referred to as the advise sink, contains either an implementation of the [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface or the [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md) interface and is within a client application.</span></span> 
  
<span data-ttu-id="8bdba-112">Advise 源对象实现**Advise**方法，由客户端注册通知调用，该方法和**Unadvise**方法，调用取消注册。</span><span class="sxs-lookup"><span data-stu-id="8bdba-112">Advise source objects implement an **Advise** method, which is called by clients to register for notifications, and an **Unadvise** method, which is called to cancel a registration.</span></span> <span data-ttu-id="8bdba-113">向**Advise**参数之一是实现**IMAPIAdviseSink**指针或 * * IMAPIViewAdviseSink * *。</span><span class="sxs-lookup"><span data-stu-id="8bdba-113">One of the parameters to **Advise** is a pointer to an implementation of **IMAPIAdviseSink** or ** IMAPIViewAdviseSink **.</span></span> <span data-ttu-id="8bdba-114">Advise 源缓存此指针，以便它可以调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)或方法之一**IMAPIViewAdviseSink**中发生更改时。</span><span class="sxs-lookup"><span data-stu-id="8bdba-114">The advise source caches this pointer so that it can call [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) or one of the methods in **IMAPIViewAdviseSink** when a change occurs.</span></span> 
  
<span data-ttu-id="8bdba-115">因为接收通知使用户能够查看的最新信息，建议所有客户端注册和处理通知。</span><span class="sxs-lookup"><span data-stu-id="8bdba-115">Because receiving notifications enables users to view the most up-to-date information, it is recommended that all clients register for and handle notifications.</span></span> <span data-ttu-id="8bdba-116">但是，它是可选的。</span><span class="sxs-lookup"><span data-stu-id="8bdba-116">However, it is optional.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8bdba-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="8bdba-117">In this section</span></span>

- <span data-ttu-id="8bdba-118">[注册的通知](registering-for-a-notification.md)： 介绍如何将通知客户端注册为其初始化过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="8bdba-118">[Registering for a Notification](registering-for-a-notification.md): Describes how to register a client for notifications as a part of its initialization process.</span></span>
    
- <span data-ttu-id="8bdba-119">[取消通知](canceling-a-notification.md)： 介绍如何取消订阅通知。</span><span class="sxs-lookup"><span data-stu-id="8bdba-119">[Canceling a Notification](canceling-a-notification.md): Describes how to cancel a subscription to a notification.</span></span>
    
- <span data-ttu-id="8bdba-120">[处理消息存储通知](handling-message-store-notification.md)： 介绍如何注册消息存储通知。</span><span class="sxs-lookup"><span data-stu-id="8bdba-120">[Handling Message Store Notification](handling-message-store-notification.md): Describes how to register for message store notifications.</span></span>
    
- <span data-ttu-id="8bdba-121">[向通讯簿通知](handing-address-book-notification.md)： 介绍如何注册和处理地址簿通知。</span><span class="sxs-lookup"><span data-stu-id="8bdba-121">[Handing Address Book Notification](handing-address-book-notification.md): Describes how to register for and handle address book notifications.</span></span>
    
- <span data-ttu-id="8bdba-122">[处理表通知](handling-table-notification.md)： 介绍如何注册层次结构表中的通知。</span><span class="sxs-lookup"><span data-stu-id="8bdba-122">[Handling Table Notification](handling-table-notification.md): Describes how to register for notifications from the hierarchy table.</span></span>
    
- <span data-ttu-id="8bdba-123">[实现接收器告知对象](implementing-an-advise-sink-object.md)： 介绍如何实现接收器 advise 对象。</span><span class="sxs-lookup"><span data-stu-id="8bdba-123">[Implementing an Advise Sink Object](implementing-an-advise-sink-object.md): Describes how to implement an advise sink object.</span></span>
    
- <span data-ttu-id="8bdba-124">[计时通知](timing-a-notification.md)： 描述服务提供商的客户端通知的执行时间。</span><span class="sxs-lookup"><span data-stu-id="8bdba-124">[Timing a Notification](timing-a-notification.md): Describes the timing of client notification by service providers.</span></span>
    
- <span data-ttu-id="8bdba-125">[确保线程安全通知](ensuring-a-thread-safe-notification.md)： 介绍如何确保与 MAPI 线程安全通知。</span><span class="sxs-lookup"><span data-stu-id="8bdba-125">[Ensuring a Thread-Safe Notification](ensuring-a-thread-safe-notification.md): Describes how to ensure thread-safe notification with MAPI.</span></span>
    
- <span data-ttu-id="8bdba-126">[强制通知](forcing-a-notification.md)： 描述如何强制 MAPI 中的通知。</span><span class="sxs-lookup"><span data-stu-id="8bdba-126">[Forcing a Notification](forcing-a-notification.md): Describes how to force a notification in MAPI.</span></span>
    

