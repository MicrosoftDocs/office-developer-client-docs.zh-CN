---
title: Project 2013 的客户端对象模型 (CSOM)
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 716325eb-b092-4934-921f-84129d0a1f5f
description: Project Server 2013 客户端对象模型 (CSOM) 实现常见的服务器功能。 Project Server CSOM 包括 Microsoft.NET CSOM、 Microsoft Silverlight CSOM、 Windows Phone 8 CSOM 和 JavaScript 对象模型 (JSOM)。 此外，CSOM 包括启用 REST 接口的 OData 服务。 在 REST 界面主要用于开发 iOS 和 Android 如非 Windows 平台上的应用程序。
ms.openlocfilehash: 8be603fbee35f228dea0fa6b6be087b8e09c30e5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394445"
---
# <a name="client-side-object-model-csom-for-project-2013"></a>Project 2013 的客户端对象模型 (CSOM)

Project Server 2013 客户端对象模型 (CSOM) 实现常见的服务器功能。 Project Server CSOM 包括 Microsoft.NET CSOM、 Microsoft Silverlight CSOM、 Windows Phone 8 CSOM 和 JavaScript 对象模型 (JSOM)。 此外，CSOM 包括启用 REST 接口的 OData 服务。 在 REST 界面主要用于开发 iOS 和 Android 如非 Windows 平台上的应用程序。
  
> [!NOTE]
> For Project Online 中的解决方案必须使用 CSOM。 但是，本地应用程序可以使用 CSOM 或 Project Server 接口 (PSI)。 如果 CSOM 包括您打算使用的功能，我们建议您对新的应用程序使用 CSOM。 
  
在 CSOM 扩展**ProjectContext**对象提供对服务器内容和功能的入口点。 .NET CSOM 和 Silverlight CSOM，Windows Phone CSOM 使用[Microsoft.ProjectServer.Client.ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx)对象，并 JSOM 使用**PS.ProjectContext**对象。 **ProjectContext**属性提供直接访问 Project Web App 网站集中当前的核心 Project Server 对象。 有关 CSOM 程序集和 JavaScript 文件的位置，请参阅[Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx) 。 
  
 **应用程序和安全模型**应用程序必须为 CRUD 使用 CSOM （创建、 读取、 更新、 删除） 与 Project Server 2013 和 Project Online 的操作。 Project 应用程序在 SharePoint 2013 中不使用仅应用程序身份验证模型。 Project Server 应用程序需要指定命令正在运行的名义特定的权限请求范围。 
  
 **REST 查询**不使用元数据，可以创建 REST 查询的 CSOM OData 服务。 某些第三方工具启用使用 CSOM 的.NET 程序集开发应用程序其他设备。 例如，搜索 Internet 上的"跨平台.NET 开发工具的 iOS 或 Android。" 
  
> [!NOTE]
> 尽管`$metadata` **ProjectData**报告服务有效的选项 ( `https://ServerName/pwaName/_api/ProjectData/$metadata`)，则`$metadata`选项的 CSOM 的**ProjectServer**服务已在 Project Server 2013 的发行版。 若要查找的 CSOM 对象和成员可用作 REST 终结点，请参阅[JavaScript 库和 REST 参考 （英文） Project Server 2013](javascript-library-and-rest-reference-for-project-server-2013.md)。 
  
若要查看通过 REST 界面 CSOM 中可用的实体，您可以使用`https://ServerName/pwaName/_api/ProjectServer`查询。 对于 REST 查询， **ProjectServer**实体清楚地反映了在托管的 Microsoft.ProjectServer.Client.dll 程序和[PS. [ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx)对象的属性ProjectContext](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx)中 JSOM 对象。 例如，使用您的浏览器，用于通过使用下面的查询从 Project Web App，中分配一个指定的项目，并指定资源，指定工作分配的任务名称中的项目有关 CSOM 获取信息 (每个查询使用同一`https://ServerName/pwaName/_api`URL 前缀)。 Guid 是**Project.Id**、 **EnterpriseResource.Id**，和**Assignment.Id**示例值。
  
```HTML
/ProjectServer/Projects
/ProjectServer/Projects('263fc8d7-427c-e111-92fc-00155d3ba208')/Assignments
/ProjectServer/EnterpriseResources('28eeb2b5-fe74-4efc-aa35-6a64514d1526')/Assignments('a2eafeb5-437c-e111-92fc-00155d3ba208')/Task?$select=Name
```

