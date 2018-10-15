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
# <a name="events-in-the-outlook-pia"></a>Outlook PIA 中的事件

浏览 Outlook 主互操作程序集 (PIA)，您可能会注意到，许多接口和事件委托都根据 Outlook 对象模型中熟悉的对象和事件名称来命名。与 COM 类型库中的事件不同，Outlook PIA 中的事件并不是与同一对象的方法和属性在同一接口中定义的。导入或创建与事件相关的接口、委托和接收器帮助程序类，以支持 Outlook PIA 中的事件。本主题将介绍这些与事件相关的接口、委托和接收器帮助程序类。

## <a name="where-do-the-event-interfaces-delegates-and-sink-helper-classes-come-from"></a>事件接口、委托和接收器帮助程序类的来源

为了创建 Outlook PIA，Outlook 将使用 .NET Framework 中的类型库导入程序 (TLBIMP) 将 COM 类型库中的类型定义转换为公共语言运行库 (CLR) 程序集中的等效定义。TLBIMP 会为每个对象导入以下两种类型的接口：

  - 主接口（例如，[\_Application](https://msdn.microsoft.com/library/bb611255\(v=office.15\)) 接口）

  - 事件接口（例如，[ApplicationEvents\_11](https://msdn.microsoft.com/library/bb609229\(v=office.15\)) 接口）

TLBIMP 将处理导入的接口并创建许多接口、委托和类，包括 .NET 接口（例如，[Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 接口）。如果该对象还有事件，则创建以下内容：

  - .NET 事件接口（例如，[ApplicationEvents\_11\_Event](https://msdn.microsoft.com/library/bb622725\(v=office.15\)) 接口）

  - 每个事件的委托（例如，[ApplicationEvents\_11\_ItemSendEventHandler](https://msdn.microsoft.com/library/bb610818\(v=office.15\)) 委托）

  - 接收器帮助程序类（例如，[ApplicationEvents\_11\_SinkHelper](https://msdn.microsoft.com/library/bb609842\(v=office.15\)) 类）

### <a name="multiple-versions-of-events"></a>事件的多个版本

有些在 Outlook 的多个版本中存在的对象在各版本中有不同的事件实现，并且随着新版本的发布添加了其他事件。为了支持在多个版本中不同的事件，Outlook 会向其名称中添加版本号，以区分这些与事件相关的接口、委托和类。例如：

  - **Application** 对象的导入事件接口包括：
    
      - 用于 Outlook 98 和 Outlook 2000 的最早期版本：[ApplicationEvents](https://msdn.microsoft.com/library/bb644093\(v=office.15\)) 接口
    
      - 用于 Outlook 2002 的版本：[ApplicationEvents\_10](https://msdn.microsoft.com/library/bb647702\(v=office.15\)) 接口
    
      - 用于 Outlook 2003 及以后发行版的版本：[ApplicationEvents\_11](https://msdn.microsoft.com/library/bb609229\(v=office.15\)) 接口

  - TLBIMP 为 **Application** 对象创建的 .NET 事件接口包括：
    
      - 用于 Outlook 98 和 Outlook 2000 的最早期版本：[ApplicationEvents\_Event](https://msdn.microsoft.com/library/bb609380\(v=office.15\)) 接口
    
      - 用于 Outlook 2002 的版本：[ApplicationEvents\_10\_Event](https://msdn.microsoft.com/library/bb610098\(v=office.15\)) 接口
    
      - 用于 Outlook 2003 及以后发行版的版本：[ApplicationEvents\_11\_Event](https://msdn.microsoft.com/library/bb622725\(v=office.15\)) 接口

  - TLBIMP 为 **Application** 对象的每个版本中的每个事件创建的委托，例如，用于 ItemSend 事件的每个版本的委托：
    
      - 用于 Outlook 98 和 Outlook 2000 的最早期版本：[ApplicationEvents\_ItemSendEventHandler](https://msdn.microsoft.com/library/bb622515\(v=office.15\)) 委托
    
      - 用于 Outlook 2002 的版本：[ApplicationEvents\_10\_ItemSendEventHandler](https://msdn.microsoft.com/library/bb646436\(v=office.15\)) 委托
    
      - 用于 Outlook 2003 及以后发行版的版本：[ApplicationEvents\_11\_ItemSendEventHandler](https://msdn.microsoft.com/library/bb610818\(v=office.15\)) 委托

从逻辑上讲，添加到较高版本中的事件不会出现在早期版本的事件接口中，在早期版本中也没有对应的委托。 例如，[AttachmentSelectionChange](https://msdn.microsoft.com/library/ff184926\(v=office.15\)) 事件被添加到了 Outlook 2010 中的 [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) 对象，因此，该事件不属于 Explorer 对象的早期事件接口的一部分：

  - ExplorerEvents 接口

  - ExplorerEvents\_Event 接口

另一方面，你可以在最新 .NET 事件接口 ExplorerEvents\_10\_Event 及其针对 Outlook 2010 版本的委托 [ExplorerEvents\_10\_AttachmentSelectionChangeEventHandler](https://msdn.microsoft.com/library/ff185177\(v=office.15\)) 中找到该事件。

## <a name="what-the-event-interfaces-delegates-and-sink-helper-classes-are-for"></a>事件接口、委托和接收器帮助程序类的用途

本节将以 **Application** 对象为例，介绍上述各个接口和类所包含的内容：

  - 主接口 \_Application 用于定义 Application 的所有方法和属性。 除下面讨论的一个情况外，通常不在代码中使用此接口。

  - TLBIMP 导入的事件接口（如 ApplicationEvents\_11 和 ApplicationEvents\_10）用于定义到对应 Outlook 版本中的 Application 事件的方法映射。 请勿在代码中使用此接口。

  - TLBIMP 创建的事件接口（如 ApplicationEvents\_11\_Event 和 ApplicationEvents\_10\_Event）用于定义对应 Outlook 版本中的所有 Application 事件。 在为特定版本中的事件设计事件处理程序时，需要将事件处理程序作为方法来实现，并将该方法连接到在 .NET 事件接口的对应版本中定义的事件。 除下面讨论的一个情况外，通常不在代码中引用该事件接口。

  - .NET 接口 Application 会继承 \_Application 接口和 ApplicationEvents\_11\_Event 接口。 通常，您在托管代码中使用此接口来访问对象、方法、属性和 **Application** 对象的最新事件成员。 但是，有两种例外情况，此时将不使用 .NET 接口而使用其他接口来连接事件：
    
      - 当您访问的事件与该对象的方法共享同一名称时，请转换为相应的事件接口来连接该事件。 例如，若要连接到 [Quit](https://msdn.microsoft.com/library/bb622595\(v=office.15\)) 事件，请转换到 ApplicationEvents\_11\_Event 接口。
    
      - 当您连接到事件的早期版本，而该事件随后在更高版本的 Outlook 中进行了扩展，请连接到该事件在早期接口中的版本。 例如，如果你希望连接到为 Outlook 2002 而非最新版本实现的 **Application** 对象的 Quit 事件版本时，请连接到在 ApplicationEvents\_10\_Event 接口中定义的 [Quit](https://msdn.microsoft.com/library/bb609660\(v=office.15\)) 事件，而不是在 ApplicationEvents\_11\_Event 接口中定义的 Quit 事件。

  - 代理会提供用于为特定版本 Outlook 中的特定事件创建自定义事件处理程序的框架。 例如，如果要添加一项检查，以在发送 Outlook 项之前检查主题行是否存在，应在与委托 ApplicationEvents\_11\_ItemSendEventHandler 具有相同签名的回调方法中实现该检查。 然后，将该回调方法作为在 ApplicationEvents\_11\_Event 接口中定义的 ItemSend 事件的事件处理程序挂起。 有关将回调方法作为对象的事件处理程序来连接的详细信息，请参阅[连接到自定义事件处理程序](connecting-to-custom-event-handlers.md)。

  - 例如，TLBIMP 创建的接收器帮助程序类（例如 ApplicationEvents\_11\_SinkHelper 和 [ApplicationEvents\_10\_SinkHelper](https://msdn.microsoft.com/library/bb644070\(v=office.15\))）是对应 Outlook 版本中的 Application 事件的事件帮助程序对象。 请勿在代码中使用这些类。

## <a name="see-also"></a>另请参阅

- [将 Outlook PIA 与对象模型相关联](relating-the-outlook-pia-with-the-object-model.md)
- [Outlook PIA 中的对象](objects-in-the-outlook-pia.md)
- [Outlook PIA 中的方法和属性](methods-and-properties-in-the-outlook-pia.md)
- [使用 Outlook PIA 开发托管 Outlook 加载项](developing-managed-outlook-add-ins-using-the-outlook-pia.md)

