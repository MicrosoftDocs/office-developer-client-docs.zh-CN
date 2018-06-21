---
title: 开发包含代码的表单模板入门
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- form templates [infopath 2007], getting started,managed code form templates [InfoPath 2007], getting started,InfoPath 2007, getting started
localization_priority: Normal
ms.assetid: 66468447-2012-4497-b371-c61f64a8bb49
description: 本节提供有关如何开始创建托管代码表单模板的信息，这些模板可以处理由 Microsoft.Office.InfoPath 命名空间的成员提供的 InfoPath 对象模型。
ms.openlocfilehash: a4e4e8a4e01dc8d0fbfe9c5cbed0ae4b85b51e94
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19773980"
---
# <a name="getting-started-developing-form-templates-with-code"></a><span data-ttu-id="0a5f7-104">开发包含代码的表单模板入门</span><span class="sxs-lookup"><span data-stu-id="0a5f7-104">Getting Started Developing Form Templates with Code</span></span>

<span data-ttu-id="0a5f7-105">本节提供有关如何开始创建托管代码表单模板的信息，这些模板可以处理由 **Microsoft.Office.InfoPath** 命名空间的成员提供的 InfoPath 对象模型。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-105">This section provides information on how to get started creating managed code form templates that work with the InfoPath object model provided by members of the **Microsoft.Office.InfoPath** namespace.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="0a5f7-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="0a5f7-106">In this section</span></span>

