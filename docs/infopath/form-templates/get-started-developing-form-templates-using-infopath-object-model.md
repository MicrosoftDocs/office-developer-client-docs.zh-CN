---
title: 使用 InfoPath 对象模型开始开发表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- form templates [infopath 2007], getting started,InfoPath 2003-compatible form templates, getting started
localization_priority: Normal
ms.assetid: 45867711-3231-43ce-bae9-caf588120550
description: 本节提供有关如何开始创建托管代码表单模板的信息，这些模板可以处理由 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间的成员提供的 InfoPath 2003 兼容对象模型。
ms.openlocfilehash: 54d60e6d73ee224845c87c08f4de1e554e6182da
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408052"
---
# <a name="get-started-developing-form-templates-using-the-infopath-object-model"></a><span data-ttu-id="69f97-104">使用 InfoPath 对象模型开始开发表单模板</span><span class="sxs-lookup"><span data-stu-id="69f97-104">Get started developing form templates using the InfoPath object model</span></span>

<span data-ttu-id="69f97-105">本节提供有关如何开始创建托管代码表单模板的信息，这些模板可以处理由 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间的成员提供的 InfoPath 2003 兼容对象模型。</span><span class="sxs-lookup"><span data-stu-id="69f97-105">This section provides information on how to get started creating managed-code form templates that work with the InfoPath 2003-compatible object model provided by members of the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="69f97-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="69f97-106">In this section</span></span>

- <span data-ttu-id="69f97-107">[使用 infopath 2003 对象模型创建表单模板](how-to-create-a-form-template-using-the-infopath-2003-object-model.md): 提供有关创建表单模板的信息和步骤, 这些表单模板包含适用于 InfoPath 2003 兼容对象模型的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="69f97-107">[Create a Form Template Using the InfoPath 2003 Object Model](how-to-create-a-form-template-using-the-infopath-2003-object-model.md): Provides information and steps for creating form templates that contain business logic that works with the InfoPath 2003-compatible object model.</span></span>
    
- <span data-ttu-id="69f97-108">[演练: 使用 infopath 2003 对象模型创建和调试基本表单模板](walkthrough-create-and-debug-basic-form-template-using-infopath-object-model.md): 一个分步指南, 提供了有关创建和部署基本 infopath 表单模板的简介, 该表单模板适用于 InfoPath 2003 兼容对象模型。</span><span class="sxs-lookup"><span data-stu-id="69f97-108">[Walkthrough: Creating and Debugging a Basic Form Template Using the InfoPath 2003 Object Model](walkthrough-create-and-debug-basic-form-template-using-infopath-object-model.md): A step-by-step guide that provides an introduction to creating and deploying a basic InfoPath form template that works with the InfoPath 2003-compatible object model.</span></span>
    
- <span data-ttu-id="69f97-109">[使用 InfoPath 2003 对象模型开发表单模板的常见任务](common-tasks-for-developing-form-templates-using-infopath-object-model.md): 可帮助您快速查找有关使用业务逻辑开发表单模板的常见问题解答, 这些表单模板适用于与 InfoPath 2003 兼容的对象模型。</span><span class="sxs-lookup"><span data-stu-id="69f97-109">[Common Tasks for Developing Form Templates Using the InfoPath 2003 Object Model](common-tasks-for-developing-form-templates-using-infopath-object-model.md): Helps you quickly find the answers to common questions about developing form templates with business logic that works against the InfoPath 2003-compatible object model.</span></span>
    
- <span data-ttu-id="69f97-110">[使用与 infopath 2003 不兼容的 SemiTrust 成员](how-to-use-microsoft-office-interop-infopath-semitrust-members.md)。讨论如何使用添加到 SemiTrust 命名空间中的新对象模型成员, 具体方法是在中[。](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx)Office InfoPath 2007 和 InfoPath 2010。</span><span class="sxs-lookup"><span data-stu-id="69f97-110">[Use Microsoft.Office.Interop.InfoPath.SemiTrust Members That Are Not Compatible with InfoPath 2003](how-to-use-microsoft-office-interop-infopath-semitrust-members.md): Discusses how to work with new object model members that were added to the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace in Office InfoPath 2007 and InfoPath 2010.</span></span> 
    
## <a name="related-sections"></a><span data-ttu-id="69f97-111">相关部分</span><span class="sxs-lookup"><span data-stu-id="69f97-111">Related sections</span></span>

- <span data-ttu-id="69f97-112">[使用 infopath 2003 对象模型创建表单模板](creating-form-templates-using-the-infopath-2003-object-model.md): 讨论初始化和清理代码、如何添加事件处理程序、如何调试和部署使用 infopath 2003 兼容对象模型的 infopath 表单模板、线程支持和使用 Microsoft XML Core Services (MSXML)。</span><span class="sxs-lookup"><span data-stu-id="69f97-112">[Creating Form Templates Using the InfoPath 2003 Object Model](creating-form-templates-using-the-infopath-2003-object-model.md): Discusses initialization and clean-up code, how to add event handlers, how to debug and deploy InfoPath form templates that use the InfoPath 2003-compatible object model, threading support, and working with Microsoft XML Core Services (MSXML).</span></span>
    
- <span data-ttu-id="69f97-113">[了解 infopath 2003 对象模型](understanding-the-infopath-2003-object-model.md): 讨论了 infopath 2003 兼容的对象模型, 并介绍了常见的编程任务。</span><span class="sxs-lookup"><span data-stu-id="69f97-113">[Understanding the InfoPath 2003 Object Model](understanding-the-infopath-2003-object-model.md): Discusses the InfoPath 2003-compatible object model, and describes common programming tasks.</span></span>
    
- <span data-ttu-id="69f97-114">[使用 infopath 2003 对象模型的表单模板疑难解答](troubleshoot-form-templates-that-use-infopath-object-model.md): 包含用于解决在开发使用 InfoPath 2003 兼容对象模型的表单模板时可能遇到的常见问题的提示。</span><span class="sxs-lookup"><span data-stu-id="69f97-114">[Troubleshooting Form Templates That Use the InfoPath 2003 Object Model](troubleshoot-form-templates-that-use-infopath-object-model.md): Contains tips for solving common problems that you might encounter when developing form templates that work with the InfoPath 2003-compatible object model.</span></span>
    

