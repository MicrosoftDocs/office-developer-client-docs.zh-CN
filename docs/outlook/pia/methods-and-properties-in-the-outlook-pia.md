---
title: Outlook PIA 中的方法和属性
TOCTitle: Methods and properties in the Outlook PIA
ms:assetid: ec7742de-ead6-41dd-90a3-1280fdf09d54
ms:mtpsurl: https://msdn.microsoft.com/library/Bb612528(v=office.15)
ms:contentKeyID: 55119780
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 90c13559094fbffd2dbe9a99602ee235c92d9445
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351030"
---
# <a name="methods-and-properties-in-the-outlook-pia"></a>Outlook PIA 中的方法和属性

本主题介绍如何通过使用 Outlook 主互操作程序集 (PIA) 来在在托管代码中访问对象的方法和属性。

## <a name="where-helper-objects-come-from"></a>帮助程序对象的由来

为了创建 Outlook PIA，Outlook 将使用 .NET Framework 中的类型库导入程序 (TLBIMP) 将 COM 类型库中的类型定义转换为公共语言运行库 (CLR) 程序集中的等效定义。在 COM 中，对象实际上是包括以下各项的 coclass：

- 主接口（如 [\_FormRegion](https://msdn.microsoft.com/library/bb645761\(v=office.15\)) 接口）。

- 事件接口（如 [FormRegionEvents](https://msdn.microsoft.com/library/bb611940\(v=office.15\)) 接口）。

TLBIMP 导入每个对象的主接口和事件接口，并创建众多接口、委托和类，其中包括以下各项：

- .NET 事件接口（如 [FormRegionEvents\_Event](https://msdn.microsoft.com/library/bb647619\(v=office.15\)) 接口）。

- .NET 类（如 [FormRegionClass](https://msdn.microsoft.com/library/bb624204\(v=office.15\)) 类）。

- .NET 接口（如 [FormRegion](https://msdn.microsoft.com/library/bb652633\(v=office.15\)) 接口）。

## <a name="what-the-helper-objects-are-for"></a>帮助程序对象的用途

继续以 **FormRegion** 对象为例，以下列表检查上述各个接口和类包含的内容。

- \_FormRegion 接口定义 FormRegion 的所有方法和属性。 除下面讨论的一个情况外，通常不在代码中使用此接口。

- **FormRegionEvents** 接口定义映射到 FormRegion 的事件的方法。 请勿在代码中使用此接口。

- TLBIMP 会进一步处理 **FormRegionEvents** 接口以创建定义 FormRegion 的所有事件的 **FormRegionEvents**\_Event 接口。 除下面讨论的一个情况外，通常不在代码中使用此接口。

- FormRegionClass 类定义 FormRegion 的所有方法、属性和事件成员。它是 FormRegion 接口在后台所关联的类，以便您可以编写代码来创建 FormRegion 接口的实例。但是，不要直接在代码中使用此接口。

- FormRegion 接口会继承 \_FormRegion 接口和 **FormRegionEvents**\_Event 接口。 图 1 说明了这个继承关系。
    
  **图 1. FormRegion 接口继承 \_FormRegion 接口的方法和属性，并继承 FormRegionEvents\_Event 接口的事件**

  ![FormRegion 接口继承 _FormRegion 接口的方法和属性，并继承 FormRegionEvents_Event 接口的事件](media/pia-form-region-interface.gif)
    
  通常，FormRegion 是在托管代码中用于访问对象和 **FormRegion** 对象的方法、属性及事件成员的一个接口。

将 **Application** 对象作为另一个示例，通过 **Application** 接口访问 [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象、方法、属性和事件。但存在三种例外情况，在这些情况下，您必须使用不同的接口，或者需要根据相应语言，使用不同的接口：

- 当您访问与事件共用同一名称的方法时，最好是转换为主接口来调用该方法。 例如，**Application** 对象具有 [Quit](https://msdn.microsoft.com/library/bb646614\(v=office.15\)) 方法和 [Quit](https://msdn.microsoft.com/library/bb622595\(v=office.15\)) 事件。 在 Visual Basic .NET 中，你可以通过 Application 接口访问 Quit 方法。 在 C\# 中，可以通过将 Quit 方法转换为主接口来避免出现编译器警告，如下面的代码示例所示：
    
   ```csharp
      void DemoApp()
      {
          Outlook.Application myApp = new Outlook.Application();
          // Other application code here
          ((Outlook._Application)myApp).Quit();
      }
   ```

- 当您访问与该对象的方法共用同一名称的事件时，必须转换为适当的事件接口才能连接到该事件。 与上述示例类似，若要连接到 Quit 事件，请转换为 [ApplicationEvents\_11\_Event](https://msdn.microsoft.com/library/bb622725\(v=office.15\)) 接口。

- 当您连接到随后在更高版本的 Outlook 中得到扩展的早期版本的事件时，必须连接到早期接口中该版本的事件。 例如，如果你希望连接到为 Outlook 2002 而非最新版本实现的 **Application** 对象的 Quit 事件版本，请连接到在 [ApplicationEvents\_10\_Event](https://msdn.microsoft.com/library/bb610098\(v=office.15\)) 接口中定义的 [Quit](https://msdn.microsoft.com/library/bb609660\(v=office.15\)) 事件，而不是在 ApplicationEvents\_11\_Event 接口中定义的 Quit 事件。

## <a name="see-also"></a>另请参阅

- [将 Outlook PIA 与对象模型相关联](relating-the-outlook-pia-with-the-object-model.md)
- [Outlook PIA 中的对象](objects-in-the-outlook-pia.md)
- [Outlook PIA 中的事件](events-in-the-outlook-pia.md)

