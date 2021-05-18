---
title: MAPI 自定义表单对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 306d62b1-d541-4039-9759-3903f62e0f26
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4c1c04e5b04be9bb67b050f5cf498be89d380410
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318242"
---
# <a name="mapi-custom-form-objects"></a><span data-ttu-id="96a6c-103">MAPI 自定义表单对象</span><span class="sxs-lookup"><span data-stu-id="96a6c-103">MAPI custom form objects</span></span>
  
<span data-ttu-id="96a6c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96a6c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96a6c-105">自定义窗体的对象由三个不同的组件实现：</span><span class="sxs-lookup"><span data-stu-id="96a6c-105">Objects for custom forms are implemented by three different components:</span></span>
  
- <span data-ttu-id="96a6c-106">表单服务器。</span><span class="sxs-lookup"><span data-stu-id="96a6c-106">A form server.</span></span>
    
- <span data-ttu-id="96a6c-107">表单库提供程序。</span><span class="sxs-lookup"><span data-stu-id="96a6c-107">A form library provider.</span></span>
    
- <span data-ttu-id="96a6c-108">表单查看器。</span><span class="sxs-lookup"><span data-stu-id="96a6c-108">A form viewer.</span></span>
    
<span data-ttu-id="96a6c-109">表单服务器的功能类似于 OLE 复合文档对象应用程序。</span><span class="sxs-lookup"><span data-stu-id="96a6c-109">A form server is similar in functionality to an OLE compound document object application.</span></span> <span data-ttu-id="96a6c-110">它是实现表单的可执行组件;它控制其显示以及用户可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="96a6c-110">It is an executable component that implements the form; it controls its display and the operations that a user can perform.</span></span> <span data-ttu-id="96a6c-111">当用户希望使用表单服务器支持的表单查看邮件以及显示的邮件类时，MAPI 会根据请求启动窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="96a6c-111">MAPI starts a form server upon request when a user wants to view a message together with a message class that is displayed by using a form supported by the form server.</span></span> <span data-ttu-id="96a6c-112">表单服务器实现三个对象：类似于标准 OLE 类工厂的表单工厂对象、用于处理表单特定事件的表单建议接收器以及表单本身。</span><span class="sxs-lookup"><span data-stu-id="96a6c-112">Form servers implement three objects: a form factory object that resembles the standard OLE class factory, a form advise sink for handling form-specific events, and the form itself.</span></span> 
  
<span data-ttu-id="96a6c-113">表单库提供程序为客户端提供对表单的属性集、其容器以及将特定类的邮件链接到可打开该类的表单的服务器的对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="96a6c-113">A form library provider supplies access for clients to a form's property set, to its container, and to the object that links messages of a specific class to the server that can open the form for that class.</span></span> <span data-ttu-id="96a6c-114">表单库提供程序实现三个对象：一个表单信息对象、一个表单容器和一个表单管理器，用于根据邮件的类将邮件绑定到相应的表单服务器。</span><span class="sxs-lookup"><span data-stu-id="96a6c-114">Form library providers implement three objects: a form information object, a form container, and a form manager for binding a message to the appropriate form server based on the message's class.</span></span>
  
<span data-ttu-id="96a6c-115">表单查看器是包含在客户端中的组件，支持在文件夹查看器中显示自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="96a6c-115">A form viewer is a component that is included in clients that support the display of custom forms in their folder viewers.</span></span> <span data-ttu-id="96a6c-116">表单查看器不是独立的 MAPI 组件，与表单库提供程序和表单服务器一样。</span><span class="sxs-lookup"><span data-stu-id="96a6c-116">Form viewers are not independent MAPI components, as are form library providers and form servers.</span></span> <span data-ttu-id="96a6c-117">表单查看器启动表单服务器并为它们提供上下文。</span><span class="sxs-lookup"><span data-stu-id="96a6c-117">Form viewers start form servers and provide context for them.</span></span> <span data-ttu-id="96a6c-118">表单查看器实现三个对象：消息网站、视图上下文和用于处理特定于视图的事件的建议接收器。</span><span class="sxs-lookup"><span data-stu-id="96a6c-118">Form viewers implement three objects: a message site, a view context, and an advise sink for handling view-specific events.</span></span>
  
<span data-ttu-id="96a6c-119">下表介绍了所有自定义窗体对象。</span><span class="sxs-lookup"><span data-stu-id="96a6c-119">The following table describes all of the custom form objects.</span></span> 
  
