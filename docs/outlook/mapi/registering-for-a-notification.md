---
title: 注册通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 45625387-dbd2-4ca8-926b-ef87998d01d7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5a35add66fb685b3c17464269456edf6b456711e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570210"
---
# <a name="registering-for-a-notification"></a><span data-ttu-id="5db12-103">注册通知</span><span class="sxs-lookup"><span data-stu-id="5db12-103">Registering for a Notification</span></span>

  
  
<span data-ttu-id="5db12-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5db12-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5db12-105">客户端可以通讯簿或消息存储通知注册为其初始化过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="5db12-105">A client can register for address book or message store notifications as part of its initialization process.</span></span>
  
<span data-ttu-id="5db12-106">MAPI 支持在通讯簿无论是否任何通讯簿提供程序支持通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-106">MAPI supports notification on the address book regardless of whether any of the address book providers support it.</span></span> <span data-ttu-id="5db12-107">消息存储区上的通知的支持取决于特定消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="5db12-107">Support for notification on message stores depends on the particular message store provider.</span></span> <span data-ttu-id="5db12-108">若要确定特定消息存储提供程序是否支持通知，请查看其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="5db12-108">To determine whether a particular message store provider supports notifications, check its **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> <span data-ttu-id="5db12-109">如果消息存储库支持通知，将设置 STORE_NOTIFY_OK 位。</span><span class="sxs-lookup"><span data-stu-id="5db12-109">If the message store supports notifications, the STORE_NOTIFY_OK bit will be set.</span></span> 
  
<span data-ttu-id="5db12-110">通过调用 advise 源对象的**Advise**方法注册通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-110">Register for notifications by calling an advise source object's **Advise** method.</span></span> <span data-ttu-id="5db12-111">许多对象实现**Advise**和客户端可以注册这些对象中的各种方式。</span><span class="sxs-lookup"><span data-stu-id="5db12-111">Many objects implement **Advise** and clients can register with those objects in a variety of ways.</span></span> 
  
 <span data-ttu-id="5db12-112">**通知注册**</span><span class="sxs-lookup"><span data-stu-id="5db12-112">**To register for a notification**</span></span>
  
1. <span data-ttu-id="5db12-113">创建 MAPI 告知接收器对象和增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="5db12-113">Create a MAPI advise sink object and increment its reference count.</span></span>
    
2. <span data-ttu-id="5db12-114">如果合适，呼叫[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)创建您的原始通知接收器的换行 advise 接收器对象然后释放原始建议接收器。.</span><span class="sxs-lookup"><span data-stu-id="5db12-114">If appropriate, call [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) to create an advise sink object that wraps your original advise sink, then release the original advice sink..</span></span> 
    
3. <span data-ttu-id="5db12-115">调用以下的**Advise**方法，以完成注册之一：</span><span class="sxs-lookup"><span data-stu-id="5db12-115">Call one of the following **Advise** methods to complete the registration:</span></span> 
    
  - <span data-ttu-id="5db12-116">调用[IMAPISession::Advise](imapisession-advise.md)注册会话通知或通讯簿或消息存储对象上的通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-116">Call [IMAPISession::Advise](imapisession-advise.md) to register for session notifications or for notifications on an address book or message store object.</span></span> 
    
  - <span data-ttu-id="5db12-117">调用[IAddrBook::Advise](iaddrbook-advise.md)注册地址簿通知或消息的用户、 容器或通讯组列表上的通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-117">Call [IAddrBook::Advise](iaddrbook-advise.md) to register for address book notifications or for notifications on a messaging user, container, or distribution list.</span></span> 
    
  - <span data-ttu-id="5db12-118">调用[IABLogon::Advise](iablogon-advise.md)可直接注册通知消息的用户、 容器或通讯组列表上的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="5db12-118">Call [IABLogon::Advise](iablogon-advise.md) to register directly with an address book provider for notifications on a messaging user, container, or distribution list.</span></span> 
    
  - <span data-ttu-id="5db12-119">调用[IMsgStore::Advise](imsgstore-advise.md)注册消息存储通知或文件夹或消息的通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-119">Call [IMsgStore::Advise](imsgstore-advise.md) to register for message store notifications or for notifications on a folder or message.</span></span> 
    
  - <span data-ttu-id="5db12-120">调用[IMSLogon::Advise](imslogon-advise.md)可直接注册的消息存储提供程序上的文件夹或消息的通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-120">Call [IMSLogon::Advise](imslogon-advise.md) to register directly with a message store provider for notifications on a folder or message.</span></span> 
    
  - <span data-ttu-id="5db12-121">调用[IMAPITable::Advise](imapitable-advise.md)注册表通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-121">Call [IMAPITable::Advise](imapitable-advise.md) to register for table notifications.</span></span> 
    
4. <span data-ttu-id="5db12-122">缓存从**Advise**返回连接数。</span><span class="sxs-lookup"><span data-stu-id="5db12-122">Cache the connection number returned from **Advise**.</span></span>
    
