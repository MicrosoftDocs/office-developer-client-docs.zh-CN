---
title: Outlook PIA 中的事件
TOCTitle: Events in the Outlook PIA
ms:assetid: 1f9eafb3-6645-4e27-81fa-5d73bf94ae40
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb644571(v=office.15)
ms:contentKeyID: 55119782
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 0433d1915008bf9317790c1ba86a9bb028161c48
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407539"
---
# <a name="events-in-the-outlook-pia"></a><span data-ttu-id="0bb0d-102">Outlook PIA 中的事件</span><span class="sxs-lookup"><span data-stu-id="0bb0d-102">Events in the Outlook PIA</span></span>

<span data-ttu-id="0bb0d-p101">浏览 Outlook 主互操作程序集 (PIA)，您可能会注意到，许多接口和事件委托都根据 Outlook 对象模型中熟悉的对象和事件名称来命名。与 COM 类型库中的事件不同，Outlook PIA 中的事件并不是与同一对象的方法和属性在同一接口中定义的。导入或创建与事件相关的接口、委托和接收器帮助程序类，以支持 Outlook PIA 中的事件。本主题将介绍这些与事件相关的接口、委托和接收器帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-p101">Browsing the Outlook Primary Interop Assembly (PIA), you might notice that many interfaces and event delegates are named after familiar names of objects and events in the Outlook object model. Unlike events in the COM type library, events in the Outlook PIA are not defined in the same interface as methods and properties of the same object. Event-related interfaces, delegates, and sink helper classes are either imported or created to support events in the Outlook PIA. This topic describes these event-related interfaces, delegates, and sink helper classes.</span></span>

## <a name="where-do-the-event-interfaces-delegates-and-sink-helper-classes-come-from"></a><span data-ttu-id="0bb0d-107">事件接口、委托和接收器帮助程序类的来源</span><span class="sxs-lookup"><span data-stu-id="0bb0d-107">Where Do the Event Interfaces, Delegates and Sink Helper Classes Come From</span></span>

