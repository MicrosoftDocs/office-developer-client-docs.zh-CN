---
title: MAPI 客户端对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 11304a4c-d986-4ad9-a140-19a59825a8df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6e78c80d861a5a56584bfb03bfdf2895efde8730
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412406"
---
# <a name="mapi-client-objects"></a><span data-ttu-id="357ae-103">MAPI 客户端对象</span><span class="sxs-lookup"><span data-stu-id="357ae-103">MAPI client objects</span></span>
  
<span data-ttu-id="357ae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="357ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="357ae-105">标准邮件客户端应用程序仅实现一个对象 — 一个建议接收器。</span><span class="sxs-lookup"><span data-stu-id="357ae-105">Standard messaging client applications implement only one object — an advise sink.</span></span> <span data-ttu-id="357ae-106">建议接收器继承自 [IMAPIAdviseSink ： IUnknown](imapiadvisesinkiunknown.md) 接口，供 MAPI 和服务提供商用于事件通知。</span><span class="sxs-lookup"><span data-stu-id="357ae-106">Advise sinks inherit from the [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface and are used by MAPI and service providers for event notification.</span></span> <span data-ttu-id="357ae-107">某些客户端还实现进度对象以支持进度对话框的显示。</span><span class="sxs-lookup"><span data-stu-id="357ae-107">Some clients also implement progress objects to support the display of progress dialog boxes.</span></span> 
  
<span data-ttu-id="357ae-108">支持自定义表单的更复杂的客户端实现另一个通知接收器对象和一些其他对象，例如从 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md) 接口继承的消息网站对象和从 [IMAPIViewContext ： IUnknown](imapiviewcontextiunknown.md) 接口继承的视图上下文对象。</span><span class="sxs-lookup"><span data-stu-id="357ae-108">More complex clients that support custom forms implement another advise sink object and a few other objects, such as the message site object that inherits from the [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) interface and the view context object that inherits from the [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md) interface.</span></span> <span data-ttu-id="357ae-109">其他建议接收器对象继承自 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="357ae-109">The additional advise sink object inherits from the [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md) interface.</span></span> 
  
<span data-ttu-id="357ae-110">下表总结了标准邮件客户端和支持查看自定义表单的客户端实现的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="357ae-110">The following table summarizes the MAPI objects implemented by standard messaging clients and by clients that support the viewing of custom forms.</span></span>
  
|<span data-ttu-id="357ae-111">**Client 对象**</span><span class="sxs-lookup"><span data-stu-id="357ae-111">**Client object**</span></span>|<span data-ttu-id="357ae-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="357ae-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="357ae-113">建议接收</span><span class="sxs-lookup"><span data-stu-id="357ae-113">Advise sink</span></span>  <br/> |<span data-ttu-id="357ae-114">为在邮件存储、通讯簿或会话中发生的事件提供回调函数。</span><span class="sxs-lookup"><span data-stu-id="357ae-114">Provides a callback function for events that occur in the message store, address book, or the session.</span></span>  <br/> |
|<span data-ttu-id="357ae-115">邮件网站</span><span class="sxs-lookup"><span data-stu-id="357ae-115">Message site</span></span>  <br/> |<span data-ttu-id="357ae-116">处理表单对象的操作。</span><span class="sxs-lookup"><span data-stu-id="357ae-116">Handles the manipulation of form objects.</span></span>  <br/> |
|<span data-ttu-id="357ae-117">Progress</span><span class="sxs-lookup"><span data-stu-id="357ae-117">Progress</span></span>  <br/> |<span data-ttu-id="357ae-118">显示一个对话框以显示操作的进度。</span><span class="sxs-lookup"><span data-stu-id="357ae-118">Displays a dialog box to show the progress of an operation.</span></span>  <br/> |
|<span data-ttu-id="357ae-119">查看建议接收器</span><span class="sxs-lookup"><span data-stu-id="357ae-119">View advise sink</span></span>  <br/> |<span data-ttu-id="357ae-120">为窗体中发生的事件提供回调函数。</span><span class="sxs-lookup"><span data-stu-id="357ae-120">Provides callback functions for events that occur in a form.</span></span>  <br/> |
|<span data-ttu-id="357ae-121">视图上下文</span><span class="sxs-lookup"><span data-stu-id="357ae-121">View context</span></span>  <br/> |<span data-ttu-id="357ae-122">支持打印和保存窗体以及表单之间的导航命令。</span><span class="sxs-lookup"><span data-stu-id="357ae-122">Supports commands for printing and saving forms and for navigating between forms.</span></span>  <br/> |
   
