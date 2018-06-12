---
title: MAPI 自定义窗体对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 306d62b1-d541-4039-9759-3903f62e0f26
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ecb40262959834ec511601ec3176887c919d944f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776215"
---
# <a name="mapi-custom-form-objects"></a><span data-ttu-id="7501e-103">MAPI 自定义窗体对象</span><span class="sxs-lookup"><span data-stu-id="7501e-103">MAPI custom form objects</span></span>
  
<span data-ttu-id="7501e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7501e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7501e-105">自定义窗体对象是由三个不同组件实现：</span><span class="sxs-lookup"><span data-stu-id="7501e-105">Objects for custom forms are implemented by three different components:</span></span>
  
- <span data-ttu-id="7501e-106">窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="7501e-106">A form server.</span></span>
    
- <span data-ttu-id="7501e-107">窗体库提供程序。</span><span class="sxs-lookup"><span data-stu-id="7501e-107">A form library provider.</span></span>
    
- <span data-ttu-id="7501e-108">表单查看器。</span><span class="sxs-lookup"><span data-stu-id="7501e-108">A form viewer.</span></span>
    
<span data-ttu-id="7501e-109">窗体服务器与 OLE 复合文档对象应用程序功能类似。</span><span class="sxs-lookup"><span data-stu-id="7501e-109">A form server is similar in functionality to an OLE compound document object application.</span></span> <span data-ttu-id="7501e-110">它是实现窗体; 可执行组件它控制其显示和用户可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7501e-110">It is an executable component that implements the form; it controls its display and the operations that a user can perform.</span></span> <span data-ttu-id="7501e-111">当用户想要查看使用窗体的窗体服务器支持显示邮件类别以及一条消息，则 MAPI 启动根据请求的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="7501e-111">MAPI starts a form server upon request when a user wants to view a message together with a message class that is displayed by using a form supported by the form server.</span></span> <span data-ttu-id="7501e-112">窗体服务器实现三个对象： 窗体中心对象类似于标准的 OLE 类工厂，窗体告知接收器用于处理特定于窗体的事件和窗体本身。</span><span class="sxs-lookup"><span data-stu-id="7501e-112">Form servers implement three objects: a form factory object that resembles the standard OLE class factory, a form advise sink for handling form-specific events, and the form itself.</span></span> 
  
<span data-ttu-id="7501e-113">表单库提供程序提供访问的客户端到窗体的属性集、 其容器和链接到的服务器，可以打开该类的窗体的邮件的特定类的对象。</span><span class="sxs-lookup"><span data-stu-id="7501e-113">A form library provider supplies access for clients to a form's property set, to its container, and to the object that links messages of a specific class to the server that can open the form for that class.</span></span> <span data-ttu-id="7501e-114">窗体库提供程序实现三个对象： 窗体信息对象、 窗体容器和窗体管理器将一条消息，绑定到基于消息的类的相应窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="7501e-114">Form library providers implement three objects: a form information object, a form container, and a form manager for binding a message to the appropriate form server based on the message's class.</span></span>
  
<span data-ttu-id="7501e-115">表单查看器是在其文件夹查看器中支持的自定义窗体显示的客户端中包含的组件。</span><span class="sxs-lookup"><span data-stu-id="7501e-115">A form viewer is a component that is included in clients that support the display of custom forms in their folder viewers.</span></span> <span data-ttu-id="7501e-116">表单查看器不独立 MAPI 组件，如是窗体库提供程序和窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="7501e-116">Form viewers are not independent MAPI components, as are form library providers and form servers.</span></span> <span data-ttu-id="7501e-117">表单查看器启动窗体服务器，并为其提供上下文。</span><span class="sxs-lookup"><span data-stu-id="7501e-117">Form viewers start form servers and provide context for them.</span></span> <span data-ttu-id="7501e-118">表单查看器实现以下三个对象： 消息网站、 了视图上下文和用于处理特定于视图的事件通知接收器。</span><span class="sxs-lookup"><span data-stu-id="7501e-118">Form viewers implement three objects: a message site, a view context, and an advise sink for handling view-specific events.</span></span>
  
<span data-ttu-id="7501e-119">下表介绍的所有自定义窗体对象。</span><span class="sxs-lookup"><span data-stu-id="7501e-119">The following table describes all of the custom form objects.</span></span> 
  
