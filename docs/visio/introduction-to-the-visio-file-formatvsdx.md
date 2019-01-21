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
# <a name="introduction-to-the-visio-file-format-vsdx"></a>Visio 文件格式 (.vsdx) 简介

了解 Visio 2013 中的新文件格式，探索以编程方式处理 Visio 2013 文件格式的一些高级概念，并创建一个用于检查 Visio 2013 文件的简单控制台应用程序。
  
|||
|:-----|:-----|
|**本文内容**         [简介](#vis15_IntroVSDX_Intro)          [Visio 2013 文件格式本质上是什么？](#vis15_IntroVSDX_What)          [开发人员使用 Visio 2013 文件格式的应用场景](#vis15_IntroVSDX_Scenarios)          [以编程方式探索 Visio 2013 文件格式](#vis15_IntroVSDX_Explore)          [其他资源](#vis15_IntroVSDX_Resources)||
   
## <a name="introduction"></a>简介
<a name="vis15_IntroVSDX_Intro"> </a>

Visio 2013 为 Visio 引入了一种新的文件格式 (.vsdx)，此格式取代了 Visio 二进制文件格式 (.vsd) 和 Visio XML 绘图文件格式 (.vdx)。 由于 Visio 2013 文件格式基于开放打包约定和 XML，熟悉这些技术的开发人员可以快速了解如何以编程方式处理 Visio 2013 文件。 熟悉 Visio 早期版本的 Visio XML 绘图文件格式 (.vdx) 的开发人员可以在 .vsdx 文件格式的部分中发现许多相同的 XML 结构。 由于第三方软件可以在文件格式级别操作 Visio 文件，因此与 Visio 文件的互操作性大大增强。 Microsoft SharePoint Server 2013 中的 Visio Services 支持 Visio 2013 文件格式，而无需使用发布到 SharePoint Server 的“中间”文件格式。
  
Visio 2013 文件格式包含几种文件类型（按扩展名区分）。 这些扩展名包括：
  
- .vsdx（Visio 绘图）
    
- .vsdm（Visio 启用宏的绘图）
    
- .vssx（Visio 模具）
    
- .vssm（Visio 启用宏的模具）
    
- .vstx（Visio 模板）
    
- .vstm（Visio 启用宏的模板）
    
> [!NOTE]
> 仅启用宏的文件（.vsdm、.vssm、.vstm）可以存储 VBA 宏。不能将宏存储在扩展名为 .vsdx、.vssx 或 .vstx 的文件中。 
  
## <a name="what-is-the-visio-2013-file-format-under-the-hood"></a>Visio 2013 文件格式本质上是什么？
<a name="vis15_IntroVSDX_What"> </a>

Visio 2013 文件格式使用开放打包约定 (OPC)，定义了使用某种容器（例如 ZIP 文件）将应用程序数据与相关资源存储在一起的结构化方法。 在底层，Visio 2013 文件实际上是包含其他类型文件的 ZIP 容器。 实际上，可以将 Visio 2013 中的绘图另存为 .vsdx 文件，在 Windows 资源管理器中将文件扩展名重命名为“\*.zip”，然后像文件夹一样打开该文件以查看其中的内容。
  
> [!NOTE]
>  本文仅提供开放打包约定的简要概述。 你可以在其他文章中找到有关此类约定的更多详细信息：> 有关开放打包约定本身的详细信息，请参阅 [OPC：数据打包的新标准](https://msdn.microsoft.com/magazine/cc163372.aspx)。 > 有关开放打包约定及其在 Microsoft Office 文件中的使用的详细信息，请参阅[开放打包约定的基础知识](https://msdn.microsoft.com/library/ee361919.aspx)和 [Office (2007) Open XML 文件格式简介](https://msdn.microsoft.com/library/aa338205.aspx)。 
  
### <a name="packages-and-package-parts"></a>包和包部件

如前所述，Visio 2013 文件是 ZIP 容器或“包”，其中包含其他文件（称为“包部件”）。 包部件可以是 XML 文件、图像甚至是 VBA 解决方案。 包内的部件可以进一步分为两大类：“文档部件”和“关系部件”。 文档部件包含 Visio 文件的实际内容和元数据，如文件名、第一页和文件包含的所有形状，甚至是形状的数据连接。 包中的图像和文本文件被视为文档部件。 本文稍后将详细介绍关系部件。
  
> [!NOTE]
> 如果使用 ZIP 实用工具打开 Visio 2013 文件，可能会看到 ZIP 包中包含的多个文件夹。 甚至可以使用 ZIP 实用工具操作这些子地址，例如文件夹。 但是，这些“文件夹”表示 ZIP 包中的子地址，而不是实际文件夹。 不能使用文件夹的程序等效项来处理解决方案中的这些子地址。 
  
包部件─文档部件和关系部件─也具有相关的内容类型。这些内容类型是用于定义 MIME 媒体类型的字符串。这些内容类型指定可以包含在文件中的 MIME 类型并限定其范围。
  
### <a name="relationships"></a>关系

关系部件（以扩展名“\*.rels”结尾并存储在“_rels”文件夹中）描述了包中的部件如何相互关联并提供文件的结构。 独立的 XML 文档使用元素的父/子关系来确定实体之间的关系。 其他文件可以使用其他层次结构或文件夹结构来描述文件内容关系。 对于 Visio 2013 文件格式，如果包中包含正确的一组部件并且包中包含部件之间的关系，则该包便是有效的 Visio 文件。 
  
关系部件是用于描述包中不同文档部件之间关系的 XML 文档。它们定义了两个项目之间的关联：指定源（由关系文件的名称和位置定义）和指定目标文档部件。例如，关系部件用于描述哪些主控形状与文件相关联，页面和文件以及页面之间有何关系，或者图像和对象与特定页面有何关系。 
  
### <a name="similarities-and-differences-with-visio-vdx-schema"></a>与 Visio VDX 架构的相似性和区别

如前所述，以前版本的 Visio 还包括基于 XML 的文件格式、Visio XML 绘图格式或 .vdx。 （在以前版本的 Visio 中，用于 Visio XML 绘图格式的架构称为 DatadiagramML。）Visio XML 架构中的某些部分在两种文件格式之间保持不变。 例如，**Windows** 元素及其子元素保持不变，例外之处在于 **Windows** 元素现在是 XML 文档 (window.xml) 的根元素。 
  
XML 绘图格式和 Visio 2013 文件格式之间的最大区别是打包。 可以像普通的独立 XML 一样对 XML 绘图格式文件进行操作；必须将 Visio 2013 文件格式作为包进行操作。 在 Visio 2013 中，XML 已分成多个部分以便于使用。 另一个明显的变化是 Visio 2013 文件格式将所有文档属性存储在由 OPC 标准描述的文档部分（app.xml、core.xml、custom.xml）中。
  
但是，所有 Visio 开发人员必须注意的一个重大变化是引入了 **Cell**、**Row** 和 **Section** 元素。 在 XML 绘图文件格式架构中，ShapeSheet 中的各个行和单元格由命名元素表示。 例如，假设有一个单页文档包含 **PinX** 值为“2”的形状（意味着形状的旋转固定点距离图形的左边缘为 2 英寸）。 在 XML 绘图文件格式中，该设置的相关标记如以下代码所示。 
  
```XML
<Shape ID="1" TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape">
    <XForm> 
        <PinX Unit="IN">2</Pinx>
        <!--- Other cells in the Shape Transform section -->
    </XForm>
    <!--- Other rows and cells in the ShapeSheet -->
</Shape>

```

在此处，**PinX** 元素是 **XForm** 元素的子元素，而后者又是 **Shape** 元素的子元素。 这样可以为 Visio ShapeSheet UI 建模，其中的 **PinX** 单元格包含在形状的 **Shape Transform** 节中。 
  
在 Visio 2013 文件格式中，ShapeSheet 中的所有单元格（**PinX**、**LinePattern**、**Geometry** 节的 **MoveTo** 行中的 **X** 单元格等）由一种类型的 XML 元素（**Cell** 元素）表示。 不同的 **Cell** 元素通过其 **N** 属性的值彼此个体化。 因此，在上面的示例中，ShapeSheet 中的 **PinX** 单元格包含的数据存储在 VSDX 文件中，如以下代码所示。 
  
```XML
<Shape TextStyle="3" FillStyle="3" LineStyle="3" Type="Shape" ID="1">
    <Cell N="PinX" U="IN" V="2"/>
    <!--- Other cells in the ShapeSheet --> 
</Shape>
```

**PinX** 的 **Cell** 元素（以及其他称为“单一单元格”的单独命名单元格，如 **LinePattern** 或 **LockSelect**）是 **Shape** 元素的直接子元素。 不需要唯一元素来表示包含 **PinX** 单元格的行，因为每个形状只能有一个 **PinX**。
  
那些包含表格数据的节（比如 **Geometry** 节）又如何呢？ 对于这些节中的单元格，Visio 2013 文件格式架构使用 **Section** 和 **Row** 元素（也可以通过它们的 **N** 属性或 **T** 属性进行区分，如下所示）来包含数据。 例如，前一个示例中的相同形状可能在 **Geometry 1** 节中包含类似于以下采用 XML 绘图架构的代码的数据。 
  
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

但是，它在 Visio 2013 文件中如以下代码所示。
  
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

## <a name="developer-scenarios-for-working-with-the-visio-2013-file-format"></a>开发人员使用 Visio 2013 文件格式的应用场景
<a name="vis15_IntroVSDX_Scenarios"> </a>

如上所述，Visio 2013 文件格式利用了一些易于理解的技术（如 ZIP 文件和 XML）来存储数据。 若要在文件级别操作 Visio 2013 绘图，一种解决方案只需要使用与 ZIP 文件或 XML（如 [System.IO.Packaging](https://msdn.microsoft.com/library/system.io.packaging%28v=vs.110%29.aspx) 或 [System.Xml](https://msdn.microsoft.com/library/system.xml%28v=vs.110%29.aspx)）的处理相关联的 .NET Framework 命名空间和类。
  
对 Visio 2013 文件格式的开发人员而言，主要好处在于可以在不自动执行 Visio 客户端应用程序的情况下读取和写入 Visio 2013 文件。 可视为使用 Visio 2013 文件格式的开发人员的一些应用场景包括：
  
- 检查各个 Visio 2013 文件以查找特定数据。 你可以选择性地从 ZIP 容器中读出一项，而无需提取整个文件。
    
- 使用特定内容更新 Visio 2013 文件的库。 你可以用编程方式更改所有背景页面中的徽标，以反映新的品牌准则。
    
- 创建使用 Visio 2013 文件的应用程序。 例如，你可以构建一个工具，用于读取 Visio 工作流图，然后根据该工作流执行自己的业务逻辑。
    
请注意，因为这些解决方案均使用标准的 .NET Framework 程序集，可在客户端计算机上运行的大多数解决方案也可在服务器上运行！
  
## <a name="exploring-the-visio-2013-file-format-programmatically"></a>以编程方式探索 Visio 2013 文件格式
<a name="vis15_IntroVSDX_Explore"> </a>

对于使用 Visio 2013 文件格式的任何开发人员来说，最基本和最重要的任务是将文件作为包打开，然后访问包中的各个部件。 WindowsBase.dll 中的 **System.IO.Packaging.Package** 包含许多可用于打开和操作包和部件的类。 
  
在以下代码示例中，您可以了解如何打开 .vsdx 文件，读取包中的部件列表并获取关于每个部件的信息。
  
### <a name="to-open-a-vsdx-file-and-view-the-document-parts"></a>打开 .vsdx 文件并查看文档部件

1. 打开 Visio 2013 并创建一个新文档。
    
2. 创建新文档并将其保存到桌面。
    
3. 打开 Visual Studio 2012。
    
4. 在“**文件**”菜单上，选择“**新建**”，然后选择“**项目**”。
    
5. 在“**Visual C#**”或“**Visual Basic**”下，展开“**Windows**”，然后选择“**控制台应用程序**”。
    
6. 在“**名称**”框中，键入“VisioFileExplorer”。 控制台应用程序项目将打开。 
    
7. 在“**解决方案资源管理器**”中，右键单击“**VisioFileExplorer**”，然后单击“**添加引用**”。 
    
8. 在“**添加引用**”对话框中的“**程序集**”下，展开“**框架**”，然后选择“**WindowsBase**”。
    
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

10. 按 F5 以调试解决方案。该程序完成运行后，按任意键退出。
    
## <a name="see-also"></a>另请参阅
<a name="vis15_IntroVSDX_Resources"> </a>

有关 Visio 2013 文件格式、开放打包约定或如何以编程方式处理 Visio 2013 或 Office OpenXML 文件的详细信息，请参阅以下资源：
  
- [Visio 开发人员参考](https://msdn.microsoft.com/office/aa905478.aspx)
    
- [OPC：打包数据的新标准](https://msdn.microsoft.com/magazine/cc163372.aspx)
    
- [开放打包约定的基础知识](https://msdn.microsoft.com/library/ee361919.aspx)
    
- [Office (2007) Open XML 文件格式简介](https://msdn.microsoft.com/library/aa338205.aspx)
    

