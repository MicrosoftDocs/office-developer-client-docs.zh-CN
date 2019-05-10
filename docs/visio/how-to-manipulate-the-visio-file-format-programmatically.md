---
title: 以编程方式处理 Visio 文件格式
manager: soliver
ms.date: 04/17/2019
ms.audience: Developer
ms.topic: overview
ms.assetid: 5f5e2288-7539-41b8-916d-410be028ed9b
description: 在 Visual Studio 2012 中创建解决方案以读取 Visio 2013 中的新文件格式包、选择包中的部件、更改部件中的数据以及向包中添加新部件。
localization_priority: Priority
ms.openlocfilehash: 2b031a74fa8d2df9b9baa15e97652b8d8afdaf23
ms.sourcegitcommit: 6f3f42b656afb45a0189a0ad4c81c095e285b3d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "33655609"
---
# <a name="manipulate-the-visio-file-format-programmatically"></a>以编程方式处理 Visio 文件格式

![操作方法主题](media/mod_icon_howto.png)
  
了解如何在 Visual Studio 2012 中创建解决方案以读取 Visio 2013 中的新文件格式包、选择包中的部件、更改部件中的数据以及向包中添加新部件。
   
## <a name="visio-file-format-manipulation-essentials"></a>Visio 文件格式操作基础知识
<a name="vis15_ManipulateFF_Essentials"> </a>

以前版本的 Visio 以专有二进制文件格式 (.vsd) 或单文档 Visio XML 绘图文件格式 (.vdx) 保存文件。 Visio 2013 引入了一种新的文件格式 (.vsdx)，它基于 XML 和 ZIP 存档技术。 与以前版本的 Visio 一样，文件保存在单个容器中。 但是，与旧版文件不同，可以在未自动化 Visio 2013 应用程序的情况下打开、读取、更新、更改和构建新的文件格式。 熟悉操作 XML 或使用 [System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx) 命名空间的开发人员可以快速开始以编程方式处理新的文件格式。 使用以前版本的 Visio XML 绘图格式的开发人员会发现该格式的许多结构都以新的文件格式保留。 
  
在本文中，我们将介绍如何使用 Microsoft .NET Framework 4.5、C# 或 Visual Basic 以及 Visual Studio 2012，以编程方式处理 Visio 2013 文件格式。 你将了解如何打开 Visio 2013 文件、选择文件中的文档部件、更改部件中的数据以及创建新的文档部件。
  
