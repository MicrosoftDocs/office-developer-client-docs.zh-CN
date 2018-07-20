---
title: 使用 InfoPath 2003 对象模型创建表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, creating,object models [InfoPath 2003], creating managed code form templates for InfoPath 2007,form templates [InfoPath 2007], creating InfoPath 2003-compatible
localization_priority: Normal
ms.assetid: e0513178-ddcb-4086-ab19-1bc80cf114cc
description: 本节讨论初始化和清理代码、如何添加事件处理程序、如何调试和部署使用 InfoPath 2003 兼容对象模型的 InfoPath 表单模板、线程支持，以及如何使用 InfoPath 托管代码解决方案中的 Microsoft XML Core Services (MSXML)。
ms.openlocfilehash: 16d49b24b2eed3b7fe15621d47663a94f1958cfa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773970"
---
# <a name="creating-form-templates-using-the-infopath-2003-object-model"></a><span data-ttu-id="0ad54-104">使用 InfoPath 2003 对象模型创建表单模板</span><span class="sxs-lookup"><span data-stu-id="0ad54-104">Creating Form Templates Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="0ad54-105">本节讨论初始化和清理代码、如何添加事件处理程序、如何调试和部署使用 InfoPath 2003 兼容对象模型的 InfoPath 表单模板、线程支持，以及如何使用 InfoPath 托管代码解决方案中的 Microsoft XML Core Services (MSXML)。</span><span class="sxs-lookup"><span data-stu-id="0ad54-105">This section discusses initialization and clean-up code, how to add event handlers, how to debug and deploy InfoPath form templates that use the InfoPath 2003-compatible object model, threading support, and working with Microsoft XML Core Services (MSXML) from InfoPath managed-code solutions.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0ad54-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="0ad54-106">In this section</span></span>

[<span data-ttu-id="0ad54-107">使用 InfoPath 2003 对象模型初始化和清理代码</span><span class="sxs-lookup"><span data-stu-id="0ad54-107">Initialization and Clean-up Code Using InfoPath 2003 Object Model</span></span>](initialization-and-clean-up-code-using-infopath-2003-object-model.md)
  
> <span data-ttu-id="0ad54-108">讨论如何在项目的 _Startup 和 _Shutdown 方法中编写初始化和清理代码。</span><span class="sxs-lookup"><span data-stu-id="0ad54-108">Discusses how to write initialization and clean-up code in the _Startup and _Shutdown methods of your project.</span></span>
    
[<span data-ttu-id="0ad54-109">使用 InfoPath 2003 对象模型添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="0ad54-109">How to: Add an Event Handler Using the InfoPath 2003 Object Model</span></span>](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="0ad54-110">讨论如何添加用于标识事件处理程序的事件处理程序和属性。</span><span class="sxs-lookup"><span data-stu-id="0ad54-110">Discusses how to add event handlers and the attributes that are applied to identify event handlers.</span></span>
    
[<span data-ttu-id="0ad54-111">使用 InfoPath 2003 对象模型调试 InfoPath 项目</span><span class="sxs-lookup"><span data-stu-id="0ad54-111">How to: Debug InfoPath Projects Using the InfoPath 2003 Object Model</span></span>](how-to-debug-infopath-projects-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="0ad54-112">讨论如何调试 InfoPath 托管代码项目。</span><span class="sxs-lookup"><span data-stu-id="0ad54-112">Discusses how to debug InfoPath managed-code projects.</span></span>
    
[<span data-ttu-id="0ad54-113">部署包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="0ad54-113">Deploy InfoPath Form Templates with Code?</span></span>](how-to-deploy-infopath-form-templates-with-code.md)
  
> <span data-ttu-id="0ad54-114">讨论如何部署 InfoPath 托管代码项目。</span><span class="sxs-lookup"><span data-stu-id="0ad54-114">Discusses how to deploy InfoPath managed-code projects.</span></span>
    
[<span data-ttu-id="0ad54-115">使用 InfoPath 2003 对象模型的 InfoPath 项目中的线程支持</span><span class="sxs-lookup"><span data-stu-id="0ad54-115">Threading Support in InfoPath Projects Using the InfoPath 2003 Object Model</span></span>](threading-support-in-infopath-projects-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="0ad54-116">讨论 InfoPath 托管代码项目中的线程支持。</span><span class="sxs-lookup"><span data-stu-id="0ad54-116">Discusses threading support in InfoPath managed-code projects.</span></span>
    
[<span data-ttu-id="0ad54-117">使用 InfoPath 2003 对象模型处理 MSXML 和 System.Xml</span><span class="sxs-lookup"><span data-stu-id="0ad54-117">Working with MSXML and System.Xml Using the InfoPath 2003 Object Model</span></span>](working-with-msxml-and-system-xml-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="0ad54-118">讨论如何在 InfoPath 托管代码项目中使用 MSXML 和 System.Xml 代码。</span><span class="sxs-lookup"><span data-stu-id="0ad54-118">Discusses how to work with MSXML and System.Xml code in InfoPath managed-code projects.</span></span>
    

