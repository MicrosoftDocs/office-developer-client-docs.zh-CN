---
title: Project 中面向开发人员的更新
manager: soliver
ms.date: 09/29/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5b2b22cd-6e28-43a8-9092-b411da8bfb53
description: 新增的功能包括客户端对象模型 (CSOM)、REST 接口、用于报告的 OData 服务、远程事件接收器、声明性工作流和 Project 客户端的任务窗格外接程序。
ms.openlocfilehash: 0c4c3f9b4bb5852f2a620b2695c15de390ac9d78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315313"
---
# <a name="updates-for-developers-in-project"></a>Project 中面向开发人员的更新

project Server 2013 中的扩展性功能适用于 project Online 和内部部署安装的外接程序。 新增的功能包括客户端对象模型 (CSOM)、REST 接口、用于报告的 OData 服务、远程事件接收器、声明性工作流和 Project 客户端的任务窗格外接程序。 此外, 还应了解不应用于新开发的不推荐使用的功能。
  
project server 2013 基于 Microsoft Office Project server 2007 引入的框架, 并由 Project Server 2010 扩展。 project server 2013 添加了从 Project Server Interface (PSI) 重构和简化的客户端对象模型 (CSOM), 其中包括适用于 windows 应用程序、windows Phone 8 和 Microsoft Silverlight 的 JavaScript 库和 .net Framework 4 库。 CSOM 设计用于 project Online 开发, 也适用于本地 project Server 安装。 

Project Server 数据库将组合成一个数据库；您可通过 OData 服务访问联机报告表和视图。 CSOM 和 OData 服务均具有一个代表性状态传输 (REST) 接口。 可以使用 SharePoint Designer 2013 创建 Project Server 工作流。 project Professional 2013 可以使用任务窗格的 Office 外接程序扩展性模型与 project Server 报告数据、SharePoint 任务列表和其他外部内容相集成。 Project Standard 2013 可以使用任务窗格外接程序与一般外部内容集成。
  
有关 project server 2013 中的主要更改的图示和详细信息, 请参阅[project server 2013 体系结构](project-server-2013-architecture.md)。
  
