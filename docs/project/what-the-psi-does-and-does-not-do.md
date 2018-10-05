---
title: PSI 可实现的操作和不可实现的操作
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: eac6be6a-9a20-4bc0-8da2-b2fd93aab04f
description: Project Server 接口 (PSI) 可帮助自动在本地安装的 Project Server 2013 中的多个服务器端进程。 但是，多个函数需要使用 Microsoft Project Professional 2013。
ms.openlocfilehash: b93c3535ca6693a84d11370de17bc18375f168ab
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386339"
---
# <a name="what-the-psi-does-and-does-not-do"></a>PSI 执行和不执行的操作

Project Server 接口 (PSI) 可帮助自动在本地安装的 Project Server 2013 中的多个服务器端进程。 但是，多个函数需要使用 Microsoft Project Professional 2013。
  
|||
|:-----|:-----|
|||
   
PSI 专为补充 Project Professional 2013 的功能，而不是所有 Project Professional 功能都提供基于服务器的替代。 第三方开发人员可以使用 PSI 可帮助您创建的 Project Web App 和项目工作区的本地安装的 Web 部件，请创建自定义 Windows 应用程序和 web 应用程序与内部部署 Project Server 数据进行交互，开发工作流项目组合管理的逻辑开发本地完全信任事件处理程序，并将 Project Server 与其他应用程序相集成。 PSI 不能用于开发的应用程序的 Office 商店、 移动设备或平板电脑;对于，您可以使用客户端对象模型 (CSOM)。
  
> [!NOTE]
> PSI 提供更全面编程接口的 Project Server 2013 比 CSOM 提供。 但是，除非 CSOM 未提供所需的功能，我们建议使用 CSOM 开发新的应用程序。 有关详细信息，请参阅[What the CSOM 执行和不可实现的操作](what-the-csom-does-and-does-not-do.md)。 
  
## <a name="usage-scenarios-for-the-psi"></a>PSI 的使用方案
<a name="pj14_WhatPSIDoes_UsageScenarios"> </a>

以下是 PSI 支持的针对服务器端项目和计算的一些应用的示例：
  
- **自动创建或管理的 Project Server 中的实体**虽然 Project Professional 2013 和 Project Web App 一起旨在处理管理和创建项目、 企业资源和自定义字段等实体，有通常情况下，自定义应用程序可以节省时间与批量或重复性的作业。 PSI 可以自动执行几种 CSOM 不会执行的作业，例如，与 OLAP 多维数据集、 项目组合分析、 业务驱动因素、 通知、 对象链接提供程序、 安全性和 SharePoint 互操作性。 
    
- **获取或 Project 数据库的存档表中已发布的数据**因为直接数据库访问草稿、 发布，并将存档表不支持，您可以使用 PSI 读取在报表的表或视图中不可用的数据。 例如，获取有关项目版本、 日期和存储在存档表中，更改的信息，然后填充具有信息的 web 部件中的 JS 网格控件。 
    
- **验证状态和时间表数据**在本地前期事件处理程序中使用 PSI 验证用户输入之前的数据保存 Project Web App 中的工作分配状态或时间表数据。 
    
- **维护项目**创建占位符用于资源计划的项目。 保留时间或簿时间对资源的维护工作或基本业务。 维护项目通常没有任务。 
    
- **创建财务项目**创建与财务系统时间捕获到时间表以供集成的项目。 创建层次结构，反映财务系统的成本细分结构的财务代码。 财务项目不需要日程安排或状态更新。 
    
- **与会计系统集成**捕获资源成本和开支关联与源财务和帐单系统的项目和预算比较目的。 同步任务、 资源和系统之间的工作分配。 在源另一个系统中捕获时间表数据 （使用哪些时间表取决于或单个项目的组织的需要）。 
    
- **来自工作组成员的自动更新**对于未主动管理的项目，自动更新进度与其他更改来自项目团队成员服务器上的项目。 项目可以更新和重新发布没有项目经理审阅结果或进行调整计划。 
    
- **完全信任的本地事件处理程序中的评估 Project Server 数据**本地事件处理程序**项目创建**前期事件可以使用 PSI 中的 Project Server 数据来帮助确定是否可取消事件。 例如之前创建的项目，比较项目建议与现有项目。 
    
