---
title: 关于 Microsoft Office InfoPath 主互操作程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2007，主互操作程序集，InfoPath 主互操作程序集，PIAs [InfoPath 2007]，主互操作程序集 [InfoPath 2007]
localization_priority: Normal
ms.assetid: 1b3ae03c-6951-49e4-a489-4712d3f7ba72
description: 为了支持创建使用托管代码语言（如 Visual C# 和 Visual Basic）的 InfoPath 解决方案，InfoPath 安装程序中的 .NET 可编程性支持选项将安装三个互操作程序集。
ms.openlocfilehash: 51773ad46b1371c410c4249e13a489f0c5550cd1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310134"
---
# <a name="about-the-microsoft-office-infopath-primary-interop-assembly"></a>关于 Microsoft Office InfoPath 主互操作程序集

InfoPath 应用程序构建为组件对象模型 (COM) 应用程序，用于将可编程性接口作为 COM 接口公开用于外部自动化。 为了支持创建使用托管代码语言（如 Visual C# 和 Visual Basic）的 InfoPath 解决方案，InfoPath 安装程序中的 **.NET 可编程** 性支持选项将安装三个互操作程序集。 互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。 
  
InfoPath 安装的三个互操作程序集的文件命名为：
  
- Microsoft.Office.Interop.InfoPath.dll
    
- Microsoft.Office.Interop.InfoPath.SemiTrust.dll
    
- Microsoft.Office.Interop.InfoPath.Xml.dll
    
