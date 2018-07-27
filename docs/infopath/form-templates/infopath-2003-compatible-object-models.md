---
title: InfoPath 2003 兼容对象模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, object model,InfoPath 2003-compatible object model,object models [InfoPath 2003], compatible with InfoPath 2007,object models [InfoPath 2007], InfoPath 2003 compatible
localization_priority: Normal
ms.assetid: e4511af6-d7e7-44ad-a50d-1b7ee04f8215
description: Microsoft InfoPath 是作为组件对象模型 (COM) 应用程序而编写的，它将可编程性接口作为 COM 接口同时向外部自动化和表单模板脚本公开。
ms.openlocfilehash: 09ba36b39e520629764bd57a623e8fb490a63a89
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774028"
---
# <a name="infopath-2003-compatible-object-models"></a>InfoPath 2003 兼容对象模型

Microsoft InfoPath 是作为组件对象模型 (COM) 应用程序而编写的，它将可编程性接口作为 COM 接口同时向外部自动化和表单模板脚本公开。为了支持创建使用 Visual C# 和 Visual Basic 托管代码语言的 InfoPath 解决方案，InfoPath 安装程序安装了三个互操作程序集。互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。 
  
InfoPath 安装的三个互操作程序集的文件命名为：
  
- Microsoft.Office.Interop.InfoPath.dll
    
- Microsoft.Office.Interop.InfoPath.SemiTrust.dll
    
- Microsoft.Office.Interop.InfoPath.Xml.dll
    
本主题讨论通过 Microsoft.Office.Interop.InfoPath.SemiTrust 互操作程序集公开的对象模型，该程序集专门用来从 InfoPath 表单模板 (.xsn) 内编写和运行托管代码业务逻辑。 
  
有关 Microsoft.Office.Interop.InfoPath 和 Microsoft.Office.Interop.InfoPath.Xml 程序集的信息，请参阅 [Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/zh-CN/library/microsoft.office.interop.infopath.aspx) 和 [Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/zh-CN/library/microsoft.office.interop.infopath.xml) 命名空间的文档。 
  
## <a name="important-installation-information"></a>重要安装信息

默认情况下，InfoPath 安装程序的**典型**安装选项会在 C:\Program Files\Microsoft Office\Office14 文件夹中安装 Microsoft.Office.Interop.InfoPath.SemiTrust 和 Microsoft.Office.Interop.InfoPath.Xml 程序集的副本。 Microsoft.Office.Interop.InfoPath 和 Microsoft.Office.Interop.InfoPath.Xml 程序集也安装在全局程序集缓存 (GAC) 中，可从 C:\Windows\Assembly 文件夹查看其内容。 
  
如果未安装这些程序集，则应确认已正确安装 Microsoft InfoPath。 只要在运行安装程序之前安装了 .NET Framework 2.0 或更高版本，InfoPath 安装程序中的 **.NET 可编程性支持**选项就会设置为**从本机运行**，实现 InfoPath 的**典型**安装。 如果计算机上没有这些互操作程序集，则必须确认已安装 .NET Framework 2.0 或更高版本，然后从**控制面板**运行**添加或删除程序**并设置 **.NET 可编程性支持**选项为**从本机运行**。
  
