---
title: Outlook 主互操作程序集参考
TOCTitle: '@NoTitle'
ms:assetid: 54bdde85-8dc9-4498-a1ac-f72eaf8f0cd3
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb652780(v=office.15)
ms:contentKeyID: 55119771
ms.date: 09/15/2015
mtps_version: v=office.15
f1_keywords:
- Outlook 2010, programming
- Outlook 2010, object model
- Outlook 2010, PIA
- Outlook code samples
- Outlook 2010, primary interop assembly
- primary interop assembly [Outlook 2010]
- PIA [Outlook 2010]
- reference [Outlook 2010], primary interop assembly
localization_priority: Normal
ms.openlocfilehash: 53c50c447c6f132c562a1a22934df646347a51bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335745"
---
# <a name="outlook-primary-interop-assembly-reference"></a><span data-ttu-id="9c0d8-102">Outlook 主互操作程序集参考</span><span class="sxs-lookup"><span data-stu-id="9c0d8-102">Outlook Primary Interop Assembly reference</span></span>

<span data-ttu-id="9c0d8-103">Outlook 2013 主互操作程序集 (PIA) 参考为开发 Outlook 2013 的托管应用程序提供了相关帮助。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-103">The Outlook 2013 Primary Interop Assembly (PIA) reference provides help for developing managed applications for Outlook 2013.</span></span> <span data-ttu-id="9c0d8-104">它将 [Outlook 2013 开发人员参考](https://docs.microsoft.com/office/vba/api/overview/outlook)从 COM 环境扩展至托管环境且重点说明了如何使用 PIA。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-104">It extends the [Outlook 2013 Developer Reference](https://docs.microsoft.com/office/vba/api/overview/outlook) from the COM environment to the managed environment and focuses on how to use the PIA.</span></span> <span data-ttu-id="9c0d8-105">其中包含对 Outlook 2013 中的对象模型的所有添加和更改，并且提供了许多 C\# 和 Visual Basic 形式的代码示例来展示如何执行 Outlook 中的常见任务。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-105">It includes all the additions and changes to the object model in Outlook 2013, and provides many code samples in C\# and Visual Basic to show how to perform common tasks in Outlook.</span></span>

<span data-ttu-id="9c0d8-106">如果你是第一次开发 Outlook 解决方案，请参阅[选择某个 API 或技术开发适用于 Outlook 的解决方案](../selecting-an-api-or-technology-for-developing-solutions-for-outlook.md)，以确定最适合你需求的 API 和技术。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-106">If you are new to developing solutions for Outlook, see [Selecting an API or technology for developing solutions for Outlook](../selecting-an-api-or-technology-for-developing-solutions-for-outlook.md) to identify the APIs and technologies that are most appropriate for your needs.</span></span>

## <a name="purpose-of-the-outlook-pia-reference"></a><span data-ttu-id="9c0d8-107">Outlook PIA 参考的用途</span><span class="sxs-lookup"><span data-stu-id="9c0d8-107">Purpose of the Outlook PIA reference</span></span>

<span data-ttu-id="9c0d8-108">如果你是刚刚开始为 Outlook 编写加载项，则应首先参考《Outlook 2013 开发人员参考》中的概念内容。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-108">If you are just beginning to write add-ins for Outlook, you should first refer to the conceptual content in the Outlook 2013 Developer Reference.</span></span> <span data-ttu-id="9c0d8-109">虽然 COM 开发和托管开发中的编程环境、某些方法的访问方式和事件连接方式均有所不同，但是 Outlook 对象模型中的功能在 COM 开发和托管开发中的行为方式是相同的。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-109">Even though the programming environment and accessing certain methods and connecting to events are different in COM and in managed development, features in the Outlook object model behave the same way in both COM and managed development.</span></span> <span data-ttu-id="9c0d8-110">你可以参考《Outlook 2013 开发人员参考》中的概念内容来了解如何使用对象模型的不同功能。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-110">You can refer to the conceptual content in the Outlook 2013 Developer Reference to understand how to use the different features of the object model.</span></span>

<span data-ttu-id="9c0d8-111">如果你对 Outlook 对象模型已经有基本的了解，正在学习如何开发托管的 Outlook 加载项，请参阅[设置以使用 Outlook PIA](setting-up-to-use-the-outlook-pia.md)。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-111">If you have a basic understanding of the Outlook object model and are learning to develop managed Outlook add-ins, see [Setting up to use the Outlook PIA](setting-up-to-use-the-outlook-pia.md).</span></span> 

<span data-ttu-id="9c0d8-112">有关使用面向 Visual Studio 2013 的 Office 开发人员工具来开发托管 Office 解决方案的信息，请参阅 [Visual Studio 中的 Office 开发](https://docs.microsoft.com/visualstudio/vsto/office-and-sharepoint-development-in-visual-studio?view=vs-2017)。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-112">For information about developing managed Office solutions by using Office Developer Tools for Visual Studio 2013, see [Office Development in Visual Studio](https://docs.microsoft.com/visualstudio/vsto/office-and-sharepoint-development-in-visual-studio?view=vs-2017).</span></span> 

<span data-ttu-id="9c0d8-113">有关如何使用 Visual Basic 和 C\# 来对一些基本的 Outlook 任务进行编程的信息，请参阅 [Outlook 解决方案](https://docs.microsoft.com/visualstudio/vsto/outlook-solutions?view=vs-2017)。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-113">For information about how to program some basic Outlook tasks in both Visual Basic and C\#, see [Outlook solutions](https://docs.microsoft.com/visualstudio/vsto/outlook-solutions?view=vs-2017).</span></span> 

<span data-ttu-id="9c0d8-114">有关更高级的代码示例，请参阅本参考中的[如何...（Outlook 2013 PIA 参考）](how-do-i-outlook-2013-pia-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-114">For more advanced code examples, see [How do I... (Outlook 2013 PIA Reference)](how-do-i-outlook-2013-pia-reference.md) in this reference.</span></span>

<span data-ttu-id="9c0d8-115">如果你已经熟悉 Outlook 对象模型，并具备一些编写托管应用程序的经验，并且是第一次使用 Outlook PIA，请通过[安装和参考 Outlook PIA](installing-and-referencing-the-outlook-pia.md) 和 [Outlook PIA 的体系结构](architecture-of-the-outlook-pia.md)来完成入门。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-115">If you are already familiar with the Outlook object model, you have some experience writing managed applications, and you are using the Outlook PIA for the first time, start with [Installing and referencing the Outlook PIA](installing-and-referencing-the-outlook-pia.md) and [Architecture of the Outlook PIA](architecture-of-the-outlook-pia.md).</span></span>

## <a name="accessing-the-outlook-pia-reference-in-design-time"></a><span data-ttu-id="9c0d8-116">在设计时访问 Outlook PIA 参考</span><span class="sxs-lookup"><span data-stu-id="9c0d8-116">Accessing the Outlook PIA reference in design time</span></span>

<span data-ttu-id="9c0d8-117">如果你使用面向 Visual Studio 2013 的 Office 开发人员工具并且已连接到 Internet，则在 Visual Studio 集成开发环境 (IDE) 中按 F1 时，可以访问上下文相关帮助。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-117">If you use Office Developer Tools for Visual Studio 2013 and you are connected to the Internet, you can access context-sensitive Help when you press F1 in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="9c0d8-118">此帮助内容是 Outlook 2013 PIA 参考。</span><span class="sxs-lookup"><span data-stu-id="9c0d8-118">This Help content is the Outlook 2013 PIA reference.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9c0d8-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="9c0d8-119">In this section</span></span>

- [<span data-ttu-id="9c0d8-120">Outlook PIA 参考的最近更新</span><span class="sxs-lookup"><span data-stu-id="9c0d8-120">What's new in the Outlook PIA reference</span></span>](what-s-new-in-the-outlook-pia-reference.md)
- [<span data-ttu-id="9c0d8-121">设置以使用 Outlook PIA</span><span class="sxs-lookup"><span data-stu-id="9c0d8-121">Setting up to use the Outlook PIA</span></span>](setting-up-to-use-the-outlook-pia.md)
- [<span data-ttu-id="9c0d8-122">Outlook PIA 的体系结构</span><span class="sxs-lookup"><span data-stu-id="9c0d8-122">Architecture of the Outlook PIA</span></span>](architecture-of-the-outlook-pia.md)
- [<span data-ttu-id="9c0d8-123">使用 Outlook PIA 开发托管 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="9c0d8-123">Developing managed Outlook add-ins using the Outlook PIA</span></span>](developing-managed-outlook-add-ins-using-the-outlook-pia.md)
- [<span data-ttu-id="9c0d8-124">我如何...（Outlook 2013 PIA 参考）</span><span class="sxs-lookup"><span data-stu-id="9c0d8-124">How do I... (Outlook 2013 PIA Reference)</span></span>](how-do-i-outlook-2013-pia-reference.md)
- [<span data-ttu-id="9c0d8-125">类库</span><span class="sxs-lookup"><span data-stu-id="9c0d8-125">Class library</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook?view=outlook-pia)

## <a name="see-also"></a><span data-ttu-id="9c0d8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c0d8-126">See also</span></span>

- [<span data-ttu-id="9c0d8-127">Outlook 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="9c0d8-127">Outlook Developer Center</span></span>](../outlook-home.md)
- [<span data-ttu-id="9c0d8-128">COM 和 .NET 互操作性</span><span class="sxs-lookup"><span data-stu-id="9c0d8-128">COM and .NET Interoperability</span></span>](https://www.apress.com/us/book/9781590590119)
- [<span data-ttu-id="9c0d8-129">Visual Studio 中的 Office 开发</span><span class="sxs-lookup"><span data-stu-id="9c0d8-129">Office Development in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/vsto/office-and-sharepoint-development-in-visual-studio?view=vs-2017)
- [<span data-ttu-id="9c0d8-130">Microsoft 产品中的辅助功能</span><span class="sxs-lookup"><span data-stu-id="9c0d8-130">Accessibility in Microsoft Products</span></span>](https://www.microsoft.com/en-us/accessibility/)