<span data-ttu-id="357ae-123">下图显示了这些不同的客户端对象、这些对象从其继承的接口以及使用这些对象的 MAPI 组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="357ae-123">The following illustration shows the relationship between these different client objects, the interfaces from which they inherit, and the MAPI components that use them.</span></span> 
  
<span data-ttu-id="357ae-124">![客户端对象和相应的接口](media/amapi_65.gif "客户端对象和相应的接口")</span><span class="sxs-lookup"><span data-stu-id="357ae-124">![Client objects and corresponding interfaces](media/amapi_65.gif "Client objects and corresponding interfaces")</span></span>
  
<span data-ttu-id="357ae-125">客户端使用的对象多于其实现的对象。</span><span class="sxs-lookup"><span data-stu-id="357ae-125">Clients use many more objects than they implement.</span></span> <span data-ttu-id="357ae-126">所有客户端都使用会话对象来访问 MAPI 实现的各种服务提供程序对象和对象。</span><span class="sxs-lookup"><span data-stu-id="357ae-126">All clients use a session object to gain access to a wide variety of service provider objects and objects that MAPI implements.</span></span> <span data-ttu-id="357ae-127">客户端通过会话、通讯簿或 MAPI 提供的状态对象间接地与服务提供商进行交互，或者直接通过特定服务提供商实现的各种对象进行交互。</span><span class="sxs-lookup"><span data-stu-id="357ae-127">Clients interact with service providers either indirectly, through the session, the address book, or the status objects that MAPI supplies, or directly through a variety of objects that particular service providers implement.</span></span> <span data-ttu-id="357ae-128">为了直接与通讯簿提供商联系，客户端使用通讯簿容器、邮件用户和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="357ae-128">To make direct contact with address book providers, clients use address book containers, messaging users, and distribution lists.</span></span> <span data-ttu-id="357ae-129">若要直接访问邮件存储提供程序，客户端可使用邮件存储对象、文件夹、邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="357ae-129">To access a message store provider directly, clients use the message store object, folders, messages, and attachments.</span></span> <span data-ttu-id="357ae-130">当服务提供商支持状态对象时，客户端可以使用 status 对象监视服务提供商的状态。</span><span class="sxs-lookup"><span data-stu-id="357ae-130">When service providers support a status object, clients can use the status object to monitor the service provider's state.</span></span>
  
<span data-ttu-id="357ae-131">支持服务提供程序和邮件服务配置的客户端使用 MAPI 实现三个对象：邮件服务管理对象、配置文件管理对象和提供程序管理对象。</span><span class="sxs-lookup"><span data-stu-id="357ae-131">Clients that support service provider and message service configuration use three objects that MAPI implements: the message service administration object, profile administration object, and provider administration object.</span></span> <span data-ttu-id="357ae-132">显示自定义表单的客户端使用表单库提供程序或表单服务器实现的几个表单对象。</span><span class="sxs-lookup"><span data-stu-id="357ae-132">Clients that display custom forms use several form objects that a form library provider or a form server implements.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="357ae-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="357ae-133">See also</span></span>

- [<span data-ttu-id="357ae-134">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="357ae-134">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md) 
- [<span data-ttu-id="357ae-135">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="357ae-135">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)  
- [<span data-ttu-id="357ae-136">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="357ae-136">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)
- [<span data-ttu-id="357ae-137">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="357ae-137">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