|<span data-ttu-id="7501e-120">**Form 对象**</span><span class="sxs-lookup"><span data-stu-id="7501e-120">**Form object**</span></span>|<span data-ttu-id="7501e-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="7501e-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7501e-122">窗体</span><span class="sxs-lookup"><span data-stu-id="7501e-122">Form</span></span>  <br/> |<span data-ttu-id="7501e-123">控件的显示和查看邮件的特定类的自定义窗体的操作。</span><span class="sxs-lookup"><span data-stu-id="7501e-123">Controls the display and operation of a custom form for viewing messages of a specific class.</span></span>  <br/> |
|<span data-ttu-id="7501e-124">窗体告知接收器</span><span class="sxs-lookup"><span data-stu-id="7501e-124">Form advise sink</span></span>  <br/> |<span data-ttu-id="7501e-125">处理从窗体查看器的通知。</span><span class="sxs-lookup"><span data-stu-id="7501e-125">Handles notifications from the form viewer.</span></span>  <br/> |
|<span data-ttu-id="7501e-126">窗体工厂</span><span class="sxs-lookup"><span data-stu-id="7501e-126">Form factory</span></span>  <br/> |<span data-ttu-id="7501e-127">创建窗体的实例，并允许其在内存中保留的服务器。</span><span class="sxs-lookup"><span data-stu-id="7501e-127">Creates an instance of a form and allows its server to remain in memory.</span></span>  <br/> |
|<span data-ttu-id="7501e-128">窗体容器</span><span class="sxs-lookup"><span data-stu-id="7501e-128">Form container</span></span>  <br/> |<span data-ttu-id="7501e-129">包含表单的信息。</span><span class="sxs-lookup"><span data-stu-id="7501e-129">Contains form information.</span></span>  <br/> |
|<span data-ttu-id="7501e-130">窗体信息</span><span class="sxs-lookup"><span data-stu-id="7501e-130">Form information</span></span>  <br/> |<span data-ttu-id="7501e-131">包含消息以及其他消息容器。</span><span class="sxs-lookup"><span data-stu-id="7501e-131">Contains messages and other message containers.</span></span>  <br/> |
|<span data-ttu-id="7501e-132">窗体管理器</span><span class="sxs-lookup"><span data-stu-id="7501e-132">Form manager</span></span>  <br/> |<span data-ttu-id="7501e-133">提供对集成视图与所有安装的表单的自定义窗体信息的访问。</span><span class="sxs-lookup"><span data-stu-id="7501e-133">Provides access to an integrated view of custom form information that is related to all of the installed forms.</span></span> <span data-ttu-id="7501e-134">此外将匹配相应窗体类标识符具有邮件类。</span><span class="sxs-lookup"><span data-stu-id="7501e-134">Also matches message classes with corresponding form class identifiers.</span></span>  <br/> |
|<span data-ttu-id="7501e-135">消息网站</span><span class="sxs-lookup"><span data-stu-id="7501e-135">Message site</span></span>  <br/> |<span data-ttu-id="7501e-136">处理的操作的内部客户端，从表单对象，并提供对窗体管理器对象的访问。</span><span class="sxs-lookup"><span data-stu-id="7501e-136">Handles the manipulation of form objects from inside the client, and provides access to a form manager object.</span></span>  <br/> |
|<span data-ttu-id="7501e-137">视图上下文</span><span class="sxs-lookup"><span data-stu-id="7501e-137">View context</span></span>  <br/> |<span data-ttu-id="7501e-138">支持窗体命令激活下一个和上一个消息和保存或打印。</span><span class="sxs-lookup"><span data-stu-id="7501e-138">Supports form commands for activating next and previous messages and for saving or printing.</span></span>  <br/> |
|<span data-ttu-id="7501e-139">查看建议接收器</span><span class="sxs-lookup"><span data-stu-id="7501e-139">View advise sink</span></span>  <br/> |<span data-ttu-id="7501e-140">处理从窗体服务器的通知。</span><span class="sxs-lookup"><span data-stu-id="7501e-140">Handles notifications from the form server.</span></span>  <br/> |
   
<span data-ttu-id="7501e-141">下图显示自定义表单组件、 对象和它们可实现的接口和对象的用户的组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="7501e-141">The following illustration shows the relationship between custom form components, the objects and interfaces that they implement, and the components that are users of the objects.</span></span> <span data-ttu-id="7501e-142">请注意，与大多数其他 MAPI 对象，该窗体对象实现通过直接继承不相关的两个接口。</span><span class="sxs-lookup"><span data-stu-id="7501e-142">Notice that, unlike most other MAPI objects, the form object implements two interfaces that are not related by direct inheritance.</span></span> <span data-ttu-id="7501e-143">对象公开了多个独立的接口，具有到一个接口的指针的对象的用户可以检索到的任何其他接口的指针。</span><span class="sxs-lookup"><span data-stu-id="7501e-143">When an object exposes multiple independent interfaces, a user of the object that has a pointer to one of the interfaces can retrieve a pointer to any of the other interfaces.</span></span> <span data-ttu-id="7501e-144">导航之间对象的接口实现此功能是一项功能的[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="7501e-144">This ability to navigate between an object's interface implementations is a feature of the [IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) method.</span></span> 
  
<span data-ttu-id="7501e-145">**自定义表单组件**</span><span class="sxs-lookup"><span data-stu-id="7501e-145">**Custom form components**</span></span>
  
<span data-ttu-id="7501e-146">![自定义表单组件](media/amapi_67.gif "自定义表单组件")</span><span class="sxs-lookup"><span data-stu-id="7501e-146">![Custom form components](media/amapi_67.gif "Custom form components")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7501e-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7501e-147">See also</span></span>

- [<span data-ttu-id="7501e-148">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="7501e-148">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

