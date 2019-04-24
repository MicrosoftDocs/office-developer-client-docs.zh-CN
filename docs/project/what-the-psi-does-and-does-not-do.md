---
title: PSI 可实现的操作和不可实现的操作
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: eac6be6a-9a20-4bc0-8da2-b2fd93aab04f
description: project server Interface (PSI) 可帮助您在 project server 2013 的本地安装中自动执行许多服务器端进程。 但是, 有几个函数需要使用 Microsoft Project Professional 2013。
ms.openlocfilehash: b93c3535ca6693a84d11370de17bc18375f168ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346527"
---
# <a name="what-the-psi-does-and-does-not-do"></a>PSI 执行和不执行的操作

project server Interface (PSI) 可帮助您在 project server 2013 的本地安装中自动执行许多服务器端进程。 但是, 有几个函数需要使用 Microsoft Project Professional 2013。
  
|||
|:-----|:-----|
|||
   
PSI 旨在补充 project professional 2013 的功能, 而不是为所有 Project professional 函数提供基于服务器的替代项。 第三方开发人员可以使用 PSI 帮助为 project web App 和 project 工作区的本地安装创建 Web 部件, 创建与本地 project Server 数据交互的自定义 Windows 应用程序和 web 应用程序, 开发工作流项目组合管理的逻辑, 开发本地完全信任事件处理程序, 并将 project Server 与其他应用程序集成。 PSI 不能用于 Office 商店、移动设备或平板电脑的应用程序开发;为此, 可以使用客户端对象模型 (CSOM)。
  
> [!NOTE]
> PSI 为 Project Server 2013 提供了更为全面的编程接口, 而不是 CSOM 提供的接口。 但是，除非 CSOM 未提供您需要的功能，否则建议您使用 CSOM 来开发新的应用程序。 有关详细信息，请参阅 [What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md)。 
  
## <a name="usage-scenarios-for-the-psi"></a>PSI 的使用方案
<a name="pj14_WhatPSIDoes_UsageScenarios"> </a>

以下是 PSI 支持的针对服务器端项目和计算的一些应用的示例：
  
- **自动创建或管理 Project Server 中的实体**虽然 project Professional 2013 和 project Web App 共同设计的实体 (如项目、企业资源和自定义字段) 的管理和创建, 但在某些情况下, 自定义应用程序可以节省大量时间或重复作业。 对于某些类别的作业而言，PSI 可实现其自动化，而 CSOM 无法做到这一点，例如，OLAP 多维数据集、项目组合分析、业务驱动因素、通知、对象链接提供程序、安全性和 SharePoint 互操作性。 
    
- **在项目数据库的 "已发布" 或 "存档" 表中获取数据**由于不支持对 "草稿"、"已发布" 和 "存档" 表的直接数据库访问, 因此您可以使用 PSI 读取报告表或视图中不可用的数据。 例如, 获取有关存储在存档表中的项目版本、日期和更改的信息, 然后使用该信息填充 web 部件中的 JS 网格控件。 
    
- **验证 statusing 和时间表数据**在本地前期事件处理程序中使用 PSI 来验证用户输入的工作分配状态或时间表数据, 然后再将数据保存在 Project Web App 中。 
    
- **维护项目**创建要与资源计划一起使用的占位符项目。 针对维护工作或基础业务的资源保留或预定时间。 通常，维护项目没有任务。 
    
- **创建财务项目**针对时间表中的时间捕获创建项目，以便与财务系统集成。 创建财务制度的层次结构，以反映财务系统的成本细分结构。 财务项目无需进行计划或状态更新。 
    
- **与会计系统集成**捕获与项目关联的资源成本和支出，为财务和计费系统提供数据源，以用于预算对比。 在系统之间同步任务、资源和工作分配。 捕获一个系统中的时间表数据以提供给另一个系统（使用哪种时间表取决于组织和各个项目的需要）。 
    
- **自动处理来自团队成员的更新**对于非主动管理的项目，可使用来自项目团队成员的进度和其他更改自动更新服务器上的项目。 项目经理无需查看结果或调整计划项目就可以更新和重新发布项目。 
    
- **评估本地完全信任事件处理程序中的 Project Server 数据****ProjectCreating**预事件的本地事件处理程序可以使用来自 PSI 的 Project Server 数据, 以帮助确定是否取消事件。 例如，在创建项目之前，将项目建议与现有项目进行比较。 
    
