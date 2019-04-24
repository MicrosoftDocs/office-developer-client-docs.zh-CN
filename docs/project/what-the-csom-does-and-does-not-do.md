---
title: CSOM 执行和不执行的操作
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.assetid: 6828485c-040b-4278-923f-4cc7c8fe0fb1
description: 客户端对象模型 (CSOM) 是一组适用于 Project Server 2013 的 API，它们设计为在专为电脑、移动设备和平板电脑开发的应用程序中联机和本地使用。 本文包含一些使用 CSOM 的典型应用场景，并且还列出了 CSOM 的限制。
localization_priority: Priority
ms.openlocfilehash: 6cdcb72c24e352365b6dcc9268ddf0bd249369af
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315223"
---
# <a name="what-the-csom-does-and-does-not-do"></a>CSOM 执行和不执行的操作

客户端对象模型 (CSOM) 是一组适用于 Project Server 2013 的 API，它们设计为在专为电脑、移动设备和平板电脑开发的应用程序中联机和本地使用。 本文包含一些使用 CSOM 的典型应用场景，并且还列出了 CSOM 的限制。
  
|||
|:-----|:-----|
|||
   
CSOM 支持在 Project Server 2013 中开发应用程序以及将 Project Server 与其他应用程序集成。 开发的应用程序可在电脑、移动设备（如 Windows Phone 7.5）、平板电脑（如 Windows 8 设备）和 iOS 以及 Android 设备上运行。 CSOM 提供的 API 涵盖了 Project Server 中十二种最常用 PSI 服务的功能。 CSOM API 的组织方式各不相同，它们比基于 ASMX 和基于 WCF 的 PSI 服务更易于使用。 CSOM 不使用 ADO.NET 数据集，可通过 OData 协议访问它。 可以通过 CSOM 使用 .NET Framework 4 库、JavaScript 或表述性状态转移 (REST) 查询来进行开发。
  
有关 CSOM 的概述以及介绍如何结合使用 JavaScript 和 .NET Framework 4 与 CSOM的文章，请参阅[Project Server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)。 有关 CSOM 程序集、类和成员的详细信息，请参阅 [Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx) 命名空间引参考。 
  
## <a name="usage-scenarios-for-the-csom"></a>CSOM 应用场景
<a name="pj15_WhatTheCSOM_UsageScenarios"> </a>

下面是使用 CSOM 支持的部分应用程序类型的示例。CSOM 可代替 PSI 用于多种方案：
  
- **开发扩展 Project Server 的应用程序** CSOM 的主要作用是在 Project Server 2013 中开发应用程序，在其中可以为包括电脑、移动设备和平板电脑在内的各种设备创建应用程序。 这些应用程序可以在私有应用程序目录或公共 Office 应用商店中分发。 
    
- **在 Project Server 中自动创建和管理实体** CSOM 可以对项目、任务、工作分配、企业资源、自定义字段、查阅表格、时间表、事件处理程序和工作流阶段和容器等实体执行 CRUD 操作。 往往有时候，自定义应用程序可以通过批量作业或重复作业节省时间。 
    
- **获取 Project 数据库的已发布表的数据**由于不支持直接访问草稿、已发布内容和存档表数据库，因此，你可以使用 CSOM 来读取报告表或视图中未提供的数据。 例如，获取有关工作流容器、阶段和活动的信息。 若要读取报告表中的数据，你可使用 OData 查询。 
    
- **验证状态和时间表数据**在前期事件的本地事件处理程序或远程事件接收器中使用 CSOM，以便在数据保存到 Project Web App 之前，验证用户输入的工作分配状态或时间表数据。 
    
- **创建财务项目**针对时间表中的时间捕获创建项目，以便与财务系统集成。 创建财务制度的层次结构，以反映财务系统的成本细分结构。 财务项目无需进行计划或状态更新。 
    
- **与会计系统集成**捕获与项目关联的资源成本和支出，为财务和计费系统提供数据源，以用于预算对比。 在系统之间同步任务、资源和工作分配。 捕获一个系统中的时间表数据以提供给另一个系统（使用哪种时间表取决于组织和各个项目的需要）。 
    
