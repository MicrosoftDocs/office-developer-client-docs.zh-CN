---
title: 关于表单模板组件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: b51361fe-cf29-f890-9876-5aebe15c73e1
description: Microsoft InfoPath 表单模板由结合使用的多个文件和组件组成，它们共同提供特定的功能以满足特定的最终用户方案或业务需求。InfoPath 表单在复杂性方面可能会有所变化，这取决于它们所服务的需求的类型。
ms.openlocfilehash: 4ef90d3fb55ee38018d2c1226bef5fd59e277186
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773964"
---
# <a name="about-form-template-components"></a><span data-ttu-id="16f61-104">关于表单模板组件</span><span class="sxs-lookup"><span data-stu-id="16f61-104">About Form Template Components</span></span>

<span data-ttu-id="16f61-p102">Microsoft InfoPath 表单模板由结合使用的多个文件和组件组成，它们共同提供特定的功能以满足特定的最终用户方案或业务需求。InfoPath 表单在复杂性方面可能会有所变化，这取决于它们所服务的需求的类型。</span><span class="sxs-lookup"><span data-stu-id="16f61-p102">Microsoft InfoPath form templates are composed of several files and components that are combined to provide specific functionality for a particular end user scenario or business need. InfoPath forms can vary in complexity depending on the type of need that they address.</span></span>
  
<span data-ttu-id="16f61-107">从本质上说，InfoPath 表单模板是一类应用程序，它创建特定类别的 XML 文档，定义其版式和编辑行为，强制其数据一致性，并且提供表明其存储位置的传送信息。</span><span class="sxs-lookup"><span data-stu-id="16f61-107">An InfoPath form template is essentially a type of application that creates a specified class of XML documents, defines their layout and editing behavior, enforces their data consistency, and provides the routing information that indicates where they should be stored.</span></span>
  
<span data-ttu-id="16f61-p103">了解 InfoPath 表单模板是由属于许多不同类型的几个不同文件组成，这一点很重要；这些文件统称为表单文件。通常，InfoPath 表单模板由下列类型的文件组成。</span><span class="sxs-lookup"><span data-stu-id="16f61-p103">It is important to understand that InfoPath form templates are composed of several different files of many different types; these files are collectively known as the form files. Usually, an InfoPath form template is composed of the following types of files.</span></span>
  
