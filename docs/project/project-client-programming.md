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
- vba，project 对象模型，项目，可编程性可编程性 （英文）、 Project VBA、 Visual Basic for Applications Project 对象模型，VBA，对象模型，VBA，Visual Basic for Applications
localization_priority: Normal
ms.assetid: 0ad49ff6-8dff-4379-a52c-d292c53c2bc0
description: Project 2013 桌面客户端应用程序 — Project Standard 2013 和 Project Professional 2013 — 可以自定义和扩展通过使用 VBA 编写宏。 Visual Studio 2012 可用于自定义功能区用户界面和创建新扩展性模型的项目中的任务窗格的通用的 Office 2013 平台上构建的 Office 加载项允许的复杂加载宏。 Project Standard 2013 和 Project Professional 2013 可以运行常规 Office 加载项，并使用任务窗格的加载专门为项目以与 SharePoint、 其他网站和 web 应用程序和外部数据集成开发。
ms.openlocfilehash: 9e89c5a1f6486ce49ad8b95bcd7a92497b7a2436
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594738"
---
# <a name="project-client-programming"></a><span data-ttu-id="038c7-106">Project 客户端编程</span><span class="sxs-lookup"><span data-stu-id="038c7-106">Project client programming</span></span>

<span data-ttu-id="038c7-107">Project 2013 桌面客户端应用程序 — Project Standard 2013 和 Project Professional 2013 — 可以自定义和扩展通过使用 VBA 编写宏。</span><span class="sxs-lookup"><span data-stu-id="038c7-107">The Project 2013 desktop client applications—Project Standard 2013 and Project Professional 2013—can be customized and extended by using VBA to write macros.</span></span> <span data-ttu-id="038c7-108">Visual Studio 2012 可用于自定义功能区用户界面和创建新扩展性模型的项目中的任务窗格的通用的 Office 2013 平台上构建的 Office 加载项允许的复杂加载宏。</span><span class="sxs-lookup"><span data-stu-id="038c7-108">You can use Visual Studio 2012 to customize the ribbon user interface and create complex add-ins. Office Add-ins enables a new extensibility model for task panes in Project that are built on a common Office 2013 platform.</span></span> <span data-ttu-id="038c7-109">Project Standard 2013 和 Project Professional 2013 可以运行常规 Office 加载项，并使用任务窗格的加载专门为项目以与 SharePoint、 其他网站和 web 应用程序和外部数据集成开发。</span><span class="sxs-lookup"><span data-stu-id="038c7-109">Project Standard 2013 and Project Professional 2013 can run general Office Add-ins and use task pane add-ins that are developed specifically for Project to integrate with SharePoint, other websites and web applications, and external data.</span></span>
  
 <span data-ttu-id="038c7-110">**移动到 Visual Studio**VBA 可用于录制宏和开发相对简单自动化解决方案。</span><span class="sxs-lookup"><span data-stu-id="038c7-110">**Moving to Visual Studio** VBA is useful for recording macros and developing relatively simple automation solutions.</span></span> <span data-ttu-id="038c7-111">若要开发任务窗格的加载项，加载项和更多的复杂、 安全、 可扩展和轻松部署的解决方案，我们建议您使用 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="038c7-111">To develop task pane add-ins, add-ins, and more complex, secure, scalable, and easily deployed solutions, we recommend that you use Visual Studio 2012.</span></span> <span data-ttu-id="038c7-112">Microsoft.NET Framework 4.0 和 Project 2013 主互操作程序集提供有关开发和部署解决方案的自动化和集成 Project 2013 桌面客户端的很多好处。</span><span class="sxs-lookup"><span data-stu-id="038c7-112">The Microsoft .NET Framework 4.0 and the Project 2013 primary interop assembly provide many advantages for developing and deploying solutions that automate and integrate the Project 2013 desktop clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="038c7-113">可以使用 Visual Studio 2010 来开发项目外接程序。但是，Visual Studio 2012 包括模板和旨在创建 Office 加载项的客户端的扩展。</span><span class="sxs-lookup"><span data-stu-id="038c7-113">You can use Visual Studio 2010 to develop Project add-ins. However, Visual Studio 2012 includes templates and extensions that are designed to create Office Add-ins clients.</span></span> 
  
<span data-ttu-id="038c7-114">Project 2013 中的 VBA **MSProject**对象模型在本质上与 Visual Studio 2013 (也称为 VSTO) 的 Office 开发人员工具的**Microsoft.Office.Interop.MSProject**对象模型的托管代码解决方案相同。</span><span class="sxs-lookup"><span data-stu-id="038c7-114">The **MSProject** object model for VBA in Project 2013 is essentially the same as the **Microsoft.Office.Interop.MSProject** object model for managed-code solutions with Office Developer Tools for Visual Studio 2013 (also known as VSTO).</span></span> <span data-ttu-id="038c7-115">Visual Studio 2012 包含模板，用于开发应用程序级加载项的 Project 2010 和 Project 2013 （Project Standard 或 Project Professional 版本）。</span><span class="sxs-lookup"><span data-stu-id="038c7-115">Visual Studio 2012 includes templates for developing application-level add-ins for Project 2010 and for Project 2013 (either the Project Standard or Project Professional versions).</span></span> <span data-ttu-id="038c7-116">VSTO 和 Visual Studio 2012 Office 开发人员工具简化开发、 测试和部署高级的集成解决方案可以使用 Project 桌面客户端和其他 Office 2013 应用程序，并将与 SharePoint 网站、 列表、 集成和工作流。</span><span class="sxs-lookup"><span data-stu-id="038c7-116">VSTO and Office Developer Tools for Visual Studio 2012 simplify developing, testing, and deploying advanced integration solutions that can use the Project desktop client and other Office 2013 applications, and integrate with SharePoint sites, lists, and workflows.</span></span> 
  