[<span data-ttu-id="0a5f7-107">为 InfoPath 开发人员提供的新功能</span><span class="sxs-lookup"><span data-stu-id="0a5f7-107">What's New for InfoPath Developers</span></span>](what-s-new-for-infopath-developers.md)
  
> <span data-ttu-id="0a5f7-108">提供有关开发人员所关注的新功能和改进的信息。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-108">Provides information on new features and improvements that are of interest to developers.</span></span>
    
[<span data-ttu-id="0a5f7-109">了解 InfoPath 对象模型和开发环境</span><span class="sxs-lookup"><span data-stu-id="0a5f7-109">Understanding InfoPath Object Models and Development Environment</span></span>](understanding-infopath-object-models-and-development-environment.md)
  
> <span data-ttu-id="0a5f7-110">描述用于开发表单模板中的业务逻辑的两种编程模型，以及 InfoPath 支持的 Visual Studio 2008 开发环境。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-110">Describes the two kinds of programming models for developing business logic in form templates, and the Visual Studio 2012 development environment supported by InfoPath.</span></span>
    
[<span data-ttu-id="0a5f7-111">使用 Visual Studio 开发</span><span class="sxs-lookup"><span data-stu-id="0a5f7-111">Develop with Visual Studio</span></span>](how-to-develop-with-visual-studio.md)
  
> <span data-ttu-id="0a5f7-112">描述如何安装 Visual Studio 2008 环境。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-112">Describes how to install the Visual Studio 2012 environment.</span></span>
    
[<span data-ttu-id="0a5f7-113">安装 Visual Studio tools for Applications 本地.NET Framework 帮助</span><span class="sxs-lookup"><span data-stu-id="0a5f7-113">Install Local .NET Framework Help for Visual Studio Tools for Applications</span></span>](how-to-install-net-framework-help-for-visual-studio-tools-for-applications.md)
  
> <span data-ttu-id="0a5f7-114">描述如何安装 .NET Framework 文档的本地副本，以便在 Visual Studio 2008 环境中脱机使用。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-114">Describes how to install a local copy of the .NET Framework documentation for offline use in the Visual Studio 2012 environment.</span></span>
    
[<span data-ttu-id="0a5f7-115">添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="0a5f7-115">Add an Event Handler</span></span>](how-to-add-an-event-handler.md)
  
> <span data-ttu-id="0a5f7-116">描述如何向 InfoPath 托管代码表单模板添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-116">Describes how to add event handlers to an InfoPath managed code form template.</span></span> 
    
[<span data-ttu-id="0a5f7-117">预览和调试包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="0a5f7-117">Preview and Debug InfoPath Form Templates with Code</span></span>](how-to-preview-and-debug-infopath-form-templates-with-code.md)
  
> <span data-ttu-id="0a5f7-118">描述如何预览和调试 InfoPath 托管代码表单模板。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-118">Describes how to preview and debug InfoPath managed code form templates.</span></span>
    
[<span data-ttu-id="0a5f7-119">预览和调试需要完全信任的表单模板</span><span class="sxs-lookup"><span data-stu-id="0a5f7-119">Preview and Debug Form Templates that Require Full Trust</span></span>](how-to-preview-and-debug-form-templates-that-require-full-trust.md)
  
> <span data-ttu-id="0a5f7-120">描述如何预览和调试包含需要完全信任的业务逻辑的 InfoPath 托管代码表单模板。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-120">Describes how to preview and debug InfoPath managed code form templates that contain business logic that requires full trust.</span></span>
    
[<span data-ttu-id="0a5f7-121">演练：创建具有代码的基本表单模板</span><span class="sxs-lookup"><span data-stu-id="0a5f7-121">Walkthrough: Creating a Basic Form Template with Code</span></span>](walkthrough-creating-a-basic-form-template-with-code.md)
  
> <span data-ttu-id="0a5f7-122">介绍如何创建和调试基本 InfoPath 托管代码表单模板的分步指南</span><span class="sxs-lookup"><span data-stu-id="0a5f7-122">A step-by-step guide that provides an introduction to creating and debugging a basic InfoPath managed code form template</span></span> 
    
[<span data-ttu-id="0a5f7-123">日志进行调试字段的值</span><span class="sxs-lookup"><span data-stu-id="0a5f7-123">Log Values to a Field for Debugging</span></span>](how-to-log-values-to-a-field-for-debugging.md)
  
> <span data-ttu-id="0a5f7-124">介绍如何创建多行域和帮助程序函数用于记录调试信息。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-124">Describes how to create a multi-line field and a helper function for logging debugging information.</span></span>
    
[<span data-ttu-id="0a5f7-125">打开或转换使用 InfoPath 工具包创建的表单模板</span><span class="sxs-lookup"><span data-stu-id="0a5f7-125">Open or Convert a Form Template Created with the InfoPath Toolkit</span></span>](how-to-open-or-convert-a-form-template-created-with-the-infopath-toolkit.md)
  
> <span data-ttu-id="0a5f7-126">描述如何打开或转换使用 InfoPath 2003 Toolkit 和 Visual Studio .NET 或 InfoPath 2003 Toolkit for Visual Studio 2005 创建的托管代码表单模板。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-126">Describes how to open or convert a managed code form template created with the InfoPath 2003 Toolkit and Visual Studio .NET or the InfoPath 2003 Toolkit for Visual Studio 2005.</span></span>
    
[<span data-ttu-id="0a5f7-127">部署包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="0a5f7-127">Deploy InfoPath Form Templates with Code</span></span>](how-to-deploy-infopath-form-templates-with-code.md)
  
> <span data-ttu-id="0a5f7-128">描述如何部署 InfoPath 托管代码表单模板。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-128">Describes how to deploy InfoPath managed code form templates.</span></span>
    
[<span data-ttu-id="0a5f7-129">在包含代码的 InfoPath 表单模板中如何...</span><span class="sxs-lookup"><span data-stu-id="0a5f7-129">How Do I...In InfoPath Form Templates with Code</span></span>](how-do-iin-infopath-form-templates-with-code.md)
  
> <span data-ttu-id="0a5f7-130">提供 InfoPath 托管代码表单模板开发人员的常见任务汇总。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-130">Provides a summary of common tasks for developers of InfoPath managed code form templates.</span></span>
    
[<span data-ttu-id="0a5f7-131">使用 XPathNavigator 和 XPathNodeIterator 类</span><span class="sxs-lookup"><span data-stu-id="0a5f7-131">Work with the XPathNavigator and XPathNodeIterator Classes</span></span>](how-to-work-with-the-xpathnavigator-and-xpathnodeiterator-classes.md)
  
> <span data-ttu-id="0a5f7-132">提供了使用 **XPathNavigator** 和 **XPathNodeIterator** 类来处理 XML 数据的 InfoPath 托管代码对象模型成员的汇总。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-132">Provides a summary of the members of the InfoPath managed code object model that use the **XPathNavigator** and **XPathNodeIterator** classes to work with XML data.</span></span> 
    
[<span data-ttu-id="0a5f7-133">使用 SharePoint 对象模型成员</span><span class="sxs-lookup"><span data-stu-id="0a5f7-133">Use SharePoint Object Model Members</span></span>](how-to-use-sharepoint-object-model-members.md)
  
> <span data-ttu-id="0a5f7-134">介绍如何创建对 Microsoft.SharePoint 程序集的引用，以便能够通过表单代码针对该程序集的对象模型编写代码。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-134">Describes how to create a reference to the Microsoft.SharePoint assembly so that you can write code against its object model from form code.</span></span>
    
[<span data-ttu-id="0a5f7-135">发布包含代码的表单</span><span class="sxs-lookup"><span data-stu-id="0a5f7-135">Publishing Forms with Code</span></span>](publishing-forms-with-code.md)
  
> <span data-ttu-id="0a5f7-136">描述发布沙盒解决方案和管理员部署的解决方案的不同之处。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-136">Describes the differences between publishing sandboxed solutions and administrator-deployed solutions.</span></span>
    
[<span data-ttu-id="0a5f7-137">示例沙盒解决方案</span><span class="sxs-lookup"><span data-stu-id="0a5f7-137">Sample Sandboxed Solutions</span></span>](sample-sandboxed-solutions.md)
  
> <span data-ttu-id="0a5f7-138">提供两个示例，演示您可在 InfoPath 沙盒解决方案中编写的代码的种类。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-138">Provides two examples that show the kind of code that you can write in an InfoPath sandboxed solution.</span></span>
    
[<span data-ttu-id="0a5f7-139">可供 InfoPath 表单模板开发人员使用的其他资源</span><span class="sxs-lookup"><span data-stu-id="0a5f7-139">Additional Resources for InfoPath Form Template Developers</span></span>](additional-resources-for-infopath-form-template-developers.md)
  
> <span data-ttu-id="0a5f7-140">如何查找可供 InfoPath 开发人员使用的其他信息来源。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-140">How to find additional sources of information for InfoPath developers.</span></span>
    

