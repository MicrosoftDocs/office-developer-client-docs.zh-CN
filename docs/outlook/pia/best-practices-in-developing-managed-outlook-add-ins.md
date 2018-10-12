---
title: 开发托管 Outlook 加载项的最佳做法
TOCTitle: Best practices in developing managed Outlook add-ins
ms:assetid: a03246f6-2ca5-4fcb-8e63-a11cfbc8d9a0
ms:mtpsurl: https://msdn.microsoft.com/library/Bb611563(v=office.15)
ms:contentKeyID: 55119784
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 87573980836d63d751302b0efcec0952331b7fc4
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406860"
---
# <a name="best-practices-in-developing-managed-outlook-add-ins"></a><span data-ttu-id="9daea-102">开发托管 Outlook 加载项的最佳做法</span><span class="sxs-lookup"><span data-stu-id="9daea-102">Best Practices in Developing Managed Outlook Add-ins</span></span>

<span data-ttu-id="9daea-p101">虽然利用 Outlook 互操作程序集，可以编写与 Outlook 交互操作的托管解决方案，但 Outlook 早于 .NET Framework，并设计为支持通过非托管语言（例如 Visual Basic for Applications (VBA) 和 Visual Basic）进行编程。本主题列出了您在开发 Outlook 的托管加载项时应注意的主要方面。</span><span class="sxs-lookup"><span data-stu-id="9daea-p101">Even though the Outlook interop assemblies allow you to write managed solutions that interoperate with Outlook, Outlook predates the .NET Framework and is designed to support programmability through unmanaged languages such as Visual Basic for Applications (VBA) and Visual Basic. This topic lists the top areas that you should be aware of when you develop a managed add-in for Outlook.</span></span>

- [<span data-ttu-id="9daea-105">系统性释放对象</span><span class="sxs-lookup"><span data-stu-id="9daea-105">Systematically Releasing Objects</span></span>](systematically-releasing-objects.md)
- [<span data-ttu-id="9daea-106">使用独立应用程序域以免发生故障</span><span class="sxs-lookup"><span data-stu-id="9daea-106">Using a Separate Application Domain to Avoid Crashing</span></span>](using-a-separate-application-domain-to-avoid-crashing.md)
- [<span data-ttu-id="9daea-107">使用 Office Developer Tools for Visual Studio 提供的受信任应用程序对象</span><span class="sxs-lookup"><span data-stu-id="9daea-107">Using a trusted application object provided by Office Developer Tools for Visual Studio</span></span>](using-a-trusted-application-object-provided-by-office-developer-tools-for-visual-studio.md)
- [<span data-ttu-id="9daea-108">在事件处理程序中适当设定变量作用范围</span><span class="sxs-lookup"><span data-stu-id="9daea-108">Scoping Variables Appropriately in Event Handlers</span></span>](scoping-variables-appropriately-in-event-handlers.md)
- [<span data-ttu-id="9daea-109">避免在托管 Outlook 加载项中使用不受支持的技术</span><span class="sxs-lookup"><span data-stu-id="9daea-109">Avoiding Unsupported Technologies in Managed Outlook Add-ins</span></span>](avoiding-unsupported-technologies-in-managed-outlook-add-ins.md)
- [<span data-ttu-id="9daea-110">在需要依赖 Outlook 的多个版本时使用晚期绑定</span><span class="sxs-lookup"><span data-stu-id="9daea-110">Using Late Binding If Depending on Multiple Versions of Outlook</span></span>](using-late-binding-if-depending-on-multiple-versions-of-outlook.md)