|<span data-ttu-id="96a6c-120">**Form 对象**</span><span class="sxs-lookup"><span data-stu-id="96a6c-120">**Form object**</span></span>|<span data-ttu-id="96a6c-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="96a6c-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96a6c-122">表单</span><span class="sxs-lookup"><span data-stu-id="96a6c-122">Form</span></span>  <br/> |<span data-ttu-id="96a6c-123">控制用于查看特定类的消息的自定义窗体的显示和操作。</span><span class="sxs-lookup"><span data-stu-id="96a6c-123">Controls the display and operation of a custom form for viewing messages of a specific class.</span></span>  <br/> |
|<span data-ttu-id="96a6c-124">表单建议接收器</span><span class="sxs-lookup"><span data-stu-id="96a6c-124">Form advise sink</span></span>  <br/> |<span data-ttu-id="96a6c-125">处理来自表单查看器的通知。</span><span class="sxs-lookup"><span data-stu-id="96a6c-125">Handles notifications from the form viewer.</span></span>  <br/> |
|<span data-ttu-id="96a6c-126">表单工厂</span><span class="sxs-lookup"><span data-stu-id="96a6c-126">Form factory</span></span>  <br/> |<span data-ttu-id="96a6c-127">创建表单的实例，并允许其服务器保留在内存中。</span><span class="sxs-lookup"><span data-stu-id="96a6c-127">Creates an instance of a form and allows its server to remain in memory.</span></span>  <br/> |
|<span data-ttu-id="96a6c-128">表单容器</span><span class="sxs-lookup"><span data-stu-id="96a6c-128">Form container</span></span>  <br/> |<span data-ttu-id="96a6c-129">包含表单信息。</span><span class="sxs-lookup"><span data-stu-id="96a6c-129">Contains form information.</span></span>  <br/> |
|<span data-ttu-id="96a6c-130">表单信息</span><span class="sxs-lookup"><span data-stu-id="96a6c-130">Form information</span></span>  <br/> |<span data-ttu-id="96a6c-131">包含邮件和其他邮件容器。</span><span class="sxs-lookup"><span data-stu-id="96a6c-131">Contains messages and other message containers.</span></span>  <br/> |
|<span data-ttu-id="96a6c-132">表单管理器</span><span class="sxs-lookup"><span data-stu-id="96a6c-132">Form manager</span></span>  <br/> |<span data-ttu-id="96a6c-133">提供对与已安装的所有表单相关的自定义表单信息的集成视图的访问权限。</span><span class="sxs-lookup"><span data-stu-id="96a6c-133">Provides access to an integrated view of custom form information that is related to all of the installed forms.</span></span> <span data-ttu-id="96a6c-134">此外，还匹配具有相应表单类标识符的邮件类。</span><span class="sxs-lookup"><span data-stu-id="96a6c-134">Also matches message classes with corresponding form class identifiers.</span></span>  <br/> |
|<span data-ttu-id="96a6c-135">邮件网站</span><span class="sxs-lookup"><span data-stu-id="96a6c-135">Message site</span></span>  <br/> |<span data-ttu-id="96a6c-136">处理从客户端内部对表单对象的操作，并提供对表单管理器对象的访问。</span><span class="sxs-lookup"><span data-stu-id="96a6c-136">Handles the manipulation of form objects from inside the client, and provides access to a form manager object.</span></span>  <br/> |
|<span data-ttu-id="96a6c-137">视图上下文</span><span class="sxs-lookup"><span data-stu-id="96a6c-137">View context</span></span>  <br/> |<span data-ttu-id="96a6c-138">支持用于激活下一个和上一个邮件以及保存或打印的表单命令。</span><span class="sxs-lookup"><span data-stu-id="96a6c-138">Supports form commands for activating next and previous messages and for saving or printing.</span></span>  <br/> |
|<span data-ttu-id="96a6c-139">查看建议接收器</span><span class="sxs-lookup"><span data-stu-id="96a6c-139">View advise sink</span></span>  <br/> |<span data-ttu-id="96a6c-140">处理来自表单服务器的通知。</span><span class="sxs-lookup"><span data-stu-id="96a6c-140">Handles notifications from the form server.</span></span>  <br/> |
   
<span data-ttu-id="96a6c-141">下图显示了自定义表单组件、它们实现的对象和接口以及作为对象用户的组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="96a6c-141">The following illustration shows the relationship between custom form components, the objects and interfaces that they implement, and the components that are users of the objects.</span></span> <span data-ttu-id="96a6c-142">请注意，与大多数其他 MAPI 对象不同，表单对象实现了两个不通过直接继承相关的接口。</span><span class="sxs-lookup"><span data-stu-id="96a6c-142">Notice that, unlike most other MAPI objects, the form object implements two interfaces that are not related by direct inheritance.</span></span> <span data-ttu-id="96a6c-143">当对象公开多个独立接口时，具有指向其中一个接口的指针的对象的用户可以检索指向任何其他接口的指针。</span><span class="sxs-lookup"><span data-stu-id="96a6c-143">When an object exposes multiple independent interfaces, a user of the object that has a pointer to one of the interfaces can retrieve a pointer to any of the other interfaces.</span></span> <span data-ttu-id="96a6c-144">这种在对象的接口实现之间导航的功能是 [IUnknown：：QueryInterface 方法的一](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) 项功能。</span><span class="sxs-lookup"><span data-stu-id="96a6c-144">This ability to navigate between an object's interface implementations is a feature of the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) method.</span></span> 
  
<span data-ttu-id="96a6c-145">**自定义表单组件**</span><span class="sxs-lookup"><span data-stu-id="96a6c-145">**Custom form components**</span></span>
  
<span data-ttu-id="96a6c-146">![自定义表单组件](media/amapi_67.gif "自定义表单组件")</span><span class="sxs-lookup"><span data-stu-id="96a6c-146">![Custom form components](media/amapi_67.gif "Custom form components")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96a6c-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96a6c-147">See also</span></span>

- [<span data-ttu-id="96a6c-148">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="96a6c-148">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

