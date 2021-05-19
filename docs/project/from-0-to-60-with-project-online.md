---
title: Project Online 从入门到精通
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5b48958e-6dab-4121-871f-fb15f58f1b24
description: 应用程序开发人员可以使用独立Project Online和/ (SharePoint加载项) 托管的网站Project网站集。大量的应用程序可能涵盖从满足项目中涉及的这些应用程序的需求到 PMO 支持功能，例如以下任一功能：
ms.openlocfilehash: 00f79b05b886bfd2c54c118245e22f10bb5451bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344406"
---
# <a name="from-0-to-60-with-project-online"></a><span data-ttu-id="e219e-103">Project Online 从入门到精通</span><span class="sxs-lookup"><span data-stu-id="e219e-103">From 0 to 60 with Project Online</span></span>

<span data-ttu-id="e219e-104">应用程序开发人员可以使用独立Project Online和/ (SharePoint加载项) 托管的网站Project网站集。大量的应用程序可能涵盖从满足项目中涉及的这些应用程序的需求到 PMO 支持功能，例如以下任一功能：</span><span class="sxs-lookup"><span data-stu-id="e219e-104">An application developer can customize a Project Online site (SharePoint hosted) using standalone applications and/or Project add-ins. A wealth of applications is possible that range from addressing needs of those involved in a project to PMO support functions, such as any of the following:</span></span>
  
- <span data-ttu-id="e219e-105">简化工作人员的时间卡数据输入</span><span class="sxs-lookup"><span data-stu-id="e219e-105">Streamlined timecard data entry for workers</span></span>
- <span data-ttu-id="e219e-106">高效的主管时间卡审批</span><span class="sxs-lookup"><span data-stu-id="e219e-106">Efficient timecard approval for supervisors</span></span>
- <span data-ttu-id="e219e-107">监督许可证 (采购和) 项目所需的状态</span><span class="sxs-lookup"><span data-stu-id="e219e-107">Oversight of permits (procurement and status) needed for a project</span></span>
- <span data-ttu-id="e219e-108">活动项目的状态/运行状况检查</span><span class="sxs-lookup"><span data-stu-id="e219e-108">Status/Health check of active projects</span></span>
- <span data-ttu-id="e219e-109">问题报告</span><span class="sxs-lookup"><span data-stu-id="e219e-109">Issues report</span></span>
- <span data-ttu-id="e219e-110">更改管理状态报告</span><span class="sxs-lookup"><span data-stu-id="e219e-110">Change Management Status report</span></span>
    
<span data-ttu-id="e219e-111">Project Online API 支持以适应以下方案：</span><span class="sxs-lookup"><span data-stu-id="e219e-111">Project Online includes API support to accommodate the following scenarios:</span></span>
  
- <span data-ttu-id="e219e-112">对于Project (SharePoint) 加载项：</span><span class="sxs-lookup"><span data-stu-id="e219e-112">For a Project (SharePoint) hosted add-in:</span></span>
    
  - <span data-ttu-id="e219e-113">托管 (Online) JavaScript、HTML、CSS SharePoint 代码</span><span class="sxs-lookup"><span data-stu-id="e219e-113">Code (JavaScript, HTML, CSS) that is hosted in SharePoint Online</span></span>
  - <span data-ttu-id="e219e-114">下载到浏览器并针对 SharePoint Online 执行的资产。</span><span class="sxs-lookup"><span data-stu-id="e219e-114">Assets that are downloaded to the browser and executed against SharePoint Online.</span></span>  
  - <span data-ttu-id="e219e-115">JavaScript 中的业务逻辑</span><span class="sxs-lookup"><span data-stu-id="e219e-115">Business logic that is in JavaScript</span></span>   
  - <span data-ttu-id="e219e-116">访问存储在数据存储区或Project Online SharePoint数据 (但不限于) ：</span><span class="sxs-lookup"><span data-stu-id="e219e-116">Access data that is in/stored in Project Online or SharePoint such as (but is not limited to):</span></span>  
  - <span data-ttu-id="e219e-117">自定义域</span><span class="sxs-lookup"><span data-stu-id="e219e-117">Custom fields</span></span>  
  - <span data-ttu-id="e219e-118">列表</span><span class="sxs-lookup"><span data-stu-id="e219e-118">Lists</span></span>
    
