---
title: 为 InfoPath 开发人员提供的新功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- what's new [infopath 2007],developer features [InfoPath 2007],InfoPath 2007, what's new,new features [InfoPath 2007]
localization_priority: Normal
ms.assetid: d0ad3111-bd41-4f35-8a34-62c17f20fc19
description: InfoPath 旨在让您轻松地在 Microsoft SharePoint Server 平台上构建各种基于表单的应用程序。Microsoft SharePoint Server 2013 与 InfoPath Forms Services 和 Microsoft InfoPath 2013 结合使用可提供面向开发人员的许多功能。利用 SharePoint Server 2013 中提供的 InfoPath Forms Services，您可以将 InfoPath 表单模板部署到 SharePoint Server，以便没有 InfoPath 富客户端的用户可以在 Web 浏览器中打开并填写 InfoPath 表单。
ms.openlocfilehash: a11c6b4018e60a470197ecd7ffdf3b79a13658b9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774092"
---
# <a name="whats-new-for-infopath-developers"></a>为 InfoPath 开发人员提供的新功能

InfoPath 旨在让您轻松地在 Microsoft SharePoint Server 平台上构建各种基于表单的应用程序。Microsoft SharePoint Server 2013 与 InfoPath Forms Services 和 Microsoft InfoPath 2013 结合使用可提供面向开发人员的许多功能。利用 SharePoint Server 2013 中提供的 InfoPath Forms Services，您可以将 InfoPath 表单模板部署到 SharePoint Server，以便没有 InfoPath 富客户端的用户可以在 Web 浏览器中打开并填写 InfoPath 表单。
  
使用 InfoPath 2013 创建的表单模板继续支持针对 **Microsoft.Office.InfoPath** 命名空间的类和成员编写的业务逻辑，此业务逻辑对于在 InfoPath Filler 中打开的表单和在 Web 浏览器中打开的表单的工作方式相同。通过使用针对此托管对象模型编写的业务逻辑并使用 InfoPath Designer 中的设计检查功能，您可以创建一个可部署到 SharePoint Server 2013 中适当配置的文档库的表单模板，该表单模板将在 InfoPath Filler 和 Web 浏览器中运行。 
  
## <a name="new-features-and-improvements"></a>新的功能和改进

以下几节简短描述了 InfoPath 开发人员所关注的这些功能和改进：
  
- 编写和编辑代码的新方法
    
- SharePoint 沙盒解决方案
    
- 只需单击一次即可发布表单
    
- 增强 SharePoint 列表表单
    
- 使用 InfoPath 表单 web 部件的门户页面上承载表单
    
- 更加丰富的 Web 表单
    
- 符合标准的浏览器表单
    
- 使用数字签名提供增强的信息安全性和完整性
    
- 新控件
    
## <a name="new-way-to-write-and-edit-code"></a>编写和编辑代码的新方法

