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
# <a name="what-the-psi-does-and-does-not-do"></a><span data-ttu-id="1ca5b-104">PSI 执行和不执行的操作</span><span class="sxs-lookup"><span data-stu-id="1ca5b-104">What the PSI does and does not do</span></span>

<span data-ttu-id="1ca5b-105">Project Server 接口 (PSI) 可帮助自动在本地安装的 Project Server 2013 中的多个服务器端进程。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-105">The Project Server Interface (PSI) can help to automate many server-side processes in on-premises installations of Project Server 2013.</span></span> <span data-ttu-id="1ca5b-106">但是，多个函数需要使用 Microsoft Project Professional 2013。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-106">But, several functions require the use of Microsoft Project Professional 2013.</span></span>
  
|||
|:-----|:-----|
|||
   
<span data-ttu-id="1ca5b-107">PSI 专为补充 Project Professional 2013 的功能，而不是所有 Project Professional 功能都提供基于服务器的替代。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-107">The PSI is designed to complement the capabilities of Project Professional 2013, rather than provide a server-based alternative for all Project Professional functions.</span></span> <span data-ttu-id="1ca5b-108">第三方开发人员可以使用 PSI 可帮助您创建的 Project Web App 和项目工作区的本地安装的 Web 部件，请创建自定义 Windows 应用程序和 web 应用程序与内部部署 Project Server 数据进行交互，开发工作流项目组合管理的逻辑开发本地完全信任事件处理程序，并将 Project Server 与其他应用程序相集成。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-108">Third-party developers can use the PSI to help create Web Parts for on-premises installations of Project Web App and project workspaces, create custom Windows applications and web applications that interact with on-premises Project Server data, develop workflow logic for project portfolio management, develop local full-trust event handlers, and integrate Project Server with other applications.</span></span> <span data-ttu-id="1ca5b-109">PSI 不能用于开发的应用程序的 Office 商店、 移动设备或平板电脑;对于，您可以使用客户端对象模型 (CSOM)。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-109">The PSI cannot be used for development of apps for the Office Store, mobile devices, or tablets; for that, you can use the client-side object model (CSOM).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ca5b-110">PSI 提供更全面编程接口的 Project Server 2013 比 CSOM 提供。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-110">The PSI provides a more comprehensive programmatic interface for Project Server 2013 than the CSOM provides.</span></span> <span data-ttu-id="1ca5b-111">但是，除非 CSOM 未提供所需的功能，我们建议使用 CSOM 开发新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-111">But, unless the CSOM does not provide the functionality that you require, we recommend that you use the CSOM to develop new applications.</span></span> <span data-ttu-id="1ca5b-112">有关详细信息，请参阅[What the CSOM 执行和不可实现的操作](what-the-csom-does-and-does-not-do.md)。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-112">For more information, see [What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md).</span></span> 
  
## <a name="usage-scenarios-for-the-psi"></a><span data-ttu-id="1ca5b-113">PSI 的使用方案</span><span class="sxs-lookup"><span data-stu-id="1ca5b-113">Usage scenarios for the PSI</span></span>
<span data-ttu-id="1ca5b-114"><a name="pj14_WhatPSIDoes_UsageScenarios"> </a></span><span class="sxs-lookup"><span data-stu-id="1ca5b-114"></span></span>

<span data-ttu-id="1ca5b-115">以下是 PSI 支持的针对服务器端项目和计算的一些应用的示例：</span><span class="sxs-lookup"><span data-stu-id="1ca5b-115">Following are examples of some applications that the PSI supports for server-side projects and calculations:</span></span>
  
- <span data-ttu-id="1ca5b-116">**自动创建或管理的 Project Server 中的实体**虽然 Project Professional 2013 和 Project Web App 一起旨在处理管理和创建项目、 企业资源和自定义字段等实体，有通常情况下，自定义应用程序可以节省时间与批量或重复性的作业。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-116">**Automate the creation or management of entities in Project Server** Although Project Professional 2013 and Project Web App together are designed to handle management and creation of entities such as projects, enterprise resources, and custom fields, there are often cases where a custom application can save time with bulk or repetitive jobs.</span></span> <span data-ttu-id="1ca5b-117">PSI 可以自动执行几种 CSOM 不会执行的作业，例如，与 OLAP 多维数据集、 项目组合分析、 业务驱动因素、 通知、 对象链接提供程序、 安全性和 SharePoint 互操作性。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-117">The PSI can automate several kinds of jobs that the CSOM does not do, for example, with OLAP cubes, project portfolio analyses, business drivers, notifications, object link providers, security, and SharePoint interoperability.</span></span> 
    
- <span data-ttu-id="1ca5b-118">**获取或 Project 数据库的存档表中已发布的数据**因为直接数据库访问草稿、 发布，并将存档表不支持，您可以使用 PSI 读取在报表的表或视图中不可用的数据。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-118">**Get data in the published or archive tables of the Project database** Because direct database access to the draft, published, and archive tables is not supported, you can use the PSI to read data that is not available in the reporting tables or views.</span></span> <span data-ttu-id="1ca5b-119">例如，获取有关项目版本、 日期和存储在存档表中，更改的信息，然后填充具有信息的 web 部件中的 JS 网格控件。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-119">For example, get information about project versions, dates, and changes that are stored in the archive tables, and then populate a JS Grid control in a web part with the information.</span></span> 
    
