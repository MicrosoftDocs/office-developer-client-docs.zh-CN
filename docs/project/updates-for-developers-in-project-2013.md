---
title: Project
manager: lindalu
ms.date: 12/03/2019
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5b2b22cd-6e28-43a8-9092-b411da8bfb53
description: 新功能包括客户端对象模型 (CSOM) 、REST 接口、用于报告的 OData 服务、远程事件接收器、声明性工作流和适用于 Project 客户端的任务窗格外接程序。
ms.openlocfilehash: c2bc0b475639a8582422b2091169116428367c60
ms.sourcegitcommit: 37080eb0087261320e24e6f067e5f434a812b2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819278"
---
# <a name="updates-for-developers-in-project"></a>Project

Project Server 2013 中的扩展性功能适用于 Project Online 外接程序和本地安装。 新功能包括客户端对象模型 (CSOM) 、REST 接口、用于报告的 OData 服务、远程事件接收器、声明性工作流和适用于 Project 客户端的任务窗格外接程序。 此外，了解不应用于新开发功能的已弃用功能。
  
ProjectServer 2013 基于 Microsoft Office Project Server 2007 引入的框架，由 Project Server 2010 扩展。 ProjectServer 2013 添加了客户端对象模型 (CSOM) ，该对象模型从 Project 服务器接口 (PSI) 重构和简化，并包括适用于 Windows 应用、Windows Phone 8 和 Microsoft Silverlight 的 JavaScript 库和 .NET Framework 4 库。 CSOM 设计用于开发 Project Online，还适用于本地 Project Server 安装。 

Project Server 数据库将组合成一个数据库；您可通过 OData 服务访问联机报告表和视图。 CSOM 和 OData 服务均具有一个代表性状态传输 (REST) 接口。 Project可以使用 SharePoint Designer 2013 创建服务器工作流。 Project Professional 2013 可以使用任务窗格的 Office 外接程序扩展模型与 Project Server 报告数据、SharePoint 任务列表和其他外部内容集成。 Project Standard 2013 可以使用任务窗格外接程序与常规外部内容集成。
  
有关 Project Server 2013 中的主要更改的图表和详细信息，请参阅[Project Server 2013 体系结构](project-server-2013-architecture.md)。
  
