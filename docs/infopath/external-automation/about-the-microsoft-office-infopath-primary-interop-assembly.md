---
title: 有关 Microsoft Office InfoPath 主互操作程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2007 主互操作程序集，InfoPath 主互操作程序集，Pia [InfoPath 2007]，主互操作程序集 [InfoPath 2007]
localization_priority: Normal
ms.assetid: 1b3ae03c-6951-49e4-a489-4712d3f7ba72
description: 若要支持使用托管代码如 Visual C# 和 Visual Basic 的语言的 InfoPath 解决方案的创建，InfoPath 安装程序中的.NET 可编程性支持选项，请安装三个互操作程序集。
ms.openlocfilehash: b6b37254773d758dc064e22045d68f29febe7bbe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773881"
---
# <a name="about-the-microsoft-office-infopath-primary-interop-assembly"></a>有关 Microsoft Office InfoPath 主互操作程序集

作为公开作为 COM 接口的外部自动化其可编程性接口的组件对象模型 (COM) 应用程序生成 InfoPath 应用程序。 若要支持使用托管代码如 Visual C# 和 Visual Basic 的语言的 InfoPath 解决方案的创建，InfoPath 安装程序中的 **.NET 可编程性支持**选项，请安装三个互操作程序集。 互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。 
  
InfoPath 安装的三个互操作程序集的文件命名为：
  
- Microsoft.Office.Interop.InfoPath.dll
    
- Microsoft.Office.Interop.InfoPath.SemiTrust.dll
    
- Microsoft.Office.Interop.InfoPath.Xml.dll
    
本主题讨论通过 Microsoft.Office.Interop.InfoPath 互操作程序集，以独占方式的外部自动化代码用于公开的对象模型。 有关信息 Microsoft.Office.Interop.InfoPath.SemiTrust 程序集，用于以独占方式编写和运行托管的代码的 InfoPath 表单模板 (.xsn) 内从运行，请参阅[InfoPath 2003 兼容对象模型](http://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx)。
  
## <a name="important-installation-information"></a>重要安装信息

InfoPath 安装程序的默认安装选项安装 Microsoft.Office.Interop.InfoPath 的程序集在全局程序集缓存 (GAC)，可以查看的内容，从 C:\Windows\Assembly 文件夹 （或在 C:\Windows\assembly\GAC_MSIL 直接查看文件系统时)。 此程序集被称为"Microsoft Office InfoPath 主互操作程序集"这通常用于结合 Microsoft.Office.Interop.InfoPath.Xml 程序集，也在 GAC 中安装，以自动执行 InfoPath 应用程序使用托管的代码的外部应用程序。 有关 Microsoft.Office.Interop.InfoPath.Xml 程序集的信息，请参阅[有关 InfoPath XML 互操作程序集](about-the-infopath-xml-interop-assembly.md)。
  
如果 Microsoft.Office.Interop.InfoPath 程序集不是在 GAC 中可见的您应确认 InfoPath 已正确安装。 默认情况下，安装程序中的 **.NET 可编程性支持**选项设置为**从本机运行**只要.NET Framework 1.1 版可再发行软件包、.NET Framework 1.1 软件开发工具包 (SDK) 或更高版本的.NET framework运行安装程序之前安装。 如果这些互操作程序集不可用您的计算机上，您必须确认.NET Framework 1.1 或更高版本安装，则，然后使用**程序和功能**从**控制面板**通过设置 **.NET 可编程性更改安装程序支持**下为**从本机运行** **Microsoft Office InfoPath**选项。
  
