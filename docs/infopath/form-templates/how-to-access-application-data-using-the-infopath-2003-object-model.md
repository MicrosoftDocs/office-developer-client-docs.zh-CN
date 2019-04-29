---
title: 使用 InfoPath 2003 对象模型访问应用程序数据
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- form templates [infopath 2007], accessing data using 2003 object model,InfoPath 2003-compatible form templates, accessing application data
localization_priority: Normal
ms.assetid: da604c72-c760-4aa3-9574-d59c392753df
description: InfoPath 2003 兼容对象模型所提供的对象和集合能够用于访问有关 InfoPath 应用程序的信息，其中包括有关表单的基础 XML 文档以及表单定义 (.xsf) 文件的信息。该数据通过 InfoPath 对象模型层次结构的顶级对象（该对象使用 Application 接口实例化）来访问。
ms.openlocfilehash: 849882a97109d91a5807a6798d5a62457ab971fd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437439"
---
# <a name="access-application-data-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型访问应用程序数据

InfoPath 2003 兼容对象模型所提供的对象和集合能够用于访问有关 InfoPath 应用程序的信息，其中包括有关表单的基础 XML 文档以及表单定义 (.xsf) 文件的信息。该数据通过 InfoPath 对象模型层次结构的顶级对象（该对象使用 [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 接口实例化）来访问。 
  
使用 Visual Studio 2008 创建的 InfoPath 2003 兼容托管代码表单模板项目会初始化表单代码类的  `thisApplication` 方法中的  `_Startup` 变量，此变量可用于访问 [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 接口的成员。在以下示例中， [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.Name.aspx) 接口的 [Name](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.Version.aspx) 和 [Version](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 属性用于返回 InfoPath 运行实例的名称和版本号。此信息通过使用 [UI2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 接口的 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.aspx) 方法显示在消息框中。 
  
```cs
thisXDocument.UI.Alert("Application name: " + thisApplication.Name +
   "\nApplication version: " + thisApplication.Version);
```

```vb
thisXDocument.UI.Alert("Application name: " &amp; thisApplication.Name &amp; _
   vbNewLine &amp; "Application version: " &amp; thisApplication.Version)
```

在 Visual C# 示例中，对警告消息字符串中的  `\n` 字符的引用由 InfoPath 非托管代码呈现为一个标准换行符，它会中断文本并将其置于消息框的新行中。若要明确使用为当前环境和平台定义的新行值，请改用 **Environment.NewLine** 属性，如以下示例中所示。 
  
```cs
thisXDocument.UI.Alert("Application name: " + thisApplication.Name +
   Environment.NewLine + "Application version: " + 
   thisApplication.Version);
```

## <a name="accessing-data-from-the-underlying-xml-document-of-a-form"></a>访问表单的基础 XML 文档中的数据

开发人员可以使用 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 接口访问有关表单的基础 XML 文档的信息，包括对包含表单源 XML 数据的 XML 文档对象模型 (DOM) 的引用。 
  
在以下示例中，第一个消息框显示 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 接口提供的一些数据，例如基础 XML 文档是否已更改（通过使用 [IsDirty](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.IsDirty.aspx) 属性），以及它是否已进行数字签名（使用 [IsSigned](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.IsSigned.aspx) 属性）。下一个消息框使用 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 接口的 [DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DOM.aspx) 属性显示表单的基础 XML 文档的源 XML。 
  
```cs
thisXDocument.UI.Alert("\nIsDirty: " + thisXDocument.IsDirty +
   "\nIsDOMReadOnly: " + thisXDocument.IsDOMReadOnly +
   "\nIsNew: " + thisXDocument.IsNew +
   "\nIsReadOnly: " + thisXDocument.IsReadOnly +
   "\nIsSigned: " + thisXDocument.IsSigned);
thisXDocument.UI.Alert(thisXDocument.DOM.xml);
```

```vb
thisXDocument.UI.Alert("IsDirty: " &amp; thisXDocument.IsDirty &amp; vbNewLine &amp; _
   "IsDOMReadOnly: " &amp; thisXDocument.IsDOMReadOnly &amp; vbNewLine &amp; _
   "IsNew: " &amp; thisXDocument.IsNew &amp; vbNewLine &amp; _
   "IsReadOnly: " &amp; thisXDocument.IsReadOnly &amp; vbNewLine &amp; _
   "IsSigned: " &amp; thisXDocument.IsSigned)
thisXDocument.UI.Alert(thisXDocument.DOM.xml)
```

上例中使用的 **xml** 属性是 XML 文档对象模型 (DOM) 的属性。有关 XML DOM 的详细信息，请参阅 MSXML 5.0 SDK 文档。 
  
## <a name="accessing-data-from-a-forms-form-definition-file"></a>访问表单的表单定义文件中的数据

还可以使用 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 接口访问有关表单的 .xsf 文件的信息，包括对它所包含的源 XML 数据的 XML DOM 引用。可使用 [Solution](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.Solution.aspx) 属性访问此信息，该属性将返回对 [SolutionObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SolutionObject.aspx) 接口的引用。 
  
在以下示例中，第一个警报显示通过 [SolutionObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SolutionObject.aspx) 接口提供的一些数据，例如，它的统一资源标识符 (URI) 位置（使用 [URI](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Solution.URI.aspx) 属性）以及它的版本号（使用 [Version](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Solution.Version.aspx) 属性）。下一个警报使用 [SolutionObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Solution.DOM.aspx) 接口的 [DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SolutionObject.aspx) 属性显示 .xsf 文件的源 XML。 
  
```cs
thisXDocument.UI.Alert("PackageURL: " +
   thisXDocument.Solution.PackageURL +
   "\nURI: " + thisXDocument.Solution.URI +
   "\nVersion: " + thisXDocument.Solution.Version);
thisXDocument.UI.Alert(thisXDocument.Solution.DOM.xml);
```

```vb
thisXDocument.UI.Alert("PackageURL: " &amp; _
   thisXDocument.Solution.PackageURL &amp; vbNewLine &amp; _
   "URI: " &amp; thisXDocument.Solution.URI &amp; vbNewLine &amp; _
   "Version: " &amp; thisXDocument.Solution.Version)
thisXDocument.UI.Alert(thisXDocument.Solution.DOM.xml)
```


