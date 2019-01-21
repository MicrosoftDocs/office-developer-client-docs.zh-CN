---
title: Visio 文件格式 (.vsdx) 简介
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.assetid: 69736f40-8f67-46c2-abf6-82dffecb2274
description: 了解 Visio 2013 中的新文件格式，探索以编程方式处理 Visio 2013 文件格式的一些高级概念，并创建一个用于检查 Visio 2013 文件的简单控制台应用程序。
localization_priority: Priority
ms.openlocfilehash: 74c0f05a1db280386f3dc9dfd23da73a9b2daaf5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699070"
---
# <a name="introduction-to-the-visio-file-format-vsdx"></a><span data-ttu-id="eed43-103">Visio 文件格式 (.vsdx) 简介</span><span class="sxs-lookup"><span data-stu-id="eed43-103">Introduction to the Visio file format (.vsdx)</span></span>

<span data-ttu-id="eed43-104">了解 Visio 2013 中的新文件格式，探索以编程方式处理 Visio 2013 文件格式的一些高级概念，并创建一个用于检查 Visio 2013 文件的简单控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="eed43-104">Learn about the new file format in vis15short, explore some high-level concepts for working with the vis15short file format programmatically, and create a simple console application that examines a vis15short file.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eed43-105">**本文内容**         [简介](#vis15_IntroVSDX_Intro)          [Visio 2013 文件格式本质上是什么？](#vis15_IntroVSDX_What)</span><span class="sxs-lookup"><span data-stu-id="eed43-105">**In this article**         [Introduction](#vis15_IntroVSDX_Intro)          [What is the Visio 2013 file format "under the hood"?](#vis15_IntroVSDX_What)</span></span>          <span data-ttu-id="eed43-106">[开发人员使用 Visio 2013 文件格式的应用场景](#vis15_IntroVSDX_Scenarios)          [以编程方式探索 Visio 2013 文件格式](#vis15_IntroVSDX_Explore)          [其他资源](#vis15_IntroVSDX_Resources)</span><span class="sxs-lookup"><span data-stu-id="eed43-106">[Developer scenarios for working with the Visio 2013 file format](#vis15_IntroVSDX_Scenarios)          [Exploring the Visio 2013 file format programmatically](#vis15_IntroVSDX_Explore)          [Additional resources](#vis15_IntroVSDX_Resources)</span></span>||
   
## <a name="introduction"></a><span data-ttu-id="eed43-107">简介</span><span class="sxs-lookup"><span data-stu-id="eed43-107">Introduction</span></span>
<span data-ttu-id="eed43-108"><a name="vis15_IntroVSDX_Intro"> </a></span><span class="sxs-lookup"><span data-stu-id="eed43-108"></span></span>

<span data-ttu-id="eed43-109">Visio 2013 为 Visio 引入了一种新的文件格式 (.vsdx)，此格式取代了 Visio 二进制文件格式 (.vsd) 和 Visio XML 绘图文件格式 (.vdx)。</span><span class="sxs-lookup"><span data-stu-id="eed43-109">Visio 2013 introduces a new file format (.vsdx) for Visio that replaces the Visio binary file format (.vsd) and Visio XML Drawing file format (.vdx).</span></span> <span data-ttu-id="eed43-110">由于 Visio 2013 文件格式基于开放打包约定和 XML，熟悉这些技术的开发人员可以快速了解如何以编程方式处理 Visio 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="eed43-110">Because the Visio 2013 file format is based upon Open Packaging Conventions and XML, developers who are familiar with these technologies can quickly learn how to work with Visio 2013 files programmatically.</span></span> <span data-ttu-id="eed43-111">熟悉 Visio 早期版本的 Visio XML 绘图文件格式 (.vdx) 的开发人员可以在 .vsdx 文件格式的部分中发现许多相同的 XML 结构。</span><span class="sxs-lookup"><span data-stu-id="eed43-111">Developers who are familiar with the Visio XML Drawing file format (.vdx) from previous versions of Visio can find many of the same XML structures within the parts of .vsdx file format.</span></span> <span data-ttu-id="eed43-112">由于第三方软件可以在文件格式级别操作 Visio 文件，因此与 Visio 文件的互操作性大大增强。</span><span class="sxs-lookup"><span data-stu-id="eed43-112">Interoperability with Visio files is greatly increased since third-party software can manipulate Visio files at a file format level.</span></span> <span data-ttu-id="eed43-113">Microsoft SharePoint Server 2013 中的 Visio Services 支持 Visio 2013 文件格式，而无需使用发布到 SharePoint Server 的“中间”文件格式。</span><span class="sxs-lookup"><span data-stu-id="eed43-113">The Visio 2013 file format is supported on Visio Services in Microsoft SharePoint Server 2013, without the need of an "intermediary" file format for publishing to SharePoint Server.</span></span>
  
