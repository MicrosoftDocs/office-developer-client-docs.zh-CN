---
title: Visio 文件格式 (.vsdx) 简介
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 69736f40-8f67-46c2-abf6-82dffecb2274
description: 了解 Visio 2013 中的新文件格式浏览以编程方式使用 Visio 2013 文件格式的一些高级概念，并创建一个简单的控制台应用程序检查 Visio 2013 文件。
ms.openlocfilehash: aa3497af7c467c8f51ab80ab82071776568b4978
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780463"
---
# <a name="introduction-to-the-visio-file-format-vsdx"></a><span data-ttu-id="0aa00-103">Visio 文件格式 (.vsdx) 简介</span><span class="sxs-lookup"><span data-stu-id="0aa00-103">Introduction to the Visio file format (.vsdx)</span></span>

<span data-ttu-id="0aa00-104">了解 Visio 2013 中的新文件格式浏览以编程方式使用 Visio 2013 文件格式的一些高级概念，并创建一个简单的控制台应用程序检查 Visio 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-104">Learn about the new file format in Visio 2013, explore some high-level concepts for working with the Visio 2013 file format programmatically, and create a simple console application that examines a Visio 2013 file.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0aa00-105">**本文中**         [简介](#vis15_IntroVSDX_Intro)          [本质"的 Visio 2013 文件格式是什么？](#vis15_IntroVSDX_What)</span><span class="sxs-lookup"><span data-stu-id="0aa00-105">**In this article**         [Introduction](#vis15_IntroVSDX_Intro)          [What is the Visio 2013 file format "under the hood"?](#vis15_IntroVSDX_What)</span></span>          <span data-ttu-id="0aa00-106">[使用 Visio 2013 文件格式的开发人员方案](#vis15_IntroVSDX_Scenarios)          [以编程方式浏览 Visio 2013 文件格式](#vis15_IntroVSDX_Explore)          [其他资源](#vis15_IntroVSDX_Resources)</span><span class="sxs-lookup"><span data-stu-id="0aa00-106">[Developer scenarios for working with the Visio 2013 file format](#vis15_IntroVSDX_Scenarios)          [Exploring the Visio 2013 file format programmatically](#vis15_IntroVSDX_Explore)          [Additional resources](#vis15_IntroVSDX_Resources)</span></span>||
   
## <a name="introduction"></a><span data-ttu-id="0aa00-107">简介</span><span class="sxs-lookup"><span data-stu-id="0aa00-107">Introduction</span></span>
<span data-ttu-id="0aa00-108"><a name="vis15_IntroVSDX_Intro"> </a></span><span class="sxs-lookup"><span data-stu-id="0aa00-108"></span></span>

<span data-ttu-id="0aa00-109">Visio 2013 为 Visio 取代了 Visio 二进制文件格式 (.vsd) 和 Visio XML 绘图文件格式 (.vdx) 引入了新的文件格式 (.vsdx)。</span><span class="sxs-lookup"><span data-stu-id="0aa00-109">Visio 2013 introduces a new file format (.vsdx) for Visio that replaces the Visio binary file format (.vsd) and Visio XML Drawing file format (.vdx).</span></span> <span data-ttu-id="0aa00-110">Visio 2013 文件格式基于开放打包约定和 XML，因为熟悉这些技术的开发人员可以快速了解如何以编程方式使用 Visio 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-110">Because the Visio 2013 file format is based upon Open Packaging Conventions and XML, developers who are familiar with these technologies can quickly learn how to work with Visio 2013 files programmatically.</span></span> <span data-ttu-id="0aa00-111">开发人员熟悉从早期版本的 Visio Visio XML 绘图文件格式 (.vdx) 可以找到许多相同的 XML 结构内.vsdx 文件格式的部分。</span><span class="sxs-lookup"><span data-stu-id="0aa00-111">Developers who are familiar with the Visio XML Drawing file format (.vdx) from previous versions of Visio can find many of the same XML structures within the parts of .vsdx file format.</span></span> <span data-ttu-id="0aa00-112">由于第三方软件可以处理文件格式级别的 Visio 文件极大地增加与 Visio 文件互操作性。</span><span class="sxs-lookup"><span data-stu-id="0aa00-112">Interoperability with Visio files is greatly increased since third-party software can manipulate Visio files at a file format level.</span></span> <span data-ttu-id="0aa00-113">Visio 2013 文件格式都支持 Microsoft SharePoint Server 2013 中的 Visio Services 无需发布到 SharePoint Server"中间"的文件格式。</span><span class="sxs-lookup"><span data-stu-id="0aa00-113">The Visio 2013 file format is supported on Visio Services in Microsoft SharePoint Server 2013, without the need of an "intermediary" file format for publishing to SharePoint Server.</span></span>
  
<span data-ttu-id="0aa00-114">有几种文件类型，按扩展名组成的 Visio 2013 文件格式。</span><span class="sxs-lookup"><span data-stu-id="0aa00-114">There are several file types, by extension, that comprise the Visio 2013 file format.</span></span> <span data-ttu-id="0aa00-115">这些扩展包括：</span><span class="sxs-lookup"><span data-stu-id="0aa00-115">These extensions include:</span></span>
  
- <span data-ttu-id="0aa00-116">.vsdx （Visio 绘图）</span><span class="sxs-lookup"><span data-stu-id="0aa00-116">.vsdx (Visio drawing)</span></span>
    
- <span data-ttu-id="0aa00-117">.vsdm （Visio 启用宏的绘图）</span><span class="sxs-lookup"><span data-stu-id="0aa00-117">.vsdm (Visio macro-enabled drawing)</span></span>
    
- <span data-ttu-id="0aa00-118">.vssx （Visio 模具）</span><span class="sxs-lookup"><span data-stu-id="0aa00-118">.vssx (Visio stencil)</span></span>
    
- <span data-ttu-id="0aa00-119">.vssm （Visio 启用宏的模具）</span><span class="sxs-lookup"><span data-stu-id="0aa00-119">.vssm (Visio macro-enabled stencil)</span></span>
    
- <span data-ttu-id="0aa00-120">.vstx （Visio 模板）</span><span class="sxs-lookup"><span data-stu-id="0aa00-120">.vstx (Visio template)</span></span>
    
- <span data-ttu-id="0aa00-121">.vstm （Visio 启用宏的模板）</span><span class="sxs-lookup"><span data-stu-id="0aa00-121">.vstm (Visio macro-enabled template)</span></span>
    
> [!NOTE]
> <span data-ttu-id="0aa00-p104">仅启用宏的文件（.vsdm、.vssm、.vstm）可以存储 VBA 宏。不能将宏存储在扩展名为 .vsdx、.vssx 或 .vstx 的文件中。</span><span class="sxs-lookup"><span data-stu-id="0aa00-p104">Only the macro-enabled files (.vsdm, .vssm, .vstm) can store VBA macros. You cannot store macros in files with a .vsdx, .vssx, or .vstx extension.</span></span> 
  
## <a name="what-is-the-visio-2013-file-format-under-the-hood"></a><span data-ttu-id="0aa00-124">什么是本质"的 Visio 2013 文件格式？</span><span class="sxs-lookup"><span data-stu-id="0aa00-124">What is the Visio 2013 file format "under the hood"?</span></span>
<span data-ttu-id="0aa00-125"><a name="vis15_IntroVSDX_What"> </a></span><span class="sxs-lookup"><span data-stu-id="0aa00-125"></span></span>

<span data-ttu-id="0aa00-126">Visio 2013 文件格式使用开放式装箱约定 (OPC)，它定义存储一起使用的一些 sort─for 示例中，一个 ZIP 文件的容器的相关资源的应用程序数据的结构化的方法。</span><span class="sxs-lookup"><span data-stu-id="0aa00-126">The Visio 2013 file format uses the Open Packing Conventions (OPC), which defines a structured means to store application data together with related resources using a container of some sort─for example, a ZIP file.</span></span> <span data-ttu-id="0aa00-127">在基本级别，Visio 2013 文件实际上是包含其他类型的文件的 ZIP 容器。</span><span class="sxs-lookup"><span data-stu-id="0aa00-127">At a basic level, a Visio 2013 file is really a ZIP container that contains other types of files.</span></span> <span data-ttu-id="0aa00-128">实际上，您可以在 Visio 2013 为.vsdx 文件中保存绘图、 重命名的文件扩展名为"\*.zip"在 Windows 资源管理器，然后打开该文件的 like 文件夹以查看内的内容。</span><span class="sxs-lookup"><span data-stu-id="0aa00-128">In fact, you can save a drawing in Visio 2013 as a .vsdx file, rename the file extension to "\*.zip" in Windows Explorer, and then open the file like a folder to see the contents inside.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0aa00-129">本文包含简要概述的开放打包约定。</span><span class="sxs-lookup"><span data-stu-id="0aa00-129">This article contains only a brief overview of the Open Packaging Conventions.</span></span> <span data-ttu-id="0aa00-130">您可以找到更多详细的其他文章中的约定的范围： > 有关自己的开放打包约定的详细信息，请参阅[OPC: 新标准打包您的数据](http://msdn.microsoft.com/zh-cn/magazine/cc163372.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0aa00-130">You can find more detailed coverage of the conventions in other articles: >  For more information about the Open Packaging Conventions themselves, see [OPC: A New Standard for Packaging Your Data](http://msdn.microsoft.com/zh-cn/magazine/cc163372.aspx).</span></span> <span data-ttu-id="0aa00-131">> 的开放打包约定以及在 Microsoft Office 文件中的使用它们的详细信息，请参阅[Essentials 的开放打包约定](http://msdn.microsoft.com/zh-cn/library/ee361919.aspx)和[介绍 Office (2007) Open XML 文件格式](http://msdn.microsoft.com/zh-cn/library/aa338205.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0aa00-131">>  For more information about the Open Packaging Conventions and their use in Microsoft Office files, see [Essentials of the Open Packaging Conventions](http://msdn.microsoft.com/zh-cn/library/ee361919.aspx) and [Introducing the Office (2007) Open XML File Formats](http://msdn.microsoft.com/zh-cn/library/aa338205.aspx).</span></span> 
  
### <a name="packages-and-package-parts"></a><span data-ttu-id="0aa00-132">包和包部件</span><span class="sxs-lookup"><span data-stu-id="0aa00-132">Packages and Package Parts</span></span>

<span data-ttu-id="0aa00-133">开始之前，Visio 2013 文件是在其中保存 （称为"包部件"） 的其他文件的 ZIP 容器或"包"。</span><span class="sxs-lookup"><span data-stu-id="0aa00-133">As started earlier, Visio 2013 files are ZIP containers or "packages" that hold other files (called "package parts") within them.</span></span> <span data-ttu-id="0aa00-134">包部件可以是 XML 文件，图像，甚至将 VBA 解决方案。</span><span class="sxs-lookup"><span data-stu-id="0aa00-134">A package part can be an XML file, an image, even a VBA solution.</span></span> <span data-ttu-id="0aa00-135">部件的包中可以进一步划分为两个三大类、"文档部件"和"关系部件"。</span><span class="sxs-lookup"><span data-stu-id="0aa00-135">The parts within the package can be further divided into two broad categories, "document parts" and "relationship parts."</span></span> <span data-ttu-id="0aa00-136">文档部件包含实际内容和元数据的 Visio 文件，如文件、 第一页和所有它所包含的形状的名称，但偶数的形状的数据连接。</span><span class="sxs-lookup"><span data-stu-id="0aa00-136">The document parts contain the actual content and metadata of the Visio file, like the name of the file, the first page and all of the shapes that it contains, and even the data connections for the shapes.</span></span> <span data-ttu-id="0aa00-137">图像和文本的包中的文件被视为文档部件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-137">Images and text files within the package are considered document parts.</span></span> <span data-ttu-id="0aa00-138">本主题后面的更详细地描述了关系部件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-138">Relationship parts are described in more detail later in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0aa00-139">如果您打开 Visio 2013 文件使用 ZIP 实用程序，您可能会看出在 ZIP 包中包含的多个文件夹。</span><span class="sxs-lookup"><span data-stu-id="0aa00-139">If you open a Visio 2013 file using a ZIP utility, you can probably see several folders contained inside of the ZIP package.</span></span> <span data-ttu-id="0aa00-140">您甚至可以处理类似文件夹使用 ZIP 实用工具这些子地址。</span><span class="sxs-lookup"><span data-stu-id="0aa00-140">You can even manipulate these sub-addresses like folders using a ZIP utility.</span></span> <span data-ttu-id="0aa00-141">但是，这些"文件夹"表示 ZIP 包，而不是实际的文件夹内的子地址。</span><span class="sxs-lookup"><span data-stu-id="0aa00-141">However, these "folders" represent sub-addresses within the ZIP package, not actual folders.</span></span> <span data-ttu-id="0aa00-142">不能使用的文件夹的编程的等效项以在您的解决方案与这些子地址。</span><span class="sxs-lookup"><span data-stu-id="0aa00-142">You cannot use the programmatic equivalents of folders to work with these sub-addresses in your solution.</span></span> 
  
<span data-ttu-id="0aa00-p109">包部件─文档部件和关系部件─也具有相关的内容类型。这些内容类型是用于定义 MIME 媒体类型的字符串。这些内容类型指定可以包含在文件中的 MIME 类型并限定其范围。</span><span class="sxs-lookup"><span data-stu-id="0aa00-p109">Package parts─both document parts and relationship parts─also have associated content types. These content types are strings that define a MIME media type. These content types specify and scope the kind of MIME types that can be contained in the file.</span></span>
  
### <a name="relationships"></a><span data-ttu-id="0aa00-146">关系</span><span class="sxs-lookup"><span data-stu-id="0aa00-146">Relationships</span></span>

<span data-ttu-id="0aa00-147">关系部件 (其结束，扩展名为"\*.rels"和"_rels"文件夹中存储) 介绍每个包中的部件之间的关系，并提供文件的结构。</span><span class="sxs-lookup"><span data-stu-id="0aa00-147">The relationship parts (which end with the extension "\*.rels" and are stored in a "_rels" folder) describe how the parts within the package relate to each other and provide the structure of the file.</span></span> <span data-ttu-id="0aa00-148">一个独立的 XML 文档使用元素的父/子的关系来确定对每个其他实体的关系。</span><span class="sxs-lookup"><span data-stu-id="0aa00-148">A standalone XML document uses the parent/child relationship of elements to determine the relationship of entities to each other.</span></span> <span data-ttu-id="0aa00-149">其他文件可以使用其他层次结构或文件的文件夹结构来描述文件中的内容的交互。</span><span class="sxs-lookup"><span data-stu-id="0aa00-149">Other files may use other hierarchies or file folder structure to describe the interaction of content in the file.</span></span> <span data-ttu-id="0aa00-150">Visio 2013 文件格式，包是一个有效的 Visio 文件，如果它包含正确的部件，并且程序包包含部分之间的关系。</span><span class="sxs-lookup"><span data-stu-id="0aa00-150">For the Visio 2013 file format, the package is a valid Visio file if it contains the correct set of parts and the package contains the relationships between the parts.</span></span> 
  
<span data-ttu-id="0aa00-p111">关系部件是用于描述包中不同文档部件之间关系的 XML 文档。它们定义了两个项目之间的关联：指定源（由关系文件的名称和位置定义）和指定目标文档部件。例如，关系部件用于描述哪些主控形状与文件相关联，页面和文件以及页面之间有何关系，或者图像和对象与特定页面有何关系。</span><span class="sxs-lookup"><span data-stu-id="0aa00-p111">Relationship parts are XML documents that describe the relationships between different document parts within the package. They define an association between two items: a specified source (defined by the name and location of the relationship file) and a specified target document part. For example, relationship parts are used to describe which shape masters are associated with the file, how pages relate to the file and to each other, or how images and objects relate to a specific page.</span></span> 
  
### <a name="similarities-and-differences-with-visio-vdx-schema"></a><span data-ttu-id="0aa00-154">相似之处以及使用 Visio VDX 架构的区别</span><span class="sxs-lookup"><span data-stu-id="0aa00-154">Similarities and differences with Visio VDX schema</span></span>

<span data-ttu-id="0aa00-155">如上所述，以前版本的 Visio 还包含一个基于 XML 的文件格式、 Visio XML 绘图格式或.vdx。</span><span class="sxs-lookup"><span data-stu-id="0aa00-155">As mentioned, past versions of Visio also included an XML-based file format, the Visio XML Drawing Format or .vdx.</span></span> <span data-ttu-id="0aa00-156">（在 Visio 以前的版本，用于 Visio XML 绘图格式的架构调用 DatadiagramML。）从 Visio XML 架构中的某些组件具有由于相同的两个文件格式之间的时间。</span><span class="sxs-lookup"><span data-stu-id="0aa00-156">(In previous versions of Visio, the schema used for the Visio XML Drawing Format is called DatadiagramML.) Some pieces from the Visio XML schema have stayed the same between the two file formats.</span></span> <span data-ttu-id="0aa00-157">例如， **Windows**元素及其子级保持 unchanged─with **Windows**元素现在是 XML 文档 (window.xml) 的根元素的异常。</span><span class="sxs-lookup"><span data-stu-id="0aa00-157">For example, the **Windows** element and its children remain unchanged─with the exception that the **Windows** element is now a root element of an XML document (window.xml).</span></span> 
  
<span data-ttu-id="0aa00-158">XML 绘图格式和 Visio 2013 文件格式的最大区别是打包。</span><span class="sxs-lookup"><span data-stu-id="0aa00-158">The largest difference between the XML Drawing Format and the Visio 2013 file format is the packaging.</span></span> <span data-ttu-id="0aa00-159">像普通的独立 XML; 可操作的 XML 绘图格式文件Visio 2013 文件格式必须为包进行操作。</span><span class="sxs-lookup"><span data-stu-id="0aa00-159">An XML Drawing Format file could be manipulated like a normal stand-alone XML; the Visio 2013 file format must be manipulated as a package.</span></span> <span data-ttu-id="0aa00-160">在 Visio 2013 中的 XML 已分为更轻松地消耗的部件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-160">In the Visio 2013, the XML has been divided up into parts for easier consumption.</span></span> <span data-ttu-id="0aa00-161">另一个显著更改是 Visio 2013 文件格式的文档部件描述标准 OPC （app.xml、 core.xml custom.xml） 中存储的所有文档属性。</span><span class="sxs-lookup"><span data-stu-id="0aa00-161">Another noticeable change is that the Visio 2013 file format stores all document properties in document parts described by the OPC standard (app.xml, core.xml, custom.xml).</span></span>
  
<span data-ttu-id="0aa00-162">但是，还有一次所有 Visio 开发人员都必须注意的重大更改：**单元格**、**行**和**部分**元素的介绍。</span><span class="sxs-lookup"><span data-stu-id="0aa00-162">However, there is one significant change that all Visio developers must be aware of: the introduction of the **Cell**, **Row**, and **Section** elements.</span></span> <span data-ttu-id="0aa00-163">在 XML 绘图文件格式架构中，由命名元素表示单个行和 ShapeSheet 中的单元格。</span><span class="sxs-lookup"><span data-stu-id="0aa00-163">In the XML Drawing File Format schema, individual rows and cells in the ShapeSheet are represented by named elements.</span></span> <span data-ttu-id="0aa00-164">例如，假设您拥有具有一个包含形状的**PinX**值为"2"（这意味着形状的旋转 pin 从左边缘的绘图的 2 英寸） 的单个页面的文档。</span><span class="sxs-lookup"><span data-stu-id="0aa00-164">For example, imagine that you have a document with a single page that contains a shape with a **PinX** value of "2" (meaning that the rotation pin of the shape is 2 inches from the left edge of the drawing).</span></span> <span data-ttu-id="0aa00-165">下面的代码中显示的 XML 绘图文件格式设置的相关标记。</span><span class="sxs-lookup"><span data-stu-id="0aa00-165">The relevant markup for that setting in the XML Drawing File Format is shown in the following code.</span></span> 
  
```XML
<Shape ID="1" TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape">
    <XForm> 
        <PinX Unit="IN">2</Pinx>
        <!--- Other cells in the Shape Transform section -->
    </XForm>
    <!--- Other rows and cells in the ShapeSheet -->
</Shape>

```

<span data-ttu-id="0aa00-166">此处**PinX**元素是**XForm**元素，这又是**形状**元素的子元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="0aa00-166">Here, the **PinX** element is a child of the **XForm** element, which is in turn a child of the **Shape** element.</span></span> <span data-ttu-id="0aa00-167">此模型 Visio ShapeSheet UI，其中将**PinX**单元格包含在形状的**Shape Transform**内容中。</span><span class="sxs-lookup"><span data-stu-id="0aa00-167">This models the Visio ShapeSheet UI, where the **PinX** cell is included in the **Shape Transform** section of a shape.</span></span> 
  
<span data-ttu-id="0aa00-168">在 Visio 2013 文件格式，ShapeSheet─ **PinX**， **LinePattern**，在**geometry**内容，etc.─are 由一种类型的**单元格**元素的 XML 元素中某一**MoveTo**行**X**单元格中所有单元格。</span><span class="sxs-lookup"><span data-stu-id="0aa00-168">In the Visio 2013 file format, all cells in the ShapeSheet─ **PinX**, **LinePattern**, an **X** cell in a **MoveTo** row in a **Geometry** section, etc.─are represented by one type of XML element, the **Cell** element.</span></span> <span data-ttu-id="0aa00-169">不同的**单元格**元素被 individuated 相互由其**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="0aa00-169">Different **Cell** elements are individuated from each other by the value of their **N** attribute.</span></span> <span data-ttu-id="0aa00-170">因此，在上面的示例中，ShapeSheet 中的**PinX**单元格中包含的数据存储在 VSDX 文件中的以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="0aa00-170">Thus, in the example from above, the data contained in the **PinX** cell in the ShapeSheet is stored in a VSDX file as shown in the following code.</span></span> 
  
```XML
<Shape TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape" ID="1">
    <Cell N="PinX" U="IN" V="2"/>
    <!--- Other cells in the ShapeSheet --> 
</Shape>
```

<span data-ttu-id="0aa00-171">**PinX** （以及如**LinePattern**或**LockSelect**调用"singleton 单元格"其他单个、 命名单元格） 的**单元格**元素是直接元素的子**形状**。</span><span class="sxs-lookup"><span data-stu-id="0aa00-171">The **Cell** element for **PinX** (as well as other individual, named cells called "singleton cells" like **LinePattern** or **LockSelect**) is a direct child of the **Shape** element.</span></span> <span data-ttu-id="0aa00-172">没有唯一元素需要为每个形状只能有一个**PinX**表示包含**PinX**单元格的行。</span><span class="sxs-lookup"><span data-stu-id="0aa00-172">No unique element is needed to represent the row that contains the **PinX** cell, as each shape can only have one **PinX**.</span></span>
  
<span data-ttu-id="0aa00-173">包括表格数据，如**geometry 内容**的部分呢？</span><span class="sxs-lookup"><span data-stu-id="0aa00-173">What about sections that include tabular data, like **Geometry** sections?</span></span> <span data-ttu-id="0aa00-174">有关这些分区中的单元格，Visio 2013 文件格式架构使用**部分**和**行**elements─also 按其**N**属性或作为显示 below─to **T**属性可分辨包含的数据。</span><span class="sxs-lookup"><span data-stu-id="0aa00-174">For the cells in those sections, the Visio 2013 file format schema uses **Section** and **Row** elements─also distinguished by their **N** attribute or **T** attribute as shown below─to contain the data.</span></span> <span data-ttu-id="0aa00-175">例如，同一形状的上一示例可能包含类似于下面的代码 XML 绘图架构中的**geometry 1**节中的数据。</span><span class="sxs-lookup"><span data-stu-id="0aa00-175">For example, the same shape from the previous example might contain data in the **Geometry 1** section that looks like the following code in the XML Drawing schema.</span></span> 
  
```XML
<Shape TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape" ID="1">
    <!--- Other cells in the ShapeSheet -->
    <Geom IX="0">
        <!--- Other cells and rows in the Geometry 1 section -->
        <LineTo IX="1">
            <X F="Width*0">0</X>
            <Y F="Height*0">0</Y>
        </LineTo>
    </Geom>
</Shape>

```

<span data-ttu-id="0aa00-176">但是，则它类似于下面的代码中的 Visio 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-176">However, it looks like the following code in the Visio 2013 file.</span></span>
  
```XML
<Shape TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape" ID="1">
    <!--- Other cells in the ShapeSheet -->
    <Section N="Geometry" IX="0"> 
        <!--- Other cells and rows in the Geometry 1 section -->
        <Row IX="1" T="LineTo">
            <Cell V="0" N="X" V="Width*0" />
            <Cell V="0" N="Y" V="Height*0" />
        </Row>
    </Section>
</Shape>

```

## <a name="developer-scenarios-for-working-with-the-visio-2013-file-format"></a><span data-ttu-id="0aa00-177">使用 Visio 2013 文件格式的开发人员方案</span><span class="sxs-lookup"><span data-stu-id="0aa00-177">Developer scenarios for working with the Visio 2013 file format</span></span>
<span data-ttu-id="0aa00-178"><a name="vis15_IntroVSDX_Scenarios"> </a></span><span class="sxs-lookup"><span data-stu-id="0aa00-178"></span></span>

<span data-ttu-id="0aa00-179">如上所述，Visio 2013 文件格式将利用如 ZIP 文件和 XML 存储数据的几种充分理解的技术。</span><span class="sxs-lookup"><span data-stu-id="0aa00-179">As explained above, the Visio 2013 file format leverages several well-understood technologies like ZIP files and XML to store data.</span></span> <span data-ttu-id="0aa00-180">操作绘图文件级别的 Visio 2013，解决方案只需使用.NET Framework 命名空间和类与使用 ZIP 文件或 XML，如[System.IO.Packaging](http://msdn.microsoft.com/zh-cn/library/system.io.packaging%28v=vs.110%29.aspx)或[System.Xml](http://msdn.microsoft.com/zh-cn/library/system.xml%28v=vs.110%29.aspx)关联。</span><span class="sxs-lookup"><span data-stu-id="0aa00-180">To manipulate a Visio 2013 drawing at the file level, a solution need only to use the .NET Framework namespaces and classes associated with working with ZIP files or XML, like [System.IO.Packaging](http://msdn.microsoft.com/zh-cn/library/system.io.packaging%28v=vs.110%29.aspx) or [System.Xml](http://msdn.microsoft.com/zh-cn/library/system.xml%28v=vs.110%29.aspx).</span></span>
  
<span data-ttu-id="0aa00-181">开发人员的 Visio 2013 文件格式的主要好处是，您可以读取和写入到 Visio 2013 文件不自动 Visio 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="0aa00-181">The key benefit to developers of the Visio 2013 file format is that you can read and write to Visio 2013 files without automating the Visio client application.</span></span> <span data-ttu-id="0aa00-182">您可以使用 Visio 2013 文件格式的考虑作为开发人员某些方案包括：</span><span class="sxs-lookup"><span data-stu-id="0aa00-182">Some scenarios that you might consider as a developer for working with Visio 2013 file format include:</span></span>
  
- <span data-ttu-id="0aa00-183">检查特定数据的单个 Visio 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-183">Checking individual Visio 2013 files for specific data.</span></span> <span data-ttu-id="0aa00-184">您可以有选择地阅读 ZIP 容器的其中一项，而无需提取整个文件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-184">You can selectively read one item out of the ZIP container without having to extract the whole file.</span></span>
    
- <span data-ttu-id="0aa00-185">使用特定内容更新 Visio 2013 文件的库。</span><span class="sxs-lookup"><span data-stu-id="0aa00-185">Updating libraries of Visio 2013 files with specific content.</span></span> <span data-ttu-id="0aa00-186">您可以编程方式更改所有背景页，以反映新的品牌准则中的徽标。</span><span class="sxs-lookup"><span data-stu-id="0aa00-186">You can programmatically change the logo in all of the background pages to reflect new branding guidelines.</span></span>
    
- <span data-ttu-id="0aa00-187">创建使用 Visio 2013 文件应用程序。</span><span class="sxs-lookup"><span data-stu-id="0aa00-187">Creating applications that consume Visio 2013 files.</span></span> <span data-ttu-id="0aa00-188">例如，您可以生成一个工具，读取 Visio 工作流关系图，然后执行自己基于该工作流的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="0aa00-188">For example, you can build a tool that reads a Visio workflow diagram and then executes its own business logic based upon that workflow.</span></span>
    
<span data-ttu-id="0aa00-189">请注意，因为这些解决方案均使用标准的 .NET Framework 程序集，可在客户端计算机上运行的大多数解决方案也可在服务器上运行！</span><span class="sxs-lookup"><span data-stu-id="0aa00-189">Be aware that because these solutions use standard .NET Framework assemblies, most solutions that can be run on a client machine can also be run on a server!</span></span>
  
## <a name="exploring-the-visio-2013-file-format-programmatically"></a><span data-ttu-id="0aa00-190">以编程方式浏览 Visio 2013 文件格式</span><span class="sxs-lookup"><span data-stu-id="0aa00-190">Exploring the Visio 2013 file format programmatically</span></span>
<span data-ttu-id="0aa00-191"><a name="vis15_IntroVSDX_Explore"> </a></span><span class="sxs-lookup"><span data-stu-id="0aa00-191"></span></span>

<span data-ttu-id="0aa00-192">使用 Visio 2013 文件格式任何开发人员的最基本、 基本任务是打开文件另存为包，然后访问的包中的各个部分。</span><span class="sxs-lookup"><span data-stu-id="0aa00-192">The most basic and fundamental task for any developer working with the Visio 2013 file format is opening the file as a package and then accessing individual parts within the package.</span></span> <span data-ttu-id="0aa00-193">**System.IO.Packaging.Package** WindowsBase.dll 中包含许多类，您可以打开和操作程序包和部件。</span><span class="sxs-lookup"><span data-stu-id="0aa00-193">The **System.IO.Packaging.Package** in the WindowsBase.dll contains many classes that enable you to open and manipulate packages and parts.</span></span> 
  
<span data-ttu-id="0aa00-194">在以下代码示例中，您可以了解如何打开 .vsdx 文件，读取包中的部件列表并获取关于每个部件的信息。</span><span class="sxs-lookup"><span data-stu-id="0aa00-194">In the following code sample, you can see how to open a .vsdx file, read the list of parts in the package, and get information about each part.</span></span>
  
### <a name="to-open-a-vsdx-file-and-view-the-document-parts"></a><span data-ttu-id="0aa00-195">打开 .vsdx 文件并查看文档部件</span><span class="sxs-lookup"><span data-stu-id="0aa00-195">To open a .vsdx file and view the document parts</span></span>

1. <span data-ttu-id="0aa00-196">打开 Visio 2013 并创建一个新文档。</span><span class="sxs-lookup"><span data-stu-id="0aa00-196">Open Visio 2013 and create a new document.</span></span>
    
2. <span data-ttu-id="0aa00-197">创建一个新文档并将其保存到桌面。</span><span class="sxs-lookup"><span data-stu-id="0aa00-197">Create a new document and save it to the Desktop.</span></span>
    
3. <span data-ttu-id="0aa00-198">打开 Visual Studio 2008。</span><span class="sxs-lookup"><span data-stu-id="0aa00-198">Open Visual Studio 2012.</span></span>
    
4. <span data-ttu-id="0aa00-199">在**文件**菜单中，选择**新建**，然后选择 * * 项目 * *。</span><span class="sxs-lookup"><span data-stu-id="0aa00-199">On the **File** menu, choose **New**, and then choose ** Project **.</span></span>
    
5. <span data-ttu-id="0aa00-200">在**Visual C#** 或**Visual Basic**，下展开**Windows**，，然后选择**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0aa00-200">Under **Visual C#** or **Visual Basic**, expand **Windows**, and then select **Console Application**.</span></span>
    
6. <span data-ttu-id="0aa00-201">在**名称**框中，键入 VisioFileExplorer。</span><span class="sxs-lookup"><span data-stu-id="0aa00-201">In the **Name** box, type 'VisioFileExplorer'.</span></span> <span data-ttu-id="0aa00-202">控制台应用程序项目打开。</span><span class="sxs-lookup"><span data-stu-id="0aa00-202">The Console Application project opens.</span></span> 
    
7. <span data-ttu-id="0aa00-203">在**解决方案资源管理器**中，右键单击**VisioFileExplorer**，，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="0aa00-203">In the **Solution Explorer**, right-click **VisioFileExplorer**, and then click **Add Reference**.</span></span> 
    
8. <span data-ttu-id="0aa00-204">在**添加引用**对话框的**程序集**，展开**框架**，，然后选择**WindowsBase**。</span><span class="sxs-lookup"><span data-stu-id="0aa00-204">In the **Add Reference** dialog box, under **Assemblies**, expand **Framework**, and then choose **WindowsBase**.</span></span>
    
9. <span data-ttu-id="0aa00-205">将以下代码粘贴到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="0aa00-205">Paste the following code into the solution.</span></span>
    
  ```cs
  using System;
  using System.Collections.Generic;
  using System.Linq;
  using System.Text;
  using System.IO;
  using System.IO.Packaging;
  using System.Diagnostics;
  namespace VisioFileExplorer
  {
      class Program
      {
          static void Main(string[] args)
          {    
              try
              {
                  Console.WriteLine("Opening the VSDX file ...");
                  // Need to get the folder path for the Desktop
                  // where the file is saved.
                  string dirPath = System.Environment.GetFolderPath(
                      System.Environment.SpecialFolder.Desktop);
                  DirectoryInfo myDir = new DirectoryInfo(dirPath);
                  // It is a best practice to get the file name string
                  // using a FileInfo object, but it isn't necessary.
                  FileInfo[] fInfos = myDir.GetFiles("*.vsdx");
                  FileInfo fi = fInfos[0];
                  string fName = fi.FullName;
                  // We're not going to do any more than open
                  // and read the list of parts in the package, although
                  // we can create a package or read/write what's inside.
                  using (Package fPackage = Package.Open(
                      fName, FileMode.Open, FileAccess.Read))
                  {
                      
                      // The way to get a reference to a package part is
                      // by using its URI. Thus, we're reading the URI
                      // for each part in the package.
                      PackagePartCollection fParts = fPackage.GetParts();
                      foreach (PackagePart fPart in fParts)
                      {
                          Console.WriteLine("Package part: {0}", fPart.Uri);
                      }
                  }   
              }
              catch (Exception err)
              {
                  Console.WriteLine("Error: {0}", err.Message);
              }
              finally
              {
                  Console.Write("\nPress any key to continue ...");
                  Console.ReadKey();
              }   
          }
      }
  }
  ```

  ```vb
  Imports System
  Imports System.Collections.Generic
  Imports System.Linq
  Imports System.Text
  Imports System.IO
  Imports System.IO.Packaging
  Imports System.Diagnostics
  Module Module1
      Sub Main()
          Try
              Console.WriteLine("Opening the VSDX file ...")
              ' Need to get the folder path for the Desktop
              ' or where the file is saved.
              Dim dirPath As String = System.Environment.GetFolderPath( _
                  System.Environment.SpecialFolder.Desktop)
              Dim myDir As New DirectoryInfo(dirPath)
              ' It is a best practice to get the file name string
              ' using a FileInfo object, but it isn't necessary.
              Dim fInfos As FileInfo() = myDir.GetFiles("*.vsdx")
              Dim fi As FileInfo = fInfos(0)
              Dim fName As String = fi.FullName
              ' We don't need to do any more than open
              ' and read the list of parts in the package, although
              ' we can create a package or read/write what's inside.
              Using fPackage As Package = Package.Open( _
                  fName, FileMode.Open, FileAccess.Read)
                  ' The way to get a reference to a document part is
                  ' by using its URI. Thus, we're reading the URI
                  ' for each document part in the package.
                  Dim fParts As PackagePartCollection = fPackage.GetParts()
                  For Each fPart As PackagePart In fParts
                      Console.WriteLine("Package part: {0}", fPart.Uri)
                  Next
              End Using
          Catch err As Exception
              Console.WriteLine("Error: {0}", err.Message)
          Finally
              Console.Write(vbLf &amp; "Press any key to continue ...")
              Console.ReadKey()
          End Try
      End Sub
  End Module
  
  ```

10. <span data-ttu-id="0aa00-p126">按 F5 调试解决方案。该程序运行完成后，按任意键退出。</span><span class="sxs-lookup"><span data-stu-id="0aa00-p126">Press F5 to debug the solution. When the program has completed running, press any key to exit.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0aa00-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0aa00-208">See also</span></span>
<span data-ttu-id="0aa00-209"><a name="vis15_IntroVSDX_Resources"> </a></span><span class="sxs-lookup"><span data-stu-id="0aa00-209"></span></span>

<span data-ttu-id="0aa00-210">关于 Visio 2013 文件格式、 开放打包约定或如何以编程方式与 Visio 2013or Office OpenXML 文件的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="0aa00-210">For more information about the Visio 2013 file format, the Open Packaging Convention, or how to work with Visio 2013or Office OpenXML files programmatically, see the following resources:</span></span>
  
- [<span data-ttu-id="0aa00-211">面向开发人员的 Visio</span><span class="sxs-lookup"><span data-stu-id="0aa00-211">Visio for developers</span></span>](http://msdn.microsoft.com/zh-cn/office/aa905478.aspx)
    
- <span data-ttu-id="0aa00-212">[OPC： 打包您的数据的新标准](http://msdn.microsoft.com/zh-cn/magazine/cc163372.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0aa00-212">[OPC: A New Standard for Packaging Your Data](http://msdn.microsoft.com/zh-cn/magazine/cc163372.aspx).</span></span>
    
- [<span data-ttu-id="0aa00-213">开放打包约定的基础知识</span><span class="sxs-lookup"><span data-stu-id="0aa00-213">Essentials of the Open Packaging Conventions</span></span>](http://msdn.microsoft.com/zh-cn/library/ee361919.aspx)
    
- [<span data-ttu-id="0aa00-214">介绍 Office (2007) Open XML 文件格式</span><span class="sxs-lookup"><span data-stu-id="0aa00-214">Introducing the Office (2007) Open XML File Formats</span></span>](http://msdn.microsoft.com/zh-cn/library/aa338205.aspx)
    

