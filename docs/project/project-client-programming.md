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
- vba，project 对象模型，项目，可编程性可编程性 （英文）、 Project VBA、 Visual Basic for Applications Project 对象模型，VBA，对象模型，VBA，Visual Basic for Applications
localization_priority: Normal
ms.assetid: 0ad49ff6-8dff-4379-a52c-d292c53c2bc0
description: Project 2013 桌面客户端应用程序 — Project Standard 2013 和 Project Professional 2013 — 可以自定义和扩展通过使用 VBA 编写宏。 Visual Studio 2012 可用于自定义功能区用户界面和创建新扩展性模型的项目中的任务窗格的通用的 Office 2013 平台上构建的 Office 加载项允许的复杂加载宏。 Project Standard 2013 和 Project Professional 2013 可以运行常规 Office 加载项，并使用任务窗格的加载专门为项目以与 SharePoint、 其他网站和 web 应用程序和外部数据集成开发。
ms.openlocfilehash: e8604b4d479d0c64f8d45ad2363d7391d57408ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779548"
---
# <a name="project-client-programming"></a>Project 客户端编程

Project 2013 桌面客户端应用程序 — Project Standard 2013 和 Project Professional 2013 — 可以自定义和扩展通过使用 VBA 编写宏。 Visual Studio 2012 可用于自定义功能区用户界面和创建新扩展性模型的项目中的任务窗格的通用的 Office 2013 平台上构建的 Office 加载项允许的复杂加载宏。 Project Standard 2013 和 Project Professional 2013 可以运行常规 Office 加载项，并使用任务窗格的加载专门为项目以与 SharePoint、 其他网站和 web 应用程序和外部数据集成开发。
  
 **移动到 Visual Studio**VBA 可用于录制宏和开发相对简单自动化解决方案。 若要开发任务窗格的加载项，加载项和更多的复杂、 安全、 可扩展和轻松部署的解决方案，我们建议您使用 Visual Studio 2012。 Microsoft.NET Framework 4.0 和 Project 2013 主互操作程序集提供有关开发和部署解决方案的自动化和集成 Project 2013 桌面客户端的很多好处。 
  
> [!NOTE]
> 可以使用 Visual Studio 2010 来开发项目外接程序。但是，Visual Studio 2012 包括模板和旨在创建 Office 加载项的客户端的扩展。 
  
Project 2013 中的 VBA **MSProject**对象模型在本质上与 Visual Studio 2013 (也称为 VSTO) 的 Office 开发人员工具的**Microsoft.Office.Interop.MSProject**对象模型的托管代码解决方案相同。 Visual Studio 2012 包含模板，用于开发应用程序级加载项的 Project 2010 和 Project 2013 （Project Standard 或 Project Professional 版本）。 VSTO 和 Visual Studio 2012 Office 开发人员工具简化开发、 测试和部署高级的集成解决方案可以使用 Project 桌面客户端和其他 Office 2013 应用程序，并将与 SharePoint 网站、 列表、 集成和工作流。 
  
可以在 Office 商店中销售任务窗格的加载项和面向 Office 和 SharePoint 的其他外接 (请参阅[http://office.microsoft.com/store/](http://office.microsoft.com/en-us/store/)) 与 Project Online 和本地安装一起使用。 无法在 Office 商店; 分布式 VBA 宏和 VSTO 外接程序它们旨在用于本地 Project Standard 和 Project Professional。 您可以将分发在项目中的 VBA 宏。MPP 文件，将其安装在您的计算机上的 Global.MPT 文件，或分发更新 Project Server 2013 中的企业全局模板中。 VSTO 加载项可通过[ClickOnce](http://msdn.microsoft.com/en-us/library/t71a733d.aspx)部署时，它使轻松更新更安全地分发。 
  
## <a name="reference"></a>参考

[项目的 VBA 开发人员参考](http://msdn.microsoft.com/en-us/library/ee861523%28office.15%29.aspx)包含介绍性和 VBA 帮助文章。 
  
## <a name="related-sections"></a>相关章节

[Project Server 2013 体系结构](project-server-2013-architecture.md)显示 Project 客户端与 Project Server 的交互方式。 
  
## <a name="see-also"></a>另请参阅



[面向开发人员的 project](http://msdn.microsoft.com/en-us/office/aa905469)
  
[Office 开发中心](https://dev.office.com)
  
[Visual Studio 开发中心](http://msdn.microsoft.com/en-us/vstudio/aa718325.aspx)
  
[ClickOnce 安全和部署](http://msdn.microsoft.com/en-us/library/t71a733d.aspx)
  
[可用字段引用](http://office.microsoft.com/en-us/project-help/available-fields-reference-HA102749299.aspx?CTT=1)

