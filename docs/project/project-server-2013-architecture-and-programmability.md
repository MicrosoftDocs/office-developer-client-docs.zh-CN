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
- project 2013、 EPM、 体系结构和 Project Server 体系结构和可编程性，可编程性 （英文）、 Project Server、 Project 2013 的好处
localization_priority: Normal
ms.assetid: 9ea3b3c1-fb90-454a-b8e6-abc44fca663d
description: 本节中的文章介绍了 Enterprise Project Management (EPM) 解决方案，从而结合使用 Project Professional 2013、 Project Server 2013、 Project Web App 和 SharePoint Server 2013 的整体体系结构。
ms.openlocfilehash: 6b5ab94968dbb996a370e0e5abb89813f5e41ef7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779554"
---
# <a name="project-server-2013-architecture-and-programmability"></a><span data-ttu-id="5eb7a-104">Project Server 2013 体系结构和可编程性</span><span class="sxs-lookup"><span data-stu-id="5eb7a-104">Project Server 2013 architecture and programmability</span></span>

<span data-ttu-id="5eb7a-105">本节中的文章介绍了 Enterprise Project Management (EPM) 解决方案，从而结合使用 Project Professional 2013、 Project Server 2013、 Project Web App 和 SharePoint Server 2013 的整体体系结构。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-105">The articles in this section describe the overall architecture of the Enterprise Project Management (EPM) solution, which combines Project Professional 2013, Project Server 2013, Project Web App, and SharePoint Server 2013.</span></span>
  
<span data-ttu-id="5eb7a-106">Project Server 2013 使用.NET Framework 4 和是 Project Server 提供的则返回 true 的多层体系结构的第三个主要版本。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-106">Project Server 2013 is built with the .NET Framework 4 and is the third major release of Project Server to provide a true multitier architecture.</span></span> <span data-ttu-id="5eb7a-107">云访问 Project Server 2013 中的 web 应用程序、 移动应用程序和 Silverlight 应用程序实现客户端对象模型 (CSOM) 和可用于报告的 OData 服务。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-107">For cloud access, Project Server 2013 implements a client-side object model (CSOM) and an OData service for reporting that can be used in web applications, mobile applications, and Silverlight applications.</span></span> <span data-ttu-id="5eb7a-108">对于应用程序的本地客户端可以使用 CSOM 或 Project Server 接口 (PSI) 的服务。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-108">For applications on-premises, clients can use either the CSOM or the Project Server Interface (PSI) services.</span></span> 
  
## <a name="introduction-to-project-server-architecture"></a><span data-ttu-id="5eb7a-109">Project Server 体系结构简介</span><span class="sxs-lookup"><span data-stu-id="5eb7a-109">Introduction to Project Server architecture</span></span>

<span data-ttu-id="5eb7a-110">本节中的主题介绍 Enterprise Project Management (EPM) 解决方案，从而结合使用 Project Professional 2013、 Project Server 2013、 Project Web App 和 SharePoint Server 2013 的整体体系结构。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-110">The topics in this section describe the overall architecture of the Enterprise Project Management (EPM) solution, which combines Project Professional 2013, Project Server 2013, Project Web App, and SharePoint Server 2013.</span></span>
  
<span data-ttu-id="5eb7a-111">以编程方式访问 Project Server，您应与 Windows Communication Foundation (WCF) 接口中使用 CSOM 或 PSI 服务。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-111">For programmatic access to Project Server, you should use either the CSOM or the PSI services with the Windows Communication Foundation (WCF) interface.</span></span> <span data-ttu-id="5eb7a-112">PSI 的 ASMX web 服务界面在 Project Server 2013 中已弃用，但仍有效。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-112">The ASMX web service interface of the PSI is deprecated in Project Server 2013, but still works.</span></span> <span data-ttu-id="5eb7a-113">PSI 使用数据集启用高效的访问，并可以创建的服务器端事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-113">The PSI enables efficient access by using datasets and you can create handlers for server-side events.</span></span> <span data-ttu-id="5eb7a-114">CSOM 本身使用 PSI 访问的 Project Server 业务对象层。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-114">The CSOM itself uses the PSI to access the Project Server business object layer.</span></span> <span data-ttu-id="5eb7a-115">而不是四个 Project Server 数据库，Project Server 2013 使用数据访问层中的单个数据库。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-115">Instead of four Project Server databases, Project Server 2013 uses a single database in the data access layer.</span></span>
  
