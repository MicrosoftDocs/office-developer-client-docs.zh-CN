---
title: Project Online 从入门到精通
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5b48958e-6dab-4121-871f-fb15f58f1b24
description: '应用程序开发人员可以使用独立应用程序和/或项目加载项自定义 Project Online 网站 (SharePoint 托管)。可以使用大量的应用程序, 包括项目中涉及到 PMO 支持功能的需求, 如以下任何一项:'
ms.openlocfilehash: 00f79b05b886bfd2c54c118245e22f10bb5451bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344406"
---
# <a name="from-0-to-60-with-project-online"></a><span data-ttu-id="961e7-103">Project Online 从入门到精通</span><span class="sxs-lookup"><span data-stu-id="961e7-103">From 0 to 60 with Project Online</span></span>

<span data-ttu-id="961e7-104">应用程序开发人员可以使用独立应用程序和/或项目加载项自定义 Project Online 网站 (SharePoint 托管)。可以使用大量的应用程序, 包括项目中涉及到 PMO 支持功能的需求, 如以下任何一项:</span><span class="sxs-lookup"><span data-stu-id="961e7-104">An application developer can customize a Project Online site (SharePoint hosted) using standalone applications and/or Project add-ins. A wealth of applications is possible that range from addressing needs of those involved in a project to PMO support functions, such as any of the following:</span></span>
  
- <span data-ttu-id="961e7-105">工作人员的简化工时记录卡数据输入</span><span class="sxs-lookup"><span data-stu-id="961e7-105">Streamlined timecard data entry for workers</span></span>
- <span data-ttu-id="961e7-106">有效工时记录卡审批主管</span><span class="sxs-lookup"><span data-stu-id="961e7-106">Efficient timecard approval for supervisors</span></span>
- <span data-ttu-id="961e7-107">项目所需的允许 (采购和状态) 监督</span><span class="sxs-lookup"><span data-stu-id="961e7-107">Oversight of permits (procurement and status) needed for a project</span></span>
- <span data-ttu-id="961e7-108">活动项目的状态/运行状况检查</span><span class="sxs-lookup"><span data-stu-id="961e7-108">Status/Health check of active projects</span></span>
- <span data-ttu-id="961e7-109">问题报告</span><span class="sxs-lookup"><span data-stu-id="961e7-109">Issues report</span></span>
- <span data-ttu-id="961e7-110">更改管理状态报告</span><span class="sxs-lookup"><span data-stu-id="961e7-110">Change Management Status report</span></span>
    
<span data-ttu-id="961e7-111">Project Online 包括 API 支持, 以适应以下方案:</span><span class="sxs-lookup"><span data-stu-id="961e7-111">Project Online includes API support to accommodate the following scenarios:</span></span>
  
- <span data-ttu-id="961e7-112">对于项目 (SharePoint) 托管外接程序:</span><span class="sxs-lookup"><span data-stu-id="961e7-112">For a Project (SharePoint) hosted add-in:</span></span>
    
  - <span data-ttu-id="961e7-113">SharePoint Online 中托管的代码 (JavaScript、HTML、CSS)</span><span class="sxs-lookup"><span data-stu-id="961e7-113">Code (JavaScript, HTML, CSS) that is hosted in SharePoint Online</span></span>
  - <span data-ttu-id="961e7-114">下载到浏览器中并对 SharePoint Online 执行的资产。</span><span class="sxs-lookup"><span data-stu-id="961e7-114">Assets that are downloaded to the browser and executed against SharePoint Online.</span></span>  
  - <span data-ttu-id="961e7-115">JavaScript 中的业务逻辑</span><span class="sxs-lookup"><span data-stu-id="961e7-115">Business logic that is in JavaScript</span></span>   
  - <span data-ttu-id="961e7-116">在 Project Online 或 SharePoint 中访问/存储的数据, 例如 (但不限于):</span><span class="sxs-lookup"><span data-stu-id="961e7-116">Access data that is in/stored in Project Online or SharePoint such as (but is not limited to):</span></span>  
  - <span data-ttu-id="961e7-117">Custom fields</span><span class="sxs-lookup"><span data-stu-id="961e7-117">Custom fields</span></span>  
  - <span data-ttu-id="961e7-118">列表</span><span class="sxs-lookup"><span data-stu-id="961e7-118">Lists</span></span>
    
