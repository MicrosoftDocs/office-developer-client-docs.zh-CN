---
title: Project 任务窗格加载项
manager: soliver
ms.date: 09/10/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 44712b7c-aead-433d-8c0e-76407264166c
description: Project Standard 2013 和 Project Professional 2013 都支持任务窗格 Office 加载项。您可以使用任务窗格的加载项集成项目、 任务、 资源，并与其他 Office 2013 客户端应用程序、 SharePoint 应用程序、 Web 部件、 其他网页和外部数据项目中查看数据。
ms.openlocfilehash: 26942cab1d1b127872a230a46fbc6242ab27b754
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396013"
---
# <a name="task-pane-add-ins-for-project"></a>Project 任务窗格加载项

Project Standard 2013 和 Project Professional 2013 都支持任务窗格 Office 加载项。您可以使用任务窗格的加载项集成项目、 任务、 资源，并与其他 Office 2013 客户端应用程序、 SharePoint 应用程序、 Web 部件、 其他网页和外部数据项目中查看数据。
  
Office 加载项是某些 Office 2013 客户端应用程序中支持的扩展性模型。 完整外接程序平台包括上下文、 内容和任务窗格外接程序类型。 Outlook 2013 支持邮件加载项，其中可以显示一封电子邮件中的网页或项目中的内容相关的日历约会项。 Word 和 Excel 2013 支持内容加载项，其中可以显示为嵌入文档中的内容的网页。 Word、 Excel 2013 和 Project Professional 2013 支持任务窗格的加载，其内容与项目中的上下文信息任务窗格中可以显示网页。
  
例如，项目加载项可以汇总活动项目中的数据并显示有关选定的任务或资源的其他数据。 外接程序中的相关的数据可以来自 SharePoint 列表报告表中的 Project Server 数据库、 web 服务或其他企业应用程序等外部源。 任务窗格中加载项可以开发与 HTML 5、 JavaScript、 JQuery 和其他 JavaScript 库。 任务窗格中加载项不直接支持 ActiveX、 Silverlight 或闪存组件。 虽然 Office 加载项可以使用**IFrame**元素以访问的服务器端 web 应用程序使用 ASP.NET 和.NET Framework 4.5 库，这种解决方案不推荐或支持。 外接程序可以开发保存本地数据或外部位置中写入数据。 
  
> [!NOTE]
> 任务窗格项目加载项可以访问数据从 Project Online 中使用 OAuth 身份验证。 您可以使用 Project Professional 2013 开发任务窗格的加载访问 Project Server 2013 和在本地或联机 SharePoint 2013 的这两个本地安装。 例如，请参阅[连接 Project 任务窗格添加到 PWA](https://blogs.msdn.com/b/project_programmability/archive/2012/11/02/connecting-a-project-task-pane-app-to-pwa.aspx)项目 Programmibility 博客中。 > Project Standard 2013 不支持与 Project Server 数据或与 Project Server 同步的 SharePoint 任务列表的直接集成。 
  
有关 Office 2013 加载项的详细信息，请参阅[Office 和 SharePoint 加载项](https://msdn.microsoft.com/library/office/fp161507%28v=office.15%29)。 
  
## <a name="developing-task-pane-add-ins"></a>开发任务窗格的加载项

面向 Office 和 SharePoint 加载项的开发人员文档包括全面文章和参考。 Project Professional 2013 和其他 Office 2013 客户端应用程序，以及 JavaScript 引用和 XML 清单引用开发加载项简介，请参阅[Office 加载项](https://msdn.microsoft.com/library/office/apps/jj220060%28v=office.15%29)。
  
Project 2013 SDK 下载包括**Project OM Test**示例外接程序显示如何获取任务、 资源和视图的 GUID、 如何获取活动项目的属性以及如何设置任务、 资源、 或查看所选内容更改事件处理程序。 当您提取并 Project2013SDK.msi 文件中安装的 SDK 和示例时，请参阅`\Samples\Apps\Copy_to_AppSource_FileShare`子目录和`\Samples\Apps\Copy_to_AppManifests_FileShare`子目录。 JSOMCall.html 示例使用下载中包含 office.js 文件和 project-15.js 文件中的 JavaScript 函数。 可以使用相应的调试文件（office.debug.js 和 project-15.debug.js）检查这些函数。 
  
**HelloProject_OData**示例外接程序 Project Professional 2013 开发使用 Visual Studio 2012。 外接程序使用**ProjectData**服务的 REST 查询以获取报告的项目成本数据和其他信息，然后将当前项目与 Project Web App 中的所有项目的平均值进行比较。 
  
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [Project 任务窗格加载项](https://msdn.microsoft.com/library/office/apps/fp161143%28v=office.15%29)
    
- [Project 任务窗格加载项连接到 PWA](https://blogs.msdn.com/b/project_programmability/archive/2012/11/02/connecting-a-project-task-pane-app-to-pwa.aspx)
    
- [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435%20)
    
- [Office 和 SharePoint 外接程序](https://msdn.microsoft.com/library/office/fp161507%28v=office.15%29)
    
- [Office 外接程序](https://msdn.microsoft.com/library/office/apps/jj220060%28v=office.15%29)
    