<span data-ttu-id="5eb7a-116">Project Server 2013 与 SharePoint Server 2013 深集成。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-116">Project Server 2013 integrates deeply with SharePoint Server 2013.</span></span> <span data-ttu-id="5eb7a-117">Project 应用程序服务可与其他服务器场中的 SharePoint 网站集相关联。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-117">The Project Application Service can be associated with other SharePoint site collections in the farm.</span></span> <span data-ttu-id="5eb7a-118">Project Server 可以与运行并报告任务列表企业项目作为 SharePoint 任务列表中的网站集和可以也会获得 Project Server 其中导入和管理的完全控制。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-118">Project Server can operate with and report on SharePoint task lists in the site collection, and can also get full control where Project Server imports and manages the task lists as enterprise projects.</span></span> <span data-ttu-id="5eb7a-119">Project Server 也使用的 Windows Workflow Foundation (WF4) 版本 4，并添加工作流活动的需求管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-119">Project Server also uses version 4 of the Windows Workflow Foundation (WF4) and adds workflow activities for Demand Management solutions.</span></span>
  
<span data-ttu-id="5eb7a-120">Project 2013 为开发人员提供的许多新功能和已被弃用的功能的讨论，请参阅[Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-120">For a discussion of the many new features that Project 2013 provides for developers, and of the features that are deprecated, see [Updates for developers in Project 2013](updates-for-developers-in-project-2013.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5eb7a-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="5eb7a-121">In this section</span></span>

<span data-ttu-id="5eb7a-122">[Project Server 2013 architecture](project-server-2013-architecture.md)介绍 Project 2013 平台，包括客户端和服务器的主要部分。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-122">[Project Server 2013 architecture](project-server-2013-architecture.md) describes the major parts of the Project 2013 platform, including the clients and servers.</span></span> 
  
<span data-ttu-id="5eb7a-123">[Project Server programmability](project-server-programmability.md)讨论了 Project Server 2013，自定义 Project Web App 和 Project Server 的早期版本构建的升级应用程序的主要扩展性功能。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-123">[Project Server programmability](project-server-programmability.md) discusses the main extensibility features of Project Server 2013, customization of Project Web App, and upgrading applications that are built for previous Project Server versions.</span></span> 
  
<span data-ttu-id="5eb7a-124">[What the PSI does and does not do](what-the-psi-does-and-does-not-do.md)描述了可使用 PSI 的方案并列出了 PSI 不能实现的操作。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-124">[What the PSI does and does not do](what-the-psi-does-and-does-not-do.md) describes scenarios where the PSI can be used and lists things that the PSI cannot do.</span></span> 
  
<span data-ttu-id="5eb7a-125">[What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md)描述了可使用 CSOM 的方案并列出了 CSOM 不能实现的操作。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-125">[What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md) describes scenarios where the CSOM can be used and lists things that the CSOM cannot do.</span></span> 
  
### <a name="topics-not-covered"></a><span data-ttu-id="5eb7a-126">未涵盖的主题</span><span class="sxs-lookup"><span data-stu-id="5eb7a-126">Topics not covered</span></span>

<span data-ttu-id="5eb7a-127">*体系结构和可编程性*部分中的文章未记录 Project 桌面客户端 （Project Standard 2013 和 Project Professional 2013） 或 Project Web App 的功能。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-127">The articles in the  *Architecture and programmability*  section do not document features of the Project desktop clients (Project Standard 2013 and Project Professional 2013) or Project Web App.</span></span> 
  
<span data-ttu-id="5eb7a-128">Visual Basic for Applications (VBA) 帮助在 Project Standard 和 Project Professional 中的 Visual Basic 编辑器中可用。</span><span class="sxs-lookup"><span data-stu-id="5eb7a-128">Visual Basic for Applications (VBA) help is available in the Visual Basic editor within Project Standard and Project Professional.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5eb7a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5eb7a-129">See also</span></span>
<span data-ttu-id="5eb7a-130"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="5eb7a-130"></span></span>

- [<span data-ttu-id="5eb7a-131">Project 2013 中面向开发人员的更新</span><span class="sxs-lookup"><span data-stu-id="5eb7a-131">Updates for developers in Project 2013</span></span>](updates-for-developers-in-project-2013.md)
    
- [<span data-ttu-id="5eb7a-132">开发 Project Server 工作流入门</span><span class="sxs-lookup"><span data-stu-id="5eb7a-132">Getting started developing Project Server workflows</span></span>](getting-started-developing-project-server-workflows.md)
    

