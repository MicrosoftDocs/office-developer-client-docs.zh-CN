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
# <a name="handling-notifications"></a><span data-ttu-id="7197f-103">处理通知</span><span class="sxs-lookup"><span data-stu-id="7197f-103">Handling notifications</span></span>

<span data-ttu-id="7197f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7197f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7197f-105">通知使一个对象可以通知另一个对象它已完成更改。</span><span class="sxs-lookup"><span data-stu-id="7197f-105">Notifications enable one object to inform another object that it has undergone a change.</span></span> <span data-ttu-id="7197f-106">更改类型称为事件。</span><span class="sxs-lookup"><span data-stu-id="7197f-106">The type of change is referred to as an event.</span></span> <span data-ttu-id="7197f-107">MAPI 定义了将为其生成通知的多个事件。</span><span class="sxs-lookup"><span data-stu-id="7197f-107">MAPI defines several events for which notifications are generated.</span></span> 
  
<span data-ttu-id="7197f-108">客户端通常为一个或多个对象注册一个或多个事件。</span><span class="sxs-lookup"><span data-stu-id="7197f-108">Clients typically register for one or more events with one or more objects.</span></span> <span data-ttu-id="7197f-109">这些对象称为 "建议源"。</span><span class="sxs-lookup"><span data-stu-id="7197f-109">These objects are referred to as advise sources.</span></span> <span data-ttu-id="7197f-110">可充当通知源的对象包括 session 对象、MAPI 的控制或服务提供商创建的对象 (如邮件)。</span><span class="sxs-lookup"><span data-stu-id="7197f-110">Objects that can act as advise sources include the session object, under MAPI's control, or an object created by a service provider, such as a message.</span></span> <span data-ttu-id="7197f-111">被告知的对象 (称为 "通知接收器") 包含[IMAPIAdviseSink: iunknown](imapiadvisesinkiunknown.md)接口或[IMAPIViewAdviseSink: iunknown](imapiviewadvisesinkiunknown.md)接口的实现, 并且在客户端应用程序中。</span><span class="sxs-lookup"><span data-stu-id="7197f-111">The informed object, referred to as the advise sink, contains either an implementation of the [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface or the [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md) interface and is within a client application.</span></span> 
  
<span data-ttu-id="7197f-112">建议源对象实现一个由客户端调用以注册通知的**advise**方法和一个**Unadvise**方法, 该方法将被调用以取消注册。</span><span class="sxs-lookup"><span data-stu-id="7197f-112">Advise source objects implement an **Advise** method, which is called by clients to register for notifications, and an **Unadvise** method, which is called to cancel a registration.</span></span> <span data-ttu-id="7197f-113">**建议**的参数之一是指向**IMAPIAdviseSink**或 \* \* IMAPIViewAdviseSink \* \* 的实现的指针。</span><span class="sxs-lookup"><span data-stu-id="7197f-113">One of the parameters to **Advise** is a pointer to an implementation of **IMAPIAdviseSink** or \*\* IMAPIViewAdviseSink \*\*.</span></span> <span data-ttu-id="7197f-114">建议源缓存此指针, 以便在发生更改时可以调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)或**IMAPIViewAdviseSink**中的一个方法。</span><span class="sxs-lookup"><span data-stu-id="7197f-114">The advise source caches this pointer so that it can call [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) or one of the methods in **IMAPIViewAdviseSink** when a change occurs.</span></span> 
  
<span data-ttu-id="7197f-115">由于接收通知使用户能够查看最新信息, 因此建议所有客户端都注册并处理通知。</span><span class="sxs-lookup"><span data-stu-id="7197f-115">Because receiving notifications enables users to view the most up-to-date information, it is recommended that all clients register for and handle notifications.</span></span> <span data-ttu-id="7197f-116">但是, 它是可选的。</span><span class="sxs-lookup"><span data-stu-id="7197f-116">However, it is optional.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7197f-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="7197f-117">In this section</span></span>

- <span data-ttu-id="7197f-118">[注册通知](registering-for-a-notification.md): 介绍如何在初始化过程中将客户端注册为通知。</span><span class="sxs-lookup"><span data-stu-id="7197f-118">[Registering for a Notification](registering-for-a-notification.md): Describes how to register a client for notifications as a part of its initialization process.</span></span>
    
- <span data-ttu-id="7197f-119">[取消通知](canceling-a-notification.md): 介绍如何取消对通知的订阅。</span><span class="sxs-lookup"><span data-stu-id="7197f-119">[Canceling a Notification](canceling-a-notification.md): Describes how to cancel a subscription to a notification.</span></span>
    
- <span data-ttu-id="7197f-120">[处理邮件存储区通知](handling-message-store-notification.md): 介绍如何注册邮件存储通知。</span><span class="sxs-lookup"><span data-stu-id="7197f-120">[Handling Message Store Notification](handling-message-store-notification.md): Describes how to register for message store notifications.</span></span>
    
- <span data-ttu-id="7197f-121">[处理通讯簿通知](handing-address-book-notification.md): 介绍如何注册和处理通讯簿通知。</span><span class="sxs-lookup"><span data-stu-id="7197f-121">[Handing Address Book Notification](handing-address-book-notification.md): Describes how to register for and handle address book notifications.</span></span>
    
- <span data-ttu-id="7197f-122">[处理表通知](handling-table-notification.md): 介绍如何注册来自层次结构表的通知。</span><span class="sxs-lookup"><span data-stu-id="7197f-122">[Handling Table Notification](handling-table-notification.md): Describes how to register for notifications from the hierarchy table.</span></span>
    
- <span data-ttu-id="7197f-123">[实现 "建议接收器" 对象](implementing-an-advise-sink-object.md): 介绍如何实现建议接收器对象。</span><span class="sxs-lookup"><span data-stu-id="7197f-123">[Implementing an Advise Sink Object](implementing-an-advise-sink-object.md): Describes how to implement an advise sink object.</span></span>
    
- <span data-ttu-id="7197f-124">[对通知计时](timing-a-notification.md): 描述服务提供程序的客户端通知的计时。</span><span class="sxs-lookup"><span data-stu-id="7197f-124">[Timing a Notification](timing-a-notification.md): Describes the timing of client notification by service providers.</span></span>
    
- <span data-ttu-id="7197f-125">[确保线程安全通知](ensuring-a-thread-safe-notification.md): 介绍了如何确保 MAPI 的线程安全通知。</span><span class="sxs-lookup"><span data-stu-id="7197f-125">[Ensuring a Thread-Safe Notification](ensuring-a-thread-safe-notification.md): Describes how to ensure thread-safe notification with MAPI.</span></span>
    
- <span data-ttu-id="7197f-126">[强制通知](forcing-a-notification.md): 介绍如何在 MAPI 中强制发出通知。</span><span class="sxs-lookup"><span data-stu-id="7197f-126">[Forcing a Notification](forcing-a-notification.md): Describes how to force a notification in MAPI.</span></span>
    