- <span data-ttu-id="e219e-119">对于Project (SharePoint) 托管的外接程序：</span><span class="sxs-lookup"><span data-stu-id="e219e-119">For a Project (SharePoint) provider-hosted add-in:</span></span>
    
  - <span data-ttu-id="e219e-120">存在于网站外部的网站上Project Online代码</span><span class="sxs-lookup"><span data-stu-id="e219e-120">Code that exists on a site external to the Project Online site</span></span> 
  - <span data-ttu-id="e219e-121">外部网站，可以 (但不限于) ：</span><span class="sxs-lookup"><span data-stu-id="e219e-121">An external site, which can be (but is not limited to):</span></span>  
  - <span data-ttu-id="e219e-122">另SharePoint网站</span><span class="sxs-lookup"><span data-stu-id="e219e-122">Another SharePoint site</span></span>  
  - <span data-ttu-id="e219e-123">在任何平台上构建的 Web 应用/服务</span><span class="sxs-lookup"><span data-stu-id="e219e-123">Web App/Service built on any platform</span></span>  
  - <span data-ttu-id="e219e-124">外部网站包含业务逻辑</span><span class="sxs-lookup"><span data-stu-id="e219e-124">The external site contains business logic</span></span>  
  - <span data-ttu-id="e219e-125">浏览器将Project Online访问令牌重定向到外部Project Online</span><span class="sxs-lookup"><span data-stu-id="e219e-125">The browser is redirected from Project Online to external site with access tokens to Project Online</span></span>  
  - <span data-ttu-id="e219e-126">外部网站可以调用 SharePoint 和 Project Online</span><span class="sxs-lookup"><span data-stu-id="e219e-126">The external site can make calls to SharePoint and Project Online</span></span>
    
- <span data-ttu-id="e219e-127">对于外部/独立外接程序：</span><span class="sxs-lookup"><span data-stu-id="e219e-127">For an external/standalone add-in:</span></span>
    
  - <span data-ttu-id="e219e-128">用户在设备上执行应用程序</span><span class="sxs-lookup"><span data-stu-id="e219e-128">User executes an application on their device</span></span>
  - <span data-ttu-id="e219e-129">应用程序直接对 api Project Online进行身份验证和调用</span><span class="sxs-lookup"><span data-stu-id="e219e-129">Application authenticates and calls Project Online APIs directly</span></span>
    

