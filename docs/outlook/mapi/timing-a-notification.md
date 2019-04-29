---
title: 对通知计时
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6981a3b0-96eb-44a2-b051-1c5efc70e9e3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fa3b155820c64ff55e324c5611eed7348cb93e2b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411146"
---
# <a name="timing-a-notification"></a><span data-ttu-id="3345f-103">对通知计时</span><span class="sxs-lookup"><span data-stu-id="3345f-103">Timing a Notification</span></span>

  
  
<span data-ttu-id="3345f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3345f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3345f-105">由于事件通知是一个异步过程, 因此您可以随时收到通知, 而不一定会在事件发生后立即收到通知。</span><span class="sxs-lookup"><span data-stu-id="3345f-105">Because event notification is an asynchronous process, you can be notified at any time, not necessarily immediately after the event has occurred.</span></span>
  
 <span data-ttu-id="3345f-106">对[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的调用的计时取决于实现建议源的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="3345f-106">The timing of calls to your [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method varies depending on the service provider implementing the advise source.</span></span> <span data-ttu-id="3345f-107">服务提供商可以通知客户端:</span><span class="sxs-lookup"><span data-stu-id="3345f-107">Service providers can notify your client either:</span></span> 
  
- <span data-ttu-id="3345f-108">同时处理事件。</span><span class="sxs-lookup"><span data-stu-id="3345f-108">Simultaneously with the event.</span></span>
    
- <span data-ttu-id="3345f-109">直接在事件之后。</span><span class="sxs-lookup"><span data-stu-id="3345f-109">Directly after the event.</span></span>
    
- <span data-ttu-id="3345f-110">在稍后的事件发生之后, 可能在**Unadvise**调用之后执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="3345f-110">At some later point following the event, possibly after an **Unadvise** call.</span></span> 
    
<span data-ttu-id="3345f-111">大多数服务提供程序在负责事件的 MAPI 方法返回到其调用方之后, 调用**OnNotify** 。</span><span class="sxs-lookup"><span data-stu-id="3345f-111">Most service providers call **OnNotify** after the MAPI method responsible for the event has returned to its caller.</span></span> <span data-ttu-id="3345f-112">例如, 在保存对邮件的更改时、在[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用之后或在邮件被释放时 ( **IUnknown:: Release**调用之后), 会发送有关邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="3345f-112">For example, notifications on messages are sent either when changes to the message are saved, after the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call, or when the message is released, after the **IUnknown::Release** call.</span></span> <span data-ttu-id="3345f-113">在发送通知之前, 邮件存储区中不显示任何更改。</span><span class="sxs-lookup"><span data-stu-id="3345f-113">Until the notification is sent, no changes are visible in the message store.</span></span> 
  
<span data-ttu-id="3345f-114">在调用**Unadvise**以取消注册后, 可以从建议源接收通知。</span><span class="sxs-lookup"><span data-stu-id="3345f-114">You can receive notifications from an advise source after you have called **Unadvise** to cancel a registration.</span></span> <span data-ttu-id="3345f-115">请确保仅在其引用计数降到零之后发布通知接收器, 而不是在成功的**Unadvise**调用之后发布。</span><span class="sxs-lookup"><span data-stu-id="3345f-115">Be sure to release your advise sink only after its reference count has fallen to zero, not following a successful **Unadvise** call.</span></span> <span data-ttu-id="3345f-116">请勿假定您已调用**Unadvise** , 通知接收器不再需要。</span><span class="sxs-lookup"><span data-stu-id="3345f-116">Do not assume that because you have called **Unadvise** that the advise sink is no longer necessary.</span></span> 
  

