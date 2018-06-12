---
title: 确保线程安全通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d46ce99a-4d7f-45b0-ba21-154498c15775
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 70e594057f2d654e0527b0caa0951e44842df809
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774873"
---
# <a name="ensuring-a-thread-safe-notification"></a><span data-ttu-id="cbad1-103">确保线程安全通知</span><span class="sxs-lookup"><span data-stu-id="cbad1-103">Ensuring a Thread-Safe Notification</span></span>

  
  
<span data-ttu-id="cbad1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cbad1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cbad1-105">如果在多线程平台上运行您的客户端，您可能需要对[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法的调用发生在特定线程的保证。</span><span class="sxs-lookup"><span data-stu-id="cbad1-105">If your client runs on a multithreaded platform, you may need assurance that calls to your [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) methods occur on a particular thread.</span></span> <span data-ttu-id="cbad1-106">因为调用**OnNotify**通常可以在任何线程上发生，就可以接收通知意外和不需要的线程，从而导致难以调试的错误。</span><span class="sxs-lookup"><span data-stu-id="cbad1-106">Because calls to **OnNotify** can typically occur on any thread, it is possible to receive notifications on unexpected and unwanted threads, leading to errors that are difficult to debug.</span></span> 
  
<span data-ttu-id="cbad1-107">若要保证**Advise**时使用的同一线程呼叫，请调用**Advise**之前调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md) ，所做的一个特定的通知调用**OnNotify** 。</span><span class="sxs-lookup"><span data-stu-id="cbad1-107">To guarantee that calls to **OnNotify** for a particular notification are made on the same thread that was used for the **Advise** call, call [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) before calling **Advise**.</span></span> <span data-ttu-id="cbad1-108">\* \* \* \* HrThisThreadAdviseSink \*\*\* 从 advise 接收器对象创建一个新的 advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="cbad1-108">** **HrThisThreadAdviseSink**** creates a new advise sink object from your advise sink object.</span></span> <span data-ttu-id="cbad1-109">将此新对象传递对**Advise**的调用中。</span><span class="sxs-lookup"><span data-stu-id="cbad1-109">Pass this new object in the call to **Advise**.</span></span> <span data-ttu-id="cbad1-110">所有客户端应始终注册可能无法运行的特定主题的上下文之外的对象的通知接收器建议使用**HrThisThreadAdviseSink**创建接收器对象。</span><span class="sxs-lookup"><span data-stu-id="cbad1-110">All clients with advise sink objects that might not work outside the context of a particular thread should always register advise sink objects created with **HrThisThreadAdviseSink**.</span></span>
  