|<span data-ttu-id="e219e-130">应用程序类型</span><span class="sxs-lookup"><span data-stu-id="e219e-130">Type of application</span></span>|<span data-ttu-id="e219e-131">API 实现</span><span class="sxs-lookup"><span data-stu-id="e219e-131">API implementation</span></span>|<span data-ttu-id="e219e-132">目标环境</span><span class="sxs-lookup"><span data-stu-id="e219e-132">Target environment</span></span>|<span data-ttu-id="e219e-133">应用程序示例</span><span class="sxs-lookup"><span data-stu-id="e219e-133">Application examples</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e219e-134">Project托管</span><span class="sxs-lookup"><span data-stu-id="e219e-134">Project hosted</span></span>  <br/> |<span data-ttu-id="e219e-135">JSOM (Java脚本对象模型) </span><span class="sxs-lookup"><span data-stu-id="e219e-135">JSOM (Java Script Object Model)</span></span>  <br/> <span data-ttu-id="e219e-136">REST</span><span class="sxs-lookup"><span data-stu-id="e219e-136">REST</span></span>  <br/> |<span data-ttu-id="e219e-137">浏览器</span><span class="sxs-lookup"><span data-stu-id="e219e-137">Browser</span></span>  <br/> |<span data-ttu-id="e219e-138">考勤卡条目</span><span class="sxs-lookup"><span data-stu-id="e219e-138">Timecard entry</span></span>  <br/> <span data-ttu-id="e219e-139">Timecard approval</span><span class="sxs-lookup"><span data-stu-id="e219e-139">Timecard approval</span></span>  <br/> <span data-ttu-id="e219e-140">项目状态</span><span class="sxs-lookup"><span data-stu-id="e219e-140">Project Status</span></span>  <br/> <span data-ttu-id="e219e-141">问题报告</span><span class="sxs-lookup"><span data-stu-id="e219e-141">Issues Report</span></span>  <br/> |
|<span data-ttu-id="e219e-142">Project提供程序托管</span><span class="sxs-lookup"><span data-stu-id="e219e-142">Project Provider Hosted</span></span>  <br/> |<span data-ttu-id="e219e-143">CSOM 客户端库</span><span class="sxs-lookup"><span data-stu-id="e219e-143">CSOM client library</span></span>  <br/> |<span data-ttu-id="e219e-144">Azure 网站/应用</span><span class="sxs-lookup"><span data-stu-id="e219e-144">Azure Website/App</span></span>  <br/> <span data-ttu-id="e219e-145">非Windows环境 (LAMP 等) </span><span class="sxs-lookup"><span data-stu-id="e219e-145">Non-Windows environment (LAMP, etc.)</span></span>  <br/> |<span data-ttu-id="e219e-146">外部时间表验证程序</span><span class="sxs-lookup"><span data-stu-id="e219e-146">External timesheet validator</span></span>  <br/> <span data-ttu-id="e219e-147">Project导入程序</span><span class="sxs-lookup"><span data-stu-id="e219e-147">Project Importer</span></span>  <br/> |
|<span data-ttu-id="e219e-148">外部/独立</span><span class="sxs-lookup"><span data-stu-id="e219e-148">External/Standalone</span></span>  <br/> |<span data-ttu-id="e219e-149">REST</span><span class="sxs-lookup"><span data-stu-id="e219e-149">REST</span></span>  <br/> <span data-ttu-id="e219e-150">CSOM</span><span class="sxs-lookup"><span data-stu-id="e219e-150">CSOM</span></span>  <br/> |<span data-ttu-id="e219e-151">REST - 任何平台</span><span class="sxs-lookup"><span data-stu-id="e219e-151">REST - any platform</span></span>  <br/> <span data-ttu-id="e219e-152">CSOM - 任何 .NET 支持的平台</span><span class="sxs-lookup"><span data-stu-id="e219e-152">CSOM - any .NET supported platform</span></span>  <br/> |<span data-ttu-id="e219e-153">考勤卡条目</span><span class="sxs-lookup"><span data-stu-id="e219e-153">Timecard entry</span></span>  <br/> <span data-ttu-id="e219e-154">将项目迁移到新网站</span><span class="sxs-lookup"><span data-stu-id="e219e-154">Migration of projects to a new site</span></span>  <br/> <span data-ttu-id="e219e-155">更改管理状态。</span><span class="sxs-lookup"><span data-stu-id="e219e-155">Change Management Status.</span></span>  <br/> |
   
## <a name="what-does-it-take-to-start-developing-applications-for-project-online"></a><span data-ttu-id="e219e-156">开始为应用程序开发应用程序需要哪些Project Online？</span><span class="sxs-lookup"><span data-stu-id="e219e-156">What does it take to start developing applications for Project Online?</span></span>

<span data-ttu-id="e219e-157">开发应用程序所需的常见项目Project Online帐户和测试数据Project Online包括工作分配、任务、资源和自定义域的项目及项目相关信息。</span><span class="sxs-lookup"><span data-stu-id="e219e-157">The common items needed for developing Project Online applications are a Project Online account and test data--projects and project-related information that include assignments, tasks, resources, and custom fields.</span></span> <span data-ttu-id="e219e-158">还需要开发环境，但开发环境的具体内容取决于应用程序的类型和应用程序所需的 API 接口。</span><span class="sxs-lookup"><span data-stu-id="e219e-158">A development environment is needed as well, but specifics of the development environment depend on the type of application and the API interface needed for the application.</span></span> <span data-ttu-id="e219e-159">接下来的几节介绍了三个 API 接口的开发需求。</span><span class="sxs-lookup"><span data-stu-id="e219e-159">The next few sections describe development needs for the three API interfaces.</span></span>
  