<span data-ttu-id="eed43-114">Visio 2013 文件格式包含几种文件类型（按扩展名区分）。</span><span class="sxs-lookup"><span data-stu-id="eed43-114">There are several file types, by extension, that comprise the vis15short file format. These extensions include:</span></span> <span data-ttu-id="eed43-115">这些扩展名包括：</span><span class="sxs-lookup"><span data-stu-id="eed43-115">These extensions include:</span></span>
  
- <span data-ttu-id="eed43-116">.vsdx（Visio 绘图）</span><span class="sxs-lookup"><span data-stu-id="eed43-116">.vsdx (Visio drawing)</span></span>
    
- <span data-ttu-id="eed43-117">.vsdm（Visio 启用宏的绘图）</span><span class="sxs-lookup"><span data-stu-id="eed43-117">.vsdm (Visio macro-enabled drawing)</span></span>
    
- <span data-ttu-id="eed43-118">.vssx（Visio 模具）</span><span class="sxs-lookup"><span data-stu-id="eed43-118">.vssx (Visio stencil)</span></span>
    
- <span data-ttu-id="eed43-119">.vssm（Visio 启用宏的模具）</span><span class="sxs-lookup"><span data-stu-id="eed43-119">.vssm (Visio macro-enabled stencil)</span></span>
    
- <span data-ttu-id="eed43-120">.vstx（Visio 模板）</span><span class="sxs-lookup"><span data-stu-id="eed43-120">.vstx (Visio template)</span></span>
    
- <span data-ttu-id="eed43-121">.vstm（Visio 启用宏的模板）</span><span class="sxs-lookup"><span data-stu-id="eed43-121">.vstm (Visio macro-enabled template)</span></span>
    
> [!NOTE]
> <span data-ttu-id="eed43-p104">仅启用宏的文件（.vsdm、.vssm、.vstm）可以存储 VBA 宏。不能将宏存储在扩展名为 .vsdx、.vssx 或 .vstx 的文件中。</span><span class="sxs-lookup"><span data-stu-id="eed43-p104">Only the macro-enabled files (.vsdm, .vssm, .vstm) can store VBA macros. You cannot store macros in files with a .vsdx, .vssx, or .vstx extension.</span></span> 
  
## <a name="what-is-the-visio-2013-file-format-under-the-hood"></a><span data-ttu-id="eed43-124">Visio 2013 文件格式本质上是什么？</span><span class="sxs-lookup"><span data-stu-id="eed43-124">What is the Visio 2013 file format “under the hood”?</span></span>
<span data-ttu-id="eed43-125"><a name="vis15_IntroVSDX_What"> </a></span><span class="sxs-lookup"><span data-stu-id="eed43-125"></span></span>