> [!NOTE]
> Project Server 2013 基于 SharePoint Server 2013 平台，并且 Project 2013 中使用的大部分基础结构与其他 Office 2013 应用程序相同。 有关 sharepoint 加载项模型、基于 sharepoint 的工作流、Web 部件、与其他 SharePoint 功能的开发以及 Office 加载项的文档的文档, 请参阅[SharePoint 加载项](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)、 [Office 外接程序](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)和[SharePoint2013开发概述](https://msdn.microsoft.com/library/jj164084%28office.15%29.aspx)。 
  
## <a name="major-new-features-in-project-2013"></a>Project 2013 的主要新增功能
<a name="pj15_WhatsNew_MajorNewFeatures"> </a>

project Standard 2013 和 project Professional 2013 中的新功能包括改进的用户界面, 可匹配其他 Office 2013 应用程序, 并支持 Windows 8 中的新式样式用户界面, 与用于报告的 Office Art 对象的集成, 燃尽报告和新的针对报告的可编程性功能。 Project Professional 2013 支持在 SharePoint Server 2013 上进行更广泛的共享和同步项目, 以及在其他 Office 2013 应用程序 (如 Word、Excel 和 Outlook) 中也实现的任务窗格加载项。
  
在 Project Server 2013 中有许多新功能。 有些不具有主要可编程性情景, 如 Project Web App 中的新日程表。 这些功能将记录在 Microsoft Office Online 的产品帮助和最终用户文档以及 Microsoft TechNet 上面向管理员和 IT 专业人员的主题中。 其他新增功能（如改进的时间表）使第三方开发人员通过 Project Server 接口 (PSI) 与时间表和状态集成变得更简单。
  
添加 project Online 和 Office 应用商店 (https://office.microsoft.com/store)对于项目外接程序来说, 更改次数较大, 其中 project Server 可通过 Microsoft Azure 访问)。 对 Project Server 的基于云的访问使用客户端对象模型 (CSOM) 在使用 JavaScript 的 microsoft .net Framework、microsoft Silverlight、Windows Phone 和 web 应用程序开发外接程序。 project Online 的要求是, 早期版本的四个 Project Server 数据库将合并到一个数据库中。
  
在许多方面 (如任务状态、时间表和项目管理) 改进了 Project Server 2013 的性能和可伸缩性。 使用 Windows Workflow Foundation (WF4) 的第4版重新设计 Project Server 工作流。 将 .net Framework 4 和 Windows Communication Foundation (WCF) 与 PSI 结合使用可提高安全性、性能和可伸缩性。 例如，您无需更改应用程序代码或重新编译，即可使用配置文件更改基于 WCF 的应用程序的传输协议。 Project Web App 缓存许多 PSI 调用, 其中的数据不会发生显著变化。
  
> [!NOTE]
> 若要使用 Project Server 2013 进行开发, 可以将 Visual Studio 与 office 和 SharePoint 工具扩展结合使用, 这可以为 office 2013 产品本身创建外接程序。 project Server 2013 要求 Visual Studio 完全启用功能 (如项目详细信息页面和基于 WCF 的应用程序) 的开发。 Visual Studio 中的 SharePoint 工具扩展可以将 Web 部件和其他 sharepoint 功能直接部署到 Project Web App 和其他 sharepoint 网站。 
>
> 不再需要 Visual Studio 开发使用可在 Project Web App 中管理的自定义字段、阶段、阶段和企业项目类型的 project Server 工作流。 虽然您可以使用 Visual Studio 开发工作流, 但使用 SharePoint Designer 创建它们通常更为简单快捷。 Visual Studio 可用于需要访问 CSOM 或其他外部 API 的工作流。 
  
### <a name="project-add-ins"></a>Project 加载项
<a name="pj15_WhatsNew_Apps"> </a>

使用外接程序的概念对软件的分发和市场营销进行了彻底的革新。 对于 Project 2013, 可以从公共 Office 商店购买和下载外接程序, 也可以在 SharePoint 上的专用目录中进行发布。 外接程序通常是一个自包含的交互程序, 可执行少量相关的任务。 项目外接程序可以是 project standard 2013 或 project standard 2013 客户端的任务窗格外接程序, 也可以是 project Server 2013 或 project Online 的外接程序。
  
有关 project 桌面客户端的外接程序的信息, 请参阅[project 中的任务窗格外接程序](#pj15_WhatsNew_Agave)。 有关 Project server 2013 示例, 请参阅[创建 SharePoint 托管的 Project Server 外接程序](create-a-sharepoint-hosted-project-server-add-in.md)。 除了[office 和 SharePoint 外接程序 SDK](https://msdn.microsoft.com/library/fp161507.aspx)中的文章外, [office 博客](https://blogs.office.com/dev/)还包含许多与 project 2013 和 project Online 相关的文章。 
  
Project Server 2013 的外接程序可同时适用于本地安装和 Project Online。 Project Server 外接程序可以包含 Web 部件、远程事件接收器和业务逻辑。 对外接程序中的 Project Server 对象模型的访问权限是通过 CSOM, 而不是 PSI。 数据存储可以是基于云的, 如使用 SQL Azure、外部的 Microsoft Business Connectivity Services (BCS)、本地数据库的内部或混合的。
  
#### <a name="add-in-security"></a>加载项安全性

通常, 外接程序所执行的操作代表运行外接程序的用户, 或者您不显式使用模拟或指定可以运行加载项的用户。 操作不能超过运行加载项的用户的权限级别。 
  
在 Visual Studio 2012 的 Office 开发人员工具中, AppManifext 文件具有一个图形编辑器, 您可以在其中设置权限请求范围。 例如, 若要创建可使项目经理更新其项目的外接程序, 请在**appmanifest.xml** designer 窗格的 "**权限**" 选项卡上, 为该范围选择**多个项目**并为该权限进行**写入**。 如果外接程序用户具有项目经理权限, 则可以为其管理的项目运行外接程序。 AppManifest.xml 文件中的代码可包括以下内容： 
  
```XML
  <AppPermissionRequests>
    <AppPermissionRequest Scope="https://sharepoint/projectserver/projects" Right="Write" />
  </AppPermissionRequests>
```

**表1。Project Server 外接程序的权限请求范围**

|Scope|权限|
|:-----|:-----|
|**Project Server** <br/> |**管理**（需要 Project Server 管理员权限。）  <br/> |
|**多个项目** <br/> |**读取**、**写入**(需要针对某些操作的项目经理权限; 针对基本读取操作的项目工作组成员权限, 例如任务分配。)  <br/> |
|**单个项目** <br/> |**读**、**写**（至少需要项目团队成员权限；对项目中某些数据的访问权限取决于其他权限级别。）  <br/> |
|**企业资源** <br/> |**读**、**写**（需要资源经理权限。）  <br/> |
|**Statusing** <br/> |**SubmitStatus**（需要提交项目状态的权限。）  <br/> |
|**报告** <br/> |**读**（需要登录 Project Server 的权限。）  <br/> |
|**工作流** <br/> |**提升**(需要具有运行工作流的权限。 外接端使用提升的权限运行, 以在工作流中启用从阶段到阶段的转换。 加载项控件中的业务逻辑的阶段转换。)  <br/> |
   
> [!NOTE]
> project Server 2013 和 project Online 在 sharepoint 2013 中不使用仅应用身份验证模型 (请参阅[sharepoint 2013 中的外接程序授权策略类型](https://msdn.microsoft.com/library/124879c7-a746-4c10-96a7-da76ad5327f0%28Office.15%29.aspx))。 
  
有关开发、分发、托管和管理外接程序的信息, 请参阅[sharepoint 外接程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)和[office 外接程序](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), 以及 sharepoint Server 2013 和 office 2013 开发人员文档中的相关主题。 有关其他 SharePoint 外接程序的权限请求范围的信息, 请参阅[SharePoint 2013 中的外接程序权限](https://msdn.microsoft.com/library/5f7a8440-3c09-4cf8-83ec-c236bfa2d6c4%28Office.15%29.aspx)。
  
### <a name="integrating-with-sharepoint-server"></a>与 SharePoint Server 集成
<a name="pj15_WhatsNew_IntegrationWSS"> </a>

Project Web App 中的许多功能都需要 sharepoint Server 2013 中的新基础结构, 例如 OAuth 和基于声明的身份验证、通过 sharepoint 组的 Project Server 授权和权限、使用 sharepoint 任务同步项目列表和 Project Server 声明性工作流。 可将 Project Service 应用程序与 SharePoint 场中的任何网站集相关联。 项目可与 SharePoint 任务列表同步，其中 SharePoint 保留项目。 企业项目还可与 SharePoint 任务列表进行同步，其中 Project Server 保留完全控制权限。 有关体系结构图表和项目同步的说明, 请参阅[project Server 2013 体系结构](project-server-2013-architecture.md)。
  
SharePoint Server 2013 中有很多新功能。 有关详细信息, 请参阅[适用于开发人员的 SharePoint](https://msdn.microsoft.com/sharepoint)。
  
### <a name="integrating-with-workflows"></a>与工作流集成
<a name="pj15_WhatsNew_Workflow"> </a>

工作流是项目组合管理的核心功能。项目生命周期可包含长时间运行的跨多个阶段的过程。管理阶段包含项目建议、业务影响分析以及选择、创建、规划、管理和跟踪项目。
  
Project Server 2013 工作流建立在使用 WF4 的 SharePoint 2013 工作流平台之上。 与以前的版本不同, 可使用 SharePoint Designer 2013 创建 Project Server 2013 的声明性工作流, 并可在内部部署和联机使用中访问。 Project Server 工作流将 SharePoint 工作流安全模型与 OAuth 结合使用, 并可将其安装在 Project Web App 网站上。 图1显示了 SharePoint Designer 2013 可以将阶段添加到需要管理的网站工作流中, 其中的阶段是在 Project Web App 中定义的。
  
**图 1. 使用 SharePoint 设计器向 Project Web App 的工作流添加容器**

![将阶段添加到 SPD 中的工作流](media/pj15_CreateWorkflowSPD_AddStageInSPD.gif "将阶段添加到 SPD 中的工作流")

<br/>

通过在设计工具 (可以是 SharePoint Designer 2013 或 Visual Studio 2012) 中添加工作流阶段、操作、条件和其他元素来构建声明性工作流。 然后, 设计工具将工作流另存为 XAML 代码, 该代码在运行时解释。 声明性工作流可在本地或 project Online 中的 project Server 2013 中运行。 通过使用 Visual Studio 2012, 您还可以为其他控件生成自定义操作和窗体, 并保存工作流模板以供多个 Project Web App 实例重复使用。 SharePoint Designer 2013 可以使用在 Visual Studio 2012 中创建的自定义操作。
  
project Server 2013 工作流充当一个应用程序, 其中管理员 (拥有 Project Web app 的设计权限) 可以发布声明性工作流, 并将其与企业项目类型 (EPT) 相关联。 EPT 必须适用于其中 Project Server 保留完全控制权限的企业项目。 SharePoint 任务列表无法使用 Project Server 工作流。 
  
利用 OAuth，具有项目创建权限的项目经理无需使用模拟，即可调用工作流。 对 Project Server 的工作流调用（例如，读取自定义字段值以决定要跟踪的分支）是代表项目经理进行的。 若要防止项目经理创建的工作流自动前进至下一容器，移至下一工作流容器的调用将以工作流作者（管理员）的身份运行。 相比之下, 旧版 Project Server 2010 工作流的用户通过工作流代理用户帐户进行模拟调用, 以获得整个工作流的管理员访问权限。
  
尽管 Project Server 2013 本地版可以使用编译的基于 wf 3.5 的工作流, 但我们建议您将旧版工作流升级到基于 WF4 的声明性工作流。 较新的技术更具可扩展性且更强大。 业务分析员和 PMO 员工可以使用 Visio 2013 创建或更新工作流设计, 并通过使用 SharePoint Designer 2013 来实现 Project Server 工作流, 而无需编码。
  
有关为 project Web App 创建声明性工作流的信息, 请参阅[开始开发 project Server 工作流](getting-started-developing-project-server-workflows.md)。 若要比较 SharePoint Designer 和 visual studio 的工作流功能, 请参阅[使用 Visual Studio 开发 sharepoint 2013 工作流](https://msdn.microsoft.com/library/office/jj163199.aspx)。
  
### <a name="client-side-object-model"></a>客户端对象模型
<a name="pj15_WhatsNew_CSOM"> </a>

以编程方式访问 Project Online 需要在 SharePoint CSOM 上构建的 CSOM。 使用 Windows Live ID (而不是 project Server Forms 身份验证或 Windows 身份验证) 将使用 OAuth 进行 Project Online 身份验证。
  
以下是 Project Server 2013 中的 CSOM 的原则和功能:
  
- CSOM 旨在易于使用。 例如, 方法和属性直接按名称使用或提供数据, 而不是需要许多 guid、 _changeXml_参数或传递数据集。 
    
- Project Server CSOM 基于第三方解决方案的最常见要求实现 PSI 功能的子集。
    
- CSOM 内部方式调用 PSI，但以不同的方式构成。 例如，对所有状态更改的更新是通过 **StatusAssignmentCollection.SubmitAllStatusUpdates** 方法而不是通过用户的 **Statusing.SubmitStatus** PSI 方法或其他资源的 **SubmitStatusForResource** 方法完成的。 
    
- CSOM 可通过一个 WCF 服务 (Client.svc) 而不是 PSI 的 22 个公共服务进行访问。
    
- project Server CSOM 的初始化通过 project Web App URL 直接通过[ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx)类, 而不是使用 WCF 引用或代理程序集。 
    
- CSOM 实现的多个客户端库和接口均受内部 SharePoint CSOM 基础结构的支持。这些客户端库和接口包括：
    
  - Microsoft.ProjectServer.Client.dll 程序集中的 Microsoft .NET 客户端库
    
  - microsoft.projectserver.client 程序集内的 Silverlight 库
    
  - microsoft microsoft.projectserver.client 程序集中的 Windows Phone 8 库
    
  - 用于 ps .js 文件或 ps. debug.exe 文件中 web 应用程序的 JavaScript 库
    
  - REST 终结点，使用 OData 协议进行访问
    
  - 对使用筛选的 LINQ 查询的本机支持，以限制返回的数据量
    
- CSOM 可用于 Project Online 解决方案和内部部署解决方案, 独立于 PSI 和其他 Project Server 程序集 (如 Microsoft. .dll.)。
    
- 根据 project server 合作伙伴和开发人员社区的请求, 可能会根据累积更新和 service pack 对 project server 2013 CSOM 的其他功能进行考虑。
    
> [!NOTE]
> CSOM 是第三方 Project Server 开发人员的首选接口。如果 CSOM 包括应用程序所需的功能，建议您使用 CSOM 开发新的应用程序。 
  
有关使用 CSOM 进行开发的信息, 请参阅[Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)。 有关 sharepoint 应用程序中的 REST 接口的信息, 请参阅 sharepoint 2013 开发人员文档中*的使用 sharepoint REST 服务编程*。 
  
### <a name="changes-in-the-reporting-database"></a>报告数据库中的更改
<a name="pj15_WhatsNew_RDBChanges"> </a>

project server 2010 中的四个数据库组合到 project server 2013 中的单个 project 数据库中。 Project 数据库的默认名称为 ProjectService。 报告表和视图保留其以前的名称, 并且 "草稿"、"已发布" 和 "存档" 数据库中`draft`的`pub`表和`ver`视图具有前缀、和 ProjectService 数据库中的表和视图。 例如，已发布项目表为 pub.MSP_PROJECTS。 
  
> [!IMPORTANT]
> 草稿 (`draft`前缀)、已发布 (`pub`) 和存档 (`ver`) 表和视图不支持直接访问。 报告应仅使用具有`dbo`前缀的报告表格和视图。 例如, dbo。MSP_EpmProject 表包含 Project Web App 实例中的项目列表。 
>
> 实际上没有任何内容阻止您使用直接编程数据库访问来更新 Project 数据库中任何表和视图中的数据。您应注意，Project Professional 缓存、草稿和已发布数据的表以及报告表均依赖可被直接数据编辑中断的缓存同步协议。如果您使用直接访问更改数据损坏了 Project Server 数据库或损坏了 Project Professional 客户端缓存，则将收到产品支持无法帮助的警告！ 
  
Project Server 2013 引入了适用于联机和本地访问的 OData 服务。 联机报告表和视图只能由 OData 接口公开；对于内部使用，您可使用 OData 接口或直接访问 SharePoint 场中的 ProjectService 数据库中的报告表和视图。 Project Online 不支持多租户数据库。 也就是说, 每个 project Web App 的实例都有自己的项目数据库。 OData 服务内部运行对报告表和视图的 SQL 查询，并提供 XML 或 JSON 负载。 有关 Project Server 2013 中用于报告的 OData 服务的简介和**ProjectData**架构参考, 请参阅[ProjectData-Project OData service reference](https://msdn.microsoft.com/library/office/jj163015.aspx)。
  
有关 odata 查询的常规信息, 请参阅[odata: URI 约定](https://www.odata.org/documentation/)。 例如, 您可以通过在浏览器中使用以下查询, 在 project Web App 的本地实例中查看所有项目, 其中项目名称以 "Test" 开头。 在浏览器页中右键单击，然后单击“查看源代码”****。
  
```html
https://ServerName /ProjectServerName /_api/ProjectData/Projects?$filter=startswith(ProjectName, 'Test') eq true
```

若要将项目数据导入 Excel 2013 中的 PowerPivot, 请在数据功能区上, 从 "**自其他源**" 下拉菜单中选择 "**来自 OData 数据源**"。 在 "**数据连接向导**" 对话框中, https://ServerName/ProjectServerName/_api/ProjectData/键入数据馈送位置, 选择 "**下一步**", 然后在向导的 "**选择表**" 页中选择 "**项目**" 表。 命名并保存此 .odc 文件，然后选择“完成”****。 在“导入数据”**** 对话框中，选择“数据透视表报告”****。 在 Excel 工作表上，选择要显示的数据透视表的行和列上的字段。
  
本地 Project Server 用户拥有适当的权限, 可以直接通过 Microsoft SQL Server 访问报告表和视图, 以创建报告, 就像在 Project Server 2010 中那样。 在 Project Server 2013 中, 用户还可以通过 OData 接口访问内部部署报告表。 您还可通过 OData 服务的 REST 终结点联机或内部检索 Project Server 数据。 例如，dbo.MSP_PROJECT 表和 dbo.MSP_EpmProject_UserView 视图可用于报告。 具有`draft`、 `pub`或`ver`前缀的任何表或视图仅供 Project Server 内部使用, 而不能用于报告。 例如，没有记录 draft.MSP_TASKS 表和 pub.MSP_PROJECTS_WORKING_VIEW 视图，它们仅供内部使用。 
  
> [!NOTE]
> 您可以通过在单独数据库中添加表、视图、字段和存储过程来扩展内部报告。您不能在 Project Server 数据库中修改现有报告表和视图。 
  
project 数据库中的报告表、视图和字段将记录在 HTML 帮助文件中, 在后续更新的 project 2013 SDK 下载中。 有关**ProjectData**服务的 OData XML 架构的文档, 请参阅[ProjectData-Project OData service reference](https://msdn.microsoft.com/library/office/jj163015.aspx)。 对为 project server 2010 创建的报告表和视图的查询在大多数情况下, 使用 project server 2013 中的 project 数据库。 内部用户可以像现在一样访问 SQL Server Analysis Services 中的 Project Server OLAP 多维数据集。 在 Project Online 中, OLAP 多维数据集不可用。
  
### <a name="task-pane-add-ins-in-project"></a>项目中的任务窗格外接程序
<a name="pj15_WhatsNew_Agave"> </a>

project Standard 2013 和 project Professional 2013 支持任务窗格外接程序, 可用于与网页中的外部内容集成并显示外部内容。 任务窗格显示可通过 JavaScript 访问任务、资源、视图和常规项目数据的网页内容。 Project 的 JavaScript 对象模型可以获取有关所选任务或资源的信息, 并且可以在网格中的选定单元格中获取数据, 例如 "甘特图" 中的视图。 Project 的任务窗格外接程序还可以实现任务、资源或视图选择已更改事件的事件处理程序。 
  
图2显示了用于查询**ProjectData**服务的**Hello ProjectData**任务窗格外接程序, 然后将当前项目中的数据与所有项目的平均值进行比较。 Project 2013 SDK 下载包括外接程序的完整源代码。 
  
**图2。project Professional 中的任务窗格加载项可以访问 project Server 中的数据**

![将当前项目与所有项目进行比较](media/pj15_RestQueryApp_CompareProject.gif "将当前项目与所有项目进行比较")
  
> [!NOTE]
> project Standard 2013 无法直接通过任务窗格外接程序与 Project Server 2013 集成。 
  
project Professional 中的任务窗格加载项可以支持为 project Server 2013 生成的 Web 部件, 因此开发人员可以在运行 project Web App 和 project Professional 的情况下构建扩展。 为其他 Office 2013 产品开发的常规任务窗格外接程序还可以与 project Standard 2013 和 project Professional 2013 一起使用。 有关详细信息, 请参阅[Project 的任务窗格外接程序](task-pane-add-ins-for-project.md)。
  
### <a name="project-server-event-receivers"></a>Project Server 事件接收器
<a name="pj15_WhatsNew_Events"> </a>

SharePoint 场中可以有多个 Project Web App 服务器 (也称为 Web 前端服务器或 wfe), 其中包括后端 Project Service 应用程序。 事件接收器还可称为事件处理程序。 本地事件处理程序可使用完全信任代码实现，并且可部署在本地 Project Server 安装的所有 WFE 中。 远程事件接收器可在本地或远程服务器上的 Web 服务中实现，并且可由多个 WFE 和多个 Project Server 安装访问。 Project Online 只能使用远程事件接收器。
  
project Server 事件处理程序由 SharePoint 为每个 project web app 实例 (而不是特定的 Project web app 设置页) 进行管理。 在 SharePoint 管理中心应用程序中, 选择 "**常规应用程序设置**", 选择 " **pwa 设置**" 下的 "**管理**", 然后在 "pwa 设置" 上的 " **Project Web App 实例**" 下拉列表中选择实例。页符. 若要添加本地事件处理程序或远程事件接收器，请选择“服务器端事件处理程序”****。
  
对于 Project Server 的本地安装, 可以创建远程事件接收器作为 SharePoint 功能, 在 CSOM 中使用 EventHandlerCreationInformation 类, 然后以编程方式管理[microsoft.projectserver.client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCreationInformation.aspx)中的事件接收器通过使用[EventHandlerCollection](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCollection.aspx)类中的方法。 对于远程事件接收器，前期事件是同步的，后期事件是异步的，在远程事件接收器未返回的情况下会出现超时。 
  
> [!NOTE]
> SharePoint 管理中心仅适用于内部安装。 对于 Project online 和 SharePoint online, 可以使用基于 CSOM 的应用程序包添加或删除远程事件接收器。 
  
在 "服务器端事件处理程序" 页上, 为本地 project server 安装添加本地事件处理程序的过程几乎与 "[创建 project server 事件处理程序并](https://msdn.microsoft.com/library/gg615466.aspx)为 project server 记录事件" 主题中所述的过程相同。2010。 区别是“新建事件处理程序”页具有其他选项。 例如，选择“事件”**** 列表中的“项目创建”****，然后选择“新建事件处理程序”****。 在“新建事件处理程序”页上，只有“名称”**** 和“顺序”**** 两个必填字段（见图 3）。 如果要添加本地完全信任的事件处理程序，请添加“程序集名称”**** 字段和“类名称”**** 字段；保留“终结点 Url”**** 为空。 如果要添加远程事件接收器，请添加“终结点 Url”**** 并保留“程序集名称”**** 和“类名称”**** 为空。 
  
> [!CAUTION]
> 如果*同时*指定程序集名称/类名和终结点 URL, 则 Project Server 仅调用本地 (内部部署) 事件处理程序。 将忽略远程事件接收器。 
> 
> 如果为同一个事件创建两个事件处理程序, 其中一个事件处理程序是本地的, 另一个是远程事件接收器, 并且这两个事件的**顺序**值相同, 则 Project Server 将忽略远程事件接收器。 
  
**图 3. 添加本地事件处理程序或远程事件接收器**

![配置事件处理程序或事件接收器](media/pj15_EventHandlers_NewEventHandler.gif "配置事件处理程序或事件接收器")
    
如果您需要对本地事件处理程序的 PSI 数据集的访问权限, 则可以从 [Windows] \Microsoft.NET\assembly\GAC\_MSIL\Microsoft.Office.Project.Schema\v4.0_15.0.0.0__ 中复制 Microsoft. .dll 程序集。71e9bce111e9429c 目录。 

建议您在 **Microsoft.ProjectServer.Client** 命名空间中使用事件类而不是 PSI；使用 CSOM 进行开发不需要操作数据集。 若要为 Project Online 开发远程事件接收器, 您必须使用 CSOM 中的[event](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.Event.aspx)类和[EventHandlerCreationInformation](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCreationInformation.aspx)类。 
  
在部署 Project Server 事件处理程序之前，请在 Project Server 的测试安装中安装并测试事件处理程序。 对于本地 Project Server 安装, 如果您添加的本地事件处理程序无效, 则 Project Server 2013 事件服务无法加载其他有效的自定义事件处理程序。 在此情况下，您必须解决事件处理程序问题，然后才能重新启动 Events 服务。
  
> [!NOTE]
> 对于本地 Project Server 安装，建议您使用 CSOM 开发事件接收器来迁移到远程事件接收器。因为远程事件接收器未在 Project Server Events 服务中运行第三方代码，因此远程事件接收器要更稳定。本地管理员免除了维护 Project Server Events 服务的责任。 
  
有关事件的一般信息, 请参阅[处理 SharePoint 相关应用程序中的事件](https://msdn.microsoft.com/library/jj220048%28office.15%29.aspx)。 
  
## <a name="deprecated-features"></a>不推荐使用的功能
<a name="pj15_WhatsNew_Deprecated"> </a>

> [!NOTE]
> 有关在 project server 2016 preview 中已弃用或删除的功能和 api 的信息, 请参阅[project server 2016 preview 中已弃用或已删除的内容](https://technet.microsoft.com/library/mt422816%28v=office.16%29.aspx)。 
  
已弃用的功能仍可用于某些解决方案的 Project 2013 中, 但不应用于新的开发。 在 SharePoint 权限模式下, 以下大部分功能和实践不适用于 project Online 或 project Server 2013 的默认本地安装。 使用这些功能的现有解决方案在将 project server 2010 升级到 project server 2013 时可能不起作用。 尽管使用弃用的功能的解决方案在某些情况下可能仍可继续工作, 但并非所有 Project 2013 安装完全支持这些解决方案。
  
如果你的解决方案使用已弃用的功能, 则应在部署之前对其进行全面测试, 并且应将其修改为尽可能使用受支持的功能。 有关为 project 权限模式配置本地 Project Server 2013 安全性的信息, 请参阅[project Server 2013 中面向 IT 专业人员的新增功能](https://technet.microsoft.com/en-us/library/ff631142%28office.15%29.aspx)中的 " *SharePoint 权限模式*" 部分。
  
- **扩展**[PSI 扩展方案](https://msdn.microsoft.com/library/office/ff843378%28v=office.14%29.aspx)已弃用, 在将来的版本中不受支持。 这些本地 Project Server 2013 方案启用了使用自定义 Windows Communication Foundation (WCF) 服务的集成。 
  
- **Project PSI**PSI 的[项目类](https://docs.microsoft.com/office/client-developer/project/project-psi-reference-overview)已被弃用。 对于所有新的开发, 请使用[项目 CSOM](client-side-object-model-csom-for-project-2013.md)。 使用 project PSI 的 project Server 2013 应用将继续工作, 但 project Online 应用程序将需要使用等效的 CSOM 方法替换任何项目类 PSI 方法。
  
- **资源计划 PSI**[资源计划 PSI](https://msdn.microsoft.com/library/office/websvcresourceplan_di_pj14mref.aspx)已弃用。 它将继续为 Project 2013 开发提供支持, 但在将来的版本中不受支持。 
  
- **PSI 的 .asmx 接口**PSI 包含用于开发本地 Project Server 扩展的重复接口。 在 Office Project Server 2007 中第一次实施 PSI 时引入了 ".asmx web 服务" 接口。 Project Server 2010 添加了 WCF 服务接口, 其中对象模型基本上复制了 ".asmx web 服务"。 [! 注意] 尽管 Project Server 2013 继续支持 .asmx 和 WCF, 但需要 PSI 的新解决方案应使用 WCF 服务。 如果可能, 应使用 CSOM 编写新的解决方案。 
  
  PSI 的 .asmx web 服务在 Project Server 2013 中已被弃用。 若要在未来的 Project Server 版本中工作, 必须将使用 ".asmx web 服务" 的解决方案重写为使用 WCF 服务或 CSOM。 有关详细信息, 请参阅[project server 可编程性](project-server-programmability.md)中的*使用 project server api 升级应用程序*一节。
  
- **对象链接提供程序 (OLP)** 在早期版本的 Project Server 中, PSI 中的**ObjectLinkProvider**服务 (请参阅[WebSvcObjectLinkProvider](https://msdn.microsoft.com/library/WebSvcObjectLinkProvider.aspx) ) 提供了一种方法, 用于管理企业项目任务和项目网站中的专门 SharePoint 列表之间的 web 对象链接。有关问题、风险、可交付结果和文档的详细说明。 在 Project Server 2013 中, OLP 已被弃用。 
  
  您可以使用 SharePoint CSOM 中的**[RelatedItemManager](https://msdn.microsoft.com/library/microsoft.sharepoint.client.relateditemmanager.aspx)** 类在 "任务" 列表中的项目与项目网站中的其他列表之间创建、读取和删除 web 对象链接。 例如, 若要向问题添加来自任务项的链接, 您可以使用**[AddSingleLink](https://msdn.microsoft.com/library/office/microsoft.sharepoint.client.relateditemmanager.addsinglelink.aspx)** 方法或以下两种类似的方法之一: **AddSingleLinkFromUrl**或**AddSingleLinkToUrl**。 **RelatedItemManager**类还包括用于删除 web 对象链接和读取相关项目的方法。 对于 JSOM 中的等效类 (JavaScript 对象模型), 请参阅[SP。RelatedItemManager 对象 (sp-1)](https://msdn.microsoft.com/library/jj838582.aspx)。
  
  建议使用 SharePoint CSOM 为本地安装的 project Server 2013 和 project Online 创建 OLP 应用程序。 [Microsoft SharePoint](https://msdn.microsoft.com/library/microsoft.sharepoint.aspx)命名空间不包含**RelatedItemManager** * * * * 类。 
  
- **自定义权限**Office Project server 2007 中支持访问特定 Project server 功能或扩展的自定义安全权限, 其中的 SDK 文章介绍了如何通过直接修改发布的数据库来创建这些功能或扩展。 在 Project Server 2010 中, 自定义权限仍有效, 但已被弃用。 在 Project Server 2013 中, 自定义权限不适用于本地安装的默认 SharePoint 权限模式。 对于项目权限模式, 支持自定义权限。 在 Project Online 中, 不可能直接访问数据库。 
  
- **模拟**在基于 PSI 的应用程序中进行模拟, 其中应用程序的用户可以假定不同 project server 用户的安全权限在 project server 2013 中已被弃用。 如前所述, 默认的本地 Project Server 2013 安装使用 SharePoint 权限模式, 该模式不允许在 Project Server 安全组中进行模拟。 有关详细信息，请参阅 [Authentication, authorization, and security in SharePoint 2013](https://msdn.microsoft.com/library/ms457529%28office.15%29.aspx)。
  
  Statusing 应用程序是早期版本的 Project Server 中可能已使用模拟的典型扩展。 Project Server 2010 在 PSI 中引入了**ReadStatusForResource**方法和**SubmitStatusForResource**方法, 并提供了**StatusBrokerPermission**全局权限, 从而消除了模拟读取的必要性并代表另一个用户更新状态。 project Server 2013 中的 CSOM 使用基础 PSI 透明地启用 statusing 扩展, 并且可用于 Project Online 或本地安装。 
  
- **报告数据库扩展**将自定义表和视图添加到报告数据库是早期版本的 Project Server 的常见做法。 由于 project server 2013 将早期版本的四个数据库合并到一个数据库中, 因此升级不会将自定义表、视图或 SPROCs 转移到 Project Server 2013 数据库中的报告表。 
  
  我们建议您为自定义报告表和视图使用 sql Azure 或单独的 sql Server 数据库, 您可以在其中管理数据库备份和更新。 对于 Project Online, 这是必需的。
  
- **报告**Project Server 数据库中的本地报告表和视图和 OLAP 多维数据集*不*会被弃用, 并保持完全受支持。 但是, 报表表和视图 (以前的 Project Server 版本中的报表数据库) 在 Project Online 中不可访问。 同样, OLAP 多维数据集仅适用于 Project Server 2013 的本地安装。 若要使用 Project Online 报告应用程序, 您可以通过使用 OData 协议的 REST 查询使用**ProjectData**服务。 
  
- **项目指南**项目指南是 Office Project 2007 桌面应用程序中的一项标准功能, 其中, 在任务窗格中的 HTML 和 JavaScript 内容提供了有关创建和管理项目的交互式指南。 在 project 2010 中, "项目向导" 在默认安装中不可用, 但可以通过 VBA 或 VSTO 加载项启用。 project 2010 SDK 下载包括修改的项目指南文件。 
  
  Project 2013 中的 VBA 对象模型和**msproject.xml**对象模型仍然包含**应用程序**类的22个成员和可以管理项目指南的**项目**类。 但是, project 2013 任务窗格应用程序可能与项目指南任务窗格中的操作冲突, 并且项目指南中的内容无法在 Office 应用商店中轻松分发或销售。 强烈建议使用 Office 外接程序开发项目任务窗格解决方案, 而不是自定义项目指南内容。 有关项目指南的详细信息, 请参阅[project 2010 SDK 文档](https://msdn.microsoft.com/library/ms512767.aspx)。
  
## <a name="comparing-project-server-on-premises-with-project-online"></a>将本地 project Server 与 project Online 进行比较
<a name="pj15_WhatsNew_Comparing"> </a>

为了帮助您决定是使用 project server 内部部署还是 project online, 以及在任一情况下可以开发哪些类型的扩展, 表2将 project Server 2013 的本地安装的可扩展功能与 Project Online 进行比较。 表2不包括部署、管理或使用方面的差异。 有关 project Online 和 project Server 2013 的详细信息, 请参阅[Project 2013 for 开发人员](https://msdn.microsoft.com/office/fp161502)和[project Online](https://developer.microsoft.com/en-us/project)。
  
**表2。project Server 本地和 project Online 的可扩展性**

| 功能 |Project Server 本地 | Project Online |
|:-----|:-----|:-----|
|**实现** <br/> |基于 CSOM 的应用;一致的编程模型  <br/>-.net、Silverlight、Windows Phone 客户端库  <br/>-自定义页面、Web 部件和功能区扩展的 JavaScript 库  <br/>-OData 和 REST 协议<br/><br/> 基于 PSI 的应用;复杂编程模型, 还可以创建用于管理、项目组合分析、通知、项目模式安全性、队列系统和其他方面的应用程序<br/><br/>PSI 扩展  <br/><br/>使用项目模式安全性的自定义权限 (已弃用)  <br/><br/>使用 PSI 进行模拟 (已弃用)  <br/><br/>完全信任代码;在 SharePoint 场中安装扩展  <br/> |基于 CSOM 的应用;一致的编程模型  <br/>-.net、Silverlight、Windows Phone 客户端库<br/>-自定义页面、Web 部件和功能区扩展的 JavaScript 库<br/>-OData 和 REST 协议<br/><br/>可以使用 PSI, 但不支持: 没有 OAuth 且无服务到服务连接<br/><br/>没有 CSOM API 的扩展<br/><br/>无自定义权限<br/><br/>无模拟<br/><br/>无完全信任代码  <br/> |
|**自定义数据库** <br/> |-SQL Azure  <br/>-SQL server (不支持修改 Project server 数据库中的报告表和视图)  <br/> |-SQL Azure  <br/>-SQL server (不支持修改 Project server 数据库中的报告表和视图)  <br/> |
|**报告** <br/> |- **ProjectData**服务;OData 和 REST 协议  <br/>在 Project Server 数据库中报告表和视图<br/>-OLAP 数据库  <br/> |- **ProjectData**服务;OData 和 REST 协议  <br/> |
|**事件处理程序** <br/> |-可通过 WCF 终结点访问的远程事件接收器<br/>-已安装在 SharePoint 场中的完全信任事件处理程序  <br/> | -可通过 WCF 终结点访问的远程事件接收器  <br/> |
|**工作流** <br/> |使用 SharePoint Designer 2013 创建的声明性工作流<br/>-仅在特定 Project Web App 实例上使用<br/>-可以从 Visio 2013 导入工作流设计<br/>-可以导入和使用自定义操作<br/><br/> 使用 Visual Studio 2012 创建的声明性工作流<br/>-创建可包含工作流的应用程序<br/>-创建可包含工作流的 SharePoint 解决方案包 (.wsp)<br/>-创建重复使用的工作流模板<br/>-创建和使用自定义操作  <br/><br/>可以使用使用 wf 3.5 创建的旧版已编译工作流 (建议升级到声明性 WF4 工作流)  <br/> |使用 SharePoint Designer 2013 创建的声明性工作流<br/>-仅在特定 Project Web App 实例上使用<br/>-可以从 Visio 2013 导入工作流设计<br/>-可以导入和使用自定义操作  <br/><br/>使用 Visual Studio 2012 创建的声明性工作流<br/>-创建可包含工作流的应用程序  <br/>-创建可包含工作流的 SharePoint 解决方案包 (.wsp)<br/>-创建重复使用的工作流模板 <br/>-创建和使用自定义操作  <br/> |
|**分发** <br/> |-Office 应用商店 (针对基于 CSOM 的应用)<br/>-SharePoint 上的专用应用程序目录<br/>-Intranet 文件共享  <br/> |-Office 应用商店<br/>-SharePoint 上的专用应用程序目录  <br/> |

   
## <a name="conclusion"></a>结束语
<a name="pj15_WhatsNew_Conclusion"> </a>

Project server 2013 提供了大量新的开发功能和方案, 合作伙伴和客户可以使用它们来调整和扩展大型企业和小型组织中的 Project Server 的功能和有用性。 您可以使用 Office 2013 和 SharePoint 2013 的基础结构来帮助创建和分发可大大扩展 marketability 和使用自定义应用程序的项目2013的应用程序。 早期版本的一些扩展性功能和做法在 project 2013 中已弃用, 尤其是 PSI 的 .asmx web 服务和涉及模拟或直接数据库更改的功能, 这些功能不能与 Project Online 一起使用。
  
引入 CSOM 使您能够以编程方式访问各种设备的 Project Online, 并在 web 应用程序中使用 JavaScript。 与 PSI 相比，CSOM 提供的编程模型更加一致。 可访问 Project Server 数据的方式比之前的版本中的方式更多，包括从联机 OData 服务和通过用于报告 Project 数据库中数据的 REST 终结点。 现有报告将仍以相同的方式供内部使用；新报告更灵活。
  
Office 外接程序为销售解决方案提供了新的途径, 并将 Project Standard 2013 与 web 内容和其他 Office 2013 产品集成在一起。 您还可以通过任务窗格 Office 外接程序创建将 project Professional 2013 与 project Server 数据和 SharePoint 列表集成的新方法。
  
有关开发应用程序以及使用可编程性功能和 CSOM 的 sharepoint Server 2013 的详细信息, 请参阅适用于[开发人员的 sharepoint](https://msdn.microsoft.com/sharepoint)和[Office for 开发人员](https://msdn.microsoft.com/office)。
  
## <a name="see-also"></a>另请参阅

- [Project Server 2013 体系结构](project-server-2013-architecture.md)  
- [Project 编程任务](project-programming-tasks.md) 
- [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md) 
- [ProjectData - Project 2013 OData 服务引用](https://msdn.microsoft.com/library/office/jj163015.aspx)  
- [Project 任务窗格加载项](task-pane-add-ins-for-project.md)   
- [OData: URI 约定](https://www.odata.org/documentation/uri-conventions#FilterSystemQueryOption)    
- [面向开发人员的 SharePoint](https://msdn.microsoft.com/sharepoint)    
- [面向开发人员的 Office](https://msdn.microsoft.com/office)   
- [处理 SharePoint 相关应用程序中的事件](https://msdn.microsoft.com/library/jj220048%28office.15%29.aspx)   
- [Office 应用商店](https://office.microsoft.com/en-us/store/)   
- [Project Online](https://developer.microsoft.com/en-us/project)
    

