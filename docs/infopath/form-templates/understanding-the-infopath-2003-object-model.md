---
title: 了解 InfoPath 2003 对象模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, object model,InfoPath 2003-compatible object model,object models [InfoPath 2003]
localization_priority: Normal
ms.assetid: cd0a890b-5a8b-42c0-abdd-5ce28aff1ba1
description: 本节讨论 InfoPath 托管代码解决方案的对象模型，并介绍常见编程任务。
ms.openlocfilehash: 0c07201475bb7bfe24182faf61cc1bf6df733709
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416655"
---
# <a name="understanding-the-infopath-2003-object-model"></a><span data-ttu-id="e50bf-104">了解 InfoPath 2003 对象模型</span><span class="sxs-lookup"><span data-stu-id="e50bf-104">Understanding the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="e50bf-105">本节讨论 InfoPath 托管代码解决方案的对象模型，并介绍常见编程任务。</span><span class="sxs-lookup"><span data-stu-id="e50bf-105">This section discusses the object model for InfoPath managed-code solutions, and describes common programming tasks.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e50bf-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e50bf-106">In this section</span></span>

[<span data-ttu-id="e50bf-107">InfoPath 2003 兼容对象模型</span><span class="sxs-lookup"><span data-stu-id="e50bf-107">InfoPath 2003 Compatible Object Models</span></span>](infopath-2003-compatible-object-models.md)
  
> <span data-ttu-id="e50bf-108">概述了 InfoPath 托管代码项目中使用的对象模型。</span><span class="sxs-lookup"><span data-stu-id="e50bf-108">Provides an overview of the object models used in InfoPath managed-code projects.</span></span>
    
[<span data-ttu-id="e50bf-109">使用 InfoPath 2003 对象模型访问应用程序数据</span><span class="sxs-lookup"><span data-stu-id="e50bf-109">Access Application Data Using the InfoPath 2003 Object Model</span></span>](how-to-access-application-data-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-110">讨论如何访问有关 InfoPath 应用程序、表单的基础 XML 文档和表单定义 (.xsf) 文件的信息。</span><span class="sxs-lookup"><span data-stu-id="e50bf-110">Discusses how to access information about the InfoPath application, the form's underlying XML document, and the form definition (.xsf) file.</span></span>
    
[<span data-ttu-id="e50bf-111">使用 InfoPath 2003 对象模型访问外部数据源</span><span class="sxs-lookup"><span data-stu-id="e50bf-111">Access External Data Sources Using the InfoPath 2003 Object Model</span></span>](how-to-access-external-data-sources-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-112">讨论如何访问外部数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="e50bf-112">Discusses how to access data from external data sources.</span></span>
    
[<span data-ttu-id="e50bf-113">使用 InfoPath 2003 对象模型访问表单数据</span><span class="sxs-lookup"><span data-stu-id="e50bf-113">Access Form Data Using the InfoPath 2003 Object Model</span></span>](how-to-access-form-data-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-114">讨论如何访问有关表单的基础 XML 文档、它所包含的数据或对 XML 文档执行一些操作的信息。</span><span class="sxs-lookup"><span data-stu-id="e50bf-114">Discusses how to access information about the form's underlying XML document, the data it contains, or to perform some action on the XML document.</span></span>
    
[<span data-ttu-id="e50bf-115">使用 InfoPath 2003 对象模型显示警报和对话框</span><span class="sxs-lookup"><span data-stu-id="e50bf-115">Display Alerts and Dialog Boxes Using the InfoPath 2003 Object Model</span></span>](how-to-display-alerts-and-dialog-boxes-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-116">讨论如何显示 InfoPath 托管代码项目中的警报和对话框。</span><span class="sxs-lookup"><span data-stu-id="e50bf-116">Discusses how to display alerts and dialog boxes in InfoPath managed-code projects.</span></span>
    
[<span data-ttu-id="e50bf-117">使用 InfoPath 2003 对象模型处理错误</span><span class="sxs-lookup"><span data-stu-id="e50bf-117">Handle Errors Using the InfoPath 2003 Object Model</span></span>](how-to-handle-errors-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-118">讨论如何处理 InfoPath 托管代码项目中的错误。</span><span class="sxs-lookup"><span data-stu-id="e50bf-118">Discusses how to handle errors in InfoPath managed-code projects.</span></span>
    
[<span data-ttu-id="e50bf-119">使用 InfoPath 2003 对象模型响应表单事件</span><span class="sxs-lookup"><span data-stu-id="e50bf-119">Respond to Form Events Using the InfoPath 2003 Object Model</span></span>](how-to-respond-to-form-events-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-120">讨论如何创建可响应用户填写表单时发生的事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e50bf-120">Discusses how to create event handlers that respond to events that occur as a user fills out a form.</span></span>
    
[<span data-ttu-id="e50bf-121">使用 InfoPath 2003 对象模型处理表单窗口</span><span class="sxs-lookup"><span data-stu-id="e50bf-121">Work with Form Windows Using the InfoPath 2003 Object Model</span></span>](how-to-work-with-form-windows-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-122">讨论如何处理表单窗口。</span><span class="sxs-lookup"><span data-stu-id="e50bf-122">Discusses how to work with form windows.</span></span>
    
[<span data-ttu-id="e50bf-123">使用 InfoPath 2003 对象模型处理视图</span><span class="sxs-lookup"><span data-stu-id="e50bf-123">Work with Views Using the InfoPath 2003 Object Model</span></span>](how-to-work-with-views-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-124">讨论如何处理视图。</span><span class="sxs-lookup"><span data-stu-id="e50bf-124">Discusses how to work with views.</span></span>
    
[<span data-ttu-id="e50bf-125">使用 InfoPath 2003 对象模型处理数字签名</span><span class="sxs-lookup"><span data-stu-id="e50bf-125">Work with Digital Signatures Using the InfoPath 2003 Object Model</span></span>](how-to-work-with-digital-signatures-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-126">讨论如何处理数字签名。</span><span class="sxs-lookup"><span data-stu-id="e50bf-126">Discusses how to work with digital signatures.</span></span>
    
[<span data-ttu-id="e50bf-127">使用 InfoPath 2003 对象模型处理脱机解决方案</span><span class="sxs-lookup"><span data-stu-id="e50bf-127">Work with Offline Solutions Using the InfoPath 2003 Object Model</span></span>](how-to-work-with-offline-solutions-using-the-infopath-2003-object-model.md)
  
> <span data-ttu-id="e50bf-128">讨论如何处理脱机解决方案。</span><span class="sxs-lookup"><span data-stu-id="e50bf-128">Discusses how to work with offline solutions.</span></span>
    