下载.NET Framework 1.1 版可再发行软件包的信息，请参阅[.NET Framework 1.1 版可再发行软件包](http://msdn.microsoft.com/netframework/technologyinfo/redist/default.aspx)。
  
## <a name="the-microsoftofficeinteropinfopath-namespace"></a>Microsoft.Office.Interop.InfoPath Namespace

尽管编写的过程管理给定任务的代码是非常类似于执行相同的应用程序或 JScript 中，查看**Microsoft.Office.Interop.InfoPath**时公开的对象模型使用如 Visual Basic 语言的任务从**对象浏览器**在 Microsoft Visual Studio 中的命名空间查找复杂。 这是因为使用.NET Framework 的互操作性要求公开的所有公共接口，以及所需的.NET Framework 本身某些其他构造 COM 服务器。 有关如何及使用原因互操作程序集公开的对象模型显示更复杂的详细信息，请参阅[InfoPath 2003 兼容对象模型](http://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx)主题的"如何 COM 对象是公开为托管代码"部分。 
  
### <a name="using-intellisense"></a>使用 IntelliSense

本节中的示例假定您已建立 Microsoft.Office.Interop.InfoPath 和 Microsoft.Office.Interop.InfoPath.Xml 程序集的引用。 有关如何设置引用和其他外部自动化示例的信息，请参阅[外部自动化方案和示例](external-automation-scenarios-and-examples.md)。
  
外部自动化代码中使用 Microsoft 智能感知语句结束之前，必须创建[Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx)类的实例的对象变量，如下面的代码行所示。 
  
```cs
Application myApp = 
    new Microsoft.Office.Interop.InfoPath.Application();
```

```vb
Dim myApp As Application = _
    New Microsoft.Office.Interop.InfoPath.Application()
```

创建对象变量后, 键入跟一个句点，变量名称时下拉列表将显示**应用程序**类的成员的选择。 
  
若要使用 InfoPath 表单，声明类型[XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocument.aspx) ，对象变量，然后将其初始化通过从**Application**对象的变量中下面的代码行所示的[XDocuments](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocuments.aspx)集合中打开窗体。 
  
```cs
XDocument myXDoc = myApp.XDocuments.Open(
    "c:\\temp\\Form1.xml",
    (int) XdDocumentVersionMode.xdFailOnVersionOlder);
```

```vb
Dim myXDoc As XDocument = myApp.XDocuments.Open( _
    "c:\\temp\\Form1.xml", _
    XdDocumentVersionMode.xdFailOnVersionOlder)
```

键入一段时间后跟变量的名称时，将显示**XDocument**类的成员的 IntelliSense 语句完成下拉列表。 
  
若要使用的窗体使用 Microsoft XML Core Services (MSXML) 的基础 XML 文档的内容，您必须创建[IXMLDOMDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Xml.IXMLDOMDocument2.aspx) ，类型的变量，然后使用**XDocument**类的[DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._XDocument2.DOM.aspx)属性分配 XML文档对象模型 (DOM) 的窗体给该变量。 
  
```cs
IXMLDOMDocument2 doc= myXDoc.DOM as IXMLDOMDocument2;
```

```vb
Dim doc As IXMLDOMDocument2 = myXDoc.DOM
```

当键入跟一个句点，以便您可以使用 MSXML 来处理 XML 文档变量的名称时，将显示**IXMLDOMDocument2**类的成员的 IntelliSense 语句完成下拉列表。 
  
### <a name="using-the-class-library-reference-documentation"></a>使用类库引用文档

[Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.aspx)命名空间类库参考文档的组织反映 coclass 接口和它们实现的继承的接口之间的关系。 
  
当打开一个 coclass 接口，[应用程序](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx)，如主题的链接到的主题的开头的接口说明 coclass 接口的成员将显示空主题。 若要显示由 coclass 接口实现的成员的列表，必须打开由 coclass 继承的最新接口的主题，然后打开其成员表。 将在 coclass 接口主题中"备注"一节的开头提供指向继承接口的链接。 
  
当您在 Visual Studio 代码编辑器中按 F1 时，行为类似，只是在其调用 F1 帮助的成员将直接显示，因为您最常使用接口的成员。 但实际上可以从版本控制接口实现成员，第一次遇到这种情况时可能容易混淆。 例如，如果键入  `myXDocument.UI.Alert`，然后将光标放在  `Alert` 上并按 F1，则将显示标题为"UI2.Alert 方法"的主题。 这是因为 **Alert** 方法是 **UI2** 接口的成员的实现。 
  
### <a name="passing-optional-parameters-to-infopath-object-model-members"></a>将可选参数传递给 InfoPath 对象模型成员

如果 InfoPath 对象模型成员包含可选参数，并且您不指定该参数的值，您必须通过该参数的**Type.Missing**字段。 如果在忽略实际值时未能传递 **Type.Missing** 域，将会导致生成错误。 这是用 C# 和 Visual Basic 编写的代码，则返回 true。 例如， [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.View2.SelectNodes.aspx) 接口的 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ViewObject.aspx) 方法包含两个可选参数：  _varEndNode_ 和  _varViewContext_。 如果某代码行未指定这些可选参数的实际值，则会发生类似如下示例的情况。
  
```cs
myXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing);
```

```vb
myXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing)
```

## <a name="see-also"></a>另请参阅

- [外部自动化方案和示例](external-automation-scenarios-and-examples.md)

