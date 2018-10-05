---
title: CSOM 执行的操作和不执行的操作
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6828485c-040b-4278-923f-4cc7c8fe0fb1
description: 客户端对象模型 (CSOM) 是一套的联机设计用于 Project Server 2013 的 Api 和应用程序可以开发用于 Pc 和移动设备或平板电脑中使用的内部部署。 本文包含使用 CSOM 的一些典型方案，并还列出了 CSOM 的限制。
ms.openlocfilehash: ad9f9e0404cb0063a1c58c8e66a022372881a24f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399289"
---
# <a name="what-the-csom-does-and-does-not-do"></a>CSOM 执行和不执行的操作

客户端对象模型 (CSOM) 是一套的联机设计用于 Project Server 2013 的 Api 和应用程序可以开发用于 Pc 和移动设备或平板电脑中使用的内部部署。 本文包含使用 CSOM 的一些典型方案，并还列出了 CSOM 的限制。
  
|||
|:-----|:-----|
|||
   
CSOM 启用的 Project Server 2013 的应用程序开发和 Project server 与其他应用程序的集成。 可以开发应用程序在 Pc，如 Windows 8 的设备和 iOS 和 Android 设备的平板电脑等 Windows Phone 7.5，移动设备上运行。 CSOM 提供最常涵盖的 12 个功能的 Api 在 Project Server 中使用 PSI 服务。 CSOM Api 不同组织，并且易于使用比基于 ASMX 和基于 WCF 的 PSI 服务。 CSOM 不使用 ADO.NET 数据集，可通过 OData 协议。 可以通过使用.NET Framework 4 库、 JavaScript、 开发与 CSOM 或代表性状态传输 (REST) 查询。
  
CSOM 和文章介绍如何使用 CSOM JavaScript 和.NET Framework 4 的概述，请参阅[Project server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)。 有关 CSOM 程序集、 类和成员的详细信息，请参阅[Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx)命名空间引用。 
  
## <a name="usage-scenarios-for-the-csom"></a>CSOM 的使用方案
<a name="pj15_WhatTheCSOM_UsageScenarios"> </a>

下面是使用 CSOM 支持的部分应用程序类型的示例。CSOM 可代替 PSI 用于多种方案：
  
- **开发应用程序的扩展 Project Server**CSOM 的主要用途是 Project Server 2013，可以在其中将应用程序创建的各种包括 Pc 和移动设备或平板电脑设备的应用程序开发。 在专用应用程序目录或公共 Office 商店中，可以将分发应用程序。 
    
- **自动创建或管理的 Project Server 中的实体**CSOM 可执行 CRUD 操作，如项目、 任务、 工作分配、 企业资源、 自定义字段、 查阅表格、 时间表、 事件处理程序和工作流阶段和阶段的实体。 通常是其中自定义应用程序可以节省时间批量或重复作业的情况。 
    
- **获取已发布的 Project 数据库表中的数据**因为直接数据库访问草稿、 发布，并将存档表不支持，您可以使用 CSOM 读取在报表的表或视图中不可用的数据。 例如，获取有关工作流阶段、 阶段、 和活动的信息。 若要读取报告表中的数据，您可以使用 OData 查询。 
    
- **验证状态和时间表数据**使用 CSOM 本地事件处理程序或远程事件接收器的前事件来验证用户输入之前的数据保存 Project Web App 中的工作分配状态或时间表数据。 
    
- **创建财务项目**创建与财务系统时间捕获到时间表以供集成的项目。 创建层次结构，反映财务系统的成本细分结构的财务代码。 财务项目不需要日程安排或状态更新。 
    
- **与会计系统集成**捕获资源成本和开支关联与源财务和帐单系统的项目和预算比较目的。 同步任务、 资源和系统之间的工作分配。 在源另一个系统中捕获时间表数据 （使用哪些时间表取决于或单个项目的组织的需要）。 
    
- **来自工作组成员的自动更新**对于未主动管理的项目，自动更新进度与其他更改来自项目团队成员服务器上的项目。 项目可以更新和重新发布没有项目经理审阅结果或进行调整计划。 
    
    > [!NOTE]
    > CSOM 支持提交状态更新，但当前不支持状态审批。 
  
