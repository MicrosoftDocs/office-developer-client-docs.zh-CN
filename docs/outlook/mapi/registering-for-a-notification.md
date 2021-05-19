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
# <a name="registering-for-a-notification"></a><span data-ttu-id="578a0-103">注册通知</span><span class="sxs-lookup"><span data-stu-id="578a0-103">Registering for a Notification</span></span>

  
  
<span data-ttu-id="578a0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="578a0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="578a0-105">客户端可以在初始化过程中注册通讯簿或邮件存储通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-105">A client can register for address book or message store notifications as part of its initialization process.</span></span>
  
<span data-ttu-id="578a0-106">MAPI 支持通讯簿上的通知，而不管是否有通讯簿提供程序支持它。</span><span class="sxs-lookup"><span data-stu-id="578a0-106">MAPI supports notification on the address book regardless of whether any of the address book providers support it.</span></span> <span data-ttu-id="578a0-107">对邮件存储通知的支持取决于特定邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="578a0-107">Support for notification on message stores depends on the particular message store provider.</span></span> <span data-ttu-id="578a0-108">若要确定特定邮件存储提供程序是否支持通知，请检查其PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="578a0-108">To determine whether a particular message store provider supports notifications, check its **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="578a0-109">如果邮件存储支持通知，STORE_NOTIFY_OK位。</span><span class="sxs-lookup"><span data-stu-id="578a0-109">If the message store supports notifications, the STORE_NOTIFY_OK bit will be set.</span></span> 
  
<span data-ttu-id="578a0-110">通过调用建议源对象的 Advise 方法注册 **通知** 。</span><span class="sxs-lookup"><span data-stu-id="578a0-110">Register for notifications by calling an advise source object's **Advise** method.</span></span> <span data-ttu-id="578a0-111">许多对象都 **实现了 Advise，** 客户端可以通过多种方式向这些对象注册。</span><span class="sxs-lookup"><span data-stu-id="578a0-111">Many objects implement **Advise** and clients can register with those objects in a variety of ways.</span></span> 
  
 <span data-ttu-id="578a0-112">**注册通知**</span><span class="sxs-lookup"><span data-stu-id="578a0-112">**To register for a notification**</span></span>
  
1. <span data-ttu-id="578a0-113">创建 MAPI 建议接收对象并递增其引用计数。</span><span class="sxs-lookup"><span data-stu-id="578a0-113">Create a MAPI advise sink object and increment its reference count.</span></span>
    
2. <span data-ttu-id="578a0-114">如果合适，请调用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 创建包装原始建议接收器的建议接收对象，然后释放原始建议接收器。</span><span class="sxs-lookup"><span data-stu-id="578a0-114">If appropriate, call [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) to create an advise sink object that wraps your original advise sink, then release the original advice sink..</span></span> 
    
3. <span data-ttu-id="578a0-115">调用下列 Advise **方法之** 一以完成注册：</span><span class="sxs-lookup"><span data-stu-id="578a0-115">Call one of the following **Advise** methods to complete the registration:</span></span> 
    
  - <span data-ttu-id="578a0-116">调用 [IMAPISession：：Advise](imapisession-advise.md) 以注册会话通知或在通讯簿或邮件存储对象上注册通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-116">Call [IMAPISession::Advise](imapisession-advise.md) to register for session notifications or for notifications on an address book or message store object.</span></span> 
    
  - <span data-ttu-id="578a0-117">调用 [IAddrBook：：Advise](iaddrbook-advise.md) 注册通讯簿通知或在邮件用户、容器或通讯组列表上注册通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-117">Call [IAddrBook::Advise](iaddrbook-advise.md) to register for address book notifications or for notifications on a messaging user, container, or distribution list.</span></span> 
    
  - <span data-ttu-id="578a0-118">调用 [IABLogon：：Advise](iablogon-advise.md) 以直接在通讯簿提供程序中注册，以接收有关邮件用户、容器或通讯组列表的通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-118">Call [IABLogon::Advise](iablogon-advise.md) to register directly with an address book provider for notifications on a messaging user, container, or distribution list.</span></span> 
    
  - <span data-ttu-id="578a0-119">调用 [IMsgStore：：Advise](imsgstore-advise.md) 以注册邮件存储通知或文件夹或邮件上的通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-119">Call [IMsgStore::Advise](imsgstore-advise.md) to register for message store notifications or for notifications on a folder or message.</span></span> 
    
  - <span data-ttu-id="578a0-120">调用 [IMSLogon：：Advise](imslogon-advise.md) 以直接向邮件存储提供程序注册，以接收有关文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-120">Call [IMSLogon::Advise](imslogon-advise.md) to register directly with a message store provider for notifications on a folder or message.</span></span> 
    
  - <span data-ttu-id="578a0-121">调用 [IMAPITable：：Advise](imapitable-advise.md) 以注册表通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-121">Call [IMAPITable::Advise](imapitable-advise.md) to register for table notifications.</span></span> 
    
