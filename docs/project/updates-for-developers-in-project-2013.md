---
title: Project 中面向开发人员的更新
manager: soliver
ms.date: 09/29/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5b2b22cd-6e28-43a8-9092-b411da8bfb53
description: 新功能包括 Project 客户端的客户端对象模型 (CSOM)、 REST 接口、 OData 服务的报告、 远程事件接收器、 声明性工作流，和任务窗格的加载项。
ms.openlocfilehash: 0c4c3f9b4bb5852f2a620b2695c15de390ac9d78
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401760"
---
# <a name="updates-for-developers-in-project"></a>Project 中面向开发人员的更新

Project Server 2013 中的扩展性功能工作与外接程序 Project Online 和本地安装。 新功能包括 Project 客户端的客户端对象模型 (CSOM)、 REST 接口、 OData 服务的报告、 远程事件接收器、 声明性工作流，和任务窗格的加载项。 此外了解已弃用的功能不应使用新的开发。
  
Project Server 2013 基于引入与 Microsoft Office Project Server 2007 和 Project Server 2010 通过扩展的框架。 Project Server 2013 添加了已重构和简化从 Project Server 接口 (PSI) 中，并包括一个 JavaScript 库和.NET Framework 4 库的 Windows 应用程序、 Windows Phone 8 和 Microsoft Silverlight 的客户端对象模型 (CSOM)。 CSOM 用于 for Project Online 中，开发，还适用于内部部署 Project Server 安装。 

Project Server 数据库合并为单个数据库;您可以通过 OData 服务访问的联机报告表和视图。 CSOM 和 OData 服务包括代表性状态传输 (REST) 接口。 可以使用 SharePoint Designer 2013 创建 project Server 工作流。 Project Professional 2013 可以与 Project Server 报告数据、 SharePoint 任务列表和其他外部内容的任务窗格中使用 Office 加载项扩展性模型集成。 Project Standard 2013 可以使用任务窗格的加载项集成常规的外部内容。
  
有关图表和 Project Server 2013 中的主要更改详细信息，请参阅[Project Server 2013 体系结构](project-server-2013-architecture.md)。
  
