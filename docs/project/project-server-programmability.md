---
title: Project Server 可编程性
manager: lindalu
ms.date: 12/03/2019
ms.audience: Developer
f1_keywords:
- events
- PDS
- PDS compatibility
- Project Server databases
- Project Server events
- Project Server Interface
- Project Server workflow
- Project workflow
- PSI
- PSI limitations
- PSI uses
- SharePoint Services
- WF
- workflow
- Workflow Foundation
- WSS
keywords:
- Project 2013, 体系结构和可编程性, PSI, 项目, 版本, 可编程性, Project Server, PSI, 限制, Project Server 接口, 不支持的功能, Project Server 接口, PDS 兼容性, Project Server 接口, 通用, Project Server, Project 版本, 版本, 项目, Project Server, 数据库, Project 2013, 平台, Project Server 接口, 使用方案, Project Server, 事件, Project Server, Project 数据服务, 与 PSI 的兼容性, Project Server 接口
ms.assetid: a93d2153-5132-4289-af51-69350471e248
description: 了解 Project Server 2013 中的主要可编程性功能。 本文包括有关移植为早期版本的 Project Server 构建的应用程序的信息。
localization_priority: Priority
ms.openlocfilehash: e6991712b87291e90c6b4f277db84686aab384e7
ms.sourcegitcommit: 31b0a7373ff74fe1d6383c30bc67d7675b73d283
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2020
ms.locfileid: "41773727"
---
# <a name="project-server-programmability"></a>Project Server 可编程性

了解 Project Server 2013 中的主要可编程性功能。 本文包括有关移植为早期版本的 Project Server 构建的应用程序的信息。

Project Server 2013 旨在支持为 Project Server 2010 开发的大部分应用程序以及为多个平台开发的新解决方案，其中应用程序可以访问在线和本地 Project Server 安装。 必须重新设计为 Project Server 2003 或更早版本开发的应用程序和扩展，这样才能使用客户端对象模型 (CSOM) 或 Project Server 接口 (PSI)。 为 Office Project Server 2007 或 Project Server 2010 开发的应用程序可能需要进行一些更改并重新编译才能使用 PSI；要使用 CSOM，需要重新设计这些应用程序。
  
Project Server 平台通过构建 SharePoint Server 2013、.NET Framework 4 和具有 CSOM 的 OData 协议，提高了程序员的生产力水平。 开发人员可以使用应用程序、应用程序部件和 Web 部件来扩展 Project Web App，使用 SharePoint Designer 2013 定义工作流，并通过使用 Project Server 事件的远程事件接收器来实施业务规则。
  
## <a name="project-server-and-sharepoint-server"></a>Project Server 和 SharePoint Server
<a name="pj15_Programmability_MOSS"> </a>

Project Web App 构建于 SharePoint Server 2013 之上，可使用母版页和 Web 部件更轻松地构建自定义应用程序和 Project Web App 解决方案。 Project Server 2013 与 SharePoint Server 2013 深度集成，可用作项目协作、报告、网站管理、安全性和工作流管理的平台。
  
项目网站包括面向团队成员提供的更多信息和协作选项，你可以在其中添加包含项目摘要的默认应用程序、具有日程表的专用 SharePoint 任务列表、跟踪的问题、风险、项目、可交付结果和团队日历，以及文档库和团队讨论。 Project Server 2013 的自定义应用程序为团队协作提供了扩展和灵活性。 通过使用相同的机制在编辑页面时添加和编辑 Web 部件，你还可以添加应用程序部件以自定义应用程序。 你可以在安装了 Project Server 的 SharePoint 场中的任何位置找到项目网站。 若要使用 SharePoint Server 2013 的其他核心服务（如 Excel Services 和企业级搜索），管理员可以启用和配置这些服务。 
  
安装 Project Server 2013 时，可以在 SharePoint Web 服务网站中设置 Project Service Application。 Project Service Application 包含本地 Windows Communication Foundation (WCF) 和 PSI 的 ASMX Web 服务。 服务应用程序的其他示例包括 SharePoint 搜索和 SharePoint 文档管理。 有关详细信息，请参阅 SharePoint Server 2013 开发人员文档。
  
