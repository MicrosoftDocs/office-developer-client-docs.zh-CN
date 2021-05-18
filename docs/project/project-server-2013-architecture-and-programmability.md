---
title: Project Server 2013 体系结构和可编程性
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
f1_keywords:
- architecture
- platform
- Project
- Project architecture
- Project programmability
- Project Server architecture
- Project Server programmability
keywords:
- project 2013， architecture and programmability， Programmability， Project Server，Project 2013， benefits for EPM， Architecture， and Project Server
localization_priority: Normal
ms.assetid: 9ea3b3c1-fb90-454a-b8e6-abc44fca663d
description: 本节中的文章介绍 Enterprise Project Management (EPM) 解决方案的整体体系结构，该解决方案结合了 Project Professional 2013、Project Server 2013、Project Web App 和 SharePoint Server 2013。
ms.openlocfilehash: 44cd5a32b8d3de421ffe3b2d9bf0137146bc4c4e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413785"
---
# <a name="project-server-2013-architecture-and-programmability"></a><span data-ttu-id="9254f-104">Project Server 2013 体系结构和可编程性</span><span class="sxs-lookup"><span data-stu-id="9254f-104">Project Server 2013 architecture and programmability</span></span>

<span data-ttu-id="9254f-105">本节中的文章介绍 Enterprise Project Management (EPM) 解决方案的整体体系结构，该解决方案结合了 Project Professional 2013、Project Server 2013、Project Web App 和 SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9254f-105">The articles in this section describe the overall architecture of the Enterprise Project Management (EPM) solution, which combines Project Professional 2013, Project Server 2013, Project Web App, and SharePoint Server 2013.</span></span>
  
<span data-ttu-id="9254f-106">ProjectServer 2013 使用 .NET Framework 4 构建，是 Project Server 的第三个主要版本，可提供真正的多层体系结构。</span><span class="sxs-lookup"><span data-stu-id="9254f-106">Project Server 2013 is built with the .NET Framework 4 and is the third major release of Project Server to provide a true multitier architecture.</span></span> <span data-ttu-id="9254f-107">对于云访问，Project Server 2013 实现了客户端对象模型 (CSOM) 以及可用于 Web 应用程序、移动应用程序和 Silverlight 应用程序的报表的 OData 服务。</span><span class="sxs-lookup"><span data-stu-id="9254f-107">For cloud access, Project Server 2013 implements a client-side object model (CSOM) and an OData service for reporting that can be used in web applications, mobile applications, and Silverlight applications.</span></span> <span data-ttu-id="9254f-108">对于本地应用程序，客户端可使用 CSOM 或 Project Server 接口 (PSI) 服务。</span><span class="sxs-lookup"><span data-stu-id="9254f-108">For applications on-premises, clients can use either the CSOM or the Project Server Interface (PSI) services.</span></span> 
  
## <a name="introduction-to-project-server-architecture"></a><span data-ttu-id="9254f-109">Project Server 体系结构简介</span><span class="sxs-lookup"><span data-stu-id="9254f-109">Introduction to Project Server architecture</span></span>

<span data-ttu-id="9254f-110">本节中的主题介绍 Enterprise Project Management (EPM) 解决方案的整体体系结构，该解决方案结合了 Project Professional 2013、Project Server 2013、Project Web App 和 SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9254f-110">The topics in this section describe the overall architecture of the Enterprise Project Management (EPM) solution, which combines Project Professional 2013, Project Server 2013, Project Web App, and SharePoint Server 2013.</span></span>
  
<span data-ttu-id="9254f-111">若要以编程方式Project服务器，您应将 CSOM 或 PSI 服务与 Windows Communication Foundation (WCF) 接口一同使用。</span><span class="sxs-lookup"><span data-stu-id="9254f-111">For programmatic access to Project Server, you should use either the CSOM or the PSI services with the Windows Communication Foundation (WCF) interface.</span></span> <span data-ttu-id="9254f-112">PSI 的 ASMX Web 服务接口在 Project Server 2013 中已弃用，但仍可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="9254f-112">The ASMX web service interface of the PSI is deprecated in Project Server 2013, but still works.</span></span> <span data-ttu-id="9254f-113">利用 PSI，可使用数据集实现高效访问，并且可以为服务器端事件创建处理程序。</span><span class="sxs-lookup"><span data-stu-id="9254f-113">The PSI enables efficient access by using datasets and you can create handlers for server-side events.</span></span> <span data-ttu-id="9254f-114">CSOM 本身使用 PSI 访问 Project Server 业务对象层。</span><span class="sxs-lookup"><span data-stu-id="9254f-114">The CSOM itself uses the PSI to access the Project Server business object layer.</span></span> <span data-ttu-id="9254f-115">Project Server 2013 使用数据访问层中的单个数据库，而不是四个 Project 服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="9254f-115">Instead of four Project Server databases, Project Server 2013 uses a single database in the data access layer.</span></span>
  
