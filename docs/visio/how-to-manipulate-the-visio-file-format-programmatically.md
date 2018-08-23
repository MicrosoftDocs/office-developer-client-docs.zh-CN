---
title: 以编程方式处理 Visio 文件格式
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5f5e2288-7539-41b8-916d-410be028ed9b
description: ''
ms.openlocfilehash: ba3c03069235b1054dabd122471be996ec515772
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567844"
---
# <a name="manipulate-the-visio-file-format-programmatically"></a><span data-ttu-id="7f309-102">以编程方式处理 Visio 文件格式</span><span class="sxs-lookup"><span data-stu-id="7f309-102">Manipulate the Visio file format programmatically</span></span>

![操作方法主题](media/mod_icon_howto.png)
  
<span data-ttu-id="7f309-104">了解如何在 Visual Studio 2012，以读取 Visio 2013 中的新文件格式包、 包中选择部件、 更改部件中的数据和将新部件添加到包中创建解决方案。</span><span class="sxs-lookup"><span data-stu-id="7f309-104">Learn how to create a solution in Visual Studio 2012 to read the new file format package in Visio 2013, select parts in the package, change the data in a part, and add new parts to the package.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7f309-105">**本文中**         [Visio 文件格式操作 essentials](#vis15_ManipulateFF_Essentials)          [创建一个.vsdx 文件和新的 Visual Studio 解决方案](#vis15_ManipulateFF_CreateFile)          [打开一个 Visio 2013 文件作为包](#vis15_ManipulateFF_OpenPackage)          [选择和读取从包包部件](#vis15_ManipulateFF_SelectPart)          [选择并更改包部件中的 XML 数据](#vis15_ManipulateFF_ChangeXML)          [重新计算文件中的数据](#vis15_ManipulateFF_Recalculate)          [添加到包中新包部件](#vis15_ManipulateFF_AddNewPart)          [确认](#vis15_ManipulateFF_Ackn)          [其他资源](#vis15_ManipulateFF_Additional)</span><span class="sxs-lookup"><span data-stu-id="7f309-105">**In this article**         [Visio file format manipulation essentials](#vis15_ManipulateFF_Essentials)          [Create a .vsdx file and a new Visual Studio solution](#vis15_ManipulateFF_CreateFile)          [Open a Visio 2013 file as a package](#vis15_ManipulateFF_OpenPackage)          [Select and read package parts from a package](#vis15_ManipulateFF_SelectPart)          [Select and change XML data in a package part](#vis15_ManipulateFF_ChangeXML)          [Recalculate data in the file](#vis15_ManipulateFF_Recalculate)          [Add a new package part to a package](#vis15_ManipulateFF_AddNewPart)          [Acknowledgements](#vis15_ManipulateFF_Ackn)          [Additional resources](#vis15_ManipulateFF_Additional)</span></span>||
   
## <a name="visio-file-format-manipulation-essentials"></a><span data-ttu-id="7f309-106">Visio 文件格式操纵基础知识</span><span class="sxs-lookup"><span data-stu-id="7f309-106">Visio file format manipulation essentials</span></span>
<span data-ttu-id="7f309-107"><a name="vis15_ManipulateFF_Essentials"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-107"></span></span>

<span data-ttu-id="7f309-108">Visio 以前的版本专有的二进制文件格式 (.vsd) 或单文档 Visio XML 绘图文件格式 (.vdx) 保存文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-108">Previous versions of Visio saved files in a proprietary binary file format (.vsd) or a single-document Visio XML Drawing file format (.vdx).</span></span> <span data-ttu-id="7f309-109">Visio 2013 引入了新的文件格式 (.vsdx)，它基于 XML 和 ZIP 存档技术。</span><span class="sxs-lookup"><span data-stu-id="7f309-109">Visio 2013 introduces a new file format (.vsdx), which is based on XML and ZIP archive technologies.</span></span> <span data-ttu-id="7f309-110">只需与以前版本的 Visio，文件将保存在单个容器中。</span><span class="sxs-lookup"><span data-stu-id="7f309-110">Just as in previous versions of Visio, files are saved in a single container.</span></span> <span data-ttu-id="7f309-111">与不同旧式文件，但是，新文件格式可以是打开、 读取、 更新、 更改，和构造不自动执行 Visio 2013 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f309-111">Unlike legacy files, however, the new file format can be opened, read, updated, changed, and constructed without automating the Visio 2013 application.</span></span> <span data-ttu-id="7f309-112">熟悉操作 XML 或使用[System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx)命名空间的开发人员可以快速开始以编程方式使用新文件格式。</span><span class="sxs-lookup"><span data-stu-id="7f309-112">Developers who are familiar with manipulating XML or working with the [System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx) namespace can quickly get started working with the new file format programmatically.</span></span> <span data-ttu-id="7f309-113">开发人员使用从早期版本的 Visio XML 绘图格式过可以找到的许多从该格式的结构中保留的新文件格式。</span><span class="sxs-lookup"><span data-stu-id="7f309-113">Developers who have worked with the Visio XML Drawing format from previous versions can find that many of the structures from that format have been retained in the new file format.</span></span> 
  
<span data-ttu-id="7f309-114">本文中，我们将研究如何使用 Visio 2013 文件格式，以编程方式使用 Microsoft.NET Framework 4.5、 C# 或 Visual Basic 和 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="7f309-114">In this article, we examine how to work with the Visio 2013 file format programmatically, using the Microsoft .NET Framework 4.5, C# or Visual Basic, and Visual Studio 2012.</span></span> <span data-ttu-id="7f309-115">您可以了解如何以打开一个 Visio 2013 文件，选择文件内的文档部件，更改数据部件中的创建的新文档部件。</span><span class="sxs-lookup"><span data-stu-id="7f309-115">You can see how to open a Visio 2013 file, select document parts within the file, change data in parts, and create a new document part.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f309-116">本文中的代码示例假定您已在[System.Xml.Linq](https://msdn.microsoft.com/library/System.Xml.Linq.aspx)和[System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx)命名空间的类的基本了解。</span><span class="sxs-lookup"><span data-stu-id="7f309-116">The code samples in this article assume that you have a rudimentary understanding of the classes in the [System.Xml.Linq](https://msdn.microsoft.com/library/System.Xml.Linq.aspx) and [System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx) namespaces.</span></span> <span data-ttu-id="7f309-117">> 本文还假定您了解的概念和术语的开放打包约定。</span><span class="sxs-lookup"><span data-stu-id="7f309-117">> This article also assumes that you understand the concepts and terminology of the Open Packaging Conventions.</span></span> <span data-ttu-id="7f309-118">您应该熟悉包、 文档部件或包部件和关系的概念。</span><span class="sxs-lookup"><span data-stu-id="7f309-118">You should have some familiarity with the concepts of packages, document parts or package parts, and relationships.</span></span> <span data-ttu-id="7f309-119">有关详细信息，请参阅[OPC: 新标准打包您的数据](http://msdn.microsoft.com/en-us/magazine/cc163372.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7f309-119">For more information, see [OPC: A New Standard for Packaging Your Data](http://msdn.microsoft.com/en-us/magazine/cc163372.aspx).</span></span> <span data-ttu-id="7f309-120">> 的代码演示如何创建 LINQ （语言集成查询） 查询以选择 XML。</span><span class="sxs-lookup"><span data-stu-id="7f309-120">> The code demonstrates how to create LINQ (Language-Integrated Query) queries to select XML.</span></span> <span data-ttu-id="7f309-121">大多数的代码示例使用用于生成 LINQ 查询查询语法。</span><span class="sxs-lookup"><span data-stu-id="7f309-121">Most of the code samples use the query syntax for building LINQ queries.</span></span> <span data-ttu-id="7f309-122">您可以重新编写任何 LINQ 查询，如有必要，代码中使用 LINQ 方法语法，提供。</span><span class="sxs-lookup"><span data-stu-id="7f309-122">You can rewrite any of the LINQ queries provided in the code by using the LINQ method syntax, if necessary.</span></span> <span data-ttu-id="7f309-123">有关 LINQ 查询语法和方法的语法的详细信息，请参阅[LINQ 查询语法与方法语法 (C#)](http://msdn.microsoft.com/en-us/library/bb397947.aspx)> 表 1 显示了通过本文工作之前应熟悉的基本主题。</span><span class="sxs-lookup"><span data-stu-id="7f309-123">For more information about LINQ query syntax and method syntax, see [LINQ Query Syntax versus Method Syntax (C#)](http://msdn.microsoft.com/en-us/library/bb397947.aspx)> Table 1 shows the essential topics that you should be familiar with before you work through this article.</span></span> 
  
<span data-ttu-id="7f309-124">**表 1. 操纵 Visio 2013 文件格式的核心概念**</span><span class="sxs-lookup"><span data-stu-id="7f309-124">**Table 1. Core concepts for manipulating the Visio 2013 file format**</span></span>