- <span data-ttu-id="961e7-119">对于项目 (SharePoint) 提供程序托管的外接程序:</span><span class="sxs-lookup"><span data-stu-id="961e7-119">For a Project (SharePoint) provider-hosted add-in:</span></span>
    
  - <span data-ttu-id="961e7-120">在 Project Online 网站外部的网站上存在的代码</span><span class="sxs-lookup"><span data-stu-id="961e7-120">Code that exists on a site external to the Project Online site</span></span> 
  - <span data-ttu-id="961e7-121">外部网站, 可以 (但不限于):</span><span class="sxs-lookup"><span data-stu-id="961e7-121">An external site, which can be (but is not limited to):</span></span>  
  - <span data-ttu-id="961e7-122">另一个 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="961e7-122">Another SharePoint site</span></span>  
  - <span data-ttu-id="961e7-123">在任何平台上构建的 Web 应用/服务</span><span class="sxs-lookup"><span data-stu-id="961e7-123">Web App/Service built on any platform</span></span>  
  - <span data-ttu-id="961e7-124">外部网站包含业务逻辑</span><span class="sxs-lookup"><span data-stu-id="961e7-124">The external site contains business logic</span></span>  
  - <span data-ttu-id="961e7-125">浏览器从 project online 重定向到外部网站, 并具有对 Project online 的访问令牌</span><span class="sxs-lookup"><span data-stu-id="961e7-125">The browser is redirected from Project Online to external site with access tokens to Project Online</span></span>  
  - <span data-ttu-id="961e7-126">外部网站可以对 SharePoint 和 Project Online 进行调用</span><span class="sxs-lookup"><span data-stu-id="961e7-126">The external site can make calls to SharePoint and Project Online</span></span>
    
- <span data-ttu-id="961e7-127">对于外部/独立外接程序:</span><span class="sxs-lookup"><span data-stu-id="961e7-127">For an external/standalone add-in:</span></span>
    
  - <span data-ttu-id="961e7-128">用户在其设备上执行应用程序</span><span class="sxs-lookup"><span data-stu-id="961e7-128">User executes an application on their device</span></span>
  - <span data-ttu-id="961e7-129">应用程序直接对 Project Online api 进行身份验证和调用</span><span class="sxs-lookup"><span data-stu-id="961e7-129">Application authenticates and calls Project Online APIs directly</span></span>
    