|<span data-ttu-id="16f61-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="16f61-110">**Name**</span></span>|<span data-ttu-id="16f61-111">**扩展名**</span><span class="sxs-lookup"><span data-stu-id="16f61-111">**Extension**</span></span>|<span data-ttu-id="16f61-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="16f61-112">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16f61-113">表单定义</span><span class="sxs-lookup"><span data-stu-id="16f61-113">Form definition</span></span>  <br/> |<span data-ttu-id="16f61-114">.xsf</span><span class="sxs-lookup"><span data-stu-id="16f61-114">.xsf</span></span>  <br/> |<span data-ttu-id="16f61-p104">InfoPath 生成的文件，其中包含有关表单中所使用的所有其他文件和组件的信息。该文件作为表单的指令清单。</span><span class="sxs-lookup"><span data-stu-id="16f61-p104">An InfoPath-generated file that contains information about all of the other files and components used in a form. This file serves as the manifest for the form.</span></span>  <br/> |
|<span data-ttu-id="16f61-117">XML 架构</span><span class="sxs-lookup"><span data-stu-id="16f61-117">XML Schema</span></span>  <br/> |<span data-ttu-id="16f61-118">.xsd</span><span class="sxs-lookup"><span data-stu-id="16f61-118">.xsd</span></span>  <br/> |<span data-ttu-id="16f61-119">XML 架构文件，用于约束和验证表单的基础 XML 文档文件。</span><span class="sxs-lookup"><span data-stu-id="16f61-119">The XML Schema files that are used to constrain and validate a form's underlying XML document files.</span></span>  <br/> |
|<span data-ttu-id="16f61-120">视图</span><span class="sxs-lookup"><span data-stu-id="16f61-120">View</span></span>  <br/> |<span data-ttu-id="16f61-121">.xsl</span><span class="sxs-lookup"><span data-stu-id="16f61-121">XSL</span></span>  <br/> |<span data-ttu-id="16f61-122">样式表逻辑文件，用于显示、查看和转换表单的基础 XML 文档文件中所包含的数据。</span><span class="sxs-lookup"><span data-stu-id="16f61-122">The presentation logic files that are used to present, view, and transform the data contained in a form's underlying XML document files.</span></span>  <br/> |
|<span data-ttu-id="16f61-123">XML 模板</span><span class="sxs-lookup"><span data-stu-id="16f61-123">XML template</span></span>  <br/> |<span data-ttu-id="16f61-124">.xml</span><span class="sxs-lookup"><span data-stu-id="16f61-124">XML</span></span>  <br/> |<span data-ttu-id="16f61-125">.xml 文件，包含新建表单时显示在视图中的默认数据。</span><span class="sxs-lookup"><span data-stu-id="16f61-125">The .xml file that contains the default data that is displayed in a view when a new form is created.</span></span>  <br/> |
|<span data-ttu-id="16f61-126">演示文稿</span><span class="sxs-lookup"><span data-stu-id="16f61-126">Presentation</span></span>  <br/> |<span data-ttu-id="16f61-127">.htm, .gif, .bmp 及其他</span><span class="sxs-lookup"><span data-stu-id="16f61-127">.htm, .gif, .bmp, and others</span></span>  <br/> |<span data-ttu-id="16f61-128">结合视图文件使用以创建自定义用户界面的文件。</span><span class="sxs-lookup"><span data-stu-id="16f61-128">The files that are used together with the view files to create a custom user interface.</span></span>  <br/> |
|<span data-ttu-id="16f61-129">业务逻辑</span><span class="sxs-lookup"><span data-stu-id="16f61-129">Business logic</span></span>  <br/> |<span data-ttu-id="16f61-130">.dll</span><span class="sxs-lookup"><span data-stu-id="16f61-130">\*.dll</span></span>  <br/> |<span data-ttu-id="16f61-p105">用于实现特定的编辑行为、数据有效性、事件处理程序、数据流的控制以及其他自定义业务逻辑的已编译编程代码。可以使用 Visual Basic 和 C# .NET 编程语言来编写 InfoPath 业务逻辑，这些语言是经过编译的，并且以二进制文件形式提供。</span><span class="sxs-lookup"><span data-stu-id="16f61-p105">The compiled programming code used to implement specific editing behavior, data validation, event handlers, control of data flow, and other custom business logic. InfoPath business logic can be written in the Visual Basic and C# .NET programming languages, which are compiled and included as binary files.</span></span>  <br/> |
|<span data-ttu-id="16f61-133">二进制数</span><span class="sxs-lookup"><span data-stu-id="16f61-133">Binary</span></span>  <br/> |<span data-ttu-id="16f61-134">.dll, .exe</span><span class="sxs-lookup"><span data-stu-id="16f61-134">.dll, .exe</span></span>  <br/> | <span data-ttu-id="16f61-135">提供附加业务逻辑的任何自定义组件。</span><span class="sxs-lookup"><span data-stu-id="16f61-135">Any custom components that provide additional business logic.</span></span>  <br/> |
|<span data-ttu-id="16f61-136">表单模板</span><span class="sxs-lookup"><span data-stu-id="16f61-136">Form template</span></span>  <br/> |<span data-ttu-id="16f61-137">.xsn</span><span class="sxs-lookup"><span data-stu-id="16f61-137">\*.xsn</span></span>  <br/> |<span data-ttu-id="16f61-138">将所有表单文件打包成一个文件的压缩文件格式 (.cab)。</span><span class="sxs-lookup"><span data-stu-id="16f61-138">The compressed file format (.cab) that packages all the form files into one file.</span></span>  <br/> |
   