- <span data-ttu-id="1ca5b-120">**验证状态和时间表数据**在本地前期事件处理程序中使用 PSI 验证用户输入之前的数据保存 Project Web App 中的工作分配状态或时间表数据。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-120">**Validate statusing and timesheet data** Use the PSI in local pre-event handlers to validate assignment status or timesheet data that users enter, before the data is saved in Project Web App.</span></span> 
    
- <span data-ttu-id="1ca5b-121">**维护项目**创建占位符用于资源计划的项目。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-121">**Maintenance projects** Create placeholder projects to use with resource plans.</span></span> <span data-ttu-id="1ca5b-122">保留时间或簿时间对资源的维护工作或基本业务。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-122">Reserve or book time against resources for maintenance work or base business.</span></span> <span data-ttu-id="1ca5b-123">维护项目通常没有任务。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-123">Maintenance projects generally do not have tasks.</span></span> 
    
- <span data-ttu-id="1ca5b-124">**创建财务项目**创建与财务系统时间捕获到时间表以供集成的项目。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-124">**Create financial projects** Create projects for time capture through the timesheet for integration with a financial system.</span></span> <span data-ttu-id="1ca5b-125">创建层次结构，反映财务系统的成本细分结构的财务代码。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-125">Create a hierarchy of financial codes that reflect the cost breakdown structure of the financial system.</span></span> <span data-ttu-id="1ca5b-126">财务项目不需要日程安排或状态更新。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-126">Financial projects do not require scheduling or status updates.</span></span> 
    
- <span data-ttu-id="1ca5b-127">**与会计系统集成**捕获资源成本和开支关联与源财务和帐单系统的项目和预算比较目的。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-127">**Integrate with accounting systems** Capture the resource costs and expenses associated with projects to feed financial and billing systems and for budget comparison purposes.</span></span> <span data-ttu-id="1ca5b-128">同步任务、 资源和系统之间的工作分配。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-128">Synchronize tasks, resources, and assignments between the systems.</span></span> <span data-ttu-id="1ca5b-129">在源另一个系统中捕获时间表数据 （使用哪些时间表取决于或单个项目的组织的需要）。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-129">Capture timesheet data in one system to feed the other (which timesheet is used depends on the needs of the organization or of individual projects).</span></span> 
    
- <span data-ttu-id="1ca5b-130">**来自工作组成员的自动更新**对于未主动管理的项目，自动更新进度与其他更改来自项目团队成员服务器上的项目。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-130">**Automate updates from team members** For projects that are not actively managed, automatically update projects on the server with progress and other changes from project team members.</span></span> <span data-ttu-id="1ca5b-131">项目可以更新和重新发布没有项目经理审阅结果或进行调整计划。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-131">Projects can be updated and republished without a project manager reviewing the results or making adjustments to the plan.</span></span> 
    
- <span data-ttu-id="1ca5b-132">**完全信任的本地事件处理程序中的评估 Project Server 数据**本地事件处理程序**项目创建**前期事件可以使用 PSI 中的 Project Server 数据来帮助确定是否可取消事件。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-132">**Evaluate Project Server data in local full-trust event handlers** A local event handler for the **ProjectCreating** pre-event can use Project Server data from the PSI to help determine whether to cancel an event.</span></span> <span data-ttu-id="1ca5b-133">例如之前创建的项目，比较项目建议与现有项目。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-133">For example, before creating a project, compare the project proposal with existing projects.</span></span> 
    
- <span data-ttu-id="1ca5b-134">**需求管理创建自定义工作流活动**在本地、 完全信任工作流活动中使用 PSI 修改和更新项目建议根据企业项目模板。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-134">**Create custom workflow activities for demand management** Use the PSI in local, full-trust workflow activities to modify and update project proposals based on enterprise project templates.</span></span> <span data-ttu-id="1ca5b-135">使用项目自定义域标记项目所需的初始和批准过程的信息。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-135">Use project custom fields to tag the project with information needed for the initiation and approval process.</span></span> <span data-ttu-id="1ca5b-136">添加任务，以确定关键里程碑或可交付结果的项目阶段。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-136">Add tasks to identify project phases for key milestones or deliverables.</span></span> <span data-ttu-id="1ca5b-137">当批准项目建议时，工作流可以更改到与 Project Professional 全面项目管理的建议。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-137">When project proposals are approved, a workflow can change the proposals into full-scale projects that are managed with Project Professional.</span></span> 
    