|<span data-ttu-id="7f309-125">**文章标题**</span><span class="sxs-lookup"><span data-stu-id="7f309-125">**Article title**</span></span>|<span data-ttu-id="7f309-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="7f309-126">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7f309-127">Visio 文件格式 (.vsdx) 简介</span><span class="sxs-lookup"><span data-stu-id="7f309-127">Introduction to the Visio file format (.vsdx)</span></span>](introduction-to-the-visio-file-formatvsdx.md) <br/> |<span data-ttu-id="7f309-128">此高级 overview 介绍一些 Visio 2013 文件格式的主要功能。</span><span class="sxs-lookup"><span data-stu-id="7f309-128">This high-level overview describes some of the major features of the Visio 2013 file format.</span></span> <span data-ttu-id="7f309-129">它讨论开放打包约定 (OPC)，因为它们具有已应用到 Visio 2013 文件格式。</span><span class="sxs-lookup"><span data-stu-id="7f309-129">It discusses the Open Packaging Conventions (OPC) as they have been applied to the Visio 2013 file format.</span></span> <span data-ttu-id="7f309-130">它还列出了一些 Visio 2013 文件格式和以前的 Visio XML 绘图文件格式 (.vdx) 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="7f309-130">It also lists some differences between the Visio 2013 file format and the previous Visio XML Drawing file format (.vdx).</span></span>  <br/> |
|[<span data-ttu-id="7f309-131">OPC： 打包您的数据的新标准</span><span class="sxs-lookup"><span data-stu-id="7f309-131">OPC: A New Standard for Packaging Your Data</span></span>](http://msdn.microsoft.com/en-us/magazine/cc163372.aspx) <br/> |<span data-ttu-id="7f309-132">此 MSDN 杂志文章将开放打包约定作为概念进行介绍。</span><span class="sxs-lookup"><span data-stu-id="7f309-132">This MSDN Magazine article describes the Open Packaging Conventions as a concept.</span></span>  <br/> |
|[<span data-ttu-id="7f309-133">开放打包约定的基础知识</span><span class="sxs-lookup"><span data-stu-id="7f309-133">Essentials of the Open Packaging Conventions</span></span>](http://msdn.microsoft.com/en-us/library/ee361919.aspx) <br/> [<span data-ttu-id="7f309-134">介绍 Office (2007) Open XML 文件格式</span><span class="sxs-lookup"><span data-stu-id="7f309-134">Introducing the Office (2007) Open XML File Formats</span></span>](http://msdn.microsoft.com/en-us/library/aa338205.aspx) <br/> |<span data-ttu-id="7f309-135">以下两篇文章讨论如何开放打包约定已应用于 Microsoft Office 文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-135">These two articles discuss how the Open Packaging Conventions have been applied to Microsoft Office files.</span></span> <span data-ttu-id="7f309-136">它们包含如何关系包中的工作原理以及还包括一些代码示例的说明。</span><span class="sxs-lookup"><span data-stu-id="7f309-136">They contain descriptions of how relationships work in a package and also include some code examples.</span></span>  <br/> |
   
## <a name="create-a-vsdx-file-and-a-new-visual-studio-solution"></a><span data-ttu-id="7f309-137">创建 .vsdx 文件和新的 Visual Studio 解决方案</span><span class="sxs-lookup"><span data-stu-id="7f309-137">Create a .vsdx file and a new Visual Studio solution</span></span>
<span data-ttu-id="7f309-138"><a name="vis15_ManipulateFF_CreateFile"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-138"></span></span>

<span data-ttu-id="7f309-139">您可以开始工作完成本文中的过程之前，您需要创建的 Visio 2013 文件打开和操作。</span><span class="sxs-lookup"><span data-stu-id="7f309-139">Before you can begin working through the procedures in this article, you need to create a Visio 2013 file to open and manipulate.</span></span> <span data-ttu-id="7f309-140">本文中的代码示例中使用该绘图包含单个页面与它被"基本流程图"模板的"开始/结束"形状的形状之一的两个连接的形状。</span><span class="sxs-lookup"><span data-stu-id="7f309-140">The drawing used in the code examples in this article contains a single page with two connected shapes on it, one of the shapes being a "Start/End" shape from the "Basic Flowchart" template.</span></span>
  
<span data-ttu-id="7f309-141">使用以下过程创建新的 Visio 2013 文件在本文中的其余过程中使用。</span><span class="sxs-lookup"><span data-stu-id="7f309-141">Use the following procedure to create a new Visio 2013 file to use in the remaining procedures in this article.</span></span>
  
### <a name="to-create-new-file-in-visio-2013"></a><span data-ttu-id="7f309-142">在 Visio 2013 中创建新的文件</span><span class="sxs-lookup"><span data-stu-id="7f309-142">To create new file in Visio 2013</span></span>

1. <span data-ttu-id="7f309-143">打开 Visio 2013。</span><span class="sxs-lookup"><span data-stu-id="7f309-143">Open Visio 2013.</span></span>
    
2. <span data-ttu-id="7f309-144">创建基本流程图模板上基于通过选择**类别**、**流程图**、**基本流程图**、**创建**一个新文档。</span><span class="sxs-lookup"><span data-stu-id="7f309-144">Create a new document based on the Basic Flowchart template by choosing **CATEGORIES**, **Flowchart**, **Basic Flowchart**, **Create**.</span></span>
    
3. <span data-ttu-id="7f309-145">从**形状**窗口中，**开始/结束**形状拖到画布中。</span><span class="sxs-lookup"><span data-stu-id="7f309-145">From the **Shapes** window, drag a **Start/End** shape onto the canvas.</span></span> 
    
4. <span data-ttu-id="7f309-146">在画布上选择新的“开始/结束”形状，并键入“Begin Process”。</span><span class="sxs-lookup"><span data-stu-id="7f309-146">Select the new Start/End shape on the drawing canvas and type 'Begin Process'.</span></span>
    
5. <span data-ttu-id="7f309-147">从**形状**窗口中，**过程**形状拖到画布中。</span><span class="sxs-lookup"><span data-stu-id="7f309-147">From the **Shapes** window, drag a **Process** shape onto the canvas.</span></span> 
    
6. <span data-ttu-id="7f309-148">在画布上选择新的“流程”形状，并键入“Perform some task”。</span><span class="sxs-lookup"><span data-stu-id="7f309-148">Select the new Process shape on the drawing canvas and type 'Perform some task'.</span></span>
    
7. <span data-ttu-id="7f309-149">在开始/结束形状的快捷菜单，选择**向页面添加一个连接器**，然后画和连接器之间的开始/结束和进程形状画布上, 图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="7f309-149">On the shortcut menu for the Start/End shape, select **Add One Connector to the Page**, and then draw a connector between the Start/End and Process shapes on the canvas, as shown in Figure 1.</span></span>
    
    <span data-ttu-id="7f309-150">**图 1。简单的 Visio 2013 绘图**</span><span class="sxs-lookup"><span data-stu-id="7f309-150">**Figure 1. Simple Visio 2013 drawing**</span></span>
    
     ![与进程形状连接的头部/尾部形状](media/vis15_SimpleFlowchart.png)
  
8. <span data-ttu-id="7f309-152">选择**文件**、**另存为**、**计算机**、**桌面**保存到您的桌面为.vsdx 文件文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-152">Save the file to your Desktop as a .vsdx file by choosing **File**, **Save As**, **Computer**, **Desktop**.</span></span>
    
    <span data-ttu-id="7f309-153">在**另存为**对话框中，输入**文件名**框中的 Visio 程序包""，请选择**Visio 绘图 (\*.vsdx)** 中**保存类型**列表，然后再选择**保存**按钮。</span><span class="sxs-lookup"><span data-stu-id="7f309-153">In the **Save As** dialog box, enter Visio Package in the **File name** box"", select **Visio Drawing (\*.vsdx)** in the **Save as type** list, and then choose the **Save** button.</span></span> 
    
9. <span data-ttu-id="7f309-154">关闭该文件，然后关闭 Visio 2013。</span><span class="sxs-lookup"><span data-stu-id="7f309-154">Close the file and then close Visio 2013.</span></span>
    
> [!TIP]
> <span data-ttu-id="7f309-155">有时 Visio 打开一个文件成功，即使有问题的文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-155">Sometimes Visio opens a file successfully even if there are issues with the file.</span></span> <span data-ttu-id="7f309-156">若要确保 Visio 通知的文件中的任何问题，应测试解决方案的处理文件包级别的 Visio 文件时启用文件打开警告。</span><span class="sxs-lookup"><span data-stu-id="7f309-156">To ensure that Visio notifies you of any file issues, you should enable file open warnings when testing solutions that manipulate Visio files at the file package level.</span></span> <span data-ttu-id="7f309-157">> 到启用文件打开警告，在 Visio 2013 中，选择**文件**，**选项**，**高级**。</span><span class="sxs-lookup"><span data-stu-id="7f309-157">> To enable file open warnings, in Visio 2013, choose **File**, **Options**, **Advanced**.</span></span> <span data-ttu-id="7f309-158">在**保存/打开**，选择**显示文件打开警告**。</span><span class="sxs-lookup"><span data-stu-id="7f309-158">Under **Save/Open**, select **Show file open warnings**.</span></span> 
  
<span data-ttu-id="7f309-159">这些过程使用 Windows 控制台应用程序操作的"Visio Package.vsdx"文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-159">These procedures use a Windows console application to manipulate the "Visio Package.vsdx" file.</span></span> <span data-ttu-id="7f309-160">使用以下过程可创建和设置 Visual Studio 2012 中的新 Windows 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f309-160">Use the following procedure to create and set up a new Windows console application in Visual Studio 2012.</span></span>
  
### <a name="to-create-a-new-solution-in-visual-studio-2012"></a><span data-ttu-id="7f309-161">在 Visual Studio 2012 中创建新的解决方案</span><span class="sxs-lookup"><span data-stu-id="7f309-161">To create a new solution in Visual Studio 2012</span></span>

1. <span data-ttu-id="7f309-162">在**文件**菜单上选择**新建****项目**。</span><span class="sxs-lookup"><span data-stu-id="7f309-162">On the **File** menu, choose **New**, **Project**.</span></span>
    
2. <span data-ttu-id="7f309-163">在**新建项目**对话框中，展开**Visual C#** 或**Visual Basic**中，，然后选择**Windows**，**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7f309-163">In the **New Project** dialog box, expand either **Visual C#** or **Visual Basic**, and then choose **Windows**, **Console Application**.</span></span>
    
    <span data-ttu-id="7f309-164">在**名称**框中，输入 VisioFileAccessor，为该项目，选择一个位置，然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="7f309-164">In the **Name** box, enter ' VisioFileAccessor', select a location for the project, and then choose the **OK** button.</span></span> 
    
3. <span data-ttu-id="7f309-165">在"项目"菜单上，选择"添加引用"。</span><span class="sxs-lookup"><span data-stu-id="7f309-165">On the **Project** menu, choose **Add Reference**.</span></span> 
    
    <span data-ttu-id="7f309-166">**引用管理器**对话框的**程序集**，选择**框架**，然后再添加对**System.Xml**和**WindowsBase**组件的引用。</span><span class="sxs-lookup"><span data-stu-id="7f309-166">In the **Reference Manager** dialog box, under **Assemblies**, choose **Framework**, and then add a reference to the **System.Xml** and **WindowsBase** components.</span></span> 
    
4. <span data-ttu-id="7f309-167">在项目的 Program.cs 或 Module1.vb 文件中，添加以下 **using** 指令（Visual Basic 中的 **Imports** 语句）：</span><span class="sxs-lookup"><span data-stu-id="7f309-167">In the Program.cs or Module1.vb file for the project, add the following **using** directives (**Imports** statements in Visual Basic):</span></span> 
    
  ```cs
  using System.Xml;
  using System.Xml.Linq;
  using System.IO;
  using System.IO.Packaging;
  using System.Text;
  
  ```

  ```vb
  Imports System.Xml
  Imports System.Xml.Linq
  Imports System.IO
  Imports System.IO.Packaging
  Imports System.Text
  
  ```

5. <span data-ttu-id="7f309-168">此外，在 Program.cs 或 Module1.vb 文件中，在 **Program** 类（Visual Basic 中的 **Module1**）的 **Main** 方法结束之前，添加以下代码，停止执行控制台应用程序，直到用户按下某个键。</span><span class="sxs-lookup"><span data-stu-id="7f309-168">Also in the Program.cs or Module1.vb file, before the end of the **Main** method of the **Program** class (**Module1** in Visual Basic), add the following code that stops execution of the console application until the user presses a key.</span></span> 
    
  ```cs
  // This code stops the execution of the console application
  // so you can read the output.
  Console.WriteLine("Press any key to continue ...");
  Console.ReadKey();
  
  ```

  ```vb
  ' This code stops the execution of the console application
  ' so you can read the output.
  Console.WriteLine("Press any key to continue ...")
  Console.ReadKey()
  ```

## <a name="open-a-visio-2013-file-as-a-package"></a><span data-ttu-id="7f309-169">为包中打开 Visio 2013 文件</span><span class="sxs-lookup"><span data-stu-id="7f309-169">Open a Visio 2013 file as a package</span></span>
<span data-ttu-id="7f309-170"><a name="vis15_ManipulateFF_OpenPackage"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-170"></span></span>

<span data-ttu-id="7f309-171">您可以处理的任何文件内数据之前，您需要首先打开[包](https://msdn.microsoft.com/library/System.IO.Packaging.Package.aspx)对象中，在[System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx)命名空间内包含的文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-171">Before you can manipulate any of the data within the file, you need to first open the file within a [Package](https://msdn.microsoft.com/library/System.IO.Packaging.Package.aspx) object, which is contained within the [System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx) namespace.</span></span> <span data-ttu-id="7f309-172">**软件包**对象作为一个整体代表 Visio 文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-172">The **Package** object represents the Visio file as a whole.</span></span> <span data-ttu-id="7f309-173">它公开允许您选择的文件包中的单个文档部件的成员。</span><span class="sxs-lookup"><span data-stu-id="7f309-173">It exposes members that allow you to select individual document parts within the file package.</span></span> <span data-ttu-id="7f309-174">具体而言，**包**类公开的静态[Open （String，FileMode，文件访问）](https://msdn.microsoft.com/library/System.IO.Packaging.Package.Open.aspx)方法用来打开包文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-174">In particular, the **Package** class exposes the static [Open(String, FileMode, FileAccess)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.Open.aspx) method that you use to open a file as a package.</span></span> <span data-ttu-id="7f309-175">它还公开[close （）](https://msdn.microsoft.com/library/System.IO.Packaging.Package.Close.aspx)方法用于关闭包后已完成，但它。</span><span class="sxs-lookup"><span data-stu-id="7f309-175">It also exposes a [Close()](https://msdn.microsoft.com/library/System.IO.Packaging.Package.Close.aspx) method for closing the package once you've finished with it.</span></span> 
  
> [!TIP]
> <span data-ttu-id="7f309-176">最佳做法是，使用**使用**块**包**对象中打开 Visio 文件，以便您无需完成后与其显式关闭文件包。</span><span class="sxs-lookup"><span data-stu-id="7f309-176">As a best practice, use a **using** block to open the Visio file in the **Package** object so that you don't have to explicitly close the file package when you're done with it.</span></span> <span data-ttu-id="7f309-177">您可以在**try/catch/finally**构造**finally**块中还显式调用**Package.Close**方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-177">You can also explicitly call the **Package.Close** method in the **finally** block of a **try/catch/finally** construction.</span></span> 
  
<span data-ttu-id="7f309-178">使用下面的代码通过使用一个[FileInfo](https://msdn.microsoft.com/library/System.IO.FileInfo.aspx)对象获取"Visio Package.vsdx"文件的完整路径，将路径作为参数传递给**Package.Open**方法，然后调用代码返回**包**对象。</span><span class="sxs-lookup"><span data-stu-id="7f309-178">Use the following code to get the full path for the "Visio Package.vsdx" file by using a [FileInfo](https://msdn.microsoft.com/library/System.IO.FileInfo.aspx) object, pass the path as an argument to the **Package.Open** method, and then return a **Package** object to the calling code.</span></span> 
  
### <a name="to-open-a-vsdx-file-as-a-package"></a><span data-ttu-id="7f309-179">将 .vsdx 文件作为文件包打开</span><span class="sxs-lookup"><span data-stu-id="7f309-179">To open a .vsdx file as a package</span></span>

1. <span data-ttu-id="7f309-180">在 **Program** 类（或 Visual Basic 中的 **Module1**）中的 **Main** 方法后面，添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-180">After the **Main** method in the **Program** class (or **Module1** in Visual Basic), add the following code.</span></span> 
    
  ```cs
  private static Package OpenPackage(string fileName, 
      Environment.SpecialFolder folder)
  {
      Package visioPackage = null;
      // Get a reference to the location 
      // where the Visio file is stored.
      string directoryPath = System.Environment.GetFolderPath(
          folder);
      DirectoryInfo dirInfo = new DirectoryInfo(directoryPath);
      // Get the Visio file from the location.
      FileInfo[] fileInfos = dirInfo.GetFiles(fileName);
      if (fileInfos.Count() > 0)
      {
          FileInfo fileInfo = fileInfos[0];
          string filePathName = fileInfo.FullName;
          // Open the Visio file as a package with
          // read/write file access.
          visioPackage = Package.Open(
              filePathName,
              FileMode.Open,
              FileAccess.ReadWrite);
          }
          // Return the Visio file as a package.
          return visioPackage;
  }
  ```

  ```vb
  Private Function OpenPackage(fileName As String, _
      folder As Environment.SpecialFolder) As Package
      Dim visioPackage As Package = Nothing
      ' Get a reference to the location
      ' where the Visio file is stored.
      Dim directoryPath As String = System.Environment.GetFolderPath( _
          folder)
      Dim dirInfo As DirectoryInfo = New DirectoryInfo(directoryPath)
      ' Get the Visio file from the location.
      Dim fileInfos As FileInfo() = dirInfo.GetFiles(fileName)
      If (fileInfos.Count() > 0) Then
          Dim fileInfo As FileInfo = fileInfos(0)
          Dim filePathName As String = fileInfo.FullName
          ' Open the Visio file as a package 
          ' with read/write access.
          visioPackage = Package.Open( _
              filePathName,
              FileMode.Open,
              FileAccess.ReadWrite)
          End If
      ' Return the Visio file as a package.
      Return visioPackage
  End Function
  
  ```

2. <span data-ttu-id="7f309-181">在 **Program** 类（或 Visual Basic 中的 **Module1**）中的 **Main** 方法中，添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-181">In the **Main** method of the **Program** class (or **Module1** in Visual Basic), add the following code.</span></span> 
    
  ```cs
  // Open the Visio file in a Package object.
  using (Package visioPackage = OpenPackage("Visio Package.vsdx", 
      Environment.SpecialFolder.Desktop))
  {
  }
  
  ```

  ```vb
  ' Open the Visio file in a Package object.
  Using visioPackage As Package = OpenPackage("Visio Package.vsdx", _
      Environment.SpecialFolder.Desktop)
  End Using
  
  ```

## <a name="select-and-read-package-parts-from-a-package"></a><span data-ttu-id="7f309-182">从包中选择并读取包部件</span><span class="sxs-lookup"><span data-stu-id="7f309-182">Select and read package parts from a package</span></span>
<span data-ttu-id="7f309-183"><a name="vis15_ManipulateFF_SelectPart"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-183"></span></span>

<span data-ttu-id="7f309-184">为包打开该 Visio 2013 文件后，您可以访问内它使用[PackagePart](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePart.aspx)类**System.IO.Packaging**命名空间中包含的文档部件。</span><span class="sxs-lookup"><span data-stu-id="7f309-184">Once you have the Visio 2013 file open as a package, you can access the document parts within it using the [PackagePart](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePart.aspx) class included in the **System.IO.Packaging** namespace.</span></span> <span data-ttu-id="7f309-185">独立的或作为集合，可以实例化**PackagePart**对象。</span><span class="sxs-lookup"><span data-stu-id="7f309-185">**PackagePart** objects can be instantiated individually or as a collection.</span></span> <span data-ttu-id="7f309-186">**包**类公开的[GetParts()](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetParts.aspx)方法以及获取**PackagePart**对象超出**包**的[GetPart(Uri)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetPart.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-186">The **Package** class exposes a [GetParts()](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetParts.aspx) method and a [GetPart(Uri)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetPart.aspx) method for getting **PackagePart** objects out of the **Package**.</span></span> <span data-ttu-id="7f309-187">**Package.GetParts**方法返回的[PackagePartCollection](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePartCollection.aspx)类中，您可以然后交互像实现的其他任何集合实例[IEnumerator\<T\>](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ienumerator-1?redirectedfrom=MSDN&view=netframework-4.7.2)接口。</span><span class="sxs-lookup"><span data-stu-id="7f309-187">The **Package.GetParts** method returns an instance of the [PackagePartCollection](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePartCollection.aspx) class, which you can then interact with like any other collection that implements the [IEnumerator\<T\>](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ienumerator-1?redirectedfrom=MSDN&view=netframework-4.7.2) interface.</span></span> 
  
<span data-ttu-id="7f309-188">使用以下过程中的代码，作为一个整体从 **Package** 中获取 **PackagePartCollection** 对象，循环访问集合中的 **PackagePart** 对象，并将每个 **PackagePart** 的 URI 和内容类型写入到控制台中。</span><span class="sxs-lookup"><span data-stu-id="7f309-188">Use the code in the following procedure to get a **PackagePartCollection** object from the **Package** as a collection, iterate through the **PackagePart** objects in the collection, and write the URI and content type of each **PackagePart** to the console.</span></span> 
  
### <a name="to-iterate-through-the-package-parts-in-a-package"></a><span data-ttu-id="7f309-189">循环访问包中的包部件</span><span class="sxs-lookup"><span data-stu-id="7f309-189">To iterate through the package parts in a package</span></span>

1. <span data-ttu-id="7f309-190">后`OpenPackage`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-190">After the  `OpenPackage` method in the **Program** class (or **Module1** in Visual Basic), add the following code.</span></span> 
    
  ```cs
  private static void IteratePackageParts(Package filePackage)
  {
      
      // Get all of the package parts contained in the package
      // and then write the URI and content type of each one to the console.
      PackagePartCollection packageParts = filePackage.GetParts();
      foreach (PackagePart part in packageParts)
      {
          Console.WriteLine("Package part URI: {0}", part.Uri);
          Console.WriteLine("Content type: {0}", part.ContentType.ToString());
      }
  }
  
  ```

  ```vb
  Private Sub IteratePackageParts(filePackage As Package)
      ' Get all of the package parts contained in the package
      ' and then write the URI and content type of each one to the console.
      Dim packageParts As PackagePartCollection = filePackage.GetParts()
      For Each part In packageParts
          Console.WriteLine("Package part: {0}", part.Uri)
          Console.WriteLine("Content type: {0}", part.ContentType.ToString())
      Next
  End Sub 
  
  ```

2. <span data-ttu-id="7f309-191">在 **Program** 类的 **Main** 方法的 **using** 块（Visual Basic 中 **Module1** 中 **Main** 方法的 **Using** 块）内，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="7f309-191">Add the following code inside the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic):</span></span> 
    
  ```cs
  // Write the URI and content type of each package part to the console.
  IteratePackageParts(visioPackage);
  
  ```

  ```vb
  ' Write the URI and content type of each package part to the console.
  IteratePackageParts(visioPackage)
  
  ```

3. <span data-ttu-id="7f309-p112">选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。</span><span class="sxs-lookup"><span data-stu-id="7f309-p112">Choose the F5 key to debug the solution. When the program has completed running, choose any key to exit.</span></span>
    
<span data-ttu-id="7f309-194">控制台应用程序生成如下所示的输出（为了简单起见，某些输出已被省略）：</span><span class="sxs-lookup"><span data-stu-id="7f309-194">The console application produces output similar to the following (some of the output has been omitted for brevity):</span></span>
  
 `Package part URI: /docProps/app.xml`
  
 `Content type: application/vnd.openxmlformats-officedocument.extended-properties+xml`
  
 `Package part URI: /docProps/core.xml`
  
 `Content type: application/vnd.openxmlformats-officedocument.core-properties+xml`
  
 `Package part URI: /docProps/custom.xml`
  
 `Content type: application/vnd.openxmlformats-officedocument.custom-properties+xml`
  
 `Package part URI: /docProps/thumbnail.emv`
  
 `Content type: image/x-emf`
  
 `Package part URI: /visio/document.xml`
  
 `Content type: application/vnd.ms-visio.drawing.main+xml`
  
 `Package part URI: /visio/_rels/document.xml.rels`
  
 `Content type: application/vnd.openxmlformats-package.relationships+xml`
  
 `Package part URI: /_rels/.rels`
  
 `Content type: application/vnd.openxmlformats-package.relationships+xml`
  
 `Press any key to continue …`
  
<span data-ttu-id="7f309-195">个通常不多，您需要选择一个**PackagePart** ，而不必循环访问所有这些。</span><span class="sxs-lookup"><span data-stu-id="7f309-195">More often than not, you need to select one **PackagePart** without having to iterate over all of them.</span></span> <span data-ttu-id="7f309-196">您可以使用它与**包**或另一个**PackagePart**关系从**包**中获取**PackagePart**对象。</span><span class="sxs-lookup"><span data-stu-id="7f309-196">You can get a **PackagePart** object from a **Package** by using its relationship to the **Package** or another **PackagePart**.</span></span> <span data-ttu-id="7f309-197">与每个其他相关的文件格式是单独的实体的介绍的文档部件如何与 Visio 2013 中的关系文件包或如何两个文档部件。</span><span class="sxs-lookup"><span data-stu-id="7f309-197">A relationship in the Visio 2013 file format is a discrete entity that describes how a document part relates to the file package or how two document parts relate to each other.</span></span> <span data-ttu-id="7f309-198">例如，Visio 2013 文件包本身已与它的 Visio 文档部件的关系和 Visio 文档部件具有与 Windows 部件的关系。</span><span class="sxs-lookup"><span data-stu-id="7f309-198">For example, the Visio 2013 file package itself has a relationship to its Visio Document part, and the Visio Document part has a relationship to the Windows part.</span></span> <span data-ttu-id="7f309-199">这些关系表示为[PackageRelationship](https://msdn.microsoft.com/library/System.IO.Packaging.PackageRelationship.aspx)或[PackageRelationshipCollection](https://msdn.microsoft.com/library/System.IO.Packaging.PackageRelationshipCollection.aspx)类的实例。</span><span class="sxs-lookup"><span data-stu-id="7f309-199">These relationships are represented as instances of the [PackageRelationship](https://msdn.microsoft.com/library/System.IO.Packaging.PackageRelationship.aspx) or [PackageRelationshipCollection](https://msdn.microsoft.com/library/System.IO.Packaging.PackageRelationshipCollection.aspx) classes.</span></span> 
  
<span data-ttu-id="7f309-200">**包**类公开几种方法来获取它包含作为**PackageRelationship**或**PackageRelationshipCollection**对象的关系。</span><span class="sxs-lookup"><span data-stu-id="7f309-200">The **Package** class exposes several methods for getting the relationships that it contains as **PackageRelationship** or **PackageRelationshipCollection** objects.</span></span> <span data-ttu-id="7f309-201">[GetRelationshipsByType(String)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetRelationshipsByType.aspx)方法可用于实例化**PackageRelationshipCollection**对象，其中包含单个特定类型的**PackageRelationship**对象。</span><span class="sxs-lookup"><span data-stu-id="7f309-201">You can use the [GetRelationshipsByType(String)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetRelationshipsByType.aspx) method to instantiate a **PackageRelationshipCollection** object that contains **PackageRelationship** objects of a single specific type.</span></span> <span data-ttu-id="7f309-202">当然，使用**Package.GetRelationshipsByType**方法要求您知道您需要的关系类型。</span><span class="sxs-lookup"><span data-stu-id="7f309-202">Of course, using the **Package.GetRelationshipsByType** method requires that you already know the relationship type that you need.</span></span> <span data-ttu-id="7f309-203">关系类型是 XML 命名空间格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="7f309-203">Relationship types are strings in XML namespace format.</span></span> <span data-ttu-id="7f309-204">例如，Visio 文档部件的关系类型是http://schemas.microsoft.com/visio/2010/relationships/document。</span><span class="sxs-lookup"><span data-stu-id="7f309-204">For example, the relationship type of the Visio Document part is http://schemas.microsoft.com/visio/2010/relationships/document.</span></span> 
  
<span data-ttu-id="7f309-p115">一旦您知道 **PackagePart** 与 **Package** 或与另一个 **PackagePart** 的关系（即，您有一个 **PackageRelationship** 对象引用所需的 **PackagePart**），即可使用此关系获取该 **PackagePart** 的 URI。然后您可以将 URI 传递到 **Package.GetPart** 方法以返回 **PackagePart**。</span><span class="sxs-lookup"><span data-stu-id="7f309-p115">Once you know the relationship of a **PackagePart** to the **Package** or to another **PackagePart** (that is, you have a **PackageRelationship** object that references the **PackagePart** that you want), you can use that relationship to get the URI of that **PackagePart**. You then pass the URI to the **Package.GetPart** method to return the **PackagePart**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f309-207">您还可以对特定**PackagePart**使用刚**Package.GetPart**方法和**PackagePart**，URI 绕过其中您获取包部件的关系的步骤。</span><span class="sxs-lookup"><span data-stu-id="7f309-207">You can also get a reference to a specific **PackagePart** by using just the **Package.GetPart** method and the URI of the **PackagePart**, bypassing the step where you get the package part's relationships.</span></span> <span data-ttu-id="7f309-208">但是，某些包部件中的 Visio 文件包可以保存到包中其默认位置以外的位置。</span><span class="sxs-lookup"><span data-stu-id="7f309-208">However, some package parts in the Visio file package can be saved to locations other than their default locations in a package.</span></span> <span data-ttu-id="7f309-209">不能假定包部件始终位于同一个 URI 的每个文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-209">You cannot assume that a package part is always located at the same URI for every file.</span></span> <span data-ttu-id="7f309-210">> 相反，它是最佳做法是使用关系来访问各个**PackagePart**对象。</span><span class="sxs-lookup"><span data-stu-id="7f309-210">> Instead, it is a best practice to use relationships to access individual **PackagePart** objects.</span></span> 
  
<span data-ttu-id="7f309-211">使用以下过程获取 **PackagePart**（Visio 文档部件），方法是使用引用该部件的 **Package** 中的 **PackageRelationship** 。</span><span class="sxs-lookup"><span data-stu-id="7f309-211">Use the following procedure to get a **PackagePart** (the Visio Document part) by using the **PackageRelationship** from the **Package** that references the part.</span></span> 
  
### <a name="to-select-a-specific-package-part-in-the-package-by-relationship"></a><span data-ttu-id="7f309-212">按关系选择包中的特定包部件</span><span class="sxs-lookup"><span data-stu-id="7f309-212">To select a specific package part in the package by relationship</span></span>

1. <span data-ttu-id="7f309-213">后`IteratePackageParts`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-213">After the  `IteratePackageParts` method in the **Program** class (or **Module1** in Visual Basic), add the following method.</span></span> 
    
  ```cs
  private static PackagePart GetPackagePart(Package filePackage, 
      string relationship)
  {
      
      // Use the namespace that describes the relationship 
      // to get the relationship.
      PackageRelationship packageRel = 
          filePackage.GetRelationshipsByType(relationship).FirstOrDefault();
      PackagePart part = null;
      // If the Visio file package contains this type of relationship with 
      // one of its parts, return that part.
      if (packageRel != null)
      {
          // Clean up the URI using a helper class and then get the part.
          Uri docUri = PackUriHelper.ResolvePartUri(
              new Uri("/", UriKind.Relative), packageRel.TargetUri);
          part = filePackage.GetPart(docUri);
      }
      return part;
  }
  
  ```

  ```vb
  Private Function GetPackagePart(filePackage As Package, relationship As String) _
      As PackagePart
      ' Use the namespace that describes the relationship 
      ' to get the relationship.
      Dim packageRel As PackageRelationship = 
          filePackage.GetRelationshipsByType(relationship).FirstOrDefault()
      Dim part As PackagePart = Nothing
      ' If the Visio file package contains this type of relationship with 
      ' one of its parts, return that part.
      If Not IsNothing(packageRel) Then
          ' Clean up the URI using a helper class and then get the part.
          Dim docUri = PackUriHelper.ResolvePartUri( _
              New Uri("/", UriKind.Relative), packageRel.TargetUri)
          part = filePackage.GetPart(docUri)
      End If
      Return part
  End Function
  
  ```

2. <span data-ttu-id="7f309-214">将 **Program** 类的 **Main** 方法的 **using** 块（Visual Basic 中 **Module1** 中 **Main** 方法的 **Using** 块）替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-214">Replace the code in the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic) with the following code.</span></span> 
    
  ```cs
  // Get a reference to the Visio Document part contained in the file package.
  PackagePart documentPart = GetPackagePart(visioPackage, 
      "http://schemas.microsoft.com/visio/2010/relationships/document");
  
  ```

  ```vb
  ' Get a reference to the Visio Document part contained in the file package.
  Dim documentPart As PackagePart = GetPackagePart(visioPackage, _
      "http://schemas.microsoft.com/visio/2010/relationships/document")
  
  ```

<span data-ttu-id="7f309-215">如前所述，还可以使用其关系的其他**PackagePart**对象获取**PackagePart**对象。</span><span class="sxs-lookup"><span data-stu-id="7f309-215">As mentioned previously, you can also get **PackagePart** objects by using their relationship to other **PackagePart** objects.</span></span> <span data-ttu-id="7f309-216">这很重要，因为 Visio 文档的任何复杂性，大多数**PackagePart**对象没有与**包**的关系。</span><span class="sxs-lookup"><span data-stu-id="7f309-216">This is important because, for a Visio document of any complexity, most of the **PackagePart** objects don't have a relationship to the **Package**.</span></span> <span data-ttu-id="7f309-217">例如，文件包 (即，/visio/pages/page1.xml) 中的单个页面内容部件具有对页索引部分 (即，/visio/pages/pages.xml)，但不适用于文件包自身的关系。</span><span class="sxs-lookup"><span data-stu-id="7f309-217">For example, an individual Page Content part in the file package (that is, /visio/pages/page1.xml) has a relationship to the Page Index part (that is, /visio/pages/pages.xml) but not to the file package itself.</span></span> <span data-ttu-id="7f309-218">如果您没有单独的页的同一 URI 程序包中，您可以使用它与页索引部件的关系以获取对它的引用。</span><span class="sxs-lookup"><span data-stu-id="7f309-218">If you don't have the exact URI of the individual page in the package, you can use its relationship to the Page Index part to get a reference to it.</span></span>
  
<span data-ttu-id="7f309-219">**PackagePart**类公开的[GetRelationshipsByType(String)](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePart.GetRelationshipsByType.aspx)方法可用于返回一个包含**PackageRelationship**对象的一种类型的**PackageRelationshipCollection**对象。</span><span class="sxs-lookup"><span data-stu-id="7f309-219">The **PackagePart** class exposes a [GetRelationshipsByType(String)](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePart.GetRelationshipsByType.aspx) method that you can use to return a **PackageRelationshipCollection** object that contains only one type of **PackageRelationship** object.</span></span> <span data-ttu-id="7f309-220">**PackageRelationshipCollection**后，您可以选择**PackageRelationship** ，您需要从集合，然后参考**PackagePart**对象。</span><span class="sxs-lookup"><span data-stu-id="7f309-220">Once you have the **PackageRelationshipCollection**, you can select the **PackageRelationship** that you need from the collection and then reference the **PackagePart** object.</span></span> 
  
<span data-ttu-id="7f309-221">使用以下代码从 **Package** 获取 **PackagePart**，方法是使用与另一个 **PackagePart** 的关系（获取 **PackageRelationship** 对象）。</span><span class="sxs-lookup"><span data-stu-id="7f309-221">Use the following code to get a **PackagePart** from the **Package** by using its relationship to (getting a **PackageRelationship** object from) another **PackagePart**.</span></span>
  
### <a name="to-select-a-specific-package-part-through-its-relationship-to-another-package-part"></a><span data-ttu-id="7f309-222">通过与另一个包部件的关系选择特定的包部件</span><span class="sxs-lookup"><span data-stu-id="7f309-222">To select a specific package part through its relationship to another package part</span></span>

1. <span data-ttu-id="7f309-223">后`GetPackagePart`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下重载方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-223">After the  `GetPackagePart` method in the **Program** class (or **Module1** in Visual Basic), add the following overload method.</span></span> 
    
  ```cs
  private static PackagePart GetPackagePart(Package filePackage, 
      PackagePart sourcePart, string relationship)
  {
      // This gets only the first PackagePart that shares the relationship
      // with the PackagePart passed in as an argument. You can modify the code
      // here to return a different PackageRelationship from the collection.
      PackageRelationship packageRel = 
          sourcePart.GetRelationshipsByType(relationship).FirstOrDefault();
      PackagePart relatedPart = null;
      if (packageRel != null)
      {
          // Use the PackUriHelper class to determine the URI of PackagePart
          // that has the specified relationship to the PackagePart passed in
          // as an argument.
          Uri partUri = PackUriHelper.ResolvePartUri(
              sourcePart.Uri, packageRel.TargetUri);
          relatedPart = filePackage.GetPart(partUri);
      }
      return relatedPart;
  }
  
  ```

  ```vb
  Private Function GetPackagePart(filePackage As Package, 
      sourcePart As PackagePart, relationship As String) As PackagePart
      ' This gets only the first PackagePart that shares the relationship
      ' with the PackagePart passed in as an argument. You can modify the
      ' code to return a different PackageRelationship from the collection.
      Dim packageRel As PackageRelationship = sourcePart. _
          GetRelationshipsByType(relationship).FirstOrDefault()
      Dim relatedPart As PackagePart = Nothing
      If Not IsNothing(packageRel) Then
          ' Use the PackUriHelper class to determine the URI of the 
          ' PackagePart that has the specified relationship to the 
          ' PackagePart passed in as an argument.
          Dim partUri As Uri = PackUriHelper.ResolvePartUri( _
              sourcePart.Uri, packageRel.TargetUri)
          relatedPart = filePackage.GetPart(partUri)
      End If
      Return relatedPart
  End Function
  ```

2. <span data-ttu-id="7f309-p119">在前一过程的代码下方，在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码。（请勿删除您在前一过程中添加的代码。）</span><span class="sxs-lookup"><span data-stu-id="7f309-p119">Add the following code to the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic), beneath the code from the previous procedure. (Do not delete the code that you added in the previous procedure.)</span></span> 
    
  ```cs
  // Get a reference to the collection of pages in the document, 
  // and then to the first page in the document.
  PackagePart pagesPart = GetPackagePart(visioPackage, documentPart, 
      "http://schemas.microsoft.com/visio/2010/relationships/pages");
  PackagePart pagePart = GetPackagePart(visioPackage, pagesPart, 
      "http://schemas.microsoft.com/visio/2010/relationships/page");
  
  ```

  ```vb
  ' Get a reference to the collection of pages in the document,
  ' and then to the first page in the document.
  Dim pagesPart As PackagePart = GetPackagePart(visioPackage, documentPart, _
      "http://schemas.microsoft.com/visio/2010/relationships/pages") 
  Dim pagePart As PackagePart = GetPackagePart(visioPackage, pagesPart, _
      "http://schemas.microsoft.com/visio/2010/relationships/page") 
  ```

<span data-ttu-id="7f309-226">您可以对文档部件中包含的 XML 进行更改之前，您需要先将 XML 文档加载到一个对象，允许您读取的 XML 中，使用[XDocument](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.aspx)类或[XmlDocument](https://msdn.microsoft.com/library/System.Xml.XmlDocument.aspx)类。</span><span class="sxs-lookup"><span data-stu-id="7f309-226">Before you can make changes to the XML included in a document part, you need to first load the XML document into an object that allows you to read the XML, using the [XDocument](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.aspx) class or [XmlDocument](https://msdn.microsoft.com/library/System.Xml.XmlDocument.aspx) class.</span></span> <span data-ttu-id="7f309-227">这两个类公开任务选择 XML 元素包含在 XML 文档中; 例如的方法创建、 读取和写入属性;并向文档中插入新的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="7f309-227">Both classes expose methods for tasks such as selecting XML elements contained within the XML documents; creating, reading, and writing attributes; and inserting new XML elements into a document.</span></span> 
  
<span data-ttu-id="7f309-p121">在这两个类中，**XDocument** 类允许您使用 LINQ 查询 XML。使用 LINQ，您可以轻松地从 XML 文档中选择单个元素，方法是通过创建查询，而不是通过循环访问集合中的所有元素并测试您所需的元素。因此，本文中的后续过程将使用 **XDocument** 类以及 **System.Xml.Linq** 命名空间的其他类来处理 XML。</span><span class="sxs-lookup"><span data-stu-id="7f309-p121">Of the two, the **XDocument** class allows you to query the XML using LINQ. With LINQ, you can easily select individual elements from an XML document by creating queries, rather than iterating over all of the elements in a collection and testing for the elements that you need. For these reasons, the following procedures in this article use the **XDocument** class and other classes of the **System.Xml.Linq** namespace for working with XML.</span></span> 
  
<span data-ttu-id="7f309-231">使用以下过程，在 **XDocument** 对象中打开 **PackagePart** 作为 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="7f309-231">Use the following procedure to open a **PackagePart** as an XML document in an **XDocument** object.</span></span> 
  
### <a name="to-read-the-xml-in-a-package-part"></a><span data-ttu-id="7f309-232">读取包部件中的 XML</span><span class="sxs-lookup"><span data-stu-id="7f309-232">To read the XML in a package part</span></span>

1. <span data-ttu-id="7f309-233">后的最后一个重载，以`GetPackagePart`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-233">After the last overload for the  `GetPackagePart` method in the **Program** class (or **Module1** in Visual Basic), add the following method.</span></span> 
    
  ```cs
  private static XDocument GetXMLFromPart(PackagePart packagePart)
  {
      XDocument partXml = null;
      // Open the packagePart as a stream and then 
      // open the stream in an XDocument object.
      Stream partStream = packagePart.GetStream();
      partXml = XDocument.Load(partStream);
      return partXml;
  }
  ```

  ```vb
  Private Function GetXMLFromPart(packagePart As PackagePart) As XDocument
      Dim partXml As XDocument = Nothing
      ' Open the packagePart as a stream and then
      ' open the stream in an an XDocument object.
      Dim partStream As Stream = packagePart.GetStream()
      partXml = XDocument.Load(partStream)
      Return partXml
  End Function
  ```

2. <span data-ttu-id="7f309-234">在前一过程的代码下方，在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-234">Add the following code to the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic), beneath the code from the previous procedure.</span></span> 
    
  ```cs
  // Open the XML from the Page Contents part.
  XDocument pageXML = GetXMLFromPart(pagePart);
  ```

  ```vb
  ' Open the XML from the Page Contents part.
  Dim pageXML As XDocument = GetXMLFromPart(pagePart)
  ```

## <a name="select-and-change-xml-data-in-a-package-part"></a><span data-ttu-id="7f309-235">选择并更改包部件中的 XML 数据</span><span class="sxs-lookup"><span data-stu-id="7f309-235">Select and change XML data in a package part</span></span>
<span data-ttu-id="7f309-236"><a name="vis15_ManipulateFF_ChangeXML"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-236"></span></span>

<span data-ttu-id="7f309-p122">将文档部件加载到 **XDocument** 对象之后，您可以使用 LINQ 选择 XML 元素并对 XML 文档进行更改。您可以更改 XML 数据、添加或删除数据，然后将 XML 文档保存回文档部件。</span><span class="sxs-lookup"><span data-stu-id="7f309-p122">Once you have loaded a document part into an **XDocument** object, you can use LINQ to select XML elements and make changes to the XML document. You can change XML data, add or remove data, and then save the XML document back to the document part.</span></span> 
  
<span data-ttu-id="7f309-239">操作的 Visio 文件格式的最常见的任务文档中选择特定的 XML 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="7f309-239">The most common task for manipulating the Visio file format is selecting specific XML elements or collections of elements in the document.</span></span> <span data-ttu-id="7f309-240">**System.Xml.Linq**命名空间包括[XElement](https://msdn.microsoft.com/library/System.Xml.Linq.XElement.aspx)类，该类表示一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="7f309-240">The **System.Xml.Linq** namespace includes the [XElement](https://msdn.microsoft.com/library/System.Xml.Linq.XElement.aspx) class, which represents an XML element.</span></span> <span data-ttu-id="7f309-241">**XElement**类使您可以访问 Visio 文件在精细级别，从**ValidationRule**元素 （作为示例） 的单个**形状**元素中包含的数据。</span><span class="sxs-lookup"><span data-stu-id="7f309-241">The **XElement** class gives you access to the data contained in the Visio file at a granular level, from individual **Shape** elements to **ValidationRule** elements (as examples).</span></span> 
  
<span data-ttu-id="7f309-242">使用以下代码从 **XDocument**（包含页面内容部件）中选择 **Shape** 元素，然后选择特定的 **Shape** 元素。</span><span class="sxs-lookup"><span data-stu-id="7f309-242">Use the following code to select the **Shape** elements from an **XDocument** (containing a Page Contents part) and to then select a specific **Shape** element.</span></span> 
  
### <a name="to-select-a-specific-element-in-a-package-part"></a><span data-ttu-id="7f309-243">选择包部件中的特定元素</span><span class="sxs-lookup"><span data-stu-id="7f309-243">To select a specific element in a package part</span></span>

1. <span data-ttu-id="7f309-244">后`GetXMLFromPart`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-244">After the  `GetXMLFromPart` method in the **Program** class (or **Module1** in Visual Basic), add the following method.</span></span> 
    
  ```cs
  private static IEnumerable<XElement> GetXElementsByName(
      XDocument packagePart, string elementType)
  {
      // Construct a LINQ query that selects elements by their element type.
      IEnumerable<XElement> elements = 
          from element in packagePart.Descendants() 
          where element.Name.LocalName == elementType 
          select element;
      // Return the selected elements to the calling code.
      return elements.DefaultIfEmpty(null);
  }
  
  ```

  ```vb
  Private Function GetXElementsByName(partXML As XDocument, _
      elementType As String) As IEnumerable(Of XElement)
      ' Construct a LINQ query that selects elements by their element type.
      Dim elements As IEnumerable(Of XElement) =
          From element In partXML.Descendants()
          Where element.Name.LocalName = elementType
          Select element
      ' If there aren't any elements of the specified type
      ' in the document, return Nothing to the calling code.
      Return elements.DefaultIfEmpty(Nothing)
  End Function
  ```

2. <span data-ttu-id="7f309-245">后`GetXElementsByName` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-245">After the  `GetXElementsByName` method in the **Program** class (or **Module1** in Visual Basic) from the previous step, add the following method.</span></span> 
    
  ```cs
  private static XElement GetXElementByAttribute(IEnumerable<XElement> elements,
      string attributeName, string attributeValue) 
  {
      // Construct a LINQ query that selects elements from a group
      // of elements by the value of a specific attribute.
      IEnumerable<XElement> selectedElements = 
          from el in elements
          where el.Attribute(attributeName).Value == attributeValue
          select el;
      // If there aren't any elements of the specified type
      // with the specified attribute value in the document,
      // return null to the calling code.
      return selectedElements.DefaultIfEmpty(null).FirstOrDefault();
  }
  ```

  ```vb
  Private Function GetXElementByAttribute(elements As IEnumerable(Of XElement), _
      attributeName As String, attributeValue As String) As XElement
      ' Construct a LINQ query that selects elements from a group
      ' of elements by the value of a specific attribute.
      Dim selectedElements As IEnumerable(Of XElement) =
          From el In elements
          Where el.Attribute(attributeName).Value = attributeValue
          Select el
      ' If there aren't any elements of the specified type 
      ' with the specified attribute value in the document,
      ' return Nothing to the calling code.
      Return selectedElements.DefaultIfEmpty(Nothing).FirstOrDefault()
  End Function
  
  ```

3. <span data-ttu-id="7f309-246">在前一过程的代码下方，在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-246">Add the following code to the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic), beneath the code from the previous procedure.</span></span> 
    
  ```cs
  // Get all of the shapes from the page by getting
  // all of the Shape elements from the pageXML document.
  IEnumerable<XElement> shapesXML = GetXElementsByName(pageXML, "Shape");
  // Select a Shape element from the shapes on the page by 
  // its name. You can modify this code to select elements
  // by other attributes and their values.
  XElement startEndShapeXML = 
      GetXElementByAttribute(shapesXML, "NameU", "Start/End");
  
  ```

  ```vb
  ' Get all of the shapes from the page by getting
  ' all of the Shape elements from the pageXML document.
  Dim shapesXML As IEnumerable(Of XElement) = GetXElementsByName( _
      pageXML, "Shape")
  ' Select a Shape element from the shapes on the page by
  ' its name. You can modify this code to select elements
  ' by other attributes and their values.
  Dim startEndShapeXML As XElement = GetXElementByAttribute( _
      shapesXML, "NameU", "Start/End")
  ```

<span data-ttu-id="7f309-247">一旦有什么对**XDocument**对象中包含一个**XElement**对象的引用，可以处理类似的任何其他 XML 数据和，从而，更改 Visio 文件中包含的数据。</span><span class="sxs-lookup"><span data-stu-id="7f309-247">Once you have gotten a reference to a **XElement** object contained within an **XDocument** object, you can manipulate it like any other XML data and, thereby, change the data contained in the Visio file.</span></span> <span data-ttu-id="7f309-248">例如，如果形状有文本，在 Visio 中打开时，则相应的**形状**元素将包含至少一个**文本**元素。</span><span class="sxs-lookup"><span data-stu-id="7f309-248">For example, if a shape has text when it is opened in Visio, the corresponding **Shape** element will contain at least one **Text** element.</span></span> <span data-ttu-id="7f309-249">如果您更改该**文本**元素的值，Visio 中查看该文件时，将更改形状的文本。</span><span class="sxs-lookup"><span data-stu-id="7f309-249">If you change the value of that **Text** element, the shape's text is changed when the file is viewed in Visio.</span></span> 
  
<span data-ttu-id="7f309-250">在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码，将“开始/结束”形状中的文本从“Begin process”更改为“Start process”。</span><span class="sxs-lookup"><span data-stu-id="7f309-250">Add the following code to the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic) to change the text in the Start/End shape from "Begin process" to "Start process".</span></span> 
  
```cs
// Query the XML for the shape to get the Text element, and
// return the first Text element node.
IEnumerable<XElement> textElements = from element in startEndShapeXML.Elements()
                               where element.Name.LocalName = "Text"
                               select element;
XElement textElement = textElements.ElementAt(0);
// Change the shape text, leaving the <cp> element alone.
textElement.LastNode.ReplaceWith("Start process");

```

```vb
' Query the XML for the shape to get the Text element, and
' return the first Text element node.
Dim textElements As IEnumerable(Of XElement) =
    From element In startEndShapeXML.Elements()
    Where element.Name.LocalName = "Text"
    Select element
Dim textElement As XElement = textElements.ElementAt(0)
' Change the shape text, leaving the <cp> element alone.
textElement.LastNode.ReplaceWith("Start process")

```

> [!CAUTION]
> <span data-ttu-id="7f309-251">在以前的代码示例中，现有的形状文本和字符串，用于替换其具有相同数量的字符。</span><span class="sxs-lookup"><span data-stu-id="7f309-251">In the previous code example, the existing shape text and the string used to replace it have the same number of characters.</span></span> <span data-ttu-id="7f309-252">另请注意，LINQ 查询更改 （即，在这种情况下，文本节点） 返回的元素的最后一个子节点的值。</span><span class="sxs-lookup"><span data-stu-id="7f309-252">Also note that the LINQ query changes the value of the last child node of the returned element (which, in this case, is a text node).</span></span> <span data-ttu-id="7f309-253">这样做是为了避免更改**cp**元素的**文本**元素的子元素的设置。</span><span class="sxs-lookup"><span data-stu-id="7f309-253">This is done to avoid changing the settings of the **cp** element that is a child of the **Text** element.</span></span> <span data-ttu-id="7f309-254">> 很可能导致形状文本采用编程方式更改通过覆盖**文本**元素的所有子级文件系统不稳定。</span><span class="sxs-lookup"><span data-stu-id="7f309-254">> It is possible to cause file instability if you alter shape text programmatically by overwriting all children of the **Text** element.</span></span> <span data-ttu-id="7f309-255">如上面的示例所示的文本格式由文件中的**文本**元素下面**cp**元素表示。</span><span class="sxs-lookup"><span data-stu-id="7f309-255">As in the example above, the text formatting is represented by **cp** elements under the **Text** element in the file.</span></span> <span data-ttu-id="7f309-256">父**部分**元素中存储的格式的定义。</span><span class="sxs-lookup"><span data-stu-id="7f309-256">The definition of the formatting is stored in the parent **Section** element.</span></span> <span data-ttu-id="7f309-257">如果这些两条信息变得不一致，该文件不可能会像预期。</span><span class="sxs-lookup"><span data-stu-id="7f309-257">If these two pieces of information become inconsistent, then the file may not behave as expected.</span></span> <span data-ttu-id="7f309-258">Visio 愈合许多不一致，但最好以确保，以便您控制该文件的最终行为编程的任何更改都是一致。</span><span class="sxs-lookup"><span data-stu-id="7f309-258">Visio heals many inconsistencies, but it is better to ensure that any programmatic changes are consistent so that you are controlling the ultimate behavior of the file.</span></span> 
  
<span data-ttu-id="7f309-p126">当您对文档部件的 XML 进行更改时，这些更改仅存在于内存中。要将更改保留在文件中，您必须将 XML 保存回文档部件。</span><span class="sxs-lookup"><span data-stu-id="7f309-p126">When you make changes to the XML of a document part, those changes exist in memory only. To persist the changes in the file, you must save the XML back to the document part.</span></span>
  
<span data-ttu-id="7f309-261">下面的代码使用[XmlWriter](https://msdn.microsoft.com/library/System.Xml.XmlWriter.aspx)类和[XmlWriterSettings](https://msdn.microsoft.com/library/System.Xml.XmlWriterSettings.aspx)类写回包部件的 XML。</span><span class="sxs-lookup"><span data-stu-id="7f309-261">The following code uses the [XmlWriter](https://msdn.microsoft.com/library/System.Xml.XmlWriter.aspx) class and [XmlWriterSettings](https://msdn.microsoft.com/library/System.Xml.XmlWriterSettings.aspx) class to write the XML back to the package part.</span></span> <span data-ttu-id="7f309-262">尽管您可以使用[save （）](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.Save.aspx)方法保存回的部件， **XmlWriter** XML 和**XmlWriterSettings**类使您更好地控制输出，包括指定的编码类型。</span><span class="sxs-lookup"><span data-stu-id="7f309-262">Although you can use the [Save()](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.Save.aspx) method to save the XML back to the part, the **XmlWriter** and **XmlWriterSettings** classes allow you finer control over the output, including specifying the type of encoding.</span></span> <span data-ttu-id="7f309-263">**XDocument**类公开的接受**XmlWriter**对象，并将 XML 写回流[WriteTo(XmlWriter)](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.WriteTo.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-263">The **XDocument** class exposes a [WriteTo(XmlWriter)](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.WriteTo.aspx) method that takes an **XmlWriter** object and writes XML back to a stream.</span></span> 
  
<span data-ttu-id="7f309-264">使用以下过程从 Visio 页上的 XML 保存回页面内容部件。</span><span class="sxs-lookup"><span data-stu-id="7f309-264">Use the following procedure to save the XML from the Visio page back to the Page Contents part.</span></span>
  
### <a name="to-save-the-changed-xml-back-to-the-package"></a><span data-ttu-id="7f309-265">将已更改的 XML 保存回包中</span><span class="sxs-lookup"><span data-stu-id="7f309-265">To save the changed XML back to the package</span></span>

1. <span data-ttu-id="7f309-266">后`GetXElementByAttribute` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-266">After the  `GetXElementByAttribute` method in the **Program** class (or **Module1** in Visual Basic) from the previous step, add the following method.</span></span> 
    
  ```cs
  private static void SaveXDocumentToPart(PackagePart packagePart, 
      XDocument partXML)
  {
      
      // Create a new XmlWriterSettings object to 
      // define the characteristics for the XmlWriter
      XmlWriterSettings partWriterSettings = new XmlWriterSettings();
      partWriterSettings.Encoding = Encoding.UTF8;
      // Create a new XmlWriter and then write the XML
      // back to the document part.
      XmlWriter partWriter = XmlWriter.Create(packagePart.GetStream(),
          partWriterSettings);
      partXML.WriteTo(partWriter);
      // Flush and close the XmlWriter.
      partWriter.Flush();
      partWriter.Close();
  }
  ```

  ```vb
  Private Sub SaveXDocumentToPart(packagePart As PackagePart, _
      partXML As XDocument)
      ' Create a new XmlWriterSettings object to 
      ' define the characteristics for the XmlWriter.
      Dim partWriterSettings As XmlWriterSettings = New XmlWriterSettings()
      partWriterSettings.Encoding = Encoding.UTF8
      ' Create a new XmlWriter and then write the XML
      ' back to the document part.
      Dim partWriter As XmlWriter = XmlWriter.Create(packagePart.GetStream())
      partXML.WriteTo(partWriter)
      ' Flush and close the XmlWriter.
      partWriter.Flush()
      partWriter.Close()
  End Sub
  ```

2. <span data-ttu-id="7f309-267">在前一过程的代码下方，在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-267">Add the following code to the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic), beneath the code from the previous procedure.</span></span> 
    
  ```cs
  // Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML);
  
  ```

  ```vb
  ' Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML)
  
  ```

3. <span data-ttu-id="7f309-p128">选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。</span><span class="sxs-lookup"><span data-stu-id="7f309-p128">Choose the F5 key to debug the solution. When the program has completed running, choose any key to exit.</span></span>
    
4. <span data-ttu-id="7f309-270">在 Visio 2013 中打开 Visio Package.vsdx 文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-270">Open the Visio Package.vsdx file in Visio 2013.</span></span> 
    
<span data-ttu-id="7f309-271">“开始/结束”形状现在应包含文本“Start process”。</span><span class="sxs-lookup"><span data-stu-id="7f309-271">The Start/End shape should now contain the text "Start process".</span></span>
  
## <a name="recalculate-data-in-the-file"></a><span data-ttu-id="7f309-272">重新计算文件中的数据</span><span class="sxs-lookup"><span data-stu-id="7f309-272">Recalculate data in the file</span></span>
<span data-ttu-id="7f309-273"><a name="vis15_ManipulateFF_Recalculate"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-273"></span></span>

<span data-ttu-id="7f309-274">对文件中的数据的某些更改可能需要 Visio 重新打开该文件时计算文档。</span><span class="sxs-lookup"><span data-stu-id="7f309-274">Some changes to the data in a file may require Visio to recalculate the document when it opens the file.</span></span> <span data-ttu-id="7f309-275">Visio 提供大量的逻辑关系图，特别是对于在形状的关系的 （即，当形状依赖于另） 和连接形状。</span><span class="sxs-lookup"><span data-stu-id="7f309-275">Visio provides a lot of logic for a diagram, particularly for shape relationships (that is, when one shape depends on another) and connecting shapes.</span></span> <span data-ttu-id="7f309-276">如果数据的自定义逻辑所依赖的任何更改，Visio 将需要将更改传播到所有受影响的计算数据文件中。</span><span class="sxs-lookup"><span data-stu-id="7f309-276">If any of the data that the custom logic relies upon is changed, Visio needs to propagate the changes to all of the affected calculated data in the file.</span></span> 
  
<span data-ttu-id="7f309-277">Visio 2013 文件格式包括两个可用于重新计算文件中的数据的方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-277">The Visio 2013 file format includes a couple of techniques that you can use to recalculate data in the file.</span></span> <span data-ttu-id="7f309-278">有三种类型的当您决定是否需要重新计算 Visio 文件以及如何执行它时必须考虑的方案：</span><span class="sxs-lookup"><span data-stu-id="7f309-278">There are three types of scenarios that you must consider when you decide whether you need to recalculate the Visio file and how to do it:</span></span>
  
- <span data-ttu-id="7f309-279">对数据的更改不会影响的文件格式中的任何其他值。</span><span class="sxs-lookup"><span data-stu-id="7f309-279">The changes to the data do not affect any other values in the file format.</span></span> <span data-ttu-id="7f309-280">您无需添加到 Visio 文档重新计算的任何其他说明。</span><span class="sxs-lookup"><span data-stu-id="7f309-280">You don't need to add any additional instructions to Visio to recalculate the document.</span></span> <span data-ttu-id="7f309-281">如前面所述，通常可以而无需重新计算文档更改形状的文本。</span><span class="sxs-lookup"><span data-stu-id="7f309-281">As demonstrated previously, you can often change a shape's text without needing to recalculate the document.</span></span>
    
- <span data-ttu-id="7f309-282">对数据的更改仅限于更改在 XML 中的 ShapeSheet 单元格的值，并且没有其他取决于此数据的 ShapeSheet 值。</span><span class="sxs-lookup"><span data-stu-id="7f309-282">The changes to the data are limited to changing the values of ShapeSheet cells in the XML, and there are other ShapeSheet values that depend on this data.</span></span> <span data-ttu-id="7f309-283">在这种情况下，您必须添加 XML 处理指令 （使用[XProcessingInstruction](https://msdn.microsoft.com/library/System.Xml.Linq.XProcessingInstruction.aspx)类），已更改的**单元格**元素。</span><span class="sxs-lookup"><span data-stu-id="7f309-283">In this case, you must add an XML processing instruction (using the [XProcessingInstruction](https://msdn.microsoft.com/library/System.Xml.Linq.XProcessingInstruction.aspx) class) to the **Cell** element that has been changed.</span></span> <span data-ttu-id="7f309-284">例如， **ThemeIndex**单元格形状影响多个其他 ShapeSheet 单元格的形状中包含的值。</span><span class="sxs-lookup"><span data-stu-id="7f309-284">For example, the **ThemeIndex** cell for a shape affects the values of several other ShapeSheet cells contained in the shape.</span></span> <span data-ttu-id="7f309-285">如果您更改文件本身 （例如，"ThemeIndex" **N**值的**单元格**元素） 内的**ThemeIndex**单元格，您需要将处理指令添加到**单元格**元素，以便更新相关的值.</span><span class="sxs-lookup"><span data-stu-id="7f309-285">If you change the **ThemeIndex** cell within the file itself (for example, the **Cell** element with an **N** value of "ThemeIndex"), you will need to add a processing instruction to the **Cell** element so that the dependent values are updated.</span></span> 
    
- <span data-ttu-id="7f309-286">对数据的更改会影响连接器或连接点的位置。</span><span class="sxs-lookup"><span data-stu-id="7f309-286">The changes to the data affect the location of a connector or connection points.</span></span> <span data-ttu-id="7f309-287">有许多更改到 ShapeSheet 数据和要重新计算一条指令 （而不是添加的每次更改单个处理说明） 的整个文档时，另一种情况。</span><span class="sxs-lookup"><span data-stu-id="7f309-287">Another situation is when there are many changes to the ShapeSheet data and you want to recalculate the whole document with one instruction (rather than adding individual processing instructions for each change).</span></span> <span data-ttu-id="7f309-288">在这种情况下，您可以指示 Visio 重新打开时计算的整个文档。</span><span class="sxs-lookup"><span data-stu-id="7f309-288">In this case you can instruct Visio to recalculate the entire document when it is opened.</span></span> <span data-ttu-id="7f309-289">执行此操作通过将**RecalcDocument**属性添加到的自定义文件属性部分 (/ docProps/custom.xml) 的 Visio 程序包。</span><span class="sxs-lookup"><span data-stu-id="7f309-289">You do this by adding a **RecalcDocument** property to the Custom File Properties part (/docProps/custom.xml) of the Visio package.</span></span> <span data-ttu-id="7f309-290">调整的位置或已连接的图表中的形状的大小是这种方案的示例。</span><span class="sxs-lookup"><span data-stu-id="7f309-290">Adjusting the position or size of shapes in a connected diagram is an example of this type of scenario.</span></span> 
    
    <span data-ttu-id="7f309-291">请记住，从性能的角度看，这是成本最高的选项。</span><span class="sxs-lookup"><span data-stu-id="7f309-291">Keep in mind that this is the most costly option from a performance standpoint.</span></span>
    
<span data-ttu-id="7f309-292">使用以下过程将一个**单元格**元素插入到**形状**元素中，同一个**形状**中的其他**单元格**元素需要重新计算由于新值。</span><span class="sxs-lookup"><span data-stu-id="7f309-292">Use the following procedure to insert a **Cell** element into a **Shape** element, where other **Cell** elements in the same **Shape** need to be recalculated because of the new value.</span></span> <span data-ttu-id="7f309-293">新的**单元格**元素包含处理指令作为子元素，以通知 Visio 它需要执行一些本地重新计算。</span><span class="sxs-lookup"><span data-stu-id="7f309-293">The new **Cell** element includes a processing instruction as a child element, to inform Visio that it needs to perform some local recalculation.</span></span> 
  
### <a name="to-recalculate-values-for-a-single-shape"></a><span data-ttu-id="7f309-294">重新计算单个形状的值</span><span class="sxs-lookup"><span data-stu-id="7f309-294">To recalculate values for a single shape</span></span>

1. <span data-ttu-id="7f309-295">从上面的两个示例的代码替换 (更改形状的文本和调用`SaveXDocumentToPart`) 中**将 Program**类 （ **Using**块的**Main**方法中**Module1**中的**Main**方法中的**使用**块在 Visual Basic) 替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-295">Replace the code from the previous two examples (changing the shape's text and the call to  `SaveXDocumentToPart`) in the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic) with the following code.</span></span> 
    
  ```cs
  // Insert a new Cell element in the Start/End shape that adds an arbitrary
  // local ThemeIndex value. This code assumes that the shape does not 
  // already have a local ThemeIndex cell.
  startEndShapeXML.Add(new XElement("Cell",
      new XAttribute("N", "ThemeIndex"),
      new XAttribute("V", "25"),
      new XProcessingInstruction("NewValue", "V")));
  // Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML);
  
  ```

  ```vb
  ' Insert a new Cell element in the shape that adds an arbitrary local
  ' ThemeIndex value. This code assumes that the shape does not
  ' alrady have a local ThemeIndex cell.
  startEndShapeXML.Add(New XElement("Cell", _
      New XAttribute("N", "ThemeIndex"),
      New XAttribute("V", "25"),
      New XProcessingInstruction("NewValue", "V")))
  ' Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML)
  
  ```

2. <span data-ttu-id="7f309-p135">选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。</span><span class="sxs-lookup"><span data-stu-id="7f309-p135">Choose the F5 key to debug the solution. When the program has completed running, choose any key to exit.</span></span>
    
3. <span data-ttu-id="7f309-298">在 Visio 2013 中打开 Visio Package.vsdx 文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-298">Open the Visio Package.vsdx file in Visio 2013.</span></span> <span data-ttu-id="7f309-299">开始/结束形状现在应具有不同的填充颜色。</span><span class="sxs-lookup"><span data-stu-id="7f309-299">The Start/End shape should now have a different fill color.</span></span>
    
<span data-ttu-id="7f309-300">形状的颜色依赖**ThemeIndex**单元格的值，它确定其活动主题的形状继承。</span><span class="sxs-lookup"><span data-stu-id="7f309-300">The shape's color relies on the value of the **ThemeIndex** cell—it determines which of the active themes the shape inherits from.</span></span> <span data-ttu-id="7f309-301">在上面的示例，该形状设置为继承自不同的主题 （ **ThemeIndex**单元格设置为"25"值）。</span><span class="sxs-lookup"><span data-stu-id="7f309-301">In the previous example, the shape is set to inherit from a different theme (the **ThemeIndex** cell is set to a value of "25").</span></span> <span data-ttu-id="7f309-302">如果您不使用处理指令，形状的文本颜色 — 这还受**ThemeIndex**单元格 — 不重新计算。</span><span class="sxs-lookup"><span data-stu-id="7f309-302">If you don't use a processing instruction, the shape's text color—which is also affected by the **ThemeIndex** cell—isn't recalculated.</span></span> <span data-ttu-id="7f309-303">形状的填充颜色将更改为白色，但它的文本将保持白色 — 文本保持不可读。</span><span class="sxs-lookup"><span data-stu-id="7f309-303">The shape's fill color would change to white, but its text would remain white—leaving the text unreadable.</span></span> <span data-ttu-id="7f309-304">此外，处理指令中，不是可能的 Visio 可能形状更新以后，让文件保留在其中无法出现不可预测更新形状的格式值不稳定状态。</span><span class="sxs-lookup"><span data-stu-id="7f309-304">Also, without the processing instruction, it is possible that Visio may update the shape at a later date, leaving the file in an unstable state where the formatting values of the shape could be updated unpredictably.</span></span> 
  
<span data-ttu-id="7f309-305">如果更改需要重新计算 （例如，更改连接的形状的位置，因此，强制重排连接线），该文档的 Visio 文件中的数据您必须将重新计算指令添加到 Visio 文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-305">If you change data in the file that requires Visio to recalculate the document (for example, changing a connected shape's position and, therefore, forcing the connectors to reroute), you must add a recalculation instruction to the Visio file.</span></span> <span data-ttu-id="7f309-306">创建指令添加到 Visio 文件程序包的自定义文件属性部件 XML**属性**元素的**name**属性值为"RecalcDocument"。</span><span class="sxs-lookup"><span data-stu-id="7f309-306">The instruction is created by adding a **property** element with a **name** attribute value of "RecalcDocument" to the XML of the Custom File Properties part of the Visio file package.</span></span> <span data-ttu-id="7f309-307">作为最佳实践，您应检查以确保"RecalcDocument"指令已经尚未已注册的文件中的自定义文件属性部分。</span><span class="sxs-lookup"><span data-stu-id="7f309-307">As a best practice, you should check the Custom File Properties part to be sure that a "RecalcDocument" instruction hasn't already been registered in the file.</span></span> 
  
<span data-ttu-id="7f309-308">使用下面的代码从上面的示例更改开始/结束形状的**PinY**单元格的值。</span><span class="sxs-lookup"><span data-stu-id="7f309-308">Use the following code to change the value of the **PinY** cell of the Start/End shape from the previous examples.</span></span> <span data-ttu-id="7f309-309">该代码选择使用其**N**属性的值为**XElement**对象包含**PinY**单元格数据的**单元格**元素。</span><span class="sxs-lookup"><span data-stu-id="7f309-309">The code selects the **Cell** element that contains the **PinY** cell data as an **XElement** object by using the value of its **N** attribute.</span></span> <span data-ttu-id="7f309-310">然后，代码将重新计算指令添加到自定义文件属性部分中的 Visio 文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-310">The code then adds a recalculation instruction to the Custom File Properties part of the Visio file.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7f309-311">此代码依赖`GetPackagePart`和`SaveXDocumentToPart`先前创建的方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-311">This code relies on the  `GetPackagePart` and  `SaveXDocumentToPart` methods created previously.</span></span> 
  
### <a name="to-recalculate-the-entire-document-when-it-is-opened"></a><span data-ttu-id="7f309-312">打开文档时重新计算整个文档</span><span class="sxs-lookup"><span data-stu-id="7f309-312">To recalculate the entire document when it is opened</span></span>

1. <span data-ttu-id="7f309-313">后`SaveXDocumentToPart` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-313">After the  `SaveXDocumentToPart` method in the **Program** class (or **Module1** in Visual Basic) from the previous step, add the following method.</span></span> 
    
  ```cs
  private static void RecalcDocument(Package filePackage)
  {
      // Get the Custom File Properties part from the package and
      // and then extract the XML from it.
      PackagePart customPart = GetPackagePart(filePackage, 
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/" + 
          "custom-properties");
      XDocument customPartXML = GetXMLFromPart(customPart);
      // Check to see whether document recalculation has already been 
      // set for this document. If it hasn't, use the integer
      // value returned by CheckForRecalc as the property ID.
      int pidValue = CheckForRecalc(customPartXML);
      if (pidValue > -1)
      {
          XElement customPartRoot = customPartXML.Elements().ElementAt(0);
          // Two XML namespaces are needed to add XML data to this 
          // document. Here, we're using the GetNamespaceOfPrefix and 
          // GetDefaultNamespace methods to get the namespaces that 
          // we need. You can specify the exact strings for the 
          // namespaces, but that is not recommended.
          XNamespace customVTypesNS = customPartRoot.GetNamespaceOfPrefix("vt");
          XNamespace customPropsSchemaNS = customPartRoot.GetDefaultNamespace();
          // Construct the XML for the new property in the XDocument.Add method.
          // This ensures that the XNamespace objects will resolve properly, 
          // apply the correct prefix, and will not default to an empty namespace.
          customPartRoot.Add(
              new XElement(customPropsSchemaNS + "property",
                  new XAttribute("pid", pidValue.ToString()),
                  new XAttribute("name", "RecalcDocument"),
                  new XAttribute("fmtid", 
                      "{D5CDD505-2E9C-101B-9397-08002B2CF9AE}"),
                  new XElement(customVTypesNS + "bool", "true")
              ));
      }
      // Save the Custom Properties package part back to the package.
      SaveXDocumentToPart(customPart, customPartXML);
  }
  ```

  ```vb
  Private Sub RecalcDocument(filePackage As Package)
          ' Get the Custom File Properties part from the package and
          ' then extract the XML from it.
          Dim customPart As PackagePart = GetPackagePart(filePackage, _
              "http://schemas.openxmlformats.org/officeDocument/2006/" + _
              "relationships/custom-properties")
          Dim customPartXML As XDocument = GetXMLFromPart(customPart)
          ' Check to see whether document recalculation has already been
          ' set for this document. If it hasn't, use the integer
          ' value returned by CheckForRecalc as the property ID.
          Dim pidValue As Integer = CheckForRecalc(customPartXML)
          If (pidValue > 1) Then
              Dim customPartRoot As XElement = _
                  customPartXML.Elements().ElementAt(0)
              ' Two XML namespaces are needed to add XML data to this 
              ' document. Here, we're using the GetNamespaceOfPrefix and
              ' GetDefaultNamespace methods to get the namespaces that
              ' we need. You can specify the exact strings for the 
              ' namespaces, but that is not recommended.
              Dim customVTypesNS As XNamespace = _
                  customPartRoot.GetNamespaceOfPrefix("vt")
              Dim customPropsSchemaNS As XNamespace = _
                  customPartRoot.GetDefaultNamespace()
              ' Contruct the XML for the new property in the XDocument.Add
              ' method. This ensures that the XML namespaces resolve 
              ' properly, apply the correct prefix, and do not default to 
              ' an empty namespace.
              customPartRoot.Add( _
                  New XElement(customPropsSchemaNS + "property", _
                      New XAttribute("pid", pidValue.ToString()), _
                      New XAttribute("name", "RecalcDocument"), _
                      New XAttribute("fmtid", _
                          "{D5CDD505-2E9C-101B-9397-08002B2CF9AE}"), _
                      New XElement(customVTypesNS + "bool", "true") _
              ))
          ' Save the Custom Properties package part back to the package.
          SaveXDocumentToPart(customPart, customPartXML)
          End If
      End Sub
  ```

2. <span data-ttu-id="7f309-314">后`RecalcDocument` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-314">After the  `RecalcDocument` method in the **Program** class (or **Module1** in Visual Basic) from the previous step, add the following method.</span></span> 
    
  ```cs
  private static int CheckForRecalc(XDocument customPropsXDoc) 
  {
      
      // Set the inital pidValue to -1, which is not an allowed value.
      // The calling code tests to see whether the pidValue is 
      // greater than -1.
      int pidValue = -1;
      // Get all of the property elements from the document. 
      IEnumerable<XElement> props = GetXElementsByName(
          customPropsXDoc, "property");
      // Get the RecalcDocument property from the document if it exists already.
      XElement recalcProp = GetXElementByAttribute(props, 
          "name", "RecalcDocument");
      // If there is already a RecalcDocument instruction in the 
      // Custom File Properties part, then we don't need to add another one. 
      // Otherwise, we need to create a unique pid value.
      if (recalcProp != null)
      {
          return pidValue;
      }
      else
      {
          // Get all of the pid values of the property elements and then
          // convert the IEnumerable object into an array.
          IEnumerable<string> propIDs = 
              from prop in props
              where prop.Name.LocalName == "property"
              select prop.Attribute("pid").Value;
          string[] propIDArray = propIDs.ToArray();
          // Increment this id value until a unique value is found.
          // This starts at 2, because 0 and 1 are not valid pid values.
          int id = 2;
          while (pidValue == -1)
          {
              if (propIDArray.Contains(id.ToString()))
              {
                  id++;
              }
              else
              {
                  pidValue = id;
              }
          }
      }
      return pidValue;
  }
  
  ```

  ```vb
  Private Function CheckForRecalc(customPropsXDoc As XDocument) As Integer
      ' Set the initial pidValue to -1, which is not an allowed value. 
      ' The calling code test to see whether the pidValue is
      ' greater than -1.
      Dim pidValue As Integer = -1
      ' Get all of the property elements from the document.
      Dim props As IEnumerable(Of XElement) = GetXElementsByName( _
          customPropsXDoc, "property")
      ' Get the RecalcDocument property from the document if 
      ' it exists already.
      Dim recalcProp As XElement = GetXElementByAttribute(props, _
          "name", "RecalcDocument")
      ' If there is already a RecalcDocument instruction in the 
      ' Custom File Properties part, then we don't need another one.
      ' Otherwise, we need to create a unique pid value.
      If Not IsNothing(recalcProp) Then
          Return pidValue
      Else
          ' Get all of the pid values of the proeprty elements and then
          ' convert the IEnumerable object into an array.
          Dim propIDs As IEnumerable(Of String) = _
          From prop In props
          Where prop.Name.LocalName = "property"
          Select prop.Attribute("pid").Value
          Dim propIDArray As String() = propIDs.ToArray()
          ' Increment this id value until a unique value is found.
          ' This starts at 2, because 0 and 1 are not valid pid values.
          Dim id As Integer = 2
          While (pidValue = -1)
              If (propIDArray.Contains(id.ToString())) Then
                  id = id + 1
              Else
                  pidValue = id
              End If
          End While
      End If
      Return pidValue
  End Function
  ```

3. <span data-ttu-id="7f309-315">将 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中的前一示例代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-315">Replace the code from the previous example in the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic), with the following code.</span></span> 
    
  ```cs
  // Change the shape's horizontal position on the page 
  // by getting a reference to the Cell element for the PinY 
  // ShapeSheet cell and changing the value of its V attribute.
  XElement pinYCellXML = GetXElementByAttribute(
      startEndShapeXML.Elements(), "N", "PinY");
  pinYCellXML.SetAttributeValue("V", "2");
  // Add instructions to Visio to recalculate the entire document
  // when it is next opened.
  RecalcDocument(visioPackage);
  // Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML);
  
  ```

  ```vb
  ' Change the shape's horizontal position on the page
  ' by getting a reference to the Cell element for the PinY
  ' ShapeSheet cell and changing the value of its V attribute.
  Dim pinYCellXML As XElement = GetXElementByAttribute(
      startEndShapeXML.Elements(), "N", "PinY")
  pinYCellXML.SetAttributeValue("V", "2")
  ' Add instructions to Visio to recalculate the entire document
  ' when it is next opened.
  RecalcDocument(visioPackage)
  ' Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML)
  
  ```

4. <span data-ttu-id="7f309-p140">选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。</span><span class="sxs-lookup"><span data-stu-id="7f309-p140">Choose the F5 key to debug the solution. When the program has completed running, choose any key to exit.</span></span>
    
5. <span data-ttu-id="7f309-318">在 Visio 2013 中打开 Visio Package.vsdx 文件。</span><span class="sxs-lookup"><span data-stu-id="7f309-318">Open the Visio Package.vsdx file in Visio 2013.</span></span> 
    
<span data-ttu-id="7f309-p141">“开始/结束”形状现在应该距离绘图底部 2 英寸。“开始/结束”形状和“流程”形状之间的连接器应该已经重新路由以适应布局变更。如果 **RecalcDocument** 属性尚未添加到文件中，形状位置可能已更改，但连接器尚未重新路由到形状的新位置。</span><span class="sxs-lookup"><span data-stu-id="7f309-p141">The Start/End shape should now be 2 inches from the bottom edge of the drawing. The connector between the Start/End shape and the Process shape should have rerouted to accommodate the change in layout. If the **RecalcDocument** property had not been added to the file, the shape position would have been changed, but the connector would not have rerouted to the new location of the shape.</span></span> 
  
## <a name="add-a-new-package-part-to-a-package"></a><span data-ttu-id="7f309-322">向包中添加新的包部件</span><span class="sxs-lookup"><span data-stu-id="7f309-322">Add a new package part to a package</span></span>
<span data-ttu-id="7f309-323"><a name="vis15_ManipulateFF_AddNewPart"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-323"></span></span>

<span data-ttu-id="7f309-324">修改文件包的最常见方案之一将新文档部件添加到包中。</span><span class="sxs-lookup"><span data-stu-id="7f309-324">One of the most common scenarios for modifying a file package is adding a new document part to the package.</span></span> <span data-ttu-id="7f309-325">例如，如果您想要将页面添加到 Visio 绘图通过将内容添加到包，您需要将页面内容部件添加到包。</span><span class="sxs-lookup"><span data-stu-id="7f309-325">For example, if you want to add a page to the Visio drawing by adding content to the package, you need to add a Page Contents part to the package.</span></span> 
  
<span data-ttu-id="7f309-326">向文件包中添加新部件的过程非常简单：</span><span class="sxs-lookup"><span data-stu-id="7f309-326">The process for adding a new part to the package is straightforward:</span></span> 
  
1. <span data-ttu-id="7f309-p143">您使用 **PackagePart** 的数据创建 XML 文档。您需要特别注意用于管理所创建的特定 XML 文档类型的方案的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="7f309-p143">You create the XML document with the data for the **PackagePart**. You need to pay special attention to the XML namespaces that govern the schema for the specific type of XML document that you create.</span></span>
    
2. <span data-ttu-id="7f309-329">您创建一个新文件以包含 XML 并将文件保存到 **Package** 中的某个位置。</span><span class="sxs-lookup"><span data-stu-id="7f309-329">You create a new file to contain the XML and save the file to a location in the **Package**.</span></span>
    
3. <span data-ttu-id="7f309-330">您在新 **PackagePart** 和 **Package** 或其他 **PackagePart** 对象之间创建必要的关系。</span><span class="sxs-lookup"><span data-stu-id="7f309-330">You create the necessary relationships between the new **PackagePart** and the **Package** or other **PackagePart** objects.</span></span> 
    
4. <span data-ttu-id="7f309-p144">您更新引用新部件所需的任何现有部件。例如，如果您在文件中添加新的页面内容部件（一个新页面），则您还需要更新页面索引部件（/visio/pages/pages.xml 文件），以包含关于新页面的正确信息。</span><span class="sxs-lookup"><span data-stu-id="7f309-p144">You update any existing parts that need to reference the new part. For example, if you add a new Page Contents part (a new page) to the file, you also need to update the Page Index part (/visio/pages/pages.xml file) to include the correct information about the new page.</span></span>
    
<span data-ttu-id="7f309-333">使用以下过程在 Visio 文件中创建新的功能区可扩展部件。</span><span class="sxs-lookup"><span data-stu-id="7f309-333">Use the following procedure to create a new Ribbon Extensibility part in the Visio file.</span></span> <span data-ttu-id="7f309-334">新的功能区可扩展部件向功能区添加新选项卡与包含一个按钮的单个组。</span><span class="sxs-lookup"><span data-stu-id="7f309-334">The new Ribbon Extensibility part adds to the ribbon a new tab with a single group that contains a single button.</span></span>
  
### <a name="to-create-a-new-package-part"></a><span data-ttu-id="7f309-335">创建新的包部件</span><span class="sxs-lookup"><span data-stu-id="7f309-335">To create a new package part</span></span>

1. <span data-ttu-id="7f309-336">后`CheckForRecalc`中前面的过程中，**程序**类 （或在 Visual Basic 中的**模块 1** ） 方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-336">After the  `CheckForRecalc` method in the **Program** class (or **Module1** in Visual Basic) from the previous procedure, add the following method.</span></span> 
    
  ```cs
  private static XDocument CreateCustomUI()
  {
      // Add a new Custom User Interface document part to the package.
      // This code adds a new CUSTOM tab to the ribbon for this
      // document. The tab has one group that contains one button.
      XNamespace customUINS = 
          "http://schemas.microsoft.com/office/2006/01/customui";
      XDocument customUIXDoc = new XDocument(
          new XDeclaration("1.0", "utf-8", "true"),
          new XElement(customUINS + "customUI",
              new XElement(customUINS + "ribbon",
                  new XElement(customUINS + "tabs",
                      new XElement(customUINS + "tab",
                          new XAttribute("id", "customTab"),
                          new XAttribute("label", "CUSTOM"),
                          new XElement(customUINS + "group",
                              new XAttribute("id", "customGroup"),
                              new XAttribute("label", "Custom Group"),
                              new XElement(customUINS + "button",
                                  new XAttribute("id", "customButton"),
                                  new XAttribute("label", "Custom Button"),
                                  new XAttribute("size", "large"),
                                  new XAttribute("imageMso", "HappyFace")
                              )
                          )
                      )
                  )
              )
          )
      );
      return customUIXDoc;
  }
  ```

  ```vb
  Private Function CreateCustomUI() As XDocument
      ' Add a new Custom User Interface document part to the package.
      ' This code adds a new CUSTOM tab to the ribbon for this
      ' document. The tab has one group that contains one button.
      Dim customUINS As XNamespace = _
          "http://schemas.microsoft.com/office/2006/01/customui"
      Dim customUIXML = New XDocument( _
          New XDeclaration("1.0", "utf-8", "true"), _
          New XElement(customUINS + "customUI", _
              New XElement(customUINS + "ribbon",
                  New XElement(customUINS + "tabs",
                      New XElement(customUINS + "tab",
                          New XAttribute("id", "customTab"),
                          New XAttribute("label", "CUSTOM"),
                          New XElement(customUINS + "group",
                              New XAttribute("id", "customGroup"),
                              New XAttribute("label", "Custom Group"),
                              New XElement(customUINS + "button",
                                  New XAttribute("id", "customButton"),
                                  New XAttribute("label", "Custom Button"),
                                  New XAttribute("size", "large"),
                                  New XAttribute("imageMso", "HappyFace")
                              )
                          )
                      )
                  )
              )
          )
      )
      Return customUIXML
  End Function
  ```

2. <span data-ttu-id="7f309-337">后`CreateCustomUI` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="7f309-337">After the  `CreateCustomUI` method in the **Program** class (or **Module1** in Visual Basic) from the previous step, add the following method.</span></span> 
    
  ```cs
  private static void CreateNewPackagePart(Package filePackage, 
      XDocument partXML, Uri packageLocation, string contentType, 
      string relationship)
  {
      // Need to check first to see whether the part exists already.
      if (!filePackage.PartExists(packageLocation))
      {
          // Create a new blank package part at the specified URI 
          // of the specified content type.
          PackagePart newPackagePart = filePackage.CreatePart(packageLocation,
              contentType);
          // Create a stream from the package part and save the 
          // XML document to the package part.
          using (Stream partStream = newPackagePart.GetStream(FileMode.Create,
              FileAccess.ReadWrite))
          {
              partXML.Save(partStream);
          }
      }
      // Add a relationship from the file package to this
      // package part. You can also create relationships
      // between an existing package part and a new part.
      filePackage.CreateRelationship(packageLocation,
          TargetMode.Internal,
          relationship);
  }
  ```

  ```vb
  Private Sub CreateNewPackagePart(filePackage As Package, _
      partXML As XDocument, packageLocation As Uri, contentType As String, _
      relationship As String)
      ' Need to check first to see whether the part exists already.
      If Not (filePackage.PartExists(packageLocation)) Then
          ' Create a new blank package part at the specified URI
          ' of the specified content type.
          Dim newPart As PackagePart = filePackage.CreatePart(packageLocation, _
              contentType)
          ' Create a stream from the package part and save the
          ' XML document to the package part.
          Using partStream As Stream = newPart.GetStream(FileMode.Create, _
              FileAccess.ReadWrite)
              partXML.Save(partStream)
          End Using
          ' Add a relationship from the file package to this
          ' package part. You can also create relationships
          ' between an existing package part and a new part.
          filePackage.CreateRelationship(packageLocation, _
              TargetMode.Internal, relationship)
      End If
  End Sub
  ```

3. <span data-ttu-id="7f309-338">将 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中的所有代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="7f309-338">Replace all the code in the **using** block in the **Main** method of the **Program** class (the **Using** block of the **Main** method in **Module1** in Visual Basic), with the following code.</span></span> 
    
  ```cs
  // Create a new Ribbon Extensibility part and add it to the file.
  XDocument customUIXML = CreateCustomUI();
  CreateNewPackagePart(visioPackage, customUIXML, 
      new Uri("/customUI/customUI1.xml", UriKind.Relative),
      "application/xml",
      "http://schemas.microsoft.com/office/2006/relationships/ui/extensibility");
  ```

  ```vb
  ' Create a new Ribbon Extensibility part and add it to the file.
  Dim customUIXML As XDocument = CreateCustomUI()
  CreateNewPackagePart(visioPackage, customUIXML, _
      New Uri("/customUI/customUI1.xml", UriKind.Relative), _
      "application/xml", _
      "http://schemas.microsoft.com/office/2006/relationships/ui/extensibility")
  ```

4. <span data-ttu-id="7f309-p146">选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。</span><span class="sxs-lookup"><span data-stu-id="7f309-p146">Choose the F5 key to debug the solution. When the program has completed running, choose any key to exit.</span></span>
    
5. <span data-ttu-id="7f309-341">在 Visio 2013 中打开 Visio Package.vsdx 文件，然后选择**自定义**选项卡。</span><span class="sxs-lookup"><span data-stu-id="7f309-341">Open the Visio Package.vsdx file in Visio 2013, and then choose the **CUSTOM** tab.</span></span> 
    
<span data-ttu-id="7f309-342">自定义功能区类似于图 2 中，在 Visio 2013 中打开该文件时。</span><span class="sxs-lookup"><span data-stu-id="7f309-342">The custom ribbon looks like Figure 2 when the file is opened in Visio 2013.</span></span>
  
 <span data-ttu-id="7f309-343">**图 2。在 Visio 2013 功能区中的自定义选项卡**</span><span class="sxs-lookup"><span data-stu-id="7f309-343">**Figure 2. Custom tab in the Visio 2013 ribbon**</span></span>
  
![功能区中的自定义选项卡](media/vis15_CustomRibbonTab.PNG)
  
<span data-ttu-id="7f309-345">创建 XML`CreateCustomUI`方法如下所示。</span><span class="sxs-lookup"><span data-stu-id="7f309-345">The XML created by the  `CreateCustomUI` method looks like the following.</span></span> 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<customUI xmlns="http://schemas.microsoft.com/office/2006/01/customui">
  <ribbon>
    <tabs>
      <tab id="customTab" label="CUSTOM">
        <group id="customGroup" label="Custom Group">
          <button id="customButton" label="Custom Button" size="large"
              imageMso="HappyFace" />
        </group>
      </tab>
    </tabs>
  </ribbon>
</customUI>
```

## <a name="acknowledgements"></a><span data-ttu-id="7f309-346">鸣谢</span><span class="sxs-lookup"><span data-stu-id="7f309-346">Acknowledgements</span></span>
<span data-ttu-id="7f309-347"><a name="vis15_ManipulateFF_Ackn"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-347"></span></span>

<span data-ttu-id="7f309-348">我们要识别的贡献和 Visio 的 MVP**所有 Edlund**创建本技术文章中包含的代码示例中的输入。</span><span class="sxs-lookup"><span data-stu-id="7f309-348">We would like to recognize the contribution and input of Visio MVP **Al Edlund** in creating the code examples contained in this technical article.</span></span> <span data-ttu-id="7f309-349">所有操作的 Visio 文件格式，包括 Visio XML 绘图格式 (.vdx) 和新的 Visio 文件格式 (.vsdx) 识别的专家。</span><span class="sxs-lookup"><span data-stu-id="7f309-349">Al is a recognized expert in manipulating the Visio file format, including both the Visio XML Drawing format (.vdx) and the new Visio file format (.vsdx).</span></span> <span data-ttu-id="7f309-350">所有创建了以编程方式浏览 Visio 文件格式的项目，并公开内的结构。</span><span class="sxs-lookup"><span data-stu-id="7f309-350">Al has created projects that explore the Visio file formats programmatically and exposes the structures inside.</span></span> 
  
<span data-ttu-id="7f309-351">有关所有的使用 Visio 文件格式的详细信息，请参阅后面的其他资源部分中的链接。</span><span class="sxs-lookup"><span data-stu-id="7f309-351">For more information about Al's work with the Visio file format, see the links in the Additional Resources section that follows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7f309-352">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f309-352">See also</span></span>
<span data-ttu-id="7f309-353"><a name="vis15_ManipulateFF_Additional"> </a></span><span class="sxs-lookup"><span data-stu-id="7f309-353"></span></span>

- <span data-ttu-id="7f309-354">Al Edlund：</span><span class="sxs-lookup"><span data-stu-id="7f309-354">By Al Edlund:</span></span>
    
  - <span data-ttu-id="7f309-355">在 CodePlex 上的[pkgVisio-Visio 2013 XML 操作](http://pkgvisio.codeplex.com/documentation)项目。</span><span class="sxs-lookup"><span data-stu-id="7f309-355">[pkgVisio - Visio 2013 XML manipulation](http://pkgvisio.codeplex.com/documentation) project on CodePlex.</span></span> 
    
  - <span data-ttu-id="7f309-356">[pkgVisio_pt1](http://www.youtube.com/watch?v=7LvDKJuP9oQ&amp;feature=youtu.be) YouTube 上的视频。</span><span class="sxs-lookup"><span data-stu-id="7f309-356">[pkgVisio_pt1 ](http://www.youtube.com/watch?v=7LvDKJuP9oQ&amp;feature=youtu.be) video on YouTube.</span></span> 
    
  - <span data-ttu-id="7f309-357">[pkgVisio_pt2](http://www.youtube.com/watch?v=ZIWSXhNSkG8&amp;feature=youtu.be) YouTube 上的视频。</span><span class="sxs-lookup"><span data-stu-id="7f309-357">[pkgVisio_pt2 ](http://www.youtube.com/watch?v=ZIWSXhNSkG8&amp;feature=youtu.be) video on YouTube.</span></span> 
    
- [<span data-ttu-id="7f309-358">Visio 开发中心</span><span class="sxs-lookup"><span data-stu-id="7f309-358">Visio Developer Center</span></span>](http://msdn.microsoft.com/en-us/office/aa905478.aspx)
    
- [<span data-ttu-id="7f309-359">操作 Office Open XML 格式文档</span><span class="sxs-lookup"><span data-stu-id="7f309-359">Manipulate Office Open XML Formats Documents</span></span>](http://msdn.microsoft.com/en-us/library/aa982683%28v=office.12%29.aspx)
    
- [<span data-ttu-id="7f309-360">创建包含命名空间 (C#) (LINQ to XML) 的文档</span><span class="sxs-lookup"><span data-stu-id="7f309-360">Create a Document with Namespaces (C#) (LINQ to XML)</span></span>](http://msdn.microsoft.com/en-us/library/bb387075.aspx)
    
- [<span data-ttu-id="7f309-361">在不启动 Microsoft Office 的情况下向文档中添加自定义 XML 部件</span><span class="sxs-lookup"><span data-stu-id="7f309-361">Add Custom XML Parts to Documents Without Starting Microsoft Office</span></span>](http://msdn.microsoft.com/en-us/library/bb608597%28VS.90%29.aspx)
    

