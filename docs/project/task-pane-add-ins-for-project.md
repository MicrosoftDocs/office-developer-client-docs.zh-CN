---
title: Project 任务窗格加载项
manager: soliver
ms.date: 09/10/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 44712b7c-aead-433d-8c0e-76407264166c
description: project Standard 2013 and project Professional 2013 都支持任务窗格 Office 外接程序。您可以使用任务窗格外接程序, 将项目中的项目、任务、资源和视图数据与其他 Office 2013 客户端应用程序、SharePoint 应用程序、Web 部件、其他网页和外部数据集成。
ms.openlocfilehash: 26942cab1d1b127872a230a46fbc6242ab27b754
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330014"
---
# <a name="task-pane-add-ins-for-project"></a>Project 任务窗格加载项

project Standard 2013 and project Professional 2013 都支持任务窗格 Office 外接程序。您可以使用任务窗格外接程序, 将项目中的项目、任务、资源和视图数据与其他 Office 2013 客户端应用程序、SharePoint 应用程序、Web 部件、其他网页和外部数据集成。
  
office 加载项是几个 office 2013 客户端应用程序支持的可扩展模型。 完整的外接平台包括上下文、内容和任务窗格加载项类型。 Outlook 2013 支持邮件加载项, 该加载项可以在电子邮件或日历约会项目中显示与项目内容相关的网页。 Word 2013 和 Excel 2013 支持内容外接程序, 可将网页显示为文档中的嵌入内容。 Word 2013、Excel 2013 和 Project Professional 2013 支持任务窗格外接程序, 它可以在任务窗格中显示一个网页, 其中的内容与项目中的上下文信息相关。
  
例如, 项目加载项可以汇总活动项目中的数据, 并显示有关所选任务或资源的其他数据。 外接程序中的相关数据可以来自外部源, 如 SharePoint 列表、Project Server 数据库中的报告表、web 服务或其他企业应用程序。 可以使用 HTML 5、JavaScript、JQuery 和其他 JavaScript 库来开发任务窗格加载项。 任务窗格加载项不直接支持 ActiveX、Silverlight 或 Flash 组件。 尽管 Office 加载项可以使用**IFrame**元素来访问使用 ASP.NET 和 .net Framework 4.5 库的服务器端 web 应用程序, 但不建议也不支持该类型的解决方案。 可以开发外接程序以在本地保存数据, 也可以将数据写入外部位置。 
  
> [!NOTE]
> 任务窗格项目外接程序可以使用 OAuth 身份验证访问 project Online 中的数据。 使用 project Professional 2013, 您可以开发可访问 Project Server 2013 和本地或联机 SharePoint 2013 的本地安装的任务窗格外接程序。 例如, 请参阅将[project 任务窗格外接程序连接到](https://blogs.msdn.com/b/project_programmability/archive/2012/11/02/connecting-a-project-task-pane-app-to-pwa.aspx)project Programmibility 博客中的 PWA。 > 项目 Standard 2013 不支持与 project server 数据或与 project server 同步的 SharePoint 任务列表的直接集成。 
  
有关 office 2013 外接程序的详细信息, 请参阅[office 和 SharePoint 外接程序](https://msdn.microsoft.com/library/office/fp161507%28v=office.15%29)。 
  
## <a name="developing-task-pane-add-ins"></a>开发任务窗格外接程序

Office 和 SharePoint 外接程序的开发人员文档包括全面的文章和参考。 有关开发适用于 Project Professional 2013 和其他 Office 2013 客户端应用程序的外接程序以及 JavaScript 参考和 XML 清单参考的简介, 请参阅[Office 外接程序](https://msdn.microsoft.com/library/office/apps/jj220060%28v=office.15%29)。
  
project 2013 SDK 下载包含**project OM 测试**示例外接程序, 该外接程序演示如何获取任务、资源和视图的 GUID、如何获取活动项目的属性, 以及如何设置任务、资源或视图选择更改事件处理程序。 当您在 Project2013SDK 文件中提取并安装 SDK 和示例时, 请参阅`\Samples\Apps\Copy_to_AppSource_FileShare`子目录和`\Samples\Apps\Copy_to_AppManifests_FileShare`子目录。 jsomcall.html 示例使用 office .js 文件和 project-15.js 文件中的 JavaScript 函数, 这些函数包含在下载内容中。 可以使用相应调试文件 （office.debug.js 和project-15.debug.js）来检查这些函数。 
  
Project Professional 2013 的**HelloProject_OData**示例外接程序是使用 Visual Studio 2012 开发的。 外接程序使用**ProjectData**服务的 REST 查询获取项目成本和其他信息的报告数据, 然后将当前项目与 project Web App 中所有项目的平均值进行比较。 
  
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [Project 任务窗格加载项](https://msdn.microsoft.com/library/office/apps/fp161143%28v=office.15%29)
    
- [将 Project 任务窗格加载项连接到 PWA](https://blogs.msdn.com/b/project_programmability/archive/2012/11/02/connecting-a-project-task-pane-app-to-pwa.aspx)
    
- [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435%20)
    
- [Office 和 SharePoint 外接程序](https://msdn.microsoft.com/library/office/fp161507%28v=office.15%29)
    
- [Office 加载项](https://msdn.microsoft.com/library/office/apps/jj220060%28v=office.15%29)
    