- <span data-ttu-id="1ca5b-138">**创建 PSI 扩展**(**弃用。**</span><span class="sxs-lookup"><span data-stu-id="1ca5b-138">**Create PSI extensions** (**Deprecated.**</span></span> <span data-ttu-id="1ca5b-139">扩展 Project Server 2013 中弃用和将来版本中将不支持）使用 Windows Communication Foundation (WCF) 接口，可使用自定义服务的扩展 PSI。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-139">Extensions are deprecated in Project Server 2013, and will not be supported in future releases.) The PSI can be extended with custom services by using the Windows Communication Foundation (WCF) interface.</span></span> <span data-ttu-id="1ca5b-140">PSI 扩展的 Project Server 计算机上，运行，并且可以使用内置的 PSI 服务使用的同一安全基础结构。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-140">PSI extensions run on the Project Server computer, and can use the same security infrastructure that the built-in PSI services use.</span></span> <span data-ttu-id="1ca5b-141">扩展可以查询报告表、 使用单独的数据库表，将其整合到保存带宽，并将与第三方应用程序和其他服务器端组件集成的 PSI 调用。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-141">Extensions can query the reporting tables, use separate database tables, consolidate PSI calls to save bandwidth, and integrate with third-party applications and other server-side components.</span></span> <span data-ttu-id="1ca5b-142">有关详细信息，请参阅[开发 PSI 扩展](https://msdn.microsoft.com/library/1b484623-94fb-47c9-84c1-3e68a9133042%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-142">For more information, see [Developing PSI Extensions](https://msdn.microsoft.com/library/1b484623-94fb-47c9-84c1-3e68a9133042%28Office.15%29.aspx).</span></span>
    
- <span data-ttu-id="1ca5b-143">**在本地、 完全信任的应用程序中使用模拟**可以模拟 PSI 的 WCF 接口的呼叫，以便应用程序假定模拟用户的安全权限。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-143">**Use impersonation in local, full-trust applications** Calls to the WCF interface of the PSI can be impersonated, so that an application assumes the security permissions of the impersonated user.</span></span> <span data-ttu-id="1ca5b-144">慎用和仔细，应使用模拟。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-144">Impersonation should be used sparingly and carefully.</span></span> <span data-ttu-id="1ca5b-145">读取和更新为其他用户的状态信息不需要模拟。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-145">Reading and updating status information for other users does not require impersonation.</span></span> <span data-ttu-id="1ca5b-146">新的应用程序需要模拟应该使用 CSOM 和 OAuth 协议，而非 PSI。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-146">New applications that require impersonation should use the CSOM and the OAuth protocol instead of the PSI.</span></span> <span data-ttu-id="1ca5b-147">有关使用 PSI 的模拟的详细信息，请参阅[使用模拟 with WCF](https://msdn.microsoft.com/library/e3597901-2f02-44a2-8076-d32aae540b38%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-147">For more information about impersonation with the PSI, see [Use Impersonation with WCF](https://msdn.microsoft.com/library/e3597901-2f02-44a2-8076-d32aae540b38%28Office.15%29.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ca5b-148">在某些情况下，可以使用 CSOM 和 Project Online 的客户端应用程序中使用 PSI。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-148">In some cases, the PSI can be used in client applications with the CSOM and Project Online.</span></span> <span data-ttu-id="1ca5b-149">如果您使用基于 ASMX 的 PSI web 服务，应用程序必须包括进行身份验证中 CSOM 的[Microsoft.ProjectServer.Client.ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx)对象的方法以及身份验证**方法System.Web.Services.Protocols.SoapHttpClientProtocol**客户端对象。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-149">If you use an ASMX-based PSI web service, the application must include a method to authenticate the [Microsoft.ProjectServer.Client.ProjectContext](https://msdn.microsoft.com/library/Microsoft.ProjectServer.Client.ProjectContext.aspx) object in the CSOM and a method to authenticate the **System.Web.Services.Protocols.SoapHttpClientProtocol** client object.</span></span> <span data-ttu-id="1ca5b-150">使用 SharePoint CSOM 与 web 服务的示例，请参阅[SharePoint Online Using Claims-Based 身份验证中的远程身份验证](https://msdn.microsoft.com/library/49067f7a-3020-478f-ba97-4b7ce3ea9b87%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-150">For an example that uses a web service with the SharePoint CSOM, see [Remote Authentication in SharePoint Online Using Claims-Based Authentication](https://msdn.microsoft.com/library/49067f7a-3020-478f-ba97-4b7ce3ea9b87%28Office.15%29.aspx).</span></span> <span data-ttu-id="1ca5b-151">> 由于的约束的应用程序级权限，PSI 不能用于设计的应用程序中公共 Office 商店中的通讯组。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-151">> Because of constrained app-level permissions, the PSI cannot be used in apps that are designed for distribution in the public Office Store.</span></span> <span data-ttu-id="1ca5b-152">在这种情况下，您可以使用仅 CSOM。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-152">In that case, you can use only the CSOM.</span></span> 
  
## <a name="what-the-psi-does-not-do"></a><span data-ttu-id="1ca5b-153">PSI 不可实现的操作</span><span class="sxs-lookup"><span data-stu-id="1ca5b-153">What the PSI does not do</span></span>
<span data-ttu-id="1ca5b-154"><a name="pj14_WhatPSIDoes_DoesNotDo"> </a></span><span class="sxs-lookup"><span data-stu-id="1ca5b-154"></span></span>

<span data-ttu-id="1ca5b-p116">虽然 PSI 可实现的操作有很多，但也有一些操作是 PSI 不可实现的。以下是 PSI 不可实现的两项操作，但 CSOM 可实现这两项操作。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p116">Although there are many things the PSI can do, there are some things the PSI does not do. Following are two things the PSI cannot do, but the CSOM can do.</span></span>
  
### <a name="project-online-and-remote-event-receivers"></a><span data-ttu-id="1ca5b-157">Project Online 和远程事件接收器</span><span class="sxs-lookup"><span data-stu-id="1ca5b-157">Project Online and remote event receivers</span></span>

<span data-ttu-id="1ca5b-158">使用 Project Online PSI 的主要限制。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-158">The primary limitation of the PSI is with Project Online.</span></span> <span data-ttu-id="1ca5b-159">使用 PSI 应用程序需要完全信任访问的 Project Server 的本地安装。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-159">Applications that use the PSI require full-trust access to an on-premises installation of Project Server.</span></span> <span data-ttu-id="1ca5b-160">例如，PSI 不能在中使用远程事件接收器事件接收器作为 Microsoft Azure 上的服务的安装。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-160">For example, the PSI cannot be used in remote event receivers, where the event receiver is installed as a service on Microsoft Azure.</span></span>
  
### <a name="workflows-and-claims-authentication"></a><span data-ttu-id="1ca5b-161">工作流和声明身份验证</span><span class="sxs-lookup"><span data-stu-id="1ca5b-161">Workflows and claims authentication</span></span>

<span data-ttu-id="1ca5b-162">工作流定义 that uses Windows Workflow Foundation 版本 4 (WF4) 需要 PSI 不直接支持的声明身份验证。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-162">A workflow definition that uses Windows Workflow Foundation version 4 (WF4) requires claims authentication, which the PSI does not directly support.</span></span> <span data-ttu-id="1ca5b-163">这意味着不能使用 PSI 具有企业项目类型 (EPT) 与 WF4 工作流定义的 Project Server 2013 中创建项目。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-163">This means you cannot use the PSI to create a project in Project Server 2013 that has an enterprise project type (EPT) with a WF4 workflow definition.</span></span>
  
<span data-ttu-id="1ca5b-164">PSI 可用于与已没有工作流或使用旧 WF3.5 定义 （Project Server 2010 中的工作流版本） 的 Ept 创建项目。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-164">You can use the PSI to create projects with EPTs that either have no workflow or use a legacy WF3.5 definition (the workflow version in Project Server 2010).</span></span> <span data-ttu-id="1ca5b-165">使用具有 WF4 定义 EPT 创建项目，请使用 CSOM。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-165">To create a project with an EPT that has a WF4 definition, use the CSOM.</span></span>
  
 <span data-ttu-id="1ca5b-166">**需要 Project Professional 的操作：**</span><span class="sxs-lookup"><span data-stu-id="1ca5b-166">**Actions that require Project Professional:**</span></span>
  
<span data-ttu-id="1ca5b-167">下面列出了 PSI 和 CSOM 都不可实现的操作。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-167">The following list are things that neither the PSI nor the CSOM can do.</span></span>
  
#### <a name="local-data"></a><span data-ttu-id="1ca5b-168">本地数据</span><span class="sxs-lookup"><span data-stu-id="1ca5b-168">Local data</span></span>

- <span data-ttu-id="1ca5b-p120">操作本地项目（.mpp 文件）中的数据。例如，定义成本费率表或本地资源的可用性分布。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p120">Manipulating data in local projects (.mpp files). For example, defining cost rate tables or availability contours for local resources.</span></span> 
    
- <span data-ttu-id="1ca5b-171">定义或编辑本地基准日历或资源日历，包括日历例外。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-171">Defining or editing local base calendars or resource calendars, including calendar exceptions.</span></span>
    
- <span data-ttu-id="1ca5b-p121">定义本地自定义域。（PSI 支持编辑针对任务、资源和工作分配的本地自定义域值。）</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p121">Defining local custom fields. (The PSI does support editing local custom field values on tasks, resources, and assignments.)</span></span>
    
#### <a name="enterprise-data"></a><span data-ttu-id="1ca5b-174">企业数据</span><span class="sxs-lookup"><span data-stu-id="1ca5b-174">Enterprise data</span></span>

- <span data-ttu-id="1ca5b-175">签出或编辑企业全局模板。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-175">Checking out or editing the enterprise global template.</span></span> <span data-ttu-id="1ca5b-176">Project Server 2013 中的企业全局数据是一套在 Project 数据库，而非 Office Project Server 2007 和早期版本的项目模板中的二进制模拟运算表。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-176">The enterprise global data in Project Server 2013 is a set of binary data tables in the Project database, not a project template as in Office Project Server 2007 and earlier versions.</span></span>
    
- <span data-ttu-id="1ca5b-177">定义或编辑企业日历。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-177">Defining or editing enterprise calendars.</span></span> <span data-ttu-id="1ca5b-178">[日历](https://msdn.microsoft.com/library/WebSvcCalendar.Calendar.aspx)方法管理仅日历例外。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-178">The [Calendar](https://msdn.microsoft.com/library/WebSvcCalendar.Calendar.aspx) methods manage only calendar exceptions.</span></span> 
    
#### <a name="master-projects-and-cross-project-links"></a><span data-ttu-id="1ca5b-179">主项目和跨项目链接</span><span class="sxs-lookup"><span data-stu-id="1ca5b-179">Master projects and cross-project links</span></span>

- <span data-ttu-id="1ca5b-180">创建主项目并插入子项目。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-180">Creating master projects and inserting subprojects.</span></span>
    
- <span data-ttu-id="1ca5b-181">计划跨主项目的关键路径。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-181">Scheduling a critical path across a master project.</span></span> 
    
- <span data-ttu-id="1ca5b-182">创建跨项目链接。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-182">Creating cross-project links.</span></span>
    
#### <a name="resources"></a><span data-ttu-id="1ca5b-183">资源</span><span class="sxs-lookup"><span data-stu-id="1ca5b-183">Resources</span></span>

- <span data-ttu-id="1ca5b-184">请求或执行资源调配。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-184">Requesting or performing resource leveling.</span></span>
    
- <span data-ttu-id="1ca5b-p124">更改工作分配的资源。（您可以使用 PSI 删除工作分配和创建新的工作分配。）</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p124">Changing the resource on an assignment. (You can use the PSI to delete the assignment and create a new one.)</span></span>
    
- <span data-ttu-id="1ca5b-187">删除或替换具有已接受实际工时的资源（实际值）。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-187">Deleting or replacing a resource that has actual work accepted (actuals).</span></span>
    
- <span data-ttu-id="1ca5b-188">更改工时、材料或成本之间的资源类型。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-188">Changing a resource type between work, material, and cost.</span></span>
    
- <span data-ttu-id="1ca5b-189">创建或编辑资源日历。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-189">Creating or editing resource calendars.</span></span>
    
- <span data-ttu-id="1ca5b-p125">在向任务中添加资源时，PSI 不会按照 Project Professional 所采用的方式自动重新分发工时。这取决于开发人员选择和显式设置工作分配的工时分发。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p125">When adding a resource to a task, the PSI does not automatically redistribute work the way Project Professional does. It is up to the developer to choose and explicitly set the work distribution on the assignments.</span></span>
    
#### <a name="cost-resources"></a><span data-ttu-id="1ca5b-192">成本资源</span><span class="sxs-lookup"><span data-stu-id="1ca5b-192">Cost resources</span></span>

- <span data-ttu-id="1ca5b-193">编辑、 创建或删除成本资源和工作分配使用[项目](https://msdn.microsoft.com/library/WebSvcProject.Project.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-193">Editing, creating, or deleting cost resources and assignments using the [Project](https://msdn.microsoft.com/library/WebSvcProject.Project.aspx) methods.</span></span> <span data-ttu-id="1ca5b-194">[资源](https://msdn.microsoft.com/library/WebSvcResource.Resource.aspx)方法可以创建成本资源，但不能编辑它们。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-194">The [Resource](https://msdn.microsoft.com/library/WebSvcResource.Resource.aspx) methods can create cost resources but cannot edit them.</span></span> 
    
#### <a name="work-contours"></a><span data-ttu-id="1ca5b-195">工时分布</span><span class="sxs-lookup"><span data-stu-id="1ca5b-195">Work contours</span></span>

- <span data-ttu-id="1ca5b-196">编辑按时间分段的数据。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-196">Editing timephased data.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ca5b-197">**Statusing** Web 服务中的[UpdateStatus](https://msdn.microsoft.com/library/WebSvcStatusing.Statusing.UpdateStatus.aspx)方法可以项目经理更新和发布工作分配数据后编辑工作分配时间分段的实际值。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-197">The [UpdateStatus](https://msdn.microsoft.com/library/WebSvcStatusing.Statusing.UpdateStatus.aspx) method in the **Statusing** Web service can edit timephased actuals on assignments after the project manager updates and publishes the assignment data.</span></span> 
  
- <span data-ttu-id="1ca5b-198">设置或更改工作分配分布类型（如常规分布、前轻后重或后重前轻）。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-198">Setting or changing the assignment contour type (such as flat, back-loaded, or front-loaded).</span></span>
    
#### <a name="baselines-and-earned-value"></a><span data-ttu-id="1ca5b-199">比较基准和挣值</span><span class="sxs-lookup"><span data-stu-id="1ca5b-199">Baselines and earned value</span></span>

- <span data-ttu-id="1ca5b-200">保存比较基准或编辑比较基准数据。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-200">Saving a baseline or editing baseline data.</span></span> 
    
- <span data-ttu-id="1ca5b-201">设置进度设定日期。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-201">Setting a progress date.</span></span>
    
- <span data-ttu-id="1ca5b-202">计算差异和挣值。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-202">Calculating variance and earned value.</span></span> 
    
#### <a name="interactive-scheduling"></a><span data-ttu-id="1ca5b-203">交互日程排定</span><span class="sxs-lookup"><span data-stu-id="1ca5b-203">Interactive scheduling</span></span>

- <span data-ttu-id="1ca5b-p127">支持交互日程排定。（由于 Project Server 以异步方式处理交互，因此交互日程排定应通过 Project Professional 完成。）</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p127">Supporting interactive scheduling. (Because Project Server handles interactions asynchronously, interactive scheduling should be done with Project Professional.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ca5b-206">若要避免更改编程行为，从 Project Server 2010 进入会被转接的 PSI 方法操作 Project Server 2013 中的相同方式。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-206">To avoid changing programmatic behavior, the PSI methods that are brought forward from Project Server 2010 act the same way in Project Server 2013.</span></span> <span data-ttu-id="1ca5b-207">例如， [QueueUpdateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject.aspx)仍具有相同的限制，并使用较旧的服务器端计划引擎。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-207">For example, [QueueUpdateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject.aspx) still has the same limitations and uses the older server-side scheduling engine.</span></span> <span data-ttu-id="1ca5b-208">新的[QueueUpdateProject2](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject2.aspx)方法删除这些限制的许多，并使用新 Project Server 2013 服务器端计划引擎，这是 Project Professional 2013 中的相同计划引擎。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-208">The new [QueueUpdateProject2](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject2.aspx) method removes many of those limitations and uses the new Project Server 2013 server-side scheduling engine, which is the same scheduling engine that is in Project Professional 2013.</span></span> 
  
#### <a name="wbs"></a><span data-ttu-id="1ca5b-209">WBS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-209">WBS</span></span>

- <span data-ttu-id="1ca5b-210">定义工作分解结构 (WBS) 代码掩码。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-210">Defining a work breakdown structure (WBS) code mask.</span></span> 
    
#### <a name="tasks"></a><span data-ttu-id="1ca5b-211">任务</span><span class="sxs-lookup"><span data-stu-id="1ca5b-211">Tasks</span></span>

- <span data-ttu-id="1ca5b-212">更改任务类型（固定工时、工期或单位）。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-212">Changing the task type (fixed work, duration, or units).</span></span>
    
- <span data-ttu-id="1ca5b-213">更改任务是否为投入比导向。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-213">Changing whether a task is effort-driven.</span></span>
    
- <span data-ttu-id="1ca5b-214">更改任务固定成本累算。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-214">Changing task fixed-cost accrual.</span></span>
    
- <span data-ttu-id="1ca5b-215">更改[TASK_NOTES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_NOTES.aspx)字段的内容。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-215">Changing the content of the [TASK_NOTES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_NOTES.aspx) field.</span></span> <span data-ttu-id="1ca5b-216">PSI 可读取任务备注，它们是.rtf 二进制数据的文本部分。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-216">The PSI can read only the text part of the task notes, which are .rtf binary data.</span></span> <span data-ttu-id="1ca5b-217">但是，您可以编辑工作分配备注 ( [ASSN_NOTES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.AssignmentRow.ASSN_NOTES.aspx) )，这些文本数据。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-217">But, you can edit assignment notes ( [ASSN_NOTES](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.AssignmentRow.ASSN_NOTES.aspx) ), which are text data.</span></span> <span data-ttu-id="1ca5b-218">报告数据库中不包含任务或工作分配备注。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-218">The Reporting database does not include task or assignment notes.</span></span> 
    
- <span data-ttu-id="1ca5b-219">创建或编辑周期性任务。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-219">Creating or editing recurring tasks.</span></span>
    
- <span data-ttu-id="1ca5b-220">分配或更改现有任务的任务日历。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-220">Assigning or changing the task calendar on existing tasks.</span></span>
    
- <span data-ttu-id="1ca5b-221">使用任务日历创建新任务。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-221">Creating a new task with a task calendar.</span></span>
    
- <span data-ttu-id="1ca5b-222">更改[TASK_IGNORES_RES_CAL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_IGNORES_RES_CAL.aspx)字段的值 （任务忽略资源日历）。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-222">Changing the value of the [TASK_IGNORES_RES_CAL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_IGNORES_RES_CAL.aspx) field (task ignores resource calendar).</span></span> 
    
- <span data-ttu-id="1ca5b-223">如果在同一呼叫进行其他更改，请使用[QueueUpdateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject.aspx) ，更改活动任务的状态。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-223">Changing the active status of a task by using [QueueUpdateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueUpdateProject.aspx) , if additional changes are made in the same call.</span></span> <span data-ttu-id="1ca5b-224">有关详细信息，请参阅[Project Server 可编程性 （英文）](project-server-programmability.md)中的*服务器上的项目计划*部分。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-224">For more information, see the  *Project Scheduling on the Server*  section in [Project Server programmability](project-server-programmability.md).</span></span>
    
#### <a name="summary-tasks"></a><span data-ttu-id="1ca5b-225">摘要任务</span><span class="sxs-lookup"><span data-stu-id="1ca5b-225">Summary tasks</span></span>

- <span data-ttu-id="1ca5b-226">创建或更改摘要任务的工作分配。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-226">Creating or changing assignments on summary tasks.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ca5b-227">我们建议您不要使用 Project Professional 或其他任何方式的摘要任务进行工作分配。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-227">We recommend that you do not make assignments on summary tasks using Project Professional or any other way.</span></span> <span data-ttu-id="1ca5b-228">有关详细信息，请参阅[Project Server 可编程性 （英文）](project-server-programmability.md)中的*服务器上的项目计划*部分。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-228">For more information, see the  *Project Scheduling on the Server*  section in [Project Server programmability](project-server-programmability.md).</span></span> 
  
- <span data-ttu-id="1ca5b-p132">编辑通常从子任务汇总的摘要任务域。服务器端项目始终汇总摘要信息，而不是设置摘要任务的信息并将其向下推送到子任务。您可以仅编辑摘要任务的以下域：</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p132">Editing summary task fields that are normally rolled up from the subtask. Server-side projects always roll up summary information, instead of setting information on the summary task and pushing it down to the subtasks. You can edit only the following fields on summary tasks:</span></span>
    
  - <span data-ttu-id="1ca5b-232">任务相关性</span><span class="sxs-lookup"><span data-stu-id="1ca5b-232">Task dependencies</span></span>
    
  - <span data-ttu-id="1ca5b-233">非公式自定义域</span><span class="sxs-lookup"><span data-stu-id="1ca5b-233">Non-formula custom fields</span></span>
    
  - [<span data-ttu-id="1ca5b-234">TASK_NAME</span><span class="sxs-lookup"><span data-stu-id="1ca5b-234">TASK_NAME</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_NAME.aspx)
    
  - [<span data-ttu-id="1ca5b-235">TASK_OUTLINE_LEVEL</span><span class="sxs-lookup"><span data-stu-id="1ca5b-235">TASK_OUTLINE_LEVEL</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_OUTLINE_LEVEL.aspx)
    
  - [<span data-ttu-id="1ca5b-236">TASK_IS_MARKED</span><span class="sxs-lookup"><span data-stu-id="1ca5b-236">TASK_IS_MARKED</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_IS_MARKED.aspx)
    
  - [<span data-ttu-id="1ca5b-237">TASK_CONSTRAINT_TYPE</span><span class="sxs-lookup"><span data-stu-id="1ca5b-237">TASK_CONSTRAINT_TYPE</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_CONSTRAINT_TYPE.aspx)
    
  - [<span data-ttu-id="1ca5b-238">TASK_CONSTRAINT_DATE</span><span class="sxs-lookup"><span data-stu-id="1ca5b-238">TASK_CONSTRAINT_DATE</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_CONSTRAINT_DATE.aspx)
    
  - [<span data-ttu-id="1ca5b-239">TASK_PRIORITY</span><span class="sxs-lookup"><span data-stu-id="1ca5b-239">TASK_PRIORITY</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_PRIORITY.aspx)
    
  - [<span data-ttu-id="1ca5b-240">TASK_DEADLINE</span><span class="sxs-lookup"><span data-stu-id="1ca5b-240">TASK_DEADLINE</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_DEADLINE.aspx)
    
  - [<span data-ttu-id="1ca5b-241">TASK_FIXED_COST</span><span class="sxs-lookup"><span data-stu-id="1ca5b-241">TASK_FIXED_COST</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_FIXED_COST.aspx)
    
  - <span data-ttu-id="1ca5b-242">[TASK_FIXED_COST_ACCRUAL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_FIXED_COST_ACCRUAL.aspx)（仅在创建任务时设置值）</span><span class="sxs-lookup"><span data-stu-id="1ca5b-242">[TASK_FIXED_COST_ACCRUAL](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_FIXED_COST_ACCRUAL.aspx) (set the value only when creating the task)</span></span> 
    
  - [<span data-ttu-id="1ca5b-243">TASK_WBS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-243">TASK_WBS</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.TaskRow.TASK_WBS.aspx)
    
<span data-ttu-id="1ca5b-p133">对于项目摘要任务，PSI 限制与 Project Professional 的限制相同。PSI 可编辑预算分配，包括成本预算。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p133">For the project summary task, the PSI limitations are the same as for Project Professional. The PSI can edit budget assignments—including cost budgets.</span></span>
  
#### <a name="project-level-calculation-options"></a><span data-ttu-id="1ca5b-246">项目级计算选项</span><span class="sxs-lookup"><span data-stu-id="1ca5b-246">Project-level calculation options</span></span>

- <span data-ttu-id="1ca5b-p134">更改从开始时间向后排定日程 (SFS) 和从完成时间前推逆向安排日程 (SFF) 之间的项目类型。（PSI 可将项目创建为 SFS 或 SFF，但一旦创建项目，只能在 Project Professional 中更改项目。）</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p134">Changing a project type between Schedule From Start (SFS) and Schedule From Finish (SFF). (The PSI can create a project as either SFS or SFF, but once created it can be changed only in Project Professional.)</span></span>
    
- <span data-ttu-id="1ca5b-249">在项目创建之后更改项目基准日历 ([CAL_UID](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.CAL_UID.aspx) )。</span><span class="sxs-lookup"><span data-stu-id="1ca5b-249">Changing the project base calendar ([CAL_UID](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.CAL_UID.aspx) ) after project creation.</span></span> 
    
- <span data-ttu-id="1ca5b-p135">更改计算选项。在创建项目时，可以使用 PSI 设置以下计算选项，但更改这些选项需要使用 Project Professional。（在 Backstage 视图中，选择“选项”\*\*\*\*，然后在“项目选项”\*\*\*\* 对话框中选择“日程安排”\*\*\*\* 选项卡。）</span><span class="sxs-lookup"><span data-stu-id="1ca5b-p135">Changing options for calculations. You can use the PSI to set the following calculation options when the project is created, but changing the options requires Project Professional. (In Backstage view, choose **Options**, and then choose the **Schedule** tab in the **Project Options** dialog box.)</span></span> 
    
  - [<span data-ttu-id="1ca5b-253">PROJ_OPT_CALC_ACT_COSTS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-253">PROJ_OPT_CALC_ACT_COSTS</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_CALC_ACT_COSTS.aspx)
    
  - [<span data-ttu-id="1ca5b-254">PROJ_OPT_CRITICAL_SLACK_LIMIT</span><span class="sxs-lookup"><span data-stu-id="1ca5b-254">PROJ_OPT_CRITICAL_SLACK_LIMIT</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_CRITICAL_SLACK_LIMIT.aspx)
    
  - [<span data-ttu-id="1ca5b-255">PROJ_OPT_HONOR_CONSTRAINTS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-255">PROJ_OPT_HONOR_CONSTRAINTS</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_HONOR_CONSTRAINTS.aspx)
    
  - [<span data-ttu-id="1ca5b-256">PROJ_OPT_MOVE_ACTUAL_IF_LATER</span><span class="sxs-lookup"><span data-stu-id="1ca5b-256">PROJ_OPT_MOVE_ACTUAL_IF_LATER</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MOVE_ACTUAL_IF_LATER.aspx)
    
  - [<span data-ttu-id="1ca5b-257">PROJ_OPT_MOVE_ACTUAL_TO_STATUS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-257">PROJ_OPT_MOVE_ACTUAL_TO_STATUS</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MOVE_ACTUAL_TO_STATUS.aspx)
    
  - [<span data-ttu-id="1ca5b-258">PROJ_OPT_MOVE_REMAINING_IF_EARLIER</span><span class="sxs-lookup"><span data-stu-id="1ca5b-258">PROJ_OPT_MOVE_REMAINING_IF_EARLIER</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MOVE_REMAINING_IF_EARLIER.aspx)
    
  - [<span data-ttu-id="1ca5b-259">PROJ_OPT_MOVE_REMAINING_TO_STATUS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-259">PROJ_OPT_MOVE_REMAINING_TO_STATUS</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MOVE_REMAINING_TO_STATUS.aspx)
    
  - [<span data-ttu-id="1ca5b-260">PROJ_OPT_MULT_CRITICAL_PATHS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-260">PROJ_OPT_MULT_CRITICAL_PATHS</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_MULT_CRITICAL_PATHS.aspx)
    
  - [<span data-ttu-id="1ca5b-261">PROJ_OPT_SPLIT_IN_PROGRESS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-261">PROJ_OPT_SPLIT_IN_PROGRESS</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_SPLIT_IN_PROGRESS.aspx)
    
  - [<span data-ttu-id="1ca5b-262">PROJ_OPT_SPREAD_ACT_COSTS</span><span class="sxs-lookup"><span data-stu-id="1ca5b-262">PROJ_OPT_SPREAD_ACT_COSTS</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_SPREAD_ACT_COSTS.aspx)
    
  - [<span data-ttu-id="1ca5b-263">PROJ_OPT_SPREAD_PCT_COMP</span><span class="sxs-lookup"><span data-stu-id="1ca5b-263">PROJ_OPT_SPREAD_PCT_COMP</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_SPREAD_PCT_COMP.aspx)
    
  - [<span data-ttu-id="1ca5b-264">PROJ_OPT_TASK_UPDATES_RES</span><span class="sxs-lookup"><span data-stu-id="1ca5b-264">PROJ_OPT_TASK_UPDATES_RES</span></span>](https://msdn.microsoft.com/library/WebSvcProject.ProjectDataSet.ProjectRow.PROJ_OPT_TASK_UPDATES_RES.aspx)
    
## <a name="see-also"></a><span data-ttu-id="1ca5b-265">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ca5b-265">See also</span></span>

- [<span data-ttu-id="1ca5b-266">CSOM 执行和不执行的操作</span><span class="sxs-lookup"><span data-stu-id="1ca5b-266">What the CSOM does and does not do</span></span>](what-the-csom-does-and-does-not-do.md)  
- [<span data-ttu-id="1ca5b-267">Project Server 可编程性</span><span class="sxs-lookup"><span data-stu-id="1ca5b-267">Project Server programmability</span></span>](project-server-programmability.md)   
- [<span data-ttu-id="1ca5b-268">使用基于声明的身份验证的 SharePoint Online 中的远程身份验证</span><span class="sxs-lookup"><span data-stu-id="1ca5b-268">Remote Authentication in SharePoint Online Using Claims-Based Authentication</span></span>](https://msdn.microsoft.com/library/49067f7a-3020-478f-ba97-4b7ce3ea9b87%28Office.15%29.aspx)  
- [<span data-ttu-id="1ca5b-269">Office 外接程序</span><span class="sxs-lookup"><span data-stu-id="1ca5b-269">Office Add-ins</span></span>](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) 
    

