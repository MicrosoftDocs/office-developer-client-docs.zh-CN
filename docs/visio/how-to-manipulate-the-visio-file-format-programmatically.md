---
title: 以编程方式处理 Visio 文件格式
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5f5e2288-7539-41b8-916d-410be028ed9b
description: ''
ms.openlocfilehash: 39f31293e99d46f33e9e9a071bd489dd461a1553
ms.sourcegitcommit: 4590b7ed906d008693a58abe63f089ed8a380b34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2018
ms.locfileid: "26643225"
---
# <a name="manipulate-the-visio-file-format-programmatically"></a>以编程方式处理 Visio 文件格式

![操作方法主题](media/mod_icon_howto.png)
  
了解如何在 Visual Studio 2012，以读取 Visio 2013 中的新文件格式包、 包中选择部件、 更改部件中的数据和将新部件添加到包中创建解决方案。
  
|||
|:-----|:-----|
|**本文中**         [Visio 文件格式操作 essentials](#vis15_ManipulateFF_Essentials)          [创建一个.vsdx 文件和新的 Visual Studio 解决方案](#vis15_ManipulateFF_CreateFile)          [打开一个 Visio 2013 文件作为包](#vis15_ManipulateFF_OpenPackage)          [选择和读取从包包部件](#vis15_ManipulateFF_SelectPart)          [选择并更改包部件中的 XML 数据](#vis15_ManipulateFF_ChangeXML)          [重新计算文件中的数据](#vis15_ManipulateFF_Recalculate)          [添加到包中新包部件](#vis15_ManipulateFF_AddNewPart)          [确认](#vis15_ManipulateFF_Ackn)          [其他资源](#vis15_ManipulateFF_Additional)||
   
## <a name="visio-file-format-manipulation-essentials"></a>Visio 文件格式操纵基础知识
<a name="vis15_ManipulateFF_Essentials"> </a>

Visio 以前的版本专有的二进制文件格式 (.vsd) 或单文档 Visio XML 绘图文件格式 (.vdx) 保存文件。 Visio 2013 引入了新的文件格式 (.vsdx)，它基于 XML 和 ZIP 存档技术。 只需与以前版本的 Visio，文件将保存在单个容器中。 与不同旧式文件，但是，新文件格式可以是打开、 读取、 更新、 更改，和构造不自动执行 Visio 2013 应用程序。 熟悉操作 XML 或使用[System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx)命名空间的开发人员可以快速开始以编程方式使用新文件格式。 开发人员使用从早期版本的 Visio XML 绘图格式过可以找到的许多从该格式的结构中保留的新文件格式。 
  
本文中，我们将研究如何使用 Visio 2013 文件格式，以编程方式使用 Microsoft.NET Framework 4.5、 C# 或 Visual Basic 和 Visual Studio 2012。 您可以了解如何以打开一个 Visio 2013 文件，选择文件内的文档部件，更改数据部件中的创建的新文档部件。
  
> [!NOTE]
> 本文中的代码示例假定您已在[System.Xml.Linq](https://msdn.microsoft.com/library/System.Xml.Linq.aspx)和[System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx)命名空间的类的基本了解。 > 本文还假定您了解的概念和术语的开放打包约定。 您应该熟悉包、 文档部件或包部件和关系的概念。 有关详细信息，请参阅[OPC: 新标准打包您的数据](https://msdn.microsoft.com/magazine/cc163372.aspx)。 > 的代码演示如何创建 LINQ （语言集成查询） 查询以选择 XML。 大多数的代码示例使用用于生成 LINQ 查询查询语法。 您可以重新编写任何 LINQ 查询，如有必要，代码中使用 LINQ 方法语法，提供。 有关 LINQ 查询语法和方法的语法的详细信息，请参阅[LINQ 查询语法与方法语法 (C#)](https://msdn.microsoft.com/library/bb397947.aspx)> 表 1 显示了通过本文工作之前应熟悉的基本主题。 
  
**表 1. 操纵 Visio 2013 文件格式的核心概念**

|**文章标题**|**说明**|
|:-----|:-----|
|[Visio 文件格式 (.vsdx) 简介](introduction-to-the-visio-file-formatvsdx.md) <br/> |此高级 overview 介绍一些 Visio 2013 文件格式的主要功能。 它讨论开放打包约定 (OPC)，因为它们具有已应用到 Visio 2013 文件格式。 它还列出了一些 Visio 2013 文件格式和以前的 Visio XML 绘图文件格式 (.vdx) 之间的差异。  <br/> |
|[OPC： 打包您的数据的新标准](https://msdn.microsoft.com/magazine/cc163372.aspx) <br/> |此 MSDN 杂志文章将开放打包约定作为概念进行介绍。  <br/> |
|[开放打包约定的基础知识](https://msdn.microsoft.com/library/ee361919.aspx) <br/> [介绍 Office (2007) Open XML 文件格式](https://msdn.microsoft.com/library/aa338205.aspx) <br/> |以下两篇文章讨论如何开放打包约定已应用于 Microsoft Office 文件。 它们包含如何关系包中的工作原理以及还包括一些代码示例的说明。  <br/> |
   
## <a name="create-a-vsdx-file-and-a-new-visual-studio-solution"></a>创建 .vsdx 文件和新的 Visual Studio 解决方案
<a name="vis15_ManipulateFF_CreateFile"> </a>

您可以开始工作完成本文中的过程之前，您需要创建的 Visio 2013 文件打开和操作。 本文中的代码示例中使用该绘图包含单个页面与它被"基本流程图"模板的"开始/结束"形状的形状之一的两个连接的形状。
  
使用以下过程创建新的 Visio 2013 文件在本文中的其余过程中使用。
  
### <a name="to-create-new-file-in-visio-2013"></a>在 Visio 2013 中创建新的文件

1. 打开 Visio 2013。
    
2. 创建基本流程图模板上基于通过选择**类别**、**流程图**、**基本流程图**、**创建**一个新文档。
    
3. 从**形状**窗口中，**开始/结束**形状拖到画布中。 
    
4. 在画布上选择新的“开始/结束”形状，并键入“Begin Process”。
    
5. 从**形状**窗口中，**过程**形状拖到画布中。 
    
6. 在画布上选择新的“流程”形状，并键入“Perform some task”。
    
7. 在开始/结束形状的快捷菜单，选择**向页面添加一个连接器**，然后画和连接器之间的开始/结束和进程形状画布上, 图 1 中所示。
    
    **图 1。简单的 Visio 2013 绘图**
    
     ![与进程形状连接的头部/尾部形状](media/vis15_SimpleFlowchart.png)
  
8. 选择**文件**、**另存为**、**计算机**、**桌面**保存到您的桌面为.vsdx 文件文件。
    
    在**另存为**对话框中，输入**文件名**框中的 Visio 程序包""，请选择**Visio 绘图 (\*.vsdx)** 中**保存类型**列表，然后再选择**保存**按钮。 
    
9. 关闭该文件，然后关闭 Visio 2013。
    
> [!TIP]
> 有时 Visio 打开一个文件成功，即使有问题的文件。 若要确保 Visio 通知的文件中的任何问题，应测试解决方案的处理文件包级别的 Visio 文件时启用文件打开警告。 > 到启用文件打开警告，在 Visio 2013 中，选择**文件**，**选项**，**高级**。 在**保存/打开**，选择**显示文件打开警告**。 
  
这些过程使用 Windows 控制台应用程序操作的"Visio Package.vsdx"文件。 使用以下过程可创建和设置 Visual Studio 2012 中的新 Windows 控制台应用程序。
  
### <a name="to-create-a-new-solution-in-visual-studio-2012"></a>在 Visual Studio 2012 中创建新的解决方案

1. 在**文件**菜单上选择**新建****项目**。
    
2. 在**新建项目**对话框中，展开**Visual C#** 或**Visual Basic**中，，然后选择**Windows**，**控制台应用程序**。
    
    在**名称**框中，输入 VisioFileAccessor，为该项目，选择一个位置，然后选择**确定**按钮。 
    
3. 在"项目"菜单上，选择"添加引用"。 
    
    **引用管理器**对话框的**程序集**，选择**框架**，然后再添加对**System.Xml**和**WindowsBase**组件的引用。 
    
4. 在项目的 Program.cs 或 Module1.vb 文件中，添加以下 **using** 指令（Visual Basic 中的 **Imports** 语句）： 
    
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

5. 此外，在 Program.cs 或 Module1.vb 文件中，在 **Program** 类（Visual Basic 中的 **Module1**）的 **Main** 方法结束之前，添加以下代码，停止执行控制台应用程序，直到用户按下某个键。 
    
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

## <a name="open-a-visio-2013-file-as-a-package"></a>为包中打开 Visio 2013 文件
<a name="vis15_ManipulateFF_OpenPackage"> </a>

您可以处理的任何文件内数据之前，您需要首先打开[包](https://msdn.microsoft.com/library/System.IO.Packaging.Package.aspx)对象中，在[System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx)命名空间内包含的文件。 **软件包**对象作为一个整体代表 Visio 文件。 它公开允许您选择的文件包中的单个文档部件的成员。 具体而言，**包**类公开的静态[Open （String，FileMode，文件访问）](https://msdn.microsoft.com/library/System.IO.Packaging.Package.Open.aspx)方法用来打开包文件。 它还公开[close （）](https://msdn.microsoft.com/library/System.IO.Packaging.Package.Close.aspx)方法用于关闭包后已完成，但它。 
  
> [!TIP]
> 最佳做法是，使用**使用**块**包**对象中打开 Visio 文件，以便您无需完成后与其显式关闭文件包。 您可以在**try/catch/finally**构造**finally**块中还显式调用**Package.Close**方法。 
  
使用下面的代码通过使用一个[FileInfo](https://msdn.microsoft.com/library/System.IO.FileInfo.aspx)对象获取"Visio Package.vsdx"文件的完整路径，将路径作为参数传递给**Package.Open**方法，然后调用代码返回**包**对象。 
  
### <a name="to-open-a-vsdx-file-as-a-package"></a>将 .vsdx 文件作为文件包打开

1. 在 **Program** 类（或 Visual Basic 中的 **Module1**）中的 **Main** 方法后面，添加以下代码。 
    
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

2. 在 **Program** 类（或 Visual Basic 中的 **Module1**）中的 **Main** 方法中，添加以下代码。 
    
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

## <a name="select-and-read-package-parts-from-a-package"></a>从包中选择并读取包部件
<a name="vis15_ManipulateFF_SelectPart"> </a>

为包打开该 Visio 2013 文件后，您可以访问内它使用[PackagePart](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePart.aspx)类**System.IO.Packaging**命名空间中包含的文档部件。 独立的或作为集合，可以实例化**PackagePart**对象。 **包**类公开的[GetParts()](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetParts.aspx)方法以及获取**PackagePart**对象超出**包**的[GetPart(Uri)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetPart.aspx)方法。 **Package.GetParts**方法返回的[PackagePartCollection](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePartCollection.aspx)类中，您可以然后交互像实现的其他任何集合实例[IEnumerator\<T\>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerator-1?redirectedfrom=MSDN&view=netframework-4.7.2)接口。 
  
使用以下过程中的代码，作为一个整体从 **Package** 中获取 **PackagePartCollection** 对象，循环访问集合中的 **PackagePart** 对象，并将每个 **PackagePart** 的 URI 和内容类型写入到控制台中。 
  
### <a name="to-iterate-through-the-package-parts-in-a-package"></a>循环访问包中的包部件

1. 后`OpenPackage`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下代码。 
    
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

2. 在 **Program** 类的 **Main** 方法的 **using** 块（Visual Basic 中 **Module1** 中 **Main** 方法的 **Using** 块）内，添加以下代码： 
    
  ```cs
  // Write the URI and content type of each package part to the console.
  IteratePackageParts(visioPackage);
  
  ```

  ```vb
  ' Write the URI and content type of each package part to the console.
  IteratePackageParts(visioPackage)
  
  ```

3. 选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。
    
控制台应用程序生成如下所示的输出（为了简单起见，某些输出已被省略）：
  
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
  
个通常不多，您需要选择一个**PackagePart** ，而不必循环访问所有这些。 您可以使用它与**包**或另一个**PackagePart**关系从**包**中获取**PackagePart**对象。 与每个其他相关的文件格式是单独的实体的介绍的文档部件如何与 Visio 2013 中的关系文件包或如何两个文档部件。 例如，Visio 2013 文件包本身已与它的 Visio 文档部件的关系和 Visio 文档部件具有与 Windows 部件的关系。 这些关系表示为[PackageRelationship](https://msdn.microsoft.com/library/System.IO.Packaging.PackageRelationship.aspx)或[PackageRelationshipCollection](https://msdn.microsoft.com/library/System.IO.Packaging.PackageRelationshipCollection.aspx)类的实例。 
  
**包**类公开几种方法来获取它包含作为**PackageRelationship**或**PackageRelationshipCollection**对象的关系。 [GetRelationshipsByType(String)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetRelationshipsByType.aspx)方法可用于实例化**PackageRelationshipCollection**对象，其中包含单个特定类型的**PackageRelationship**对象。 当然，使用**Package.GetRelationshipsByType**方法要求您知道您需要的关系类型。 关系类型是 XML 命名空间格式的字符串。 例如，Visio 文档部件的关系类型是https://schemas.microsoft.com/visio/2010/relationships/document。 
  
一旦您知道 **PackagePart** 与 **Package** 或与另一个 **PackagePart** 的关系（即，您有一个 **PackageRelationship** 对象引用所需的 **PackagePart**），即可使用此关系获取该 **PackagePart** 的 URI。然后您可以将 URI 传递到 **Package.GetPart** 方法以返回 **PackagePart**。
  
> [!NOTE]
> 您还可以对特定**PackagePart**使用刚**Package.GetPart**方法和**PackagePart**，URI 绕过其中您获取包部件的关系的步骤。 但是，某些包部件中的 Visio 文件包可以保存到包中其默认位置以外的位置。 不能假定包部件始终位于同一个 URI 的每个文件。 > 相反，它是最佳做法是使用关系来访问各个**PackagePart**对象。 
  
使用以下过程获取 **PackagePart**（Visio 文档部件），方法是使用引用该部件的 **Package** 中的 **PackageRelationship** 。 
  
### <a name="to-select-a-specific-package-part-in-the-package-by-relationship"></a>按关系选择包中的特定包部件

1. 后`IteratePackageParts`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下方法。 
    
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

2. 将 **Program** 类的 **Main** 方法的 **using** 块（Visual Basic 中 **Module1** 中 **Main** 方法的 **Using** 块）替换为以下代码。 
    
  ```cs
  // Get a reference to the Visio Document part contained in the file package.
  PackagePart documentPart = GetPackagePart(visioPackage, 
      "https://schemas.microsoft.com/visio/2010/relationships/document");
  
  ```

  ```vb
  ' Get a reference to the Visio Document part contained in the file package.
  Dim documentPart As PackagePart = GetPackagePart(visioPackage, _
      "https://schemas.microsoft.com/visio/2010/relationships/document")
  
  ```

如前所述，还可以使用其关系的其他**PackagePart**对象获取**PackagePart**对象。 这很重要，因为 Visio 文档的任何复杂性，大多数**PackagePart**对象没有与**包**的关系。 例如，文件包 (即，/visio/pages/page1.xml) 中的单个页面内容部件具有对页索引部分 (即，/visio/pages/pages.xml)，但不适用于文件包自身的关系。 如果您没有单独的页的同一 URI 程序包中，您可以使用它与页索引部件的关系以获取对它的引用。
  
**PackagePart**类公开的[GetRelationshipsByType(String)](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePart.GetRelationshipsByType.aspx)方法可用于返回一个包含**PackageRelationship**对象的一种类型的**PackageRelationshipCollection**对象。 **PackageRelationshipCollection**后，您可以选择**PackageRelationship** ，您需要从集合，然后参考**PackagePart**对象。 
  
使用以下代码从 **Package** 获取 **PackagePart**，方法是使用与另一个 **PackagePart** 的关系（获取 **PackageRelationship** 对象）。
  
### <a name="to-select-a-specific-package-part-through-its-relationship-to-another-package-part"></a>通过与另一个包部件的关系选择特定的包部件

1. 后`GetPackagePart`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下重载方法。 
    
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

2. 在前一过程的代码下方，在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码。（请勿删除您在前一过程中添加的代码。） 
    
  ```cs
  // Get a reference to the collection of pages in the document, 
  // and then to the first page in the document.
  PackagePart pagesPart = GetPackagePart(visioPackage, documentPart, 
      "https://schemas.microsoft.com/visio/2010/relationships/pages");
  PackagePart pagePart = GetPackagePart(visioPackage, pagesPart, 
      "https://schemas.microsoft.com/visio/2010/relationships/page");
  
  ```

  ```vb
  ' Get a reference to the collection of pages in the document,
  ' and then to the first page in the document.
  Dim pagesPart As PackagePart = GetPackagePart(visioPackage, documentPart, _
      "https://schemas.microsoft.com/visio/2010/relationships/pages") 
  Dim pagePart As PackagePart = GetPackagePart(visioPackage, pagesPart, _
      "https://schemas.microsoft.com/visio/2010/relationships/page") 
  ```

您可以对文档部件中包含的 XML 进行更改之前，您需要先将 XML 文档加载到一个对象，允许您读取的 XML 中，使用[XDocument](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.aspx)类或[XmlDocument](https://msdn.microsoft.com/library/System.Xml.XmlDocument.aspx)类。 这两个类公开任务选择 XML 元素包含在 XML 文档中; 例如的方法创建、 读取和写入属性;并向文档中插入新的 XML 元素。 
  
在这两个类中，**XDocument** 类允许您使用 LINQ 查询 XML。使用 LINQ，您可以轻松地从 XML 文档中选择单个元素，方法是通过创建查询，而不是通过循环访问集合中的所有元素并测试您所需的元素。因此，本文中的后续过程将使用 **XDocument** 类以及 **System.Xml.Linq** 命名空间的其他类来处理 XML。 
  
使用以下过程，在 **XDocument** 对象中打开 **PackagePart** 作为 XML 文档。 
  
### <a name="to-read-the-xml-in-a-package-part"></a>读取包部件中的 XML

1. 后的最后一个重载，以`GetPackagePart`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下方法。 
    
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

2. 在前一过程的代码下方，在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码。 
    
  ```cs
  // Open the XML from the Page Contents part.
  XDocument pageXML = GetXMLFromPart(pagePart);
  ```

  ```vb
  ' Open the XML from the Page Contents part.
  Dim pageXML As XDocument = GetXMLFromPart(pagePart)
  ```

## <a name="select-and-change-xml-data-in-a-package-part"></a>选择并更改包部件中的 XML 数据
<a name="vis15_ManipulateFF_ChangeXML"> </a>

将文档部件加载到 **XDocument** 对象之后，您可以使用 LINQ 选择 XML 元素并对 XML 文档进行更改。您可以更改 XML 数据、添加或删除数据，然后将 XML 文档保存回文档部件。 
  
操作的 Visio 文件格式的最常见的任务文档中选择特定的 XML 元素的集合。 **System.Xml.Linq**命名空间包括[XElement](https://msdn.microsoft.com/library/System.Xml.Linq.XElement.aspx)类，该类表示一个 XML 元素。 **XElement**类使您可以访问 Visio 文件在精细级别，从**ValidationRule**元素 （作为示例） 的单个**形状**元素中包含的数据。 
  
使用以下代码从 **XDocument**（包含页面内容部件）中选择 **Shape** 元素，然后选择特定的 **Shape** 元素。 
  
### <a name="to-select-a-specific-element-in-a-package-part"></a>选择包部件中的特定元素

1. 后`GetXMLFromPart`中的**程序**类 （或 Visual Basic 中的**模块 1** ），方法添加以下方法。 
    
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

2. 后`GetXElementsByName` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。 
    
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

3. 在前一过程的代码下方，在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码。 
    
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

一旦有什么对**XDocument**对象中包含一个**XElement**对象的引用，可以处理类似的任何其他 XML 数据和，从而，更改 Visio 文件中包含的数据。 例如，如果形状有文本，在 Visio 中打开时，则相应的**形状**元素将包含至少一个**文本**元素。 如果您更改该**文本**元素的值，Visio 中查看该文件时，将更改形状的文本。 
  
在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码，将“开始/结束”形状中的文本从“Begin process”更改为“Start process”。 
  
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
> 在以前的代码示例中，现有的形状文本和字符串，用于替换其具有相同数量的字符。 另请注意，LINQ 查询更改 （即，在这种情况下，文本节点） 返回的元素的最后一个子节点的值。 这样做是为了避免更改**cp**元素的**文本**元素的子元素的设置。 > 很可能导致形状文本采用编程方式更改通过覆盖**文本**元素的所有子级文件系统不稳定。 如上面的示例所示的文本格式由文件中的**文本**元素下面**cp**元素表示。 父**部分**元素中存储的格式的定义。 如果这些两条信息变得不一致，该文件不可能会像预期。 Visio 愈合许多不一致，但最好以确保，以便您控制该文件的最终行为编程的任何更改都是一致。 
  
当您对文档部件的 XML 进行更改时，这些更改仅存在于内存中。要将更改保留在文件中，您必须将 XML 保存回文档部件。
  
下面的代码使用[XmlWriter](https://msdn.microsoft.com/library/System.Xml.XmlWriter.aspx)类和[XmlWriterSettings](https://msdn.microsoft.com/library/System.Xml.XmlWriterSettings.aspx)类写回包部件的 XML。 尽管您可以使用[save （）](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.Save.aspx)方法保存回的部件， **XmlWriter** XML 和**XmlWriterSettings**类使您更好地控制输出，包括指定的编码类型。 **XDocument**类公开的接受**XmlWriter**对象，并将 XML 写回流[WriteTo(XmlWriter)](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.WriteTo.aspx)方法。 
  
使用以下过程从 Visio 页上的 XML 保存回页面内容部件。
  
### <a name="to-save-the-changed-xml-back-to-the-package"></a>将已更改的 XML 保存回包中

1. 后`GetXElementByAttribute` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。 
    
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

2. 在前一过程的代码下方，在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码。 
    
  ```cs
  // Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML);
  
  ```

  ```vb
  ' Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML)
  
  ```

3. 选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。
    
4. 在 Visio 2013 中打开 Visio Package.vsdx 文件。 
    
“开始/结束”形状现在应包含文本“Start process”。
  
## <a name="recalculate-data-in-the-file"></a>重新计算文件中的数据
<a name="vis15_ManipulateFF_Recalculate"> </a>

对文件中的数据的某些更改可能需要 Visio 重新打开该文件时计算文档。 Visio 提供大量的逻辑关系图，特别是对于在形状的关系的 （即，当形状依赖于另） 和连接形状。 如果数据的自定义逻辑所依赖的任何更改，Visio 将需要将更改传播到所有受影响的计算数据文件中。 
  
Visio 2013 文件格式包括两个可用于重新计算文件中的数据的方法。 有三种类型的当您决定是否需要重新计算 Visio 文件以及如何执行它时必须考虑的方案：
  
- 对数据的更改不会影响的文件格式中的任何其他值。 您无需添加到 Visio 文档重新计算的任何其他说明。 如前面所述，通常可以而无需重新计算文档更改形状的文本。
    
- 对数据的更改仅限于更改在 XML 中的 ShapeSheet 单元格的值，并且没有其他取决于此数据的 ShapeSheet 值。 在这种情况下，您必须添加 XML 处理指令 （使用[XProcessingInstruction](https://msdn.microsoft.com/library/System.Xml.Linq.XProcessingInstruction.aspx)类），已更改的**单元格**元素。 例如， **ThemeIndex**单元格形状影响多个其他 ShapeSheet 单元格的形状中包含的值。 如果您更改文件本身 （例如，"ThemeIndex" **N**值的**单元格**元素） 内的**ThemeIndex**单元格，您需要将处理指令添加到**单元格**元素，以便更新相关的值. 
    
- 对数据的更改会影响连接器或连接点的位置。 有许多更改到 ShapeSheet 数据和要重新计算一条指令 （而不是添加的每次更改单个处理说明） 的整个文档时，另一种情况。 在这种情况下，您可以指示 Visio 重新打开时计算的整个文档。 执行此操作通过将**RecalcDocument**属性添加到的自定义文件属性部分 (/ docProps/custom.xml) 的 Visio 程序包。 调整的位置或已连接的图表中的形状的大小是这种方案的示例。 
    
    请记住，从性能的角度看，这是成本最高的选项。
    
使用以下过程将一个**单元格**元素插入到**形状**元素中，同一个**形状**中的其他**单元格**元素需要重新计算由于新值。 新的**单元格**元素包含处理指令作为子元素，以通知 Visio 它需要执行一些本地重新计算。 
  
### <a name="to-recalculate-values-for-a-single-shape"></a>重新计算单个形状的值

1. 从上面的两个示例的代码替换 (更改形状的文本和调用`SaveXDocumentToPart`) 中**将 Program**类 （ **Using**块的**Main**方法中**Module1**中的**Main**方法中的**使用**块在 Visual Basic) 替换为以下代码。 
    
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
  ' already have a local ThemeIndex cell.
  startEndShapeXML.Add(New XElement("Cell", _
      New XAttribute("N", "ThemeIndex"),
      New XAttribute("V", "25"),
      New XProcessingInstruction("NewValue", "V")))
  ' Save the XML back to the Page Contents part.
  SaveXDocumentToPart(pagePart, pageXML)
  
  ```

2. 选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。
    
3. 在 Visio 2013 中打开 Visio Package.vsdx 文件。 开始/结束形状现在应具有不同的填充颜色。
    
形状的颜色依赖**ThemeIndex**单元格的值，它确定其活动主题的形状继承。 在上面的示例，该形状设置为继承自不同的主题 （ **ThemeIndex**单元格设置为"25"值）。 如果您不使用处理指令，形状的文本颜色 — 这还受**ThemeIndex**单元格 — 不重新计算。 形状的填充颜色将更改为白色，但它的文本将保持白色 — 文本保持不可读。 此外，处理指令中，不是可能的 Visio 可能形状更新以后，让文件保留在其中无法出现不可预测更新形状的格式值不稳定状态。 
  
如果更改需要重新计算 （例如，更改连接的形状的位置，因此，强制重排连接线），该文档的 Visio 文件中的数据您必须将重新计算指令添加到 Visio 文件。 创建指令添加到 Visio 文件程序包的自定义文件属性部件 XML**属性**元素的**name**属性值为"RecalcDocument"。 作为最佳实践，您应检查以确保"RecalcDocument"指令已经尚未已注册的文件中的自定义文件属性部分。 
  
使用下面的代码从上面的示例更改开始/结束形状的**PinY**单元格的值。 该代码选择使用其**N**属性的值为**XElement**对象包含**PinY**单元格数据的**单元格**元素。 然后，代码将重新计算指令添加到自定义文件属性部分中的 Visio 文件。 
  
> [!NOTE]
> 此代码依赖`GetPackagePart`和`SaveXDocumentToPart`先前创建的方法。 
  
### <a name="to-recalculate-the-entire-document-when-it-is-opened"></a>打开文档时重新计算整个文档

1. 后`SaveXDocumentToPart` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。 
    
  ```cs
  private static void RecalcDocument(Package filePackage)
  {
      // Get the Custom File Properties part from the package and
      // and then extract the XML from it.
      PackagePart customPart = GetPackagePart(filePackage, 
          "https://schemas.openxmlformats.org/officeDocument/2006/relationships/" + 
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
              "https://schemas.openxmlformats.org/officeDocument/2006/" + _
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

2. 后`RecalcDocument` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。 
    
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

3. 将 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中的前一示例代码替换为以下代码。 
    
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

4. 选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。
    
5. 在 Visio 2013 中打开 Visio Package.vsdx 文件。 
    
“开始/结束”形状现在应该距离绘图底部 2 英寸。“开始/结束”形状和“流程”形状之间的连接器应该已经重新路由以适应布局变更。如果 **RecalcDocument** 属性尚未添加到文件中，形状位置可能已更改，但连接器尚未重新路由到形状的新位置。 
  
## <a name="add-a-new-package-part-to-a-package"></a>向包中添加新的包部件
<a name="vis15_ManipulateFF_AddNewPart"> </a>

修改文件包的最常见方案之一将新文档部件添加到包中。 例如，如果您想要将页面添加到 Visio 绘图通过将内容添加到包，您需要将页面内容部件添加到包。 
  
向文件包中添加新部件的过程非常简单： 
  
1. 您使用 **PackagePart** 的数据创建 XML 文档。您需要特别注意用于管理所创建的特定 XML 文档类型的方案的 XML 命名空间。
    
2. 您创建一个新文件以包含 XML 并将文件保存到 **Package** 中的某个位置。
    
3. 您在新 **PackagePart** 和 **Package** 或其他 **PackagePart** 对象之间创建必要的关系。 
    
4. 您更新引用新部件所需的任何现有部件。例如，如果您在文件中添加新的页面内容部件（一个新页面），则您还需要更新页面索引部件（/visio/pages/pages.xml 文件），以包含关于新页面的正确信息。
    
使用以下过程在 Visio 文件中创建新的功能区可扩展部件。 新的功能区可扩展部件向功能区添加新选项卡与包含一个按钮的单个组。
  
### <a name="to-create-a-new-package-part"></a>创建新的包部件

1. 后`CheckForRecalc`中前面的过程中，**程序**类 （或在 Visual Basic 中的**模块 1** ） 方法添加以下方法。 
    
  ```cs
  private static XDocument CreateCustomUI()
  {
      // Add a new Custom User Interface document part to the package.
      // This code adds a new CUSTOM tab to the ribbon for this
      // document. The tab has one group that contains one button.
      XNamespace customUINS = 
          "https://schemas.microsoft.com/office/2006/01/customui";
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
          "https://schemas.microsoft.com/office/2006/01/customui"
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

2. 后`CreateCustomUI` **Program**类 （或在 Visual Basic 中的**模块 1** ） 从上一步中方法添加以下方法。 
    
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

3. 将 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中的所有代码替换为以下代码。 
    
  ```cs
  // Create a new Ribbon Extensibility part and add it to the file.
  XDocument customUIXML = CreateCustomUI();
  CreateNewPackagePart(visioPackage, customUIXML, 
      new Uri("/customUI/customUI1.xml", UriKind.Relative),
      "application/xml",
      "https://schemas.microsoft.com/office/2006/relationships/ui/extensibility");
  ```

  ```vb
  ' Create a new Ribbon Extensibility part and add it to the file.
  Dim customUIXML As XDocument = CreateCustomUI()
  CreateNewPackagePart(visioPackage, customUIXML, _
      New Uri("/customUI/customUI1.xml", UriKind.Relative), _
      "application/xml", _
      "https://schemas.microsoft.com/office/2006/relationships/ui/extensibility")
  ```

4. 选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。
    
5. 在 Visio 2013 中打开 Visio Package.vsdx 文件，然后选择**自定义**选项卡。 
    
自定义功能区类似于图 2 中，在 Visio 2013 中打开该文件时。
  
 **图 2。在 Visio 2013 功能区中的自定义选项卡**
  
![功能区中的自定义选项卡](media/vis15_CustomRibbonTab.PNG)
  
创建 XML`CreateCustomUI`方法如下所示。 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<customUI xmlns="https://schemas.microsoft.com/office/2006/01/customui">
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

## <a name="acknowledgements"></a>鸣谢
<a name="vis15_ManipulateFF_Ackn"> </a>

我们要识别的贡献和 Visio 的 MVP**所有 Edlund**创建本技术文章中包含的代码示例中的输入。 所有操作的 Visio 文件格式，包括 Visio XML 绘图格式 (.vdx) 和新的 Visio 文件格式 (.vsdx) 识别的专家。 所有创建了以编程方式浏览 Visio 文件格式的项目，并公开内的结构。 
  
有关所有的使用 Visio 文件格式的详细信息，请参阅后面的其他资源部分中的链接。
  
## <a name="see-also"></a>另请参阅
<a name="vis15_ManipulateFF_Additional"> </a>

- Al Edlund：
    
  - 在 CodePlex 上的[pkgVisio-Visio 2013 XML 操作](https://pkgvisio.codeplex.com/documentation)项目。 
    
  - [pkgVisio_pt1](https://www.youtube.com/watch?v=7LvDKJuP9oQ&amp;feature=youtu.be) YouTube 上的视频。 
    
  - [pkgVisio_pt2](https://www.youtube.com/watch?v=ZIWSXhNSkG8&amp;feature=youtu.be) YouTube 上的视频。 
    
- [Visio 开发中心](https://msdn.microsoft.com/office/aa905478.aspx)
    
- [操作 Office Open XML 格式文档](https://msdn.microsoft.com/library/aa982683%28v=office.12%29.aspx)
    
- [创建包含命名空间 (C#) (LINQ to XML) 的文档](https://msdn.microsoft.com/library/bb387075.aspx)
    
- [在不启动 Microsoft Office 的情况下向文档中添加自定义 XML 部件](https://msdn.microsoft.com/library/bb608597%28VS.90%29.aspx)
    