Project Service Application 是一个逻辑服务提供程序，可以管理 Project Web App 的多个实例。 Project Server 设置可在 SharePoint Web 应用程序中创建特定的 Project Web App 网站。 Project Web App 主页包含指向项目中心页面、资源中心页面、用于报告的商业智能中心页面以及包含其他标准应用程序列表的页面的链接。 图 1 显示 Project Web App 主页上“**设置**”下拉列表中的“**编辑页面**”命令，它允许你添加或编辑 Web 部件。 
  
> [!NOTE]
> Project Web App 中的某些管理页面（如“PWA 设置”页面）不可编辑，并且不会显示“**编辑页面**”命令。 Project Web App 不允许你使用 SharePoint Designer 2013 编辑页面。 你可以使用 SharePoint Designer 2013 编辑项目网站页面。 
  
**图 1. 使用 Project Web App 中的“编辑页面”菜单**

![在 Project Web Access 中编辑主页](media/pj15_Programmability_PWAHome.gif "在 Project Web Access 中编辑主页")
  
若要访问 Project Web App 中的“网站设置”页面，请在页面右上角选择“**设置**”图标。 “网站设置”页面 (  `https://ServerName/ProjectServerName/_layouts/15/settings.aspx`) 允许你更改外观和网站主题、添加自定义 Web 部件以及修改或创建项目网站的母版页。
  
不支持在 ASPX 页面中自定义代码，也不支持使用 SharePoint Designer 2013 自定义 Project Web App 母版页。 在 Project Web App 页面中自定义代码可能会导致 Project Server 更新和服务包出现问题。 
  
### <a name="customization-of-project-web-app-with-sharepoint-packages"></a>使用 SharePoint 包自定义 Project Web App
<a name="pj15_Programmability_CustomizationOfPWA"> </a>

由于 Project Web App 是 SharePoint 应用程序，而项目网站是 SharePoint 网站，因此你可以使用 SharePoint 包（.wsp 文件）或 SharePoint 应用程序（.spapp 文件）添加自定义应用程序、Web 部件、事件处理程序、自定义字段和其他功能。 SharePoint 包或应用程序包可能包含多个 Project Server 实体，其中实体定义已在程序包的 elements.xml 文件中指定。
  
对于 Project Online，你可以向 Project Web App 功能区添加按钮，但无法删除或重命名现有产品按钮，也无法创建新的功能区选项卡。 有关详细信息，请参阅[创建自定义操作以部署 SharePoint 应用程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/create-custom-actions-to-deploy-with-sharepoint-add-ins)。
  
> [!CAUTION]
> 在安装 SharePoint 包或应用程序包时，Project Server 实体的类型必须以 PSEntityProvision.xsd 架构所指定的顺序显示，否则包的架构验证将失败且安装不会完成。 
  
PSEntityProvision.xsd 架构文件位于 Project 2013 SDK 下载的 `Documentation\Schemas\AppProvisioning` 子目录中。 图 2 显示 **PSEntityProvision** 架构的 Visual Studio 中的 XML 架构资源管理器视图，其中展开了 **LookupTable** 序列。 
  
**图 2. Project Server 实体设置架构的 Visual Studio 视图**

![Project Server 实体架构的视图](media/pj15_Programmability_EntitySchema.gif "Project Server 实体架构的视图")
  
安装 Project Server 的功能的 SharePoint 包可包含遵循 **PSEntityProvision** 架构的一个或多个 elements.xml 文件。单个 XML 文件中的 Project Server 实体必须按以下顺序显示： 
  
1. 工作流阶段
    
2. 查阅表格
    
3. 自定义域
    
4. 工作流容器
    
5. 企业项目类型
    
6. 事件处理程序
    
在创建包含 Project Server 实体的 SharePoint 包时，可以将实体定义置于多个 elements.xml 文件中。每个 XML 文件均可传递架构验证，但整个包中的实体的顺序可能不正确。例如，第一个 XML 文件中的自定义域实体会引用第二个 XML 文件中的查阅表格。在安装过程中，无法创建自定义域，因为尚未创建查阅表格。
  