<span data-ttu-id="e219e-160">参考文档介绍了这三个接口通用的对象模型，以及显示对象模型组件之间的关系的实体映射。</span><span class="sxs-lookup"><span data-stu-id="e219e-160">The reference documentation describes the object model that is common for all three interfaces, as well as an entity map that shows relations among the object model components.</span></span>
  
## <a name="project-hosted-add-in-development-environment"></a><span data-ttu-id="e219e-161">Project托管的外接程序开发环境</span><span class="sxs-lookup"><span data-stu-id="e219e-161">Project hosted add-in development environment</span></span>

<span data-ttu-id="e219e-162">托管加载项是驻留在服务器上并下载到浏览器进行运行时执行的加载项。</span><span class="sxs-lookup"><span data-stu-id="e219e-162">A hosted add-in is an add-in that resides on the server and is downloaded to a browser for runtime execution.</span></span> <span data-ttu-id="e219e-163">托管加载项可以使用 JSOM 或 REST 接口，并且使用 JavaScript 编写。</span><span class="sxs-lookup"><span data-stu-id="e219e-163">Hosted add-ins can use the JSOM or REST interfaces and are written in JavaScript.</span></span> <span data-ttu-id="e219e-164">Project Online为运行时执行提供对 JSOM 库的引用。</span><span class="sxs-lookup"><span data-stu-id="e219e-164">Project Online provides references to the JSOM library for runtime execution.</span></span> <span data-ttu-id="e219e-165">假设开发在Windows上，则所需的资源如下：</span><span class="sxs-lookup"><span data-stu-id="e219e-165">Assuming development is on a Windows platform, the needed resources follow:</span></span>
  
- <span data-ttu-id="e219e-166">Visual Studio 2015 (首选) 或 Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="e219e-166">Visual Studio 2015 (preferred) or Visual Studio 2013</span></span>
    
- <span data-ttu-id="e219e-167">Office开发工具Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e219e-167">Office development tools for Visual Studio</span></span>
    
- <span data-ttu-id="e219e-168">JavaScript 语言</span><span class="sxs-lookup"><span data-stu-id="e219e-168">JavaScript language</span></span>
    
<span data-ttu-id="e219e-169">有关 https://github.com/OfficeDev/Project-JSOM-Copy-Work-Packages 示例应用程序，请访问 。</span><span class="sxs-lookup"><span data-stu-id="e219e-169">Visit https://github.com/OfficeDev/Project-JSOM-Copy-Work-Packages for a sample application.</span></span> 
  
<span data-ttu-id="e219e-170">可以通过几个简单的步骤下载并运行示例：</span><span class="sxs-lookup"><span data-stu-id="e219e-170">You can download and run the sample in a few easy steps:</span></span>
  
1. <span data-ttu-id="e219e-171">下载并打开示例应用程序</span><span class="sxs-lookup"><span data-stu-id="e219e-171">Download and open the sample application</span></span>
    
2. <span data-ttu-id="e219e-172">在"属性"窗口中更新 SiteURL</span><span class="sxs-lookup"><span data-stu-id="e219e-172">Update the SiteURL in the Properties window</span></span>
    
   <span data-ttu-id="e219e-173">Project Online检查加载项的应用程序范围以及管理对加载项主机上信息的访问Project Online权限。</span><span class="sxs-lookup"><span data-stu-id="e219e-173">Project Online examines both the application scope of the add-in and the user permissions to govern access to information on the Project Online host.</span></span> <span data-ttu-id="e219e-174">如果在任一设置或两种设置中都明确拒绝访问，Project Online拒绝访问该信息。</span><span class="sxs-lookup"><span data-stu-id="e219e-174">If access is explicitly denied in either or both settings, Project Online denies access to the information.</span></span> <span data-ttu-id="e219e-175">否则，将授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="e219e-175">Otherwise, access is granted.</span></span>
    