有关下载 .NET Framework 2.0 Redistributable 的信息，请参阅 [.NET Framework 2.0 Redistributable](http://www.microsoft.com/downloads/details.aspx?displaylang=en&amp;FamilyID=0856eacb-4362-4b0d-8edd-aab15c5e04f5)。
  
## <a name="the-microsoftofficeinteropinfopathsemitrust-namespace"></a>Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间

在 Microsoft Office InfoPath 2003 Service Pack 1 和 Microsoft Office InfoPath 2003 Toolkit for Visual Studio® .NET 发布之前，InfoPath 表单模板的所有编程逻辑都是使用 Microsoft JScript 或 Microsoft VBScript 创建的，这些脚本是在 Microsoft 脚本编辑器 (MSE) 开发环境中编写的。在 MSE 中编写的脚本在运行时进行解释，它们访问由 IPEDITOR.dll 动态链接库公开的 COM 对象模型。
  
为了支持为编程逻辑创建使用 Visual C# 和 Visual Basic 等托管代码语言的表单模板，向 InfoPath 增加了功能以便允许承载公共语言运行库 (CLR)，同时创建了 Microsoft.Office.Interop.InfoPath.SemiTrust 互操作程序集，来允许托管代码以一种安全的方式与 InfoPath 公开的 COM 对象模型进行互操作。有关应用于 InfoPath 托管代码表单模板的安全模型的信息，请参阅[关于具有代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)。 
  
虽然在 InfoPath 表单模板中为给定任务编写托管代码的过程与通过编写脚本执行相同编程任务非常相似，但在从 Visual Studio 2012 中通过**对象浏览器**查看 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间时所公开的 InfoPath 2003 兼容对象模型看起来要复杂得多。 这是因为用于支持 InfoPath 2003 兼容对象模型的 .NET Framework 互操作性技术需要 COM 服务器公开其所有公共接口，以及 .NET Framework 本身所需的一些其他构造。 
  
### <a name="how-com-objects-are-exposed-to-the-infopath-2003-compatible-object-model"></a>COM 对象如何向 InfoPath 2003 兼容对象模型公开

当通过 JScript、VBScript 或 Visual Basic（但不是 .NET 版本的 Visual Basic 和 Visual C#）等高级语言在本地使用 COM 服务器时，公开的对象模型比基础 COM 类和接口要简单一些。例如，在使用这些语言进行工作时，InfoPath **UI** 对象公开了一组方法（共七种），例如用来向用户显示消息框的 **Alert** 方法。 
  
但是，支持 **UI** 对象的基础 COM 构造实际上由三个实体组成：两个分别名为 **UI** 和 **UI2** 的接口以及一个实现这两个接口的成员的 COM coclass。 **UI** 接口有两个版本，这是因为 COM 框架要求接口的定义保持不变，以便使调用该接口的实现的程序和组件保持向后兼容性。 
  
在本例中，为 InfoPath 的第一个版本定义的 **UI** 接口提供了四种方法，包括 **Alert** 方法。 **UI2** 接口可以视为 **UI** 接口的第二个版本，它是为 InfoPath Service Pack 1 版本而定义的。 **UI2** 接口继承了初始 **UI** 接口的四种方法并且还新增了三种方法，如 **Confirm** 方法。虽然可以在脚本或托管代码中编写一行代码来使用  **** 调用 `XDocument.UI.Confirm` 方法，但基础代码实际上通过 COM coclass 中 **Confirm** 方法的实现来调用 **UI2** 接口的该方法。 
  
对象模型在公开给脚本时隐藏了这些细节，但是通过托管代码使用 COM 服务器所需的互操作程序集公开了 coclass 与这两个接口。对于在 MSE 脚本环境中使用的单个 **UI** 对象， **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间公开了以下三项： 
  
- [UI](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI.aspx) 接口 
    
- [UI2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.aspx) 接口 
    
- [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) coclass 接口 
    
虽然这三个接口都会在**对象浏览器**中公开，并且包含在命名空间的类库文档中，但你只能使用执行 **UI** 对象的 **UIObject** coclass 接口，或使用 **UI2** 接口成员（由 **UIObject** coclass 接口执行的最新版本的接口）。 要从其父 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 对象访问 **UIObject** coclass 接口（就像在脚本中一样），请使用 [UI](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.UI.aspx) 访问器属性。 除了一些值得注意的异常外，这是 InfoPath Service Pack 1 发布时更新的 InfoPath 原始版本中所有对象的模式。 
  
虽然模式基本相同，但 InfoPath Service Pack 1 中添加的全新对象（例如 **Certificate** 对象）的情况稍微简单一些。 在这种情况下，只需要关注两个项目：[ CertificateObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.CertificateObject.aspx) coclass 接口和 [Certificate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Certificate.aspx) 接口的成员，这是 **CertificateObject** coclass 接口执行的最新且唯一的接口。 就像在脚本中使用 InfoPath COM 对象一样，[Certificate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Signature.Certificate.aspx) 访问器属性用于从其父访问对象。 
  
此相同模式适用于集合的接口，不同之处在于集合的 coclass 接口的名称中追加了"Collection"而不是"Object"。例如，COM **DataAdapters** 集合的 coclass 接口被命名为 [DataAdaptersCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataAdaptersCollection.aspx) ，并且它实现的接口是 [DataAdapters](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataAdapters.aspx) 接口。同样，使用 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DataAdapters.aspx) 父对象的 **DataAdapters** accessor 属性访问该集合。 
  
