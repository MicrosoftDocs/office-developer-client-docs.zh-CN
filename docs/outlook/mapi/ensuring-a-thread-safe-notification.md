---
title: 确保Thread-Safe通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d46ce99a-4d7f-45b0-ba21-154498c15775
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 88c58d14893f2ac561dc56441eb38b7f4bd0db32
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424845"
---
# <a name="ensuring-a-thread-safe-notification"></a><span data-ttu-id="e1d5f-103">确保Thread-Safe通知</span><span class="sxs-lookup"><span data-stu-id="e1d5f-103">Ensuring a Thread-Safe Notification</span></span>

  
  
<span data-ttu-id="e1d5f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1d5f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1d5f-105">如果客户端在多线程平台上运行，你可能需要保证对 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法的调用发生在特定线程上。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-105">If your client runs on a multithreaded platform, you may need assurance that calls to your [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) methods occur on a particular thread.</span></span> <span data-ttu-id="e1d5f-106">由于对 **OnNotify** 的调用通常可以在任何线程上发生，因此可能会接收意外和不需要的线程上的通知，从而导致难以调试的错误。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-106">Because calls to **OnNotify** can typically occur on any thread, it is possible to receive notifications on unexpected and unwanted threads, leading to errors that are difficult to debug.</span></span> 
  
<span data-ttu-id="e1d5f-107">若要保证对特定通知 **的 OnNotify** 调用在用于 **Advise** 调用的同一线程上执行，在调用 **Advise** 之前调用 [HrThisThreadAdviseSink。](hrthisthreadadvisesink.md)</span><span class="sxs-lookup"><span data-stu-id="e1d5f-107">To guarantee that calls to **OnNotify** for a particular notification are made on the same thread that was used for the **Advise** call, call [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) before calling **Advise**.</span></span> <span data-ttu-id="e1d5f-108">\*\* \*\*HrThisThreadAdviseSink\*\*\*\* 从你的建议接收器对象创建新的通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-108">\*\* \*\*HrThisThreadAdviseSink\*\*\*\* creates a new advise sink object from your advise sink object.</span></span> <span data-ttu-id="e1d5f-109">在调用 Advise 时传递此新 **对象**。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-109">Pass this new object in the call to **Advise**.</span></span> <span data-ttu-id="e1d5f-110">具有建议接收对象（这些对象可能无法在特定线程的上下文之外工作）的所有客户端应始终注册使用 **HrThisThreadAdviseSink** 创建的通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-110">All clients with advise sink objects that might not work outside the context of a particular thread should always register advise sink objects created with **HrThisThreadAdviseSink**.</span></span>
  

