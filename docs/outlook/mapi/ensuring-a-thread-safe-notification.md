---
title: 确保线程安全通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d46ce99a-4d7f-45b0-ba21-154498c15775
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 88c58d14893f2ac561dc56441eb38b7f4bd0db32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316582"
---
# <a name="ensuring-a-thread-safe-notification"></a><span data-ttu-id="ec9ac-103">确保线程安全通知</span><span class="sxs-lookup"><span data-stu-id="ec9ac-103">Ensuring a Thread-Safe Notification</span></span>

  
  
<span data-ttu-id="ec9ac-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec9ac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec9ac-105">如果您的客户端在多线程平台上运行, 您可能需要确保对[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的调用在特定的线程上出现。</span><span class="sxs-lookup"><span data-stu-id="ec9ac-105">If your client runs on a multithreaded platform, you may need assurance that calls to your [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) methods occur on a particular thread.</span></span> <span data-ttu-id="ec9ac-106">由于对**OnNotify**的调用通常会在任何线程上发生, 因此可以在意外和不需要的线程上接收通知, 从而导致难以调试的错误。</span><span class="sxs-lookup"><span data-stu-id="ec9ac-106">Because calls to **OnNotify** can typically occur on any thread, it is possible to receive notifications on unexpected and unwanted threads, leading to errors that are difficult to debug.</span></span> 
  
<span data-ttu-id="ec9ac-107">若要确保对用于通知调用的同一线程发出特定通知的**OnNotify**调用, 请先调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)再调用**建议**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ec9ac-107">To guarantee that calls to **OnNotify** for a particular notification are made on the same thread that was used for the **Advise** call, call [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) before calling **Advise**.</span></span> <span data-ttu-id="ec9ac-108">\* \* \* \* HrThisThreadAdviseSink \* \* \* \* 从您的建议接收器对象创建一个新的通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="ec9ac-108">\*\* \*\*HrThisThreadAdviseSink\*\*\*\* creates a new advise sink object from your advise sink object.</span></span> <span data-ttu-id="ec9ac-109">在调用中将此新对象传递给 "**建议**"。</span><span class="sxs-lookup"><span data-stu-id="ec9ac-109">Pass this new object in the call to **Advise**.</span></span> <span data-ttu-id="ec9ac-110">如果所有客户端的建议接收器对象可能无法在特定线程的上下文外部运行, 则应始终使用**HrThisThreadAdviseSink**创建的通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="ec9ac-110">All clients with advise sink objects that might not work outside the context of a particular thread should always register advise sink objects created with **HrThisThreadAdviseSink**.</span></span>
  

