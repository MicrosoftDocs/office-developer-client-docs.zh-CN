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
ms.openlocfilehash: 2f8235caceec8b27b2b14fac26d51e9e31ce1024
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579772"
---
# <a name="implementing-thread-safe-objects"></a><span data-ttu-id="17824-103">实现线程安全对象</span><span class="sxs-lookup"><span data-stu-id="17824-103">Implementing Thread-Safe Objects</span></span>

  
  
<span data-ttu-id="17824-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17824-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="17824-105">直接从接口方法的调用返回的对象，它是以确保线程安全的提供程序的责任。</span><span class="sxs-lookup"><span data-stu-id="17824-105">With objects that are returned from interface method calls directly, it is the provider's responsibility to ensure thread-safety.</span></span> <span data-ttu-id="17824-106">回调对象，它是客户端应用程序的责任。</span><span class="sxs-lookup"><span data-stu-id="17824-106">With callback objects, it is the client application's responsibility.</span></span>
  
<span data-ttu-id="17824-107">客户端可以通过调用 MAPI 实用程序[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)实现线程安全通知回调。</span><span class="sxs-lookup"><span data-stu-id="17824-107">A client can implement a thread-safe notification callback by calling the MAPI utility [HrThisThreadAdviseSink](hrthisthreadadvisesink.md).</span></span> <span data-ttu-id="17824-108">**HrThisThreadAdviseSink**转换一个线程安全的非线程安全通知接收器。</span><span class="sxs-lookup"><span data-stu-id="17824-108">**HrThisThreadAdviseSink** transforms a non-thread-safe advise sink into a thread-safe one.</span></span> <span data-ttu-id="17824-109">用于进度回调，没有任何此类实用程序。</span><span class="sxs-lookup"><span data-stu-id="17824-109">For progress callbacks, there is no such utility.</span></span> <span data-ttu-id="17824-110">客户端可以选择使用 MAPI 线程安全进度对象或手动创建一个。</span><span class="sxs-lookup"><span data-stu-id="17824-110">A client can choose to use the MAPI thread-safe progress object or create one manually.</span></span> 
  
<span data-ttu-id="17824-111">线程安全对象，可能或者也可能线程感知。</span><span class="sxs-lookup"><span data-stu-id="17824-111">A thread-safe object might or might not also be thread-aware.</span></span> <span data-ttu-id="17824-112">线程感知对象维护单独正在使用它的每个线程上下文。</span><span class="sxs-lookup"><span data-stu-id="17824-112">A thread-aware object maintains a separate context for every thread that is using it.</span></span> <span data-ttu-id="17824-113">服务提供商不需要在其线程安全对象，支持线程认知虽然线程认知度的支持可在某些情况下有用。</span><span class="sxs-lookup"><span data-stu-id="17824-113">Service providers are not required to support thread-awareness in their thread-safe objects, although supporting thread-awareness can be useful in some situations.</span></span> <span data-ttu-id="17824-114">两个 MAPI 表始终提供其自己的上下文定义。</span><span class="sxs-lookup"><span data-stu-id="17824-114">Two MAPI tables always provide their own context by definition.</span></span> <span data-ttu-id="17824-115">在不同线程上使用的一个表不和不应提供唯一的上下文。</span><span class="sxs-lookup"><span data-stu-id="17824-115">One table used on different threads does not and should not provide unique context.</span></span>
  
<span data-ttu-id="17824-116">客户端可以选择接收通知**MAPIInitialize**时使用的同一线程上调用，在同一线程了用于**Advise**呼叫，或在单独的线程归 MAPI。</span><span class="sxs-lookup"><span data-stu-id="17824-116">A client can choose between receiving notifications on the same thread that was used for the **MAPIInitialize** call, on the same thread that was used for the **Advise** call, or on a separate thread owned by MAPI.</span></span> <span data-ttu-id="17824-117">若要确保通知到达用于调用**MAPIInitialize**的同一线程，客户端调用[MAPIInitialize](mapiinitialize.md) ，并传递零[MAPIINIT_0](mapiinit_0.md)结构的**ulFlags**成员中。</span><span class="sxs-lookup"><span data-stu-id="17824-117">To ensure that notifications arrive on the same thread that was used to call **MAPIInitialize**, a client calls [MAPIInitialize](mapiinitialize.md) and passes zero in the **ulFlags** member of the [MAPIINIT_0](mapiinit_0.md) structure.</span></span> <span data-ttu-id="17824-118">在主消息循环期间然后传递通知。</span><span class="sxs-lookup"><span data-stu-id="17824-118">Notifications are then delivered during the main message loop.</span></span> 
  
<span data-ttu-id="17824-119">要接收通知 MAPI 拥有线程上的，在客户端调用**MAPIInitialize**的设置为 MAPI_MULTITHREAD_NOTIFICATIONS **MAPIINIT_0**结构**ulFlags**成员。</span><span class="sxs-lookup"><span data-stu-id="17824-119">To receive notifications on the MAPI-owned thread, a client calls **MAPIInitialize** with the **ulFlags** member of the **MAPIINIT_0** structure set to MAPI_MULTITHREAD_NOTIFICATIONS.</span></span> <span data-ttu-id="17824-120">**Advise**调用与客户端的建议接收器对象，而不是包装的版本。</span><span class="sxs-lookup"><span data-stu-id="17824-120">The **Advise** call is made with the client's advise sink object rather than a wrapped version.</span></span> 
  
<span data-ttu-id="17824-121">若要确保通知到达用于调用**Advise**的同一线程，客户端调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)并将新创建自动换行建议为**Advise**接收器，而不是原始通知接收器。</span><span class="sxs-lookup"><span data-stu-id="17824-121">To ensure that notifications arrive on the same thread that was used to call **Advise**, a client calls [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) and passes the newly created wrapped advise sink to **Advise** rather than the original advise sink.</span></span> <span data-ttu-id="17824-122">任一标志值，可调用**MAPIInitialize** 。</span><span class="sxs-lookup"><span data-stu-id="17824-122">**MAPIInitialize** can be called with either flag value.</span></span> 
  

