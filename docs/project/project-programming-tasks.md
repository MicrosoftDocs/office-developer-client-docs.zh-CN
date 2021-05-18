---
title: Project 编程任务
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: ac5544e7-ff7a-4af5-ac1b-33a49bc6be0d
description: 本节包括一些操作方法，这些说明显示如何将 JavaScript 库用于客户端对象模型 (CSOM) ，以及执行 Project Server 2013 和 Project Online 的其他编程任务。 编程任务的示例包括SharePoint托管的 Project Server 应用程序、创建用于需求管理的工作流;使用 Project Communication Foundation 和 WCF Windows 对 (Server) ;自定义Project Web App功能区;创建 Project Server Web 部件;创建Project服务器事件处理程序和远程事件接收器;和批量更新自定义域，并创建项目Project Online。
ms.openlocfilehash: 385b9fa53c2c7faf2a218816bf4d3f0499b9ecd1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301496"
---
# <a name="project-programming-tasks"></a><span data-ttu-id="4ef20-104">Project 编程任务</span><span class="sxs-lookup"><span data-stu-id="4ef20-104">Project programming tasks</span></span>

<span data-ttu-id="4ef20-105">本节包含一些"操作方法"文章，这些文章介绍了如何针对客户端对象模型 (CSOM) 使用 JavaScript 库，以及如何执行 Project Server 2013 和 Project Online 的其他编程任务。</span><span class="sxs-lookup"><span data-stu-id="4ef20-105">This section includes some "how-to" articles that show how to use the JavaScript library for the client-side object model (CSOM), and perform other programming tasks for Project Server 2013 and Project Online.</span></span> <span data-ttu-id="4ef20-106">编程任务的示例包括SharePoint托管的 Project Server 应用程序、创建用于需求管理的工作流;使用 Project Communication Foundation 和 WCF Windows 对 (Server) ;自定义Project Web App功能区;创建 Project Server Web 部件;创建Project服务器事件处理程序和远程事件接收器;和批量更新自定义域，并创建项目Project Online。</span><span class="sxs-lookup"><span data-stu-id="4ef20-106">Examples of programming tasks include creating a SharePoint-hosted Project Server app, creating workflows for demand management; programming Project Server applications with the Windows Communication Foundation (WCF); customizing the Project Web App ribbon; creating Project Server Web Parts; creating Project Server event handlers and remote event receivers; and bulk updating custom fields and creating project sites for Project Online.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ef20-107">有关使用 JS 网格控件进行编程的信息，请参阅 js [Grid Control](https://msdn.microsoft.com/library/ee535898%28office.14%29.aspx) in the SharePoint 2010 developer reference。</span><span class="sxs-lookup"><span data-stu-id="4ef20-107">For information about programming with the JS Grid control, see [JS Grid Control](https://msdn.microsoft.com/library/ee535898%28office.14%29.aspx) in the SharePoint 2010 developer reference.</span></span> <span data-ttu-id="4ef20-108">有关托管代码引用，请参阅 [Microsoft.SharePoint.JSGrid Namespace](https://msdn.microsoft.com/library/microsoft.sharepoint.jsgrid%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4ef20-108">For the managed code reference, see [Microsoft.SharePoint.JSGrid Namespace](https://msdn.microsoft.com/library/microsoft.sharepoint.jsgrid%28Office.15%29.aspx).</span></span> <span data-ttu-id="4ef20-109">有关 JS 网格控件 Web 控件，请参阅 [JSGrid 类](https://msdn.microsoft.com/library/microsoft.sharepoint.webcontrols.jsgrid%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4ef20-109">For the JS Grid control web controls, see [JSGrid class](https://msdn.microsoft.com/library/microsoft.sharepoint.webcontrols.jsgrid%28Office.15%29.aspx).</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="4ef20-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="4ef20-110">In this section</span></span>

[<span data-ttu-id="4ef20-111">开始开发 Project Server 工作流</span><span class="sxs-lookup"><span data-stu-id="4ef20-111">Getting started developing Project Server workflows</span></span>](getting-started-developing-project-server-workflows.md)
  
[<span data-ttu-id="4ef20-112">批量更新自定义字段并通过 Project Online 中的工作流创建项目网站</span><span class="sxs-lookup"><span data-stu-id="4ef20-112">Bulk update custom fields and create project sites from a workflow in Project Online</span></span>](bulk-update-custom-fields-and-create-project-sites-from-workflow-in-project.md)
  
[<span data-ttu-id="4ef20-113">使用 Project Server JavaScript 对象模型创建、检索、更新和删除项目</span><span class="sxs-lookup"><span data-stu-id="4ef20-113">Create, retrieve, update, and delete projects by using the Project Server JavaScript object model</span></span>](create-retrieve-update-delete-projects-using-project-server-javascript.md)
  
<span data-ttu-id="4ef20-114">[Create a SharePoint hosted Project Server add-in](create-a-sharepoint-hosted-project-server-add-in.md) ： includes a section on how to modify the Project Web App ribbon</span><span class="sxs-lookup"><span data-stu-id="4ef20-114">[Create a SharePoint-hosted Project Server add-in](create-a-sharepoint-hosted-project-server-add-in.md) : includes a section on how to modify the Project Web App ribbon</span></span> 
  
## <a name="reference"></a><span data-ttu-id="4ef20-115">参考</span><span class="sxs-lookup"><span data-stu-id="4ef20-115">Reference</span></span>

[<span data-ttu-id="4ef20-116">Project PSI 参考概述</span><span class="sxs-lookup"><span data-stu-id="4ef20-116">Project PSI reference overview</span></span>](project-psi-reference-overview.md)
  
## <a name="see-also"></a><span data-ttu-id="4ef20-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ef20-117">See also</span></span>



[<span data-ttu-id="4ef20-118">Project 2013 的客户端对象模型 (CSOM)</span><span class="sxs-lookup"><span data-stu-id="4ef20-118">Client-side object model (CSOM) for Project 2013</span></span>](client-side-object-model-csom-for-project-2013.md)