|<span data-ttu-id="961e7-130">应用程序类型</span><span class="sxs-lookup"><span data-stu-id="961e7-130">Type of application</span></span>|<span data-ttu-id="961e7-131">API 实现</span><span class="sxs-lookup"><span data-stu-id="961e7-131">API implementation</span></span>|<span data-ttu-id="961e7-132">目标环境</span><span class="sxs-lookup"><span data-stu-id="961e7-132">Target environment</span></span>|<span data-ttu-id="961e7-133">应用程序示例</span><span class="sxs-lookup"><span data-stu-id="961e7-133">Application examples</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="961e7-134">托管项目</span><span class="sxs-lookup"><span data-stu-id="961e7-134">Project hosted</span></span>  <br/> |<span data-ttu-id="961e7-135">JSOM (Java 脚本对象模型)</span><span class="sxs-lookup"><span data-stu-id="961e7-135">JSOM (Java Script Object Model)</span></span>  <br/> <span data-ttu-id="961e7-136">REST</span><span class="sxs-lookup"><span data-stu-id="961e7-136">REST</span></span>  <br/> |<span data-ttu-id="961e7-137">Browser</span><span class="sxs-lookup"><span data-stu-id="961e7-137">Browser</span></span>  <br/> |<span data-ttu-id="961e7-138">工时记录卡条目</span><span class="sxs-lookup"><span data-stu-id="961e7-138">Timecard entry</span></span>  <br/> <span data-ttu-id="961e7-139">工时记录卡审核</span><span class="sxs-lookup"><span data-stu-id="961e7-139">Timecard approval</span></span>  <br/> <span data-ttu-id="961e7-140">项目状态</span><span class="sxs-lookup"><span data-stu-id="961e7-140">Project Status</span></span>  <br/> <span data-ttu-id="961e7-141">问题报告</span><span class="sxs-lookup"><span data-stu-id="961e7-141">Issues Report</span></span>  <br/> |
|<span data-ttu-id="961e7-142">项目提供程序托管</span><span class="sxs-lookup"><span data-stu-id="961e7-142">Project Provider Hosted</span></span>  <br/> |<span data-ttu-id="961e7-143">CSOM 客户端库</span><span class="sxs-lookup"><span data-stu-id="961e7-143">CSOM client library</span></span>  <br/> |<span data-ttu-id="961e7-144">Azure 网站/应用</span><span class="sxs-lookup"><span data-stu-id="961e7-144">Azure Website/App</span></span>  <br/> <span data-ttu-id="961e7-145">非 Windows 环境 (灯等)</span><span class="sxs-lookup"><span data-stu-id="961e7-145">Non-Windows environment (LAMP, etc.)</span></span>  <br/> |<span data-ttu-id="961e7-146">外部时间表验证程序</span><span class="sxs-lookup"><span data-stu-id="961e7-146">External timesheet validator</span></span>  <br/> <span data-ttu-id="961e7-147">项目导入程序</span><span class="sxs-lookup"><span data-stu-id="961e7-147">Project Importer</span></span>  <br/> |
|<span data-ttu-id="961e7-148">外部/独立</span><span class="sxs-lookup"><span data-stu-id="961e7-148">External/Standalone</span></span>  <br/> |<span data-ttu-id="961e7-149">REST</span><span class="sxs-lookup"><span data-stu-id="961e7-149">REST</span></span>  <br/> <span data-ttu-id="961e7-150">CSOM</span><span class="sxs-lookup"><span data-stu-id="961e7-150">CSOM</span></span>  <br/> |<span data-ttu-id="961e7-151">REST-任意平台</span><span class="sxs-lookup"><span data-stu-id="961e7-151">REST - any platform</span></span>  <br/> <span data-ttu-id="961e7-152">CSOM-任何 .net 支持的平台</span><span class="sxs-lookup"><span data-stu-id="961e7-152">CSOM - any .NET supported platform</span></span>  <br/> |<span data-ttu-id="961e7-153">工时记录卡条目</span><span class="sxs-lookup"><span data-stu-id="961e7-153">Timecard entry</span></span>  <br/> <span data-ttu-id="961e7-154">将项目迁移到新网站</span><span class="sxs-lookup"><span data-stu-id="961e7-154">Migration of projects to a new site</span></span>  <br/> <span data-ttu-id="961e7-155">更改管理状态。</span><span class="sxs-lookup"><span data-stu-id="961e7-155">Change Management Status.</span></span>  <br/> |
   
## <a name="what-does-it-take-to-start-developing-applications-for-project-online"></a><span data-ttu-id="961e7-156">开始开发 Project Online 应用程序需要执行哪些操作？</span><span class="sxs-lookup"><span data-stu-id="961e7-156">What does it take to start developing applications for Project Online?</span></span>

<span data-ttu-id="961e7-157">开发 project online 应用程序所需的常见项目是 project online 帐户和测试数据, 包括工作分配、任务、资源和自定义字段的项目和项目相关信息。</span><span class="sxs-lookup"><span data-stu-id="961e7-157">The common items needed for developing Project Online applications are a Project Online account and test data--projects and project-related information that include assignments, tasks, resources, and custom fields.</span></span> <span data-ttu-id="961e7-158">开发环境也是必需的, 但开发环境的具体情况取决于应用程序所需的应用程序和 API 接口的类型。</span><span class="sxs-lookup"><span data-stu-id="961e7-158">A development environment is needed as well, but specifics of the development environment depend on the type of application and the API interface needed for the application.</span></span> <span data-ttu-id="961e7-159">接下来的几节介绍了三个 API 接口的开发需求。</span><span class="sxs-lookup"><span data-stu-id="961e7-159">The next few sections describe development needs for the three API interfaces.</span></span>
  
