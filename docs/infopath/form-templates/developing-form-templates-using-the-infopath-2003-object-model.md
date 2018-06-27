---
title: 使用 InfoPath 2003 对象模型开发表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- form templates [infopath 2007], using infopath 2003 object model,InfoPath 2003-compatible form templates,InfoPath 2007, developing form templates using InfoPath 2003 object model,object models [InfoPath 2003], developing managed code form templates
localization_priority: Normal
ms.assetid: c74cbcd0-4fe6-4eb7-a05c-f61e1868c42b
description: Microsoft InfoPath 继续支持利用 Microsoft Office InfoPath 2003 Toolkit for Visual Studio .NET 或 Visual Studio 2005 Tools for the Microsoft Office System 创建的、且具有依据 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间的成员编写的业务逻辑的表单模板项目。本节中的主题将此命名空间的类型和成员称为 InfoPath 2003 兼容对象模型，或简称为 InfoPath 2003 对象模型。InfoPath 还支持通过 Microsoft Office InfoPath 2007 创建的、使用 InfoPath 2003 兼容对象模型的表单模板项目。此外，还可以利用 InfoPath 创建使用 InfoPath 2003 兼容对象模型的新表单模板对象，以便为 Office InfoPath 2007 用户保留向后兼容性。本节中的所有主题专门讲述如何创建和开发使用 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间提供的 InfoPath 2003 兼容对象模型的表单模板。
ms.openlocfilehash: 5d949242068586c752e7a92fa53792cda9ececea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773965"
---
# <a name="developing-form-templates-using-the-infopath-2003-object-model"></a><span data-ttu-id="b2564-108">使用 InfoPath 2003 对象模型开发表单模板</span><span class="sxs-lookup"><span data-stu-id="b2564-108">Developing Form Templates Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="b2564-p102">Microsoft InfoPath 继续支持利用 Microsoft Office InfoPath 2003 Toolkit for Visual Studio .NET 或 Visual Studio 2005 Tools for the Microsoft Office System 创建的、且具有依据 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间的成员编写的业务逻辑的表单模板项目。本节中的主题将此命名空间的类型和成员称为 InfoPath 2003 兼容对象模型，或简称为 InfoPath 2003 对象模型。InfoPath 还支持通过 Microsoft Office InfoPath 2007 创建的、使用 InfoPath 2003 兼容对象模型的表单模板项目。此外，还可以利用 InfoPath 创建使用 InfoPath 2003 兼容对象模型的新表单模板对象，以便为 Office InfoPath 2007 用户保留向后兼容性。本节中的所有主题专门讲述如何创建和开发使用 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的 InfoPath 2003 兼容对象模型的表单模板。</span><span class="sxs-lookup"><span data-stu-id="b2564-p102">Microsoft InfoPath continues to support form template projects created with Microsoft Office InfoPath 2003 Toolkit for Visual Studio .NET or Visual Studio 2005 Tools for the Microsoft Office System that have business logic written against members of the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace. The topics in this section refer to the types and members of this namespace as the InfoPath 2003-compatible object model or simply the InfoPath 2003 object model. InfoPath also supports form template projects created with Microsoft Office InfoPath 2007 that use the InfoPath 2003-compatible object model. In addition, you can use InfoPath to create new form template projects that use InfoPath 2003-compatible object model to retain backward compatibility for users of Office InfoPath 2007. All topics in this section are specific to creating and developing form templates that work with the InfoPath 2003-compatible object model provided by the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b2564-p103">[!重要信息] 尽管 InfoPath 仍支持使用 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的托管代码对象模型来创建业务逻辑，但是对于部署到 Microsoft SharePoint Server 2010（带有 InfoPath Forms Services）且启用浏览器功能的表单模板，并不支持使用此对象模型编写的业务逻辑。启用浏览器功能的表单模板必须使用由 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的成员提供的新的 InfoPath 托管代码对象模型，来创建自定义业务逻辑。有关创建含有用 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间成员编写的业务逻辑的表单模板的详细信息，请参阅 [开发包含代码的 InfoPath 表单模板](developing-infopath-form-templates-with-code.md)。 > 另请注意，利用 Visual Studio 2008 编译的表单模板的用户必须在其计算机上安装 Microsoft .NET Framework 2.0 或更高版本，而利用 Visual Studio .NET 2003 编译的表单模板的用户只需在其计算机上安装 Microsoft .NET Framework 1.1。</span><span class="sxs-lookup"><span data-stu-id="b2564-p103">Although creating business logic with the managed-code object model provided by the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace is still supported by InfoPath, business logic written using this object model it is not supported for browser-enabled form templates deployed to Microsoft SharePoint Server 2010 with InfoPath Forms Services. Browser-enabled form templates must use the new InfoPath managed code object model provided by members of the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace for custom business logic. For more information about creating form templates with business logic written with members of the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace, see [Developing InfoPath Form Templates with Code](developing-infopath-form-templates-with-code.md). > Also, note that users of form templates compiled with Visual Studio 2012 must have Microsoft .NET Framework 2.0 or later installed on their computers. Users of form templates compiled with Visual Studio .NET 2003 are only required to have Microsoft .NET Framework 1.1 on their computers.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="b2564-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="b2564-119">In this section</span></span>

