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
ms.openlocfilehash: 4242e466b0e784bb260d0525db0e253f1c1f37f3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568768"
---
# <a name="mapi-client-objects"></a><span data-ttu-id="f5f7f-103">MAPI 客户端对象</span><span class="sxs-lookup"><span data-stu-id="f5f7f-103">MAPI client objects</span></span>
  
<span data-ttu-id="f5f7f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f5f7f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f5f7f-105">标准邮件客户端应用程序实现只有一个对象 — 通知接收器。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-105">Standard messaging client applications implement only one object — an advise sink.</span></span> <span data-ttu-id="f5f7f-106">建议从继承接收器[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口和使用 MAPI 服务提供商的事件通知。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-106">Advise sinks inherit from the [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface and are used by MAPI and service providers for event notification.</span></span> <span data-ttu-id="f5f7f-107">某些客户端还实现进度对象，以支持显示进度对话框。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-107">Some clients also implement progress objects to support the display of progress dialog boxes.</span></span> 
  
<span data-ttu-id="f5f7f-108">更复杂的客户端支持自定义窗体实现另一个 advise 接收器对象和其他几个对象，如 message 网站对象继承[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)界面和视图上下文对象继承[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-108">More complex clients that support custom forms implement another advise sink object and a few other objects, such as the message site object that inherits from the [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) interface and the view context object that inherits from the [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md) interface.</span></span> <span data-ttu-id="f5f7f-109">其他 advise 接收器对象继承[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-109">The additional advise sink object inherits from the [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md) interface.</span></span> 
  
<span data-ttu-id="f5f7f-110">下表总结了实现标准消息客户端和支持的自定义窗体的查看的客户端的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-110">The following table summarizes the MAPI objects implemented by standard messaging clients and by clients that support the viewing of custom forms.</span></span>
  
|<span data-ttu-id="f5f7f-111">**客户端对象**</span><span class="sxs-lookup"><span data-stu-id="f5f7f-111">**Client object**</span></span>|<span data-ttu-id="f5f7f-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="f5f7f-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f5f7f-113">建议接收器</span><span class="sxs-lookup"><span data-stu-id="f5f7f-113">Advise sink</span></span>  <br/> |<span data-ttu-id="f5f7f-114">提供消息存储、 通讯簿或会话中发生的事件的回调函数。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-114">Provides a callback function for events that occur in the message store, address book, or the session.</span></span>  <br/> |
|<span data-ttu-id="f5f7f-115">消息网站</span><span class="sxs-lookup"><span data-stu-id="f5f7f-115">Message site</span></span>  <br/> |<span data-ttu-id="f5f7f-116">处理表单对象的操作。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-116">Handles the manipulation of form objects.</span></span>  <br/> |
|<span data-ttu-id="f5f7f-117">Progress</span><span class="sxs-lookup"><span data-stu-id="f5f7f-117">Progress</span></span>  <br/> |<span data-ttu-id="f5f7f-118">显示一个对话框，以显示操作的进度。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-118">Displays a dialog box to show the progress of an operation.</span></span>  <br/> |
|<span data-ttu-id="f5f7f-119">查看建议接收器</span><span class="sxs-lookup"><span data-stu-id="f5f7f-119">View advise sink</span></span>  <br/> |<span data-ttu-id="f5f7f-120">提供在窗体中发生的事件的回调函数。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-120">Provides callback functions for events that occur in a form.</span></span>  <br/> |
|<span data-ttu-id="f5f7f-121">视图上下文</span><span class="sxs-lookup"><span data-stu-id="f5f7f-121">View context</span></span>  <br/> |<span data-ttu-id="f5f7f-122">支持命令用于打印和保存窗体和窗体之间导航。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-122">Supports commands for printing and saving forms and for navigating between forms.</span></span>  <br/> |
   
<span data-ttu-id="f5f7f-123">下图显示了这些不同的客户端对象、 它们继承的接口和使用它们的 MAPI 组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-123">The following illustration shows the relationship between these different client objects, the interfaces from which they inherit, and the MAPI components that use them.</span></span> 
  
<span data-ttu-id="f5f7f-124">![客户端对象和对应接口](media/amapi_65.gif "客户端对象和对应接口")</span><span class="sxs-lookup"><span data-stu-id="f5f7f-124">![Client objects and corresponding interfaces](media/amapi_65.gif "Client objects and corresponding interfaces")</span></span>
  
<span data-ttu-id="f5f7f-125">客户端使用更多的对象不是他们实现。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-125">Clients use many more objects than they implement.</span></span> <span data-ttu-id="f5f7f-126">所有客户端使用的会话对象访问各种服务提供商对象和 MAPI 实现的对象。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-126">All clients use a session object to gain access to a wide variety of service provider objects and objects that MAPI implements.</span></span> <span data-ttu-id="f5f7f-127">客户端与服务提供商间接通过会话、 通讯簿中或提供 MAPI，状态对象或直接通过各种特定服务提供程序实现的对象进行交互。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-127">Clients interact with service providers either indirectly, through the session, the address book, or the status objects that MAPI supplies, or directly through a variety of objects that particular service providers implement.</span></span> <span data-ttu-id="f5f7f-128">若要使直接联系人通讯簿提供程序，客户端使用通讯簿容器消息用户和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-128">To make direct contact with address book providers, clients use address book containers, messaging users, and distribution lists.</span></span> <span data-ttu-id="f5f7f-129">若要访问消息存储提供程序直接，客户端使用的消息存储对象、 文件夹、 邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-129">To access a message store provider directly, clients use the message store object, folders, messages, and attachments.</span></span> <span data-ttu-id="f5f7f-130">服务提供商支持状态对象，当客户端可以使用状态对象来监控服务提供商的状态。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-130">When service providers support a status object, clients can use the status object to monitor the service provider's state.</span></span>
  
<span data-ttu-id="f5f7f-131">支持服务提供商和消息服务配置的客户端使用 MAPI 实现的三个对象： 消息服务管理对象、 配置文件管理对象和提供程序管理对象。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-131">Clients that support service provider and message service configuration use three objects that MAPI implements: the message service administration object, profile administration object, and provider administration object.</span></span> <span data-ttu-id="f5f7f-132">显示自定义窗体的客户端使用的窗体库提供程序或窗体服务器实现的多个窗体对象。</span><span class="sxs-lookup"><span data-stu-id="f5f7f-132">Clients that display custom forms use several form objects that a form library provider or a form server implements.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f5f7f-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5f7f-133">See also</span></span>

- [<span data-ttu-id="f5f7f-134">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f5f7f-134">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md) 
- [<span data-ttu-id="f5f7f-135">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f5f7f-135">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)  
- [<span data-ttu-id="f5f7f-136">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f5f7f-136">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)
- [<span data-ttu-id="f5f7f-137">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="f5f7f-137">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