4. <span data-ttu-id="578a0-122">缓存从 Advise 返回的连接 **号**。</span><span class="sxs-lookup"><span data-stu-id="578a0-122">Cache the connection number returned from **Advise**.</span></span>
    
5. <span data-ttu-id="578a0-123">如果使用包装的建议接收器，请释放它。</span><span class="sxs-lookup"><span data-stu-id="578a0-123">If using a wrapped advise sink, release it.</span></span> <span data-ttu-id="578a0-124">注册包装的建议接收器后，你不再需要它。</span><span class="sxs-lookup"><span data-stu-id="578a0-124">Once the wrapped advise sink is registered, you no longer need it.</span></span>
    
<span data-ttu-id="578a0-125">调用 \*\* IMAPISession：：Advise \*\* 使你能够注册整个会话上的关键错误通知或单个对象上的各种通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-125">Calling \*\* IMAPISession::Advise \*\* enables you to register for critical error notifications on the overall session or for various notifications on individual objects.</span></span> <span data-ttu-id="578a0-126">当使用共享会话的另一个客户端调用 [IMAPISession：：Logoff](imapisession-logoff.md) 方法时，会话会向登录到共享会话的客户端发送关键错误通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-126">Sessions send critical error notifications to clients logged on to shared sessions when another client using the shared session calls the [IMAPISession::Logoff](imapisession-logoff.md) method.</span></span> <span data-ttu-id="578a0-127">若要注册会话通知，请为条目标识符参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="578a0-127">To register for session notifications, pass NULL for the entry identifier parameter.</span></span> <span data-ttu-id="578a0-128">若要在单个对象上注册通知，请传递对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="578a0-128">To register for notifications on an individual object, pass the object's entry identifier.</span></span> <span data-ttu-id="578a0-129">**IMAPISession** 方法将调用转发到相应的服务提供商，由条目标识符的 **MAPIUID** 部分确定。</span><span class="sxs-lookup"><span data-stu-id="578a0-129">The **IMAPISession** method forwards the call to the appropriate service provider, as determined by the **MAPIUID** portion of the entry identifier.</span></span> <span data-ttu-id="578a0-130">调用 **IMAPISession：：Advise** 注册对象通知比调用服务提供商的 Advise 方法 **更简单** 。</span><span class="sxs-lookup"><span data-stu-id="578a0-130">Calling **IMAPISession::Advise** to register for object notifications is simpler than calling a service provider's **Advise** method.</span></span> 
  
<span data-ttu-id="578a0-131">在通讯簿中注册类似于向会话注册。</span><span class="sxs-lookup"><span data-stu-id="578a0-131">Registering with the address book is similar to registering with the session.</span></span> <span data-ttu-id="578a0-132">若要注册通讯簿中的关键错误通知，请为条目标识符传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="578a0-132">To register for critical error notification from the address book, pass NULL for the entry identifier.</span></span> <span data-ttu-id="578a0-133">若要注册特定通讯簿对象上的通知，请指定相应的条目标识符和感兴趣的事件。</span><span class="sxs-lookup"><span data-stu-id="578a0-133">To register for notifications on a particular address book object, specify the appropriate entry identifier and event or events of interest.</span></span> <span data-ttu-id="578a0-134">请注意，许多通讯簿提供程序不支持有关单个对象的通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-134">Be aware that many address book providers do not support notifications on individual objects.</span></span> <span data-ttu-id="578a0-135">相反，它们支持有关其内容和层次结构表的表通知。</span><span class="sxs-lookup"><span data-stu-id="578a0-135">Rather, they support table notifications on their contents and hierarchy tables.</span></span> 
  
<span data-ttu-id="578a0-136">最佳做法是在 Advise 调用成功返回后立即释放您通过 [HrAllocAdviseSink](hrallocadvisesink.md) 实现或创建的 **通知** 接收器。</span><span class="sxs-lookup"><span data-stu-id="578a0-136">It is good practice to release the advise sink that you implement or create with [HrAllocAdviseSink](hrallocadvisesink.md) immediately after a successful return from an **Advise** call.</span></span> <span data-ttu-id="578a0-137">这是因为服务提供商可以先在 **Advise** 调用之后，但在进行 **Unadvise** 调用之前释放通知接收器。</span><span class="sxs-lookup"><span data-stu-id="578a0-137">This is because it is possible for service providers to release your advise sink after the **Advise** call, but before an **Unadvise** call is made.</span></span> <span data-ttu-id="578a0-138">一旦向建议源提供指向建议接收器的指针，并且引用计数已针对此建议接收器递增，那么除非长期使用，否则应释放它。</span><span class="sxs-lookup"><span data-stu-id="578a0-138">Once you have given the advise source a pointer to your advise sink and the reference count has been incremented on this advise sink, it is wise to release it unless you have a long term use for it.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="578a0-139">在调用 **Unadvise** 之前，不会释放表示有效咨询注册的所有连接号码。</span><span class="sxs-lookup"><span data-stu-id="578a0-139">All connection numbers that represent valid advisory registrations will not be released until the **Unadvise** call is made.</span></span> 
  