[<span data-ttu-id="b2564-120">使用 InfoPath 2003 对象模型开发表单模板入门</span><span class="sxs-lookup"><span data-stu-id="b2564-120">Getting Started Developing Form Templates Using the InfoPath 2003 Object Model</span></span>](get-started-developing-form-templates-using-infopath-object-model.md)
  
> <span data-ttu-id="b2564-121">提供有关如何开始创建托管代码表单模板（使用 InfoPath 2003 兼容对象模型）的信息。</span><span class="sxs-lookup"><span data-stu-id="b2564-121">Provides information about how to start creating managed code form templates that work with the InfoPath 2003-compatible object model.</span></span>
    
[<span data-ttu-id="b2564-122">使用 InfoPath 2003 对象模型创建表单模板</span><span class="sxs-lookup"><span data-stu-id="b2564-122">Creating Form Templates Using the InfoPath 2003 Object Model</span></span>](creating-form-templates-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="b2564-123">讨论初始化和清理代码、如何添加事件处理程序、如何调试和部署托管代码表单模板、线程支持以及如何使用 InfoPath 托管代码解决方案中的 Microsoft XML Core Services (MSXML)。</span><span class="sxs-lookup"><span data-stu-id="b2564-123">Discusses initialization and clean-up code, how to add event handlers, how to debug and deploy managed-code form templates, threading support, and working with Microsoft XML Core Services (MSXML) from InfoPath managed-code solutions.</span></span>
    
[<span data-ttu-id="b2564-124">具有代码的 InfoPath 表单模板中的安全性</span><span class="sxs-lookup"><span data-stu-id="b2564-124">Security in InfoPath Form Templates with Code</span></span>](security-in-infopath-form-templates-with-code.md)
  
> <span data-ttu-id="b2564-125">讨论使用托管代码的 InfoPath 表单模板的安全模型，调试完全信任的 InfoPath 表单模板以及相关的安全过程。</span><span class="sxs-lookup"><span data-stu-id="b2564-125">Discusses the security model for InfoPath form templates that use managed code, debugging fully-trusted InfoPath form templates, and related security procedures.</span></span>
    
[<span data-ttu-id="b2564-126">了解 InfoPath 2003 对象模型</span><span class="sxs-lookup"><span data-stu-id="b2564-126">Understanding the InfoPath 2003 Object Model</span></span>](understanding-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="b2564-127">讨论 InfoPath 2003 兼容对象模型，以及使用该对象模型的托管代码表单模板的常见编程任务。</span><span class="sxs-lookup"><span data-stu-id="b2564-127">Discusses the InfoPath 2003-compatible object model, and common programming tasks for managed code form templates that work with that object model.</span></span>
    
[<span data-ttu-id="b2564-128">使用 InfoPath 2003 对象模型的表单模板的疑难解答</span><span class="sxs-lookup"><span data-stu-id="b2564-128">Troubleshooting Form Templates That Use the InfoPath 2003 Object Model</span></span>](troubleshoot-form-templates-that-use-infopath-object-model.md)
  
> <span data-ttu-id="b2564-129">包含用于解决您在创建使用 InfoPath 2003 兼容对象模型的托管代码表单模板时可能遇到的常见问题的提示。</span><span class="sxs-lookup"><span data-stu-id="b2564-129">Contains tips for solving common problems that you might encounter when creating managed-code form templates that work with the InfoPath 2003-compatible object model.</span></span>
    
## <a name="related-sections"></a><span data-ttu-id="b2564-130">相关章节</span><span class="sxs-lookup"><span data-stu-id="b2564-130">Related sections</span></span>

[<span data-ttu-id="b2564-131">InfoPath 开发人员门户</span><span class="sxs-lookup"><span data-stu-id="b2564-131">InfoPath Developer Portal</span></span>](http://go.microsoft.com/fwlink?LinkID=11689)
  
> <span data-ttu-id="b2564-132">包含许多链接，这些链接指向有关构建自定义 InfoPath 解决方案的技术文章、代码示例、下载内容、支持以及其他 MSDN 文档。</span><span class="sxs-lookup"><span data-stu-id="b2564-132">Contains links to technical articles, code samples, downloads, support, and other MSDN documentation on building custom InfoPath solutions.</span></span>
    
[<span data-ttu-id="b2564-133">Microsoft Office 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="b2564-133">Microsoft Office Developer Center</span></span>](http://go.microsoft.com/fwlink?LinkID=27128)
  
> <span data-ttu-id="b2564-134">包含许多链接，这些链接指向有关构建自定义 Office 解决方案的技术文章、代码示例、下载内容、支持以及其他 MSDN 文档。</span><span class="sxs-lookup"><span data-stu-id="b2564-134">Contains links to technical articles, code samples, downloads, support, and other MSDN documentation on building custom Office solutions.</span></span>
    

