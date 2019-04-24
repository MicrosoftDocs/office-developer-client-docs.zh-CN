---
title: Project 2013 的客户端对象模型 (CSOM)
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
ms.assetid: 716325eb-b092-4934-921f-84129d0a1f5f
description: Project Server 2013 客户端对象模型 (CSOM) 实施常见服务器功能。 Project Server CSOM 包括 Microsoft .NET CSOM、Microsoft Silverlight CSOM、Windows Phone 8 CSOM 和 JavaScript 对象模型 (JSOM)。 此外，CSOM 还包括支持 REST 接口的 OData 服务。 REST 接口主要用于在非 Windows 平台（如 iOS 和 Android）上开发应用。
localization_priority: Priority
ms.openlocfilehash: b722e316f5cb2054eb6522297c5c5ef3e75f9fa4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355200"
---
# <a name="client-side-object-model-csom-for-project-2013"></a>Project 2013 的客户端对象模型 (CSOM)

Project Server 2013 客户端对象模型 (CSOM) 实施常见服务器功能。 Project Server CSOM 包括 Microsoft .NET CSOM、Microsoft Silverlight CSOM、Windows Phone 8 CSOM 和 JavaScript 对象模型 (JSOM)。 此外，CSOM 还包括支持 REST 接口的 OData 服务。 REST 接口主要用于在非 Windows 平台（如 iOS 和 Android）上开发应用。
  
> [!NOTE]
> Project Online 解决方案必须使用 CSOM。 但是，本地应用可以使用 CSOM 或 Project Server Interface (PSI)。 如果 CSOM 中包括你计划使用的功能，那么我们建议你使用 CSOM 来开发新应用。 
  
在 CSOM 扩展中，**ProjectContext** 对象提供服务器内容和功能的入口点。 .NET CSOM、Silverlight CSOM 和 Windows Phone CSOM 使用 [Microsoft.ProjectServer.Client.ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx) 对象，而 JSOM 使用 **PS.ProjectContext** 对象。 通过 **ProjectContext** 属性可直接访问当前 Project Web App 网站集中的核心 Project Server 对象。 有关 CSOM 程序集和 JavaScript 文件的信息，请参阅 [Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx)。 
  
 **应用和安全模型**在 Project Server 2013 和 Project Online 中，应用必须使用 CSOM 进行 CRUD（创建、读取、更新和删除）操作。 在 SharePoint 2013 中，Project 应用不能使用仅应用身份验证。 Project Server 应用需要特定的权限请求范围，该范围指定是代表谁运行命令。 
  
 **REST 查询**无需使用元数据即可创建 CSOM OData 服务的 REST 查询。 一些第三方工具启用使用 CSOM 的 .NET 程序集来开发适用于其他设备的应用。 例如，搜索 Internet 上的“适用于 iOS 或 Android 的跨平台 .NET 开发工具”。 
  
> [!NOTE]
> 尽管 **ProjectData** 报告服务的 `$metadata` 选项有效 (`https://ServerName/pwaName/_api/ProjectData/$metadata`)，但 CSOM 的 **ProjectServer** 服务的 `$metadata` 选项会在 Project Server 2013 的发行版中删除。 若要查找可用作 REST 终结点的 CSOM 对象和成员，请参阅[适用于 Project Server 2013 的 JavaScript 库和 REST 引用](javascript-library-and-rest-reference-for-project-server-2013.md)。 
  
若要通过 REST 接口查看 CSOM 中的可用实体，可以使用 `https://ServerName/pwaName/_api/ProjectServer` 查询。 对于 REST 查询，**ProjectServer** 实体将密切镜像 Microsoft.ProjectServer.Client.dll 托管程序集中的 [ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx) 对象的属性以及 JSOM 中的 [PS.ProjectContext](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx) 对象。 例如，可以通过浏览器使用以下查询（每个查询都使用相同的 `https://ServerName/pwaName/_api` URL 前缀）从 CSOM 中获取有关 Project Web App 中的项目的信息、指定项目中的工作分配以及指定资源的指定工作分配的任务名称。 GUID 是 **Project.Id**、**EnterpriseResource.Id** 和 **Assignment.Id** 的示例值。
  