<span data-ttu-id="038c7-117">可以在 Office 商店中销售任务窗格的加载项和面向 Office 和 SharePoint 的其他外接 (请参阅[http://office.microsoft.com/store/](http://office.microsoft.com/en-us/store/)) 与 Project Online 和本地安装一起使用。</span><span class="sxs-lookup"><span data-stu-id="038c7-117">Task pane add-ins and other add-ins for Office and SharePoint can be sold in the Office Store (see [http://office.microsoft.com/store/](http://office.microsoft.com/en-us/store/)) for use with both Project Online and on-premises installations.</span></span> <span data-ttu-id="038c7-118">无法在 Office 商店; 分布式 VBA 宏和 VSTO 外接程序它们旨在用于本地 Project Standard 和 Project Professional。</span><span class="sxs-lookup"><span data-stu-id="038c7-118">VBA macros and VSTO add-ins cannot be distributed in the Office Store; they are designed for local use with Project Standard and Project Professional.</span></span> <span data-ttu-id="038c7-119">您可以将分发在项目中的 VBA 宏。MPP 文件，将其安装在您的计算机上的 Global.MPT 文件，或分发更新 Project Server 2013 中的企业全局模板中。</span><span class="sxs-lookup"><span data-stu-id="038c7-119">You can distribute VBA macros within a project .MPP file, install them in the Global.MPT file on your computer, or distribute them in the enterprise global template in Project Server 2013.</span></span> <span data-ttu-id="038c7-120">VSTO 加载项可通过[ClickOnce](http://msdn.microsoft.com/en-us/library/t71a733d.aspx)部署时，它使轻松更新更安全地分发。</span><span class="sxs-lookup"><span data-stu-id="038c7-120">VSTO add-ins can be distributed more securely through [ClickOnce](http://msdn.microsoft.com/en-us/library/t71a733d.aspx) deployment, which enables easy updates.</span></span> 
  
## <a name="reference"></a><span data-ttu-id="038c7-121">参考</span><span class="sxs-lookup"><span data-stu-id="038c7-121">Reference</span></span>

<span data-ttu-id="038c7-122">[项目的 VBA 开发人员参考](http://msdn.microsoft.com/en-us/library/ee861523%28office.15%29.aspx)包含介绍性和 VBA 帮助文章。</span><span class="sxs-lookup"><span data-stu-id="038c7-122">[Project VBA developer reference](http://msdn.microsoft.com/en-us/library/ee861523%28office.15%29.aspx) Contains introductory and VBA Help articles.</span></span> 
  
## <a name="related-sections"></a><span data-ttu-id="038c7-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="038c7-123">Related sections</span></span>

<span data-ttu-id="038c7-124">[Project Server 2013 体系结构](project-server-2013-architecture.md)显示 Project 客户端与 Project Server 的交互方式。</span><span class="sxs-lookup"><span data-stu-id="038c7-124">[Project Server 2013 architecture](project-server-2013-architecture.md) Shows how the Project clients interact with Project Server.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="038c7-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="038c7-125">See also</span></span>

- [<span data-ttu-id="038c7-126">面向开发人员的 project</span><span class="sxs-lookup"><span data-stu-id="038c7-126">Project for developers</span></span>](http://msdn.microsoft.com/en-us/office/aa905469)
- [<span data-ttu-id="038c7-127">Office 开发中心</span><span class="sxs-lookup"><span data-stu-id="038c7-127">Office developer center</span></span>](https://dev.office.com)
- [<span data-ttu-id="038c7-128">Visual Studio 开发中心</span><span class="sxs-lookup"><span data-stu-id="038c7-128">Visual Studio developer center</span></span>](http://msdn.microsoft.com/en-us/vstudio/aa718325.aspx)
- [<span data-ttu-id="038c7-129">ClickOnce 安全和部署</span><span class="sxs-lookup"><span data-stu-id="038c7-129">ClickOnce Security and Deployment</span></span>](http://msdn.microsoft.com/en-us/library/t71a733d.aspx)
- [<span data-ttu-id="038c7-130">可用字段引用</span><span class="sxs-lookup"><span data-stu-id="038c7-130">Available fields reference</span></span>](https://support.office.com/en-us/article/available-fields-reference-615a4563-1cc3-40f4-b66f-1b17e793a460)

