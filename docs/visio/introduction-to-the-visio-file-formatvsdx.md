---
title: Visio 文件格式 (.vsdx) 简介
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 69736f40-8f67-46c2-abf6-82dffecb2274
description: 了解 Visio 2013 中的新文件格式浏览以编程方式使用 Visio 2013 文件格式的一些高级概念，并创建一个简单的控制台应用程序检查 Visio 2013 文件。
ms.openlocfilehash: 4efa90ee513def005653f4f8717b0149de1cdc3d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389363"
---
# <a name="introduction-to-the-visio-file-format-vsdx"></a>Visio 文件格式 (.vsdx) 简介

了解 Visio 2013 中的新文件格式浏览以编程方式使用 Visio 2013 文件格式的一些高级概念，并创建一个简单的控制台应用程序检查 Visio 2013 文件。
  
|||
|:-----|:-----|
|**本文中**         [简介](#vis15_IntroVSDX_Intro)          [本质"的 Visio 2013 文件格式是什么？](#vis15_IntroVSDX_What)          [使用 Visio 2013 文件格式的开发人员方案](#vis15_IntroVSDX_Scenarios)          [以编程方式浏览 Visio 2013 文件格式](#vis15_IntroVSDX_Explore)          [其他资源](#vis15_IntroVSDX_Resources)||
   
## <a name="introduction"></a>简介
<a name="vis15_IntroVSDX_Intro"> </a>

Visio 2013 为 Visio 取代了 Visio 二进制文件格式 (.vsd) 和 Visio XML 绘图文件格式 (.vdx) 引入了新的文件格式 (.vsdx)。 Visio 2013 文件格式基于开放打包约定和 XML，因为熟悉这些技术的开发人员可以快速了解如何以编程方式使用 Visio 2013 文件。 开发人员熟悉从早期版本的 Visio Visio XML 绘图文件格式 (.vdx) 可以找到许多相同的 XML 结构内.vsdx 文件格式的部分。 由于第三方软件可以处理文件格式级别的 Visio 文件极大地增加与 Visio 文件互操作性。 Visio 2013 文件格式都支持 Microsoft SharePoint Server 2013 中的 Visio Services 无需发布到 SharePoint Server"中间"的文件格式。
  
有几种文件类型，按扩展名组成的 Visio 2013 文件格式。 这些扩展包括：
  
- .vsdx （Visio 绘图）
    
- .vsdm （Visio 启用宏的模具）
    
- .vssx （Visio 模具）
    
- .vssm （Visio 启用宏的绘图）
    
- .vstx （Visio 模板）
    
- .vstm （Visio 启用宏的模板）
    
> [!NOTE]
> 仅启用宏的文件（.vsdm、.vssm、.vstm）可以存储 VBA 宏。不能将宏存储在扩展名为 .vsdx、.vssx 或 .vstx 的文件中。 
  
## <a name="what-is-the-visio-2013-file-format-under-the-hood"></a>什么是本质"的 Visio 2013 文件格式？
<a name="vis15_IntroVSDX_What"> </a>

Visio 2013 文件格式使用开放式装箱约定 (OPC)，它定义存储一起使用的一些 sort─for 示例中，一个 ZIP 文件的容器的相关资源的应用程序数据的结构化的方法。 在基本级别，Visio 2013 文件实际上是包含其他类型的文件的 ZIP 容器。 实际上，您可以在 Visio 2013 为.vsdx 文件中保存绘图、 重命名的文件扩展名为"\*.zip"在 Windows 资源管理器，然后打开该文件的 like 文件夹以查看内的内容。
  
> [!NOTE]
>  本文包含简要概述的开放打包约定。 您可以找到更多详细的其他文章中的约定的范围： > 有关自己的开放打包约定的详细信息，请参阅[OPC: 新标准打包您的数据](https://msdn.microsoft.com/magazine/cc163372.aspx)。 > 的开放打包约定以及在 Microsoft Office 文件中的使用它们的详细信息，请参阅[Essentials 的开放打包约定](https://msdn.microsoft.com/library/ee361919.aspx)和[介绍 Office (2007) Open XML 文件格式](https://msdn.microsoft.com/library/aa338205.aspx)。 
  
### <a name="packages-and-package-parts"></a>包和包部件

开始之前，Visio 2013 文件是在其中保存 （称为"包部件"） 的其他文件的 ZIP 容器或"包"。 包部件可以是 XML 文件，图像，甚至将 VBA 解决方案。 部件的包中可以进一步划分为两个三大类、"文档部件"和"关系部件"。 文档部件包含实际内容和元数据的 Visio 文件，如文件、 第一页和所有它所包含的形状的名称，但偶数的形状的数据连接。 图像和文本的包中的文件被视为文档部件。 本主题后面的更详细地描述了关系部件。
  
> [!NOTE]
> 如果您打开 Visio 2013 文件使用 ZIP 实用程序，您可能会看出在 ZIP 包中包含的多个文件夹。 您甚至可以处理类似文件夹使用 ZIP 实用工具这些子地址。 但是，这些"文件夹"表示 ZIP 包，而不是实际的文件夹内的子地址。 不能使用的文件夹的编程的等效项以在您的解决方案与这些子地址。 
  
包部件─文档部件和关系部件─也具有相关的内容类型。这些内容类型是用于定义 MIME 媒体类型的字符串。这些内容类型指定可以包含在文件中的 MIME 类型并限定其范围。
  
### <a name="relationships"></a>关系

关系部件 (其结束，扩展名为"\*.rels"和"_rels"文件夹中存储) 介绍每个包中的部件之间的关系，并提供文件的结构。 一个独立的 XML 文档使用元素的父/子的关系来确定对每个其他实体的关系。 其他文件可以使用其他层次结构或文件的文件夹结构来描述文件中的内容的交互。 Visio 2013 文件格式，包是一个有效的 Visio 文件，如果它包含正确的部件，并且程序包包含部分之间的关系。 
  
关系部件是用于描述包中不同文档部件之间关系的 XML 文档。它们定义了两个项目之间的关联：指定源（由关系文件的名称和位置定义）和指定目标文档部件。例如，关系部件用于描述哪些主控形状与文件相关联，页面和文件以及页面之间有何关系，或者图像和对象与特定页面有何关系。 
  
### <a name="similarities-and-differences-with-visio-vdx-schema"></a>相似之处以及使用 Visio VDX 架构的区别

如上所述，以前版本的 Visio 还包含一个基于 XML 的文件格式、 Visio XML 绘图格式或.vdx。 （在 Visio 以前的版本，用于 Visio XML 绘图格式的架构调用 DatadiagramML。）从 Visio XML 架构中的某些组件具有由于相同的两个文件格式之间的时间。 例如， **Windows**元素及其子级保持 unchanged─with **Windows**元素现在是 XML 文档 (window.xml) 的根元素的异常。 
  
XML 绘图格式和 Visio 2013 文件格式的最大区别是打包。 像普通的独立 XML; 可操作的 XML 绘图格式文件Visio 2013 文件格式必须为包进行操作。 在 Visio 2013 中的 XML 已分为更轻松地消耗的部件。 另一个显著更改是 Visio 2013 文件格式的文档部件描述标准 OPC （app.xml、 core.xml custom.xml） 中存储的所有文档属性。
  
但是，还有一次所有 Visio 开发人员都必须注意的重大更改：**单元格**、**行**和**部分**元素的介绍。 在 XML 绘图文件格式架构中，由命名元素表示单个行和 ShapeSheet 中的单元格。 例如，假设您拥有具有一个包含形状的**PinX**值为"2"（这意味着形状的旋转 pin 从左边缘的绘图的 2 英寸） 的单个页面的文档。 下面的代码中显示的 XML 绘图文件格式设置的相关标记。 
  
```XML
<Shape ID="1" TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape">
    <XForm> 
        <PinX Unit="IN">2</Pinx>
        <!--- Other cells in the Shape Transform section -->
    </XForm>
    <!--- Other rows and cells in the ShapeSheet -->
</Shape>

```

此处**PinX**元素是**XForm**元素，这又是**形状**元素的子元素的子元素。 此模型 Visio ShapeSheet UI，其中将**PinX**单元格包含在形状的**Shape Transform**内容中。 
  
在 Visio 2013 文件格式，ShapeSheet─ **PinX**， **LinePattern**，在**geometry**内容，etc.─are 由一种类型的**单元格**元素的 XML 元素中某一**MoveTo**行**X**单元格中所有单元格。 不同的**单元格**元素被 individuated 相互由其**N**属性的值。 因此，在上面的示例中，ShapeSheet 中的**PinX**单元格中包含的数据存储在 VSDX 文件中的以下代码所示。 
  
```XML
<Shape TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape" ID="1">
    <Cell N="PinX" U="IN" V="2"/>
    <!--- Other cells in the ShapeSheet --> 
</Shape>
```

**PinX** （以及如**LinePattern**或**LockSelect**调用"singleton 单元格"其他单个、 命名单元格） 的**单元格**元素是直接元素的子**形状**。 没有唯一元素需要为每个形状只能有一个**PinX**表示包含**PinX**单元格的行。
  
包括表格数据，如**geometry 内容**的部分呢？ 有关这些分区中的单元格，Visio 2013 文件格式架构使用**部分**和**行**elements─also 按其**N**属性或作为显示 below─to **T**属性可分辨包含的数据。 例如，同一形状的上一示例可能包含类似于下面的代码 XML 绘图架构中的**geometry 1**节中的数据。 
  
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

但是，则它类似于下面的代码中的 Visio 2013 文件。
  
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

## <a name="developer-scenarios-for-working-with-the-visio-2013-file-format"></a>使用 Visio 2013 文件格式的开发人员方案
<a name="vis15_IntroVSDX_Scenarios"> </a>

如上所述，Visio 2013 文件格式将利用如 ZIP 文件和 XML 存储数据的几种充分理解的技术。 操作绘图文件级别的 Visio 2013，解决方案只需使用.NET Framework 命名空间和类与使用 ZIP 文件或 XML，如[System.IO.Packaging](https://msdn.microsoft.com/library/system.io.packaging%28v=vs.110%29.aspx)或[System.Xml](https://msdn.microsoft.com/library/system.xml%28v=vs.110%29.aspx)关联。
  
开发人员的 Visio 2013 文件格式的主要好处是，您可以读取和写入到 Visio 2013 文件不自动 Visio 客户端应用程序。 您可以使用 Visio 2013 文件格式的考虑作为开发人员某些方案包括：
  
- 检查特定数据的单个 Visio 2013 文件。 您可以有选择地阅读 ZIP 容器的其中一项，而无需提取整个文件。
    
- 使用特定内容更新 Visio 2013 文件的库。 您可以编程方式更改所有背景页，以反映新的品牌准则中的徽标。
    
- 创建使用 Visio 2013 文件应用程序。 例如，您可以生成一个工具，读取 Visio 工作流关系图，然后执行自己基于该工作流的业务逻辑。
    
请注意，因为这些解决方案均使用标准的 .NET Framework 程序集，可在客户端计算机上运行的大多数解决方案也可在服务器上运行！
  
## <a name="exploring-the-visio-2013-file-format-programmatically"></a>以编程方式浏览 Visio 2013 文件格式
<a name="vis15_IntroVSDX_Explore"> </a>

使用 Visio 2013 文件格式任何开发人员的最基本、 基本任务是打开文件另存为包，然后访问的包中的各个部分。 **System.IO.Packaging.Package** WindowsBase.dll 中包含许多类，您可以打开和操作程序包和部件。 
  
在以下代码示例中，您可以了解如何打开 .vsdx 文件，读取包中的部件列表并获取关于每个部件的信息。
  
### <a name="to-open-a-vsdx-file-and-view-the-document-parts"></a>打开 .vsdx 文件并查看文档部件

1. 打开 Visio 2013 并创建一个新文档。
    
2. 创建一个新文档并将其保存到桌面。
    
3. 打开 Visual Studio 2008。
    
4. 在**文件**菜单中，选择**新建**，然后选择 * * 项目 * *。
    
5. 在“Visual C#”**** 或“Visual Basic”**** 下，展开“Windows”****，然后选择“控制台应用程序”****。
    
6. 在**名称**框中，键入 VisioFileExplorer。 控制台应用程序项目打开。 
    
7. 在“解决方案资源管理器”中，右键单击“VisioFileExplorer”，然后单击“添加引用”。 
    
8. 在“添加引用”**** 对话框的“程序集”**** 下，展开“框架”****，然后选择“WindowsBase”****。
    
9. 将以下代码粘贴到解决方案中。
    
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

10. 按 F5 调试解决方案。该程序运行完成后，按任意键退出。
    
## <a name="see-also"></a>另请参阅
<a name="vis15_IntroVSDX_Resources"> </a>

关于 Visio 2013 文件格式、 开放打包约定或如何以编程方式与 Visio 2013or Office OpenXML 文件的详细信息，请参阅以下资源：
  
- [面向开发人员的 Visio](https://msdn.microsoft.com/office/aa905478.aspx)
    
- [OPC： 打包您的数据的新标准](https://msdn.microsoft.com/magazine/cc163372.aspx)。
    
- [开放打包约定的基础知识](https://msdn.microsoft.com/library/ee361919.aspx)
    
- [介绍 Office (2007) Open XML 文件格式](https://msdn.microsoft.com/library/aa338205.aspx)
    

