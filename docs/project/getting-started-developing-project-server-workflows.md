---
title: 开发 Project Server 工作流入门
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 735bbb04-a8c1-46c0-a346-42050f0ac9b1
description: 管理 Project Server 2013 中的过程包括帮助您的工作流的需求管理项目建议和项目组合分析。 本节包含演示如何为 Project Server 中创建工作流的文章。
ms.openlocfilehash: 275f61b7992423a5e10a7ba90b8c76433290343e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779409"
---
# <a name="getting-started-developing-project-server-workflows"></a><span data-ttu-id="05fd6-104">开发 Project Server 工作流入门</span><span class="sxs-lookup"><span data-stu-id="05fd6-104">Getting started developing Project Server workflows</span></span>

<span data-ttu-id="05fd6-105">管理 Project Server 2013 中的过程包括帮助您的工作流的需求管理项目建议和项目组合分析。</span><span class="sxs-lookup"><span data-stu-id="05fd6-105">Demand management processes in Project Server 2013 include workflows that help you manage project proposals and portfolio analyses.</span></span> <span data-ttu-id="05fd6-106">本节包含演示如何为 Project Server 中创建工作流的文章。</span><span class="sxs-lookup"><span data-stu-id="05fd6-106">This section includes articles that show how to create workflows for Project Server.</span></span>
  
<span data-ttu-id="05fd6-107">Project Server 2013 工作流使用的 SharePoint Server 2013 工作流平台，基于版本 4 的 Windows Workflow Foundation (WF4)。</span><span class="sxs-lookup"><span data-stu-id="05fd6-107">Project Server 2013 workflows use the SharePoint Server 2013 workflow platform, which is built on version 4 of Windows Workflow Foundation (WF4).</span></span> <span data-ttu-id="05fd6-108">基于 WF4 的工作流是声明性，这意味着该工作流设计工具将工作流阶段、 操作、 条件和其他元素保存到 XAML 代码，解释在运行时。</span><span class="sxs-lookup"><span data-stu-id="05fd6-108">WF4-based workflows are declarative, which means that the workflow design tool saves workflow stages, actions, conditions, and other elements to XAML code, which is interpreted at run-time.</span></span> <span data-ttu-id="05fd6-109">您可以使用 SharePoint Designer 2013 或 Visual Studio 2012 创建声明性工作流。</span><span class="sxs-lookup"><span data-stu-id="05fd6-109">You can use either SharePoint Designer 2013 or Visual Studio 2012 to create declarative workflows.</span></span> <span data-ttu-id="05fd6-110">工作流需要的工作流管理器客户端 1.0 执行引擎，可以在内部部署解决方案的本地服务器或 Project Online 的解决方案的远程服务器上。</span><span class="sxs-lookup"><span data-stu-id="05fd6-110">A workflow requires the Workflow Manager Client 1.0 execution engine, which can be on a local server for on-premises solutions or on a remote server for Project Online solutions.</span></span>
  
<span data-ttu-id="05fd6-111">您可以使用 SharePoint Designer 2013 创建相对简单的声明性工作流。</span><span class="sxs-lookup"><span data-stu-id="05fd6-111">You can use SharePoint Designer 2013 to create relatively simple declarative workflows.</span></span> <span data-ttu-id="05fd6-112">对于复杂的工作流的可重用工作流模板，您可以使用 Visual Studio 2012 开发和调试 Project Web app 的工作流。</span><span class="sxs-lookup"><span data-stu-id="05fd6-112">For complex workflows, and workflow templates that can be reused, you can use Visual Studio 2012 to develop and debug workflows for Project Web App.</span></span> <span data-ttu-id="05fd6-113">有关详细信息，请参阅[创建 Project 工作流使用 Visual Studio 2012](http://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx)。</span><span class="sxs-lookup"><span data-stu-id="05fd6-113">For more information, see [Creating Project Workflows using Visual Studio 2012](http://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="05fd6-114">测试安装的 Project Server，生产安装，用于开发和测试工作流。</span><span class="sxs-lookup"><span data-stu-id="05fd6-114">Use a test installation of Project Server, not a production installation, to develop and test workflows.</span></span> <span data-ttu-id="05fd6-115">预发布版本的 Project Server 2013 开发的工作流必须要测试的发行版，并且可能需要再次创建和重新部署。</span><span class="sxs-lookup"><span data-stu-id="05fd6-115">Workflows that are developed for pre-release versions of Project Server 2013 must be tested for the release version, and may have to be created again and redeployed.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="05fd6-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="05fd6-116">In this section</span></span>

[<span data-ttu-id="05fd6-117">创建用于命令管理的 Project Server 工作流</span><span class="sxs-lookup"><span data-stu-id="05fd6-117">Create a Project Server workflow for Demand Management</span></span>](create-a-project-server-workflow-for-demand-management.md)
  
## <a name="see-also"></a><span data-ttu-id="05fd6-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05fd6-118">See also</span></span>



[<span data-ttu-id="05fd6-119">批量更新自定义字段和从 Project Online 中的工作流创建项目网站</span><span class="sxs-lookup"><span data-stu-id="05fd6-119">Bulk update custom fields and create project sites from a Project Online workflow</span></span>](bulk-update-custom-fields-and-create-project-sites-from-workflow-in-project.md)


[<span data-ttu-id="05fd6-120">SharePoint Designer 2013 和 Visio 2013 中的工作流开发</span><span class="sxs-lookup"><span data-stu-id="05fd6-120">Workflow development in SharePoint Designer 2013 and Visio 2013</span></span>](http://msdn.microsoft.com/zh-cn/library/jj163272%28office.15%29.aspx)
  
[<span data-ttu-id="05fd6-121">SharePoint 工作流的新增功能</span><span class="sxs-lookup"><span data-stu-id="05fd6-121">What's new in workflows for SharePoint 2013</span></span>](http://msdn.microsoft.com/zh-cn/library/jj163177.aspx)
  
[<span data-ttu-id="05fd6-122">使用 Visual Studio 开发 SharePoint 2013 工作流</span><span class="sxs-lookup"><span data-stu-id="05fd6-122">Develop SharePoint 2013 workflows using Visual Studio</span></span>](http://msdn.microsoft.com/zh-cn/library/jj163199.aspx)
  
[<span data-ttu-id="05fd6-123">创建项目工作流使用 Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="05fd6-123">Creating Project Workflows using Visual Studio 2012</span></span>](http://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx)
  
[<span data-ttu-id="05fd6-124">Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="05fd6-124">Windows Workflow Foundation</span></span>](http://msdn.microsoft.com/zh-cn/library/dd489441.aspx)
  
[<span data-ttu-id="05fd6-125">开发人员的简介到 Windows Workflow Foundation (WF).NET 4 中</span><span class="sxs-lookup"><span data-stu-id="05fd6-125">A developer's introduction to Windows Workflow Foundation (WF) in .NET 4</span></span>](http://msdn.microsoft.com/zh-cn/library/ee342461.aspx)
  
[<span data-ttu-id="05fd6-126">(White paper) 的需求管理漫游指南</span><span class="sxs-lookup"><span data-stu-id="05fd6-126">Hitchhiker's guide to demand management (white paper)</span></span>](http://msdn.microsoft.com/zh-cn/library/ff973112.aspx)

