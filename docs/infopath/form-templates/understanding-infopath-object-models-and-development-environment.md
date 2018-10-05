---
title: 了解 InfoPath 对象模型和开发环境
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2007, object models,object models [InfoPath 2007],InfoPath 2007, development environments
localization_priority: Normal
ms.assetid: 29415c5b-9a42-46f4-a9e8-6a7d5bb7bdbf
description: Microsoft InfoPath 2013 支持两种用于在表单模板中开发业务逻辑的编程模型，并且支持通过托管代码实现的外部自动化。
ms.openlocfilehash: c2ed1254acf86136ab7144c732aef91ac4c14c53
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400107"
---
# <a name="understanding-infopath-object-models-and-development-environment"></a>了解 InfoPath 对象模型和开发环境

Microsoft InfoPath 2013 支持两种用于在表单模板中开发业务逻辑的编程模型，并且支持通过托管代码实现的外部自动化。
  
SharePoint Server 2013 中提供的 InfoPath Forms Services 提供了用于填写 InfoPath 表单的 Web 浏览器体验。如果部署到运行 InfoPath Forms Services 的服务器，将能够从未安装 InfoPath 的计算机上的 Web 浏览器中打开基于浏览器兼容的表单模板 (.xsn) 的表单，但如果安装了该软件，则这些表单将在 InfoPath 中打开。InfoPath Forms Services 还提供了一个对象模型，用于自动执行与 InfoPath 表单模板发布和管理相关的服务器任务。
  
InfoPath 2013 支持 Visual Studio 2008 编程环境及其关联的编程语言，本主题后面描述了这些语言。
  
## <a name="infopath-programming-models"></a>InfoPath 编程模型

InfoPath 2013 支持两种用于在表单模板中开发业务逻辑的对象模型：
  
- InfoPath 托管代码对象模型
    
- InfoPath 2003 兼容的托管代码对象模型
    
此外，利用 InfoPath 2013 可以编写托管代码，以便从外部应用程序自动执行 InfoPath。
  
InfoPath Forms Services 提供了用于自动执行服务器任务的对象模型，这些任务包括通过服务器上运行的代码验证和上载表单模板（需要服务器管理员访问和权限）等。
  
> [!NOTE]
> InfoPath Filler 2013 可打开和运行在 InfoPath 的早期版本中创建的 InfoPath 表单模板解决方案，这些解决方案使用通过脚本语言（JScript 和 VBScript）编写的业务逻辑。但是，InfoPath Designer 2010 不支持创建或修改使用通过脚本编写的业务逻辑的表单模板。 
  
### <a name="the-infopath-managed-code-object-model"></a>InfoPath 托管代码对象模型

InfoPath 2013 托管代码对象模型在两个名称均为 Microsoft.Office.Infopath.dll 的程序集中实现。
  
程序集的其中一个版本实现 InfoPath 对象模型的一个子集，该子集只包含在表单模板（作为启用浏览器功能的表单模板部署，而且运行在带有 InfoPath Forms Services 的 SharePoint Server 2013 上）业务逻辑中支持的类型和成员。带有依据此程序集编写的业务逻辑的表单模板将在 InfoPath Filler 和 Web 浏览器中打开和运行。
  
程序集的另一个版本实现其他类型和成员，能提供在启用浏览器功能的表单模板的业务逻辑中不支持的功能。带有依据此程序集中的其他类和成员编写的业务逻辑的表单模板将只在 InfoPath Filler 编辑器中打开和运行。
  
> [!NOTE]
> 可以编写条件逻辑，以使用 [Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.aspx) 类的属性来确定表单模板在哪个环境（InfoPath Filler 或 Web 浏览器）中运行。 通过使用此条件逻辑，业务逻辑可以在以下两种代码之间分支：在 Web 浏览器中工作的代码，以及依据只在 InfoPath Filler 编辑器中工作的类和成员编写的代码。 有关详细信息，请参阅[编写确定运行时环境的条件逻辑](how-to-write-conditional-logic-that-determines-the-run-time-environment.md)
  