如果程序包安装失败，则已创建的对象仍将保留在 Project Web App 中，但该程序包无法完全安装。 重新安装程序包可以解决问题，但这对客户来说不是一个好的体验。 如果实体定义跨多个 elements.xml 文件，请在整个 SharePoint 包中整理 Project Server 实体，以确保按照正确的顺序进行安装。 使用 Project 2013 SDK 下载中的 PSEntityProvision.xsd 架构，可以开发一种工具来检查 XML 文件中规定的实体顺序。
  
## <a name="upgrading-applications-with-the-project-server-apis"></a>使用 Project Server API 升级应用程序
<a name="pj15_Programmability_APIs"> </a>

在升级已为早期版本的 Project Server 开发的应用程序时，可以选择对包含用于创建、读取、更新和删除项目实体（CRUD 操作）的方法的编程接口使用 CSOM 或 PSI。虽然 CSOM 将内部调用 PSI，但无法完全取代所有 PSI 方法。有关 PSI 和 CSOM 的方案和限制，请参阅 [What the PSI does and does not do](what-the-psi-does-and-does-not-do.md)和 [What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md)。
  
> [!NOTE]
> 如果 CSOM 包含你所需的功能，我们建议你升级应用程序以使用 CSOM。 CSOM 允许在本地和在线安装的 Project Server 2013 中使用应用程序。 
  