<span data-ttu-id="eed43-126">Visio 2013 文件格式使用开放打包约定 (OPC)，定义了使用某种容器（例如 ZIP 文件）将应用程序数据与相关资源存储在一起的结构化方法。</span><span class="sxs-lookup"><span data-stu-id="eed43-126">The Visio 2013 file format uses the Open Packing Conventions (OPC), which defines a structured means to store application data together with related resources using a container of some sort─for example, a ZIP file.</span></span> <span data-ttu-id="eed43-127">在底层，Visio 2013 文件实际上是包含其他类型文件的 ZIP 容器。</span><span class="sxs-lookup"><span data-stu-id="eed43-127">At a basic level, a Visio 2013 file is really a ZIP container that contains other types of files.</span></span> <span data-ttu-id="eed43-128">实际上，可以将 Visio 2013 中的绘图另存为 .vsdx 文件，在 Windows 资源管理器中将文件扩展名重命名为“\*.zip”，然后像文件夹一样打开该文件以查看其中的内容。</span><span class="sxs-lookup"><span data-stu-id="eed43-128">In fact, you can save a drawing in Visio 2013 as a .vsdx file, rename the file extension to "\*.zip" in Windows Explorer, and then open the file like a folder to see the contents inside.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="eed43-129">本文仅提供开放打包约定的简要概述。</span><span class="sxs-lookup"><span data-stu-id="eed43-129">This article contains only a brief overview of the Open Packaging Conventions. You can find more detailed coverage of the conventions in other articles:</span></span> <span data-ttu-id="eed43-130">你可以在其他文章中找到有关此类约定的更多详细信息：> 有关开放打包约定本身的详细信息，请参阅 [OPC：数据打包的新标准](https://msdn.microsoft.com/magazine/cc163372.aspx)。</span><span class="sxs-lookup"><span data-stu-id="eed43-130">You can find more detailed coverage of the conventions in other articles: >  For more information about the Open Packaging Conventions themselves, see [OPC: A New Standard for Packaging Your Data](https://msdn.microsoft.com/magazine/cc163372.aspx).</span></span> <span data-ttu-id="eed43-131">> 有关开放打包约定及其在 Microsoft Office 文件中的使用的详细信息，请参阅[开放打包约定的基础知识](https://msdn.microsoft.com/library/ee361919.aspx)和 [Office (2007) Open XML 文件格式简介](https://msdn.microsoft.com/library/aa338205.aspx)。</span><span class="sxs-lookup"><span data-stu-id="eed43-131">For more information about the Open Packaging Conventions and their use in officenv files, see  Essentials of the Open Packaging Conventions http://msdn.microsoft.com/en-us/library/ee361919.aspx  and  Introducing the Office (2007) Open XML File Formats http://msdn.microsoft.com/en-us/library/aa338205.aspx .</span></span> 
  
### <a name="packages-and-package-parts"></a><span data-ttu-id="eed43-132">包和包部件</span><span class="sxs-lookup"><span data-stu-id="eed43-132">Packages and Package Parts</span></span>

<span data-ttu-id="eed43-133">如前所述，Visio 2013 文件是 ZIP 容器或“包”，其中包含其他文件（称为“包部件”）。</span><span class="sxs-lookup"><span data-stu-id="eed43-133">As started earlier, Visio 2013 files are ZIP containers or "packages" that hold other files (called "package parts") within them.</span></span> <span data-ttu-id="eed43-134">包部件可以是 XML 文件、图像甚至是 VBA 解决方案。</span><span class="sxs-lookup"><span data-stu-id="eed43-134">A package part can be an XML file, an image, even a VBA solution.</span></span> <span data-ttu-id="eed43-135">包内的部件可以进一步分为两大类：“文档部件”和“关系部件”。</span><span class="sxs-lookup"><span data-stu-id="eed43-135">The parts within the package can be further divided into two broad categories, "document parts" and "relationship parts."</span></span> <span data-ttu-id="eed43-136">文档部件包含 Visio 文件的实际内容和元数据，如文件名、第一页和文件包含的所有形状，甚至是形状的数据连接。</span><span class="sxs-lookup"><span data-stu-id="eed43-136">The document parts contain the actual content and metadata of the Visio file, like the name of the file, the first page and all of the shapes that it contains, and even the data connections for the shapes.</span></span> <span data-ttu-id="eed43-137">包中的图像和文本文件被视为文档部件。</span><span class="sxs-lookup"><span data-stu-id="eed43-137">Images and text files within the package are considered document parts.</span></span> <span data-ttu-id="eed43-138">本文稍后将详细介绍关系部件。</span><span class="sxs-lookup"><span data-stu-id="eed43-138">Relationship parts are described in more detail later in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eed43-139">如果使用 ZIP 实用工具打开 Visio 2013 文件，可能会看到 ZIP 包中包含的多个文件夹。</span><span class="sxs-lookup"><span data-stu-id="eed43-139">If you open a Visio 2013 file using a ZIP utility, you can probably see several folders contained inside of the ZIP package.</span></span> <span data-ttu-id="eed43-140">甚至可以使用 ZIP 实用工具操作这些子地址，例如文件夹。</span><span class="sxs-lookup"><span data-stu-id="eed43-140">You can even manipulate these sub-addresses like folders using a ZIP utility.</span></span> <span data-ttu-id="eed43-141">但是，这些“文件夹”表示 ZIP 包中的子地址，而不是实际文件夹。</span><span class="sxs-lookup"><span data-stu-id="eed43-141">However, these "folders" represent sub-addresses within the ZIP package, not actual folders.</span></span> <span data-ttu-id="eed43-142">不能使用文件夹的程序等效项来处理解决方案中的这些子地址。</span><span class="sxs-lookup"><span data-stu-id="eed43-142">You cannot use the programmatic equivalents of folders to work with these sub-addresses in your solution.</span></span> 
  
<span data-ttu-id="eed43-p109">包部件─文档部件和关系部件─也具有相关的内容类型。这些内容类型是用于定义 MIME 媒体类型的字符串。这些内容类型指定可以包含在文件中的 MIME 类型并限定其范围。</span><span class="sxs-lookup"><span data-stu-id="eed43-p109">Package parts─both document parts and relationship parts─also have associated content types. These content types are strings that define a MIME media type. These content types specify and scope the kind of MIME types that can be contained in the file.</span></span>
  
### <a name="relationships"></a><span data-ttu-id="eed43-146">关系</span><span class="sxs-lookup"><span data-stu-id="eed43-146">Relationships</span></span>

<span data-ttu-id="eed43-147">关系部件（以扩展名“\*.rels”结尾并存储在“_rels”文件夹中）描述了包中的部件如何相互关联并提供文件的结构。</span><span class="sxs-lookup"><span data-stu-id="eed43-147">The relationship parts (which end with the extension "\*.rels" and are stored in a "_rels" folder) describe how the parts within the package relate to each other and provide the structure of the file.</span></span> <span data-ttu-id="eed43-148">独立的 XML 文档使用元素的父/子关系来确定实体之间的关系。</span><span class="sxs-lookup"><span data-stu-id="eed43-148">A standalone XML document uses the parent/child relationship of elements to determine the relationship of entities to each other.</span></span> <span data-ttu-id="eed43-149">其他文件可以使用其他层次结构或文件夹结构来描述文件内容关系。</span><span class="sxs-lookup"><span data-stu-id="eed43-149">Other files may use other hierarchies or file folder structure to describe the interaction of content in the file.</span></span> <span data-ttu-id="eed43-150">对于 Visio 2013 文件格式，如果包中包含正确的一组部件并且包中包含部件之间的关系，则该包便是有效的 Visio 文件。</span><span class="sxs-lookup"><span data-stu-id="eed43-150">For the Visio 2013 file format, the package is a valid Visio file if it contains the correct set of parts and the package contains the relationships between the parts.</span></span> 
  
<span data-ttu-id="eed43-p111">关系部件是用于描述包中不同文档部件之间关系的 XML 文档。它们定义了两个项目之间的关联：指定源（由关系文件的名称和位置定义）和指定目标文档部件。例如，关系部件用于描述哪些主控形状与文件相关联，页面和文件以及页面之间有何关系，或者图像和对象与特定页面有何关系。</span><span class="sxs-lookup"><span data-stu-id="eed43-p111">Relationship parts are XML documents that describe the relationships between different document parts within the package. They define an association between two items: a specified source (defined by the name and location of the relationship file) and a specified target document part. For example, relationship parts are used to describe which shape masters are associated with the file, how pages relate to the file and to each other, or how images and objects relate to a specific page.</span></span> 
  
### <a name="similarities-and-differences-with-visio-vdx-schema"></a><span data-ttu-id="eed43-154">与 Visio VDX 架构的相似性和区别</span><span class="sxs-lookup"><span data-stu-id="eed43-154">Similarities and differences with visnvshort VDX schema</span></span>

<span data-ttu-id="eed43-155">如前所述，以前版本的 Visio 还包括基于 XML 的文件格式、Visio XML 绘图格式或 .vdx。</span><span class="sxs-lookup"><span data-stu-id="eed43-155">As mentioned, past versions of Visio also included an XML-based file format, the Visio XML Drawing Format or .vdx.</span></span> <span data-ttu-id="eed43-156">（在以前版本的 Visio 中，用于 Visio XML 绘图格式的架构称为 DatadiagramML。）Visio XML 架构中的某些部分在两种文件格式之间保持不变。</span><span class="sxs-lookup"><span data-stu-id="eed43-156">(In previous versions of Visio, the schema used for the Visio XML Drawing Format is called DatadiagramML.) Some pieces from the Visio XML schema have stayed the same between the two file formats.</span></span> <span data-ttu-id="eed43-157">例如，**Windows** 元素及其子元素保持不变，例外之处在于 **Windows** 元素现在是 XML 文档 (window.xml) 的根元素。</span><span class="sxs-lookup"><span data-stu-id="eed43-157">For example, the **Windows** element and its children remain unchanged─with the exception that the **Windows** element is now a root element of an XML document (window.xml).</span></span> 
  
<span data-ttu-id="eed43-158">XML 绘图格式和 Visio 2013 文件格式之间的最大区别是打包。</span><span class="sxs-lookup"><span data-stu-id="eed43-158">The largest difference between the XML Drawing Format and the Visio 2013 file format is the packaging.</span></span> <span data-ttu-id="eed43-159">可以像普通的独立 XML 一样对 XML 绘图格式文件进行操作；必须将 Visio 2013 文件格式作为包进行操作。</span><span class="sxs-lookup"><span data-stu-id="eed43-159">An XML Drawing Format file could be manipulated like a normal stand-alone XML; the Visio 2013 file format must be manipulated as a package.</span></span> <span data-ttu-id="eed43-160">在 Visio 2013 中，XML 已分成多个部分以便于使用。</span><span class="sxs-lookup"><span data-stu-id="eed43-160">In the Visio 2013, the XML has been divided up into parts for easier consumption.</span></span> <span data-ttu-id="eed43-161">另一个明显的变化是 Visio 2013 文件格式将所有文档属性存储在由 OPC 标准描述的文档部分（app.xml、core.xml、custom.xml）中。</span><span class="sxs-lookup"><span data-stu-id="eed43-161">Another noticeable change is that the Visio 2013 file format stores all document properties in document parts described by the OPC standard (app.xml, core.xml, custom.xml).</span></span>
  
<span data-ttu-id="eed43-162">但是，所有 Visio 开发人员必须注意的一个重大变化是引入了 **Cell**、**Row** 和 **Section** 元素。</span><span class="sxs-lookup"><span data-stu-id="eed43-162">However, there is one significant change that all Visio developers must be aware of: the introduction of the **Cell**, **Row**, and **Section** elements.</span></span> <span data-ttu-id="eed43-163">在 XML 绘图文件格式架构中，ShapeSheet 中的各个行和单元格由命名元素表示。</span><span class="sxs-lookup"><span data-stu-id="eed43-163">In the XML Drawing File Format schema, individual rows and cells in the ShapeSheet are represented by named elements.</span></span> <span data-ttu-id="eed43-164">例如，假设有一个单页文档包含 **PinX** 值为“2”的形状（意味着形状的旋转固定点距离图形的左边缘为 2 英寸）。</span><span class="sxs-lookup"><span data-stu-id="eed43-164">For example, imagine that you have a document with a single page that contains a shape with a **PinX** value of "2" (meaning that the rotation pin of the shape is 2 inches from the left edge of the drawing).</span></span> <span data-ttu-id="eed43-165">在 XML 绘图文件格式中，该设置的相关标记如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="eed43-165">The relevant markup for that setting in the XML Drawing File Format is shown in the following code.</span></span> 
  
```XML
<Shape ID="1" TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape">
    <XForm> 
        <PinX Unit="IN">2</Pinx>
        <!--- Other cells in the Shape Transform section -->
    </XForm>
    <!--- Other rows and cells in the ShapeSheet -->
</Shape>

```

<span data-ttu-id="eed43-166">在此处，**PinX** 元素是 **XForm** 元素的子元素，而后者又是 **Shape** 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="eed43-166">Here, the **PinX** element is a child of the **XForm** element, which is in turn a child of the **Shape** element. This models the visnvshort ShapeSheet UI, where the PinX cell is included in the Shape Transform section of a shape.</span></span> <span data-ttu-id="eed43-167">这样可以为 Visio ShapeSheet UI 建模，其中的 **PinX** 单元格包含在形状的 **Shape Transform** 节中。</span><span class="sxs-lookup"><span data-stu-id="eed43-167">Here, the PinX element is a child of the XForm element, which is in turn a child of the Shape element. This models the visnvshort ShapeSheet UI, where the PinX cell is included in the Shape Transform section of a shape.</span></span> 
  
<span data-ttu-id="eed43-168">在 Visio 2013 文件格式中，ShapeSheet 中的所有单元格（**PinX**、**LinePattern**、**Geometry** 节的 **MoveTo** 行中的 **X** 单元格等）由一种类型的 XML 元素（**Cell** 元素）表示。</span><span class="sxs-lookup"><span data-stu-id="eed43-168">In the Visio 2013 file format, all cells in the ShapeSheet─ **PinX**, **LinePattern**, an **X** cell in a **MoveTo** row in a **Geometry** section, etc.─are represented by one type of XML element, the **Cell** element.</span></span> <span data-ttu-id="eed43-169">不同的 **Cell** 元素通过其 **N** 属性的值彼此个体化。</span><span class="sxs-lookup"><span data-stu-id="eed43-169">Different **Cell** elements are individuated from each other by the value of their **N** attribute.</span></span> <span data-ttu-id="eed43-170">因此，在上面的示例中，ShapeSheet 中的 **PinX** 单元格包含的数据存储在 VSDX 文件中，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="eed43-170">Thus, in the example from above, the data contained in the **PinX** cell in the ShapeSheet is stored in a VSDX file as shown in the following code.</span></span> 
  
```XML
<Shape TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape" ID="1">
    <Cell N="PinX" U="IN" V="2"/>
    <!--- Other cells in the ShapeSheet --> 
</Shape>
```

<span data-ttu-id="eed43-171">**PinX** 的 **Cell** 元素（以及其他称为“单一单元格”的单独命名单元格，如 **LinePattern** 或 **LockSelect**）是 **Shape** 元素的直接子元素。</span><span class="sxs-lookup"><span data-stu-id="eed43-171">The **Cell** element for **PinX** (as well as other individual, named cells called “singleton cells” like **LinePattern** or **LockSelect**) is a direct child of the **Shape** element. No unique element is needed to represent the row that contains the PinX cell, as each shape can only have one PinX.</span></span> <span data-ttu-id="eed43-172">不需要唯一元素来表示包含 **PinX** 单元格的行，因为每个形状只能有一个 **PinX**。</span><span class="sxs-lookup"><span data-stu-id="eed43-172">The **Cell** element for **PinX** (as well as other individual, named cells called “singleton cells” like LinePattern or LockSelect) is a direct child of the Shape element. No unique element is needed to represent the row that contains the PinX cell, as each shape can only have one PinX.</span></span>
  
<span data-ttu-id="eed43-173">那些包含表格数据的节（比如 **Geometry** 节）又如何呢？</span><span class="sxs-lookup"><span data-stu-id="eed43-173">What about sections that include tabular data, like **Geometry** sections?</span></span> <span data-ttu-id="eed43-174">对于这些节中的单元格，Visio 2013 文件格式架构使用 **Section** 和 **Row** 元素（也可以通过它们的 **N** 属性或 **T** 属性进行区分，如下所示）来包含数据。</span><span class="sxs-lookup"><span data-stu-id="eed43-174">For the cells in those sections, the Visio 2013 file format schema uses **Section** and **Row** elements─also distinguished by their **N** attribute or **T** attribute as shown below─to contain the data.</span></span> <span data-ttu-id="eed43-175">例如，前一个示例中的相同形状可能在 **Geometry 1** 节中包含类似于以下采用 XML 绘图架构的代码的数据。</span><span class="sxs-lookup"><span data-stu-id="eed43-175">For example, the same shape from the previous example might contain data in the **Geometry 1** section that looks like the following code in the XML Drawing schema.</span></span> 
  
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

<span data-ttu-id="eed43-176">但是，它在 Visio 2013 文件中如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="eed43-176">However, it looks like the following code in the vis15short file.</span></span>
  
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

## <a name="developer-scenarios-for-working-with-the-visio-2013-file-format"></a><span data-ttu-id="eed43-177">开发人员使用 Visio 2013 文件格式的应用场景</span><span class="sxs-lookup"><span data-stu-id="eed43-177">Developer scenarios for working with the Visio 2013 file format</span></span>
<span data-ttu-id="eed43-178"><a name="vis15_IntroVSDX_Scenarios"> </a></span><span class="sxs-lookup"><span data-stu-id="eed43-178"></span></span>

<span data-ttu-id="eed43-179">如上所述，Visio 2013 文件格式利用了一些易于理解的技术（如 ZIP 文件和 XML）来存储数据。</span><span class="sxs-lookup"><span data-stu-id="eed43-179">As explained above, the Visio 2013 file format leverages several well-understood technologies like ZIP files and XML to store data.</span></span> <span data-ttu-id="eed43-180">若要在文件级别操作 Visio 2013 绘图，一种解决方案只需要使用与 ZIP 文件或 XML（如 [System.IO.Packaging](https://msdn.microsoft.com/library/system.io.packaging%28v=vs.110%29.aspx) 或 [System.Xml](https://msdn.microsoft.com/library/system.xml%28v=vs.110%29.aspx)）的处理相关联的 .NET Framework 命名空间和类。</span><span class="sxs-lookup"><span data-stu-id="eed43-180">To manipulate a Visio 2013 drawing at the file level, a solution need only to use the .NET Framework namespaces and classes associated with working with ZIP files or XML, like [System.IO.Packaging](https://msdn.microsoft.com/library/system.io.packaging%28v=vs.110%29.aspx) or [System.Xml](https://msdn.microsoft.com/library/system.xml%28v=vs.110%29.aspx).</span></span>
  
<span data-ttu-id="eed43-181">对 Visio 2013 文件格式的开发人员而言，主要好处在于可以在不自动执行 Visio 客户端应用程序的情况下读取和写入 Visio 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="eed43-181">The key benefit to developers of the Visio 2013 file format is that you can read and write to Visio 2013 files without automating the Visio client application.</span></span> <span data-ttu-id="eed43-182">可视为使用 Visio 2013 文件格式的开发人员的一些应用场景包括：</span><span class="sxs-lookup"><span data-stu-id="eed43-182">Some scenarios that you might consider as a developer for working with Visio 2013 file format include:</span></span>
  
- <span data-ttu-id="eed43-183">检查各个 Visio 2013 文件以查找特定数据。</span><span class="sxs-lookup"><span data-stu-id="eed43-183">Checking individual Visio 2013 files for specific data.</span></span> <span data-ttu-id="eed43-184">你可以选择性地从 ZIP 容器中读出一项，而无需提取整个文件。</span><span class="sxs-lookup"><span data-stu-id="eed43-184">Checking individual vis15short files for specific data. You can selectively read one item out of the ZIP container without having to extract the whole file.</span></span>
    
- <span data-ttu-id="eed43-185">使用特定内容更新 Visio 2013 文件的库。</span><span class="sxs-lookup"><span data-stu-id="eed43-185">Updating libraries of Visio 2013 files with specific content.</span></span> <span data-ttu-id="eed43-186">你可以用编程方式更改所有背景页面中的徽标，以反映新的品牌准则。</span><span class="sxs-lookup"><span data-stu-id="eed43-186">Updating libraries of vis15short files with specific content. You can programmatically change the logo in all of the background pages to reflect new branding guidelines.</span></span>
    
- <span data-ttu-id="eed43-187">创建使用 Visio 2013 文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="eed43-187">Creating applications that consume Visio 2013 files.</span></span> <span data-ttu-id="eed43-188">例如，你可以构建一个工具，用于读取 Visio 工作流图，然后根据该工作流执行自己的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="eed43-188">Creating applications that consume vis15short files. For example, you can build a tool that reads a visnvshort workflow diagram and then executes its own business logic based upon that workflow.</span></span>
    
<span data-ttu-id="eed43-189">请注意，因为这些解决方案均使用标准的 .NET Framework 程序集，可在客户端计算机上运行的大多数解决方案也可在服务器上运行！</span><span class="sxs-lookup"><span data-stu-id="eed43-189">Be aware that because these solutions use standard .NET Framework assemblies, most solutions that can be run on a client machine can also be run on a server!</span></span>
  
## <a name="exploring-the-visio-2013-file-format-programmatically"></a><span data-ttu-id="eed43-190">以编程方式探索 Visio 2013 文件格式</span><span class="sxs-lookup"><span data-stu-id="eed43-190">Exploring the Visio 2013 file format programmatically</span></span>
<span data-ttu-id="eed43-191"><a name="vis15_IntroVSDX_Explore"> </a></span><span class="sxs-lookup"><span data-stu-id="eed43-191"></span></span>

<span data-ttu-id="eed43-192">对于使用 Visio 2013 文件格式的任何开发人员来说，最基本和最重要的任务是将文件作为包打开，然后访问包中的各个部件。</span><span class="sxs-lookup"><span data-stu-id="eed43-192">The most basic and fundamental task for any developer working with the vis15short file format is opening the file as a package and then accessing individual parts within the package. The System.IO.Packaging.Package in the WindowsBase.dll contains many classes that enable you to open and manipulate packages and parts.</span></span> <span data-ttu-id="eed43-193">WindowsBase.dll 中的 **System.IO.Packaging.Package** 包含许多可用于打开和操作包和部件的类。</span><span class="sxs-lookup"><span data-stu-id="eed43-193">The most basic and fundamental task for any developer working with the vis15short file format is opening the file as a package and then accessing individual parts within the package. The **System.IO.Packaging.Package** in the WindowsBase.dll contains many classes that enable you to open and manipulate packages and parts.</span></span> 
  
<span data-ttu-id="eed43-194">在以下代码示例中，您可以了解如何打开 .vsdx 文件，读取包中的部件列表并获取关于每个部件的信息。</span><span class="sxs-lookup"><span data-stu-id="eed43-194">In the following code sample, you can see how to open a .vsdx file, read the list of parts in the package, and get information about each part.</span></span>
  
### <a name="to-open-a-vsdx-file-and-view-the-document-parts"></a><span data-ttu-id="eed43-195">打开 .vsdx 文件并查看文档部件</span><span class="sxs-lookup"><span data-stu-id="eed43-195">To open a .vsdx file and view the document parts</span></span>

1. <span data-ttu-id="eed43-196">打开 Visio 2013 并创建一个新文档。</span><span class="sxs-lookup"><span data-stu-id="eed43-196">Open vis15short and create a new document.</span></span>
    
2. <span data-ttu-id="eed43-197">创建新文档并将其保存到桌面。</span><span class="sxs-lookup"><span data-stu-id="eed43-197">Create a new document and save it to the Desktop.</span></span>
    
3. <span data-ttu-id="eed43-198">打开 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="eed43-198">Open Visual Studio 2012.</span></span>
    
4. <span data-ttu-id="eed43-199">在“**文件**”菜单上，选择“**新建**”，然后选择“**项目**”。</span><span class="sxs-lookup"><span data-stu-id="eed43-199">On the **File** menu, point to **New**, and then choose Project.</span></span>
    
5. <span data-ttu-id="eed43-200">在“**Visual C#**”或“**Visual Basic**”下，展开“**Windows**”，然后选择“**控制台应用程序**”。</span><span class="sxs-lookup"><span data-stu-id="eed43-200">Under **Visual C#** or **Visual Basic**, expand **Windows**, and then select **Console Application**.</span></span>
    
6. <span data-ttu-id="eed43-201">在“**名称**”框中，键入“VisioFileExplorer”。</span><span class="sxs-lookup"><span data-stu-id="eed43-201">In the Name box, type SampleUdf.</span></span> <span data-ttu-id="eed43-202">控制台应用程序项目将打开。</span><span class="sxs-lookup"><span data-stu-id="eed43-202">In the Name box, type ‘VisioFileExplorer’. The Console Application project opens.</span></span> 
    
7. <span data-ttu-id="eed43-203">在“**解决方案资源管理器**”中，右键单击“**VisioFileExplorer**”，然后单击“**添加引用**”。</span><span class="sxs-lookup"><span data-stu-id="eed43-203">In the **Solution Explorer**, right-click **VisioFileExplorer**, and then click **Add Reference**.</span></span> 
    
8. <span data-ttu-id="eed43-204">在“**添加引用**”对话框中的“**程序集**”下，展开“**框架**”，然后选择“**WindowsBase**”。</span><span class="sxs-lookup"><span data-stu-id="eed43-204">In the **Add Reference** dialog box, under **Assemblies**, expand **Framework**, and then choose **WindowsBase**.</span></span>
    
9. <span data-ttu-id="eed43-205">将以下代码粘贴到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="eed43-205">Paste the following code into the solution.</span></span>
    
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

10. <span data-ttu-id="eed43-p126">按 F5 以调试解决方案。该程序完成运行后，按任意键退出。</span><span class="sxs-lookup"><span data-stu-id="eed43-p126">Press F5 to debug the solution. When the program has completed running, press any key to exit.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eed43-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eed43-208">See also</span></span>
<span data-ttu-id="eed43-209"><a name="vis15_IntroVSDX_Resources"> </a></span><span class="sxs-lookup"><span data-stu-id="eed43-209"></span></span>

<span data-ttu-id="eed43-210">有关 Visio 2013 文件格式、开放打包约定或如何以编程方式处理 Visio 2013 或 Office OpenXML 文件的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="eed43-210">For more information about the vis15short file format, the Open Packaging Convention, or how to work with vis15shortor Office OpenXML files programmatically, see the following resources:</span></span>
  
- [<span data-ttu-id="eed43-211">Visio 开发人员参考</span><span class="sxs-lookup"><span data-stu-id="eed43-211">New in Visio for developers</span></span>](https://msdn.microsoft.com/office/aa905478.aspx)
    
- [<span data-ttu-id="eed43-212">OPC：打包数据的新标准</span><span class="sxs-lookup"><span data-stu-id="eed43-212">OPC: A New Standard for Packaging Your Datahttp://msdn.microsoft.com/en-us/magazine/cc163372.aspx</span></span>](https://msdn.microsoft.com/magazine/cc163372.aspx)
    
- [<span data-ttu-id="eed43-213">开放打包约定的基础知识</span><span class="sxs-lookup"><span data-stu-id="eed43-213">Essentials of the Open Packaging Conventions</span></span>](https://msdn.microsoft.com/library/ee361919.aspx)
    
- [<span data-ttu-id="eed43-214">Office (2007) Open XML 文件格式简介</span><span class="sxs-lookup"><span data-stu-id="eed43-214">Introducing the Office (2007) Open XML File Formatshttp://msdn.microsoft.com/en-us/library/aa338205.aspx</span></span>](https://msdn.microsoft.com/library/aa338205.aspx)
    

