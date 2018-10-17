---
title: COM 和 .NET 之间的互操作性简介
TOCTitle: Introduction to interoperability between COM and .NET
ms:assetid: 6b2d099a-ec6f-4099-aaf6-e61003fe5a32
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb610378(v=office.15)
ms:contentKeyID: 55119776
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: eede42c542c1fc3d83831ae72ccf9b906648cea1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406825"
---
# <a name="introduction-to-interoperability-between-com-and-net"></a>COM 和 .NET 之间的互操作性简介

组件对象模型 (COM) 和 .NET 开发具有迥然不同的类型系统以及对象生存期管理、接口创建和接口继承机制。 

例如，COM 中的 **Variant** 类型对应的是 .NET Framework 中的 **System.Object** 数据类型。 若要创建对象，COM 客户端会调用 [CoCreateInstance](https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)，而托管客户端可以使用内置在托管编程语言中的关键字（如 new 或 New）。 

同时，COM 不支持传统继承，并且 COM 客户端管理 [IUnknown（该链接可能指向英文页面）](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) 所提供的内部引用计数以释放 coclass，而托管客户端依赖 .NET Framework 提供的公共语言运行库 (CLR) 垃圾收集器来释放对象。 

假定 COM 和 .NET 开发间存在这些差异，那么在 COM 对象模型上开发托管客户端则需要可处理这些差异的机制。 运行时可调用包装 (RCW) 就是这样一种机制，它可促进 COM 和托管编程模型之间的透明通信。

本主题提供了有关 RCW 如何利用 COM 和托管编程模型之间的通信的高级别描述。 请注意，虽然此主题使用了 Visual Studio 来阐述 RCW 机制，你也可以在 Visual Studio 外部使用互操作程序集来开发托管客户端。

## <a name="facilitating-interoperability-the-interop-assembly-and-rcw"></a>推动互操作性：互操作程序集和 RCW

### <a name="compile-time"></a>编译时

互操作程序集定义了可以与托管客户端进行交互且映射到基于 COM 的类型库的托管接口。 若要在 Visual Studio 中使用互操作程序集，请首先添加对相应 COM 组件的引用。 Visual Studio 将自动生成互操作程序集的本地副本。 互操作程序集包含一个命名空间，后者的下面则是 COM 对象模型中每个 COM 对象的托管等效接口。 

图 1 展示了一个希望使用会定义 coclass X 的 COM 类型库的托管客户端。托管客户端会调用类 X，后者是 coclass X 的托管等效接口，正如互操作程序集中所定义的。 在编译时，系统会使用互操作程序集中关于类 X 的信息来编译托管项目。

**图 1. 使用与非托管类型库互操作的互操作程序集编译的托管应用程序**

![使用与非托管类型库互操作的互操作程序集编译的托管应用程序](media/pia-unmanaged-type-library.gif)
  
通常，只要设置对某类型库的引用，Visual Studio 就会为该类型库生成互操作程序集的副本。可以使用任意数量的互操作程序集描述同一 COM 类型。但是，一个类型库只能有一个主互操作程序集 (PIA)，即该类型库所发布的互操作程序集。与其他互操作程序集不同，PIA 并不是在您每次向 Visual Studio 中添加引用时生成的。相反，您可以在计算机上向全局程序集缓存 (GAC) 中安装一次 PIA。添加对类型库的引用时，Visual Studio 会自动加载 PIA。

若要编程实现 Outlook 托管解决方案，应使用 Outlook PIA。 若要将来自 Outlook PIA 的信息纳入托管加载项，首先必须在 GAC 中安装 Outlook PIA。 如果使用 Visual Studio 创建托管项目，则在添加对 Outlook 类型库的引用后，Visual Studio 会加载 PIA。 在对象浏览器中的命名空间 Microsoft.Office.Interop.Outlook 下，可以看到具有对应于 Outlook 对象模型中对象的名称的托管接口。 例如，Account 接口对应的是 Outlook 对象模型中的 **Account** 对象。 编译托管项目时，此信息会被包含在可执行文件中。

### <a name="run-time"></a>运行时

在运行时，借助互操作程序集所提供的信息，.NET Framework CLR 将为托管客户端所交互的每个 coclass 创建一个 RCW。请注意，无论客户端从 coclass 获得了多少个接口，运行时只为每个 coclass 创建一个 RCW。RCW 是和 COM coclass 有关的 .NET Framework 类的类型。RCW 可跟踪 coclass 的实例，并且仅在客户端不再需要 RCW 时才释放对这些实例的引用。因此，托管客户端不必按照 COM 下非托管客户端的方式来管理对象生存期。

图 2 阐述的是：在运行时，RCW 从托管客户端截获 API 调用，并使用互操作程序集信息以透明方式将该调用映射到 COM coclass 中的相应 API。以下过程描述了此操作：

1.  如互操作程序集中 COM 类型库的相关定义，托管客户端调用类 X' 的方法 A'。

2.  如果类 X' 尚不具有 RCW，.NET Framework 运行时将使用互操作程序集信息并为类 X' 创建 RCW。

3.  RCW 截获对方法 A' 的调用，将参数转换为相应的 COM 类型，并按照 COM 类型库中的定义，调用 coclass X 的方法 A。

**图 2. RCW 截获来自托管可执行文件的调用，并将其映射到非托管类型库中的 coclass**

![RCW 截获来自托管可执行文件的调用，并将其映射到非托管类型库中的 coclass](media/pia-unmanaged-type-library-2.gif)
  

## <a name="see-also"></a>另请参阅

- [为什么要使用 Outlook PIA](why-use-the-outlook-pia.md)
- [安装和参考 Outlook PIA](installing-and-referencing-the-outlook-pia.md)