```HTML
/ProjectServer/Projects
/ProjectServer/Projects('263fc8d7-427c-e111-92fc-00155d3ba208')/Assignments
/ProjectServer/EnterpriseResources('28eeb2b5-fe74-4efc-aa35-6a64514d1526')/Assignments('a2eafeb5-437c-e111-92fc-00155d3ba208')/Task?$select=Name
```

与 **ProjectData** 服务的 OData 接口不同（此接口对于报告是只读的），可以结合使用 REST 查询和 **ProjectServer** 服务来执行 CRUD 操作。 Project Server CSOM 的 REST 查询主要是为 Windows 桌面以外的其他平台（如 Windows RT、iOS 和 Android）设计的。 对于 Windows 桌面和服务器平台（如 Windows 7、Windows 8 和 Windows Server 2008 R2），可以使用 CSOM 托管程序集。 对于 Web 应用，可以使用 JavaScript 的 PS.js。 有关使用 REST 查询执行 CRUD 操作的信息，请参阅 SharePoint 2013 SDK 中的[在 SharePoint REST 请求中使用 OData 查询操作](https://msdn.microsoft.com/library/d4b5c277-ed50-420c-8a9b-860342284b72%28Office.15%29.aspx)主题。 有关使用 **ProjectData** 服务的信息，请参阅[查询 Project 报告数据的 OData 数据源](https://msdn.microsoft.com/library/office/jj163048.aspx)。
  
表 1 列出了代表 Project Server 对象的 **ProjectContext** 属性。 可以使用这些对象检索其他 Project Server 2013 实体，例如工作分配和任务。 
  
**表 1. 提供对 CSOM 和 JSOM 中的 Project Server 对象的访问权的 ProjectContext 属性**

|**CSOM（.NET、Silverlight 和 Windows Phone）**|**JSOM**|
|:-----|:-----|
|[CustomFields](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.CustomFields.aspx) <br/> |customFields  <br/> |
|[EnterpriseProjectTypes](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.EnterpriseProjectTypes.aspx) <br/> |enterpriseProjectTypes  <br/> |
|[EnterpriseResources](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.EnterpriseResources.aspx) <br/> |enterpriseResources  <br/> |
|[EntityTypes](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.EntityTypes.aspx) <br/> |entityTypes  <br/> |
|[EventHandlers](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.EventHandlers.aspx) <br/> |eventHandlers  <br/> |
|[Events](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.Events.aspx) <br/> |events  <br/> |
|[LookupTables](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.LookupTables.aspx) <br/> |lookupTables  <br/> |
|[Phases](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.Phases.aspx) <br/> |phases  <br/> |
|[Projects](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.Projects.aspx) <br/> |projects  <br/> |
|[Stages](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.Stages.aspx) <br/> |stages  <br/> |
|[WorkflowActivities](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.WorkflowActivities.aspx) <br/> |workflowActivities  <br/> |
|[WorkflowDesigner](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.WorkflowDesigner.aspx) <br/> |workflowDesigner  <br/> |
   
## <a name="in-this-section"></a>本节内容

[Project Server CSOM 和 .NET 入门](getting-started-with-the-project-server-csom-and-net.md)提供了有关 Project Server CSOM 和 .NET 的概述信息、有关如何在 Visual Studio 2012 中创建简单 .NET CSOM 扩展的说明以及支持的代码示例。 
  
[Project Server 2013 JavaScript 对象模型入门](getting-started-with-the-project-server-2013-javascript-object-model.md)提供了有关 Project Server JSOM 的概述信息、有关如何在 Visual Studio 2012 中创建简单 JSOM 扩展的说明以及支持的代码示例。 
  
此外，查看这些介绍如何使用 CSOM 的文章：
  
- [批量更新自定义字段并通过 Project Online 中的工作流创建项目网站](bulk-update-custom-fields-and-create-project-sites-from-workflow-in-project.md)
    
- [使用 JavaScript 对象模型处理项目](create-retrieve-update-delete-projects-using-project-server-javascript.md)
    
> [!NOTE]
> 此外，还可以使用 Visual Studio 2010 通过 CSOM 进行 .NET Framework 4 开发。 
  
## <a name="reference"></a>引用

[Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx)
  
## <a name="see-also"></a>另请参阅



[Project Server 2013 体系结构](project-server-2013-architecture.md)


[在 SharePoint 2013 中选择正确的 API 集](https://msdn.microsoft.com/library/f36645da-77c5-47f1-a2ca-13d4b62b320d%28Office.15%29.aspx)

