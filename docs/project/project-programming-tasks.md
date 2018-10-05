---
title: Project 编程任务
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: ac5544e7-ff7a-4af5-ac1b-33a49bc6be0d
description: 本节包含以某种方式-toarticles 显示如何使用 JavaScript 库客户端对象模型 (CSOM) 和 Project Server 2013 和 Project Online 执行其他编程任务。 编程任务的示例包括创建 SharePoint 承载的 Project Server 应用程序，创建工作流的需求管理;编程 Project Server 应用程序与 Windows Communication Foundation (WCF);自定义 Project Web App 功能区;创建 Project Server Web 部件;创建 Project Server 事件处理程序和远程事件接收器;和批量更新自定义字段和 for Project Online 中创建项目网站。
ms.openlocfilehash: 385b9fa53c2c7faf2a218816bf4d3f0499b9ecd1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388607"
---
# <a name="project-programming-tasks"></a><span data-ttu-id="c410b-104">Project 编程任务</span><span class="sxs-lookup"><span data-stu-id="c410b-104">Project programming tasks</span></span>

<span data-ttu-id="c410b-105">本节包含一些介绍如何使用 JavaScript 库客户端对象模型 (CSOM) 和 Project Server 2013 和 Project Online 执行其他编程任务的"帮助"文章。</span><span class="sxs-lookup"><span data-stu-id="c410b-105">This section includes some "how-to" articles that show how to use the JavaScript library for the client-side object model (CSOM), and perform other programming tasks for Project Server 2013 and Project Online.</span></span> <span data-ttu-id="c410b-106">编程任务的示例包括创建 SharePoint 承载的 Project Server 应用程序，创建工作流的需求管理;编程 Project Server 应用程序与 Windows Communication Foundation (WCF);自定义 Project Web App 功能区;创建 Project Server Web 部件;创建 Project Server 事件处理程序和远程事件接收器;和批量更新自定义字段和 for Project Online 中创建项目网站。</span><span class="sxs-lookup"><span data-stu-id="c410b-106">Examples of programming tasks include creating a SharePoint-hosted Project Server app, creating workflows for demand management; programming Project Server applications with the Windows Communication Foundation (WCF); customizing the Project Web App ribbon; creating Project Server Web Parts; creating Project Server event handlers and remote event receivers; and bulk updating custom fields and creating project sites for Project Online.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c410b-107">有关使用 JS 网格控件进行编程的信息，请参阅 SharePoint 2010 开发人员参考中的[JS 网格控件](https://msdn.microsoft.com/library/ee535898%28office.14%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c410b-107">For information about programming with the JS Grid control, see [JS Grid Control](https://msdn.microsoft.com/library/ee535898%28office.14%29.aspx) in the SharePoint 2010 developer reference.</span></span> <span data-ttu-id="c410b-108">有关的托管的代码参考，请参阅[Microsoft.SharePoint.JSGrid Namespace](https://msdn.microsoft.com/library/microsoft.sharepoint.jsgrid%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c410b-108">For the managed code reference, see [Microsoft.SharePoint.JSGrid Namespace](https://msdn.microsoft.com/library/microsoft.sharepoint.jsgrid%28Office.15%29.aspx).</span></span> <span data-ttu-id="c410b-109">JS 网格控件 web 控件，请参阅[JSGrid 类](https://msdn.microsoft.com/library/microsoft.sharepoint.webcontrols.jsgrid%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c410b-109">For the JS Grid control web controls, see [JSGrid class](https://msdn.microsoft.com/library/microsoft.sharepoint.webcontrols.jsgrid%28Office.15%29.aspx).</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="c410b-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="c410b-110">In this section</span></span>

[<span data-ttu-id="c410b-111">开发 Project Server 工作流入门</span><span class="sxs-lookup"><span data-stu-id="c410b-111">Getting started developing Project Server workflows</span></span>](getting-started-developing-project-server-workflows.md)
  
[<span data-ttu-id="c410b-112">批量更新自定义字段并从 Project Online 中的工作流创建项目网站</span><span class="sxs-lookup"><span data-stu-id="c410b-112">Bulk update custom fields and create project sites from a workflow in Project Online</span></span>](bulk-update-custom-fields-and-create-project-sites-from-workflow-in-project.md)
  
[<span data-ttu-id="c410b-113">创建、 检索、 更新和删除项目使用 Project Server JavaScript 对象模型</span><span class="sxs-lookup"><span data-stu-id="c410b-113">Create, retrieve, update, and delete projects by using the Project Server JavaScript object model</span></span>](create-retrieve-update-delete-projects-using-project-server-javascript.md)
  
<span data-ttu-id="c410b-114">[创建 SharePoint 承载的 Project Server 加载项](create-a-sharepoint-hosted-project-server-add-in.md)： 包括如何修改 Project Web App 功能区上的部分</span><span class="sxs-lookup"><span data-stu-id="c410b-114">[Create a SharePoint-hosted Project Server add-in](create-a-sharepoint-hosted-project-server-add-in.md) : includes a section on how to modify the Project Web App ribbon</span></span> 
  
## <a name="reference"></a><span data-ttu-id="c410b-115">参考</span><span class="sxs-lookup"><span data-stu-id="c410b-115">Reference</span></span>

[<span data-ttu-id="c410b-116">项目 PSI 参考概述</span><span class="sxs-lookup"><span data-stu-id="c410b-116">Project PSI reference overview</span></span>](project-psi-reference-overview.md)
  
## <a name="see-also"></a><span data-ttu-id="c410b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c410b-117">See also</span></span>



[<span data-ttu-id="c410b-118">Project 2013 的客户端对象模型 (CSOM)</span><span class="sxs-lookup"><span data-stu-id="c410b-118">Client-side object model (CSOM) for Project 2013</span></span>](client-side-object-model-csom-for-project-2013.md)