与不同的 OData 接口用于**ProjectData**服务，它是只读的报告，您可以使用**ProjectServer**服务的 REST 查询的 CRUD 操作。 Project Server CSOM 的 REST 查询主要用于 Windows 桌面上，如 Windows RT、 iOS 和 Android 之外的平台。 对于 Windows 台式机和服务器平台，如 Windows 7、 Windows 8 和 Windows Server 2008 R2，您可以使用 CSOM 托管程序集。 对于 web 应用程序，您可以用于 PS.js JavaScript。 有关执行 CRUD 操作使用 REST 查询的信息，请参阅 SharePoint 2013 SDK 中的[SharePoint REST 请求中的使用 OData 查询操作](https://msdn.microsoft.com/library/d4b5c277-ed50-420c-8a9b-860342284b72%28Office.15%29.aspx)主题。 有关使用**ProjectData**服务的信息，请参阅[查询 OData 源的报告数据的项目](https://msdn.microsoft.com/library/office/jj163048.aspx)。
  
表 1 列出**ProjectContext**属性表示 Project Server 对象。 您可以使用这些对象来检索其他 Project Server 2013 实体，如工作分配和任务。 
  
**表 1. 提供对 CSOM 和 JSOM 中的 Project Server 对象的访问权的 ProjectContext 属性**

|**CSOM（.NET、Silverlight 和 Windows Phone）**|**JSOM**|
|:-----|:-----|
|[CustomFields](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.CustomFields.aspx) <br/> |customFields  <br/> |
|[EnterpriseProjectTypes](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.EnterpriseProjectTypes.aspx) <br/> |enterpriseProjectTypes  <br/> |
|[EnterpriseResources](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.EnterpriseResources.aspx) <br/> |enterpriseResources  <br/> |
|[EntityTypes](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.EntityTypes.aspx) <br/> |entityTypes  <br/> |
|[事件处理](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.EventHandlers.aspx) <br/> |事件处理  <br/> |
|[事件](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.Events.aspx) <br/> |events  <br/> |
|[将查找表](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.LookupTables.aspx) <br/> |将查找表  <br/> |
|[阶段](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.Phases.aspx) <br/> |phases  <br/> |
|[Projects](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.Projects.aspx) <br/> |projects  <br/> |
|[阶段](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.Stages.aspx) <br/> |stages  <br/> |
|[WorkflowActivities](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.WorkflowActivities.aspx) <br/> |workflowActivities  <br/> |
|[WorkflowDesigner](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.WorkflowDesigner.aspx) <br/> |workflowDesigner  <br/> |
   
## <a name="in-this-section"></a>本节内容

[与 Project Server CSOM 和.NET 入门](getting-started-with-the-project-server-csom-and-net.md)提供了有关 Project Server CSOM 和.NET，说明有关如何在 Visual Studio 2012 和支持的代码示例中创建简单.NET CSOM 扩展的概述信息。 
  
[Getting started 与 Project Server 2013 JavaScript 对象模型](getting-started-with-the-project-server-2013-javascript-object-model.md)提供了有关 Project Server JSOM，说明有关如何在 Visual Studio 2012 和支持的代码示例中创建简单 JSOM 扩展的概述信息。 
  
此外，查看这些介绍如何使用 CSOM 的文章：
  
- [批量更新自定义字段并从 Project Online 中的工作流创建项目网站](bulk-update-custom-fields-and-create-project-sites-from-workflow-in-project.md)
    
- [使用 JavaScript 对象模型处理项目](create-retrieve-update-delete-projects-using-project-server-javascript.md)
    
> [!NOTE]
> 您还可以使用.NET Framework 4 CSOM 开发的 Visual Studio 2010。 
  
## <a name="reference"></a>参考

[Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx)
  
## <a name="see-also"></a>另请参阅



[Project Server 2013 体系结构](project-server-2013-architecture.md)


[在 SharePoint 2013 中选择正确的 API 集](https://msdn.microsoft.com/library/f36645da-77c5-47f1-a2ca-13d4b62b320d%28Office.15%29.aspx)