- **自动处理来自团队成员的更新**对于非主动管理的项目，可使用来自项目团队成员的进度和其他更改自动更新服务器上的项目。 项目经理无需查看结果或调整计划项目就可以更新和重新发布项目。 
    
    > [!NOTE]
    > CSOM 支持提交状态更新，但目前不支持状态审批。 
  
- **评估远程事件接收器中的 Project Server 数据** **ProjectCreating** 前期事件的远程事件接收器使用来自 CSOM 的 Project Server 数据帮助确定是否取消事件。 例如，在创建项目之前，将项目建议与现有项目进行比较。 
    
- **支持声明性 Project Server 工作流** CSOM 支持在 SharePoint Designer 2013 中创建的 Project Server 工作流。 CSOM 支持使用 Windows Workflow Foundation 版本 4 (WF4) 的工作流定义。 （PSI 不支持 WF4 工作流。） 
    
- **创建复杂 Project Server 工作流** 使用 Visual Studio 2012 开发工作流时，可以将 CSOM 用于工作流阶段内的复杂操作，也可以创建自定义工作流操作。 
    
## <a name="what-the-csom-does-not-do"></a>CSOM 不会执行的操作
<a name="pj15_WhatTheCSOM_DoesNotDo"> </a>

CSOM 不是 PSI 的完整替代。 由于 CSOM 在内部使用 PSI 服务，因此 CSOM 具有许多与 PSI 相同的功能限制。 除了 PSI 的限制之外，例如无法访问本地项目（.mpp 文件）中的数据，CSOM 还不包括 Project Web App 通常处理的管理功能。 例如，可以在 Project Web App 的“网站设置 - 权限”页面中处理创建自定义安全组。 
  
有关 PSI 与 CSOM 都不会处理的操作的列表，请参阅 [PSI 执行和不执行的操作](what-the-psi-does-and-does-not-do.md)中的 *PSI 不会执行的操作*部分。
  
### <a name="psi-services-that-the-csom-does-not-cover"></a>CSOM 未涵盖的 PSI 服务
<a name="pj15_WhatTheCSOM_PSIServices"> </a>

CSOM 不包含以下 PSI 服务的功能：
  
