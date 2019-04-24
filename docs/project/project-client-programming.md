---
title: Project 客户端编程
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
f1_keywords:
- object model
- Project object model
- Project VBA
- VBA
keywords:
- vba、project 对象模型、项目、可编程性、可编程性、project VBA、Visual basic for applications、project 对象模型、vba、对象模型、VBA、Visual Basic for applications
localization_priority: Normal
ms.assetid: 0ad49ff6-8dff-4379-a52c-d292c53c2bc0
description: project 2013 桌面客户端应用程序 (project Standard 2013 和 project Professional 2013) 可通过使用 VBA 编写宏进行自定义和扩展。 您可以使用 Visual Studio 2012 来自定义功能区用户界面并创建复杂的外接程序。 Office 外接程序为项目中基于公共 Office 2013 平台构建的任务窗格启用了一个新的扩展性模型。 project Standard 2013 and project Professional 2013 可以运行常规的 Office 外接程序, 并使用专门为 Project 集成的 SharePoint、其他网站和 web 应用程序以及外部数据而开发的任务窗格加载项。
ms.openlocfilehash: cc345f0ff91dfb573dd86c256e89df478edd4924
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301510"
---
# <a name="project-client-programming"></a><span data-ttu-id="82867-106">Project 客户端编程</span><span class="sxs-lookup"><span data-stu-id="82867-106">Project client programming</span></span>

<span data-ttu-id="82867-107">project 2013 桌面客户端应用程序 (project Standard 2013 和 project Professional 2013) 可通过使用 VBA 编写宏进行自定义和扩展。</span><span class="sxs-lookup"><span data-stu-id="82867-107">The Project 2013 desktop client applications—Project Standard 2013 and Project Professional 2013—can be customized and extended by using VBA to write macros.</span></span> <span data-ttu-id="82867-108">您可以使用 Visual Studio 2012 来自定义功能区用户界面并创建复杂的外接程序。 Office 外接程序为项目中基于公共 Office 2013 平台构建的任务窗格启用了一个新的扩展性模型。</span><span class="sxs-lookup"><span data-stu-id="82867-108">You can use Visual Studio 2012 to customize the ribbon user interface and create complex add-ins. Office Add-ins enables a new extensibility model for task panes in Project that are built on a common Office 2013 platform.</span></span> <span data-ttu-id="82867-109">project Standard 2013 and project Professional 2013 可以运行常规的 Office 外接程序, 并使用专门为 Project 集成的 SharePoint、其他网站和 web 应用程序以及外部数据而开发的任务窗格加载项。</span><span class="sxs-lookup"><span data-stu-id="82867-109">Project Standard 2013 and Project Professional 2013 can run general Office Add-ins and use task pane add-ins that are developed specifically for Project to integrate with SharePoint, other websites and web applications, and external data.</span></span>
  
 <span data-ttu-id="82867-110">**移动到 Visual Studio**VBA 对录制宏和开发相对简单的自动化解决方案非常有用。</span><span class="sxs-lookup"><span data-stu-id="82867-110">**Moving to Visual Studio** VBA is useful for recording macros and developing relatively simple automation solutions.</span></span> <span data-ttu-id="82867-111">若要开发任务窗格外接程序、外接程序以及更复杂、安全、可扩展且易于部署的解决方案, 建议使用 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="82867-111">To develop task pane add-ins, add-ins, and more complex, secure, scalable, and easily deployed solutions, we recommend that you use Visual Studio 2012.</span></span> <span data-ttu-id="82867-112">Microsoft .net Framework 4.0 和 Project 2013 主互操作程序集为开发和部署可自动化和集成项目2013桌面客户端的解决方案提供了许多优势。</span><span class="sxs-lookup"><span data-stu-id="82867-112">The Microsoft .NET Framework 4.0 and the Project 2013 primary interop assembly provide many advantages for developing and deploying solutions that automate and integrate the Project 2013 desktop clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="82867-113">您可以使用 Visual Studio 2010 开发项目外接程序。但是, Visual Studio 2012 包含旨在创建 Office 外接程序客户端的模板和扩展。</span><span class="sxs-lookup"><span data-stu-id="82867-113">You can use Visual Studio 2010 to develop Project add-ins. However, Visual Studio 2012 includes templates and extensions that are designed to create Office Add-ins clients.</span></span> 
  
