---
title: 使用独立应用程序域以免发生故障
TOCTitle: Using a separate application domain to avoid crashing
ms:assetid: 7fc6d1e5-7032-47a9-826f-6b5d3b43fef9
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb623114(v=office.15)
ms:contentKeyID: 55119786
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e2490c15da9c993a1a26b50adeb38207457f8286
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285145"
---
# <a name="using-a-separate-application-domain-to-avoid-crashing"></a><span data-ttu-id="d706f-102">使用独立应用程序域以免发生故障</span><span class="sxs-lookup"><span data-stu-id="d706f-102">Using a separate application domain to avoid crashing</span></span>

<span data-ttu-id="d706f-p101">实现 **IDTExtensibility2** 接口的托管加载项将加载到相同的默认应用程序域中。当应用程序域中的某一加载项崩溃时，会导致同一应用程序域中的其他加载项也出现故障。</span><span class="sxs-lookup"><span data-stu-id="d706f-p101">Managed add-ins that implement the **IDTExtensibility2** interface are loaded into the same default application domain. When an add-in in the application domain crashes, it can cause other add-ins in the same application domain to fail as well.</span></span>

<span data-ttu-id="d706f-p102">若要解决这一问题，可以为加载项创建一个填充程序，以便可以将加载项加载到其自己的应用程序域中。填充程序是用 C++ 编写的非托管动态链接库。当使用填充程序时，注册的是填充程序而非加载项。Outlook 可加载填充程序，而填充程序可加载构建它的加载项。必须为每个加载项构建和注册一个单独的填充程序。有关为托管加载项开发填充程序的详细信息，请参阅[借助 COM 填充程序向导隔离 Office 扩展（该链接可能指向英文页面）](https://go.microsoft.com/fwlink/?linkid=89109)。</span><span class="sxs-lookup"><span data-stu-id="d706f-p102">To work around this problem, you can create a shim for the add-in, so that the add-in can be loaded in its own application domain. A shim is an unmanaged dynamic link library written in C++. When you use a shim, you register the shim instead of the add-in. Outlook loads the shim, and the shim loads the add-in for which it was built. You must build and register a separate shim for each add-in. For more information about developing shims for managed add-ins, see [Isolating Office Extensions with the COM Shim Wizard](https://go.microsoft.com/fwlink/?linkid=89109).</span></span>

<span data-ttu-id="d706f-111">另一种将加载项加载到独立应用程序域的方法是，使用 Visual Studio 2010 中的 Office 开发工具或更高版本的 Visual Studio Office 开发人员工具来开发加载项。</span><span class="sxs-lookup"><span data-stu-id="d706f-111">Another alternative to load your add-in into a separate application domain is to develop your add-in using Office development tools in Visual Studio 2010, or a later release of Office Developer Tools for Visual Studio.</span></span> <span data-ttu-id="d706f-112">使用这些版本的 Visual Studio Office 开发人员工具开发的加载项不实现 IDTExtensibility2 接口，但使用 **IStartup** 接口。</span><span class="sxs-lookup"><span data-stu-id="d706f-112">Add-ins developed by these versions of Office Developer Tools for Visual Studio do not implement the IDTExtensibility2 interface but use the **IStartup** interface.</span></span> <span data-ttu-id="d706f-113">它们使用 Visual Studio 提供的加载程序 AddinLoader.dll，其作用类似于通用垫片。</span><span class="sxs-lookup"><span data-stu-id="d706f-113">They use a loader provided by Visual Studio, AddinLoader.dll, which acts like a generic shim.</span></span> <span data-ttu-id="d706f-114">Outlook 在注册表中查找使用 Visual Studio 创建的加载项。</span><span class="sxs-lookup"><span data-stu-id="d706f-114">Outlook looks in the registry for add-ins created with Visual Studio.</span></span> 

<span data-ttu-id="d706f-115">如果 Outlook 找到此类加载项，便会启动 AddinLoader.dll。然后，此加载程序会启动 Visual Studio Tools for Office 运行时，并将应用程序部件清单中继到 Visual Studio Tools for Office 运行时。</span><span class="sxs-lookup"><span data-stu-id="d706f-115">If Outlook finds such add-ins, Outlook starts AddinLoader.dll, which then starts the Visual Studio Tools for Office Runtime and relays the application manifest to the Visual Studio Tools for Office Runtime.</span></span> <span data-ttu-id="d706f-116">然后，Visual Studio Tools for Office 运行时在独立应用程序域中加载每个此类加载项。</span><span class="sxs-lookup"><span data-stu-id="d706f-116">The Visual Studio Tools for Office Runtime then loads each such add-in in a separate application domain.</span></span> <span data-ttu-id="d706f-117">若要详细了解 Visual Studio 如何加载加载项，请参阅[应用程序级加载项的体系结构](https://msdn.microsoft.com/library/bb386298\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="d706f-117">For more information about how Visual Studio loads an add-in, see [Architecture of Application-Level Add-Ins](https://msdn.microsoft.com/library/bb386298\(v=office.15\)).</span></span>

