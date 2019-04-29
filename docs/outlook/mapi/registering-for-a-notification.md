---
title: 注册通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 45625387-dbd2-4ca8-926b-ef87998d01d7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ccc2758b59a9227afbc50360102e793892bbdc52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424901"
---
# <a name="registering-for-a-notification"></a><span data-ttu-id="5d86e-103">注册通知</span><span class="sxs-lookup"><span data-stu-id="5d86e-103">Registering for a Notification</span></span>

  
  
<span data-ttu-id="5d86e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d86e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d86e-105">客户端可以将通讯簿或邮件存储通知注册为其初始化过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d86e-105">A client can register for address book or message store notifications as part of its initialization process.</span></span>
  
<span data-ttu-id="5d86e-106">MAPI 支持对通讯簿发出通知, 而不管通讯簿提供程序是否支持它。</span><span class="sxs-lookup"><span data-stu-id="5d86e-106">MAPI supports notification on the address book regardless of whether any of the address book providers support it.</span></span> <span data-ttu-id="5d86e-107">对邮件存储区的通知支持取决于特定的邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="5d86e-107">Support for notification on message stores depends on the particular message store provider.</span></span> <span data-ttu-id="5d86e-108">若要确定特定的邮件存储提供程序是否支持通知, 请检查其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="5d86e-108">To determine whether a particular message store provider supports notifications, check its **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="5d86e-109">如果邮件存储区支持通知, 则将设置 STORE_NOTIFY_OK 位。</span><span class="sxs-lookup"><span data-stu-id="5d86e-109">If the message store supports notifications, the STORE_NOTIFY_OK bit will be set.</span></span> 
  
<span data-ttu-id="5d86e-110">通过调用通知源对象的**advise**方法注册通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-110">Register for notifications by calling an advise source object's **Advise** method.</span></span> <span data-ttu-id="5d86e-111">许多对象都实现了**建议**, 客户端可以通过多种方式向这些对象注册。</span><span class="sxs-lookup"><span data-stu-id="5d86e-111">Many objects implement **Advise** and clients can register with those objects in a variety of ways.</span></span> 
  
 <span data-ttu-id="5d86e-112">**注册通知**</span><span class="sxs-lookup"><span data-stu-id="5d86e-112">**To register for a notification**</span></span>
  
1. <span data-ttu-id="5d86e-113">创建一个 MAPI 建议接收器对象并增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="5d86e-113">Create a MAPI advise sink object and increment its reference count.</span></span>
    
2. <span data-ttu-id="5d86e-114">如果需要, 请调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)以创建一个包装原始通知接收器的建议接收器对象, 然后释放原始的建议接收器。</span><span class="sxs-lookup"><span data-stu-id="5d86e-114">If appropriate, call [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) to create an advise sink object that wraps your original advise sink, then release the original advice sink..</span></span> 
    
3. <span data-ttu-id="5d86e-115">调用以下 "**建议**" 方法之一以完成注册:</span><span class="sxs-lookup"><span data-stu-id="5d86e-115">Call one of the following **Advise** methods to complete the registration:</span></span> 
    
  - <span data-ttu-id="5d86e-116">调用[IMAPISession:: 建议](imapisession-advise.md)注册会话通知或通讯簿或邮件存储对象上的通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-116">Call [IMAPISession::Advise](imapisession-advise.md) to register for session notifications or for notifications on an address book or message store object.</span></span> 
    
  - <span data-ttu-id="5d86e-117">调用[IAddrBook:: 建议](iaddrbook-advise.md)注册通讯簿通知或邮件用户、容器或通讯组列表上的通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-117">Call [IAddrBook::Advise](iaddrbook-advise.md) to register for address book notifications or for notifications on a messaging user, container, or distribution list.</span></span> 
    
  - <span data-ttu-id="5d86e-118">调用[IABLogon:: 建议](iablogon-advise.md)直接为邮件用户、容器或通讯组列表上的通知注册通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="5d86e-118">Call [IABLogon::Advise](iablogon-advise.md) to register directly with an address book provider for notifications on a messaging user, container, or distribution list.</span></span> 
    
  - <span data-ttu-id="5d86e-119">调用[IMsgStore:: 建议](imsgstore-advise.md)注册邮件存储通知或文件夹或邮件上的通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-119">Call [IMsgStore::Advise](imsgstore-advise.md) to register for message store notifications or for notifications on a folder or message.</span></span> 
    
  - <span data-ttu-id="5d86e-120">调用[IMSLogon:: 建议](imslogon-advise.md)直接向邮件存储提供程序注册文件夹或邮件中的通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-120">Call [IMSLogon::Advise](imslogon-advise.md) to register directly with a message store provider for notifications on a folder or message.</span></span> 
    
  - <span data-ttu-id="5d86e-121">调用[IMAPITable:: 建议](imapitable-advise.md)注册表通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-121">Call [IMAPITable::Advise](imapitable-advise.md) to register for table notifications.</span></span> 
    