<span data-ttu-id="82867-114">Project 2013 中 VBA 的**msproject.xml**对象模型与 Visual Studio 2013 的 office 开发人员工具 (也称为 VSTO) 中的托管代码解决方案的**msproject.xml**对象模型本质上是相同的。</span><span class="sxs-lookup"><span data-stu-id="82867-114">The **MSProject** object model for VBA in Project 2013 is essentially the same as the **Microsoft.Office.Interop.MSProject** object model for managed-code solutions with Office Developer Tools for Visual Studio 2013 (also known as VSTO).</span></span> <span data-ttu-id="82867-115">Visual Studio 2012 包括用于开发项目2010的应用程序级外接程序和项目 2013 (project Standard 或 project Professional 版本) 的模板。</span><span class="sxs-lookup"><span data-stu-id="82867-115">Visual Studio 2012 includes templates for developing application-level add-ins for Project 2010 and for Project 2013 (either the Project Standard or Project Professional versions).</span></span> <span data-ttu-id="82867-116">适用于 Visual Studio 2012 的 VSTO 和 Office 开发人员工具简化了开发、测试和部署可使用 Project 桌面客户端和其他 Office 2013 应用程序的高级集成解决方案, 并与 SharePoint 网站、列表和流会.</span><span class="sxs-lookup"><span data-stu-id="82867-116">VSTO and Office Developer Tools for Visual Studio 2012 simplify developing, testing, and deploying advanced integration solutions that can use the Project desktop client and other Office 2013 applications, and integrate with SharePoint sites, lists, and workflows.</span></span> 
  
<span data-ttu-id="82867-117">可以在 office 应用商店中销售任务窗格外接程序和其他 office 和 SharePoint 外接程序 (请参阅[https://office.microsoft.com/store/](https://office.microsoft.com/en-us/store/)), 以便与 Project Online 和本地安装一起使用。</span><span class="sxs-lookup"><span data-stu-id="82867-117">Task pane add-ins and other add-ins for Office and SharePoint can be sold in the Office Store (see [https://office.microsoft.com/store/](https://office.microsoft.com/en-us/store/)) for use with both Project Online and on-premises installations.</span></span> <span data-ttu-id="82867-118">VBA 宏和 VSTO 外接程序不能在 Office 应用商店中分发;它们专为与 project Standard 和 project Professional 的本地使用而设计。</span><span class="sxs-lookup"><span data-stu-id="82867-118">VBA macros and VSTO add-ins cannot be distributed in the Office Store; they are designed for local use with Project Standard and Project Professional.</span></span> <span data-ttu-id="82867-119">您可以在项目中分发 VBA 宏。MPP 文件, 请将它们安装在计算机上的 global.mpt 文件中, 或将它们分布在 Project Server 2013 中的企业全局模板中。</span><span class="sxs-lookup"><span data-stu-id="82867-119">You can distribute VBA macros within a project .MPP file, install them in the Global.MPT file on your computer, or distribute them in the enterprise global template in Project Server 2013.</span></span> <span data-ttu-id="82867-120">可以通过[ClickOnce](https://msdn.microsoft.com/library/t71a733d.aspx)部署来更安全地分发 VSTO 加载项, 从而实现轻松的更新。</span><span class="sxs-lookup"><span data-stu-id="82867-120">VSTO add-ins can be distributed more securely through [ClickOnce](https://msdn.microsoft.com/library/t71a733d.aspx) deployment, which enables easy updates.</span></span> 
  
## <a name="reference"></a><span data-ttu-id="82867-121">参考</span><span class="sxs-lookup"><span data-stu-id="82867-121">Reference</span></span>

<span data-ttu-id="82867-122">[Project VBA 开发人员参考](https://msdn.microsoft.com/library/ee861523%28office.15%29.aspx)包含介绍性和 VBA 帮助文章。</span><span class="sxs-lookup"><span data-stu-id="82867-122">[Project VBA developer reference](https://msdn.microsoft.com/library/ee861523%28office.15%29.aspx) Contains introductory and VBA Help articles.</span></span> 
  
## <a name="related-sections"></a><span data-ttu-id="82867-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="82867-123">Related sections</span></span>

<span data-ttu-id="82867-124">[Project Server 2013 体系结构](project-server-2013-architecture.md)显示 project 客户端与 project Server 进行交互的方式。</span><span class="sxs-lookup"><span data-stu-id="82867-124">[Project Server 2013 architecture](project-server-2013-architecture.md) Shows how the Project clients interact with Project Server.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="82867-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82867-125">See also</span></span>

- [<span data-ttu-id="82867-126">面向开发人员的 Project</span><span class="sxs-lookup"><span data-stu-id="82867-126">Project for developers</span></span>](https://msdn.microsoft.com/office/aa905469)
- [<span data-ttu-id="82867-127">Office 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="82867-127">Office developer center</span></span>](https://dev.office.com)
- [<span data-ttu-id="82867-128">Visual Studio 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="82867-128">Visual Studio developer center</span></span>](https://msdn.microsoft.com/vstudio/aa718325.aspx)
- [<span data-ttu-id="82867-129">ClickOnce 安全性和部署</span><span class="sxs-lookup"><span data-stu-id="82867-129">ClickOnce Security and Deployment</span></span>](https://msdn.microsoft.com/library/t71a733d.aspx)
- [<span data-ttu-id="82867-130">可用域引用</span><span class="sxs-lookup"><span data-stu-id="82867-130">Available fields reference</span></span>](https://support.office.com/en-us/article/available-fields-reference-615a4563-1cc3-40f4-b66f-1b17e793a460)