此命名模式有三个例外。COM **Application** 和 **XDocument** 对象的 coclass 接口名称中没有追加"Object"。它们的名称与对应的 COM 对象相同，即 [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 和 **XDocument**。另外， **Application** 和 **XDocument** coclass 接口实现的接口的名称都以下划线 (_) 作为前缀，即 [_Application2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.aspx) 和 [_XDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.aspx) 。第三个例外是 COM **DataObject** 对象。此对象的 coclass 接口被命名为 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) ，但正如其他 InfoPath COM 对象一样，它实现的接口是 [DataObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.aspx) 接口。 
  
### <a name="how-microsoft-xml-core-services-msxml-50-for-microsoft-office-objects-are-exposed-to-the-infopath-2003-compatible-object-model"></a>Microsoft XML Core Services (MSXML) 5.0 for Microsoft Office 对象如何向 InfoPath 2003 兼容对象模型公开

Microsoft XML Core Services（MSXML，也是一个 COM 服务器）提供的对象模型的对象和成员的子集由 Microsoft.Office.Interop.InfoPath.SemiTrust 互操作程序集公开的接口封装。必须要封装的原因是 InfoPath COM 对象模型的某些成员依赖于 MSXML，并且必须能够以一种安全的方式访问这些成员。 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间中封装 MSXML 对象模型的对象和成员的接口名称与 MSXML COM 服务器公开的名称相同。多数情况下，这些名称都以"IXMLDOM"作为前缀，这是因为它们被用来处理 XML 文档对象模型 (DOM)。例如， [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DOM.aspx) 接口的 **DOM** 属性（用来返回对表单的基础 XML 文档的引用）返回由 Microsoft.Office.Interop.InfoPath.SemiTrust 互操作程序集封装的 [IXMLDOMDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.IXMLDOMDocument.aspx) 接口。调用和使用 **IXMLDOMDocument** 接口成员的方式基本上与在不使用托管代码的表单模板中使用脚本时相同。 
  
有关在托管代码表单模板中使用 Microsoft XML Core Services (MSXML) for Microsoft Office 对象模型的成员的详细信息，请参阅[使用 InfoPath 2003 对象模型处理 MSXML 和 System.Xml](working-with-msxml-and-system-xml-using-the-infopath-2003-object-model.md)。
  
### <a name="using-intellisense"></a>使用 IntelliSense

对于在托管代码表单模板中针对 InfoPath 2003 兼容对象模型编写的多数代码，您将使用在默认 FormCode.cs 或 FormCode.vb 类文件的  `thisXDocument` 方法中进行初始化的  `thisApplication` 和  `_Startup` 变量。可以使用  `thisXDocument` 和  `thisApplication` 变量访问 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 和 [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) coclass 接口的成员。在键入这两个变量中任何一个变量的名称并在其后加上句点后，IntelliSense 语句完成信息将显示相应 coclass 接口的列表成员。可以继续以这种方式访问您要使用的对象模型成员。 
  
下面显示的是一个简单示例，该示例使用  `thisXDocument` 变量访问 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 方法，以便使用通过  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.Version.aspx) 变量访问的 `thisApplication` 属性来显示 InfoPath 应用程序的版本。 
  