如果你的应用程序主要用于从 Project Server 读取数据，则对于本地方案，可以使用 Project Server 数据库中的报告表和视图。 如果你打算将该应用程序与 Project Online 一起使用，则可以将 OData 协议用于 **ProjectData** 服务，该服务提供对报告数据的本地访问和在线访问。 有关详细信息，请参阅 [ProjectData - Project OData 服务引用](https://docs.microsoft.com/previous-versions/office/project-odata/jj163015(v=office.15))
  
### <a name="using-the-psi"></a>使用 PSI
<a name="pj15_Programmability_PSI"> </a>

PSI 允许完全信任的客户端应用程序（包括Project Professional 2013、Project Web App 和 LOB 应用程序）访问 SharePoint 场中的 Project Server 数据。 PSI 与 .NET Framework 4 一起构建和使用，并且具有优势，例如包含内置安全性的已知开发环境、错误处理和垃圾收集。
  
可通过 WCF 服务或 ASMX Web 服务来访问 PSI。 ASMX 接口基于 WCF。 每个 PSI 服务通常都包含一个基类，它为该类中的项目使用 CRUD 方法。 这些项目由相关的 **DataSet** 类指定。 例如，**CustomFields** 服务包含 **CustomFields** 类，其中包含 [CreateCustomFields2](https://docs.microsoft.com/previous-versions/office/ee767959(v=office.14)) 等方法。 一个或多个企业自定义字段的数据在 **CustomFieldDataSet** 中指定。
  
> [!NOTE]
> 在 Project Server 2013 中，已弃用 PSI 的 ASMX Web 服务接口。 尽管 ASMX 接口仍然可用，但使用 PSI 的新应用程序应该使用 WCF 接口，或者如果可能，新应用程序应该使用 CSOM 而不是 PSI。 未来的 Project Server 版本将要求升级基于 ASMX 的现有应用程序，以便使用 PSI 的 WCF 接口或使用 CSOM。 
  
在 WCF 接口和 ASMX 接口中，有 22 个重复的已记录的公共 PSI 服务。 PSI 还包含 8 个未记录的私有服务。 Project Web App 和 Project Professional 使用公共 PSI 服务和私有 PSI 服务。 PSI 通常用于匹配业务对象。 也就是说，每种 PSI 方法都与业务对象相关联，例如**日历**或**资源**。 PSI 是业务对象的主要接口。 由于业务层提供可重用的业务逻辑组件，因此与 Project Server 数据交互的不同应用程序可以使用相同的业务逻辑。
  
与 Project Server 异步交互的 PSI 方法具有以 **Queue** 开头的名称。 每种 PSI 方法都通过一个独立接口来实现，该接口使用强键入的数据。 例如，**Project** 服务中的 **QueueCreateProject** 方法接受 **ProjectDataSet** 类型的 _dataset_ 参数。 **ProjectDataSet** 类派生自 **DataSet** 类型。 在 Visual Studio 中完成 .NET Framework 和 IntelliSense 的类型检查有助于减少 PSI 开发中的错误。 有关 PSI 命名空间、类、方法、属性、事件和相关程序集的详细参考的说明，请参阅 [Project PSI 参考概述](project-psi-reference-overview.md)。
  
Project Server 2013 使用 .NET Framework 的异常处理。 所有错误都记录在位于 PSI 堆栈顶部的服务器上。 某些错误会向客户端发送一个简单的报告，例如 ASMX 接口的 **SoapException** 对象或 WCF 接口的 **FaultException** 对象。 可能会在应用程序事件日志中记录异常，并且某些错误还会在统一日志记录服务 (ULS) 跟踪日志中记录服务器上的详细报告。 
  
此外，可以为本地完全信任应用程序扩展 PSI。可以将 .NET 程序集与服务一起添加，该服务提供了新功能、使用相同的 Project Server 安全基础结构并调用其他 PSI 方法或从 PSI 类继承。PSI 扩展还可提供新功能所需的业务逻辑和数据库访问权。
  
### <a name="using-the-csom"></a>使用 CSOM
<a name="pj15_Programmability_CSOM"> </a>

使用 CSOM，你可以开发访问 Project Online 或本地 Project Server 2013 安装的应用程序。 可以在公共 Office 商店或私有应用程序目录中分发应用程序。 CSOM 是易于使用的 API，它通过 LINQ 查询按名称直接使用或提供数据，而不是通过传递数据集和构建 _changeXml_ 参数或 XM _filter_ 参数来提供。 CSOM 为主要实体（如 **Project**、**Task**、**EnterpriseResource** 和 **Assignment**）实现 Project Server 接口 (PSI) 的主要功能。 CSOM 包含许多其他实体，例如 **CustomField**、**LookupTable**、**WorkflowActivities**、**EventHandler** 和 **QueueJob**，它们支持其他常见的 Project Server 功能。
  
可以通过将以下资源复制到本地开发计算机来使用 CSOM：
  
- 对于 .NET Framework 4 开发，请复制 `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\ISAPI\Microsoft.ProjectServer.Client.dll` 程序集。 
    
  有关 CSOM 类和成员的文档，请参阅 [Microsoft.ProjectServer.Client](https://docs.microsoft.com/previous-versions/office/dn529530(v=office.15)) 命名空间。 有关示例应用程序，请参阅 [CSOM 和 .NET 入门](getting-started-with-the-project-server-csom-and-net.md)。
    
- 对于 Microsoft Silverlight 开发，请复制 `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\ClientBin\Microsoft.ProjectServer.Client.Silverlight.dll` 程序集。 
    
- 若要为 Windows Phone 8 开发应用程序，请复制 `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\ClientBin\Microsoft.ProjectServer.Client.Phone.dll` 程序集。 
    
- 若要使用 JavaScript 为其他设备开发 Web 应用程序和应用程序，请复制 `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.js` 文件和 `PS.debug.js` 文件。 有关示例 Web 应用程序，请参阅 [Project Server 2013 JavaScript 对象模型入门](getting-started-with-the-project-server-2013-javascript-object-model.md)。
    
CSOM 在内部调用 PSI；因此，如果 PSI 无法工作，则 CSOM 也不能工作。 有关 CSOM 的限制，请参阅 [CSOM 执行和不执行的操作](what-the-csom-does-and-does-not-do.md)和 [PSI 执行和不执行的操作](what-the-psi-does-and-does-not-do.md)。 有关使用 CSOM 进行开发的详细信息，请参阅 [Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)和 [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)。
  
### <a name="porting-applications-built-for-project-server-2003"></a>移植为 Project Server 2003 构建的应用程序
<a name="pj15_Programmability_Porting2003"> </a>

在 Project Server 2003 中，许多数据和功能仅适用于 Project Professional 2003 或通过直接数据库访问使用。Project Server 2007 中引入的 PSI 在很大程度上消除了此限制。与 Project Server 2003 中的 Project Data Service (PDS) 不同，PSI 和 CSOM 为 Project Server 中的业务对象提供了全面的接口。
  
为 PDS 开发的应用程序与更新版本的 Project Server 不兼容。CSOM 和 PSI 为 PDS 提供了功能奇偶校验位，但与 PDS 方法或参数不匹配。
  
> [!NOTE]
> 由于必须为 Project Server 2013 完全重新设计 PDS 应用程序，因此我们建议你使用 CSOM。 
  
有关 PDS 兼容性的详细信息以及将 PDS 扩展移植到 PSI 的指南，请参阅 [PSI Web 服务中的 PDS 奇偶校验](https://docs.microsoft.com/previous-versions/office/developer/office-2007/ms197081(v=office.12))。
  
### <a name="porting-applications-built-for-project-server-2007-and-project-server-2010"></a>移植为 Project Server 2007 和 Project Server 2010 构建的应用程序
<a name="pj15_Programmability_Porting2007"> </a>

Project Server 2013 中的 PSI 是 Office Project Server 2007 和 Project Server 2010 中的 PSI 对象模型的超集。 为 Project Server 的两个先前版本构建的许多应用程序都可继续在完全信任的本地安装的 Project Server 2013 中工作。 但是，以下类型的应用程序需要更新或重新设计：
  
- 对修改为与 Project Online 一起使用的应用程序使用 CSOM。
    
- 对修改为在移动设备和平板电脑上使用的应用程序使用 CSOM。
    
- 对 Office 商店或私有应用程序目录中的可用应用程序使用 CSOM。
    
- 对于修改项目计划的应用程序，请使用 CSOM，或将应用程序更改为使用 [QueueUpdateProject2](https://docs.microsoft.com/previous-versions/office/project-class/jj236245(v=office.15)) PSI 方法。 
    
- 将用户登录到 Project Web App 的不同实例的本地或 Web 应用程序应使用 CSOM 或 PSI 的 WCF 终结点编程设置。 这些方法已弃用。 应用程序应使用 OAuth 身份验证代替窗体身份验证，并与 Project Online 一起使用。 有关详细信息，请参阅 [SharePoint 2013 中应用程序的授权和身份验证](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/authorization-and-authentication-of-sharepoint-add-ins)。
    
- 依赖于或修改特定 Project Server 安全设置的应用程序。
    
  > [!NOTE]
  > Project Server 2013 的默认本地安装使用 SharePoint 权限模式，其中无法通过 PSI 访问 Project Server 安全设置。 若要更改 Project 权限模式，请参阅 [Project Server 2013 中面向 IT 专业人员的新增功能](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2016)中的 *SharePoint 权限模式*部分。 
  
- 对于许多自定义 Project Server 工作流，你可以使用 SharePoint Designer 2013 创建声明性工作流。 对于需要额外编程的自定义工作流，你*不应该*直接使用 **Microsoft.Office.Project.Server.Workflow** 命名空间中的类或成员。 请改用 CSOM 中的 [Microsoft.ProjectServer.Client.WorkflowActivities](https://docs.microsoft.com/previous-versions/office/mt780562(v=office.15)) 类。 
    
- 通常，应该将使用模拟的应用程序重写为使用 PSI 的 WCF 接口。 为其他用户执行简单状态更新的应用程序不需要模拟。 它们可以使用 CSOM 中的 [StatusAssignment.SubmitStatusUpdates](https://docs.microsoft.com/previous-versions/office/project-class/jj235883(v=office.15)) 方法或 PSI 中的 [Statusing.SubmitStatusForResource](https://docs.microsoft.com/previous-versions/office/ee755393(v=office.14)) 方法。 
    
- 在 Project Server 计算机上运行的中间件组件只能在本地安装使用，并且必须使用 PSI 的 WCF 接口。 例如，使用 ASMX 接口在本地 Project Web App 和外部时间表应用程序之间交换数据的中间件组件必须重写为使用 PSI 的 WCF 接口。 若要使用 Project Online，必须将组件重新设计为应用程序并使用 CSOM。
    
### <a name="migration-and-compatibility-of-custom-solutions"></a>自定义解决方案的迁移和兼容性
<a name="pj15_Programmability_CustomSolutions"> </a>

PSI 的公共 ASMX 和 WCF 接口中的类和成员是相同的。 但是，在 Project Server 2013 和 Project Server 的两个先前版本之间，PSI 方法使用或返回的数据表列数和大小可能不同。 此外，与先前版本中的报告数据库相比，报告表和视图也存在差异。
  
> [!IMPORTANT]
> 强烈建议你先在 Project Server 2013 的非生产安装中全面测试解决方案，然后再将其部署到生产服务器。 
  
在将解决方案迁移到 Project Server 2013 时，或在解决方案未按预期运行的情况下，你至少应执行以下操作：
  
- 通过在 Visual Studio 2012 中打开解决方案来进行更新。 某些解决方案还可以使用 Visual Studio 2010。
    
- 将目标更改为 .NET Framework 4。
    
- 更改程序集引用以使用 Project Server 2013 程序集，如 Microsoft.Office.Project.Server.Library.dll 和 Microsoft.Office.Project.Server.Events.Receivers.dll。
    
- 列出 ASMX Web 引用或 WCF 服务引用和命名空间名称，然后删除 Project Server 引用。
    
- 添加可以从 Project 2013 SDK 下载的 WCF 代理源文件构建的 ProjectServerServices.dll 代理程序集，或者为所需的 WCF 服务添加代理源文件。 对于 ASMX 服务，请使用相同的命名空间名称再次添加前端 ASMX Web 服务引用；或者添加可以从 Project 2013 SDK 下载的 WSDL 源构建的 ProjectServerServices.dll 代理程序集。
    
  > [!NOTE]
  > 在 Project 2013 SDK 下载中，代理源文件中的命名空间均以 *Svc* 开头。 例如，WCF 代理文件和 ASMX 代理文件中的 **Resource** 服务命名空间是 **SvcResource**。 > 如果应用程序使用不同的命名空间名称，则可以将代理程序集重新编译为使用你的命名空间，或者更改应用程序中的 PSI 命名空间。 例如，你可以修改 CompileWCFProxyAssembly.cmd 脚本，并从 SDK 下载的代理源文件中重新编译 ProjectServerServices.dll。 
  
- 如果你从使用 PSI 的 ASMX 接口更改为使用 WCF 接口，则可以编程方式或通过使用 app.config 中的 WFC 终结点初始化客户端类。在必须快速切换到 Project Web App 的其他实例时，或在开发使用 PSI 的 Web 部件时使用编程初始化。
    
- Project Server 2013 的 PSI 服务中有几个新方法和数据集，并且某些 **DataRow** 类包含新属性。 例如，PSI 中的 [QueueUpdateProject2](https://docs.microsoft.com/previous-versions/office/project-class/jj236245(v=office.15)) 方法使用 Project Server 计划引擎来重新计划更新的项目，而无需在 Project Professional 2013 中打开该项目，它还允许在同一次调用中添加或删除项目实体。 
    
- 编译和测试解决方案。
    
## <a name="project-scheduling-on-the-server"></a>服务器上的项目计划
<a name="pj15_Programmability_Scheduling"> </a>

Project Server 2013 具有两个计划引擎。 新版计划引擎与 Project Professional 2013 中的计划引擎相同。 通过使用 Project Web App 或项目网站中的计划 Web 部件（“项目详细信息”页面）或使用 CSOM 来更改计划和发布更改时，日期、成本、工期、剩余工时、基线以及与计划相关的其他更改的计算方式与使用 Project Professional 2013 更改和发布项目时采用的方式相同。 但是，除了 [QueueUpdateProject2](https://docs.microsoft.com/previous-versions/office/project-class/jj236245(v=office.15)) 方法之外，PSI 方法可使用从 Project Server 2010 迁移的旧版计划引擎。 原因是确保旧版应用程序在 Project Server 2013 中的行为与以前相同。 
  
> [!NOTE]
> 若要在 Project Server 2013 中使用更新的计划引擎，应用程序可使用 CSOM。 
  
旧版计划引擎和新版计划引擎都具有以下限制：
  
- **仅限单个项目计划** 当使用 PSI、CSOM 或Project Web App 通过任务状态更新进行更改时，计划仅影响当前项目。 如果当前项目具有指向其他项目、子项目或主项目的链接，则链接的项目不会发生更改。 
    
- **摘要任务** 在 Project Server 上，摘要任务通常为只读。 例如，无法创建摘要任务的分配，并且无法修改完成百分比。 但是，Project Server 支持编辑手动计划的摘要任务的日期和工期。 
    
    Project Server 上的实际数据不会自动添加到摘要任务工作分配，因为这可能绕过 Project Server 中的审批流程。在 Project Professional 中，当您向子任务添加实际数据时，也会为摘要任务的工作分配添加这些实际值。用户可能会混淆行为上的差异。
    
    如果子任务工期缩短或完成日期发生更改，则 Project Server 会删除摘要任务工作分配的实际值。
    
    > [!CAUTION]
    > 虽然 Project Professional 可执行此操作，但建议您不要对摘要任务进行工作分配。 
  
以下是使用旧版 Project Server 计划引擎进行 PSI 编程的问题和限制：
  
- **更改任务的活动状态** 当你使用 [QueueUpdateProject](https://docs.microsoft.com/previous-versions/office/ms471014(v=office.14)) 方法更改任务的活动状态时，如果 **ProjectDataSet** 对象的 _dataset_ 参数存在多项更改，则旧版 Project Server 计划引擎可能会显示不一致的开始或结束时间。 如果在 **QueueUpdateProject** 的 _dataset_ 参数中，**TASK_IS_ACTIVE** 属性是唯一发生更改的属性，则你可以更新项目。
    
    有关非活动任务和旧版计划引擎的详细信息，请参阅博客文章 [Project 2010 中的非活动任务简介](https://blogs.msdn.com/b/project/archive/2010/06/10/introducing-inactive-tasks-in-project-2010.aspx)和 [Project Server 2010：在 Web、PSI 和 Project Professional 上创建计划](https://blogs.msdn.com/b/brismith/archive/2010/09/10/project-server-2010-scheduling-on-the-web-the-psi-and-project-professional.aspx?wa=wsignin1.0)。 有关 Project Professional 2010 中的计划与 Project Server 2010 中的 Project Web App 的比较，请参阅[基于 Web 的计划管理比较](https://blogs.msdn.microsoft.com/brismith/2010/09/10/project-server-2010-scheduling-on-the-web-the-psi-and-project-professional/)。
    
- **未计算的挣值** 旧版计划引擎不会计算以下挣值域：ACWP、BAC、BCWP、BCWS、CPI、CV、CV％、EAC、SPI、SV、SV％、TCPI、VAC、工期差异、开始时间差异、完成时间差异、成本差异和工时差异。 如果项目具有这些域值，并且是使用 **QueueUpdateProject** 方法更新的，则域值不会发生更改。 若要避免此问题，请使用 **QueueUpdateProject2** 方法。 
    
你可以通过以下方式处理 PSI 计划限制：
  
- 如果 CSOM 具有应用程序所需的方法，则使用 CSOM 而非 PSI。
    
- 在 Project Professional 中打开项目，并将这些项目保存回 Project Server。
    
- 在报表中，不要包括 PSI 未更新的域。
    
- 在报表中添加有关数据可能过时的说明。
    
报告表和多维数据集中存在可帮助您检测某些项目数据未更新的情况的标记。MSP_EpmProject 表和 MSP_EpmProject_UserView 中的报表数据包括以下域： 
  
-  _ProjectWbsIsStale_ &ndash; 指示工作分解结构（任务大纲层次结构）是否已过时。 
    
-  _ProjectEarnedValueIsStale_ &ndash; 指示挣值域已过时。 
    
-  _ProjectRollupsAreStale_&ndash; 指示子项目已在草稿数据库中更新，但主项目未更新。 子项目中的汇总值已过时。 
    
-  _ProjectHierarchyNotSynchronized_ &ndash; 主项目与其子项目不同步。 当子项目显式发布而不是作为主项目的一部分进行发布时，会发生这种情况。 
    
-  _ProjectCalculationsAreStale_ &ndash; Project Professional 在没有计算计划的情况下保存项目（即在“**项目选项**”对话框的“**计划**”选项卡上将计算模式设置为“**手动**”）。 
    
-  _ProjectGhostTaskAreStale_ &ndash; 与 _ProjectHierarchyNotSynchronized_ 类似，但会针对跨项目链接数据发出警告。 可以没有主项目，但链接一端的项目数据比另一端的项目数据更新。
    
## <a name="about-accessing-the-project-server-database"></a>有关访问 Project Server 数据库
<a name="pj15_Programmability_Databases"> </a>

如果你在 Microsoft SQL Server 中具有访问 Project Server 数据库的权限，则可以读取报告表和视图。 如果你具有必要的 Project Server 权限，则还可以使用 OData 查询从报告表中读取数据。 强烈建议开发人员不要通过 Project Server 数据库中的 SQL Server 查询直接访问草稿、已发布或存档的表格。 在 Project Server 数据库的任何表格中直接进行更改可能会破坏引用的完整性，并通过 Project Server 队列服务干扰数据库访问。
  
> [!IMPORTANT]
> 任何项目都不会主动阻止您使用直接编程数据库访问来更新数据。您应知道，Project Professional 缓存、已发布的表和报告表都依赖于可由直接数据编辑中断的缓存同步协议。在此警告您，如果您由于使用直接访问更改数据而破坏了 Project Server 数据库或损坏了 Project Professional 客户端缓存，产品支持将无法提供帮助！ 
  
直接访问草稿、已发布或存档表和视图的应用程序也依赖于数据库架构，它们可能会在 Project Server 2013 的服务包或更高版本中发生更改。 直接访问数据库的应用程序还会失去 Project Server 内置安全性、常见业务逻辑、跟踪、审计、错误检查、报告、工作流和其他功能。 在 Project Server 2013 更新后，你可能需要重写此类应用程序。 
  
出于上述所有原因，Project Professional 和 Project Web App 不会直接调用草稿、已发布或存档表；与 Project Server 集成的任何其他应用程序也不应这样做。
  
草稿、已发布和存档表的架构未编档。 可以使用报告表来帮助生成报表，报告表和视图的架构将编档在 Project 2013 SDK 下载中。 有关报告数据的 OData 架构，请参阅 [ProjectData - Project OData 服务引用](https://docs.microsoft.com/previous-versions/office/project-odata/jj163015(v=office.15))。
  
## <a name="see-also"></a>另请参阅

- [Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)    
- [Project Server 2013 体系结构](project-server-2013-architecture.md)    
- [PSI 执行和不执行的操作](what-the-psi-does-and-does-not-do.md)   
- [CSOM 执行和不执行的操作](what-the-csom-does-and-does-not-do.md)    
- [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)    
- [开始开发 Project Server 工作流](getting-started-developing-project-server-workflows.md)    
- [Project 2013 编程参考](project-2013-programming-references.md)    
- [Project PSI 参考概述](project-psi-reference-overview.md)    
- [创建自定义操作以部署 SharePoint 应用程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/create-custom-actions-to-deploy-with-sharepoint-add-ins)    
- [Project 2010 中的非活动任务简介](https://blogs.msdn.com/b/project/archive/2010/06/10/introducing-inactive-tasks-in-project-2010.aspx)    
- [Project Server 2010：在 Web、PSI 和 Project Professional 上创建计划](https://blogs.msdn.microsoft.com/brismith/2010/09/10/project-server-2010-scheduling-on-the-web-the-psi-and-project-professional/)

