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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413526"
---
# <a name="implementing-thread-safe-objects"></a><span data-ttu-id="aa547-103">实现线程安全对象</span><span class="sxs-lookup"><span data-stu-id="aa547-103">Implementing Thread-Safe Objects</span></span>

  
  
<span data-ttu-id="aa547-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa547-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa547-105">通过直接从接口方法调用返回的对象, 提供程序负责确保线程安全。</span><span class="sxs-lookup"><span data-stu-id="aa547-105">With objects that are returned from interface method calls directly, it is the provider's responsibility to ensure thread-safety.</span></span> <span data-ttu-id="aa547-106">使用 callback 对象时, 客户端应用程序的责任是客户端应用程序的责任。</span><span class="sxs-lookup"><span data-stu-id="aa547-106">With callback objects, it is the client application's responsibility.</span></span>
  
<span data-ttu-id="aa547-107">客户端可以通过调用 MAPI 实用工具[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)来实现线程安全的通知回调。</span><span class="sxs-lookup"><span data-stu-id="aa547-107">A client can implement a thread-safe notification callback by calling the MAPI utility [HrThisThreadAdviseSink](hrthisthreadadvisesink.md).</span></span> <span data-ttu-id="aa547-108">**HrThisThreadAdviseSink**将非线程安全的通知接收器转换为线程安全的通知接收器。</span><span class="sxs-lookup"><span data-stu-id="aa547-108">**HrThisThreadAdviseSink** transforms a non-thread-safe advise sink into a thread-safe one.</span></span> <span data-ttu-id="aa547-109">对于进度回调, 没有这样的实用工具。</span><span class="sxs-lookup"><span data-stu-id="aa547-109">For progress callbacks, there is no such utility.</span></span> <span data-ttu-id="aa547-110">客户端可以选择使用 MAPI 线程安全的进度对象或手动创建一个。</span><span class="sxs-lookup"><span data-stu-id="aa547-110">A client can choose to use the MAPI thread-safe progress object or create one manually.</span></span> 
  
<span data-ttu-id="aa547-111">线程安全对象可能也可能不会有线程感知。</span><span class="sxs-lookup"><span data-stu-id="aa547-111">A thread-safe object might or might not also be thread-aware.</span></span> <span data-ttu-id="aa547-112">线程感知对象为使用它的每个线程维护单独的上下文。</span><span class="sxs-lookup"><span data-stu-id="aa547-112">A thread-aware object maintains a separate context for every thread that is using it.</span></span> <span data-ttu-id="aa547-113">服务提供程序不需要在其线程安全对象中支持线程感知, 但在某些情况下支持线程感知非常有用。</span><span class="sxs-lookup"><span data-stu-id="aa547-113">Service providers are not required to support thread-awareness in their thread-safe objects, although supporting thread-awareness can be useful in some situations.</span></span> <span data-ttu-id="aa547-114">两个 MAPI 表始终按定义提供自己的上下文。</span><span class="sxs-lookup"><span data-stu-id="aa547-114">Two MAPI tables always provide their own context by definition.</span></span> <span data-ttu-id="aa547-115">一个表在不同的线程中使用并不应提供唯一的上下文。</span><span class="sxs-lookup"><span data-stu-id="aa547-115">One table used on different threads does not and should not provide unique context.</span></span>
  
<span data-ttu-id="aa547-116">客户端可以选择在用于**MAPIInitialize**呼叫的同一线程上接收通知, 在用于**通知**调用的同一线程上, 或在 MAPI 拥有的单独线程上接收通知。</span><span class="sxs-lookup"><span data-stu-id="aa547-116">A client can choose between receiving notifications on the same thread that was used for the **MAPIInitialize** call, on the same thread that was used for the **Advise** call, or on a separate thread owned by MAPI.</span></span> <span data-ttu-id="aa547-117">若要确保通知到达用于调用**MAPIInitialize**的同一线程, 客户端将调用[MAPIInitialize](mapiinitialize.md)并在[MAPIINIT_0](mapiinit_0.md)结构的**ulFlags**成员中传递零。</span><span class="sxs-lookup"><span data-stu-id="aa547-117">To ensure that notifications arrive on the same thread that was used to call **MAPIInitialize**, a client calls [MAPIInitialize](mapiinitialize.md) and passes zero in the **ulFlags** member of the [MAPIINIT_0](mapiinit_0.md) structure.</span></span> <span data-ttu-id="aa547-118">然后, 在主邮件循环期间传递通知。</span><span class="sxs-lookup"><span data-stu-id="aa547-118">Notifications are then delivered during the main message loop.</span></span> 
  
<span data-ttu-id="aa547-119">若要在 MAPI 拥有的线程上接收通知, 客户端将调用**MAPIInitialize** , 并将**MAPIINIT_0**结构的**ulFlags**成员设置为 MAPI_MULTITHREAD_NOTIFICATIONS。</span><span class="sxs-lookup"><span data-stu-id="aa547-119">To receive notifications on the MAPI-owned thread, a client calls **MAPIInitialize** with the **ulFlags** member of the **MAPIINIT_0** structure set to MAPI_MULTITHREAD_NOTIFICATIONS.</span></span> <span data-ttu-id="aa547-120">使用客户端的建议接收器对象 (而不是包装版本) 发出**通知**调用。</span><span class="sxs-lookup"><span data-stu-id="aa547-120">The **Advise** call is made with the client's advise sink object rather than a wrapped version.</span></span> 
  
<span data-ttu-id="aa547-121">为了确保通知到达用于呼叫**通知**的同一线程, 客户端会调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)并将新创建的包装建议接收器传递给**通知**, 而不是原始的通知接收器。</span><span class="sxs-lookup"><span data-stu-id="aa547-121">To ensure that notifications arrive on the same thread that was used to call **Advise**, a client calls [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) and passes the newly created wrapped advise sink to **Advise** rather than the original advise sink.</span></span> <span data-ttu-id="aa547-122">可以使用任意一个标志值调用**MAPIInitialize** 。</span><span class="sxs-lookup"><span data-stu-id="aa547-122">**MAPIInitialize** can be called with either flag value.</span></span> 
  