- **Admin 服务** 若要管理 Project Server 和相关项目网站中的管理设置和操作，例如创建会计期间和执行时间表设置，请使用 [WebSvcAdmin.Admin](https://msdn.microsoft.com/library/WebSvcAdmin.Admin.aspx) 类中的 PSI 方法。 Project Web App 本身在许多链接到“服务器设置”页面的页面中使用 **Admin** 方法 (https://  *ServerName*  /  *ProjectServerName*  /_layouts/15/pwa/Admin/Admin.aspx)。 
    
- **Archive 服务** 若要在存档表中保存和管理项目、资源和自定义字段等实体，请使用 [Archive](https://msdn.microsoft.com/library/WebSvcArchive.Archive.aspx) 类中的 PSI 方法。 
    
- **CubeAdmin 服务** 若要创建和管理本地安装的 OLAP 多维数据集，请使用 [WebSvcCubeAdmin.CubeAdmin](https://msdn.microsoft.com/library/WebSvcCubeAdmin.CubeAdmin.aspx) 类中的 PSI 方法，或使用 Project Web App 的“OLAP 数据库管理”页面 (https://  *ServerName*  /  *ProjectServerName*  /_layouts/15/pwa/CubeAdmin/CubeAnalysisAdmin.aspx)。 
    
    > [!NOTE]
    > Project Online 不支持 OLAP 多维数据集。 
  
- **Driver service** 若要创建和管理业务驱动因素供项目组合分析，请使用 [WebSvcDriver.Driver](https://msdn.microsoft.com/library/WebSvcDriver.Driver.aspx) 类中的 PSI 方法。 
    
- **LoginForms 服务和 LoginWindows 服务** CSOM 中的身份验证是在使用 OAuth 或 Windows 身份验证初始化 **ProjectContext** 对象的过程中完成的。 若要创建多重身份验证应用程序（其中本地完全信任应用程序可使用表单身份验证和 Windows 身份验证），请使用 [WebSvcLoginForms.LoginForms](https://msdn.microsoft.com/library/WebSvcLoginForms.LoginForms.aspx) 类和 [WebSvcLoginWindows.LoginWindows](https://msdn.microsoft.com/library/WebSvcLoginWindows.LoginWindows.aspx) 类中的 PSI 方法。 
    
- **Notification 服务** 若要管理警告和提醒，请使用 [WebSvcNotifications.Notifications](https://msdn.microsoft.com/library/WebSvcNotifications.Notifications.aspx) 类中的 PSI 方法。 
    
- **ObjectLinkProvider 服务** 若要创建和管理 Web 对象和指向文档和 SharePoint 列表项的链接，请使用 [WebSvcObjectLinkProvider.ObjectLinkProvider](https://msdn.microsoft.com/library/WebSvcObjectLinkProvider.ObjectLinkProvider.aspx) 类中的 PSI 方法。 
    
- **PortfolioAnalyses 服务** 若要创建和管理项目组合分析（包括计划工具解决方案和优化器解决方案），请使用 [WebSvcPortfolioAnalyses.PortfolioAnalyses](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.aspx) 类中的 PSI 方法。 
    
- **QueueSystem 服务** CSOM 可以获取有关 Project Server 队列作业的基本信息，并且包含 [ProjectContext.WaitForQueue](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.WaitForQueue.aspx) 方法。 若要更广泛地管理 Project Server 队列系统，请使用 [WebSvcQueueSystem.QueueSystem](https://msdn.microsoft.com/library/WebSvcQueueSystem.QueueSystem.aspx) 类中的 PSI 方法。 
    
- **Security 服务** 若要创建和管理 Project Server 安全组、模板和目录并且要检查当前用户的权限，请使用 [WebSvcSecurity.Security](https://msdn.microsoft.com/library/WebSvcSecurity.Security.aspx) 类中的 PSI 方法。 
    
- **WssInterop 服务** 若要获取有关项目网站的信息和管理项目网站，请使用 [WebSvcWssInterop.WssInterop](https://msdn.microsoft.com/library/WebSvcWssInterop.WssInterop.aspx) 类中的 PSI 方法。 
    
    > [!NOTE]
    > 你可以在 SharePoint Server 2013 中使用 CSOM。 项目网站是 SharePoint 网站。 
  
CSOM 不支持 PSI 可具有的扩展。例如，如果创建供本地使用的 PSI 扩展，则 CSOM 不能修改为使用 PSI 扩展。您可通过其他方式实现扩展方案：
  
- 聚合本地组件或 Microsoft Azure 上运行的某个组件的 CSOM 调用。
    
- 使用报告数据的 OData 查询，而不是直接访问 Project Server 数据库中的报告表。
    
- 通过 Project Online 的 OAuth 身份验证将 CSOM 调用与第三方应用程序集成，或与服务器端组件集成以供本地使用。
    
- 使用 CSOM 的应用程序还可使用本地或 SQL Azure 的自定义数据库。
    
### <a name="request-limits-of-the-csom"></a>CSOM 的请求限制
<a name="pj15_WhatTheCSOM_RequestLimits"> </a>

Project Server 2013 中的 CSOM 构建于 SharePoint Server 2013 中的 CSOM 实现之上，并且继承了请求的最大大小限制。 SharePoint 对操作请求的限制为 2 MB，对提交的二进制对象的大小限制为 50 MB。 限制请求大小是为了防止服务器受到过长操作队列和大型二进制对象的处理延迟的影响。
  
例如，如果您使用 CSOM 创建项目，然后编辑项目以添加具有最小信息量的 252 个任务（如短名称、任务 GUID 和 1d 的持续时间），则 **DraftProject.Update** 请求的数据总量小于 2 MB。但是，如果您尝试将 253 个此类任务添加到空项目，则将超出 2 MB 限制，您将收到以下异常：**Microsoft.SharePoint.Client.ServerException: 此请求使用太多资源**
  
若要通过 HTTP 或 HTTPS 捕获 CSOM 请求中的数据，你可以使用 Web 调试工具，如 [Fiddler](https://www.fiddler2.com) (https://www.fiddler2.com))。 有关实现请求大小测试并且包含可将大型请求分解为较小组的解决方案的代码示例，请参阅 [DraftProject.Update](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.DraftProject.Update.aspx)。 
  
## <a name="see-also"></a>另请参阅
<a name="pj15_WhatTheCSOM_AR"> </a>

- [Project Server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)
    
- [PSI 执行和不执行的操作](what-the-psi-does-and-does-not-do.md)
    
- [Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx)
    