- **需求管理创建自定义工作流活动**在本地、 完全信任工作流活动中使用 PSI 修改和更新项目建议根据企业项目模板。 使用项目自定义域标记项目所需的初始和批准过程的信息。 添加任务，以确定关键里程碑或可交付结果的项目阶段。 当批准项目建议时，工作流可以更改到与 Project Professional 全面项目管理的建议。 
    
- **创建 PSI 扩展**(**弃用。** 扩展 Project Server 2013 中弃用和将来版本中将不支持）使用 Windows Communication Foundation (WCF) 接口，可使用自定义服务的扩展 PSI。 PSI 扩展的 Project Server 计算机上，运行，并且可以使用内置的 PSI 服务使用的同一安全基础结构。 扩展可以查询报告表、 使用单独的数据库表，将其整合到保存带宽，并将与第三方应用程序和其他服务器端组件集成的 PSI 调用。 有关详细信息，请参阅[开发 PSI 扩展](https://msdn.microsoft.com/library/1b484623-94fb-47c9-84c1-3e68a9133042%28Office.15%29.aspx)。
    
- **在本地、 完全信任的应用程序中使用模拟**可以模拟 PSI 的 WCF 接口的呼叫，以便应用程序假定模拟用户的安全权限。 慎用和仔细，应使用模拟。 读取和更新为其他用户的状态信息不需要模拟。 新的应用程序需要模拟应该使用 CSOM 和 OAuth 协议，而非 PSI。 有关使用 PSI 的模拟的详细信息，请参阅[使用模拟 with WCF](https://msdn.microsoft.com/library/e3597901-2f02-44a2-8076-d32aae540b38%28Office.15%29.aspx)。
    
> [!NOTE]
> 在某些情况下，可以使用 CSOM 和 Project Online 的客户端应用程序中使用 PSI。 如果您使用基于 ASMX 的 PSI web 服务，应用程序必须包括进行身份验证中 CSOM 的[Microsoft.ProjectServer.Client.ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx)对象的方法以及身份验证**方法System.Web.Services.Protocols.SoapHttpClientProtocol**客户端对象。 使用 SharePoint CSOM 与 web 服务的示例，请参阅[SharePoint Online Using Claims-Based 身份验证中的远程身份验证](https://msdn.microsoft.com/library/49067f7a-3020-478f-ba97-4b7ce3ea9b87%28Office.15%29.aspx)。 > 由于的约束的应用程序级权限，PSI 不能用于设计的应用程序中公共 Office 商店中的通讯组。 在这种情况下，您可以使用仅 CSOM。 
  
## <a name="what-the-psi-does-not-do"></a>PSI 不可实现的操作
<a name="pj14_WhatPSIDoes_DoesNotDo"> </a>

虽然 PSI 可实现的操作有很多，但也有一些操作是 PSI 不可实现的。以下是 PSI 不可实现的两项操作，但 CSOM 可实现这两项操作。
  
### <a name="project-online-and-remote-event-receivers"></a>Project Online 和远程事件接收器

使用 Project Online PSI 的主要限制。 使用 PSI 应用程序需要完全信任访问的 Project Server 的本地安装。 例如，PSI 不能在中使用远程事件接收器事件接收器作为 Microsoft Azure 上的服务的安装。
  
### <a name="workflows-and-claims-authentication"></a>工作流和声明身份验证

工作流定义 that uses Windows Workflow Foundation 版本 4 (WF4) 需要 PSI 不直接支持的声明身份验证。 这意味着不能使用 PSI 具有企业项目类型 (EPT) 与 WF4 工作流定义的 Project Server 2013 中创建项目。
  
PSI 可用于与已没有工作流或使用旧 WF3.5 定义 （Project Server 2010 中的工作流版本） 的 Ept 创建项目。 使用具有 WF4 定义 EPT 创建项目，请使用 CSOM。
  
 **需要 Project Professional 的操作：**
  
下面列出了 PSI 和 CSOM 都不可实现的操作。
  
#### <a name="local-data"></a>本地数据

- 操作本地项目（.mpp 文件）中的数据。例如，定义成本费率表或本地资源的可用性分布。 
    
- 定义或编辑本地基准日历或资源日历，包括日历例外。
    
- 定义本地自定义域。（PSI 支持编辑针对任务、资源和工作分配的本地自定义域值。）
    
#### <a name="enterprise-data"></a>企业数据

- 签出或编辑企业全局模板。 Project Server 2013 中的企业全局数据是一套在 Project 数据库，而非 Office Project Server 2007 和早期版本的项目模板中的二进制模拟运算表。
    
- 定义或编辑企业日历。 [日历](https://msdn.microsoft.com/library/WebSvcCalendar.Calendar.aspx)方法管理仅日历例外。 
    
#### <a name="master-projects-and-cross-project-links"></a>主项目和跨项目链接

- 创建主项目并插入子项目。
    
- 计划跨主项目的关键路径。 
    
- 创建跨项目链接。
    
#### <a name="resources"></a>资源

- 请求或执行资源调配。
    
- 更改工作分配的资源。（您可以使用 PSI 删除工作分配和创建新的工作分配。）
    
- 删除或替换具有已接受实际工时的资源（实际值）。
    
- 更改工时、材料或成本之间的资源类型。
    
- 创建或编辑资源日历。
    
- 在向任务中添加资源时，PSI 不会按照 Project Professional 所采用的方式自动重新分发工时。这取决于开发人员选择和显式设置工作分配的工时分发。
    
#### <a name="cost-resources"></a>成本资源

- 编辑、 创建或删除成本资源和工作分配使用[项目](https://msdn.microsoft.com/library/WebSvcProject.Project.aspx)方法。 [资源](https://msdn.microsoft.com/library/WebSvcResource.Resource.aspx)方法可以创建成本资源，但不能编辑它们。 
    
#### <a name="work-contours"></a>工时分布

- 编辑按时间分段的数据。
    
    > [!NOTE]
    > **Statusing** Web 服务中的[UpdateStatus](https://msdn.microsoft.com/library/WebSvcStatusing.Statusing.UpdateStatus.aspx)方法可以项目经理更新和发布工作分配数据后编辑工作分配时间分段的实际值。 
  
- 设置或更改工作分配分布类型（如常规分布、前轻后重或后重前轻）。
    
#### <a name="baselines-and-earned-value"></a>比较基准和挣值

- 保存比较基准或编辑比较基准数据。 
    
- 设置进度设定日期。
    
- 计算差异和挣值。 
    
#### <a name="interactive-scheduling"></a>交互日程排定

- 支持交互日程排定。（由于 Project Server 以异步方式处理交互，因此交互日程排定应通过 Project Professional 完成。）
    
    > [!NOTE]
    > 若要避免更改编程行为，从 Project Server 2010 进入会被转接的 PSI 方法操作 Project Server 2013 中的相同方式。 例如， [QueueUpdateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject.aspx)仍具有相同的限制，并使用较旧的服务器端计划引擎。 新的[QueueUpdateProject2](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject2.aspx)方法删除这些限制的许多，并使用新 Project Server 2013 服务器端计划引擎，这是 Project Professional 2013 中的相同计划引擎。 
  
#### <a name="wbs"></a>WBS

- 定义工作分解结构 (WBS) 代码掩码。 
    
#### <a name="tasks"></a>任务

- 更改任务类型（固定工时、工期或单位）。
    
- 更改任务是否为投入比导向。
    
- 更改任务固定成本累算。
    
- 更改[TASK_NOTES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_NOTES.aspx)字段的内容。 PSI 可读取任务备注，它们是.rtf 二进制数据的文本部分。 但是，您可以编辑工作分配备注 ( [ASSN_NOTES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.AssignmentRow.ASSN_NOTES.aspx) )，这些文本数据。 报告数据库中不包含任务或工作分配备注。 
    
- 创建或编辑周期性任务。
    
- 分配或更改现有任务的任务日历。
    
- 使用任务日历创建新任务。
    
- 更改[TASK_IGNORES_RES_CAL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_IGNORES_RES_CAL.aspx)字段的值 （任务忽略资源日历）。 
    
- 如果在同一呼叫进行其他更改，请使用[QueueUpdateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject.aspx) ，更改活动任务的状态。 有关详细信息，请参阅[Project Server 可编程性 （英文）](project-server-programmability.md)中的*服务器上的项目计划*部分。
    
#### <a name="summary-tasks"></a>摘要任务

- 创建或更改摘要任务的工作分配。
    
    > [!NOTE]
    > 我们建议您不要使用 Project Professional 或其他任何方式的摘要任务进行工作分配。 有关详细信息，请参阅[Project Server 可编程性 （英文）](project-server-programmability.md)中的*服务器上的项目计划*部分。 
  
- 编辑通常从子任务汇总的摘要任务域。服务器端项目始终汇总摘要信息，而不是设置摘要任务的信息并将其向下推送到子任务。您可以仅编辑摘要任务的以下域：
    
  - 任务相关性
    
  - 非公式自定义域
    
  - [TASK_NAME](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_NAME.aspx)
    
  - [TASK_OUTLINE_LEVEL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_OUTLINE_LEVEL.aspx)
    
  - [TASK_IS_MARKED](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_IS_MARKED.aspx)
    
  - [TASK_CONSTRAINT_TYPE](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_CONSTRAINT_TYPE.aspx)
    
  - [TASK_CONSTRAINT_DATE](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_CONSTRAINT_DATE.aspx)
    
  - [TASK_PRIORITY](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_PRIORITY.aspx)
    
  - [TASK_DEADLINE](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_DEADLINE.aspx)
    
  - [TASK_FIXED_COST](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_FIXED_COST.aspx)
    
  - [TASK_FIXED_COST_ACCRUAL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_FIXED_COST_ACCRUAL.aspx)（仅在创建任务时设置值） 
    
  - [TASK_WBS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_WBS.aspx)
    
对于项目摘要任务，PSI 限制与 Project Professional 的限制相同。PSI 可编辑预算分配，包括成本预算。
  
#### <a name="project-level-calculation-options"></a>项目级计算选项

- 更改从开始时间向后排定日程 (SFS) 和从完成时间前推逆向安排日程 (SFF) 之间的项目类型。（PSI 可将项目创建为 SFS 或 SFF，但一旦创建项目，只能在 Project Professional 中更改项目。）
    
- 在项目创建之后更改项目基准日历 ([CAL_UID](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.CAL_UID.aspx) )。 
    
- 更改计算选项。在创建项目时，可以使用 PSI 设置以下计算选项，但更改这些选项需要使用 Project Professional。（在 Backstage 视图中，选择“选项”****，然后在“项目选项”**** 对话框中选择“日程安排”**** 选项卡。） 
    
  - [PROJ_OPT_CALC_ACT_COSTS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_CALC_ACT_COSTS.aspx)
    
  - [PROJ_OPT_CRITICAL_SLACK_LIMIT](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_CRITICAL_SLACK_LIMIT.aspx)
    
  - [PROJ_OPT_HONOR_CONSTRAINTS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_HONOR_CONSTRAINTS.aspx)
    
  - [PROJ_OPT_MOVE_ACTUAL_IF_LATER](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MOVE_ACTUAL_IF_LATER.aspx)
    
  - [PROJ_OPT_MOVE_ACTUAL_TO_STATUS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MOVE_ACTUAL_TO_STATUS.aspx)
    
  - [PROJ_OPT_MOVE_REMAINING_IF_EARLIER](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MOVE_REMAINING_IF_EARLIER.aspx)
    
  - [PROJ_OPT_MOVE_REMAINING_TO_STATUS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MOVE_REMAINING_TO_STATUS.aspx)
    
  - [PROJ_OPT_MULT_CRITICAL_PATHS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MULT_CRITICAL_PATHS.aspx)
    
  - [PROJ_OPT_SPLIT_IN_PROGRESS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_SPLIT_IN_PROGRESS.aspx)
    
  - [PROJ_OPT_SPREAD_ACT_COSTS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_SPREAD_ACT_COSTS.aspx)
    
  - [PROJ_OPT_SPREAD_PCT_COMP](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_SPREAD_PCT_COMP.aspx)
    
  - [PROJ_OPT_TASK_UPDATES_RES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_TASK_UPDATES_RES.aspx)
    
## <a name="see-also"></a>另请参阅

- [CSOM 执行和不执行的操作](what-the-csom-does-and-does-not-do.md)  
- [Project Server 可编程性](project-server-programmability.md)   
- [使用基于声明的身份验证的 SharePoint Online 中的远程身份验证](https://msdn.microsoft.com/library/49067f7a-3020-478f-ba97-4b7ce3ea9b87%28Office.15%29.aspx)  
- [Office 外接程序](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) 
    