<span data-ttu-id="961e7-160">参考文档介绍了所有三个接口通用的对象模型, 以及显示对象模型组件之间关系的实体映射。</span><span class="sxs-lookup"><span data-stu-id="961e7-160">The reference documentation describes the object model that is common for all three interfaces, as well as an entity map that shows relations among the object model components.</span></span>
  
## <a name="project-hosted-add-in-development-environment"></a><span data-ttu-id="961e7-161">项目托管的加载项开发环境</span><span class="sxs-lookup"><span data-stu-id="961e7-161">Project hosted add-in development environment</span></span>

<span data-ttu-id="961e7-162">托管加载项是驻留在服务器上并下载到浏览器以进行运行时执行的外接程序。</span><span class="sxs-lookup"><span data-stu-id="961e7-162">A hosted add-in is an add-in that resides on the server and is downloaded to a browser for runtime execution.</span></span> <span data-ttu-id="961e7-163">托管的外接程序可以使用 JSOM 或 REST 接口, 并在 JavaScript 中编写。</span><span class="sxs-lookup"><span data-stu-id="961e7-163">Hosted add-ins can use the JSOM or REST interfaces and are written in JavaScript.</span></span> <span data-ttu-id="961e7-164">Project Online 为运行时执行提供对 JSOM 库的引用。</span><span class="sxs-lookup"><span data-stu-id="961e7-164">Project Online provides references to the JSOM library for runtime execution.</span></span> <span data-ttu-id="961e7-165">假定开发在 Windows 平台上, 则需要执行以下资源:</span><span class="sxs-lookup"><span data-stu-id="961e7-165">Assuming development is on a Windows platform, the needed resources follow:</span></span>
  
- <span data-ttu-id="961e7-166">visual studio 2015 (首选) 或 visual studio 2013</span><span class="sxs-lookup"><span data-stu-id="961e7-166">Visual Studio 2015 (preferred) or Visual Studio 2013</span></span>
    
- <span data-ttu-id="961e7-167">适用于 Visual Studio 的 Office 开发工具</span><span class="sxs-lookup"><span data-stu-id="961e7-167">Office development tools for Visual Studio</span></span>
    
- <span data-ttu-id="961e7-168">JavaScript 语言</span><span class="sxs-lookup"><span data-stu-id="961e7-168">JavaScript language</span></span>
    
<span data-ttu-id="961e7-169">请https://github.com/OfficeDev/Project-JSOM-Copy-Work-Packages访问示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="961e7-169">Visit https://github.com/OfficeDev/Project-JSOM-Copy-Work-Packages for a sample application.</span></span> 
  
<span data-ttu-id="961e7-170">您可以通过几个简单的步骤下载并运行示例:</span><span class="sxs-lookup"><span data-stu-id="961e7-170">You can download and run the sample in a few easy steps:</span></span>
  
1. <span data-ttu-id="961e7-171">下载并打开示例应用程序</span><span class="sxs-lookup"><span data-stu-id="961e7-171">Download and open the sample application</span></span>
    
2. <span data-ttu-id="961e7-172">在 "属性" 窗口中更新 SiteURL</span><span class="sxs-lookup"><span data-stu-id="961e7-172">Update the SiteURL in the Properties window</span></span>
    
   <span data-ttu-id="961e7-173">project online 将检查外接程序的应用程序范围和用户权限以管理对 Project Online 主机上的信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="961e7-173">Project Online examines both the application scope of the add-in and the user permissions to govern access to information on the Project Online host.</span></span> <span data-ttu-id="961e7-174">如果在一个或两个设置中明确拒绝访问, Project Online 将拒绝对信息的访问。</span><span class="sxs-lookup"><span data-stu-id="961e7-174">If access is explicitly denied in either or both settings, Project Online denies access to the information.</span></span> <span data-ttu-id="961e7-175">否则, 将授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="961e7-175">Otherwise, access is granted.</span></span>
    
