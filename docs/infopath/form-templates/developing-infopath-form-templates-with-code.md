---
title: 开发包含代码的 InfoPath 表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- form templates [infopath 2007], developing,form templates [InfoPath 2007], managed code,InfoPath 2007,managed code form templates [InfoPath 2007]
localization_priority: Normal
ms.assetid: b43ada73-349d-498f-a8bb-e8fd5020d207
description: 本节中的主题提供有关依据 Microsoft.Office.InfoPath 命名空间的成员，创建具有用托管代码（Visual Basic 或 C#）编写的业务逻辑的表单模板的信息。
ms.openlocfilehash: 4b113e1c189fe8ebdb5781e969e7f67961d4ea18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773959"
---
# <a name="developing-infopath-form-templates-with-code"></a><span data-ttu-id="ec2c6-104">开发包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="ec2c6-104">Developing InfoPath Form Templates with Code</span></span>

<span data-ttu-id="ec2c6-105">本节中的主题提供有关依据 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的成员，创建具有用托管代码（Visual Basic 或 C#）编写的业务逻辑的表单模板的信息。</span><span class="sxs-lookup"><span data-stu-id="ec2c6-105">The topics in this section provide information about creating form templates that have business logic written in managed code (Visual Basic or C#) against members of the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="ec2c6-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="ec2c6-106">In this section</span></span>

[<span data-ttu-id="ec2c6-107">开发包含代码的表单模板入门</span><span class="sxs-lookup"><span data-stu-id="ec2c6-107">Getting Started Developing Form Templates with Code</span></span>](getting-started-developing-form-templates-with-code.md)
  
> <span data-ttu-id="ec2c6-108">提供有关如何开始创建托管代码表单模板的信息，这些模板使用由 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的 InfoPath 对象模型。</span><span class="sxs-lookup"><span data-stu-id="ec2c6-108">Provides information about how to start creating managed code form templates that work with the InfoPath object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace.</span></span> 
    
[<span data-ttu-id="ec2c6-109">了解 InfoPath 对象模型和常见开发任务</span><span class="sxs-lookup"><span data-stu-id="ec2c6-109">Understanding the InfoPath Object Model and Common Developer Tasks</span></span>](understanding-the-infopath-object-model-and-common-developer-tasks.md)
  
> <span data-ttu-id="ec2c6-110">讨论 InfoPath 对象模型，以及与使用 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的对象模型的托管代码表单模板有关的常见编程任务。</span><span class="sxs-lookup"><span data-stu-id="ec2c6-110">Discusses the InfoPath object model, and common programming tasks for managed code form templates that work with the object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace.</span></span> 
    
[<span data-ttu-id="ec2c6-111">具有代码的 InfoPath 表单模板中的安全性</span><span class="sxs-lookup"><span data-stu-id="ec2c6-111">Security in InfoPath Form Templates with Code</span></span>](security-in-infopath-form-templates-with-code.md)
  
> <span data-ttu-id="ec2c6-112">讨论使用托管代码的 InfoPath 表单模板的安全模式以及相关的安全过程。</span><span class="sxs-lookup"><span data-stu-id="ec2c6-112">Discusses the security model for InfoPath form templates that use managed code, and related security procedures.</span></span>
    
[<span data-ttu-id="ec2c6-113">使用 SharePoint 和 InfoPath Forms Services</span><span class="sxs-lookup"><span data-stu-id="ec2c6-113">Working with SharePoint and InfoPath Forms Services</span></span>](working-with-sharepoint-and-infopath-forms-services.md)
  
> <span data-ttu-id="ec2c6-114">讨论为 InfoPath Forms Services 创建的托管代码表单模板中的对象模型支持和功能兼容性。</span><span class="sxs-lookup"><span data-stu-id="ec2c6-114">Discusses object model support and feature compatibility in managed code form templates created for InfoPath Forms Services.</span></span> 
    
[<span data-ttu-id="ec2c6-115">其他 InfoPath 开发概念</span><span class="sxs-lookup"><span data-stu-id="ec2c6-115">Additional InfoPath Development Concepts</span></span>](additional-infopath-development-concepts.md)
  
> <span data-ttu-id="ec2c6-116">论述与 InfoPath 表单模板开发相关的其他概念。</span><span class="sxs-lookup"><span data-stu-id="ec2c6-116">Discusses additional concepts that relate to InfoPath form template development.</span></span>
    
## <a name="related-sections"></a><span data-ttu-id="ec2c6-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="ec2c6-117">Related sections</span></span>

[<span data-ttu-id="ec2c6-118">InfoPath 开发人员门户</span><span class="sxs-lookup"><span data-stu-id="ec2c6-118">InfoPath Developer Portal</span></span>](http://go.microsoft.com/fwlink?LinkID=11689)
  
> <span data-ttu-id="ec2c6-119">包含许多链接，这些链接指向有关构建自定义 InfoPath 解决方案的技术文章、代码示例、下载内容、支持以及其他 MSDN 文档。</span><span class="sxs-lookup"><span data-stu-id="ec2c6-119">Contains links to technical articles, code samples, downloads, support, and other MSDN documentation on building custom InfoPath solutions.</span></span>
    
[<span data-ttu-id="ec2c6-120">Microsoft Office 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ec2c6-120">Microsoft Office Developer Center</span></span>](http://go.microsoft.com/fwlink?LinkID=27128)
  
> <span data-ttu-id="ec2c6-121">包含许多链接，这些链接指向有关构建自定义 Office 解决方案的技术文章、代码示例、下载内容、支持以及其他 MSDN 文档。</span><span class="sxs-lookup"><span data-stu-id="ec2c6-121">Contains links to technical articles, code samples, downloads, support, and other MSDN documentation on building custom Office solutions.</span></span>
    