<span data-ttu-id="0bb0d-p102">为了创建 Outlook PIA，Outlook 将使用 .NET Framework 中的类型库导入程序 (TLBIMP) 将 COM 类型库中的类型定义转换为公共语言运行库 (CLR) 程序集中的等效定义。TLBIMP 会为每个对象导入以下两种类型的接口：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-p102">To create the Outlook PIA, Outlook uses the Type Library Importer (TLBIMP) in the .NET Framework to convert type definitions in the COM type library into equivalent definitions in a common language runtime (CLR) assembly. TLBIMP imports the following two types of interfaces for each object:</span></span>

  - <span data-ttu-id="0bb0d-110">主接口（例如，[\_Application](https://msdn.microsoft.com/library/bb611255\(v=office.15\)) 接口）</span><span class="sxs-lookup"><span data-stu-id="0bb0d-110">The primary interface (for example, the _Application interface)</span></span>

  - <span data-ttu-id="0bb0d-111">事件接口（例如，[ApplicationEvents\_11](https://msdn.microsoft.com/library/bb609229\(v=office.15\)) 接口）</span><span class="sxs-lookup"><span data-stu-id="0bb0d-111">The event interface (for example, the ApplicationEvents_11 interface)</span></span>

<span data-ttu-id="0bb0d-p103">TLBIMP 将处理导入的接口并创建许多接口、委托和类，包括 .NET 接口（例如，[Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 接口）。如果该对象还有事件，则创建以下内容：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-p103">TLBIMP processes the imported interfaces and creates a number of interfaces, delegates, and classes, including the .NET interface (for example, the [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) interface). If the object has events, the following are created:</span></span>

  - <span data-ttu-id="0bb0d-114">.NET 事件接口（例如，[ApplicationEvents\_11\_Event](https://msdn.microsoft.com/library/bb622725\(v=office.15\)) 接口）</span><span class="sxs-lookup"><span data-stu-id="0bb0d-114">The .NET event interface (for example, the ApplicationEvents_11_Event interface)</span></span>

  - <span data-ttu-id="0bb0d-115">每个事件的委托（例如，[ApplicationEvents\_11\_ItemSendEventHandler](https://msdn.microsoft.com/library/bb610818\(v=office.15\)) 委托）</span><span class="sxs-lookup"><span data-stu-id="0bb0d-115">Delegate for each event (for example, the ApplicationEvents_11_ItemSendEventHandler delegate)</span></span>

  - <span data-ttu-id="0bb0d-116">接收器帮助程序类（例如，[ApplicationEvents\_11\_SinkHelper](https://msdn.microsoft.com/library/bb609842\(v=office.15\)) 类）</span><span class="sxs-lookup"><span data-stu-id="0bb0d-116">Sink helper class (for example, ApplicationEvents_11_SinkHelper class)</span></span>

### <a name="multiple-versions-of-events"></a><span data-ttu-id="0bb0d-117">事件的多个版本</span><span class="sxs-lookup"><span data-stu-id="0bb0d-117">Multiple Versions of Events</span></span>

<span data-ttu-id="0bb0d-p104">有些在 Outlook 的多个版本中存在的对象在各版本中有不同的事件实现，并且随着新版本的发布添加了其他事件。为了支持在多个版本中不同的事件，Outlook 会向其名称中添加版本号，以区分这些与事件相关的接口、委托和类。例如：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-p104">Some objects that have existed for multiple versions of Outlook have different implementations of events over the versions, and have had additional events added as new versions are released. To support events that vary over multiple versions, Outlook distinguishes these event-related interfaces, delegates, and classes by adding a version number to their names. For example:</span></span>

  - <span data-ttu-id="0bb0d-121">**Application** 对象的导入事件接口包括：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-121">The imported event interfaces of the **Application** object includes:</span></span>
    
      - <span data-ttu-id="0bb0d-122">用于 Outlook 98 和 Outlook 2000 的最早期版本：[ApplicationEvents](https://msdn.microsoft.com/library/bb644093\(v=office.15\)) 接口</span><span class="sxs-lookup"><span data-stu-id="0bb0d-122">The earliest version for Outlook 98 and Outlook 2000: the [ApplicationEvents](https://msdn.microsoft.com/library/bb644093\(v=office.15\)) interface</span></span>
    
      - <span data-ttu-id="0bb0d-123">用于 Outlook 2002 的版本：[ApplicationEvents\_10](https://msdn.microsoft.com/library/bb647702\(v=office.15\)) 接口</span><span class="sxs-lookup"><span data-stu-id="0bb0d-123">The version for Outlook 2002: the ApplicationEvents_10 interface</span></span>
    
      - <span data-ttu-id="0bb0d-124">用于 Outlook 2003 及以后发行版的版本：[ApplicationEvents\_11](https://msdn.microsoft.com/library/bb609229\(v=office.15\)) 接口</span><span class="sxs-lookup"><span data-stu-id="0bb0d-124">The version for Outlook 2003 and later releases: the ApplicationEvents_11 interface</span></span>

  - <span data-ttu-id="0bb0d-125">TLBIMP 为 **Application** 对象创建的 .NET 事件接口包括：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-125">The .NET event interfaces created by TLBIMP for the **Application** object includes:</span></span>
    
      - <span data-ttu-id="0bb0d-126">用于 Outlook 98 和 Outlook 2000 的最早期版本：[ApplicationEvents\_Event](https://msdn.microsoft.com/library/bb609380\(v=office.15\)) 接口</span><span class="sxs-lookup"><span data-stu-id="0bb0d-126">The earliest version for Outlook 98 and Outlook 2000: the ApplicationEvents_Event interface</span></span>
    
      - <span data-ttu-id="0bb0d-127">用于 Outlook 2002 的版本：[ApplicationEvents\_10\_Event](https://msdn.microsoft.com/library/bb610098\(v=office.15\)) 接口</span><span class="sxs-lookup"><span data-stu-id="0bb0d-127">The version for Outlook 2002: the ApplicationEvents_10_Event interface</span></span>
    
      - <span data-ttu-id="0bb0d-128">用于 Outlook 2003 及以后发行版的版本：[ApplicationEvents\_11\_Event](https://msdn.microsoft.com/library/bb622725\(v=office.15\)) 接口</span><span class="sxs-lookup"><span data-stu-id="0bb0d-128">The version for Outlook 2003 and later releases: the ApplicationEvents_11_Event interface</span></span>

  - <span data-ttu-id="0bb0d-129">TLBIMP 为 **Application** 对象的每个版本中的每个事件创建的委托，例如，用于 ItemSend 事件的每个版本的委托：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-129">The delegates that TLBIMP creates for each event in each version of the **Application** object, for example, a delegate for each version of the ItemSend event:</span></span>
    
      - <span data-ttu-id="0bb0d-130">用于 Outlook 98 和 Outlook 2000 的最早期版本：[ApplicationEvents\_ItemSendEventHandler](https://msdn.microsoft.com/library/bb622515\(v=office.15\)) 委托</span><span class="sxs-lookup"><span data-stu-id="0bb0d-130">The earliest version for Outlook 98 and Outlook 2000: the ApplicationEvents_ItemSendEventHandler delegate</span></span>
    
      - <span data-ttu-id="0bb0d-131">用于 Outlook 2002 的版本：[ApplicationEvents\_10\_ItemSendEventHandler](https://msdn.microsoft.com/library/bb646436\(v=office.15\)) 委托</span><span class="sxs-lookup"><span data-stu-id="0bb0d-131">The version for Outlook 2002: the ApplicationEvents_10_ItemSendEventHandler delegate</span></span>
    
      - <span data-ttu-id="0bb0d-132">用于 Outlook 2003 及以后发行版的版本：[ApplicationEvents\_11\_ItemSendEventHandler](https://msdn.microsoft.com/library/bb610818\(v=office.15\)) 委托</span><span class="sxs-lookup"><span data-stu-id="0bb0d-132">The version for Outlook 2003 and later releases: the ApplicationEvents_11_ItemSendEventHandler delegate</span></span>

<span data-ttu-id="0bb0d-133">从逻辑上讲，添加到较高版本中的事件不会出现在早期版本的事件接口中，在早期版本中也没有对应的委托。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-133">Logically, events that are added to a later version do not appear in event interfaces of earlier versions and do not have corresponding delegates in earlier versions.</span></span> <span data-ttu-id="0bb0d-134">例如，[AttachmentSelectionChange](https://msdn.microsoft.com/library/ff184926\(v=office.15\)) 事件被添加到了 Outlook 2010 中的 [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) 对象，因此，该事件不属于 Explorer 对象的早期事件接口的一部分：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-134">For example, the [AttachmentSelectionChange](https://msdn.microsoft.com/library/ff184926\(v=office.15\)) event was added to the [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) object in Microsoft Outlook 2010, therefore, it is not part of these earlier event interfaces for the Explorer object:</span></span>

  - <span data-ttu-id="0bb0d-135">ExplorerEvents 接口</span><span class="sxs-lookup"><span data-stu-id="0bb0d-135">ExplorerEvents interface</span></span>

  - <span data-ttu-id="0bb0d-136">ExplorerEvents\_Event 接口</span><span class="sxs-lookup"><span data-stu-id="0bb0d-136">\_ interface</span></span>

<span data-ttu-id="0bb0d-137">另一方面，你可以在最新 .NET 事件接口 ExplorerEvents\_10\_Event 及其针对 Outlook 2010 版本的委托 [ExplorerEvents\_10\_AttachmentSelectionChangeEventHandler](https://msdn.microsoft.com/library/ff185177\(v=office.15\)) 中找到该事件。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-137">On the other hand, you can find the event in the most recent .NET event interface, ExplorerEvents_10_Event, and its delegate for the Outlook 2010 version, ExplorerEvents_10_AttachmentSelectionChangeEventHandler .</span></span>

## <a name="what-the-event-interfaces-delegates-and-sink-helper-classes-are-for"></a><span data-ttu-id="0bb0d-138">事件接口、委托和接收器帮助程序类的用途</span><span class="sxs-lookup"><span data-stu-id="0bb0d-138">What the Event Interfaces, Delegates, and Sink Helper Classes Are For</span></span>

<span data-ttu-id="0bb0d-139">本节将以 **Application** 对象为例，介绍上述各个接口和类所包含的内容：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-139">Using the **Application** object as an example, this section describes what each interface and class listed above contains:</span></span>

  - <span data-ttu-id="0bb0d-140">主接口 \_Application 用于定义 Application 的所有方法和属性。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-140">The primary interface, _Application, defines all the methods and properties of Application.</span></span> <span data-ttu-id="0bb0d-141">除下面讨论的一个情况外，通常不在代码中使用此接口。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-141">Except for a condition discussed below, typically you do not use this interface in code.</span></span>

  - <span data-ttu-id="0bb0d-142">TLBIMP 导入的事件接口（如 ApplicationEvents\_11 和 ApplicationEvents\_10）用于定义到对应 Outlook 版本中的 Application 事件的方法映射。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-142">The events interfaces imported by TLBIMP, such as ApplicationEvents_11 and ApplicationEvents_10, define methods mapping to events of Application in the corresponding version of Outlook.</span></span> <span data-ttu-id="0bb0d-143">请勿在代码中使用此接口。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-143">You do not use this interface in code.</span></span>

  - <span data-ttu-id="0bb0d-144">TLBIMP 创建的事件接口（如 ApplicationEvents\_11\_Event 和 ApplicationEvents\_10\_Event）用于定义对应 Outlook 版本中的所有 Application 事件。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-144">The events interfaces created by TLBIMP, such as ApplicationEvents_11_Event and ApplicationEvents_10_Event, define all the events of Application in the corresponding version of Outlook.</span></span> <span data-ttu-id="0bb0d-145">在为特定版本中的事件设计事件处理程序时，需要将事件处理程序作为方法来实现，并将该方法连接到在 .NET 事件接口的对应版本中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-145">When designing an event handler for an event in a specific version, you implement the event handler as a method and connect the method to the event defined in the corresponding version of the .NET events interface.</span></span> <span data-ttu-id="0bb0d-146">除下面讨论的一个情况外，通常不在代码中引用该事件接口。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-146">Except for a condition discussed below, typically you do not reference the events interface in code.</span></span>

  - <span data-ttu-id="0bb0d-147">.NET 接口 Application 会继承 \_Application 接口和 ApplicationEvents\_11\_Event 接口。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-147">The .NET interface, \_, inherits the \_ interface and the \_ interface.</span></span> <span data-ttu-id="0bb0d-148">通常，您在托管代码中使用此接口来访问对象、方法、属性和 **Application** 对象的最新事件成员。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-148">Typically, this is the one interface you use in managed code to access the object, method, property, and the latest event members of the **Application** object.</span></span> <span data-ttu-id="0bb0d-149">但是，有两种例外情况，此时将不使用 .NET 接口而使用其他接口来连接事件：</span><span class="sxs-lookup"><span data-stu-id="0bb0d-149">There are however two exceptions where you would not use the .NET interface but a different interface to connect to an event:</span></span>
    
      - <span data-ttu-id="0bb0d-150">当您访问的事件与该对象的方法共享同一名称时，请转换为相应的事件接口来连接该事件。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-150">When you access an event that shares the same name as a method of that object, cast to the appropriate event interface to connect to the event.</span></span> <span data-ttu-id="0bb0d-151">例如，若要连接到 [Quit](https://msdn.microsoft.com/library/bb622595\(v=office.15\)) 事件，请转换到 ApplicationEvents\_11\_Event 接口。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-151">For example, to connect to the Quit event, you cast to the ApplicationEvents_11_Event interface.</span></span>
    
      - <span data-ttu-id="0bb0d-152">当您连接到事件的早期版本，而该事件随后在更高版本的 Outlook 中进行了扩展，请连接到该事件在早期接口中的版本。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-152">When you connect to an earlier version of an event that has been subsequently extended in a later version of Outlook, connect to the version of the event in the earlier interface.</span></span> <span data-ttu-id="0bb0d-153">例如，如果你希望连接到为 Outlook 2002 而非最新版本实现的 **Application** 对象的 Quit 事件版本时，请连接到在 ApplicationEvents\_10\_Event 接口中定义的 [Quit](https://msdn.microsoft.com/library/bb609660\(v=office.15\)) 事件，而不是在 ApplicationEvents\_11\_Event 接口中定义的 Quit 事件。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-153">For example, if you want to connect to the version of the **Quit** event of the [Application](https://msdn.microsoft.com/library/bb609660\(v=office.15\)) object implemented for Outlook 2002 instead of the latest version, connect to the \_ event defined in the \_ interface, instead of the \_ event defined in the \_ interface.</span></span>

  - <span data-ttu-id="0bb0d-154">代理会提供用于为特定版本 Outlook 中的特定事件创建自定义事件处理程序的框架。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-154">Delegates provide a framework for you to create custom event handlers for specific events in a specific version of Outlook.</span></span> <span data-ttu-id="0bb0d-155">例如，如果要添加一项检查，以在发送 Outlook 项之前检查主题行是否存在，应在与委托 ApplicationEvents\_11\_ItemSendEventHandler 具有相同签名的回调方法中实现该检查。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-155">For example, if you want to add a check for the existence of a subject line in an Outlook item just before you send it, you implement the check in a callback method that has the same signature as the delegate, ApplicationEvents_11_ItemSendEventHandler.</span></span> <span data-ttu-id="0bb0d-156">然后，将该回调方法作为在 ApplicationEvents\_11\_Event 接口中定义的 ItemSend 事件的事件处理程序挂起。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-156">Then you hook up the callback method as an event handler for the \_ event that is defined in the \_ interface.</span></span> <span data-ttu-id="0bb0d-157">有关将回调方法作为对象的事件处理程序来连接的详细信息，请参阅[连接到自定义事件处理程序](connecting-to-custom-event-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-157">For more information about connecting the callback method as an event handler for an object, see [Connecting to Custom Event Handlers](connecting-to-custom-event-handlers.md).</span></span>

  - <span data-ttu-id="0bb0d-158">例如，TLBIMP 创建的接收器帮助程序类（例如 ApplicationEvents\_11\_SinkHelper 和 [ApplicationEvents\_10\_SinkHelper](https://msdn.microsoft.com/library/bb644070\(v=office.15\))）是对应 Outlook 版本中的 Application 事件的事件帮助程序对象。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-158">The sink helper classes created by TLBIMP, for example, ApplicationEvents_11_SinkHelper and ApplicationEvents_10_SinkHelper , are event helper objects for Application events in the corresponding version of Outlook.</span></span> <span data-ttu-id="0bb0d-159">请勿在代码中使用这些类。</span><span class="sxs-lookup"><span data-stu-id="0bb0d-159">Do not use these classes in code.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bb0d-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bb0d-160">See also</span></span>

- [<span data-ttu-id="0bb0d-161">将 Outlook PIA 与对象模型相关联</span><span class="sxs-lookup"><span data-stu-id="0bb0d-161">Relating the Outlook PIA with the Object Model</span></span>](relating-the-outlook-pia-with-the-object-model.md)
- [<span data-ttu-id="0bb0d-162">Outlook PIA 中的对象</span><span class="sxs-lookup"><span data-stu-id="0bb0d-162">Objects in the Outlook PIA</span></span>](objects-in-the-outlook-pia.md)
- [<span data-ttu-id="0bb0d-163">Outlook PIA 中的方法和属性</span><span class="sxs-lookup"><span data-stu-id="0bb0d-163">Methods and Properties in the Outlook PIA</span></span>](methods-and-properties-in-the-outlook-pia.md)
- [<span data-ttu-id="0bb0d-164">使用 Outlook PIA 开发托管 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="0bb0d-164">Developing Managed Outlook Add-ins Using the Outlook PIA</span></span>](developing-managed-outlook-add-ins-using-the-outlook-pia.md)