- **远程事件接收器中的评估 Project Server 数据****项目创建**前期事件的远程事件接收器可以使用 Project Server CSOM 数据来帮助确定是否来取消事件。 例如之前创建的项目，比较项目建议与现有项目。 
    
- **支持声明性的 Project Server 工作流**CSOM 启用 SharePoint Designer 2013 中创建的 Project Server 工作流。 CSOM 支持使用 Windows Workflow Foundation 版本 4 (WF4) 的工作流定义。 （PSI 不支持 WF4 工作流）。 
    
- **创建复杂的 Project Server 工作流**当开发工作流使用 Visual Studio 2012 的服务器时，可以在工作流容器内的复杂操作中使用 CSOM 或创建自定义工作流操作。 
    
## <a name="what-the-csom-does-not-do"></a>CSOM 不会执行的操作
<a name="pj15_WhatTheCSOM_DoesNotDo"> </a>

CSOM 不是 PSI 的完整的替换。 CSOM 内部使用 PSI 服务，因为 CSOM 具有许多 PSI 具有相同功能的限制。 除了的 PSI，如本地项目 （.mpp 文件），在具有数据不能访问限制 CSOM 未包含 Project Web App 通常处理的管理功能。 例如，创建自定义安全组可以处理网站设置的 Project Web app 的权限页面中。 
  
PSI 和 CSOM 都不处理的操作的列表，请参阅[What the PSI 执行 and 不可实现的操作](what-the-psi-does-and-does-not-do.md)中的*What the PSI 不可实现的操作*部分。
  
### <a name="psi-services-that-the-csom-does-not-cover"></a>CSOM 未包含的 PSI 服务
<a name="pj15_WhatTheCSOM_PSIServices"> </a>

CSOM 未包含下列 PSI 服务的功能：
  