- **为需求管理创建自定义工作流活动**使用本地的完全信任工作流活动中的 PSI, 以根据企业项目模板修改和更新项目建议。 可通过项目自定义域使用启动和审核过程所需的信息标记项目。 添加任务以标识关键里程碑或可交付结果的项目阶段。 在项目建议得到批准后，工作流可将建议变成通过 Project Professional 管理的全面项目。 
    
- **创建 PSI 扩展**(已**弃用。** 扩展在 Project Server 2013 中已弃用, 在将来的版本中不受支持。通过使用 Windows Communication Foundation (WCF) 接口, 可以使用自定义服务扩展 PSI。 PSI 扩展在 Project Server 计算机上运行，并且此扩展可使用与内置 PSI 服务相同的安全基础结构。 扩展可查询报告表、使用单独的数据库表、整合 PSI 调用以节省带宽以及与第三方应用程序和其他服务器端组件集成。 有关详细信息，请参阅[开发 PSI 扩展](https://msdn.microsoft.com/library/1b484623-94fb-47c9-84c1-3e68a9133042%28Office.15%29.aspx)。
    
- **在本地和完全信任的应用程序中使用模拟**可以模拟对 PSI 的 WCF 接口的调用, 以便应用程序假设模拟用户的安全权限。 使用模拟时应小心谨慎。 读取和更新其他用户的状态信息不需要模拟。 需要模拟的新应用程序应使用 CSOM 和 OAuth 协议而不是 PSI。 有关与 PSI 的模拟的详细信息, 请参阅[Use 模拟 with WCF](https://msdn.microsoft.com/library/e3597901-2f02-44a2-8076-d32aae540b38%28Office.15%29.aspx)。
    
> [!NOTE]
> 在某些情况下, 可以在 CSOM 和 Project Online 的客户端应用程序中使用 PSI。 如果使用基于用户的 PSI web 服务, 则应用程序必须包含用于对 CSOM 中的 ProjectContext 对象进行身份验证的方法, 以及用于对[microsoft.projectserver.client](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx)进行身份验证**的方法。SoapHttpClientProtocol**客户端对象的网站。 有关将 Web 服务与 SharePoint CSOM 一起使用的示例，请参阅[使用基于声明的身份验证的 SharePoint Online 中的远程身份验证](https://msdn.microsoft.com/library/49067f7a-3020-478f-ba97-4b7ce3ea9b87%28Office.15%29.aspx)。 > 由于受约束的应用程序级别权限而无法在为公共 Office 商店中的分发而设计的应用程序中使用 PSI。 在此情况下，只能使用 CSOM。 
  
## <a name="what-the-psi-does-not-do"></a>PSI 不可实现的操作
<a name="pj14_WhatPSIDoes_DoesNotDo"> </a>

虽然 PSI 可实现的操作有很多，但也有一些操作是 PSI 不可实现的。以下是 PSI 不可实现的两项操作，但 CSOM 可实现这两项操作。
  
### <a name="project-online-and-remote-event-receivers"></a>Project Online 和远程事件接收器

PSI 的主要限制是 Project Online。 使用 PSI 应用程序需要对 Project Server 的本地安装的完全信任访问权。 例如, 不能在远程事件接收器中使用 PSI, 其中, 在 Microsoft Azure 上将事件接收器安装为一项服务。
  
### <a name="workflows-and-claims-authentication"></a>工作流和声明身份验证

使用 Windows workflow Foundation 版本 4 (WF4) 的工作流定义需要声明身份验证, 而 PSI 不直接支持声明身份验证。 这意味着您不能使用 PSI 在包含企业项目类型 (EPT) 和 WF4 工作流定义的 project Server 2013 中创建项目。
  
可以使用 PSI 创建具有 ept 的项目, 这些项目没有工作流或使用旧版 wf 3.5 定义 (Project Server 2010 中的工作流版本)。 若要创建包含具有 WF4 定义的 EPT 的项目，请使用 CSOM。
  
 **需要 Project Professional 的操作：**
  
下面列出了 PSI 和 CSOM 都不可实现的操作。
  
#### <a name="local-data"></a>本地数据

- 操作本地项目（.mpp 文件）中的数据。例如，定义成本费率表或本地资源的可用性分布。 
    
- 定义或编辑本地基准日历或资源日历，包括日历例外。
    
- 定义本地自定义域。（PSI 支持编辑针对任务、资源和工作分配的本地自定义域值。）
    
#### <a name="enterprise-data"></a>企业数据

- 签出或编辑企业全局模板。 project Server 2013 中的企业全局数据是项目数据库中的一组二进制数据表, 而不是 Office project Server 2007 和早期版本中的项目模板。
    
- 定义或编辑企业日历。 [日历](https://msdn.microsoft.com/library/WebSvcCalendar.Calendar.aspx)方法只管理日历例外。 
    
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
    
#### <a name="cost-resources"></a>Cost resources

- 使用[项目](https://msdn.microsoft.com/library/WebSvcProject.Project.aspx)方法编辑、创建或删除成本资源和工作分配。 [资源](https://msdn.microsoft.com/library/WebSvcResource.Resource.aspx)方法可以创建成本资源, 但不能对其进行编辑。 
    
#### <a name="work-contours"></a>工时分布

- 编辑按时间分段的数据。
    
    > [!NOTE]
    > 在项目经理更新和发布工作分配数据之后, **Statusing** Web 服务中的[UpdateStatus](https://msdn.microsoft.com/library/WebSvcStatusing.Statusing.UpdateStatus.aspx)方法可以编辑分配的按时间分段的实际值。 
  
- 设置或更改工作分配分布类型（如常规分布、前轻后重或后重前轻）。
    
#### <a name="baselines-and-earned-value"></a>比较基准和挣值

- 保存比较基准或编辑比较基准数据。 
    
- 设置进度设定日期。
    
- 计算差异和挣值。 
    
#### <a name="interactive-scheduling"></a>交互日程排定

- 支持交互日程排定。（由于 Project Server 以异步方式处理交互，因此交互日程排定应通过 Project Professional 完成。）
    
    > [!NOTE]
    > 若要避免更改编程行为, 从 project server 2010 转发的 PSI 方法在 project server 2013 中的行为方式相同。 例如, [QueueUpdateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject.aspx)仍具有相同的限制, 并使用较旧的服务器端日程安排引擎。 新的[QueueUpdateProject2](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject2.aspx)方法将删除许多这些限制, 并使用新的 project server 2013 服务器端日程安排引擎, 这是 Project Professional 2013 中的相同日程安排引擎。 
  
#### <a name="wbs"></a>WBS

- 定义工作分解结构 (WBS) 代码掩码。 
    
#### <a name="tasks"></a>任务

- 更改任务类型（固定工时、工期或单位）。
    
- 更改任务是否为投入比导向。
    
- 更改任务固定成本累算。
    
- 更改 " [TASK_NOTES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_NOTES.aspx) " 字段的内容。 PSI 只能读取任务备注的文本部分，它们是一些 .rtf 二进制数据。 不过, 您可以编辑工作分配备注 ( [ASSN_NOTES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.AssignmentRow.ASSN_NOTES.aspx) ), 这是文本数据。 报告数据库不包括任务或工作分配备注。 
    
- 创建或编辑周期性任务。
    
- 分配或更改现有任务的任务日历。
    
- 使用任务日历创建新任务。
    
- 更改 " [TASK_IGNORES_RES_CAL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_IGNORES_RES_CAL.aspx) " 字段的值 ("任务" 忽略资源日历)。 
    
- 如果在同一调用中进行了其他更改, 则使用[QueueUpdateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject.aspx)更改任务的活动状态。 有关详细信息, 请参阅[project server 可编程性](project-server-programmability.md)中的 "*服务器上的项目计划*" 部分。
    
#### <a name="summary-tasks"></a>摘要任务

- 创建或更改摘要任务的工作分配。
    
    > [!NOTE]
    > 建议您不要使用 Project Professional 或任何其他方式为摘要任务创建工作分配。 有关详细信息, 请参阅[project server 可编程性](project-server-programmability.md)中的 "*服务器上的项目计划*" 部分。 
  
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
    
  - [TASK_FIXED_COST_ACCRUAL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_FIXED_COST_ACCRUAL.aspx)(仅在创建任务时设置值) 
    
  - [TASK_WBS](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_WBS.aspx)
    
对于项目摘要任务，PSI 限制与 Project Professional 的限制相同。 PSI 可编辑预算分配，包括成本预算。
  
#### <a name="project-level-calculation-options"></a>项目级计算选项

- 更改从开始时间向后排定日程 (SFS) 和从完成时间前推逆向安排日程 (SFF) 之间的项目类型。（PSI 可将项目创建为 SFS 或 SFF，但一旦创建项目，只能在 Project Professional 中更改项目。）
    
- 在创建项目后更改项目基准日历 ([CAL_UID](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.CAL_UID.aspx) )。 
    
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
- [Office 加载项](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) 
    