已从 InfoPath 2013 中删除已与 InfoPath 2010 集成的 Microsoft Visual Studio Tools for Applications IDE 工具。现在，若要在 InfoPath 2013 中编写或编辑表单代码，则需要 Visual Studio 2008 和已安装的 [Microsoft Visual Studio Tools for Applications 2012（该链接可能指向英文页面）](http://www.microsoft.com/en-us/download/details.aspx?id=38807) 加载项。虽然编程体验基本上未发生更改，但在为 InfoPath 表单编写托管代码时，您可以使用完整的 Visual Studio 开发体验。 
  
以下几节描述了 InfoPath 2010 和 SharePoint Server 2010 中首次添加的功能，并继续为使用 InfoPath 2013 和 SharePoint Server 2013 的开发人员提供了有价值的信息。
  
## <a name="sharepoint-server-sandboxed-solutions"></a>SharePoint Server 沙盒解决方案

利用 InfoPath，将包含代码的表单部署到 SharePoint Server 2013 比以前更为轻松。在 Office InfoPath 2007 中，所有包含代码的表单都必须由 SharePoint 场管理员批准和上载。利用 SharePoint Server 2013 中对沙盒解决方案的支持，具有网站集管理权限的表单设计人员现在可以将包含代码的大多数表单直接发布到其 SharePoint 网站。服务器上的资源配额设置可限制使用过多的资源。网站集管理员可继续保持控制，并做出有关解决方案的信任决策。服务器场管理员可以不干预。有关发布 InfoPath 表单模板作为沙盒解决方案的详细信息，请参阅[发布包含代码的表单](publishing-forms-with-code.md)。
  
## <a name="publish-forms-with-one-click"></a>只需单击一次即可发布表单

InfoPath 在设计上可轻松比以往任何时候都要将更新发布到窗体正在 首次发布表单模板，而不是通过几个对话框中，单击之后，您可以完成的新**快速发布**按钮，这是可用的**快速访问工具栏**中，然后在新中单击一次此任务Microsoft Office Backstage，这是可通过单击**文件**选项卡。 
  
## <a name="enhance-sharepoint-list-forms"></a>增强 SharePoint 列表表单

使用 InfoPath，您现在可以扩展和增强用于创建、 编辑和查看 SharePoint 列表项的表单。 通过打开列表，在**列表工具**，单击**列表**选项卡，然后单击**自定义窗体**，您可以自动生成类似于默认的 InfoPath 表单、 开的 SharePoint 列表表单。 然后，您可以自定义和增强修改布局、 创建其他视图，并在 InfoPath 中添加规则和数据验证此窗体。 当您完成修改改进的列表窗体时，您可以将其发布到 SharePoint 中使用新的一键式发布功能在 InfoPath 中。
  
## <a name="host-forms-on-portal-pages-using-the-infopath-form-web-part"></a>使用 InfoPath 表单 web 部件的门户页面上承载表单

SharePoint Server 2013 中为比以往任何时候都以承载窗体使用新的**InfoPath 表单 web 部件**的网页上更轻松。 在 Microsoft Office SharePoint Server 2007，希望承载其网页上的 InfoPath 表单的用户必须在 Visual Studio 中编写代码。 现在，无需编写一行代码，您可以将**InfoPath 表单 web 部件**添加到 Web 部件页和其指向您已发布表单。您可以使用**InfoPath 表单 web 部件**来承载任何 InfoPath 浏览器表单发布到 SharePoint 列表或表单库的。 您还可以将其连接到在上其他 Web 部件，以发送或接收数据。 有关如何使用**InfoPath 表单 web 部件**的详细信息，请参阅 SharePoint 2010 SDK 中[使用 InfoPath 表单 web 部件](http://msdn.microsoft.com/library/bb87e126-1a07-45aa-af36-b294df3a2576%28Office.15%29.aspx)。 
  
## <a name="richer-web-forms"></a>更加丰富的 Web 表单

客户端表单和浏览器表单之间的功能差距已经缩小，从而可为所有用户创造更加一致的表单填写体验。浏览器表单中现在支持的控件和功能包括：
  
- 项目符号列表、编号列表和普通列表
    
- 多重选择列表框
    
- 组合框
    
- 图片按钮
    
- 超链接功能
    
- 选项组和节 
    
- 日期和时间控件
    
- 个人/组选取器
    
- 筛选功能
    
## <a name="standards-compliant-browser-forms"></a>符合标准的浏览器表单

InfoPath 浏览器表单现在符合 Web 内容辅助功能准则 2.0 (WCAG 2.0) AA，从而使表单设计人员能够创建可供残疾用户使用的表单。
  
## <a name="provide-enhanced-information-security-and-integrity-with-digital-signatures"></a>使用数字签名提供增强的信息安全性和完整性

InfoPath 支持下一代加密技术 (CNG) 数字签名内容。为了帮助您确保表单中所含信息的完整性，InfoPath 客户端和 SharePoint Server 2013 提供了为整个表单或表单的节启用单一、联署和副署方案所必需的控件。可以在 Internet Explorer 中使用 ActiveX 签名行控件对表单进行签名。可以在 SharePoint Server 2013 支持的任何浏览器中查看经过签名的表单。
  
## <a name="new-controls"></a>新控件

InfoPath 提供了更加丰富的控件集，可以将这些控件添加到表单。以下列表简要描述了部分新控件：
  
- **图片按钮** - 在表单中使用任何图像作为按钮，而不是灰色矩形。 
    
- **超链接** - 使用户能够在填写表单时输入自己的超链接。 
    
- **个人/组选取器** - 使用户能够在填写表单时检查和查询帐户名称和组。 
    
- **实体选取器** - 使用户能够在填写表单时从运行 SharePoint Server 2013 的服务器上的外部列表中选择值。 
    
- **签名行** - 在以数字方式对表单进行签名时，向用户提供签名行或图章图像（例如印鉴或判子图章）。 
    
## <a name="see-also"></a>另请参阅



[开发包含代码的 InfoPath 表单模板](developing-infopath-form-templates-with-code.md)
  
[使用 InfoPath 2003 对象模型开发表单模板](developing-form-templates-using-the-infopath-2003-object-model.md)