<span data-ttu-id="9254f-116">ProjectServer 2013 与 SharePoint Server 2013 深度集成。</span><span class="sxs-lookup"><span data-stu-id="9254f-116">Project Server 2013 integrates deeply with SharePoint Server 2013.</span></span> <span data-ttu-id="9254f-117">Project Application Service 可与服务器场中的其他 SharePoint 网站集关联。</span><span class="sxs-lookup"><span data-stu-id="9254f-117">The Project Application Service can be associated with other SharePoint site collections in the farm.</span></span> <span data-ttu-id="9254f-118">Project Server 可对网站集中的 SharePoint 任务列表进行操作和报告，并可以获得完全控制权，这样一来，Project Server 便能将任务列表作为企业项目进行导入和管理。</span><span class="sxs-lookup"><span data-stu-id="9254f-118">Project Server can operate with and report on SharePoint task lists in the site collection, and can also get full control where Project Server imports and manages the task lists as enterprise projects.</span></span> <span data-ttu-id="9254f-119">Project服务器还使用 WF4 Windows Workflow Foundation (4) ，并添加需求管理解决方案的工作流活动。</span><span class="sxs-lookup"><span data-stu-id="9254f-119">Project Server also uses version 4 of the Windows Workflow Foundation (WF4) and adds workflow activities for Demand Management solutions.</span></span>
  
<span data-ttu-id="9254f-120">有关 Project 2013 为开发人员提供的许多新功能以及已弃用的功能的讨论，请参阅[Project 2013](updates-for-developers-in-project-2013.md)中的开发人员更新。</span><span class="sxs-lookup"><span data-stu-id="9254f-120">For a discussion of the many new features that Project 2013 provides for developers, and of the features that are deprecated, see [Updates for developers in Project 2013](updates-for-developers-in-project-2013.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9254f-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="9254f-121">In this section</span></span>

<span data-ttu-id="9254f-122">[Project Server 2013](project-server-2013-architecture.md)体系结构介绍了 Project 2013 平台的主要部分，包括客户端和服务器。</span><span class="sxs-lookup"><span data-stu-id="9254f-122">[Project Server 2013 architecture](project-server-2013-architecture.md) describes the major parts of the Project 2013 platform, including the clients and servers.</span></span> 
  
<span data-ttu-id="9254f-123">[Project Server 可编程](project-server-programmability.md)性讨论 Project Server 2013 的主要扩展性功能、自定义 Project Web App 以及升级为以前的 Project Server 版本构建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9254f-123">[Project Server programmability](project-server-programmability.md) discusses the main extensibility features of Project Server 2013, customization of Project Web App, and upgrading applications that are built for previous Project Server versions.</span></span> 
  
<span data-ttu-id="9254f-124">[What the PSI does and does not do](what-the-psi-does-and-does-not-do.md)描述了可使用 PSI 的方案并列出了 PSI 不能实现的操作。</span><span class="sxs-lookup"><span data-stu-id="9254f-124">[What the PSI does and does not do](what-the-psi-does-and-does-not-do.md) describes scenarios where the PSI can be used and lists things that the PSI cannot do.</span></span> 
  
<span data-ttu-id="9254f-125">[What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md)描述了可使用 CSOM 的方案并列出了 CSOM 不能实现的操作。</span><span class="sxs-lookup"><span data-stu-id="9254f-125">[What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md) describes scenarios where the CSOM can be used and lists things that the CSOM cannot do.</span></span> 
  
### <a name="topics-not-covered"></a><span data-ttu-id="9254f-126">未涵盖的主题</span><span class="sxs-lookup"><span data-stu-id="9254f-126">Topics not covered</span></span>

<span data-ttu-id="9254f-127">体系结构和可编程性部分中的文章未记录 Project 桌面客户端 (Project Standard 2013 和 Project Professional 2013) 或 Project Web App 的功能。</span><span class="sxs-lookup"><span data-stu-id="9254f-127">The articles in the  *Architecture and programmability*  section do not document features of the Project desktop clients (Project Standard 2013 and Project Professional 2013) or Project Web App.</span></span> 
  
<span data-ttu-id="9254f-128">Visual Basic for Applications (VBA) 帮助在 Project Standard 和 Project Professional 中的 Visual Basic 编辑器中可用。</span><span class="sxs-lookup"><span data-stu-id="9254f-128">Visual Basic for Applications (VBA) help is available in the Visual Basic editor within Project Standard and Project Professional.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9254f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9254f-129">See also</span></span>
<span data-ttu-id="9254f-130"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="9254f-130"><a name="bk_addresources"> </a></span></span>

- [<span data-ttu-id="9254f-131">Project 2013 中面向开发人员的更新</span><span class="sxs-lookup"><span data-stu-id="9254f-131">Updates for developers in Project 2013</span></span>](updates-for-developers-in-project-2013.md)
    
- [<span data-ttu-id="9254f-132">开始开发 Project Server 工作流</span><span class="sxs-lookup"><span data-stu-id="9254f-132">Getting started developing Project Server workflows</span></span>](getting-started-developing-project-server-workflows.md)
    