当你添加和编译表单模板的业务逻辑时，InfoPath 使用的程序集取决于你在 InfoPath Designer 中开始设计新表单时，在 Microsoft Office Backstage 的“新建”**** 选项卡上选择了“空白表单”**** 还是“空白表单 (InfoPath Filler)”**** 表单模板。 使用“空白表单”**** 表单模板创建的表单使用这样的程序集：仅包含在部署为启用浏览器的表单模板的表单模板的业务逻辑中支持的类型和成员。 使用“空白表单”**** 表单模板创建的表单可以使用 Web 浏览器和 InfoPath Filler 打开。 使用“空白表单 (InfoPath Filler)”**** 表单模板创建的表单使用这样的程序集：实现提供启用浏览器的表单模板的业务逻辑中不支持的功能的其他类型和成员，并且此类表单只能使用 InfoPath Filler 打开。 
  
> [!TIP]
> 开始设计表单模板后，可以通过更改表单兼容性设置更改使用的程序集。 为此，请单击“开发者”**** 选项卡上的“语言”****，然后单击“类别”**** 列表中的“兼容性”****。 在“表单类型”**** 列表中，选择“Web 浏览器表单”**** 创建一个可以在 SharePoint Server 2013 上部署为浏览器兼容表单的表单。 选择“InfoPath Filler 表单”**** 创建一个只能在 InfoPath Filler 编辑器中运行的表单。 “表单类型”**** 列表中的其他选择为与 InfoPath 2007 和 InfoPath 2003 兼容提供支持。 
  
此对象模型的两个版本的类和成员均通过 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间公开。下表列出了这些程序集在 InfoPath 2013 安装的目录中所处的位置。 
  
|**程序集**|**说明**|
|:-----|:-----|
|Microsoft.Office.InfoPath.dll          （位于 C:\Program Files\Microsoft Office\Office15\InfoPathOM\InfoPathOMFormServices 中）  <br/> |对象模型的子集，其中仅包含将在表单模板（部署到运行 InfoPath Forms Services 的服务器）的业务逻辑中运行的类型和成员。  <br/> |
|Microsoft.Office.InfoPath.dll          （位于 C:\Program Files\Microsoft Office\Office15\InfoPathOM 中）  <br/> |"完整的"对象模型，包括将不会在部署到 InfoPath Forms Services 的表单模板的业务逻辑中运行的类型和成员。  <br/> |
   
> [!NOTE]
> 编写和编译代码时，上述程序集在设计时使用。在运行时，在 InfoPath 中打开表单模板时使用的程序集位于安装了 InfoPath 的计算机的全局程序集缓存 (GAC) 中。在 Web 浏览器中从运行 InfoPath Forms Services 的服务器打开表单模板时，使用的程序集位于服务器中。 
  
提供两个程序集有助于确保业务逻辑将只包含对适合受支持的表单编辑器（Web 浏览器或 InfoPath Filler）的对象模型成员的调用。例如，在编辑代码时，IntelliSense 功能（例如语句完成和嵌入式文档）将只显示适合目标表单编辑器的对象模型成员，并依据这些成员工作。
  
在 Microsoft.Office.InfoPath 程序集公开的两个版本的托管代码对象模型中，导航和更新业务逻辑中的 XML 数据存储需要调用 **System.Xml.XPath.XPathNavigator** 类的成员。在 InfoPath 2003 中，导航和更新 XML 数据存储需要调用 MSXML 类的成员（对于使用 JScript 或 VBScript 创建的业务逻辑），或需要通过由 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的 MSXML 类的封装程序进行调用（对于使用 C# 或 Visual Basic 和 Microsoft Office InfoPath 2003 Toolkit for Visual Studio .NET 创建的业务逻辑）。 
  
使用 **XPathNavigator** 类的成员可允许相同的业务逻辑代码支持表单模板的 DOM 操作，这些表单模板在 InfoPath 客户端和启用 Web 功能的表单（在 Web 浏览器中从带有 InfoPath Forms Services 的 SharePoint Server 2013 中打开）中打开。 
  
有关如何在 InfoPath 托管代码表单模板的业务逻辑中使用 **XPathNavigator** 类的成员的信息，请参阅[使用 XPathNavigator 和 XPathNodeIterator 类](how-to-work-with-the-xpathnavigator-and-xpathnodeiterator-classes.md)。
  
### <a name="the-infopath-2003-compatible-managed-code-object-model"></a>InfoPath 2003 兼容的托管代码对象模型

InfoPath 2003 兼容的托管代码对象模型在 InfoPath 2003 Service Pack 1 中引入，同时引入的还有 Microsoft Office InfoPath 2003 Toolkit for Visual Studio .NET，用于通过托管代码在表单模板中编写业务逻辑。此对象模型仍受 InfoPath 2013 支持，以提供与 InfoPath 2003 的兼容性。
  
