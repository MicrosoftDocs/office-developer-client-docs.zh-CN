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
ms.openlocfilehash: 5d469dfb99290054008271867f24d947a42efeee
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385149"
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
    
- 使用 InfoPath 表单 Web 部件在门户页上托管表单
    
- 更丰富的 Web 表单
    
- 符合标准的浏览器表单
    
- 使用数字签名提供增强的信息安全性和完整性
    
- 新控件
    
## <a name="new-way-to-write-and-edit-code"></a>编写和编辑代码的新方法

已从 InfoPath 2013 中删除已与 InfoPath 2010 集成的 Microsoft Visual Studio Tools for Applications IDE 工具。现在，若要在 InfoPath 2013 中编写或编辑表单代码，则需要 Visual Studio 2008 和已安装的 [Microsoft Visual Studio Tools for Applications 2012（该链接可能指向英文页面）](https://www.microsoft.com/en-us/download/details.aspx?id=38807) 加载项。虽然编程体验基本上未发生更改，但在为 InfoPath 表单编写托管代码时，您可以使用完整的 Visual Studio 开发体验。 
  
以下几节描述了 InfoPath 2010 和 SharePoint Server 2010 中首次添加的功能，并继续为使用 InfoPath 2013 和 SharePoint Server 2013 的开发人员提供了有价值的信息。
  
## <a name="sharepoint-server-sandboxed-solutions"></a>SharePoint Server 沙盒解决方案

利用 InfoPath，将包含代码的表单部署到 SharePoint Server 2013 比以前更为轻松。在 Office InfoPath 2007 中，所有包含代码的表单都必须由 SharePoint 场管理员批准和上载。利用 SharePoint Server 2013 中对沙盒解决方案的支持，具有网站集管理权限的表单设计人员现在可以将包含代码的大多数表单直接发布到其 SharePoint 网站。服务器上的资源配额设置可限制使用过多的资源。网站集管理员可继续保持控制，并做出有关解决方案的信任决策。服务器场管理员可以不干预。有关发布 InfoPath 表单模板作为沙盒解决方案的详细信息，请参阅[发布包含代码的表单](publishing-forms-with-code.md)。
  
## <a name="publish-forms-with-one-click"></a>只需单击一次即可发布表单

InfoPath 旨在使发布对表单的更新比以前更为轻松。 首次发布表单模板后，你只需单击新的“快速发布”**** 按钮（可在“快速访问工具栏”**** 和新的 Microsoft Office Backstage 中找到，后者可通过单击“文件”**** 选项卡找到）一次，即可完成此任务，而无需在若干个对话框中单击。 
  
## <a name="enhance-sharepoint-list-forms"></a>增强 SharePoint 列表表单

使用 InfoPath，现在可以扩展和增强用于创建、编辑和查看 SharePoint 列表中的项目的表单。 通过打开列表，单击“列表工具”**** 下的“列表”**** 选项卡，然后单击“自定义表单”****，可以自动生成类似于默认现成可用的 SharePoint 列表表单的 InfoPath 表单。 然后可以通过修改布局、创建其他视图和在 InfoPath 中添加规则和数据验证来自定义和增强此表单。 修改完改进的列表表单后，可以使用 InfoPath 中新的一键发布功能将其发布到 SharePoint。
  
## <a name="host-forms-on-portal-pages-using-the-infopath-form-web-part"></a>使用 InfoPath 表单 Web 部件在门户页上托管表单

在 SharePoint Server 2013 中，使用新的“InfoPath 表单 Web 部件”**** 在 Web 页面上托管表单比以往更容易。 在 Microsoft Office SharePoint Server 2007 中，希望在 Web 页面上托管其 InfoPath 表单的用户需要在 Visual Studio 中编写代码。 现在，无需编写任何代码，便可以将“InfoPath 表单 Web 部件”**** 添加到 Web 部件页面并将其指向已发布的表单。可以使用“InfoPath 表单 Web 部件”**** 托管发布到 SharePoint 列表或表单库的任何 InfoPath 浏览器表单。 还可以将其连接到页面上的其他 Web 部件以发送或接收数据。 有关如何使用“InfoPath 表单 Web 部件”**** 的详细信息，请参阅 SharePoint 2010 SDK 中的[使用 InfoPath 表单 Web 部件](https://msdn.microsoft.com/library/bb87e126-1a07-45aa-af36-b294df3a2576%28Office.15%29.aspx)。 
  
## <a name="richer-web-forms"></a>更丰富的 Web 表单

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