3. <span data-ttu-id="e219e-176">在你的 [网站上启用](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins) 旁加载。</span><span class="sxs-lookup"><span data-stu-id="e219e-176">Enable [sideloading](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins) on your site.</span></span>  
    
4. <span data-ttu-id="e219e-177">生成项目。</span><span class="sxs-lookup"><span data-stu-id="e219e-177">Build the project.</span></span>
    
5. <span data-ttu-id="e219e-178">运行项目。</span><span class="sxs-lookup"><span data-stu-id="e219e-178">Run the project.</span></span>
    
## <a name="project-provider-hosted-add-in-development-environment"></a><span data-ttu-id="e219e-179">Project提供程序托管的外接程序开发环境</span><span class="sxs-lookup"><span data-stu-id="e219e-179">Project provider-hosted add-in development environment</span></span>

<span data-ttu-id="e219e-180">提供程序托管的外接程序是在任何 Web 平台上编写和驻留的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e219e-180">Provider hosted add-ins are applications written and residing on any web platform.</span></span> <span data-ttu-id="e219e-181">他们可以使用适用于 Microsoft 平台和 API 的 REST (CSOM 连接并执行) 操作。</span><span class="sxs-lookup"><span data-stu-id="e219e-181">They can connect and perform data operations using the REST (or CSOM for Microsoft platforms) API.</span></span> <span data-ttu-id="e219e-182">支持 REST 接口的任何语言和环境都可用于开发。</span><span class="sxs-lookup"><span data-stu-id="e219e-182">Any language and environment that supports the REST interface can be used for development.</span></span> 
  
<span data-ttu-id="e219e-183">此类型的Windows开发环境的示例包括以下项目：</span><span class="sxs-lookup"><span data-stu-id="e219e-183">An example of the Windows development environment for this type of application includes the following items:</span></span>
  
-  <span data-ttu-id="e219e-184">Visual Studio 2015 (首选) 或 Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="e219e-184">Visual Studio 2015 (preferred) or Visual Studio 2013</span></span> 
    
- <span data-ttu-id="e219e-185">Microsoft OfficeVisual Studio (2015 Visual Studio 2015 Professional 和 Enterprise 版本) </span><span class="sxs-lookup"><span data-stu-id="e219e-185">Microsoft Office Development Tools for Visual Studio (supplied with Visual Studio 2015 Professional and Enterprise editions)</span></span>
    
- <span data-ttu-id="e219e-186">.NET Framework 4.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e219e-186">.NET Framework 4.0 or newer</span></span>
    
- <span data-ttu-id="e219e-187">[用于 CSOM 调用 (SharePointOnline](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM) CSOM) </span><span class="sxs-lookup"><span data-stu-id="e219e-187">[SharePointOnline CSOM package](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM) (for CSOM calls)</span></span> 
    
- <span data-ttu-id="e219e-188">编程语言，如 C#</span><span class="sxs-lookup"><span data-stu-id="e219e-188">A programming language, such as C#</span></span> 
    
<span data-ttu-id="e219e-189">请访问 https://github.com/OfficeDev/Project-Add-in-REST-BasicDataOperations ，以使用示例脚本。</span><span class="sxs-lookup"><span data-stu-id="e219e-189">Visit https://github.com/OfficeDev/Project-Add-in-REST-BasicDataOperations for working sample scripts.</span></span> 
  
<span data-ttu-id="e219e-190">可以通过几个步骤运行示例：</span><span class="sxs-lookup"><span data-stu-id="e219e-190">You can run the sample in a few steps:</span></span>
  