此对象模型的类和成员通过 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间公开。此对象模型在以下程序集文件中实现，该文件位于 C:\Program Files\Microsoft Office\Office14 文件夹中： 
  
|**程序集**|**说明**|
|:-----|:-----|
|Microsoft.Office.Interop.InfoPath.SemiTrust.dll  <br/> |提供针对 InfoPath COM 对象模型的 COM Interop，用于通过 C# 或 Visual Basic 编写的表单模板业务逻辑。  <br/> |
   
> [!NOTE]
> 尽管 InfoPath 2013 仍支持使用 Microsoft.Office.Interop.InfoPath.SemiTrust 程序集提供的 COM Interop 托管代码对象模型来创建业务逻辑，但是，对于部署到 SharePoint Server 2013（带有 InfoPath Forms Services）且启用了浏览器功能的表单模板，并不支持使用此对象模型编写的业务逻辑。启用了浏览器功能的表单模板必须使用 InfoPath 托管代码对象模型来实现自定义业务逻辑。 
  
### <a name="automating-infopath-from-managed-code"></a>通过托管代码自动执行 InfoPath

除了利用托管代码编写业务逻辑之外，开发人员还可以通过使用在外部应用程序中运行的托管代码来自动执行 InfoPath。此功能和编写代码所需的程序集在 InfoPath 2003 Service Pack 1 中引入。用于自动执行 InfoPath 的对象和成员已经过更新，以便在为 InfoPath 2013 编写外部自动化代码时提供其他功能。
  
用于外部自动化的类和成员通过 [Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx) 和 [Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml) 命名空间公开。编写自动化代码所需的程序集文件位于 C:\Program Files\Microsoft Office\Office14 文件夹中。 
  
|**程序集**|**说明**|
|:-----|:-----|
|Microsoft.Office.Interop.InfoPath.dll  <br/> |提供针对 InfoPath COM 对象模型的 COM Interop，用于通过 C# 或 Visual Basic 编写的外部自动化代码。  <br/> |
|Microsoft.Office.Interop.InfoPath.Xml.dll  <br/> |提供针对 MSXML 的 COM Interop，用于使用 C# 或 Visual Basic 编写的外部自动化代码中的 XML DOM 操作。  <br/> |
   
有关 **Microsoft.Office.Interop.InfoPath** 和 **Microsoft.Office.Interop.InfoPath.Xml** 命名空间（这两个命名空间专门用来使用外部应用程序中的托管代码来实现 InfoPath 应用程序的自动化）提供的对象模型的详细信息，请参阅 [InfoPath 开发人员中心](https://msdn.microsoft.com/office/aa905434.aspx)。
  
### <a name="the-infopath-forms-services-object-model"></a>InfoPath Forms Services 对象模型

用于自动执行 InfoPath Forms Services 管理任务的托管代码对象模型在 Microsoft.Office.InfoPath.Server.dll 中实现，该文件位于所安装的 Microsoft SharePoint Server 2013 的 \<驱动器\>:\Program Files\Microsoft Office Server\15.0\Bin 中。
  
|**程序集**|**说明**|
|:-----|:-----|
|Microsoft.Office.InfoPath.Server.dll  <br/> |用于自动执行 InfoPath Forms Services 任务的对象模型，这些任务包括上载、激活或停用启用了浏览器功能的表单模板等。  <br/> |
   
有关 InfoPath Forms Services 对象模型的详细信息，请参阅 MSDN 上提供的 SharePoint Server 2013 软件开发工具包 (SDK)。
  
## <a name="infopath-development-environment"></a>InfoPath 开发环境

可通过将 Visual Studio 2008 与已安装的 [Microsoft Visual Studio Tools for Applications 2012](https://www.microsoft.com/en-us/download/details.aspx?id=38807) 加载项来执行 InfoPath 2013 中的业务逻辑的开发。 
  
> [!NOTE]
> InfoPath 2013 不支持创建或编辑使用通过 JScript 或 VBScript 编写的业务逻辑的表单模板，尽管 InfoPath Filler 支持打开在 InfoPath 的早期版本中创建的基于脚本的表单模板。 
  
## <a name="see-also"></a>另请参阅

- [演练：创建包含代码的基本表单模板](walkthrough-creating-a-basic-form-template-with-code.md)
- [演练：使用 InfoPath 2003 对象模型创建和调试基本表单模板](walkthrough-create-and-debug-basic-form-template-using-infopath-object-model.md)

