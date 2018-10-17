---
title: 使用独立应用程序域以免发生故障
TOCTitle: Using a separate application domain to avoid crashing
ms:assetid: 7fc6d1e5-7032-47a9-826f-6b5d3b43fef9
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb623114(v=office.15)
ms:contentKeyID: 55119786
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: b397fa2ad37102e12a3a0cf569e74323391b8e86
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407252"
---
# <a name="using-a-separate-application-domain-to-avoid-crashing"></a>使用独立应用程序域以免发生故障

实现 **IDTExtensibility2** 接口的托管加载项将加载到相同的默认应用程序域中。当应用程序域中的某一加载项崩溃时，会导致同一应用程序域中的其他加载项也出现故障。

若要解决这一问题，可以为加载项创建一个填充程序，以便可以将加载项加载到其自己的应用程序域中。填充程序是用 C++ 编写的非托管动态链接库。当使用填充程序时，注册的是填充程序而非加载项。Outlook 可加载填充程序，而填充程序可加载构建它的加载项。必须为每个加载项构建和注册一个单独的填充程序。有关为托管加载项开发填充程序的详细信息，请参阅[借助 COM 填充程序向导隔离 Office 扩展（该链接可能指向英文页面）](https://go.microsoft.com/fwlink/?linkid=89109)。

另一种将加载项加载到独立应用程序域的方法是，使用 Visual Studio 2010 中的 Office 开发工具或更高版本的 Visual Studio Office 开发人员工具来开发加载项。 使用这些版本的 Visual Studio Office 开发人员工具开发的加载项不实现 IDTExtensibility2 接口，但使用 **IStartup** 接口。 它们使用 Visual Studio 提供的加载程序 AddinLoader.dll，其作用类似于通用垫片。 Outlook 在注册表中查找使用 Visual Studio 创建的加载项。 

如果 Outlook 找到此类加载项，便会启动 AddinLoader.dll。然后，此加载程序会启动 Visual Studio Tools for Office 运行时，并将应用程序部件清单中继到 Visual Studio Tools for Office 运行时。 然后，Visual Studio Tools for Office 运行时在独立应用程序域中加载每个此类加载项。 若要详细了解 Visual Studio 如何加载加载项，请参阅[应用程序级加载项的体系结构](https://msdn.microsoft.com/library/bb386298\(v=office.15\))。