> [!NOTE]
> Project Server 2013 构建在 SharePoint Server 2013 平台上，并且 Project 2013 包括何种为其他 Office 2013 应用程序相同的基础结构。 有关文档的模型的 SharePoint 加载项，基于 SharePoint 的工作流，Web 部件开发与其他 SharePoint 功能和文档的 Office 加载项，请参阅[SharePoint 加载项](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)、 [Office 加载项](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)和[SharePoint2013 开发概述](https://msdn.microsoft.com/library/jj164084%28office.15%29.aspx)。 
  
## <a name="major-new-features-in-project-2013"></a>Project 2013 的主要新增功能
<a name="pj15_WhatsNew_MajorNewFeatures"> </a>

Project Standard 2013 和 Project Professional 2013 中的新增功能包括改进的用户界面的匹配其他 Office 2013 应用程序并在 Windows 8，与艺术字对象对于报表，燃尽集成支持现代风格的用户界面报告和报告的新可编程性功能。 Project Professional 2013 启用更复杂的共享和同步任务窗格的加载还实现其他 Office 2013 应用程序，例如 Word、 Excel 和 Outlook 中以及在 SharePoint Server 2013 上的项目。
  
Project Server 2013 中有许多新功能。 某些没有主要可编程性文章，如 Project Web App 中新的时间线。 在 Microsoft Office Online 上的产品帮助和最终用户文档和目标为管理员和 Microsoft TechNet 上的 IT 专业人员的主题，将记录这些功能。 其他新功能，如改进的时间表，轻松第三方开发人员与时间表和进展状况通过 Project Server 接口 (PSI) 进行交互。
  
添加了 Project Online 和 Office 应用商店 (https://office.microsoft.com/store)的项目加载项是广泛的更改，其中的 Project Server 是可通过 Microsoft Azure 访问。 基于云的访问 Project Server 开发使用 Microsoft.NET Framework、 Microsoft Silverlight、 Windows Phone 和使用 JavaScript 的 web 应用程序外接程序中使用客户端对象模型 (CSOM)。 Project Online 要求是四个早期版本的 Project Server 数据库已合并到一个数据库。
  
Project Server 2013 性能和可扩展性等任务状态、 时间表和项目管理的许多方面得到改进。 Project Server 工作流是经过重新设计的 Windows Workflow Foundation (WF4) 版本 4。 使用.NET Framework 4 和使用 PSI 的 Windows Communication Foundation (WCF) 提高了安全性、 性能和可伸缩性。 例如，您可以使用配置文件，而不更改应用程序代码或重新编译更改基于 WCF 的应用程序的传输协议。 Project Web App 缓存许多其中数据不会更改会显著的 PSI 调用。
  
> [!NOTE]
> 对于与 Project Server 2013 的开发，可以与 Office 和 SharePoint 工具可的扩展本机可以创建外接程序的 Office 2013 产品中使用 Visual Studio。 Project Server 2013 需要完全启用的功能，如项目详细信息页面和基于 WCF 的应用程序开发的 Visual Studio。 在 Visual Studio SharePoint 工具扩展可以直接向 Project Web App 和其他 SharePoint 网站部署 Web 部件和其他 SharePoint 功能。 
>
> Visual Studio 不再需要开发自定义字段、 阶段、 阶段、 和可管理 Project Web App 中的企业项目类型使用的 Project Server 工作流。 尽管可以使用 Visual Studio 开发工作流，它们通常是更轻松和快速地使用 SharePoint Designer 创建。 Visual Studio 可用于需要访问 CSOM 或其他外部 Api 的工作流。 
  
### <a name="project-add-ins"></a>Project 加载项
<a name="pj15_WhatsNew_Apps"> </a>

通讯组和软件的市场营销具有已彻底改变与外接程序的概念。 Project 2013 的可以从公共 Office 商店中使其可供购买和下载或分布式 SharePoint 上专用目录中的加载项。 外接程序，通常执行少量相关任务的自我包含、 交互式程序。 项目加载项可以是任务窗格外接程序的 Project Standard 2013 或 Project Standard 2013 客户端或外接程序的 Project Server 2013 或 Project Online。
  
Project 桌面客户端外接程序的信息，请参阅[任务窗格中的加载项项目](#pj15_WhatsNew_Agave)。 有关 Project Server 2013 的示例，请参阅[创建 SharePoint 承载 Project Server 加载项](create-a-sharepoint-hosted-project-server-add-in.md)。 [Office 和 SharePoint 加载项 SDK](https://msdn.microsoft.com/library/fp161507.aspx)中的文章，除了[Office 博客](https://blogs.office.com/dev/)具有许多也是为 Project 2013 和 Project Online 相关的文章。 
  
Project Server 2013 的加载项可以使用同时在本地安装和 Project Online。 Project Server 加载项可以包括 Web 部件、 远程事件接收器和业务逻辑。 访问 Project Server 对象模型中加载项是通过 CSOM、 不 PSI。 数据存储可以是基于云的如与 SQL Azure、 外部如通过 Microsoft Business Connectivity Services (BCS)，使用本地数据库中，内部或混合。
  
#### <a name="add-in-security"></a>加载项安全

代表用户运行外接程序; 通常情况下，将执行外接程序所需的操作您未明确不要使用模拟或指定谁能运行外接程序。 操作不能超过运行外接程序的用户的权限级别。 
  
在 Visual Studio 2012 Office 开发人员工具，AppManifext.xml 文件具有的图形编辑器可在其中设置的权限请求范围。 例如，若要创建使项目经理更新其项目，在**AppManifest.xml**设计器窗格的**权限**选项卡上的外接程序选择**多个项目**的范围和**写入**权限。 如果外接程序用户具有项目经理权限，她可以运行外接程序其管理的项目。 AppManifest.xml 文件中的代码应如下所示： 
  
```XML
  <AppPermissionRequests>
    <AppPermissionRequest Scope="https://sharepoint/projectserver/projects" Right="Write" />
  </AppPermissionRequests>
```

**表 1。针对 Project Server 加载项的权限请求作用域**

|范围|权限|
|:-----|:-----|
|**Project Server** <br/> |**管理**（需要 Project Server 管理员权限。）  <br/> |
|**多个项目** <br/> |**读**、**写**(需要项目经理权限对于某些操作; basic 读取操作，例如任务工作分配的项目团队成员权限。)  <br/> |
|**单个项目** <br/> |**读**、**写**（至少需要项目团队成员权限；对项目中某些数据的访问权限取决于其他权限级别。）  <br/> |
|**企业资源** <br/> |**读**、**写**（需要资源经理权限。）  <br/> |
|**状态** <br/> |**SubmitStatus**（需要提交项目状态的权限。）  <br/> |
|**报告** <br/> |**读**（需要登录 Project Server 的权限。）  <br/> |
|**工作流** <br/> |**提升**（需要权限来运行工作流。 使用提升的权限，可在工作流中启用切换阶段阶段外接程序运行。 在外接程序中的业务逻辑控制阶段过渡）。  <br/> |
   
> [!NOTE]
> Project Server 2013 和 Project Online 不使用仅应用程序身份验证模型 SharePoint 2013 （请参阅[外接程序授权策略类型在 SharePoint 2013 中](https://msdn.microsoft.com/library/124879c7-a746-4c10-96a7-da76ad5327f0%28Office.15%29.aspx)） 中。 
  
有关开发的信息，分发、 承载和管理外接程序，请参阅[SharePoint 加载项](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)和[Office 加载项](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)和 SharePoint Server 2013 和 Office 2013 开发人员文档中的相关的主题。 有关权限请求范围的其他 SharePoint 加载项的信息，请参阅[SharePoint 2013 中的加载项权限](https://msdn.microsoft.com/library/5f7a8440-3c09-4cf8-83ec-c236bfa2d6c4%28Office.15%29.aspx)。
  
### <a name="integrating-with-sharepoint-server"></a>与 SharePoint Server 集成
<a name="pj15_WhatsNew_IntegrationWSS"> </a>

Project Web App 中的许多功能需要 SharePoint Server 2013 OAuth 和基于声明的身份验证、 Project Server 授权和权限通过 SharePoint 组，如同步 SharePoint 任务的项目中的新基础结构列表和 Project Server 声明性工作流。 Project Service 应用程序可与 SharePoint 场中的任何网站集相关联。 项目同步可以是与 SharePoint 任务列表，其中 SharePoint 将维护项目。 此外可以与 SharePoint 任务列表，其中 Project Server 维护完全控制同步企业项目。 有关体系结构图表和项目同步的说明，请参阅[Project Server 2013 体系结构](project-server-2013-architecture.md)。
  
SharePoint Server 2013 中有许多新功能。 有关详细信息，请参阅[SharePoint 开发人员 (英文）](https://msdn.microsoft.com/sharepoint)。
  
### <a name="integrating-with-workflows"></a>与工作流集成
<a name="pj15_WhatsNew_Workflow"> </a>

工作流是项目组合管理的核心功能。项目生命周期可包含长时间运行的跨多个阶段的过程。管理阶段包含项目建议、业务影响分析以及选择、创建、规划、管理和跟踪项目。
  
Project Server 2013 工作流构建在 SharePoint 2013 工作流平台上，使用 WF4。 与不同在早期版本，Project Server 2013 的声明性工作流可以使用 SharePoint Designer 2013 创建和可访问的内部部署和联机使用。 Project Server 工作流使用 OAuth 的 SharePoint 工作流安全模型，并且可以安装在 Project Web App 网站。 图 1 显示了 SharePoint Designer 2013，可以为进行需求管理阶段定义 Project Web App 中的位置向网站工作流添加阶段。
  
**图 1. 使用 SharePoint 设计器向 Project Web App 的工作流添加容器**

![添加到 SPD 中的工作流阶段](media/pj15_CreateWorkflowSPD_AddStageInSPD.gif "添加到 SPD 中的工作流阶段")

<br/>

通过在设计工具，可以是 SharePoint Designer 2013 或 Visual Studio 2012 中添加工作流阶段、 操作、 条件和其他元素生成声明性工作流。 然后，设计工具将工作流保存为 XAML 代码，解释在运行时。 在 Project Server 2013 内部部署或 Project Online 中，可以运行声明性工作流。 通过使用 Visual Studio 2012，还可以生成自定义操作和其他控件的窗体并保存具有多个 Project Web App 实例的重复使用的工作流模板。 SharePoint Designer 2013 可以使用 Visual Studio 2012 中创建的自定义操作。
  
Project Server 2013 工作流用作应用程序，其中管理员 — 拥有设计权限的 Project Web App 的人员 — 可以发布声明性工作流并将其与企业项目类型 (EPT)。 EPT 必须是企业项目，其中 Project Server 维护完全控制。 SharePoint 任务列表不能使用 Project Server 工作流。 
  
OAuth 使项目经理具有项目创建调用无需使用模拟的工作流的权限。 代表项目经理进行工作流呼叫到 Project Server，例如读取自定义域值来确定要执行的分支。 要阻止项目经理创建自动提升到的下一个阶段的工作流，请对将移到下一个工作流阶段的呼叫就运行工作流作者 （管理员）。 相比之下，旧的 Project Server 2010 工作流的用户进行模拟的呼叫通过工作流代理用户帐户，以获得整个工作流的管理员访问权限。
  
虽然 Project Server 2013 内部部署可以使用基于 WF3.5 已编译工作流，我们建议您升级到声明性工作流基于 WF4 旧的工作流。 较新的技术是更可伸缩且可靠。 业务分析师和 PMO 人员可以创建或使用 Visio 2013 更新工作流设计和实现无需使用 SharePoint Designer 2013 编码的 Project Server 工作流。
  
有关为 Project Web App 中创建声明性工作流的信息，请参阅[Getting started 开发 Project Server 工作流](getting-started-developing-project-server-workflows.md)。 SharePoint Designer 和 Visual Studio 工作流功能的比较，请参阅[使用 Visual Studio 开发 SharePoint 2013 工作流](https://msdn.microsoft.com/library/office/jj163199.aspx)。
  
### <a name="client-side-object-model"></a>客户端对象模型
<a name="pj15_WhatsNew_CSOM"> </a>

Project Online 中以编程方式访问需要基于 SharePoint CSOM CSOM。 Project Online 身份验证将与使用 Windows Live ID、 不 Project Server 表单身份验证或 Windows 身份验证的 OAuth。
  
以下是原则和 Project Server 2013 中 CSOM 的功能：
  
- CSOM 专为方便使用。 例如，方法和属性直接使用或提供的名称，而不需要许多 Guid， _changexml （英文）_ 参数，或传递了数据集的数据。 
    
- Project Server CSOM 基于第三方解决方案的最常见要求实现 PSI 功能的子集。
    
- CSOM 内部方式调用 PSI，但以不同的方式构成。例如，对所有状态更改的更新是通过 **StatusAssignmentCollection.SubmitAllStatusUpdates** 方法而不是通过用户的 **Statusing.SubmitStatus** PSI 方法或其他资源的 **SubmitStatusForResource** 方法完成的。 
    
- CSOM 可通过一个 WCF 服务 (Client.svc) 而不是 PSI 的 22 个公共服务进行访问。
    
- Project Server CSOM 的初始化是直接通过 Project Web App 的 URL，与[ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx)类不使用 WCF 引用或代理程序集。 
    
- CSOM 实现的多个客户端库和接口均受内部 SharePoint CSOM 基础结构的支持。这些客户端库和接口包括：
    
  - Microsoft.ProjectServer.Client.dll 程序集中的 Microsoft .NET 客户端库
    
  - Microsoft.ProjectServer.Client.Silverlight.dll 程序集中的 Silverlight 库
    
  - Microsoft.ProjectServer.Client.Phone.dll 程序集中的 Windows Phone 8 库
    
  - PS.js 文件或 PS.debug.js 文件中的 web 应用程序的 JavaScript 库
    
  - REST 终结点，使用 OData 协议进行访问
    
  - 对使用筛选的 LINQ 查询的本机支持，以限制返回的数据量
    
- Project Online 的解决方案和内部部署解决方案，独立于 PSI 和其他 Project Server 程序集，如 Microsoft.Office.Project.Server.Library.dll，可使用 CSOM。
    
- Project Server 2013 CSOM 的其他功能可能会考虑用于累积更新和 service pack，根据请求由 Project Server 合作伙伴和开发人员社区中。
    
> [!NOTE]
> CSOM 是第三方 Project Server 开发人员的首选接口。如果 CSOM 包括应用程序所需的功能，建议您使用 CSOM 开发新的应用程序。 
  
有关使用 CSOM 进行开发的信息，请参阅[Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)。 SharePoint 应用程序中的 REST 界面有关的信息，请参阅 SharePoint 2013 开发人员文档中的*编程使用 SharePoint REST 服务*。 
  
### <a name="changes-in-the-reporting-database"></a>报告数据库中的更改
<a name="pj15_WhatsNew_RDBChanges"> </a>

Project Server 2010 中的四个数据库合并到 Project Server 2013 中为单个 Project 数据库中。 将 Project 数据库的默认名称是 ProjectService。 报告表和视图保留其以前的名称，并且表和视图从草稿、 发布和存档数据库具有前缀`draft`， `pub`，和`ver`ProjectService 数据库中。 例如，已发布的项目表是出版物。MSP_PROJECTS。 
  
> [!IMPORTANT]
> 直接访问不支持草稿 (`draft`前缀)、 已发布 (`pub`)，和存档 (`ver`) 表和视图。 仅报告的表和视图，具有，应使用报告`dbo`前缀。 例如，dbo。MSP_EpmProject 表包含 Project Web App 实例中的项目的列表。 
>
> 实际上没有任何内容阻止您使用直接编程数据库访问来更新 Project 数据库中任何表和视图中的数据。您应注意，Project Professional 缓存、草稿和已发布数据的表以及报告表均依赖可被直接数据编辑中断的缓存同步协议。如果您使用直接访问更改数据损坏了 Project Server 数据库或损坏了 Project Professional 客户端缓存，则将收到产品支持无法帮助的警告！ 
  
Project Server 2013 介绍 OData 服务的联机和本地访问。 仅由的 OData 接口; 公开的联机报告表和视图供内部使用，您可以使用的 OData 接口，或直接访问报告的表和 SharePoint 场中 ProjectService 数据库中的视图。 Project Online 不支持多租户的数据库。 即多个 Project Web 应用程序的每个实例具有自己的 Project 数据库。 OData 服务内部报告的表和视图，运行 SQL 查询，并提供了 XML 或 JSON 负载。 有关 OData 服务的 Project Server 2013 中的报告和**ProjectData**架构引用的简介，请参阅[ProjectData-Project OData 服务引用](https://msdn.microsoft.com/library/office/jj163015.aspx)。
  
有关 OData 查询的常规信息，请参阅[OData: URI 约定](https://www.odata.org/documentation/)。 例如，您可以看到所有的 Project Web App 的项目名称其中开头在浏览器中使用下面的查询的"Test"的本地实例中的项目。 在浏览器页中，右键单击，然后单击**查看源文件**。
  
```html
https://ServerName /ProjectServerName /_api/ProjectData/Projects?$filter=startswith(ProjectName, 'Test') eq true
```

要导入 PowerPivot Excel 2013 中的项目数据，数据功能区上，选择**自其他来源**下拉列表菜单中**从 OData 数据源**。 在**数据连接向导**对话框中，键入https://ServerName/ProjectServerName/_api/ProjectData/在数据源位置，选择**下一步**，，然后选择在向导的**选择表**页的**项目**表。 命名和保存.odc 文件，然后选择**完成**。 在**导入数据**对话框中，选择**数据透视表报告**。 在 Excel 表中，选择字段的数据透视表行和您想要显示的列。
  
内部部署 Project Server 用户具有正确的权限，可以直接访问报告的表和视图 Microsoft SQL Server 创建报表，通过在 Project Server 2010 中一样。 Project Server 2013 中用户还可以通过 OData 接口访问本地申报表。 您可以检索联机 Project Server 数据或本地通过 OData 服务的 REST 终结点。 例如，dbo。MSP_PROJECT 表并 dbo。MSP_EpmProject_UserView 视图可用于报告。 任何表或视图的`draft`， `pub`，或`ver`前缀仅供内部使用 Project server，且未进行报告使用。 例如，草稿。MSP_TASKS 表并出版物。MSP_PROJECTS_WORKING_VIEW 视图未进行归档，以及是仅供内部使用。 
  
> [!NOTE]
> 您可以通过在单独数据库中添加表、视图、字段和存储过程来扩展内部报告。您不能在 Project Server 数据库中修改现有报告表和视图。 
  
报告表、 视图和项目数据库中的字段将记录在更高版本更新的 Project 2013 SDK 下载中的 HTML 帮助文件。 有关 OData XML 架构的**ProjectData**服务的文档，请参阅[ProjectData-Project OData 服务引用](https://msdn.microsoft.com/library/office/jj163015.aspx)。 报告表和 Project Server 2010 创建的视图的查询将在大多数情况下，使用 Project Server 2013 中的 Project 数据库。 与当前内部部署用户可以访问 SQL Server Analysis Services 中的 Project Server OLAP 多维数据集。 Project Online 中不可用 OLAP 多维数据集。
  
### <a name="task-pane-add-ins-in-project"></a>任务窗格中的加载项项目
<a name="pj15_WhatsNew_Agave"> </a>

Project Standard 2013 和 Project Professional 2013 支持任务窗格的加载，可以用于与集成并在网页中显示外部内容。 任务窗格显示网页内容有权通过 JavaScript 任务、 资源、 视图和常规项目数据。 项目的 JavaScript 对象模型可以获取信息的选定的任务或资源，并可以获取在网格中的所选单元格的数据，例如甘特图视图。 任务窗格的加载项项目还可以实现事件处理程序的任务、 资源、 或查看所选内容更改事件。 
  
图 2 显示**Hello ProjectData**任务窗格外接程序查询**ProjectData**服务中，然后比较所有项目的平均当前项目中的数据。 Project 2013 SDK 下载包括加载项的完整源代码。 
  
**图 2。任务窗格外接程序在 Project Professional 可以访问 Project Server 中的数据**

![比较所有项目在当前项目](media/pj15_RestQueryApp_CompareProject.gif "比较所有项目在当前项目")
  
> [!NOTE]
> Project Standard 2013 不能直接与集成 Project Server 2013 通过任务窗格的加载项。 
  
任务窗格的加载在 Project Professional 可以支持的 Project Server 2013 的内置，因此开发人员可以构建分机号，一旦使用 Project Web App 和 Project Professional 中运行的 Web 部件。 常规任务窗格的加载其他 Office 2013 产品开发还可用于 Project Standard 2013 和 Project Professional 2013。 有关详细信息，请参阅[任务窗格的加载项项目](task-pane-add-ins-for-project.md)。
  
### <a name="project-server-event-receivers"></a>Project Server 事件接收器
<a name="pj15_WhatsNew_Events"> </a>

SharePoint 服务器场，其中包括后端 Project Service 应用程序中可以有多个 Project Web App 服务器 （也称为 web 前端服务器或 Wfe）。 此外可以调用事件接收器的事件处理程序。 可以实施完全信任代码和所有本地的 Project Server 安装 Wfe 上部署本地事件处理程序。 可以在本地或远程服务器上的 web 服务中实现并访问多个 Wfe 服务器和多个 Project Server 安装远程事件接收器。 Project Online 可以使用仅远程事件接收器。
  
由 SharePoint 对于每个 Project Web App 实例，而不是按特定的 Project Web App 设置页管理 project Server 事件处理程序。 在 SharePoint 管理中心应用程序中，选择**应用程序的常规设置**，选择**管理** **PWA 的设置**下，然后选择在 PWA 的设置的**Project Web App 实例**下拉列表中的实例页。 若要添加的本地事件处理程序或远程事件接收器，请选择**服务器端事件处理程序**。
  
Project Server 的本地安装，您可以作为 SharePoint 功能中 CSOM、 使用[Microsoft.ProjectServer.Client.EventHandlerCreationInformation](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCreationInformation.aspx)类的数据创建远程事件接收器并以编程方式管理通过使用方法[EventHandlerCollection](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCollection.aspx)类中的事件接收器。 远程事件接收器预事件同步，后期事件是异步的并且没有超时的远程事件接收器中不会返回的情况。 
  
> [!NOTE]
> 仅适用于本地安装 SharePoint 管理中心。 有关 Project Online 和 SharePoint Online，您可以添加或删除使用基于 CSOM 的应用程序包的远程事件接收器。 
  
在服务器端事件处理程序页上，添加内部部署 Project Server 安装本地事件处理程序的过程是为 Project Server[创建 Project Server 事件处理器并记录事件](https://msdn.microsoft.com/library/gg615466.aspx)主题中所述的过程几乎相同2010。 不同之处在于，新的事件处理程序页具有其他选项。 例如，选择**事件**列表中的**项目创建**，然后选择**新建事件处理程序**。 在新的事件处理程序页上，只有两个必需的域 （参见图 3） 的**名称**和**顺序**。 如果要添加的完全信任的本地事件处理程序，添加**程序集名称**字段和**类名称**字段中;保留**终结点 Url**为空。 如果您要添加远程事件接收器，请添加**终结点 Url**，并将**程序集名称**和**类名称**保留为空。 
  
> [!CAUTION]
> Project Server 如果指定*同时*程序集名称/类名称和终结点 URL，请调用仅本地 （本地） 事件处理程序。 远程事件接收器将被忽略。 
> 
> 如果您创建两个事件处理程序相同的事件，其中一个事件处理程序本地有远程事件接收器，和**顺序**值是相同的同时，Project Server 将忽略远程事件接收器。 
  
**图 3. 添加本地事件处理程序或远程事件接收器**

![配置事件处理程序或事件接收器](media/pj15_EventHandlers_NewEventHandler.gif "配置事件处理程序或事件接收器")
    
如果您需要访问 PSI 数据集的本地事件处理程序，您可以从 Microsoft.Office.Project.Schema.dll 程序集复制 [Windows]\Microsoft.NET\assembly\GAC\_MSIL\Microsoft.Office.Project.Schema\v4.0_15.0.0.0__71e9bce111e9429c 目录。 

而不是 PSI，我们建议您**Microsoft.ProjectServer.Client**命名空间; 中使用的事件类使用 CSOM 开发不需要的数据集的操作。 若要开发 for Project Online 中的远程事件接收器，您必须使用[事件](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.Event.aspx)类和[EventHandlerCreationInformation](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCreationInformation.aspx)类中 CSOM。 
  
部署 Project Server 事件处理程序之前，请安装和测试全面上测试安装的 Project Server 事件处理程序。 对于内部部署 Project Server 安装，如果的本地事件处理程序添加变得不起作用，Project Server 2013 事件服务未能在加载其他有效的自定义事件处理程序。 在这种情况下，您必须删除问题的事件处理程序并重新启动事件服务。
  
> [!NOTE]
> 对于本地 Project Server 安装，建议您使用 CSOM 开发事件接收器来迁移到远程事件接收器。因为远程事件接收器未在 Project Server Events 服务中运行第三方代码，因此远程事件接收器要更稳定。本地管理员免除了维护 Project Server Events 服务的责任。 
  
有关事件的常规信息，请参阅[处理 SharePoint 相关应用程序中的事件](https://msdn.microsoft.com/library/jj220048%28office.15%29.aspx)。 
  
## <a name="deprecated-features"></a>已弃用的功能
<a name="pj15_WhatsNew_Deprecated"> </a>

> [!NOTE]
> 有关功能和 Api 已被弃用或移除 Project Server 2016 Preview 中的信息，请参阅[已弃用或删除 Project Server 2016 Preview 中的内容](https://technet.microsoft.com/library/mt422816%28v=office.16%29.aspx)。 
  
已弃用的功能在 Project 2013 中的某些解决方案，仍然可用，但不是应用于新的开发。 使用 Project Online，或使用默认的本地安装的 Project Server 2013 中 SharePoint 权限模式不工作的大多数以下功能和实践。 使用这些功能的现有解决方案可能不适用于升级到 Project Server 2013 的 Project Server 2010。 虽然使用的解决方案弃用功能可能继续在某些情况下，它们不完全支持的所有 Project 2013 安装。
  
如果您的解决方案使用已弃用的功能，应在部署之前，全面测试它们，并且应修改这些尽快使用支持功能原样实践。 有关配置 Project 权限模式的内部部署 Project Server 2013 安全性的信息，请参阅中[What's new for Project Server 2013 中的 IT 专业人员](https://technet.microsoft.com/en-us/library/ff631142%28office.15%29.aspx)的*SharePoint 权限模式下*一节。
  
- **扩展**[PSI 扩展方案](https://msdn.microsoft.com/library/office/ff843378%28v=office.14%29.aspx)已被弃用，并将在将来版本中不支持。 这些内部部署 Project Server 2013 方案通过使用自定义 Windows Communication Foundation (WCF) 服务启用集成。 
  
- **项目 PSI**PSI[项目类](https://docs.microsoft.com/office/client-developer/project/project-psi-reference-overview)已被弃用。 对于所有新开发，使用[Project CSOM](client-side-object-model-csom-for-project-2013.md)。 使用 Project PSI 的 project Server 2013 应用程序将继续工作，但 Project Online 的应用程序需要将替换其等效的 CSOM 方法的任何项目类的 PSI 方法。
  
- **资源计划 PSI**[资源计划 PSI](https://msdn.microsoft.com/library/office/websvcresourceplan_di_pj14mref.aspx)已被弃用。 它将继续支持 Project 2013 开发的但将来版本中将不支持。 
  
- **Psi 的 ASMX 接口**PSI 包括用于开发的本地 Project Server 扩展重复的接口。 ASMX web 服务界面引入使用 Office Project Server 2007 中的 PSI 的第一个实现。 Project Server 2010 添加的对象模型本质上复制的 ASMX web 服务的 WCF 服务接口。 Project Server 2013 继续支持 ASMX 和 WCF，尽管需要 PSI 的新解决方案应使用 WCF 服务。 如果可能，应使用 CSOM 编写新解决方案。 
  
  Project Server 2013 中弃用的 PSI 的 ASMX web 服务。 要在将来版本的 Project Server，必须重新使用 ASMX web 服务的解决方案使用 WCF 服务或 CSOM。 有关详细信息，请参阅[Project Server 可编程性 （英文）](project-server-programmability.md)中的*使用 Project Server Api 升级应用程序*一节。
  
- **对象链接提供程序 (OLP)** 在 Project server 的早期版本，PSI 中的**ObjectLinkProvider** service （请参阅[WebSvcObjectLinkProvider](https://msdn.microsoft.com/library/WebSvcObjectLinkProvider.aspx) ） 提供用于管理企业项目任务与项目网站中的专用的 SharePoint 列表之间的 web 对象链接方法问题、 风险、 可交付结果和文档。 Project Server 2013 中 OLP 已被弃用。 
  
  您可以用于**[RelatedItemManager](https://msdn.microsoft.com/library/microsoft.sharepoint.client.relateditemmanager.aspx)** 类 SharePoint CSOM 中创建、 读取、 和删除任务列表中的项目和项目网站中的其他列表之间的 web 对象链接。 例如，若要添加到问题从任务项目的链接，可以使用**[AddSingleLink](https://msdn.microsoft.com/library/office/microsoft.sharepoint.client.relateditemmanager.addsinglelink.aspx)** 方法或**AddSingleLinkFromUrl**或**AddSingleLinkToUrl**的两个类似方法之一。 **RelatedItemManager**类还包括用于删除 web 对象链接和读取相关的项目的方法。 JSOM （JavaScript 对象模型） 中的等效类，请参阅[sp。RelatedItemManager object (sp.js)](https://msdn.microsoft.com/library/jj838582.aspx)。
  
  我们建议使用 SharePoint CSOM 创建 OLP 类型应用程序的本地安装的 Project Server 2013 和 Project Online。 [Microsoft.SharePoint](https://msdn.microsoft.com/library/microsoft.sharepoint.aspx)命名空间不包括**RelatedItemManager** *** 类。 
  
- **自定义权限**自定义安全权限才能访问特定的 Project Server 功能或扩展受支持 Office Project Server 2007，其中 SDK 文章介绍了如何创建它们通过直接修改的已发布数据库中。 Project Server 2010 中自定义权限仍工作，但已被弃用。 Project Server 2013 中自定义权限未处理的本地安装的默认 SharePoint 权限模式。 有关 Project 权限模式，支持自定义权限。 使用 Project Online，不能直接数据库访问权限。 
  
- **模拟**基于 PSI 的应用程序中的模拟应用程序的用户可以在其中假定的不同的 Project Server 用户的安全权限在 Project Server 2013 中已弃用。 为以前指示，默认为本地 Project Server 2013 安装使用 SharePoint 权限模式，不允许模拟 Project Server 安全组中。 有关详细信息，请参阅[身份验证、 授权和 SharePoint 2013 中的安全性](https://msdn.microsoft.com/library/ms457529%28office.15%29.aspx)。
  
  Statusing 应用程序可能已在早期版本的 Project Server 中使用模拟的典型扩展。 Project Server 2010 引入**ReadStatusForResource**方法和 PSI，以及**StatusBrokerPermission**全局权限，这不需要模拟读取中的**SubmitStatusForResource**方法并代表另一个用户更新状态。 Project Server 2013 中的 CSOM 使用基础 PSI 透明地启用 statusing 扩展，并可用于 Project Online 或本地安装。 
  
- **报告数据库扩展**添加自定义表和报告数据库的视图与早期版本的 Project Server 的常见做法。 Project Server 2013 将四个早期版本的数据库合并为一个数据库，因为升级不会传输自定义表、 视图或存储过程于 Project Server 2013 数据库中的报告表。 
  
  我们建议您使用 SQL Azure 或单独的 SQL Server 数据库的自定义报告表和视图，可在其中管理数据库备份和更新。 For Project Online 中，这是必需的。
  
- **报告**本地申报表和视图中 Project Server 数据库和 OLAP 多维数据集，是*不*被弃用，并保持完全受支持。 但是，报告的表和视图 （在以前版本的 Project Server 报告数据库） 不在 Project Online 可访问。 同样，OLAP 多维数据集可仅与 Project Server 2013 的本地安装。 对于报告使用 Project Online 的应用程序，您可以使用**ProjectData**服务，通过使用 OData 协议的 REST 查询。 
  
- **项目向导**项目指南是 Office Project 2007 桌面应用程序中的标准功能其中中的任务窗格的 HTML 和 JavaScript 内容提供用于创建和管理项目的交互式指南。 Project 2010 中项目指南不可用在默认安装中，但可以通过 VBA 或 VSTO 加载项来启用。 Project 2010 SDK 下载包括已修改的项目向导文件。 
  
  VBA 对象模型和**Microsoft.Office.Interop.MSProject**对象模型 Project 2013 中的仍包括 22**应用程序**类以及可以管理 Project 指南的**项目**类的成员。 但是，Project 2013 任务窗格应用程序可能会发生冲突的项目向导任务窗格和项目指南内容中的操作与无法轻松分布式或在 Office 商店中销售。 我们强烈建议您开发项目任务窗格与 Office 加载项，不是自定义项目指南内容的解决方案。 关于 Project 指南的详细信息，请参阅[Project 2010 SDK 文档](https://msdn.microsoft.com/library/ms512767.aspx)。
  
## <a name="comparing-project-server-on-premises-with-project-online"></a>比较 Project Server 内部部署与 Project Online
<a name="pj15_WhatsNew_Comparing"> </a>

为了帮助您决定是否使用 Project Server 本地或 Project Online，以及哪些类型的扩展名您可以开发在任一情况下，表 2 比较内部部署安装 Project Server 2013 和 Project Online 的可扩展功能。 表 2 不包括部署、 管理或使用率的差异。 有关 Project Online 和 Project Server 2013 的详细信息，请参阅[面向开发人员的 Project 2013](https://msdn.microsoft.com/office/fp161502)和[Project Online](https://developer.microsoft.com/en-us/project)。
  
**表 2。Project Server 的扩展性在本地和 Project Online**

| 功能 |Project Server 内部部署 | Project Online |
|:-----|:-----|:-----|
|**可编程性 （英文)** <br/> |基于 CSOM 的应用程序;一致的编程模型  <br/>.NET，Silverlight Windows Phone 客户端库  <br/>的自定义页面、 Web 部件和功能区扩展 JavaScript 库  <br/>-OData 和 REST 协议<br/><br/> 基于 PSI 的应用程序;复杂的编程模型，还可以创建用于管理、 项目组合分析、 通知、 项目模式安全性、 队列系统和其他方面的应用程序<br/><br/>PSI 扩展  <br/><br/>项目模式安全性 （已过时） 使用的自定义权限  <br/><br/>模拟使用 PSI （已过时）  <br/><br/>完全信任代码;在 SharePoint 服务器场中安装扩展  <br/> |基于 CSOM 的应用程序;一致的编程模型  <br/>.NET，Silverlight Windows Phone 客户端库<br/>的自定义页面、 Web 部件和功能区扩展 JavaScript 库<br/>-OData 和 REST 协议<br/><br/>可以使用 PSI，但不是支持： 没有 OAuth 和任何服务的服务连接<br/><br/>CSOM API 的任何扩展<br/><br/>无自定义权限<br/><br/>没有模拟<br/><br/>没有完全信任代码  <br/> |
|**自定义数据库** <br/> |-SQL Azure  <br/>-SQL Server （修改报告中 Project Server 不支持数据库表和视图）  <br/> |-SQL Azure  <br/>-SQL Server （修改报告中 Project Server 不支持数据库表和视图）  <br/> |
|**报告** <br/> |- **ProjectData**服务;OData 和 REST 协议  <br/>-报告中的 Project Server 数据库表和视图<br/>OLAP 数据库  <br/> |- **ProjectData**服务;OData 和 REST 协议  <br/> |
|**事件处理程序** <br/> |-远程事件接收器，可通过 WCF 终结点<br/>-完全信任事件处理程序，安装在 SharePoint 服务器场  <br/> | -远程事件接收器，可通过 WCF 终结点  <br/> |
|**工作流** <br/> |声明性工作流，使用 SharePoint Designer 2013 创建<br/>-使用仅对特定的 Project Web App 实例<br/>-从 Visio 2013 可以导入的工作流设计<br/>-可导入并使用自定义操作<br/><br/> 声明性工作流，使用 Visual Studio 2012 创建<br/>创建应用程序可包括工作流<br/>创建可以包含工作流的 SharePoint 解决方案包 (.wsp)<br/>创建供重复使用的工作流模板<br/>创建和使用自定义操作  <br/><br/>可以使用旧的已编译工作流，使用 WF3.5 （建议升级到声明性 WF4 工作流） 创建  <br/> |声明性工作流，使用 SharePoint Designer 2013 创建<br/>-使用仅对特定的 Project Web App 实例<br/>-从 Visio 2013 可以导入的工作流设计<br/>-可导入并使用自定义操作  <br/><br/>声明性工作流，使用 Visual Studio 2012 创建<br/>创建应用程序可包括工作流  <br/>创建可以包含工作流的 SharePoint 解决方案包 (.wsp)<br/>创建供重复使用的工作流模板 <br/>创建和使用自定义操作  <br/> |
|**通讯组** <br/> |-Office 商店 （的基于 CSOM 的应用程序）<br/>-在 SharePoint 上的专用应用程序目录<br/>-Intranet 文件共享  <br/> |-Office 商店<br/>-在 SharePoint 上的专用应用程序目录  <br/> |

   
## <a name="conclusion"></a>结束语
<a name="pj15_WhatsNew_Conclusion"> </a>

Project Server 2013 提供了大量新的开发功能和方案的合作伙伴和客户可以使用调整和扩展的功能和 Project Server 的大型企业和小型组织中的有效性。 可以使用 Office 2013 和 SharePoint 2013 的基础结构可帮助创建和分发可以极大地扩展的营销能力和自定义应用程序使用的 Project 2013 相关应用程序。 某些扩展性功能和实践的以前版本的 Project 2013，特别是 ASMX web 服务的 PSI 和涉及模拟或直接数据库更改，不能用于 Project Online 的功能中弃用。
  
CSOM 简介启用对 Project Online 的各种不同的设备和 web 应用程序中使用 JavaScript 的编程访问。 CSOM 提供更一致的编程模型与 PSI 进行比较。 可以比早期版本，包括通过联机 OData 服务和 Project 数据库中的报表数据的 REST 终结点中的许多更多的方式访问 project Server 数据。 现有报表仍按供内部使用; 相同的方式新报表具有更大的灵活性。
  
Office 加载项提供销售解决方案和与 web 内容和其他 Office 2013 产品集成 Project Standard 2013 新的途径。 您还可以创建与 Project Server 数据集成 Project Professional 2013 的新方式以及通过任务窗格 Office 加载项的 SharePoint 列表。
  
有关开发应用程序和使用的编程功能和 SharePoint Server 2013 的 CSOM 的详细信息，请参阅[面向开发人员的 SharePoint](https://msdn.microsoft.com/sharepoint)和[面向开发人员的 Office](https://msdn.microsoft.com/office)。
  
## <a name="see-also"></a>另请参阅

- [Project Server 2013 体系结构](project-server-2013-architecture.md)  
- [Project 编程任务](project-programming-tasks.md) 
- [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md) 
- [ProjectData - Project 2013 OData 服务引用](https://msdn.microsoft.com/library/office/jj163015.aspx)  
- [Project 任务窗格加载项](task-pane-add-ins-for-project.md)   
- [OData: URI 约定](https://www.odata.org/documentation/uri-conventions#FilterSystemQueryOption)    
- [面向开发人员的 SharePoint](https://msdn.microsoft.com/sharepoint)    
- [面向开发人员的 office](https://msdn.microsoft.com/office)   
- [SharePoint 相关应用程序中处理事件](https://msdn.microsoft.com/library/jj220048%28office.15%29.aspx)   
- [Office 应用商店](https://office.microsoft.com/en-us/store/)   
- [Project Online](https://developer.microsoft.com/en-us/project)
    

