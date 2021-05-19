---
title: 开始开发 Project Server 工作流
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 735bbb04-a8c1-46c0-a346-42050f0ac9b1
description: Project Server 2013 中的需求管理流程包括可帮助您管理项目建议和项目组合分析的工作流。 本节中的文章说明了如何为 Project Server 创建工作流。
ms.openlocfilehash: 0a09022e63528f50ee4f0c8bd69bd6c34c5d8753
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344469"
---
# <a name="getting-started-developing-project-server-workflows"></a><span data-ttu-id="526f4-104">开始开发 Project Server 工作流</span><span class="sxs-lookup"><span data-stu-id="526f4-104">Getting started developing Project Server workflows</span></span>

<span data-ttu-id="526f4-105">Project Server 2013 中的需求管理流程包括可帮助您管理项目建议和项目组合分析的工作流。</span><span class="sxs-lookup"><span data-stu-id="526f4-105">Demand management processes in Project Server 2013 include workflows that help you manage project proposals and portfolio analyses.</span></span> <span data-ttu-id="526f4-106">本节中的文章说明了如何为 Project Server 创建工作流。</span><span class="sxs-lookup"><span data-stu-id="526f4-106">This section includes articles that show how to create workflows for Project Server.</span></span>
  
<span data-ttu-id="526f4-107">Project服务器 2013 工作流使用 SharePoint Server 2013 工作流平台，该平台基于 Windows Workflow Foundation (WF4 版本 4) 。</span><span class="sxs-lookup"><span data-stu-id="526f4-107">Project Server 2013 workflows use the SharePoint Server 2013 workflow platform, which is built on version 4 of Windows Workflow Foundation (WF4).</span></span> <span data-ttu-id="526f4-108">基于 WF4 的工作流是声明性工作流，这意味着工作流设计工具将工作流阶段、操作、条件和其他元素保存到 XAML 代码中，这将运行时进行解释。</span><span class="sxs-lookup"><span data-stu-id="526f4-108">WF4-based workflows are declarative, which means that the workflow design tool saves workflow stages, actions, conditions, and other elements to XAML code, which is interpreted at run-time.</span></span> <span data-ttu-id="526f4-109">可以使用 Designer 2013 或 SharePoint 2012 Visual Studio声明性工作流。</span><span class="sxs-lookup"><span data-stu-id="526f4-109">You can use either SharePoint Designer 2013 or Visual Studio 2012 to create declarative workflows.</span></span> <span data-ttu-id="526f4-110">工作流需要 工作流管理器 Client 1.0 执行引擎，该引擎可以位于本地解决方案的本地服务器上，也可以位于远程服务器上Project Online解决方案。</span><span class="sxs-lookup"><span data-stu-id="526f4-110">A workflow requires the Workflow Manager Client 1.0 execution engine, which can be on a local server for on-premises solutions or on a remote server for Project Online solutions.</span></span>
  
<span data-ttu-id="526f4-111">您可以使用 SharePoint Designer 2013 创建相对简单的声明性工作流。</span><span class="sxs-lookup"><span data-stu-id="526f4-111">You can use SharePoint Designer 2013 to create relatively simple declarative workflows.</span></span> <span data-ttu-id="526f4-112">对于可以重复使用的复杂工作流和工作流模板，您可以使用 Visual Studio 2012 开发和调试 Project Web App。</span><span class="sxs-lookup"><span data-stu-id="526f4-112">For complex workflows, and workflow templates that can be reused, you can use Visual Studio 2012 to develop and debug workflows for Project Web App.</span></span> <span data-ttu-id="526f4-113">有关详细信息，请参阅[Creating Project Workflows using Visual Studio 2012](https://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx)。</span><span class="sxs-lookup"><span data-stu-id="526f4-113">For more information, see [Creating Project Workflows using Visual Studio 2012](https://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="526f4-114">使用 Project Server 的测试安装而非生产安装来开发和测试工作流。</span><span class="sxs-lookup"><span data-stu-id="526f4-114">Use a test installation of Project Server, not a production installation, to develop and test workflows.</span></span> <span data-ttu-id="526f4-115">必须为发布版本测试为 Project Server 2013 的预发行版开发的工作流，并且可能需要再次创建和重新部署。</span><span class="sxs-lookup"><span data-stu-id="526f4-115">Workflows that are developed for pre-release versions of Project Server 2013 must be tested for the release version, and may have to be created again and redeployed.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="526f4-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="526f4-116">In this section</span></span>

[<span data-ttu-id="526f4-117">为需求Project创建一个 Project Server 工作流</span><span class="sxs-lookup"><span data-stu-id="526f4-117">Create a Project Server workflow for Demand Management</span></span>](create-a-project-server-workflow-for-demand-management.md)
  
## <a name="see-also"></a><span data-ttu-id="526f4-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="526f4-118">See also</span></span>



[<span data-ttu-id="526f4-119">批量更新自定义域，然后从工作流创建Project Online网站</span><span class="sxs-lookup"><span data-stu-id="526f4-119">Bulk update custom fields and create project sites from a Project Online workflow</span></span>](bulk-update-custom-fields-and-create-project-sites-from-workflow-in-project.md)


[<span data-ttu-id="526f4-120">SharePoint Designer 2013 和 Visio 2013 中的工作流开发</span><span class="sxs-lookup"><span data-stu-id="526f4-120">Workflow development in SharePoint Designer 2013 and Visio 2013</span></span>](https://msdn.microsoft.com/library/jj163272%28office.15%29.aspx)
  
[<span data-ttu-id="526f4-121">SharePoint 工作流的新增功能</span><span class="sxs-lookup"><span data-stu-id="526f4-121">What's new in workflows for SharePoint 2013</span></span>](https://msdn.microsoft.com/library/jj163177.aspx)
  
[<span data-ttu-id="526f4-122">使用 Visual Studio 开发 SharePoint 2013 工作流</span><span class="sxs-lookup"><span data-stu-id="526f4-122">Develop SharePoint 2013 workflows using Visual Studio</span></span>](https://msdn.microsoft.com/library/jj163199.aspx)
  
[<span data-ttu-id="526f4-123">使用 Project 2012 创建Visual Studio工作流</span><span class="sxs-lookup"><span data-stu-id="526f4-123">Creating Project Workflows using Visual Studio 2012</span></span>](https://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx)
  
[<span data-ttu-id="526f4-124">Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="526f4-124">Windows Workflow Foundation</span></span>](https://msdn.microsoft.com/library/dd489441.aspx)
  
[<span data-ttu-id="526f4-125">开发人员对 .NET 4 Windows Workflow Foundation (WF) 简介</span><span class="sxs-lookup"><span data-stu-id="526f4-125">A developer's introduction to Windows Workflow Foundation (WF) in .NET 4</span></span>](https://msdn.microsoft.com/library/ee342461.aspx)
  
[<span data-ttu-id="526f4-126">将需求管理指南 (白皮书) </span><span class="sxs-lookup"><span data-stu-id="526f4-126">Hitchhiker's guide to demand management (white paper)</span></span>](https://msdn.microsoft.com/library/ff973112.aspx)