4. <span data-ttu-id="5d86e-122">缓存从**Advise**返回的连接号码。</span><span class="sxs-lookup"><span data-stu-id="5d86e-122">Cache the connection number returned from **Advise**.</span></span>
    
5. <span data-ttu-id="5d86e-123">如果使用包装的建议接收器, 请将其释放。</span><span class="sxs-lookup"><span data-stu-id="5d86e-123">If using a wrapped advise sink, release it.</span></span> <span data-ttu-id="5d86e-124">在注册了包装的通知接收器之后, 您将不再需要它。</span><span class="sxs-lookup"><span data-stu-id="5d86e-124">Once the wrapped advise sink is registered, you no longer need it.</span></span>
    
<span data-ttu-id="5d86e-125">通过调用 \* \* IMAPISession:: Advise \* \*, 可以在整个会话或针对单个对象的各种通知中注册关键错误通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-125">Calling \*\* IMAPISession::Advise \*\* enables you to register for critical error notifications on the overall session or for various notifications on individual objects.</span></span> <span data-ttu-id="5d86e-126">会话向登录到共享会话的客户端发送关键错误通知。当另一个客户端使用共享会话时, 将调用[IMAPISession:: 注销](imapisession-logoff.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5d86e-126">Sessions send critical error notifications to clients logged on to shared sessions when another client using the shared session calls the [IMAPISession::Logoff](imapisession-logoff.md) method.</span></span> <span data-ttu-id="5d86e-127">若要注册会话通知, 请为条目标识符参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="5d86e-127">To register for session notifications, pass NULL for the entry identifier parameter.</span></span> <span data-ttu-id="5d86e-128">若要在单个对象上注册通知, 请传递对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5d86e-128">To register for notifications on an individual object, pass the object's entry identifier.</span></span> <span data-ttu-id="5d86e-129">**IMAPISession**方法将调用转发给相应的服务提供程序, 由条目标识符的**MAPIUID**部分确定。</span><span class="sxs-lookup"><span data-stu-id="5d86e-129">The **IMAPISession** method forwards the call to the appropriate service provider, as determined by the **MAPIUID** portion of the entry identifier.</span></span> <span data-ttu-id="5d86e-130">调用**IMAPISession:: 建议**注册对象通知比调用服务提供商的**建议**方法更简单。</span><span class="sxs-lookup"><span data-stu-id="5d86e-130">Calling **IMAPISession::Advise** to register for object notifications is simpler than calling a service provider's **Advise** method.</span></span> 
  
<span data-ttu-id="5d86e-131">使用通讯簿注册类似于在会话中注册。</span><span class="sxs-lookup"><span data-stu-id="5d86e-131">Registering with the address book is similar to registering with the session.</span></span> <span data-ttu-id="5d86e-132">若要从通讯簿中注册关键错误通知, 请为条目标识符传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="5d86e-132">To register for critical error notification from the address book, pass NULL for the entry identifier.</span></span> <span data-ttu-id="5d86e-133">若要在特定的通讯簿对象上注册通知, 请指定适当的条目标识符和事件或相关事件。</span><span class="sxs-lookup"><span data-stu-id="5d86e-133">To register for notifications on a particular address book object, specify the appropriate entry identifier and event or events of interest.</span></span> <span data-ttu-id="5d86e-134">请注意, 许多通讯簿提供程序不支持单个对象上的通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-134">Be aware that many address book providers do not support notifications on individual objects.</span></span> <span data-ttu-id="5d86e-135">相反, 它们支持对其内容和层次结构表的表通知。</span><span class="sxs-lookup"><span data-stu-id="5d86e-135">Rather, they support table notifications on their contents and hierarchy tables.</span></span> 
  
<span data-ttu-id="5d86e-136">最佳做法是, 在成功返回**通知**调用之后, 释放在[HrAllocAdviseSink](hrallocadvisesink.md)中实现或创建的通知接收器。</span><span class="sxs-lookup"><span data-stu-id="5d86e-136">It is good practice to release the advise sink that you implement or create with [HrAllocAdviseSink](hrallocadvisesink.md) immediately after a successful return from an **Advise** call.</span></span> <span data-ttu-id="5d86e-137">这是因为, 服务提供商在发出**通知**调用之后, 但在进行**Unadvise**调用之前, 可以发布您的通知接收器。</span><span class="sxs-lookup"><span data-stu-id="5d86e-137">This is because it is possible for service providers to release your advise sink after the **Advise** call, but before an **Unadvise** call is made.</span></span> <span data-ttu-id="5d86e-138">在此通知接收器上为通知源提供指向通知接收器和引用计数的指针后, 最好将其释放, 除非您对其使用长期。</span><span class="sxs-lookup"><span data-stu-id="5d86e-138">Once you have given the advise source a pointer to your advise sink and the reference count has been incremented on this advise sink, it is wise to release it unless you have a long term use for it.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5d86e-139">在进行**Unadvise**呼叫之前, 将不会发布表示有效的咨询注册的所有连接号码。</span><span class="sxs-lookup"><span data-stu-id="5d86e-139">All connection numbers that represent valid advisory registrations will not be released until the **Unadvise** call is made.</span></span> 
  