1. <span data-ttu-id="e219e-191">下载并打开示例应用程序</span><span class="sxs-lookup"><span data-stu-id="e219e-191">Download and open the sample application</span></span>
    
2. <span data-ttu-id="e219e-192">在"属性"窗口中更新 SiteURL</span><span class="sxs-lookup"><span data-stu-id="e219e-192">Update the SiteURL in the Properties window</span></span>
    
   <span data-ttu-id="e219e-193">Project Online检查加载项的应用程序范围以及管理对加载项主机上信息的访问Project Online权限。</span><span class="sxs-lookup"><span data-stu-id="e219e-193">Project Online examines both the application scope of the add-in and the user permissions to govern access to information on the Project Online host.</span></span> <span data-ttu-id="e219e-194">如果在任一设置或两种设置中都明确拒绝访问，Project Online拒绝访问该信息。</span><span class="sxs-lookup"><span data-stu-id="e219e-194">If access is explicitly denied in either or both settings, Project Online denies access to the information.</span></span> <span data-ttu-id="e219e-195">否则，将授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="e219e-195">Otherwise, access is granted.</span></span>
    
3. <span data-ttu-id="e219e-196">在你的 [网站上启用](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins) 旁加载。</span><span class="sxs-lookup"><span data-stu-id="e219e-196">Enable [sideloading](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins) on your site.</span></span> 
    
4. <span data-ttu-id="e219e-197">生成项目。</span><span class="sxs-lookup"><span data-stu-id="e219e-197">Build the project.</span></span>
    
5. <span data-ttu-id="e219e-198">运行项目。</span><span class="sxs-lookup"><span data-stu-id="e219e-198">Run the project.</span></span>
    
## <a name="externalstandalone-application-development-environment"></a><span data-ttu-id="e219e-199">外部/独立应用程序开发环境</span><span class="sxs-lookup"><span data-stu-id="e219e-199">External/standalone application development environment</span></span>

<span data-ttu-id="e219e-200">独立应用程序可以使用客户端对象模型 (CSOM) 或 REST 调用 Project Online 以与 Project Online 通信，以创建、检索、更新和删除驻留在服务器上的信息。</span><span class="sxs-lookup"><span data-stu-id="e219e-200">A standalone application can call Project Online using the Client Side Object Model (CSOM) or REST to communicate with Project Online to create, retrieve, update, and delete information residing on the server.</span></span> <span data-ttu-id="e219e-201">这是一个独立的客户端应用程序，它依赖于要运行的用户访问级别。</span><span class="sxs-lookup"><span data-stu-id="e219e-201">This is a standalone client application that depends on the user access level to run.</span></span> 
  
<span data-ttu-id="e219e-202">此类型的Windows开发环境的示例包括以下项目：</span><span class="sxs-lookup"><span data-stu-id="e219e-202">An example of the Windows development environment for this type of application includes the following items:</span></span>
  
- <span data-ttu-id="e219e-203">Visual Studio 2015 (首选) 或 Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="e219e-203">Visual Studio 2015 (preferred) or Visual Studio 2013</span></span> 
    
- <span data-ttu-id="e219e-204">Microsoft OfficeVisual Studio (2015 Visual Studio 2015 Professional 和 Enterprise 版本) </span><span class="sxs-lookup"><span data-stu-id="e219e-204">Microsoft Office Development Tools for Visual Studio (supplied with Visual Studio 2015 Professional and Enterprise editions)</span></span>
    
- <span data-ttu-id="e219e-205">.NET Framework 4.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e219e-205">.NET Framework 4.0 or newer</span></span>
    
- <span data-ttu-id="e219e-206">[用于 CSOM 调用 (SharePointOnline](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM) CSOM) </span><span class="sxs-lookup"><span data-stu-id="e219e-206">[SharePointOnline CSOM package](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM) (for CSOM calls)</span></span> 
    
- <span data-ttu-id="e219e-207">编程语言，如 C#</span><span class="sxs-lookup"><span data-stu-id="e219e-207">A programming language, such as C#</span></span> 
    
