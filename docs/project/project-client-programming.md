---
title: Project 客户端编程
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
f1_keywords:
- object model
- Project object model
- Project VBA
- VBA
keywords:
- vba， 项目对象模型， 项目， 可编程性， 可编程性， Project VBA，Visual Basic for Applications， Project 对象模型，VBA， 对象模型，VBA，Visual Basic for Applications
localization_priority: Normal
ms.assetid: 0ad49ff6-8dff-4379-a52c-d292c53c2bc0
description: 可以使用 VBA 编写宏来自定义和扩展 Project 2013 桌面客户端应用程序（Project Standard 2013 和 Project Professional 2013）。 您可以使用 Visual Studio 2012 自定义功能区用户界面和创建复杂的外接程序。Office 外接程序为 Project 中基于常见 Office 2013 平台构建的任务窗格启用新的扩展模型。 Project Standard 2013 和 Project Professional 2013 可以运行常规 Office 外接程序，并使用专为 Project 开发的任务窗格外接程序与 SharePoint、其他网站和 Web 应用程序以及外部数据集成。
ms.openlocfilehash: cc345f0ff91dfb573dd86c256e89df478edd4924
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301510"
---
# <a name="project-client-programming"></a>Project 客户端编程

可以使用 VBA 编写宏来自定义和扩展 Project 2013 桌面客户端应用程序（Project Standard 2013 和 Project Professional 2013）。 您可以使用 Visual Studio 2012 自定义功能区用户界面和创建复杂的外接程序。Office 外接程序为 Project 中基于常见 Office 2013 平台构建的任务窗格启用新的扩展模型。 Project Standard 2013 和 Project Professional 2013 可以运行常规 Office 外接程序，并使用专为 Project 开发的任务窗格外接程序与 SharePoint、其他网站和 Web 应用程序以及外部数据集成。
  
 **移动到Visual Studio** VBA 对于录制宏和开发相对简单的自动化解决方案非常有用。 若要开发任务窗格外接程序、外接程序以及更复杂、安全、可扩展且易于部署的解决方案，我们建议您使用 Visual Studio 2012。 Microsoft .NET Framework 4.0 和 Project 2013 主互操作程序集为开发并部署自动化和集成 Project 2013 桌面客户端的解决方案提供了许多优势。 
  
> [!NOTE]
> 您可以使用 Visual Studio 2010开发 Project 加载项。但是，Visual Studio 2012 包含旨在创建 Office 外接程序客户端的模板和扩展。 
  
Project 2013 中 VBA 的 **MSProject** 对象模型本质上与使用 Visual Studio 2013 office 开发人员工具的托管代码解决方案的 **Microsoft.Office.Interop.MSProject** 对象模型 (VSTO) 。 Visual Studio 2012 包括用于开发 Project 2010 和 Project 2013 应用程序级外接程序的模板 (Project Standard 或 Project Professional) 。 VSTO 和适用于 Visual Studio 2012 的 Office 开发人员工具简化了开发、测试和部署高级集成解决方案，这些解决方案可以使用 Project 桌面客户端和其他 Office 2013 应用程序，并与 SharePoint 网站、列表和工作流集成。 
  
任务窗格外接程序和其他 Office 和 SharePoint 外接程序可以在 Office 应用商店中出售 (请参阅) 以用于 Project Online 和本地 [https://office.microsoft.com/store/](https://office.microsoft.com/en-us/store/) 安装。 VBA 宏和 VSTO 加载项无法在 Office 应用商店中分发;它们设计为与 Project Standard 和 Project Professional 本地使用。 可以在项目中分发 VBA 宏。MPP 文件，将其安装在您计算机的 Global.MPT 文件中，或将其分发到 Project Server 2013 的企业全局模板中。 VSTO 加载项可通过部署来更安全地 [ClickOnce，从而](https://msdn.microsoft.com/library/t71a733d.aspx) 便于更新。 
  
## <a name="reference"></a>参考

[Project VBA 开发人员参考](https://msdn.microsoft.com/library/ee861523%28office.15%29.aspx) 包含介绍性文章和 VBA 帮助文章。 
  
## <a name="related-sections"></a>相关章节

[Project Server 2013 体系结构](project-server-2013-architecture.md) 显示 Project 客户端如何与 Project Server 交互。 
  
## <a name="see-also"></a>另请参阅

- [面向开发人员的 Project](https://msdn.microsoft.com/office/aa905469)
- [Office 开发人员中心](https://dev.office.com)
- [Visual Studio开发人员中心](https://msdn.microsoft.com/vstudio/aa718325.aspx)
- [ClickOnce安全性和部署](https://msdn.microsoft.com/library/t71a733d.aspx)
- [可用域引用](https://support.office.com/en-us/article/available-fields-reference-615a4563-1cc3-40f4-b66f-1b17e793a460)

