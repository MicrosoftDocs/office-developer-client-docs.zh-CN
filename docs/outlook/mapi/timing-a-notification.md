---
title: 为通知计时
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6981a3b0-96eb-44a2-b051-1c5efc70e9e3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b4b0292ab16eabe30755fe84885a29fb8e3ce295
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595193"
---
# <a name="timing-a-notification"></a><span data-ttu-id="03809-103">为通知计时</span><span class="sxs-lookup"><span data-stu-id="03809-103">Timing a Notification</span></span>

  
  
<span data-ttu-id="03809-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="03809-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="03809-105">因为事件通知是一个异步过程，可以通知您在任何时候，不必在事件发生后立即。</span><span class="sxs-lookup"><span data-stu-id="03809-105">Because event notification is an asynchronous process, you can be notified at any time, not necessarily immediately after the event has occurred.</span></span>
  
 <span data-ttu-id="03809-106">[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法调用的计时服务提供商实现 advise 源而异。</span><span class="sxs-lookup"><span data-stu-id="03809-106">The timing of calls to your [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method varies depending on the service provider implementing the advise source.</span></span> <span data-ttu-id="03809-107">服务提供商可以也通知您的客户端：</span><span class="sxs-lookup"><span data-stu-id="03809-107">Service providers can notify your client either:</span></span> 
  
- <span data-ttu-id="03809-108">同时与该事件。</span><span class="sxs-lookup"><span data-stu-id="03809-108">Simultaneously with the event.</span></span>
    
- <span data-ttu-id="03809-109">直接后事件。</span><span class="sxs-lookup"><span data-stu-id="03809-109">Directly after the event.</span></span>
    
- <span data-ttu-id="03809-110">某些更高版本指向该事件，以下可能后**Unadvise**呼叫。</span><span class="sxs-lookup"><span data-stu-id="03809-110">At some later point following the event, possibly after an **Unadvise** call.</span></span> 
    
<span data-ttu-id="03809-111">大多数服务提供商调用**OnNotify**后负责事件 MAPI 方法已返回到其呼叫者。</span><span class="sxs-lookup"><span data-stu-id="03809-111">Most service providers call **OnNotify** after the MAPI method responsible for the event has returned to its caller.</span></span> <span data-ttu-id="03809-112">例如，通知邮件发送到邮件将更改保存之后[IMAPIProp::SaveChanges](imapiprop-savechanges.md)呼叫, 时或释放邮件时， **IUnknown::Release**呼叫之后。</span><span class="sxs-lookup"><span data-stu-id="03809-112">For example, notifications on messages are sent either when changes to the message are saved, after the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call, or when the message is released, after the **IUnknown::Release** call.</span></span> <span data-ttu-id="03809-113">发送通知，直到不是可见消息存储库中的任何更改。</span><span class="sxs-lookup"><span data-stu-id="03809-113">Until the notification is sent, no changes are visible in the message store.</span></span> 
  
<span data-ttu-id="03809-114">在调用**Unadvise**取消注册后，您可以从 advise 源收到通知。</span><span class="sxs-lookup"><span data-stu-id="03809-114">You can receive notifications from an advise source after you have called **Unadvise** to cancel a registration.</span></span> <span data-ttu-id="03809-115">请务必仅后引用计数具有不为零，没有关注成功**Unadvise**调用释放通知接收器。</span><span class="sxs-lookup"><span data-stu-id="03809-115">Be sure to release your advise sink only after its reference count has fallen to zero, not following a successful **Unadvise** call.</span></span> <span data-ttu-id="03809-116">不要假定，因为您以前呼叫过**Unadvise**的通知接收器不再需要。</span><span class="sxs-lookup"><span data-stu-id="03809-116">Do not assume that because you have called **Unadvise** that the advise sink is no longer necessary.</span></span> 
  