5. <span data-ttu-id="5db12-123">如果使用换行的通知接收器，请将其释放。</span><span class="sxs-lookup"><span data-stu-id="5db12-123">If using a wrapped advise sink, release it.</span></span> <span data-ttu-id="5db12-124">换行的通知接收器注册后，您不再需要它。</span><span class="sxs-lookup"><span data-stu-id="5db12-124">Once the wrapped advise sink is registered, you no longer need it.</span></span>
    
<span data-ttu-id="5db12-125">调用 * * IMAPISession::Advise * * 使您能够注册总体会话上的错误通知，或在单个对象的各种通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-125">Calling ** IMAPISession::Advise ** enables you to register for critical error notifications on the overall session or for various notifications on individual objects.</span></span> <span data-ttu-id="5db12-126">会话将严重错误通知发送到客户端登录到共享会话时使用的共享的会话的另一个客户端调用[IMAPISession::Logoff](imapisession-logoff.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5db12-126">Sessions send critical error notifications to clients logged on to shared sessions when another client using the shared session calls the [IMAPISession::Logoff](imapisession-logoff.md) method.</span></span> <span data-ttu-id="5db12-127">若要注册会话通知，请为条目标识符参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="5db12-127">To register for session notifications, pass NULL for the entry identifier parameter.</span></span> <span data-ttu-id="5db12-128">若要注册的单个对象上的通知，请传递对象的项标识符。</span><span class="sxs-lookup"><span data-stu-id="5db12-128">To register for notifications on an individual object, pass the object's entry identifier.</span></span> <span data-ttu-id="5db12-129">**IMAPISession**方法转发到适当的服务提供程序，呼叫与由的项标识符的**MAPIUID**部分。</span><span class="sxs-lookup"><span data-stu-id="5db12-129">The **IMAPISession** method forwards the call to the appropriate service provider, as determined by the **MAPIUID** portion of the entry identifier.</span></span> <span data-ttu-id="5db12-130">调用**IMAPISession::Advise**注册对象通知是比调用服务提供商的**Advise**方法更简单。</span><span class="sxs-lookup"><span data-stu-id="5db12-130">Calling **IMAPISession::Advise** to register for object notifications is simpler than calling a service provider's **Advise** method.</span></span> 
  
<span data-ttu-id="5db12-131">注册通讯簿等同于注册会话。</span><span class="sxs-lookup"><span data-stu-id="5db12-131">Registering with the address book is similar to registering with the session.</span></span> <span data-ttu-id="5db12-132">若要注册的通讯簿中的错误通知，请为条目标识符传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="5db12-132">To register for critical error notification from the address book, pass NULL for the entry identifier.</span></span> <span data-ttu-id="5db12-133">若要注册特定地址簿对象上的通知，请指定适当的项标识符和事件或感兴趣的事件。</span><span class="sxs-lookup"><span data-stu-id="5db12-133">To register for notifications on a particular address book object, specify the appropriate entry identifier and event or events of interest.</span></span> <span data-ttu-id="5db12-134">请注意，许多通讯簿提供程序不支持通知上单个对象。</span><span class="sxs-lookup"><span data-stu-id="5db12-134">Be aware that many address book providers do not support notifications on individual objects.</span></span> <span data-ttu-id="5db12-135">相反，它们在其内容和层次结构表支持表通知。</span><span class="sxs-lookup"><span data-stu-id="5db12-135">Rather, they support table notifications on their contents and hierarchy tables.</span></span> 
  
<span data-ttu-id="5db12-136">很好的做法发行版的实现，或使用[HrAllocAdviseSink](hrallocadvisesink.md) **Advise**调用的成功返回后立即创建通知接收器。</span><span class="sxs-lookup"><span data-stu-id="5db12-136">It is good practice to release the advise sink that you implement or create with [HrAllocAdviseSink](hrallocadvisesink.md) immediately after a successful return from an **Advise** call.</span></span> <span data-ttu-id="5db12-137">这是因为可能为服务提供商释放通知接收器在**Advise**调用后，但之前**Unadvise**进行调用。</span><span class="sxs-lookup"><span data-stu-id="5db12-137">This is because it is possible for service providers to release your advise sink after the **Advise** call, but before an **Unadvise** call is made.</span></span> <span data-ttu-id="5db12-138">一旦您已指定 advise 源指针到通知接收器，在此通知接收器上会增加引用计数，最好其释放，除非您有长期使用它。</span><span class="sxs-lookup"><span data-stu-id="5db12-138">Once you have given the advise source a pointer to your advise sink and the reference count has been incremented on this advise sink, it is wise to release it unless you have a long term use for it.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5db12-139">直到**Unadvise**调用，并不会释放表示有效顾问注册的所有连接号码。</span><span class="sxs-lookup"><span data-stu-id="5db12-139">All connection numbers that represent valid advisory registrations will not be released until the **Unadvise** call is made.</span></span> 
  

