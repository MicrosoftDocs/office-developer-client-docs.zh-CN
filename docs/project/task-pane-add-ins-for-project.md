---
title: Project 任务窗格加载项
manager: soliver
ms.date: 09/10/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 44712b7c-aead-433d-8c0e-76407264166c
description: Project Standard 2013 和 Project Professional 2013 都支持任务窗格Office外接程序。您可以使用任务窗格外接程序将项目中的项目、任务、资源和查看数据与其他 Office 2013 客户端应用程序、SharePoint 应用程序、Web 部件、其他网页和外部数据集成。
ms.openlocfilehash: 26942cab1d1b127872a230a46fbc6242ab27b754
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330014"
---
# <a name="task-pane-add-ins-for-project"></a>Project 任务窗格加载项

Project Standard 2013 和 Project Professional 2013 都支持任务窗格Office外接程序。您可以使用任务窗格外接程序将项目中的项目、任务、资源和查看数据与其他 Office 2013 客户端应用程序、SharePoint 应用程序、Web 部件、其他网页和外部数据集成。
  
Office外接程序是一种可扩展性模型，在几个 Office 2013 客户端应用程序中受支持。 完整的外接程序平台包括上下文、内容和任务窗格外接程序类型。 Outlook 2013 支持邮件外接程序，它可以在电子邮件或日历约会项目（与项目内容相关）中显示网页。 Word 2013 和 Excel 2013 支持内容外接程序，该外接程序可以将网页显示为文档中的嵌入内容。 Word 2013、Excel 2013 和 Project Professional 2013 支持任务窗格外接程序，它可以在任务窗格中显示网页，其中的内容与项目中的上下文信息相关。
  
例如，Project加载项可以汇总活动项目中的数据，并显示有关选定任务或资源的其他数据。 外接程序中的数据可能来自外部源，如 SharePoint 列表、Project Server 数据库中的报告表、Web 服务或其他企业应用程序。 可以使用 HTML 5、JavaScript、JQuery 和其他 JavaScript 库开发任务窗格外接程序。 任务窗格外接程序不直接支持ActiveX、Silverlight 或 Flash 组件。 尽管Office加载项可以使用 **IFrame** 元素访问使用 ASP.NET 和 .NET Framework 4.5 库的服务器端 Web 应用程序，但建议也不支持此类解决方案。 加载项可以开发为本地保存数据或将数据写入外部位置。 
  
> [!NOTE]
> 任务Project加载项可以使用 OAuth 身份验证Project Online访问任务窗格中的数据。 使用 Project Professional 2013，您可以开发访问 Project Server 2013 本地安装以及本地或联机 SharePoint 2013 的任务窗格外接程序。 例如，请参阅编程[Project](https://blogs.msdn.com/b/project_programmability/archive/2012/11/02/connecting-a-project-task-pane-app-to-pwa.aspx)中的将任务窗格PWA连接到Project加载项。 > Project Standard 2013 不支持与 Project Server 数据或与 Project Server 同步的 SharePoint 任务列表直接集成。 
  
有关适用于 Office 2013 的外接程序Office和 SharePoint[外接程序](https://msdn.microsoft.com/library/office/fp161507%28v=office.15%29)。 
  
## <a name="developing-task-pane-add-ins"></a>开发任务窗格加载项

适用于外接程序和Office SharePoint开发人员文档包括全面的文章和参考。 有关为 Project Professional 2013 和其他 Office 2013 客户端应用程序开发外接程序的简介，以及 JavaScript 参考和 XML 清单参考，请参阅 Office [Add-ins。](https://msdn.microsoft.com/library/office/apps/jj220060%28v=office.15%29)
  
Project 2013 SDK 下载包括 **Project OM Test** 示例外接程序，该外接程序演示如何获取任务、资源和视图的 GUID，如何获取活动项目的属性以及如何设置任务、资源或视图选择更改事件处理程序。 在文件中提取和安装 SDK 和示例Project2013SDK.msi，请参阅子  `\Samples\Apps\Copy_to_AppSource_FileShare` 目录和  `\Samples\Apps\Copy_to_AppManifests_FileShare` 子目录。 the JSOMCall.html sample uses JavaScript functions in the office.js file and project-15.js file， which are included in the download. 可以使用相应调试文件 （office.debug.js 和project-15.debug.js）来检查这些函数。 
  
2013 HelloProject_OData 2013 Project Professional外接程序是使用 2012 Visual Studio开发的。  外接程序使用 **ProjectData** 服务的 REST 查询获取项目成本和其他信息的报告数据，然后将当前项目与项目中所有项目的Project Web App。 
  
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [Project 任务窗格加载项](https://msdn.microsoft.com/library/office/apps/fp161143%28v=office.15%29)
    
- [将Project任务窗格加载项连接到PWA](https://blogs.msdn.com/b/project_programmability/archive/2012/11/02/connecting-a-project-task-pane-app-to-pwa.aspx)
    
- [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435%20)
    
- [Office 和 SharePoint 外接程序](https://msdn.microsoft.com/library/office/fp161507%28v=office.15%29)
    
- [Office 加载项](https://msdn.microsoft.com/library/office/apps/jj220060%28v=office.15%29)
    