- **管理服务**若要管理的管理设置和操作 Project Server 中和相关的项目网站，如创建财政周期和进行时间表设置使用[WebSvcAdmin.Admin](https://msdn.microsoft.com/library/WebSvcAdmin.Admin.aspx)类中的 PSI 方法。 Project Web App 本身中的许多链接到服务器设置页的页面使用**管理员**方法 (https:// *ServerName*  /  *ProjectServerName* /_layouts/15/pwa/Admin/Admin.aspx)。 
    
- **存档服务**若要保存和管理项目、 资源和在存档表中的自定义字段等实体，请使用[存档](https://msdn.microsoft.com/library/WebSvcArchive.Archive.aspx)类中的 PSI 方法。 
    
- **CubeAdmin 服务**若要创建和管理 OLAP 多维数据集的本地安装，在[WebSvcCubeAdmin.CubeAdmin](https://msdn.microsoft.com/library/WebSvcCubeAdmin.CubeAdmin.aspx)类中，使用 PSI 方法，或使用 OLAP 数据库管理页 (https:// *ServerName*  /  *ProjectServerName* /_layouts/15/pwa/ CubeAdmin/CubeAnalysisAdmin.aspx) Project Web App 中。 
    
    > [!NOTE]
    > Project Online 不支持 OLAP 多维数据集。 
  
- **Driver 服务**若要创建和管理业务驱动因素供项目组合分析，请使用[WebSvcDriver.Driver](https://msdn.microsoft.com/library/WebSvcDriver.Driver.aspx)类中的 PSI 方法。 
    
- **LoginForms 服务和 LoginWindows 服务**在初始化**ProjectContext**对象，使用 OAuth 或 Windows 身份验证的过程完成 CSOM 中的身份验证。 若要为多重身份验证，其中本地完全信任应用程序可以使用表单身份验证和 Windows 身份验证，创建应用程序使用[WebSvcLoginForms.LoginForms](https://msdn.microsoft.com/library/WebSvcLoginForms.LoginForms.aspx)类和[中的 PSI 方法WebSvcLoginWindows.LoginWindows](https://msdn.microsoft.com/library/WebSvcLoginWindows.LoginWindows.aspx)类。 
    
- **通知服务**若要创建和管理通知和提醒，请使用[WebSvcNotifications.Notifications](https://msdn.microsoft.com/library/WebSvcNotifications.Notifications.aspx)类中的 PSI 方法。 
    
- **ObjectLinkProvider service**若要创建和管理 web 对象和指向文档和 SharePoint 列表项，使用[WebSvcObjectLinkProvider.ObjectLinkProvider](https://msdn.microsoft.com/library/WebSvcObjectLinkProvider.ObjectLinkProvider.aspx)类中的 PSI 方法。 
    
- **PortfolioAnalyses 服务**创建和管理项目组合分析，包括计划工具解决方案和优化器解决方案使用[WebSvcPortfolioAnalyses.PortfolioAnalyses](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.aspx)类中的 PSI 方法。 
    
- **QueueSystem 服务**CSOM 可获取有关 Project Server 队列作业的基本信息，并包括[ProjectContext.WaitForQueue](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.WaitForQueue.aspx)方法。 用于更复杂管理的 Project Server 队列系统中，使用[WebSvcQueueSystem.QueueSystem](https://msdn.microsoft.com/library/WebSvcQueueSystem.QueueSystem.aspx)类中的 PSI 方法。 
    
- **安全服务**若要创建和管理 Project Server 安全组、 模板和类别，并检查当前用户的权限，使用[WebSvcSecurity.Security](https://msdn.microsoft.com/library/WebSvcSecurity.Security.aspx)类中的 PSI 方法。 
    
- **WssInterop 服务**若要获取有关的信息和管理项目网站，使用[WebSvcWssInterop.WssInterop](https://msdn.microsoft.com/library/WebSvcWssInterop.WssInterop.aspx)类中的 PSI 方法。 
    
    > [!NOTE]
    > 您可以在 SharePoint Server 2013 中使用 CSOM。 项目网站的 SharePoint 网站。 
  
CSOM 不支持 PSI 可具有的扩展。例如，如果创建供本地使用的 PSI 扩展，则 CSOM 不能修改为使用 PSI 扩展。您可通过其他方式实现扩展方案：
  
- 聚合本地组件或 Microsoft Azure 运行的组件中的 CSOM 调用。
    
- 使用报告数据的 OData 查询，而不是直接访问 Project Server 数据库中的报告表。
    
- 与第三方应用程序通过从 Project Online 的 OAuth 身份验证或用于内部部署的服务器端组件集成 CSOM 调用。
    
- 使用 CSOM 的应用程序也可以使用自定义数据库内部或与 SQL Azure。
    
### <a name="request-limits-of-the-csom"></a>CSOM 的请求限制
<a name="pj15_WhatTheCSOM_RequestLimits"> </a>

Project Server 2013 中的 CSOM 基于 SharePoint Server 2013 中的 CSOM 实现和继承请求的最大大小限制。 SharePoint 具有 2 MB 限制对于操作请求和提交二进制对象的大小为 50 MB 限制。 仅限于保护服务器从过长队列的操作和处理二进制大型对象的延迟的请求大小。
  
例如，如果您使用 CSOM 创建项目，然后编辑项目以添加具有最小信息量的 252 个任务（如短名称、任务 GUID 和 1d 的持续时间），则 **DraftProject.Update** 请求的数据总量小于 2 MB。但是，如果您尝试将 253 个此类任务添加到空项目，则将超出 2 MB 限制，您将收到以下异常：**Microsoft.SharePoint.Client.ServerException: 此请求使用太多资源**
  
要捕获的 CSOM 请求中的数据通过 HTTP 或 HTTPS，您可以使用 web 调试工具，如[Fiddler](https://www.fiddler2.com) (https://www.fiddler2.com)。 实现请求大小的测试，包括到大型请求将断开与较小的组的解决方案的代码示例，请参阅[DraftProject.Update](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.DraftProject.Update.aspx) 。 
  
## <a name="see-also"></a>另请参阅
<a name="pj15_WhatTheCSOM_AR"> </a>

- [Project Server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)
    
- [PSI 执行和不执行的操作](what-the-psi-does-and-does-not-do.md)
    
- [Microsoft.ProjectServer.Client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.aspx)
    