```cs
thisXDocument.UI.Alert(thisApplication.Version);
```

```vb
thisXDocument.UI.Alert(thisApplication.Version)
```

### <a name="using-the-class-library-reference-documentation"></a>使用类库引用文档

**Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间类库参考文档的组织结构反映 coclass 接口与其实现的继承接口之间的关系。这将在本主题前面所述的"COM 对象如何向托管代码公开"一节中介绍。 
  
尽管 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间引用文档的组织结构和命名方式给人的第一印象似乎有些混乱，但这些主题与作为 InfoPath 开发人员参考（包含在 InfoPath 中）的一部分的"InfoPath 对象模型引用"使用基本相同的方式进行组织。除了 **Application** 和 **XDocument** 接口的主题以外，所有 COM coclass 接口主题均映射到 InfoPath 脚本引用中等同的"对象"和"集合"主题。例如， **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间引用文档的"UIObject 接口"和"WindowsCollection 接口"主题对应于"InfoPath 对象模型引用"脚本引用的"UI 对象"和"Windows 集合"主题中相似的内容。 
  
但是，按照主题开头的接口描述转到 coclass 接口的成员的链接将显示一个空标题。若要显示由 coclass 接口实现的成员的列表，必须打开由 coclass 继承的最新接口的主题，然后打开其成员表。将在 coclass 接口主题中"备注"一节的开头提供指向继承接口的链接。
  
在代码编辑器中按 F1 时，除了调用 F1 帮助的成员将直接显示以外，其他行为是相似的，因为您最常使用的是接口的成员。但实际上可以从版本控制接口实现成员，第一次遇到这种情况时可能容易混淆。例如，如果键入  `thisXDocument.UI.Alert`，然后将光标放在  `Alert` 上并按 F1，则将显示标题为"UI2.Alert 方法"的主题。这是因为 **Alert** 方法是 **UI2** 接口的成员的实现。 
  
### <a name="passing-optional-parameters-to-infopath-object-model-members"></a>将可选参数传递给 InfoPath 对象模型成员

如果 InfoPath 2003 兼容对象模型成员包含一个可选参数，并且您没有为该参数指定值，则必须传递该参数的 **Type.Missing** 域。如果在忽略实际值时未能传递 **Type.Missing** 域，将会导致生成错误。对于用 Visual C# 和 Visual Basic 编写的代码，都会出现这种情况。例如， [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectNodes.aspx) 接口的 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 方法包含两个可选参数：  _varEndNode_ 和  _varViewContext_。如果某代码行未指定这些可选参数的实际值，则会发生类似如下示例的情况。
  
```cs
IXMLDOMNode group1 = 
   thisXDocument.DOM.selectSingleNode("/my:myFields/my:group1");
thisXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing);
```

```vb
Dim group1 As IXMLDOMNode = _
   thisXDocument.DOM.selectSingleNode("/my:myFields/my:group1")
thisXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing)
```

### <a name="about-common-language-specification-compliance"></a>关于公共语言规范的符合情况

在内部，Microsoft.Office.Interop.InfoPath.SemiTrust 程序集中的每个接口和成员的 **CLSCompliant** 属性都设置为 **false**。由于引用文档的一部分是使用 **System.Reflection** 生成的，因此每个接口和成员的说明中都追加了短语"This interface/method/property is not CLS-compliant"。但是 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间的多数接口和成员实际上都符合 CLS。 
  
## <a name="see-also"></a>另请参阅

- [使用 InfoPath 2003 对象模型开发表单模板的常见任务](common-tasks-for-developing-form-templates-using-infopath-object-model.md)
- [有关包含代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)
- [使用 InfoPath 2003 对象创建表单模板](creating-form-templates-using-the-infopath-2003-object-model.md)
- [了解 InfoPath 2003 对象模型](understanding-the-infopath-2003-object-model.md)