<span data-ttu-id="e219e-208">有关 https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields 示例应用程序，请访问 。</span><span class="sxs-lookup"><span data-stu-id="e219e-208">Visit https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields for a sample application.</span></span> 
  
<span data-ttu-id="e219e-209">可以通过几个步骤运行示例：</span><span class="sxs-lookup"><span data-stu-id="e219e-209">You can run the sample in a few steps:</span></span>
  
1. <span data-ttu-id="e219e-210">下载示例应用程序</span><span class="sxs-lookup"><span data-stu-id="e219e-210">Download the sample application</span></span>
    
2. <span data-ttu-id="e219e-211">进行一些更改以访问Project Online网站- 网站名称、用户帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="e219e-211">Make a couple of changes to access your Project Online site—the site name, user account, and password.</span></span>
    
   <span data-ttu-id="e219e-212">确保用户有权访问所有项目。</span><span class="sxs-lookup"><span data-stu-id="e219e-212">Ensure the user has access to all projects.</span></span> <span data-ttu-id="e219e-213">Project Online使用用户权限来管理对数据存储中信息的访问。</span><span class="sxs-lookup"><span data-stu-id="e219e-213">Project Online uses user permissions to govern access to information in the data store.</span></span>
    
3. <span data-ttu-id="e219e-214">使用SharePoint Nuget 程序包管理器控制台（通过在 Nuget 控制台中键入以下内容从"工具"菜单提供）将程序集添加到引用中：</span><span class="sxs-lookup"><span data-stu-id="e219e-214">Add the SharePoint assembly to the references using the Nuget Package Manager Console, available from the Tools menu by typing the following in the Nuget console:</span></span> 
    
   `Install-Package Microsoft.SharePointOnline.CSOM`

4. <span data-ttu-id="e219e-215">生成项目。</span><span class="sxs-lookup"><span data-stu-id="e219e-215">Build the project.</span></span>
    
5. <span data-ttu-id="e219e-216">运行项目。</span><span class="sxs-lookup"><span data-stu-id="e219e-216">Run the project.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="e219e-217">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e219e-217">Next steps</span></span>

<span data-ttu-id="e219e-218">每个示例应用程序都有一篇文章，解释使用单个应用程序 API 的Project点。</span><span class="sxs-lookup"><span data-stu-id="e219e-218">Each sample application has an article to explain the highlights of working with the individual Project API.</span></span> <span data-ttu-id="e219e-219">这些文章显示在以下列表中，以及介绍实体关系、查询系统信息和访问自定义字段的一些文章。</span><span class="sxs-lookup"><span data-stu-id="e219e-219">The articles appear in the following list, along with a few articles that describe the entity relationships, information on the query system, and accessing Custom Fields.</span></span> 
  
- [<span data-ttu-id="e219e-220">使用Project Online对象模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="e219e-220">Developing a Project Online Application Using the Client-side Object Model</span></span>](developing-a-project-online-application-using-the-client-side-object-model.md)
    
- [<span data-ttu-id="e219e-221">使用 JAVAScript Project Online JSOM 模型开发 (加载项) </span><span class="sxs-lookup"><span data-stu-id="e219e-221">Developing a Project Online add-in using the JavaScript Object Model (JSOM)</span></span>](developing-a-project-online-add-in-using-the-javascript-object-model-jsom.md)
    
- [<span data-ttu-id="e219e-222">访问 Project Online 企业自定义字段</span><span class="sxs-lookup"><span data-stu-id="e219e-222">Accessing Project Online enterprise custom fields</span></span>](accessing-project-online-enterprise-custom-fields.md)
    
## <a name="see-also"></a><span data-ttu-id="e219e-223">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e219e-223">See also</span></span>

<span data-ttu-id="e219e-224">有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/en-us/project)。</span><span class="sxs-lookup"><span data-stu-id="e219e-224">For documentation and samples related to Project Online and application development using CSOM, see the [Project Development Portal](https://developer.microsoft.com/en-us/project).</span></span>
    