本主题讨论通过 Microsoft 公开的对象模型。Office.Interop.InfoPath 互操作程序集，专用于外部自动化代码。 有关 Microsoft 的信息。Office.Interop.InfoPath.SemiTrust 程序集，它专门用于编写和运行从 InfoPath 表单模板 (.xsn) 中运行的托管代码，请参阅[InfoPath 2003 Compatible Object Models。](https://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx)
  
## <a name="important-installation-information"></a>重要安装信息

InfoPath 安装程序的默认安装选项将安装 Microsoft。全局程序集缓存 (GAC) 中的 Office.Interop.InfoPath 程序集，当直接查看文件系统) 时，可以从 C：\Windows\Assembly 文件夹 (或 C：\Windows\assembly\GAC_MSIL 中查看其中的内容。 此程序集称为"Microsoft Office InfoPath 主互操作程序集"，通常与 Microsoft.Office.Interop.InfoPath.Xml 程序集（也安装在 GAC 中）结合使用，以自动执行使用托管代码的外部应用程序中的 InfoPath 应用程序。 有关该程序集Microsoft.Office.Interop.InfoPath.Xml，请参阅 [关于 InfoPath XML 互操作程序集](about-the-infopath-xml-interop-assembly.md)。
  
如果为 Microsoft。Office.Interop.InfoPath 程序集在 GAC 中不可见，您应该确认 InfoPath 安装正确。 默认情况下，只要在运行安装程序之前安装了 .NET Framework 1.1可再发行软件包、.NET Framework 1.1 软件开发工具包 (SDK) 或更高版本的 .NET Framework，安装程序中的 **.NET** 可编程性支持选项就设置为"从我的计算机运行"。 如果这些互操作程序集在你的计算机上不可用，则必须确认已安装 .NET Framework 1.1 或更高版本，然后使用控制面板中的程序和功能更改安装程序，方法为将 **Microsoft Office InfoPath** 下的 **.NET 可编程** 性支持选项设置为"从我的计算机运行 **"。**
  
有关下载 1.1 可再发行.NET Framework的信息，请参阅 .NET Framework [1.1 Redistributable。](https://www.microsoft.com/en-us/download/details.aspx?id=26)
  
## <a name="the-microsoftofficeinteropinfopath-namespace"></a>Microsoft。Office.Interop.InfoPath 命名空间

尽管为给定任务编写托管代码的过程与使用语言（如 Visual Basic for Applications 或 JScript）执行相同任务非常相似，但从 Microsoft Visual Studio 中的对象浏览器查看 **Microsoft.Office.Interop.InfoPath** 命名空间时公开的对象模型看起来更为复杂。  这是因为与 .NET Framework 的互操作性需要 COM 服务器公开其所有公共接口，以及该接口本身所需的.NET Framework构造。 有关互操作程序集公开的对象模型如何以及为什么看起来更复杂的详细信息，请参阅 [InfoPath 2003 Compatible Object Models](../form-templates/infopath-2003-compatible-object-models.md) 主题的"COM 对象如何向托管代码公开"一节。 
  
### <a name="using-intellisense"></a>使用 IntelliSense

本节中的示例假定你已建立对 Microsoft 的引用。Office.Interop.InfoPath 和 Microsoft.Office.Interop.InfoPath.Xml 程序集。 若要了解如何设置引用和其他外部自动化示例，请参阅外部 [自动化方案和示例](external-automation-scenarios-and-examples.md)。
  
在外部自动化代码中IntelliSense Microsoft 语句完成之前，您必须为[Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx)类的实例创建对象变量，如下面的代码行所示。 
  
```cs
Application myApp = 
    new Microsoft.Office.Interop.InfoPath.Application();
```

```vb
Dim myApp As Application = _
    New Microsoft.Office.Interop.InfoPath.Application()
```

创建对象变量后，当您键入变量名称后跟一个时间段时，将显示一个下拉列表，其中包含要选择的 **Application** 类的成员。 
  
若要使用 InfoPath 表单，请声明一个 [类型为 XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocument.aspx)的对象变量，然后通过从 **Application** 对象变量的 [XDocuments](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocuments.aspx)集合中打开表单来初始化它，如下面的代码行所示。 
  
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

键入IntelliSense后跟一个时间段的名称时，**将显示 XDocument** 类的成员的"IntelliSense 语句完成"下拉列表。 
  
若要使用 Microsoft XML Core Services (MSXML)  (MSXML) 处理表单的基础 XML 文档的内容，必须创建一个 [类型为 IXMLDOMDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Xml.IXMLDOMDocument2.aspx)的变量，然后使用 **XDocument** 类的 [DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._XDocument2.DOM.aspx)属性将表单的 XML 文档对象模型 (DOM) 分配给该变量。 
  
```cs
IXMLDOMDocument2 doc= myXDoc.DOM as IXMLDOMDocument2;
```

```vb
Dim doc As IXMLDOMDocument2 = myXDoc.DOM
```

当您键入变量的名称后跟一个时间段（允许您使用 MSXML 处理 XML 文档）时，将显示 **IXMLDOMDocument2** 类成员的 IntelliSense 语句完成下拉列表。 
  
### <a name="using-the-class-library-reference-documentation"></a>使用类库引用文档

[Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.aspx)命名空间类库参考文档的组织反映 coclass 接口和它们实现继承的接口之间的关系。 
  
当您打开 Coclass 接口的主题（如 [Application）](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx) 时，在本主题开头的接口说明之后，指向 coclass 接口成员的链接将显示一个空主题。 若要显示由 coclass 接口实现的成员的列表，必须打开由 coclass 继承的最新接口的主题，然后打开其成员表。 将在 coclass 接口主题中"备注"一节的开头提供指向继承接口的链接。 
  
在编辑器中按 F1 时，该行为相似，只是调用 F Visual Studio Code 1 帮助的成员将直接显示，因为你最通常使用接口的成员。 但实际上可以从版本控制接口实现成员，第一次遇到这种情况时可能容易混淆。 例如，如果键入  `myXDocument.UI.Alert`，然后将光标放在  `Alert` 上并按 F1，则将显示标题为"UI2.Alert 方法"的主题。 这是因为 **Alert** 方法是 **UI2** 接口的成员的实现。 
  
### <a name="passing-optional-parameters-to-infopath-object-model-members"></a>将可选参数传递给 InfoPath 对象模型成员

如果 InfoPath 对象模型成员包含可选参数，并且您未指定该参数的值，则必须传递该参数的 **Type.Missing** 字段。 如果在忽略实际值时未能传递 **Type.Missing** 域，将会导致生成错误。 对于同时使用 C# 和 Visual Basic 编写的代码Visual Basic。 例如， [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.View2.SelectNodes.aspx) 接口的 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ViewObject.aspx) 方法包含两个可选参数：  _varEndNode_ 和  _varViewContext_。 如果某代码行未指定这些可选参数的实际值，则会发生类似如下示例的情况。
  
```cs
myXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing);
```

```vb
myXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing)
```

## <a name="see-also"></a>另请参阅

- [外部自动化方案和示例](external-automation-scenarios-and-examples.md)