> [!NOTE]
> 本文中的代码示例假定你对 [System.Xml.Linq](https://msdn.microsoft.com/library/System.Xml.Linq.aspx) 和 [System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx) 命名空间中的类有一个基本的了解。 > 本文还假定你了解开放打包约定的概念和术语。 你应该熟悉包、文档部件或包部件及关系的概念。 有关详细信息，请参阅 [OPC：打包数据的新标准](https://msdn.microsoft.com/magazine/cc163372.aspx)。 > 该代码演示如何创建用于选择 XML 的 LINQ（语言集成查询）查询。 大多数代码示例都使用查询语法来构建 LINQ 查询。 如有必要，可以使用 LINQ 方法语法重写代码中提供的任何 LINQ 查询。 有关LINQ查询语法和方法语法的详细信息，请参阅 [LINQ 查询语法与方法语法 (C#)](https://msdn.microsoft.com/library/bb397947.aspx)> 表 1显示在阅读本文之前应该熟悉的基本主题。 
  
**表 1. 操作 Visio 2013 文件格式的核心概念**

|**文章标题**|**说明**|
|:-----|:-----|
|[Visio 文件格式 (.vsdx) 简介](introduction-to-the-visio-file-formatvsdx.md) <br/> |此高级概述介绍了 Visio 2013 文件格式的一些主要功能。 它讨论了开放打包约定 (OPC)，因为它们已应用于 Visio 2013 文件格式。 它还列出了 Visio 2013 文件格式与以前的 Visio XML 绘图文件格式 (.vdx) 之间的一些差异。  <br/> |
|[OPC：打包数据的新标准](https://msdn.microsoft.com/magazine/cc163372.aspx) <br/> |此 MSDN 杂志文章将开放打包约定作为概念进行介绍。  <br/> |
|[开放打包约定的基础知识](https://msdn.microsoft.com/library/ee361919.aspx) <br/> [Office (2007) Open XML 文件格式](https://msdn.microsoft.com/library/aa338205.aspx) <br/> |以下两篇文章讨论了如何将开放打包约定应用于 Microsoft Office 文件。 它们提供了有关包中关系的工作方式的说明，并且包含一些代码示例。  <br/> |
   
## <a name="create-a-vsdx-file-and-a-new-visual-studio-solution"></a>创建 .vsdx 文件和新的 Visual Studio 解决方案
<a name="vis15_ManipulateFF_CreateFile"> </a>

在开始执行本文中的过程之前，你需要创建一个可以打开和操作的 Visio 2013 文件。 本文的代码示例中使用的绘图包含一页，上面具有两个连接的形状，其中一个是“基本流程图”模板中的“开始/结束”形状。
  
使用以下过程创建一个新的 Visio 2013 文件，以便在本文中的其余步骤中使用。
  
### <a name="to-create-new-file-in-visio-2013"></a>在 Visio 2013 中创建新文件

1. 打开 Visio 2013。
    
2. 基于“基本流程图”模板创建一个新文档，方法是依次选择“**类别**、“**流程图**”、“**基本流程图**”、“**创建**”。
    
3. 从“**形状**”窗口中，将“**开始/结束**”形状拖放到画布上。 
    
4. 在画布上选择新的“开始/结束”形状，并键入“Begin Process”。
    
5. 从“**形状**”窗口中，将“**流程**”形状拖放到画布上。 
    
6. 在画布上选择新的“流程”形状，并键入“Perform some task”。
    
7. 在“开始/结束”形状的快捷菜单中，选择“**向页面添加一个连接器**”，然后在画布上的“开始/结束”形状和“流程”形状之间绘制一个连接器，如图 1 中所示。
    
    **图 1. 简单 Visio 2013 绘图**
    
     ![与进程形状连接的头部/尾部形状](media/vis15_SimpleFlowchart.png)
  
8. 将文件作为 .vsdx 文件保存到桌面上，方法是依次选择“**文件**”、“**另存为**”、“**计算机**”、“**桌面**”。
    
    在“**另存为**”对话框中，在“**文件名**”框中输入 Visio Package，在“**保存类型**”列表中选择“**Visio 绘图 (\*.vsdx)**”，然后选择“**保存**”按钮。 
    
9. 关闭文件，然后关闭 Visio 2013。
    
> [!TIP]
> 有时即使文件有一些问题，Visio 也可以成功打开它。 若要确保 Visio 向你通知任何文件问题，你应该在测试在文件包级别操作 Visio 文件的解决方案时，启用文件打开警告。 > 若要启用文件打开警告，请在 Visio 2013 中依次选择“**文件**”、“**选项**”和“**高级**”。 在“**保存/打开**”下方，选择“**显示文件打开警告**”。 
  
这些过程使用 Windows 控制台应用程序来操作“Visio Package.vsdx”文件。 使用以下过程在 Visual Studio 2012 中创建和设置新的 Windows 控制台应用程序。
  
### <a name="to-create-a-new-solution-in-visual-studio-2012"></a>在 Visual Studio 2012 中创建新的解决方案

1. 在“**文件**”菜单上，依次选择“**新建**”、“**项目**”。
    
2. 在“**新建项目**”对话框中，展开“**Visual C#**”或“**Visual Basic**”，然后依次选择“**Windows**”、“**控制台应用程序**”。
    
    在“**名称**”框中，输入“VisioFileAccessor”，为项目选择一个位置，然后选择“**确定**”按钮。 
    
3. 在"**项目**"菜单上，选择"**添加引用**"。 
    
    在“**引用管理器**”对话框中的“**程序集**”下，选择“**框架**”，然后添加对“**System.Xml**”和“**WindowsBase**”组件的引用。 
    
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

## <a name="open-a-visio-2013-file-as-a-package"></a>将 Visio 2013 文件作为包打开
<a name="vis15_ManipulateFF_OpenPackage"> </a>

在操作文件中的任何数据之前，需要先在 [Package](https://msdn.microsoft.com/library/System.IO.Packaging.Package.aspx) 对象中打开该文件，该对象包含在 [System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx) 命名空间中。 **Package** 对象表示整个 Visio 文件。 它公开可让你在文件包中选择各个文档部件的成员。 特别是，**Package** 类公开用于将文件作为包打开的静态 [Open(String, FileMode, FileAccess)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.Open.aspx) 方法。 它还公开用于在完成后立即关闭包的 [Close()](https://msdn.microsoft.com/library/System.IO.Packaging.Package.Close.aspx) 方法。 
  
> [!TIP]
> 最佳做法是使用 **using** 块在 **Package** 对象中打开 Visio 文件，这样你就不必在完成后立即关闭文件包。 你还可以在 **try/catch/finally** 构造的 **finally** 块中显式调用 **Package.Close** 方法。 
  
使用以下代码，通过 [FileInfo](https://msdn.microsoft.com/library/System.IO.FileInfo.aspx) 对象获取“Visio Package.vsdx”文件的完整路径，将路径作为参数传递到 **Package.Open** 方法，然后向调用代码返回一个 **Package** 对象。 
  
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

将 Visio 2013 文件作为包打开后，可以使用 **System.IO.Packaging** 命名空间中包含的 [PackagePart](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePart.aspx) 类访问其中的文档部件。 **PackagePart** 对象可以单独实例化，也可以作为集合实例化。 **Package** 类公开 [GetParts()](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetParts.aspx) 方法和 [GetPart(Uri)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetPart.aspx) 方法，用于从 **Package** 中获取 **PackagePart** 对象。 **Package.GetParts** 方法将返回 [PackagePartCollection](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePartCollection.aspx) 类的实例，随后你可以像实现 [IEnumerator\<T\>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerator-1?redirectedfrom=MSDN&view=netframework-4.7.2) 接口的任何其他集合那样进行交互。 
  
使用以下过程中的代码，作为一个整体从 **Package** 中获取 **PackagePartCollection** 对象，循环访问集合中的 **PackagePart** 对象，并将每个 **PackagePart** 的 URI 和内容类型写入到控制台中。 
  
### <a name="to-iterate-through-the-package-parts-in-a-package"></a>循环访问包中的包部件

1. 在 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `OpenPackage` 方法后面，添加以下代码。 
    
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
  
通常，你需要选择一个 **PackagePart**，而无需循环访问所有部件。 你可以使用它与 **Package** 或另一个 **PackagePart** 的关系，从 **Package** 中获取 **PackagePart** 对象。 Visio 2013 文件格式中的关系是一个离散实体，它描述了文档部件与文件包之间有何关联，以及两个文档部件之间相互有何关联。 例如，Visio 2013 文件包本身与其 Visio 文档部件存在关系，Visio 文档部件与 Windows 部件存在关系。 这些关系表示为 [PackageRelationship](https://msdn.microsoft.com/library/System.IO.Packaging.PackageRelationship.aspx) 或 [PackageRelationshipCollection](https://msdn.microsoft.com/library/System.IO.Packaging.PackageRelationshipCollection.aspx) 类的实例。 
  
**Package** 类公开几种用于获取其中包含的作为 **PackageRelationship** 或 **PackageRelationshipCollection** 对象的关系的方法。 你可以使用 [GetRelationshipsByType(String)](https://msdn.microsoft.com/library/System.IO.Packaging.Package.GetRelationshipsByType.aspx) 方法，对包含单一特定类型的 **PackageRelationship** 对象的 **PackageRelationshipCollection** 对象进行实例化。 当然，使用 **Package.GetRelationshipsByType** 方法要求你已经知道所需的关系类型。 关系类型是采用 XML 命名空间格式的字符串。 例如，Visio 文档部件的关系类型为 http://schemas.microsoft.com/visio/2010/relationships/document。 
  
一旦您知道 **PackagePart** 与 **Package** 或与另一个 **PackagePart** 的关系（即，您有一个 **PackageRelationship** 对象引用所需的 **PackagePart**），即可使用此关系获取该 **PackagePart** 的 URI。然后您可以将 URI 传递到 **Package.GetPart** 方法以返回 **PackagePart**。
  
> [!NOTE]
> 你还可以获取对特定 **PackagePart** 的引用，方法是仅使用 **Package.GetPart** 方法和 **PackagePart** 的 URI，跳过获取文件包部件的关系的步骤。 但是，Visio 文件包中的某些包部件可以保存到包中默认位置以外的位置。 你不能假定包部件始终位于与每个文件相同的 URI。 > 相反，最佳做法是使用关系访问单个 **PackagePart** 对象。 
  
使用以下过程获取 **PackagePart**（Visio 文档部件），方法是使用引用该部件的 **Package** 中的 **PackageRelationship**。 
  
### <a name="to-select-a-specific-package-part-in-the-package-by-relationship"></a>按关系选择包中的特定包部件

1. 在 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `IteratePackageParts` 方法后面，添加以下方法。 
    
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
        "http://schemas.microsoft.com/visio/2010/relationships/document");
    
    ```

    ```vb
    ' Get a reference to the Visio Document part contained in the file package.
    Dim documentPart As PackagePart = GetPackagePart(visioPackage, _
        "http://schemas.microsoft.com/visio/2010/relationships/document")
    
    ```

如上所述，你还可以使用与其他 **PackagePart** 对象的关系获取 **PackagePart** 对象。 这一点很重要，因为对于具有任何复杂度的 Visio 文档，大多数 **PackagePart** 对象都与 **Package** 没有关系。 例如，文件包（即 /visio/pages/page1.xml）中的单个页面内容部件与页面索引部件（即 /visio/pages/pages.xml）存在关系，但与文件包本身没有关系。 如果你没有包中各个页面的确切 URI，则可以使用它与页面索引部件的关系来获取对它的引用。
  
**PackagePart** 类公开 [GetRelationshipsByType(String)](https://msdn.microsoft.com/library/System.IO.Packaging.PackagePart.GetRelationshipsByType.aspx) 方法，你可以使用此方法返回仅包含一种 **PackageRelationship** 对象的 **PackageRelationshipCollection** 对象。 当你具有 **PackageRelationshipCollection** 后，你可以从集合中选择所需的 **PackageRelationship**，然后引用 **PackagePart** 对象。 
  
使用以下代码从 **Package** 获取 **PackagePart**，方法是使用与另一个 **PackagePart** 的关系（获取 **PackageRelationship** 对象）。
  
### <a name="to-select-a-specific-package-part-through-its-relationship-to-another-package-part"></a>通过与另一个包部件的关系选择特定的包部件

1. 在 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `GetPackagePart` 方法后面，添加以下重载方法。 
    
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

在更改文档部件中包含的 XML 之前，你需要先将 XML 文档加载到一个允许你读取 XML 的对象中，方法是使用 [XDocument](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.aspx) 类或 [XmlDocument](https://msdn.microsoft.com/library/System.Xml.XmlDocument.aspx) 类。 这两个类都会公开用于以下任务的方法，例如选择 XML 文档内包含的 XML 元素；创建、读取和写入属性；在文档中插入新 XML 元素。 
  
在这两个类中，**XDocument** 类允许您使用 LINQ 查询 XML。使用 LINQ，您可以轻松地从 XML 文档中选择单个元素，方法是通过创建查询，而不是通过循环访问集合中的所有元素并测试您所需的元素。因此，本文中的后续过程将使用 **XDocument** 类以及 **System.Xml.Linq** 命名空间的其他类来处理 XML。 
  
使用以下过程，在 **XDocument** 对象中打开 **PackagePart** 作为 XML 文档。 
  
### <a name="to-read-the-xml-in-a-package-part"></a>读取包部件中的 XML

1. 在最后一次重载 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `GetPackagePart` 方法后，添加以下方法。 
    
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
  
操作 Visio 文件格式的最常见任务是选择文档中的特定 XML 元素或元素集合。 **System.Xml.Linq** 命名空间包括 [XElement](https://msdn.microsoft.com/library/System.Xml.Linq.XElement.aspx) 类，该类表示 XML 元素。 **XElement** 类使你可以访问 Visio 文件在粒度级别包含的数据，包括从单个 **Shape** 元素到 **ValidationRule** 元素（举例）。 
  
使用以下代码从 **XDocument**（包含页面内容部件）中选择 **Shape** 元素，然后选择特定的 **Shape** 元素。 
  
### <a name="to-select-a-specific-element-in-a-package-part"></a>选择包部件中的特定元素

1. 在 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `GetXMLFromPart` 方法后面，添加以下方法。 
        
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

2. 在前一步中 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `GetXElementsByName` 方法后面，添加以下方法。 
    
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

获得对包含在 **XDocument** 对象内的 **XElement** 对象的引用后，即可像任何其他 XML 数据一样对其进行操作，因此可以更改 Visio 文件中包含的数据。 例如，如果形状在 Visio 中打开时具有文本，相应的 **Shape** 元素将至少包含一个 **Text** 元素。 如果你更改该 **Text** 元素的值，则在 Visio 中查看文件时，将会更改形状的文本。 
  
在 **Program** 类的 **Main** 方法中的 **using** 块（在 Visual Basic 中为 **Module1** 中 **Main** 方法的 **Using** 块）中添加以下代码，将“开始/结束”形状中的文本从“Begin process”更改为“Start process”。 
  
```cs
// Query the XML for the shape to get the Text element, and
// return the first Text element node.
IEnumerable<XElement> textElements = from element in startEndShapeXML.Elements()
                               where element.Name.LocalName == "Text"
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
    Where element.Name.LocalName == "Text"
    Select element
Dim textElement As XElement = textElements.ElementAt(0)
' Change the shape text, leaving the <cp> element alone.
textElement.LastNode.ReplaceWith("Start process")

```

> [!CAUTION]
> 在前一代码示例中，现有形状文本和用于替换它的字符串具有相同的字符数。 另外请注意，LINQ 查询将更改所返回元素的最后一个子节点（在本示例中为文本节点）的值。 这样做是为了避免更改 **cp** 元素（这是 **Text** 元素的子元素）的设置。 > 如果你覆盖了 **Text** 元素的所有子元素，以编程方式更改形状文本，可能导致文件不稳定。 与在上述示例中一样，文本格式使用文件中 **Text** 元素下的 **cp** 元素来表示。 格式的定义存储在父 **Section** 元素中。 如果这两项信息变得不一致，文件可能无法按预期使用。 Visio 存在很多不一致，但这可以更好地确保任何编程更改一致，以便控制文件的最终行为。 
  
当您对文档部件的 XML 进行更改时，这些更改仅存在于内存中。要将更改保留在文件中，您必须将 XML 保存回文档部件。
  
以下代码使用 [XmlWriter](https://msdn.microsoft.com/library/System.Xml.XmlWriter.aspx) 类和 [XmlWriterSettings](https://msdn.microsoft.com/library/System.Xml.XmlWriterSettings.aspx) 类将 XML 写入回包部件。 尽管你可以使用 [Save()](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.Save.aspx) 方法将 XML 保存回部件中，**XmlWriter** 和 **XmlWriterSettings** 类将允许你更好地控制输出，包括指定编码类型。 **XDocument** 类公开 [WriteTo(XmlWriter)](https://msdn.microsoft.com/library/System.Xml.Linq.XDocument.WriteTo.aspx) 方法，此方法将提取 **XmlWriter** 对象并将 XML 写回到流中。 
  
使用以下过程将 Visio 页中的 XML 保存回页面内容部件。
  
### <a name="to-save-the-changed-xml-back-to-the-package"></a>将已更改的 XML 保存回包中

1. 在前一步中 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `GetXElementByAttribute` 方法后面，添加以下方法。 
    
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

对文件中的数据进行某些更改可能需要 Visio 在打开文件时重新计算文档。 Visio 为图提供了大量逻辑，尤其是形状关系（即当一个形状依赖于另一个形状时）和连接形状。 如果自定义逻辑所依赖的任何数据发生更改，Visio 需将更改传播到文件中所有受影响的计算数据。 
  
Visio 2013 文件格式包括多种用于重新计算文件中数据的技术。 当你决定是否需要重新计算 Visio 文件以及如何重新计算时，必须考虑三种类型的方案：
  
- 对数据的更改不会影响文件格式中的任何其他值。 你不需要添加到有关 Visio 重新计算文档的任何其他说明。 如上所述，你可以经常更改形状的文本，而无需重新计算文档。
    
- 对数据的更改仅限于更改 XML 中 ShapeSheet 单元格的值，并且有其他 ShapeSheet 值依赖于此数据。 在这种情况下，你必须将 XML 处理指令（使用 [XProcessingInstruction](https://msdn.microsoft.com/library/System.Xml.Linq.XProcessingInstruction.aspx) 类）添加到已更改的 **Cell** 元素。 例如，形状的 **ThemeIndex** 单元格会影响形状中包含的多个其他 ShapeSheet 单元格的值。 如果你更改文件本身的 **ThemeIndex** 单元格（例如，**N** 值为“ThemeIndex”的 **Cell** 元素），你将需要将处理指令添加到 **Cell** 元素以更新相关值。 
    
- 对数据的更改会影响连接器或连接点的位置。 另一种情况是，当对 ShapeSheet 数据进行了很多更改，并且你需要使用一条指令重新计算整个文档（而不是添加对每个更改的单个处理指令）时。 在这种情况下，你可以指示 Visio 在打开文档时重新计算整个文档。 你可以通过将 **RecalcDocument** 属性添加到 Visio 包的“自定义文件属性”部分 (/docProps/custom.xml) 来执行此操作。 此类方案的示例包括调整连接图中形状的位置或大小。 
    
    请记住，从性能的角度看，这是成本最高的选项。
    
使用以下过程将 **Cell** 元素插入到 **Shape** 元素中，由于新值，需要重新计算相同 **Shape** 中的其他 **Cell** 元素。 新的 **Cell** 元素包括处理指令作为子元素，以通知 Visio 需要执行一些本地重新计算。 
  
### <a name="to-recalculate-values-for-a-single-shape"></a>重新计算单个形状的值

1. 将 **Program** 类的 **Main** 方法中 **using** 块中的前两个示例（更改形状的文本并调用 `SaveXDocumentToPart`）代码（在 Visual Basic 中，为 **Module1** 中 **Main** 方法的 **Using** 块）替换为以下代码。 
    
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
    
3. 在 Visio 2013 中打开 Visio Package.vsdx 文件。 “开始/结束”形状现在应该为不同的填充颜色。
    
形状的颜色依赖于 **ThemeIndex** 单元格的值—它确定了形状从哪些活动主题中继承。 在前一示例中，形状设置为从不同主题继承（**ThemeIndex** 单元格设置为值“25”）。 如果你不使用处理指令，将不会重新计算形状的文本颜色—它还会受 **ThemeIndex** 单元格影响。 形状的填充颜色将更改为白色，但其文本仍保留为白色，这会使文本不可读。 此外，如果没有处理指令，Visio 可能会稍后再更新形状，这会使文件处于不稳定状态，导致形状的格式值不可预见地更新。 
  
如果对文件中的数据更改需要 Visio 重新计算文档（例如，更改连接形状的位置，从而强迫连接器重新路由），则必须在向 Visio 文件添加重新计算指令。 指令可通过以下方式创建：将 **name** 属性值为“RecalcDocument”的 **property** 元素添加到 Visio 文件包的“自定义文件属性”部分的 XML 中。 作为最佳做法，你应该检查“自定义文件属性”部分，确保“RecalcDocument”指令尚未在文件中注册。 
  
使用以下代码更改之前示例中“开始/结束”形状的 **PinY** 单元格的值。 代码使用其 **N** 属性的值，选择 **Cell** 元素，其中包含 **PinY** 单元格数据作为 **XElement** 对象。 然后代码将重新计算指令添加到 Visio 文件的“自定义文件属性”部分。 
  
> [!NOTE]
> 此代码依赖于之前创建的 `GetPackagePart` 和 `SaveXDocumentToPart` 方法。 
  
### <a name="to-recalculate-the-entire-document-when-it-is-opened"></a>打开文档时重新计算整个文档

1. 在前一步中 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `SaveXDocumentToPart` 方法后面，添加以下方法。 
    
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

2. 在前一步中 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `RecalcDocument` 方法后面，添加以下方法。 
    
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

修改文件包的一个常见方案是向包中添加新的文档部件。 例如，如果你想通过向包中添加内容来向 Visio 绘图添加页面，你需要将页面内容部件添加到包。 
  
向文件包中添加新部件的过程非常简单： 
  
1. 您使用 **PackagePart** 的数据创建 XML 文档。您需要特别注意用于管理所创建的特定 XML 文档类型的方案的 XML 命名空间。
    
2. 创建一个新文件以包含 XML 并将文件保存到 **Package** 中的某个位置。
    
3. 在新 **PackagePart** 和 **Package** 或其他 **PackagePart** 对象之间创建必要的关系。 
    
4. 您更新引用新部件所需的任何现有部件。例如，如果您在文件中添加新的页面内容部件（一个新页面），则您还需要更新页面索引部件（/visio/pages/pages.xml 文件），以包含关于新页面的正确信息。
    
使用以下过程在 Visio 文件中创建一个新的功能区可扩展性部件。 该新的功能区可扩展性部件在功能区中添加一个新的选项卡，该选项卡具有一个包含单个按钮的组。
  
### <a name="to-create-a-new-package-part"></a>创建新的包部件

1. 在前一步中 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `CheckForRecalc` 方法后面，添加以下方法。 
    
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

2. 在前一步中 **Program** 类（或 Visual Basic 中的 **Module1**）中的 `CreateCustomUI` 方法后面，添加以下方法。 
    
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

4. 选择 F5 键以调试解决方案。该程序完成运行后，选择任意键退出。
    
5. 在 Visio 2013 中打开 Visio Package.vsdx 文件，然后选择“**自定义**”选项卡。 
    
当文件在 Visio 2013 中打开时，自定义功能区将如图 2 中所示。
  
 **图 2. Visio 2013 功能区中的“自定义”选项卡**
  
![功能区中的自定义选项卡](media/vis15_CustomRibbonTab.PNG)
  
`CreateCustomUI` 方法创建的 XML 如下所示。 
  
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

## <a name="acknowledgements"></a>鸣谢
<a name="vis15_ManipulateFF_Ackn"> </a>

我们非常感谢 Visio MVP **Al Edlund** 在创建本技术文章中包含的代码示例中所做的贡献和努力。 Al 是操作 Visio 文件格式方面的公认专家，包括 Visio XML 绘图格式 (.vdx) 和新的 Visio 文件格式 (.vsdx)。 Al 创建了众多项目，用于以编程方式探索 Visio 文件格式和公开其内部结构。 
  
有关 AI 在 Visio 文件格式方面的所做工作的详细信息，请参阅后面“其他资源”部分中的链接。
  
## <a name="see-also"></a>另请参阅
<a name="vis15_ManipulateFF_Additional"> </a>

- 作者 Al Edlund：
    
  - CodePlex 上的 [pkgVisio - Visio 2013 XML 操作](https://pkgvisio.codeplex.com/documentation)项目。 
    
  - YouTube 上的 [pkgVisio_pt1](https://www.youtube.com/watch?v=7LvDKJuP9oQ&amp;feature=youtu.be) 视频。 
    
  - YouTube 上的 [pkgVisio_pt2](https://www.youtube.com/watch?v=ZIWSXhNSkG8&amp;feature=youtu.be) 视频。 
    
- [Visio 开发中心](https://msdn.microsoft.com/office/aa905478.aspx)
    
- [操作 Office Open XML 格式文档](https://msdn.microsoft.com/library/aa982683%28v=office.12%29.aspx)
    
- [创建包含命名空间的文档 (C#) (LINQ to XML)](https://msdn.microsoft.com/library/bb387075.aspx)
    
- [在不启动 Microsoft Office 的情况下向文档中添加自定义 XML 部件](https://msdn.microsoft.com/library/bb608597%28VS.90%29.aspx)
    