3. <span data-ttu-id="961e7-176">在您的网站上启用[旁加载](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="961e7-176">Enable [sideloading](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins) on your site.</span></span>  
    
4. <span data-ttu-id="961e7-177">生成项目。</span><span class="sxs-lookup"><span data-stu-id="961e7-177">Build the project.</span></span>
    
5. <span data-ttu-id="961e7-178">运行项目。</span><span class="sxs-lookup"><span data-stu-id="961e7-178">Run the project.</span></span>
    
## <a name="project-provider-hosted-add-in-development-environment"></a><span data-ttu-id="961e7-179">项目提供程序托管的外接程序开发环境</span><span class="sxs-lookup"><span data-stu-id="961e7-179">Project provider-hosted add-in development environment</span></span>

<span data-ttu-id="961e7-180">提供程序托管的外接程序是编写并驻留在任何 web 平台上的应用程序。</span><span class="sxs-lookup"><span data-stu-id="961e7-180">Provider hosted add-ins are applications written and residing on any web platform.</span></span> <span data-ttu-id="961e7-181">他们可以使用 REST (或 CSOM for Microsoft 平台) API 连接和执行数据操作。</span><span class="sxs-lookup"><span data-stu-id="961e7-181">They can connect and perform data operations using the REST (or CSOM for Microsoft platforms) API.</span></span> <span data-ttu-id="961e7-182">支持 REST 接口的任何语言和环境都可用于开发。</span><span class="sxs-lookup"><span data-stu-id="961e7-182">Any language and environment that supports the REST interface can be used for development.</span></span> 
  
<span data-ttu-id="961e7-183">此类应用程序的 Windows 开发环境示例包括以下各项:</span><span class="sxs-lookup"><span data-stu-id="961e7-183">An example of the Windows development environment for this type of application includes the following items:</span></span>
  
-  <span data-ttu-id="961e7-184">visual studio 2015 (首选) 或 visual studio 2013</span><span class="sxs-lookup"><span data-stu-id="961e7-184">Visual Studio 2015 (preferred) or Visual Studio 2013</span></span> 
    
- <span data-ttu-id="961e7-185">适用于 visual studio 的 Microsoft Office 开发工具 (由 visual studio 2015 Professional 和 Enterprise edition 提供)</span><span class="sxs-lookup"><span data-stu-id="961e7-185">Microsoft Office Development Tools for Visual Studio (supplied with Visual Studio 2015 Professional and Enterprise editions)</span></span>
    
- <span data-ttu-id="961e7-186">.net Framework 4.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="961e7-186">.NET Framework 4.0 or newer</span></span>
    
- <span data-ttu-id="961e7-187">[SharePointOnline CSOM 程序包](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM)(对于 CSOM 呼叫)</span><span class="sxs-lookup"><span data-stu-id="961e7-187">[SharePointOnline CSOM package](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM) (for CSOM calls)</span></span> 
    
- <span data-ttu-id="961e7-188">一种编程语言, 例如 c #</span><span class="sxs-lookup"><span data-stu-id="961e7-188">A programming language, such as C#</span></span> 
    
<span data-ttu-id="961e7-189">访问https://github.com/OfficeDev/Project-Add-in-REST-BasicDataOperations以获取工作示例脚本。</span><span class="sxs-lookup"><span data-stu-id="961e7-189">Visit https://github.com/OfficeDev/Project-Add-in-REST-BasicDataOperations for working sample scripts.</span></span> 
  
<span data-ttu-id="961e7-190">您可以通过以下几个步骤来运行该示例:</span><span class="sxs-lookup"><span data-stu-id="961e7-190">You can run the sample in a few steps:</span></span>
  
1. <span data-ttu-id="961e7-191">下载并打开示例应用程序</span><span class="sxs-lookup"><span data-stu-id="961e7-191">Download and open the sample application</span></span>
    
2. <span data-ttu-id="961e7-192">在 "属性" 窗口中更新 SiteURL</span><span class="sxs-lookup"><span data-stu-id="961e7-192">Update the SiteURL in the Properties window</span></span>
    
   <span data-ttu-id="961e7-193">project online 将检查外接程序的应用程序范围和用户权限以管理对 Project Online 主机上的信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="961e7-193">Project Online examines both the application scope of the add-in and the user permissions to govern access to information on the Project Online host.</span></span> <span data-ttu-id="961e7-194">如果在一个或两个设置中明确拒绝访问, Project Online 将拒绝对信息的访问。</span><span class="sxs-lookup"><span data-stu-id="961e7-194">If access is explicitly denied in either or both settings, Project Online denies access to the information.</span></span> <span data-ttu-id="961e7-195">否则, 将授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="961e7-195">Otherwise, access is granted.</span></span>
    
3. <span data-ttu-id="961e7-196">在您的网站上启用[旁加载](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="961e7-196">Enable [sideloading](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins) on your site.</span></span> 
    
4. <span data-ttu-id="961e7-197">生成项目。</span><span class="sxs-lookup"><span data-stu-id="961e7-197">Build the project.</span></span>
    
5. <span data-ttu-id="961e7-198">运行项目。</span><span class="sxs-lookup"><span data-stu-id="961e7-198">Run the project.</span></span>
    
## <a name="externalstandalone-application-development-environment"></a><span data-ttu-id="961e7-199">外部/独立应用程序开发环境</span><span class="sxs-lookup"><span data-stu-id="961e7-199">External/standalone application development environment</span></span>

<span data-ttu-id="961e7-200">独立应用程序可以使用客户端对象模型 (CSOM) 或 REST 与 project online 进行通信以创建、检索、更新和删除服务器上的信息, 从而调用 project online。</span><span class="sxs-lookup"><span data-stu-id="961e7-200">A standalone application can call Project Online using the Client Side Object Model (CSOM) or REST to communicate with Project Online to create, retrieve, update, and delete information residing on the server.</span></span> <span data-ttu-id="961e7-201">这是一个独立的客户端应用程序, 它依赖于要运行的用户访问级别。</span><span class="sxs-lookup"><span data-stu-id="961e7-201">This is a standalone client application that depends on the user access level to run.</span></span> 
  
<span data-ttu-id="961e7-202">此类应用程序的 Windows 开发环境示例包括以下各项:</span><span class="sxs-lookup"><span data-stu-id="961e7-202">An example of the Windows development environment for this type of application includes the following items:</span></span>
  
- <span data-ttu-id="961e7-203">visual studio 2015 (首选) 或 visual studio 2013</span><span class="sxs-lookup"><span data-stu-id="961e7-203">Visual Studio 2015 (preferred) or Visual Studio 2013</span></span> 
    
- <span data-ttu-id="961e7-204">适用于 visual studio 的 Microsoft Office 开发工具 (由 visual studio 2015 Professional 和 Enterprise edition 提供)</span><span class="sxs-lookup"><span data-stu-id="961e7-204">Microsoft Office Development Tools for Visual Studio (supplied with Visual Studio 2015 Professional and Enterprise editions)</span></span>
    
- <span data-ttu-id="961e7-205">.net Framework 4.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="961e7-205">.NET Framework 4.0 or newer</span></span>
    
- <span data-ttu-id="961e7-206">[SharePointOnline CSOM 程序包](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM)(对于 CSOM 呼叫)</span><span class="sxs-lookup"><span data-stu-id="961e7-206">[SharePointOnline CSOM package](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM) (for CSOM calls)</span></span> 
    
- <span data-ttu-id="961e7-207">一种编程语言, 例如 c #</span><span class="sxs-lookup"><span data-stu-id="961e7-207">A programming language, such as C#</span></span> 
    
<span data-ttu-id="961e7-208">请https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields访问示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="961e7-208">Visit https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields for a sample application.</span></span> 
  
<span data-ttu-id="961e7-209">您可以通过以下几个步骤来运行该示例:</span><span class="sxs-lookup"><span data-stu-id="961e7-209">You can run the sample in a few steps:</span></span>
  
1. <span data-ttu-id="961e7-210">下载示例应用程序</span><span class="sxs-lookup"><span data-stu-id="961e7-210">Download the sample application</span></span>
    
2. <span data-ttu-id="961e7-211">进行几处更改, 以访问 Project Online 网站 (网站名称、用户帐户和密码)。</span><span class="sxs-lookup"><span data-stu-id="961e7-211">Make a couple of changes to access your Project Online site—the site name, user account, and password.</span></span>
    
   <span data-ttu-id="961e7-212">确保用户有权访问所有项目。</span><span class="sxs-lookup"><span data-stu-id="961e7-212">Ensure the user has access to all projects.</span></span> <span data-ttu-id="961e7-213">Project Online 使用用户权限来管理对数据存储区中的信息的访问。</span><span class="sxs-lookup"><span data-stu-id="961e7-213">Project Online uses user permissions to govern access to information in the data store.</span></span>
    
3. <span data-ttu-id="961e7-214">通过在 nuget 控制台中键入以下内容, 使用 nuget 包管理器控制台将 SharePoint 程序集添加到引用中, 可从 "工具" 菜单中进行以下操作:</span><span class="sxs-lookup"><span data-stu-id="961e7-214">Add the SharePoint assembly to the references using the Nuget Package Manager Console, available from the Tools menu by typing the following in the Nuget console:</span></span> 
    
   `Install-Package Microsoft.SharePointOnline.CSOM`

4. <span data-ttu-id="961e7-215">生成项目。</span><span class="sxs-lookup"><span data-stu-id="961e7-215">Build the project.</span></span>
    
5. <span data-ttu-id="961e7-216">运行项目。</span><span class="sxs-lookup"><span data-stu-id="961e7-216">Run the project.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="961e7-217">后续步骤</span><span class="sxs-lookup"><span data-stu-id="961e7-217">Next steps</span></span>

<span data-ttu-id="961e7-218">每个示例应用程序都有一篇文章, 其中介绍了使用单个项目 API 的重点。</span><span class="sxs-lookup"><span data-stu-id="961e7-218">Each sample application has an article to explain the highlights of working with the individual Project API.</span></span> <span data-ttu-id="961e7-219">这些文章将显示在以下列表中, 以及一些描述实体关系、查询系统上的信息以及访问自定义字段的文章。</span><span class="sxs-lookup"><span data-stu-id="961e7-219">The articles appear in the following list, along with a few articles that describe the entity relationships, information on the query system, and accessing Custom Fields.</span></span> 
  
- [<span data-ttu-id="961e7-220">使用客户端对象模型开发 Project Online 应用程序</span><span class="sxs-lookup"><span data-stu-id="961e7-220">Developing a Project Online Application Using the Client-side Object Model</span></span>](developing-a-project-online-application-using-the-client-side-object-model.md)
    
- [<span data-ttu-id="961e7-221">使用 JavaScript 对象模型 (JSOM) 开发 Project Online 外接</span><span class="sxs-lookup"><span data-stu-id="961e7-221">Developing a Project Online add-in using the JavaScript Object Model (JSOM)</span></span>](developing-a-project-online-add-in-using-the-javascript-object-model-jsom.md)
    
- [<span data-ttu-id="961e7-222">访问 Project Online 企业自定义字段</span><span class="sxs-lookup"><span data-stu-id="961e7-222">Accessing Project Online enterprise custom fields</span></span>](accessing-project-online-enterprise-custom-fields.md)
    
## <a name="see-also"></a><span data-ttu-id="961e7-223">另请参阅</span><span class="sxs-lookup"><span data-stu-id="961e7-223">See also</span></span>

<span data-ttu-id="961e7-224">有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/en-us/project)。</span><span class="sxs-lookup"><span data-stu-id="961e7-224">For documentation and samples related to Project Online and application development using CSOM, see the [Project Development Portal](https://developer.microsoft.com/en-us/project).</span></span>
    