> [!NOTE]
> Project Server 2013 基于 SharePoint Server 2013 平台，并且 Project 2013 中使用的大部分基础结构与其他 Office 2013 应用程序相同。 有关 SharePoint 外接程序、基于 SharePoint 的工作流、Web 部件、其他 SharePoint 功能的开发以及 Office 外接程序的文档的文档，请参阅[SharePoint Add-ins、](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)Office [Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)和[SharePoint 2013 development overview。](https://msdn.microsoft.com/library/jj164084%28office.15%29.aspx) 
  
## <a name="major-new-features-in-project-2013"></a>Project 2013 的主要新增功能
<a name="pj15_WhatsNew_MajorNewFeatures"> </a>

Project Standard 2013 和 Project Professional 2013 中的新功能包括与其他 Office 2013 应用程序匹配的改进的用户界面，并支持 Windows 8 中的新式用户界面、与用于报表的 Office Art 对象集成、刻录报告和报表的新可编程性功能。 Project Professional 2013 可在 SharePoint Server 2013 上实现更广泛的共享和同步项目，以及同样在其他 Office 2013 应用程序（如 Word、Excel 和 Outlook）中实现的任务窗格外接程序。
  
Project Server 2013 中有许多新功能。 一些没有主要的可编程性情景，例如新时间线Project Web App。 这些功能将记录在 Microsoft Office Online 的产品帮助和最终用户文档以及 Microsoft TechNet 上面向管理员和 IT 专业人员的主题中。 其他新增功能（如改进的时间表）使第三方开发人员通过 Project Server 接口 (PSI) 与时间表和状态集成变得更简单。
  
添加 Project Online 和 Office Store (for Project 是一项影响广泛的更改，其中 Project Server 可通过 Microsoft Azure https://office.microsoft.com/store) 访问。 对 Project Server 的基于云的访问使用客户端对象模型 (CSOM) 来开发具有 Microsoft .NET Framework、Microsoft Silverlight、Windows Phone 和使用 JavaScript 的 Web 应用的外接程序。 要求Project Online早期版本的四Project服务器数据库合并到一个数据库中。
  
Project服务器 2013 性能和可伸缩性在任务状态、时间表和项目管理等许多方面都得到改进。 Project服务器工作流是使用 WF4 Windows 的 Windows 4 (重新设计) 。 通过 PSI 使用 .NET Framework 4 Windows Communication Foundation (WCF) 可提高安全性、性能和可伸缩性。 例如，您无需更改应用程序代码或重新编译，即可使用配置文件更改基于 WCF 的应用程序的传输协议。 Project Web App缓存数据没有明显更改的许多 PSI 调用。
  
> [!NOTE]
> 对于 Project Server 2013 开发，您可以将 Visual Studio 与 Office 和 SharePoint 工具扩展一同使用，这两种工具可本机为 Office 2013 产品创建外接程序。 ProjectServer 2013 要求Visual Studio完全启用项目详细信息页和基于 WCF 的应用程序等功能的开发。 SharePoint工具扩展Visual Studio可以将 Web 部件 和其他 SharePoint 功能直接部署到 Project Web App 和其他 SharePoint 网站。 
>
> Visual Studio开发使用自定义域、阶段、阶段和企业项目类型的 Project Server 工作流，这些类型可在 Project Web App 中进行管理。 尽管您可以使用 Visual Studio开发工作流，但是使用设计器通常可以更轻松地SharePoint工作流。 Visual Studio 可用于需要访问 CSOM 或其他外部 API 的工作流。 
  
### <a name="project-add-ins"></a>Project 加载项
<a name="pj15_WhatsNew_Apps"> </a>

软件分发和营销已随外接程序的概念发生了变革。 对于 Project 2013，可以从公共 Office 商店购买和下载外接程序，或在 SharePoint 上的专用目录中分发外接程序。 加载项通常是一个自包含的交互式程序，它执行少量相关任务。 Project外接程序可以是 Project Standard 2013 或 Project Standard 2013 客户端的任务窗格外接程序，或 Project Server 2013 或 Project Online 的外接程序。
  
有关桌面客户端加载项Project，请参阅任务窗格[加载项Project。](#pj15_WhatsNew_Agave) 有关 Project Server 2013 的示例，请参阅 Create [a SharePoint-hosted Project Server add-in。](create-a-sharepoint-hosted-project-server-add-in.md) 除了 Office 和[SharePoint Add-ins SDK](https://msdn.microsoft.com/library/fp161507.aspx)中的文章之外[，Office 博客](https://blogs.office.com/dev/)还包含许多与 Project 2013 和 Project Online 相关的文章。 
  
适用于 Project Server 2013 的外接程序可以同时用于本地安装和Project Online。 Project服务器加载项可以包括Web 部件、远程事件接收器和业务逻辑。 加载项Project服务器对象模型的访问是通过 CSOM，而不是 PSI。 数据存储可以是基于云的，例如SQL Azure、外部（如通过 Microsoft Business Connectivity Services (BCS) 、使用本地数据库的内部存储或混合存储）。
  
#### <a name="add-in-security"></a>加载项安全性

通常，加载项执行的操作是代表运行加载项的用户执行的;您不会显式使用模拟或指定可以运行外接程序的用户。 操作不能超过运行外接程序的用户的权限级别。 
  
在 Office Tools for Visual Studio 2012 中，AppManifext.xml文件具有一个图形编辑器，您可以在其中设置权限请求范围。 例如，若要创建允许项目经理更新其项目的外接程序，请在AppManifest.xml设计器窗格的"权限 **"** 选项卡上，选择"多个项目"作为范围，为权限选择 **"** 写入"。  如果外接程序用户具有项目经理权限，则她可以针对自己管理的项目运行外接程序。 AppManifest.xml 文件中的代码可包括以下内容： 
  
```XML
  <AppPermissionRequests>
    <AppPermissionRequest Scope="https://sharepoint/projectserver/projects" Right="Write" />
  </AppPermissionRequests>
```

**表 1.Project 服务器外接程序的权限请求范围**

|范围|Permissions|
|:-----|:-----|
|**Project Server** <br/> |**管理**（需要 Project Server 管理员权限。）  <br/> |
|**多个项目** <br/> |**读取****、 (** 某些操作需要项目经理权限;基本读取操作（如任务分配）的项目团队成员)   <br/> |
|**单Project** <br/> |**读**、**写**（至少需要项目团队成员权限；对项目中某些数据的访问权限取决于其他权限级别。）  <br/> |
|**企业资源** <br/> |**读**、**写**（需要资源经理权限。）  <br/> |
|**Statusing** <br/> |**SubmitStatus**（需要提交项目状态的权限。）  <br/> |
|**报告** <br/> |**读**（需要登录 Project Server 的权限。）  <br/> |
|**工作流** <br/> |**提升** (需要运行工作流的权限。 外接程序使用提升的权限运行，以在工作流中实现从一个阶段到一个阶段的转换。 外接程序控件中的业务逻辑阶段转换。)   <br/> |
   
> [!NOTE]
> ProjectServer 2013 和 Project Online 不使用 SharePoint 2013 中的仅应用程序身份验证模型 (请参阅[SharePoint 2013](https://msdn.microsoft.com/library/124879c7-a746-4c10-96a7-da76ad5327f0%28Office.15%29.aspx)) 中的外接程序授权策略类型。 
  
有关开发、分发、托管和管理外接程序的信息，请参阅[SharePoint Add-ins](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins) and [Office Add-ins，](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)以及 SharePoint Server 2013 和 Office 2013 开发人员文档中的相关主题。 有关其他外接程序的权限请求SharePoint，请参阅[Add-in permissions in SharePoint 2013。](https://msdn.microsoft.com/library/5f7a8440-3c09-4cf8-83ec-c236bfa2d6c4%28Office.15%29.aspx)
  
### <a name="integrating-with-sharepoint-server"></a>与 SharePoint Server 集成
<a name="pj15_WhatsNew_IntegrationWSS"> </a>

Project Web App 中的许多功能都需要 SharePoint Server 2013 中的新基础结构，例如 OAuth 和基于声明的身份验证、Project Server 通过 SharePoint 组的授权和权限、将项目与 SharePoint 任务列表同步以及 Project Server 声明性工作流。 可将 Project Service 应用程序与 SharePoint 场中的任何网站集相关联。 项目可与 SharePoint 任务列表同步，其中 SharePoint 保留项目。 企业项目还可与 SharePoint 任务列表进行同步，其中 Project Server 保留完全控制权限。 有关体系结构图和项目同步说明，请参阅 Project [Server 2013 体系结构](project-server-2013-architecture.md)。
  
SharePoint Server 2013 中有许多新功能。 有关详细信息，请参阅SharePoint[开发人员。](https://msdn.microsoft.com/sharepoint)
  
### <a name="integrating-with-workflows"></a>与工作流集成
<a name="pj15_WhatsNew_Workflow"> </a>

工作流是项目组合管理的核心功能。项目生命周期可包含长时间运行的跨多个阶段的过程。管理阶段包含项目建议、业务影响分析以及选择、创建、规划、管理和跟踪项目。
  
Project服务器 2013 工作流基于使用 WF4 的 SharePoint 2013 工作流平台构建。 与早期版本不同，Project Server 2013 的声明性工作流可以使用 SharePoint Designer 2013 创建，并且可供本地和联机使用。 Project服务器工作流将 SharePoint工作流安全模型与 OAuth 一起使用，并可以安装在Project Web App网站上。 图 1 SharePoint Designer 2013 可以将阶段添加到需求管理的网站工作流，其中阶段在 Project Web App 中定义。
  
**图 1. 使用 SharePoint 设计器向 Project Web App 的工作流添加容器**

![将容器添加到 SPD 中的工作流](media/pj15_CreateWorkflowSPD_AddStageInSPD.gif "将容器添加到 SPD 中的工作流")

<br/>

您可以通过在设计工具（可以是 SharePoint Designer 2013 或 Visual Studio 2012）中添加工作流阶段、操作、条件和其他元素来构建声明性工作流。 然后，设计工具将工作流保存为 XAML 代码，该代码在运行时进行解释。 声明性工作流可以在 Project Server 2013 内部部署或 Project Online。 通过使用 Visual Studio 2012，您还可以构建用于其他控件的自定义操作和表单，并保存工作流模板以用于多个 Project Web App 实例。 SharePointDesigner 2013 可以使用在 Visual Studio 2012 中创建的自定义操作。
  
Project Server 2013 工作流充当应用程序，其中具有 Project Web App 设计权限的管理员可发布声明性工作流并将其与企业项目类型 (EPT) 关联。 EPT 必须适用于其中 Project Server 保留完全控制权限的企业项目。 SharePoint 任务列表无法使用 Project Server 工作流。 
  
利用 OAuth，具有项目创建权限的项目经理无需使用模拟，即可调用工作流。 对 Project Server 的工作流调用（例如，读取自定义字段值以决定要跟踪的分支）是代表项目经理进行的。 若要防止项目经理创建的工作流自动前进至下一容器，移至下一工作流容器的调用将以工作流作者（管理员）的身份运行。 相反，旧版 Project Server 2010 工作流的用户通过工作流代理用户帐户进行模拟调用，以获取整个工作流中的管理员访问权限。
  
尽管 Project Server 2013 内部部署可以使用已编译的基于 WF3.5 的工作流，但我们建议您将旧工作流升级到基于 WF4 的声明性工作流。 较新的技术更具可扩展性和稳定性。 业务分析师和 PMO 员工可以使用 Visio 2013 创建或更新工作流设计，而无需使用 SharePoint Designer 2013 编码即可实现 Project Server 工作流。
  
有关为应用程序创建声明性工作流Project Web App，请参阅开始开发 Project [Server 工作流](getting-started-developing-project-server-workflows.md)。 有关工作流的 SharePoint Designer 和 Visual Studio 功能的比较，请参阅使用 SharePoint [2013 工作流Visual Studio。](https://msdn.microsoft.com/library/office/jj163199.aspx)
  
### <a name="client-side-object-model"></a>客户端对象模型
<a name="pj15_WhatsNew_CSOM"> </a>

以编程Project Online访问需要基于 CSOM 构建SharePoint CSOM。 Project Online使用 Live ID Windows OAuth 进行身份验证，Project服务器表单身份验证或 Windows 身份验证。
  
以下是 Project Server 2013 中 CSOM 的原则和功能：
  
- CSOM 旨在易于使用。 例如，方法和属性直接使用或按名称提供数据，而不是需要许多  _GUID、changeXml_ 参数或传递数据集。 
    
- Project Server CSOM 基于第三方解决方案的最常见要求实现 PSI 功能的子集。
    
- CSOM 内部方式调用 PSI，但以不同的方式构成。例如，对所有状态更改的更新是通过 **StatusAssignmentCollection.SubmitAllStatusUpdates** 方法而不是通过用户的 **Statusing.SubmitStatus** PSI 方法或其他资源的 **SubmitStatusForResource** 方法完成的。 
    
- CSOM 可通过一个 WCF 服务 (Client.svc) 而不是 PSI 的 22 个公共服务进行访问。
    
- Project服务器 CSOM 的初始化直接通过具有 Project Web App URL 的[ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx)类，而不是使用 WCF 引用或代理程序集。 
    
- CSOM 实现的多个客户端库和接口均受内部 SharePoint CSOM 基础结构的支持。这些客户端库和接口包括：
    
  - Microsoft.ProjectServer.Client.dll 程序集中的 Microsoft .NET 客户端库
    
  - 程序集中的 Silverlight Microsoft.ProjectServer.Client.Silverlight.dll库
    
  - Windows Phone程序集中的 Microsoft.ProjectServer.Client.Phone.dll 8 库
    
  - PS.js 或 PS.debug.js 文件中 Web 应用程序的 JavaScript 库
    
  - REST 终结点，使用 OData 协议进行访问
    
  - 对使用筛选的 LINQ 查询的本机支持，以限制返回的数据量
    
- CSOM 既可用于Project Online解决方案，也可用于本地解决方案，独立于 PSI 和其他 Project Server 程序集（如 Microsoft.Office.Project.Server.Library.dll）。
    
- 根据 Project Server 合作伙伴和开发人员社区的请求，可能会考虑使用 Project Server 2013 CSOM 的其他功能进行累积更新和 Service Pack。
    
> [!NOTE]
> CSOM 是第三方 Project Server 开发人员的首选接口。如果 CSOM 包括应用程序所需的功能，建议您使用 CSOM 开发新的应用程序。 
  
有关使用 CSOM 进行开发的信息，请参阅[Client-side object model (CSOM) for Project 2013。](client-side-object-model-csom-for-project-2013.md) 有关 SharePoint 应用程序中 REST 接口的信息，请参阅 SharePoint 2013 开发人员文档中的使用 *SharePoint REST* 服务进行编程。 
  
### <a name="changes-in-the-reporting-database"></a>报告数据库中的更改
<a name="pj15_WhatsNew_RDBChanges"> </a>

Project Server 2010 中的四个数据库组合到 Project Server 2013 Project单个数据库。 Project 数据库的默认名称为 ProjectService。 报告表和视图保留其以前的名称，草稿、已发布和存档数据库中的表和视图具有前缀 、 和 在  `draft`  `pub`  `ver` ProjectService 数据库中。 例如，已发布项目表为 pub.MSP_PROJECTS。 
  
> [!IMPORTANT]
> 在表和视图中， (前缀) 、已发布 () 和存档 () `draft` `pub` `ver` 直接访问。 报告应仅使用前缀为 的报告表和 `dbo` 视图。 例如，dbo。MSP_EpmProject表包含项目实例中的Project Web App列表。 
>
> 实际上没有任何内容阻止您使用直接编程数据库访问来更新 Project 数据库中任何表和视图中的数据。您应注意，Project Professional 缓存、草稿和已发布数据的表以及报告表均依赖可被直接数据编辑中断的缓存同步协议。如果您使用直接访问更改数据损坏了 Project Server 数据库或损坏了 Project Professional 客户端缓存，则将收到产品支持无法帮助的警告！ 
  
ProjectServer 2013 引入了 OData 服务，用于联机和本地访问。 联机报告表和视图只能由 OData 接口公开；对于内部使用，您可使用 OData 接口或直接访问 SharePoint 场中的 ProjectService 数据库中的报告表和视图。 Project Online不支持多租户数据库。 也就是说，每个数据库的多个Project Web App都有自己的数据库Project数据库。 OData 服务内部运行对报告表和视图的 SQL 查询，并提供 XML 或 JSON 负载。 有关 OData 服务在 Project Server 2013 中用于报告的介绍，以及 **ProjectData** 架构参考，请参阅 [ProjectData - Project OData service reference](https://msdn.microsoft.com/library/office/jj163015.aspx)。
  
有关 OData 查询的常规信息，请参阅 [OData：URI 约定](https://www.odata.org/documentation/)。 例如，您可以在本地 Project Web App（其中项目名称以"Test"开头）的所有项目在浏览器中使用下面的查询。 在浏览器页中右键单击，然后单击“查看源代码”。
  
```html
https://ServerName /ProjectServerName /_api/ProjectData/Projects?$filter=startswith(ProjectName, 'Test') eq true
```

若要将项目数据导入 PowerPivot 2013 Excel，请在"数据"功能区上，从"自其他源"下拉菜单中选择"来自 **OData** 数据馈送"。 在"**数据连接向导**"对话框中，键入数据馈送位置，选择"下一步"，然后选择向导的"选择表"页中的" https://ServerName/ProjectServerName/_api/ProjectData/ 项目"表。    命名并保存此 .odc 文件，然后选择“完成”。 在“导入数据”对话框中，选择“数据透视表报告”。 在 Excel 工作表上，选择要显示的数据透视表的行和列上的字段。
  
本地 Project 服务器用户（具有正确的权限）可以通过 Microsoft SQL Server 直接访问报告表和视图以创建报告，就像在 Project Server 2010 中一样。 在 Project Server 2013 中，用户还可通过 OData 接口访问内部部署报告表。 您还可通过 OData 服务的 REST 终结点联机或内部检索 Project Server 数据。 例如，dbo.MSP_PROJECT 表和 dbo.MSP_EpmProject_UserView 视图可用于报告。 具有 、 或 前缀的任何表或视图仅供 Project 服务器内部使用， `draft` `pub` `ver` 不用于报告使用。 例如，没有记录 draft.MSP_TASKS 表和 pub.MSP_PROJECTS_WORKING_VIEW 视图，它们仅供内部使用。 
  
> [!NOTE]
> 您可以通过在单独数据库中添加表、视图、字段和存储过程来扩展内部报告。您不能在 Project Server 数据库中修改现有报告表和视图。 
  
Project 数据库中的报告表、视图和字段将在 HTML 帮助文件中记录在 Project 2013 SDK 下载的更新中。 有关 **ProjectData** 服务的 OData XML 架构的文档，请参阅 [ProjectData - Project OData service reference](https://msdn.microsoft.com/library/office/jj163015.aspx)。 在大多数情况下，为 Project Server 2010 创建的报告表和视图的查询将在 Project Server 2013 中处理 Project 数据库。 内部用户可以像现在一样访问 SQL Server Analysis Services 中的 Project Server OLAP 多维数据集。 在Project Online中，OLAP 多维数据集不可用。
  
### <a name="task-pane-add-ins-in-project"></a>任务窗格中的任务窗格Project
<a name="pj15_WhatsNew_Agave"> </a>

2013 Project Standard 2013 和 Project Professional 2013 都支持任务窗格外接程序，可用于与网页中的外部内容集成和显示。 任务窗格显示通过 JavaScript 访问任务、资源、视图和常规项目数据的网页内容。 适用于以下对象的 JavaScript 对象Project可以获取有关所选任务或资源的信息，并可以获取网格中选定单元格的数据，以获得视图（如甘特图）。 适用于用户的任务窗格外接程序Project任务、资源或视图选择更改事件的事件处理程序。 
  
图 2 显示了查询 **ProjectData** 服务的 **Hello ProjectData** 任务窗格外接程序，然后将当前项目中的数据与所有项目的平均值进行比较。 the Project 2013 SDK download includes the complete source code for the add-in. 
  
**图 2.任务窗格中的任务窗格外接程序Project Professional访问 Project Server 中的数据**

![将当前项目与所有项目进行比较](media/pj15_RestQueryApp_CompareProject.gif "将当前项目与所有项目进行比较")
  
> [!NOTE]
> Project Standard 2013 无法通过任务窗格Project与 Project Server 2013 直接集成。 
  
Project Professional 中的任务窗格加载项可以支持为 Project Server 2013 构建的 Web 部件，因此开发人员可以在同时使用 Project Web App 和 Project Professional 运行后生成扩展。 为其他 Office 2013 产品开发的常规任务窗格外接程序还可与 Project Standard 2013 和 Project Professional 2013 一起使用。 有关详细信息，请参阅 Task [pane add-ins for Project](task-pane-add-ins-for-project.md)。
  
### <a name="project-server-event-receivers"></a>Project Server 事件接收器
<a name="pj15_WhatsNew_Events"> </a>

可以有多个 Project Web App 服务器 (也称为 Web 前端服务器，或者) 服务器场（包括后端 Project 服务应用程序的 SharePoint） 事件接收器还可称为事件处理程序。 本地事件处理程序可使用完全信任代码实现，并且可部署在本地 Project Server 安装的所有 WFE 中。 远程事件接收器可在本地或远程服务器上的 Web 服务中实现，并且可由多个 WFE 和多个 Project Server 安装访问。 Project Online只能使用远程事件接收器。
  
Project服务器事件处理程序由每个SharePoint实例的 Project Web App进行管理，而不是由特定的 Project Web App 设置 管理。 在 SharePoint 管理中心应用程序中，选择"一般应用程序 设置"，选择 **"PWA 设置"** 下的"管理"，然后在"PWA 设置"页上的 **"Project Web App** 实例"下拉列表中选择实例。 若要添加本地事件处理程序或远程事件接收器，请选择“服务器端事件处理程序”。
  
对于 Project Server 本地安装，您可以将远程事件接收器创建为使用 CSOM 中的[Microsoft.ProjectServer.Client.EventHandlerCreationInformation](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCreationInformation.aspx)类的 SharePoint 功能，然后使用[EventHandlerCollection](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCollection.aspx)类中的方法以编程方式管理事件接收器。 对于远程事件接收器，前期事件是同步的，后期事件是异步的，在远程事件接收器未返回的情况下会出现超时。 
  
> [!NOTE]
> SharePoint 管理中心仅适用于内部安装。 对于 Project Online 和 SharePoint Online，可以使用基于 CSOM 的应用包添加或删除远程事件接收器。 
  
在"服务器端事件处理程序"页上，为本地 Project Server 安装添加本地事件处理程序的过程几乎与创建[Project Server](https://msdn.microsoft.com/library/gg615466.aspx)事件处理程序并记录 Project Server 2010 的事件主题中描述的过程相同。 区别是“新建事件处理程序”页具有其他选项。 例如，选择“事件”列表中的“项目创建”，然后选择“新建事件处理程序”。 在“新建事件处理程序”页上，只有“名称”和“顺序”两个必填字段（见图 3）。 如果要添加本地完全信任的事件处理程序，请添加“程序集名称”字段和“类名称”字段；保留“终结点 Url”为空。 如果要添加远程事件接收器，请添加“终结点 Url”并保留“程序集名称”和“类名称”为空。 
  
> [!CAUTION]
> 如果同时 *指定* 程序集名称/类名称和终结点 URL，Project Server 将仅调用本地 (本地) 事件处理程序。 远程事件接收器将被忽略。 
> 
> 如果为同一事件创建两个事件处理程序，其中一个事件处理程序是本地事件处理程序，一个事件处理程序是远程事件接收器，Order 值对于这两个事件处理程序是相同的，Project Server 将忽略远程事件接收器。 
  
**图 3. 添加本地事件处理程序或远程事件接收器**

![配置事件处理程序或事件接收器](media/pj15_EventHandlers_NewEventHandler.gif "配置事件处理程序或事件接收器")
    
如果需要访问本地事件处理程序的 PSI 数据集，可以从 [Windows]\Microsoft.NET\assembly\GAC \_ MSIL\Microsoft.Office 复制 Microsoft.Office.Project.Schema.dll 程序集。Project。Schema\v4.0_15.0.0.0__71e9bce111e9429c 目录。 

建议您在 **Microsoft.ProjectServer.Client** 命名空间中使用事件类而不是 PSI；使用 CSOM 进行开发不需要操作数据集。 若要开发远程事件接收器Project Online，必须使用 CSOM 中的[Event](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.Event.aspx)类和[EventHandlerCreationInformation](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.EventHandlerCreationInformation.aspx)类。 
  
在部署 Project Server 事件处理程序之前，请在 Project Server 的测试安装中安装并测试事件处理程序。 对于本地 Project Server 安装，如果您添加的本地事件处理程序变得不起作用，则 Project Server 2013 事件服务无法加载其他有效的自定义事件处理程序。 在此情况下，您必须解决事件处理程序问题，然后才能重新启动 Events 服务。
  
> [!NOTE]
> 对于本地 Project Server 安装，建议您使用 CSOM 开发事件接收器来迁移到远程事件接收器。因为远程事件接收器未在 Project Server Events 服务中运行第三方代码，因此远程事件接收器要更稳定。本地管理员免除了维护 Project Server Events 服务的责任。 
  
有关事件的常规信息，请参阅处理应用程序的事件[SharePoint。](https://msdn.microsoft.com/library/jj220048%28office.15%29.aspx) 
  
## <a name="deprecated-features"></a>不推荐使用的功能
<a name="pj15_WhatsNew_Deprecated"> </a>

> [!NOTE]
> 有关 Project Server 2016 Preview 中已弃用或删除的功能和 API 的信息，请参阅 Project Server 2016 Preview 中弃用[或删除的功能](https://docs.microsoft.com/project/what-s-deprecated-or-removed-in-project-server-2016)。 
  
2013 年 2 月Project弃用的功能仍可用于某些解决方案，但不应用于新开发。 以下大部分功能和做法都Project Online权限模式下的 Project Server 2013 的默认本地SharePoint安装。 使用这些功能的现有解决方案可能无法用于将 Project Server 2010 升级到 Project Server 2013。 尽管在某些情况下，使用已弃用功能的解决方案可能仍可以继续运行，但并非所有 Project 2013 安装都支持这些解决方案。
  
如果解决方案使用已弃用的功能，应在部署之前对其进行全面测试，并且应将其修改为尽快使用支持的功能。 有关为 Project 权限模式配置本地 Project Server 2013 安全性的信息，请参阅 Project  [Server 2013](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2016)中针对 IT 专业人员的新增功能中的 SharePoint 权限模式部分。
  
- **扩展** [PSI 扩展方案](https://docs.microsoft.com/previous-versions/office/developer/office-2010/ff843378(v=office.14)) 已弃用，在未来版本中不受支持。 这些本地 Project Server 2013 方案通过使用自定义 Windows Communication Foundation (WCF) 集成。 
  
- **Project PSI** PSI [Project](https://docs.microsoft.com/office/client-developer/project/project-psi-reference-overview)类已弃用。 对于所有新开发，请使用[Project CSOM。](client-side-object-model-csom-for-project-2013.md) Project使用 Project PSI 的服务器 2013 应用将继续工作，但 Project Online 应用需要将任何 Project 类 PSI 方法替换为其等效的 CSOM 方法。
  
- **资源计划 PSI**[资源计划 PSI](https://docs.microsoft.com/previous-versions/office/project-class/gg240019(v=office.15))已弃用。 2013 年 3 月Project仍支持该版本，但以后的版本中将不支持它。 
  
- PSI 的 **ASMX 接口** PSI 包括用于开发内部部署服务器扩展Project接口。 ASMX Web 服务接口是在 Office Project Server 2007 中首次实现 PSI 时引入的。 ProjectServer 2010 添加了 WCF 服务接口，其中对象模型基本上与 ASMX Web 服务重复。 尽管 Project Server 2013 继续支持 ASMX 和 WCF，但需要 PSI 的新解决方案应该使用 WCF 服务。 如果可能，应该使用 CSOM 编写新的解决方案。 
  
  PSI 的 ASMX Web 服务在 Project Server 2013 中已弃用。 若要在将来Project服务器版本，必须将使用 ASMX Web 服务的解决方案重写为使用 WCF 服务或 CSOM。 有关详细信息，请参阅使用 Project Server 可编程性 中的使用 *Project* Server [API 升级应用程序部分](project-server-programmability.md)。
  
- **OLP 对象 (提供程序)** 在早期版本的 Project Server 中，PSI 中的 **ObjectLinkProvider** 服务 (请参阅 [WebSvcObjectLinkProvider](https://docs.microsoft.com/previous-versions/office/ms481347(v=office.14))提供了一种用于管理企业项目任务与项目网站中专用 SharePoint 列表之间的 Web 对象链接的方法，用于了解问题、风险、可交付结果和文档。 在 Project Server 2013 中，OLP 已弃用。 
  
  您可以使用 SharePoint CSOM 中的 **[RelatedItemManager](https://docs.microsoft.com/previous-versions/office/sharepoint-server/jj168020(v=office.15))** 类创建、读取和删除任务列表中的项目与项目网站中其他列表之间的 Web 对象链接。 例如，若要添加从任务项到问题的链接，可以使用 **[AddSingleLink](https://docs.microsoft.com/previous-versions/office/sharepoint-server/jj166451(v=office.15))** 方法或两个类似方法之一， **AddSingleLinkFromUrl** 或 **AddSingleLinkToUrl**。 **RelatedItemManager** 类还包括用于删除 Web 对象链接和读取相关项目的方法。 有关 JAVAScript 对象模型 (JSOM 中的等效) ，请参阅 [SP。RelatedItemManager 对象 (sp.js) ](https://docs.microsoft.com/previous-versions/office/sharepoint-visio/jj838582(v=office.15))。
  
  建议您使用 SharePoint CSOM 为 Project Server 2013 和 Project Online 本地安装创建 OLP 类型的Project Online。 [Microsoft.SharePoint](https://docs.microsoft.com/previous-versions/office/sharepoint-server/ms464984(v=office.15))命名空间不包括 **RelatedItemManager** **** 类。 
  
- **自定义权限** Office Project Server 2007 中支持用于访问特定 Project Server 功能或扩展的自定义安全权限，其中 SDK 文章介绍了如何直接修改已发布数据库来创建它们。 在 Project Server 2010 中，自定义权限仍正常工作，但已弃用。 在 Project Server 2013 中，自定义权限不能用于本地SharePoint的默认自定义权限模式。 对于Project模式，支持自定义权限。 如果Project Online，则不能直接访问数据库。 
  
- **模拟** 基于 PSI 的应用（其中应用用户可以假定其他 Project Server 用户的安全权限）中的模拟在 Project Server 2013 中已弃用。 如前所述，默认的本地 Project Server 2013 安装使用 SharePoint 权限模式，该模式不允许在 Project Server 安全组中进行模拟。 有关详细信息，请参阅 [Authentication, authorization, and security in SharePoint 2013](https://docs.microsoft.com/sharepoint/dev/general-development/authentication-authorization-and-security-in-sharepoint)。
  
  状态应用程序是典型扩展，在早期版本的 Project Server 中可能使用了模拟。 Project服务器 2010 在 PSI 中引入了 **ReadStatusForResource** 方法和 **SubmitStatusForResource** 方法以及 **StatusBrokerPermission** 全局权限，这不需要模拟代表其他用户读取和更新状态。 Project Server 2013 中的 CSOM 使用基础 PSI 以透明方式启用状态扩展，并可用于 Project Online 或本地安装。 
  
- **报告数据库扩展** 向报告数据库添加自定义表和视图是早期版本的 Project Server 的常见做法。 由于 Project Server 2013 将早期版本的四个数据库合并到一个数据库中，因此升级不会将自定义表、视图或 SPROC 转移到 Project Server 2013 数据库中的报告表。 
  
  建议您对自定义报告表和SQL Azure使用单独的 SQL Server 数据库，可以在其中管理数据库备份和更新。 对于Project Online，这是必需的。
  
- **报告** 未弃用 Project Server 数据库和 OLAP 多维数据集中的本地报告表和视图，它们仍然完全受支持。 但是，上一 (服务器版本中的报告Project报表表和) 无法Project Online。 同样，OLAP 多维数据集仅适用于 Project Server 2013 本地安装。 对于使用 Project Online报告应用程序，可以通过使用 OData 协议的 REST 查询来使用 **ProjectData** 服务。 
  
- **Project指南** Project指南是 Office Project 2007 桌面应用程序中的标准功能，其中任务窗格中的 HTML 和 JavaScript 内容提供了用于创建和管理项目的交互式指导。 在 Project 2010 中，Project指南不适用于默认安装，但可以通过 VBA 或 VSTO加载项启用。 the Project 2010 SDK download includes the modified Project Guide files. 
  
  VBA 对象模型和 **Microsoft.Office。** Project 2013 中的 Interop.MSProject 对象模型仍包括 **Application** 类和 Project 类的 22 个成员，这些 **成员** 可以管理 Project Guide。 但是，Project 2013 任务窗格应用程序可能会与 Project Guide 任务窗格中的操作发生冲突，Project Guide 内容无法在 Office Store 中轻松分发或出售。 我们强烈建议您开发Project外接程序（而不是自定义Office指南内容）Project任务窗格解决方案。 有关本指南Project，请参阅[Project 2010 SDK 文档](https://msdn.microsoft.com/library/ms512767.aspx)。
  
## <a name="comparing-project-server-on-premises-with-project-online"></a>将 Project Server 本地与 Project Online
<a name="pj15_WhatsNew_Comparing"> </a>

为了帮助您决定是使用 Project Server 内部部署还是使用 Project Online，以及您可以在这两种情况下开发哪些类型的扩展，表 2 将 Project Server 2013 本地安装的可扩展功能与 Project Online 进行比较。 表 2 不包括部署、管理或用法的差异。 有关 Project Online 和 Project Server 2013 Project，请参阅[Project 2013 for developers](https://developer.microsoft.com/project/docs)和[Project Online](https://developer.microsoft.com/project)。
  
**表 2.Project Server 本地和本地服务器的可扩展性Project Online**

| 功能 |Project服务器本地 | Project Online |
|:-----|:-----|:-----|
|**可编程性** <br/> |基于 CSOM 的应用;一致的编程模型  <br/>- .NET、Silverlight、Windows Phone客户端库  <br/>- 自定义页面、Web 部件功能区扩展的 JavaScript 库  <br/>- OData 和 REST 协议<br/><br/> 基于 PSI 的应用程序;复杂编程模型，还可以创建用于管理、项目组合分析、通知、Project模式安全性、队列系统和其他领域的应用<br/><br/>PSI 扩展  <br/><br/>已弃Project模式 (自定义)   <br/><br/>已弃用 PSI (模拟)   <br/><br/>完全信任代码;在服务器场中安装SharePoint扩展  <br/> |基于 CSOM 的应用;一致的编程模型  <br/>- .NET、Silverlight、Windows Phone客户端库<br/>- 自定义页面、Web 部件功能区扩展的 JavaScript 库<br/>- OData 和 REST 协议<br/><br/>可以使用 PSI，但不受支持：无 OAuth 和无服务到服务连接<br/><br/>CSOM API 没有扩展<br/><br/>无自定义权限<br/><br/>无模拟<br/><br/>无完全信任代码  <br/> |
|**自定义数据库** <br/> |- SQL Azure  <br/>- SQL Server (服务器数据库中的报告表和Project视图的修改不受支持)   <br/> |- SQL Azure  <br/>- SQL Server (服务器数据库中的报告表和Project视图的修改不受支持)   <br/> |
|**报告** <br/> |- **ProjectData** 服务;OData 和 REST 协议  <br/>- 报告 Project Server 数据库中的表和视图<br/>- OLAP 数据库  <br/> |- **ProjectData** 服务;OData 和 REST 协议  <br/> |
|**事件处理程序** <br/> |- 可通过 WCF 终结点访问的远程事件接收器<br/>- 完全信任事件处理程序，安装在SharePoint服务器场中  <br/> | - 可通过 WCF 终结点访问的远程事件接收器  <br/> |
|**工作流** <br/> |声明性工作流，使用 SharePoint Designer 2013 创建<br/>- 仅在特定实例Project Web App使用<br/>- 可以从 2013 Visio工作流设计<br/>- 可以导入和使用自定义操作<br/><br/> 使用 Visual Studio 2012 创建的声明性工作流<br/>- 创建可包含工作流的应用程序<br/>- 在 SharePoint.wsp (.wsp) 可包含工作流的解决方案包<br/>- 创建工作流模板以重复使用<br/>- 创建和使用自定义操作  <br/><br/>可以使用使用 WF3.5 创建的旧版已编译 (建议升级到声明性 WF4 工作流)   <br/> |声明性工作流，使用 SharePoint Designer 2013 创建<br/>- 仅在特定实例Project Web App使用<br/>- 可以从 2013 Visio工作流设计<br/>- 可以导入和使用自定义操作  <br/><br/>使用 Visual Studio 2012 创建的声明性工作流<br/>- 创建可包含工作流的应用程序  <br/>- 在 SharePoint.wsp (.wsp) 可包含工作流的解决方案包<br/>- 创建工作流模板以重复使用 <br/>- 创建和使用自定义操作  <br/> |
|**分发** <br/> |- Office基于 CSOM (应用的应用商店) <br/>- 专用应用程序目录SharePoint<br/>- Intranet 文件共享  <br/> |- Office应用商店<br/>- 专用应用程序目录SharePoint  <br/> |

   
## <a name="conclusion"></a>结束语
<a name="pj15_WhatsNew_Conclusion"> </a>

ProjectServer 2013 提供了大量新的开发功能和方案，合作伙伴和客户可以使用它们适应和扩展大型企业和小型组织中 Project Server 的功能和用途。 您可以使用 Office 2013 和 SharePoint 2013 的基础结构来帮助创建和分发 Project 2013 的应用程序，这些应用程序可极大地扩展自定义应用程序的市场性和使用。 Project 2013 中已弃用早期版本的一些扩展功能和做法，尤其是 PSI 的 ASMX Web 服务和涉及模拟或直接数据库更改的功能，这些更改不能与 Project Online 一同使用。
  
通过引入 CSOM，可以编程方式Project Online各种设备的客户端访问，并可在 Web 应用程序中使用 JavaScript。 与 PSI 相比，CSOM 提供的编程模型更加一致。 可访问 Project Server 数据的方式比之前的版本中的方式更多，包括从联机 OData 服务和通过用于报告 Project 数据库中数据的 REST 终结点。 现有报告将仍以相同的方式供内部使用；新报告更灵活。
  
Office外接程序提供了销售解决方案以及将 Project Standard 2013 与 Web 内容和其他 Office 2013 产品集成的新途径。 您还可以创建新的方法，以将 Project Professional 2013 与 Project Server 数据SharePoint通过任务窗格Office外接程序集成。
  
有关开发应用以及使用 SharePoint Server 2013 的可编程功能和 CSOM 详细信息，请参阅[SharePoint for developers](https://docs.microsoft.com/sharepoint/dev/)和 Office [for developers](https://developer.microsoft.com/office/docs)。
  
## <a name="see-also"></a>另请参阅

- [Project Server 2013 体系结构](project-server-2013-architecture.md)  
- [Project 编程任务](project-programming-tasks.md) 
- [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md) 
- [ProjectData - Project 2013 OData 服务引用](https://msdn.microsoft.com/library/office/jj163015.aspx)  
- [Project 任务窗格加载项](task-pane-add-ins-for-project.md)   
- [OData：URI 约定](https://www.odata.org/documentation/uri-conventions#FilterSystemQueryOption)    
- [面向开发人员的 SharePoint](https://msdn.microsoft.com/sharepoint)    
- [Office开发人员](https://msdn.microsoft.com/office)   
- [处理应用程序应用程序的事件SharePoint](https://msdn.microsoft.com/library/jj220048%28office.15%29.aspx)   
- [AppSource](https://appsource.microsoft.com/marketplace/apps?product=office)   
- [Project Online](https://developer.microsoft.com/project)
    

