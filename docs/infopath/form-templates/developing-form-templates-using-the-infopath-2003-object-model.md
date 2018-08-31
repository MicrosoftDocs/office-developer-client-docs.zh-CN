---
title: 使用 InfoPath 2003 对象模型开发表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- form templates [infopath 2007], using infopath 2003 object model,InfoPath 2003-compatible form templates,InfoPath 2007, developing form templates using InfoPath 2003 object model,object models [InfoPath 2003], developing managed code form templates
localization_priority: Normal
ms.assetid: c74cbcd0-4fe6-4eb7-a05c-f61e1868c42b
description: Microsoft InfoPath 继续支持利用 Microsoft Office InfoPath 2003 Toolkit for Visual Studio .NET 或 Visual Studio 2005 Tools for the Microsoft Office System 创建的、且具有依据 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间的成员编写的业务逻辑的表单模板项目。本节中的主题将此命名空间的类型和成员称为 InfoPath 2003 兼容对象模型，或简称为 InfoPath 2003 对象模型。InfoPath 还支持通过 Microsoft Office InfoPath 2007 创建的、使用 InfoPath 2003 兼容对象模型的表单模板项目。此外，还可以利用 InfoPath 创建使用 InfoPath 2003 兼容对象模型的新表单模板对象，以便为 Office InfoPath 2007 用户保留向后兼容性。本节中的所有主题专门讲述如何创建和开发使用 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间提供的 InfoPath 2003 兼容对象模型的表单模板。
ms.openlocfilehash: 5d949242068586c752e7a92fa53792cda9ececea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773965"
---
# <a name="developing-form-templates-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型开发表单模板

Microsoft InfoPath 继续支持利用 Microsoft Office InfoPath 2003 Toolkit for Visual Studio .NET 或 Visual Studio 2005 Tools for the Microsoft Office System 创建的、且具有依据 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间的成员编写的业务逻辑的表单模板项目。本节中的主题将此命名空间的类型和成员称为 InfoPath 2003 兼容对象模型，或简称为 InfoPath 2003 对象模型。InfoPath 还支持通过 Microsoft Office InfoPath 2007 创建的、使用 InfoPath 2003 兼容对象模型的表单模板项目。此外，还可以利用 InfoPath 创建使用 InfoPath 2003 兼容对象模型的新表单模板对象，以便为 Office InfoPath 2007 用户保留向后兼容性。本节中的所有主题专门讲述如何创建和开发使用 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的 InfoPath 2003 兼容对象模型的表单模板。 
  
> [!IMPORTANT]
> [!重要信息] 尽管 InfoPath 仍支持使用 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的托管代码对象模型来创建业务逻辑，但是对于部署到 Microsoft SharePoint Server 2010（带有 InfoPath Forms Services）且启用浏览器功能的表单模板，并不支持使用此对象模型编写的业务逻辑。启用浏览器功能的表单模板必须使用由 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的成员提供的新的 InfoPath 托管代码对象模型，来创建自定义业务逻辑。有关创建含有用 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间成员编写的业务逻辑的表单模板的详细信息，请参阅 [开发包含代码的 InfoPath 表单模板](developing-infopath-form-templates-with-code.md)。 > 另请注意，利用 Visual Studio 2008 编译的表单模板的用户必须在其计算机上安装 Microsoft .NET Framework 2.0 或更高版本，而利用 Visual Studio .NET 2003 编译的表单模板的用户只需在其计算机上安装 Microsoft .NET Framework 1.1。 
  
## <a name="in-this-section"></a>本节内容

[使用 InfoPath 2003 对象模型开发表单模板入门](get-started-developing-form-templates-using-infopath-object-model.md)
  
> 提供有关如何开始创建托管代码表单模板（使用 InfoPath 2003 兼容对象模型）的信息。
    
[使用 InfoPath 2003 对象模型创建表单模板](creating-form-templates-using-the-infopath-2003-object-model.md)
  
> 讨论初始化和清理代码、如何添加事件处理程序、如何调试和部署托管代码表单模板、线程支持以及如何使用 InfoPath 托管代码解决方案中的 Microsoft XML Core Services (MSXML)。
    
[具有代码的 InfoPath 表单模板中的安全性](security-in-infopath-form-templates-with-code.md)
  
> 讨论使用托管代码的 InfoPath 表单模板的安全模型，调试完全信任的 InfoPath 表单模板以及相关的安全过程。
    
[了解 InfoPath 2003 对象模型](understanding-the-infopath-2003-object-model.md)
  
> 讨论 InfoPath 2003 兼容对象模型，以及使用该对象模型的托管代码表单模板的常见编程任务。
    
[使用 InfoPath 2003 对象模型的表单模板的疑难解答](troubleshoot-form-templates-that-use-infopath-object-model.md)
  
> 包含用于解决您在创建使用 InfoPath 2003 兼容对象模型的托管代码表单模板时可能遇到的常见问题的提示。
    
## <a name="related-sections"></a>相关章节

[InfoPath 开发人员门户](http://go.microsoft.com/fwlink?LinkID=11689)
  
> 包含许多链接，这些链接指向有关构建自定义 InfoPath 解决方案的技术文章、代码示例、下载内容、支持以及其他 MSDN 文档。
    
[Microsoft Office 开发人员中心](http://go.microsoft.com/fwlink?LinkID=27128)
  
> 包含许多链接，这些链接指向有关构建自定义 Office 解决方案的技术文章、代码示例、下载内容、支持以及其他 MSDN 文档。
    

