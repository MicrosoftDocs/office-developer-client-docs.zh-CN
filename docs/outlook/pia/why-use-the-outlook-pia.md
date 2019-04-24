---
title: 为什么要使用 Outlook PIA
TOCTitle: Why use the Outlook PIA
ms:assetid: 5cc9085e-7c97-4698-8cb9-e33e427c02e7
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb645534(v=office.15)
ms:contentKeyID: 55119773
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: dc882eba5f4e6c7729b81626d7324f89b724a244
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338736"
---
# <a name="why-use-the-outlook-pia"></a>为什么要使用 Outlook PIA

从 Outlook 98 开始，Outlook 为开发人员提供了一个对象模型，用于将 Outlook 功能集成到应用程序中、扩展 Outlook 或实现 Outlook 的自动化。 此对象模型旨在使用组件对象模型 (COM) 技术。 过去，Outlook 应用程序开发人员都是使用 Visual Basic for Applications (VBA) 和 Visual Basic 来开发 COM 解决方案。 但是，使用 VBA 开发的 Outlook 解决方案具有部署限制（尤其是在企业环境中），而且在部署后很难再进行更新。

.NET Framework 提供了一套丰富的类库和支持技术，它们可突破 VBA 和 COM 加载项的许多限制。但是，对于托管应用程序而言，我们需要在 .NET 环境和 COM 环境之间架设一座桥梁，以便根据 COM 对象模型进行编程。 互操作程序集便是一种充当这种桥梁的 COM 包装。 因此，现在越来越多的 Outlook 解决方案都是以依赖于互操作程序集的托管应用程序的形式进行开发。 有关互操作程序集如何利用 .NET 和 COM 之间的互操作性的更多信息，请参阅 [COM 和 .NET 之间的互操作性简介](introduction-to-interoperability-between-com-and-net.md)。

互操作程序集用于描述 COM 类型，允许托管代码与 COM 对象模型交互。可以使用任意数量的互操作程序集来描述一个给定的 COM 类型。作为类型库的发布者，Outlook 提供主互操作程序集 (PIA)，其中包含对基于 COM 的 Outlook 对象模型的官方描述。通常，最好使用 Outlook PIA，而不要依靠来自另一个源的互操作程序集。

## <a name="using-visual-studio-and-office-developer-tools-for-visual-studio"></a>使用 Visual Studio 和面向 Visual Studio 的 Office 开发人员工具

开发人员可以在 Visual Studio 外部创建托管的 Outlook 解决方案，但是，在使用 Visual Studio 后，将 Outlook 功能集成到托管代码中的过程会变得更加简单。 由于这种开发的便捷性，加载项开发人员更喜欢从 COM 开发迁移至 .NET 开发。 在设计时，开发人员可以使用面向 Visual Studio 的 Office 开发人员工具来创建对 Outlook 对象模型和 .NET Framework 均具有访问权限的加载项。 在运行时，面向 Visual Studio 的 Office 开发人员工具会为这些加载项提供加载程序：当用户启动 Outlook 时，此加载程序会启动 Visual Studio Tools for Office Runtime 这一公共语言运行时 (CLR)，然后加载相应的加载项程序集。 该程序集可以捕获在 Outlook 中引发的事件。

Visual Studio 2012 会默认安装适用于 Office 2010 的加载项模板。 若要使用面向 Visual Studio 的 Office 开发人员工具来开发适用于 Outlook 2013 的托管加载项，则必须[下载](https://aka.ms/officedevtoolsforvs2012)适用于 Office 2013 的模板。

有关面向 Visual Studio 的 Office 开发人员工具的详细信息，请参阅[配置计算机以开发 Office 解决方案](https://docs.microsoft.com/visualstudio/vsto/how-to-configure-a-computer-to-develop-office-solutions?view=vs-2017)。 有关为 Outlook 编程托管的加载项的详细信息，请参阅 [VSTO 加载项编程入门](https://docs.microsoft.com/visualstudio/vsto/getting-started-programming-vsto-add-ins?view=vs-2017)。

## <a name="see-also"></a>另请参阅

- [安装和参考 Outlook PIA](installing-and-referencing-the-outlook-pia.md)

