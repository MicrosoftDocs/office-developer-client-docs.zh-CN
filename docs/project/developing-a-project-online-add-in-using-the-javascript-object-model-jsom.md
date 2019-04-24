---
title: 使用 JavaScript 对象模型 (JSOM) 开发 Project Online 外接
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4a4b1ad2-de46-421d-a698-53c20c90b93a
description: 本文介绍 Microsoft project online 外接程序开发, 以增强你对 Project online 的体验。 开发项目作为演练实现。 用于本文的外接程序从 project Online 帐户读取和显示已发布项目的项目名称和 id, 并允许您向下钻取以检索与单个项目相关联的任务。
ms.openlocfilehash: 0a472a6300f18aaa65649f44d944445642a59e1a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322682"
---
# <a name="developing-a-project-online-add-in-using-the-javascript-object-model-jsom"></a><span data-ttu-id="15a67-105">使用 JavaScript 对象模型 (JSOM) 开发 Project Online 外接</span><span class="sxs-lookup"><span data-stu-id="15a67-105">Developing a Project Online add-in using the JavaScript Object Model (JSOM)</span></span>

<span data-ttu-id="15a67-106">本文介绍 Microsoft project online 外接程序开发, 以增强你对 Project online 的体验。</span><span class="sxs-lookup"><span data-stu-id="15a67-106">This article describes Microsoft Project Online Add-in development to enhance your experience with the Project Online.</span></span> <span data-ttu-id="15a67-107">开发项目作为演练实现。</span><span class="sxs-lookup"><span data-stu-id="15a67-107">The development project is implemented as a walkthrough.</span></span> <span data-ttu-id="15a67-108">用于本文的外接程序从 project Online 帐户读取和显示已发布项目的项目名称和 id, 并允许您向下钻取以检索与单个项目相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="15a67-108">The add-in used for this article reads and displays the project names and IDs of the published projects from your Project Online account and allows you to drill down to retrieve tasks associated with individual projects.</span></span>
  
<span data-ttu-id="15a67-109">在运行时, 外接列表类似于下图:</span><span class="sxs-lookup"><span data-stu-id="15a67-109">At run time, the add-in listing looks similar to the following illustration:</span></span>
  
<span data-ttu-id="15a67-110">![显示 JSOM 项目和任务列表的屏幕截图](media/766e5914-f048-48f4-9282-291f55e6e90d.png "显示 JSOM 项目和任务列表的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="15a67-110">![Screen shot showing a listing of JSOM projects and tasks](media/766e5914-f048-48f4-9282-291f55e6e90d.png "Screen shot showing a listing of JSOM projects and tasks")</span></span>
  
<span data-ttu-id="15a67-111">此示例的重点是与 Project Online 的交互, 使查询和为服务中的每个请求设置上下文。</span><span class="sxs-lookup"><span data-stu-id="15a67-111">The focus of the example is the interaction with the Project Online, making queries and setting the context for each request from the service.</span></span> <span data-ttu-id="15a67-112">用户界面 (UI) 元素获得最少的注意。</span><span class="sxs-lookup"><span data-stu-id="15a67-112">User interface (UI) elements receive minimal attention.</span></span> <span data-ttu-id="15a67-113">相反, 源列表提供有关 UI 的注释。</span><span class="sxs-lookup"><span data-stu-id="15a67-113">Instead, the source listings provide comments regarding the UI.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15a67-114">可从以下https://github.com/OfficeDev/Project-JSOM-List-Projects-Tasks....位置获取示例外接程序 (一个 Visual Studio 项目) 的源文件。</span><span class="sxs-lookup"><span data-stu-id="15a67-114">The source files for the example add-in, a Visual Studio project, are available at: https://github.com/OfficeDev/Project-JSOM-List-Projects-Tasks.....</span></span> <span data-ttu-id="15a67-115">阅读本文时, 请务必将源文件作为参考, 因为每个文件都要补充另一个文件。</span><span class="sxs-lookup"><span data-stu-id="15a67-115">Keep the source files handy as a reference while you read the article, as each complements the other.</span></span> <span data-ttu-id="15a67-116">Visual Studio 项目中的文件以最少的更改生成并为可执行文件—将 project Online 租户的 URL 向下替换到 PWA 文件夹。</span><span class="sxs-lookup"><span data-stu-id="15a67-116">The files in the Visual Studio project build and are executable with minimal changes—substituting the URL for your Project Online tenant down to the PWA folder.</span></span> 
  
## <a name="background"></a><span data-ttu-id="15a67-117">背景</span><span class="sxs-lookup"><span data-stu-id="15a67-117">Background</span></span>

<span data-ttu-id="15a67-118">Project Online 是一种 Office 365 服务, 它为公司提供了项目组合管理 (PPM) 和项目管理办公室 (PMO) 解决方案, 以协调和管理项目组合、程序和项目。</span><span class="sxs-lookup"><span data-stu-id="15a67-118">Project Online is a Office 365 service that provides companies with a project portfolio management (PPM) and project management office (PMO) solution to coordinate and manage portfolios, programs, and projects.</span></span> <span data-ttu-id="15a67-119">project Online 与 project desktop 版本是不同的解决方案;然而, project Online 仍包含在项目的整个生命周期中维护和跟踪项目详细信息的功能。</span><span class="sxs-lookup"><span data-stu-id="15a67-119">Project Online is a different offering than the Project desktop editions; yet, Project Online still contains the functionality to maintain and track project details throughout the life of a project.</span></span> <span data-ttu-id="15a67-120">Project online 是基于 SharePoint Online 建立的。</span><span class="sxs-lookup"><span data-stu-id="15a67-120">Project Online is built on SharePoint Online.</span></span>
  
<span data-ttu-id="15a67-121">Project Online 托管加载项由与客户端对象模型 API 交互的 JavaScript 和资源文件组成。</span><span class="sxs-lookup"><span data-stu-id="15a67-121">A Project Online hosted add-in consists of JavaScript and resource files that interact with the Client-Side-Object-Model API.</span></span> <span data-ttu-id="15a67-122">当用户访问加载项时, JavaScript 和资源将下载并在浏览器中执行。</span><span class="sxs-lookup"><span data-stu-id="15a67-122">When the user visits the add-in, the JavaScript and resources are downloaded and executed within the browser.</span></span> <span data-ttu-id="15a67-123">加载项进行异步调用 Project Online, 以与服务进行交互, 无论是创建、检索、更新还是删除数据。</span><span class="sxs-lookup"><span data-stu-id="15a67-123">The add-In makes asynchronous calls to Project Online to interact with the service, whether creating, retrieving, updating, or deleting data.</span></span> 
  
<span data-ttu-id="15a67-124">Project Online 执行另一个操作来保护属于来自外接程序的其他租户的信息;即, Project Online 将创建一个独立的网站, 以与外接程序中的请求进行交互。</span><span class="sxs-lookup"><span data-stu-id="15a67-124">Project Online performs one more action to protect information that belongs to other tenants from the add-in; namely, Project Online creates an isolated site to interact with the requests from the add-in.</span></span> <span data-ttu-id="15a67-125">不会在 Project Online 主机上运行任何自定义代码。</span><span class="sxs-lookup"><span data-stu-id="15a67-125">No custom code runs on the Project Online host.</span></span> 
  
<span data-ttu-id="15a67-126">Project Online 外接程序的开发设置使用 Visual Studio SharePoint 外接程序项目类型。</span><span class="sxs-lookup"><span data-stu-id="15a67-126">The development setup for Project Online add-ins uses the Visual Studio SharePoint Add-in project type.</span></span> <span data-ttu-id="15a67-127">加载项以 JavaScript 的方式编写, 并使用项目 JavaScript 对象模型 (JSOM) 与 project Online service 进行交互。</span><span class="sxs-lookup"><span data-stu-id="15a67-127">The add-in is written in JavaScript, and uses the Project JavaScript object model (JSOM) to interact with the Project Online service.</span></span> <span data-ttu-id="15a67-128">JSOM 从 SharePoint JSOM 继承了大部分功能。</span><span class="sxs-lookup"><span data-stu-id="15a67-128">The JSOM inherits much of its functionality from the SharePoint JSOM.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15a67-129">可以在 Office 应用商店中发布和销售外接程序, 也可以将其部署到 SharePoint 上的专用应用程序目录中。</span><span class="sxs-lookup"><span data-stu-id="15a67-129">Add-ins can be published and sold in the Office Store or deployed to a private app catalog on SharePoint.</span></span> <span data-ttu-id="15a67-130">有关详细信息, 请参阅[部署和发布 Office 外接程序](https://docs.microsoft.com/office/dev/add-ins/publish/publish)。</span><span class="sxs-lookup"><span data-stu-id="15a67-130">For more information, see [Deploy and publish your Office Add-in](https://docs.microsoft.com/office/dev/add-ins/publish/publish).</span></span>
> 
> <span data-ttu-id="15a67-131">本文中使用的外接程序是开发人员的示例;它不应在生产环境中使用。</span><span class="sxs-lookup"><span data-stu-id="15a67-131">The add-in used in this article is a sample for developers; it is not intended for use in a production environment.</span></span> <span data-ttu-id="15a67-132">主要目的是显示 Project Online 应用程序开发的一个示例。</span><span class="sxs-lookup"><span data-stu-id="15a67-132">The primary purpose is to show an example of app development for Project Online.</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="15a67-133">先决条件</span><span class="sxs-lookup"><span data-stu-id="15a67-133">Prerequisites</span></span>

<span data-ttu-id="15a67-134">将以下项添加到受支持的 Windows 环境:</span><span class="sxs-lookup"><span data-stu-id="15a67-134">Add the following items to a supported Windows environment:</span></span>
  
- <span data-ttu-id="15a67-135">**.net Framework 4.0 或更高**版本: 版本4.0 中的 Framework 的完整版本是兼容的。</span><span class="sxs-lookup"><span data-stu-id="15a67-135">**.NET Framework 4.0 or later**: Complete versions of the framework from version 4.0 are compatible.</span></span> <span data-ttu-id="15a67-136">下载网站为 https://msdn.microsoft.com/vstudio/aa496123.aspx。</span><span class="sxs-lookup"><span data-stu-id="15a67-136">The download site is https://msdn.microsoft.com/vstudio/aa496123.aspx.</span></span>
    
- <span data-ttu-id="15a67-137">**Visual Studio 2013 或更高版本**:</span><span class="sxs-lookup"><span data-stu-id="15a67-137">**Visual Studio 2013 or later**:</span></span>  
    
   - <span data-ttu-id="15a67-138">Visual Studio 2015 专业版已准备就绪, 可在https://www.visualstudio.com/en-us/products/visual-studio-professional-with-msdn-vs.aspx中找到。</span><span class="sxs-lookup"><span data-stu-id="15a67-138">The professional edition of Visual Studio 2015 is ready to go out-of-the box and is available at https://www.visualstudio.com/en-us/products/visual-studio-professional-with-msdn-vs.aspx.</span></span>
    
   - <span data-ttu-id="15a67-139">可从https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx获取 Visual Studio 2015 的社区版。</span><span class="sxs-lookup"><span data-stu-id="15a67-139">The community edition of Visual Studio 2015 is available at https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx.</span></span> <span data-ttu-id="15a67-140">此版本需要手动安装适用于 Visual Studio 的 Microsoft Office 开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="15a67-140">This edition requires manual installation of the Microsoft Office Developer Tools for Visual Studio.</span></span>
    
   <span data-ttu-id="15a67-141">中提供了适用于 Visual Studio 的 Microsoft Office 开发https://www.visualstudio.com/en-us/features/office-tools-vs.aspx人员工具。</span><span class="sxs-lookup"><span data-stu-id="15a67-141">The Microsoft Office Developer Tools for Visual Studio are available at https://www.visualstudio.com/en-us/features/office-tools-vs.aspx.</span></span>
    
- <span data-ttu-id="15a67-142">**Project Online 帐户**: 它提供对托管服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="15a67-142">**A Project Online account**: This provides access to the hosting service.</span></span> <span data-ttu-id="15a67-143">有关获取 Project Online 帐户的详细信息，请参阅 https://products.office.com/en-us/Project/project-online-portfolio-management</span><span class="sxs-lookup"><span data-stu-id="15a67-143">For more information about obtaining a Project Online account, see https://products.office.com/en-us/Project/project-online-portfolio-management.</span></span>
    
   <span data-ttu-id="15a67-144">确保加载项用户具有足够的权限来访问 Project Online 租户中的某些项目。</span><span class="sxs-lookup"><span data-stu-id="15a67-144">Ensure that the add-in user has sufficient authorization to access some projects in the Project Online tenant.</span></span> 
    
- <span data-ttu-id="15a67-145">**托管网站上**使用信息填充的项目。</span><span class="sxs-lookup"><span data-stu-id="15a67-145">**Projects on the hosting site** that are populated with information.</span></span>
    
> [!NOTE]
> <span data-ttu-id="15a67-146">标准 .net Framework 是要使用的正确框架。</span><span class="sxs-lookup"><span data-stu-id="15a67-146">The standard .NET Framework is the correct framework to use.</span></span> <span data-ttu-id="15a67-147">请勿使用 ".net Framework 4 客户端配置文件"。</span><span class="sxs-lookup"><span data-stu-id="15a67-147">Do not use the ".NET Framework 4 Client Profile".</span></span> 
  
### <a name="set-up-the-visual-studio-project"></a><span data-ttu-id="15a67-148">设置 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="15a67-148">Set up the Visual Studio project</span></span>

<span data-ttu-id="15a67-149">应用程序安装程序由创建新项目、链接适当的库和声明所需的命名空间组成。</span><span class="sxs-lookup"><span data-stu-id="15a67-149">The application setup consists of creating a new project, linking the appropriate libraries and declaring the needed namespaces.</span></span> <span data-ttu-id="15a67-150">Visual Studio 提供有多种类型的开发项目。</span><span class="sxs-lookup"><span data-stu-id="15a67-150">Visual Studio presents several types of development projects.</span></span> <span data-ttu-id="15a67-151">该部分是简短且非常基本的部分。</span><span class="sxs-lookup"><span data-stu-id="15a67-151">The section is brief and very basic.</span></span> <span data-ttu-id="15a67-152">值是将信息合并到一个位置。</span><span class="sxs-lookup"><span data-stu-id="15a67-152">The value is having the information is coalesced in one place.</span></span>
  
#### <a name="select-a-visual-studio-project"></a><span data-ttu-id="15a67-153">选择 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="15a67-153">Select a Visual Studio project</span></span>

<span data-ttu-id="15a67-154">若要为外接程序创建适当类型的项目, 您必须执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="15a67-154">To create a project of the appropriate type for the add-in, you must do the following steps.</span></span> <span data-ttu-id="15a67-155">在屏幕上遇到的关键字具有**bold**属性:</span><span class="sxs-lookup"><span data-stu-id="15a67-155">Keywords encountered on the screen have a **bold** attribute:</span></span> 
  
1. <span data-ttu-id="15a67-156">从 "文件" 菜单中选择 "**文件** > " "**新建** > **项目**"。</span><span class="sxs-lookup"><span data-stu-id="15a67-156">From the File menu, choose **File** > **New** > **Project**.</span></span> 
    
2. <span data-ttu-id="15a67-157">从左侧窗格中的 "已安装的模板" 中, 选择 " **c #** > **Office/SharePoint** > **Web 外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="15a67-157">From the Installed templates in the left pane, select **C#** > **Office/SharePoint** > **Web Add-ins**.</span></span> 
    
3. <span data-ttu-id="15a67-158">在中央窗格顶部, 选择 " **.net Framework 4** " 或 "更高版本";当前版本是4.6。</span><span class="sxs-lookup"><span data-stu-id="15a67-158">At the top of the central pane, select **.NET Framework 4** or later; the current version is 4.6.</span></span> 
    
4. <span data-ttu-id="15a67-159">从中央窗格中的应用程序类型中, 选择 " **SharePoint 外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="15a67-159">From the application types in the central pane, choose **SharePoint Add-in**.</span></span> 
    
5. <span data-ttu-id="15a67-160">在底部为项目指定名称和位置以及解决方案名称。</span><span class="sxs-lookup"><span data-stu-id="15a67-160">In the bottom section, specify a name and location for the project, and a solution name.</span></span> 
    
6. <span data-ttu-id="15a67-161">此外，在底部选中“**创建解决方案的目录**”复选框。</span><span class="sxs-lookup"><span data-stu-id="15a67-161">Also in the bottom section, check the **Create directory for solution** box.</span></span> 
    
7. <span data-ttu-id="15a67-162">单击“**确定**”以创建初始项目。</span><span class="sxs-lookup"><span data-stu-id="15a67-162">Click **OK** to create the initial project.</span></span> 
    
<span data-ttu-id="15a67-163">Visual Studio 向导会在下面几个对话框中询问有关 Project Online 设置网站的几个后续问题 (在对话框中称为 "SharePoint 设置")。</span><span class="sxs-lookup"><span data-stu-id="15a67-163">The Visual Studio Wizard asks a few follow-up questions about the Project Online settings site (called SharePoint settings in the dialogs) in a couple of dialogs that follow.</span></span> <span data-ttu-id="15a67-164">以下是问题:</span><span class="sxs-lookup"><span data-stu-id="15a67-164">Here are the questions:</span></span>
  
1. <span data-ttu-id="15a67-165">您要使用哪个 SharePoint 网站调试外接程序？</span><span class="sxs-lookup"><span data-stu-id="15a67-165">What SharePoint site do you want to use for debugging your add-in?</span></span> <span data-ttu-id="15a67-166">指定 PWA 网站的 URL, 例如https://contoso.sharepoint.com/sites/pwa。</span><span class="sxs-lookup"><span data-stu-id="15a67-166">Specify the URL to your PWA site, such as https://contoso.sharepoint.com/sites/pwa.</span></span>
    
2. <span data-ttu-id="15a67-167">你希望如何托管 SharePoint 外接程序？</span><span class="sxs-lookup"><span data-stu-id="15a67-167">How do you want to host your SharePoint Add-in?</span></span> <span data-ttu-id="15a67-168">选择 "[X] **SharePoint 托管**"。</span><span class="sxs-lookup"><span data-stu-id="15a67-168">Choose [X] **SharePoint-hosted**.</span></span>
    
   <span data-ttu-id="15a67-169">有关 SharePoint 外接程序 (包括托管选项) 的详细信息, 请参阅[SharePoint 外接程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="15a67-169">For more information about SharePoint Add-ins, including hosting options, see [SharePoint Add-ins](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins).</span></span>
    
3. <span data-ttu-id="15a67-170">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="15a67-170">Click **Next**.</span></span> 
    
<span data-ttu-id="15a67-171">第二个附加对话框要求您为外接程序指定 SharePoint Online 版本:</span><span class="sxs-lookup"><span data-stu-id="15a67-171">The second additional dialog asks you to specify the SharePoint Online version for the add-in:</span></span> 
  
1. <span data-ttu-id="15a67-172">您希望外接程序定位的最早版本的 SharePoint 是什么？</span><span class="sxs-lookup"><span data-stu-id="15a67-172">What's the earliest version of SharePoint that you want your add-in to target?</span></span> <span data-ttu-id="15a67-173">选择 [X] S **harePoint-Online**。</span><span class="sxs-lookup"><span data-stu-id="15a67-173">Choose [X] S **harePoint-Online**.</span></span> 
    
2. <span data-ttu-id="15a67-174">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="15a67-174">Click **Finish**.</span></span> 
    
<span data-ttu-id="15a67-175">Visual Studio 将创建项目并访问 project Online 网站。</span><span class="sxs-lookup"><span data-stu-id="15a67-175">Visual Studio creates the project and accesses the Project Online site.</span></span> 
  
### <a name="enable-sideloading-on-the-project-online-site"></a><span data-ttu-id="15a67-176">在 Project Online 网站上启用旁加载</span><span class="sxs-lookup"><span data-stu-id="15a67-176">Enable sideloading on the Project Online site</span></span>

<span data-ttu-id="15a67-177">旁加载是用于测试和调试 Project Online 外接程序的机制。您需要有两个用于旁加载的脚本: 一个用于在 Project Online 网站上启用旁加载, 另一个用于在完成测试和调试外接程序后禁用旁加载。</span><span class="sxs-lookup"><span data-stu-id="15a67-177">Sideloading is the mechanism for testing and debugging Project Online add-ins. You need two scripts for sideloading: one to enable sideloading on your Project Online site and another to disable sideloading once you finish testing and debugging the add-in.</span></span>
  
<span data-ttu-id="15a67-178">有关设置旁加载的详细信息, 请参阅[在非开发人员网站集中启用应用程序旁加载](https://blogs.msdn.microsoft.com/officeapps/2013/12/10/enable-app-sideloading-in-your-non-developer-site-collection/)。</span><span class="sxs-lookup"><span data-stu-id="15a67-178">For more information about setting up sideloading, see [Enable app SideLoading in your non-developer site collection](https://blogs.msdn.microsoft.com/officeapps/2013/12/10/enable-app-sideloading-in-your-non-developer-site-collection/).</span></span>
  
> [!NOTE]
> <span data-ttu-id="15a67-179">旁加载应用程序是一项开发/测试功能。</span><span class="sxs-lookup"><span data-stu-id="15a67-179">Sideloading apps is a developer/test feature.</span></span> <span data-ttu-id="15a67-180">它**不用于生产用途**。</span><span class="sxs-lookup"><span data-stu-id="15a67-180">It is **not intended for production use**.</span></span> <span data-ttu-id="15a67-181">请勿定期旁加载应用程序, 或保持应用程序旁加载的时间超过您主动使用该功能所需的时间。</span><span class="sxs-lookup"><span data-stu-id="15a67-181">Do not sideload apps regularly, or keep app sideloading enabled for longer than you are actively using the feature.</span></span> 
  
## <a name="add-content-to-the-add-in-project"></a><span data-ttu-id="15a67-182">将内容添加到加载项项目</span><span class="sxs-lookup"><span data-stu-id="15a67-182">Add content to the add-in project</span></span>

<span data-ttu-id="15a67-183">创建项目并设置调试机制后, 向应用程序添加内容包括以下任务:</span><span class="sxs-lookup"><span data-stu-id="15a67-183">After creating a project and setting up the debugging mechanism, adding content to the app includes the following tasks:</span></span>
  
- <span data-ttu-id="15a67-184">设置应用程序范围</span><span class="sxs-lookup"><span data-stu-id="15a67-184">Setting the application scope</span></span>
    
- <span data-ttu-id="15a67-185">链接 JSOM 库</span><span class="sxs-lookup"><span data-stu-id="15a67-185">Linking the JSOM library</span></span>
    
- <span data-ttu-id="15a67-186">向加载项添加 UI 元素</span><span class="sxs-lookup"><span data-stu-id="15a67-186">Adding UI Elements to the add-in</span></span>
    
- <span data-ttu-id="15a67-187">初始化和连接到 Project Online 服务</span><span class="sxs-lookup"><span data-stu-id="15a67-187">Initializing and connecting to the Project Online service</span></span>
    
- <span data-ttu-id="15a67-188">检索项目和详细信息/属性</span><span class="sxs-lookup"><span data-stu-id="15a67-188">Retrieving projects and details/properties</span></span>
    
- <span data-ttu-id="15a67-189">显示项目</span><span class="sxs-lookup"><span data-stu-id="15a67-189">Displaying projects</span></span>
    
- <span data-ttu-id="15a67-190">显示项目的任务</span><span class="sxs-lookup"><span data-stu-id="15a67-190">Displaying tasks for a Project</span></span>
    
<span data-ttu-id="15a67-191">加载项项目由多个文件组成。</span><span class="sxs-lookup"><span data-stu-id="15a67-191">The add-in project consists of many files.</span></span> <span data-ttu-id="15a67-192">在此示例中, 需要编辑以下文件:</span><span class="sxs-lookup"><span data-stu-id="15a67-192">In this example, you'll need to edit the following files:</span></span> 
  
- <span data-ttu-id="15a67-193">appmanifest.xml</span><span class="sxs-lookup"><span data-stu-id="15a67-193">AppManifest.xml</span></span>
    
- <span data-ttu-id="15a67-194">default.aspx</span><span class="sxs-lookup"><span data-stu-id="15a67-194">Default.aspx</span></span>
    
- <span data-ttu-id="15a67-195">node.js</span><span class="sxs-lookup"><span data-stu-id="15a67-195">App.js</span></span>
    
- <span data-ttu-id="15a67-196">"应用程序"。 css-可选;包含为外接程序开发的样式定义</span><span class="sxs-lookup"><span data-stu-id="15a67-196">App.css - optional; contains style definitions developed for the add-in</span></span>
    
<span data-ttu-id="15a67-197">如果 project Online 租户发生更改 (例如, 从试用版移动到订阅网站), 则可以使用 "属性" 窗口通过**视图** > 属性更新项目属性, 包括服务器连接和网站 URL。**Window**命令。</span><span class="sxs-lookup"><span data-stu-id="15a67-197">If the Project Online tenant changes, such as moving from a trial to a subscription site, you can update the project properties, including the Server Connection and Site URL, using the Properties Window available through the **View** > **Properties Window** command.</span></span> 
  
<span data-ttu-id="15a67-198">您还可以将文件添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="15a67-198">You can also add files to the project.</span></span> <span data-ttu-id="15a67-199">如果是这样, 您需要更新位于同一组 (内容、图像、页面或脚本) 中的元素 .xml 文件, 以包含新文件。</span><span class="sxs-lookup"><span data-stu-id="15a67-199">If so, you'll need to update the Elements.xml file located in the same group (Content, Images, Pages, or Scripts) to include the new files.</span></span> <span data-ttu-id="15a67-200">有关项目文件的详细信息, 请参阅[探究应用部件清单 (manifest) 结构和 SharePoint 加载项的包](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/explore-the-app-manifest-structure-and-the-package-of-a-sharepoint-add-in)。</span><span class="sxs-lookup"><span data-stu-id="15a67-200">For more information about the project files, see [Explore the app manifest structure and the package of a SharePoint Add-in](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/explore-the-app-manifest-structure-and-the-package-of-a-sharepoint-add-in).</span></span>
  
### <a name="set-application-scope"></a><span data-ttu-id="15a67-201">设置应用程序范围</span><span class="sxs-lookup"><span data-stu-id="15a67-201">Set application scope</span></span>

<span data-ttu-id="15a67-202">外接端需要在服务返回查询结果中的信息之前定义的范围或权限级别。</span><span class="sxs-lookup"><span data-stu-id="15a67-202">The add-in needs scope or permission levels defined before the service returns information in query results.</span></span> <span data-ttu-id="15a67-203">对于此外接程序, 请使用 Visual Studio 项目的以下范围。</span><span class="sxs-lookup"><span data-stu-id="15a67-203">For this add-in, use the following scope to the Visual Studio project.</span></span> <span data-ttu-id="15a67-204">对 "权限" 选项卡中的 appmanifest.xml 文件进行此更改:</span><span class="sxs-lookup"><span data-stu-id="15a67-204">This change is made to the AppManifest.xml file in the Permissions tab:</span></span>

|<span data-ttu-id="15a67-205">Scope</span><span class="sxs-lookup"><span data-stu-id="15a67-205">Scope</span></span>|<span data-ttu-id="15a67-206">权限</span><span class="sxs-lookup"><span data-stu-id="15a67-206">Permission</span></span>|
|:-----|:-----|
|<span data-ttu-id="15a67-207">多个项目 (Project Server)</span><span class="sxs-lookup"><span data-stu-id="15a67-207">Multiple Projects (Project Server)</span></span>  <br/> |<span data-ttu-id="15a67-208">读取</span><span class="sxs-lookup"><span data-stu-id="15a67-208">Read</span></span>  <br/> |
   
<span data-ttu-id="15a67-209">在设置应用程序范围后保存文件。</span><span class="sxs-lookup"><span data-stu-id="15a67-209">Save the file after setting the application scope.</span></span> <span data-ttu-id="15a67-210">否则, 服务将不会返回任何数据。</span><span class="sxs-lookup"><span data-stu-id="15a67-210">Otherwise, no data will be returned from the service.</span></span> 
  
### <a name="link-the-jsom-library"></a><span data-ttu-id="15a67-211">链接 JSOM 库</span><span class="sxs-lookup"><span data-stu-id="15a67-211">Link the JSOM library</span></span>

<span data-ttu-id="15a67-212">运行时 project online 库、.ps 和 .ps 是由 Project online 提供的, 并且始终是最新版本。</span><span class="sxs-lookup"><span data-stu-id="15a67-212">The runtime Project Online libraries, PS.js and PS.debug.js, are provided by Project Online and are always the most recent version.</span></span> <span data-ttu-id="15a67-213">使用 JSOM 的 JavaScript 加载项必须与这些库中的一个相链接。</span><span class="sxs-lookup"><span data-stu-id="15a67-213">JavaScript add-ins that use JSOM must link with one of these libraries.</span></span> <span data-ttu-id="15a67-214">将链接定义添加到默认 .aspx 文件中。</span><span class="sxs-lookup"><span data-stu-id="15a67-214">The linking definitions are added in the Default.aspx file.</span></span> <span data-ttu-id="15a67-215">使用 PS .js 和/或 .ps 的命令是位于 app.config 文件中的代码的一部分。</span><span class="sxs-lookup"><span data-stu-id="15a67-215">The commands to use the PS.js and/or PS.debug.js are part of the code located in the App.js file.</span></span>
  
<span data-ttu-id="15a67-216">在 ScriptLink 的 "SharePoint:" 后面的`<asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead"`元素中为 .ps 或 .ps 定义添加以下命令。</span><span class="sxs-lookup"><span data-stu-id="15a67-216">Add the following command for PS.js or PS.debug.js definition in the  `<asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead"` element following the "SharePoint:ScriptLink" for sp.js.</span></span> 
  
```js
<SharePoint:ScriptLink name="PS.js" runat="server" OnDemand="false" LoadAfterUI="true" Localizable="false" />
```

> [!NOTE]
> <span data-ttu-id="15a67-217">将 .ps 或 ps. .js 的**OnDemand**属性设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="15a67-217">The **OnDemand** attribute for PS.js or PS.debug.js set to **false**.</span></span> 
  
### <a name="add-ui-elements-to-the-add-in"></a><span data-ttu-id="15a67-218">向加载项添加 UI 元素</span><span class="sxs-lookup"><span data-stu-id="15a67-218">Add UI elements to the add-in</span></span>

<span data-ttu-id="15a67-219">该示例加载项由几个组件组成。</span><span class="sxs-lookup"><span data-stu-id="15a67-219">The example add-in consists of a few components.</span></span> <span data-ttu-id="15a67-220">静态元素说明位于默认的 .aspx 文件中。</span><span class="sxs-lookup"><span data-stu-id="15a67-220">Static element descriptions are located in the Default.aspx file.</span></span> <span data-ttu-id="15a67-221">所有组件的动态元素说明和代码都位于 app.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="15a67-221">Dynamic element descriptions and code for all components are located in the App.js file.</span></span> <span data-ttu-id="15a67-222">有关这些组件的注释, 请参考源代码清单。</span><span class="sxs-lookup"><span data-stu-id="15a67-222">For comments regarding the components, refer to the source code listings.</span></span> <span data-ttu-id="15a67-223">下面是加载项中的 UI 组件的列表:</span><span class="sxs-lookup"><span data-stu-id="15a67-223">Here is a list of the UI components in the add-in:</span></span>
  
- <span data-ttu-id="15a67-224">标题</span><span class="sxs-lookup"><span data-stu-id="15a67-224">Title</span></span>
    
- <span data-ttu-id="15a67-225">介绍性措辞</span><span class="sxs-lookup"><span data-stu-id="15a67-225">Introductory verbiage</span></span>
    
- <span data-ttu-id="15a67-226">用于从表格中删除任务的按钮</span><span class="sxs-lookup"><span data-stu-id="15a67-226">Button to remove tasks from the table</span></span>
    
- <span data-ttu-id="15a67-227">列出项目 ID 和名称以及任务信息的表。</span><span class="sxs-lookup"><span data-stu-id="15a67-227">Table that lists the project ID and name, and the task information.</span></span>
    
- <span data-ttu-id="15a67-228">将任务数据导入表中的 "任务" 按钮 (为每个项目克隆一次)。</span><span class="sxs-lookup"><span data-stu-id="15a67-228">Tasks Button (cloned once for each project) that imports task data into the table.</span></span>
    
<span data-ttu-id="15a67-229">有关用户界面的详细信息, 如项目表的标题和标头部分, 请参阅 default.aspx 项目文件。</span><span class="sxs-lookup"><span data-stu-id="15a67-229">For details of the user interface, such as the title and the header portion of the project table, see the Default.aspx project file.</span></span>
  
### <a name="initialize-and-connect-to-the-host-system"></a><span data-ttu-id="15a67-230">初始化并连接到主机系统</span><span class="sxs-lookup"><span data-stu-id="15a67-230">Initialize and connect to the host system</span></span>

<span data-ttu-id="15a67-231">应用 .js 文件包含 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="15a67-231">The App.js file contains the JavaScript code.</span></span> <span data-ttu-id="15a67-232">加载项在浏览器中加载 PS .js, 然后调用 initializePage 函数。</span><span class="sxs-lookup"><span data-stu-id="15a67-232">The add-in loads PS.js in the browser, and then calls the initializePage function.</span></span> <span data-ttu-id="15a67-233">InitializePage 检索 Project Online 终结点的上下文并启动 loadProjects 函数。</span><span class="sxs-lookup"><span data-stu-id="15a67-233">InitializePage retrieves a context to the Project Online endpoint and starts the loadProjects function.</span></span>
  
```js
    'use strict';
    SP.SOD.executeOrDelayUntilScriptLoaded(initializePage, "PS.js");
    //Project PWA Context and published projects in PWA
    var projContext;
    var projects;
    function initializePage() {
        //Get the Project context for this web
        projContext = PS.ProjectContext.get_current();
        loadProjects();
    }
    //General CSOM failure event handler
    //Invoked when ExecuteQueryAsync returns unsuccessfully
    function onRequestFailed(sender, args) {
        alert("Failed to execute: " + args.get_message());
        return;
    };

```

### <a name="retrieve-the-projects"></a><span data-ttu-id="15a67-234">检索项目</span><span class="sxs-lookup"><span data-stu-id="15a67-234">Retrieve the projects</span></span>

<span data-ttu-id="15a67-235">loadProjects 函数查询服务中的项目名称和 id。</span><span class="sxs-lookup"><span data-stu-id="15a67-235">The loadProjects function queries the service for the project names and IDs.</span></span> 
  
<span data-ttu-id="15a67-236">应用程序将检索项目名称和项目 Id。可通过修改 load 方法以显式标识要检索的属性来访问有关项目的其他信息。</span><span class="sxs-lookup"><span data-stu-id="15a67-236">The application retrieves the project name and project Id. Other information about the project is available and can be accessed by modifying the load method to identify explicitly the properties to retrieve.</span></span> <span data-ttu-id="15a67-237">代码中提供了一个示例作为注释。</span><span class="sxs-lookup"><span data-stu-id="15a67-237">An example is provided in the code as a comment.</span></span> 
  
<span data-ttu-id="15a67-238">如果查询成功, 则外接程序会通过调用 displayProjects 继续进行。</span><span class="sxs-lookup"><span data-stu-id="15a67-238">If the query succeeds, the add-in continues by calling displayProjects.</span></span> 
  
```js
    //Query CSOM and get the list of projects in PWA
    function loadProjects() {
        projects = projContext.get_projects();
    //Request to server - identifies what to retrieve
        projContext.load(projects, 'Include(Name, Id)');
        //Notice to server to execute query
        projContext.executeQueryAsync(displayProjects, onRequestFailed);
        // Syntax for requesting more fields to pull down from server
        // projContext.load(projects, 'Include(Name, Description, StartDate, 
        // Id, IsCheckedOut)');
    }

```

### <a name="display-the-projects"></a><span data-ttu-id="15a67-239">显示项目</span><span class="sxs-lookup"><span data-stu-id="15a67-239">Display the projects</span></span>

<span data-ttu-id="15a67-240">displayProjects 函数创建一个表, 每个项目一行, 并使用一个按钮来显示特定项目的任务。</span><span class="sxs-lookup"><span data-stu-id="15a67-240">The displayProjects function creates a table, one row per project, and a button to show the tasks for the specific project.</span></span> 
  
```js
    //Display the projects with names and ids in a table
    function displayProjects() {
        //Current published project and ID
        var p, projId;
        //Project table rows to publish collectively
        var pTable = []; 
        var pEnum = projects.getEnumerator();
        //Build a 3-column table, with one project per row.
        while (pEnum.moveNext()) {
            p = pEnum.get_current();
        
            //Items used in getting information for table rows:
            //Current published project object, and ID and name
            // var project = p;
            // var projId = p.get_id();
            // var projName = p.get_name();
        
            //Continue processing/working with project object as needed.
        }
    }

```

> [!NOTE]
> <span data-ttu-id="15a67-241">while 循环访问 ID 和 name 属性。</span><span class="sxs-lookup"><span data-stu-id="15a67-241">The while loop accesses the ID and name properties.</span></span> <span data-ttu-id="15a67-242">这与调用函数的源代码项目略有不同, 后者又访问相同的属性。</span><span class="sxs-lookup"><span data-stu-id="15a67-242">This is slightly different than the source code project that calls a function that, in turn, accesses the same properties.</span></span> 
  
### <a name="display-the-tasks-for-a-project"></a><span data-ttu-id="15a67-243">显示项目的任务</span><span class="sxs-lookup"><span data-stu-id="15a67-243">Display the tasks for a project</span></span>

<span data-ttu-id="15a67-244">加载项的一部分任务不是初始加载的一部分。</span><span class="sxs-lookup"><span data-stu-id="15a67-244">The tasks, while part of the add-in, are not part of the initial loading.</span></span> <span data-ttu-id="15a67-245">如果用户对与项目相关联的任务感兴趣, 则单击 "显示任务" 按钮会导致任务使用 btnLoadTasks 事件处理程序在列表中显示。</span><span class="sxs-lookup"><span data-stu-id="15a67-245">If the user is interested in the tasks associated with a project, clicking the "Show Tasks" button causes the tasks to display in the list using the btnLoadTasks event handler.</span></span> 
  
<span data-ttu-id="15a67-246">btnLoadTasks 事件处理程序 (具有相应的项目 ID) 从服务器请求指定项目的任务。</span><span class="sxs-lookup"><span data-stu-id="15a67-246">The btnLoadTasks event handler, with the appropriate project ID, requests the tasks for the specified project from the server.</span></span> <span data-ttu-id="15a67-247">检索后, btnLoadTasks 会将任务列表传递给 displayTasks, 以在屏幕上显示任务。</span><span class="sxs-lookup"><span data-stu-id="15a67-247">Once retrieved, btnLoadTasks passes the task list to displayTasks to present the tasks onscreen.</span></span>
  
```js
    //Query CSOM and get the list of tasks for a specific project
    function btnLoadTasks(pid) {
        //Event handler for the "Show tasks" buttons. 
        //
        //The project ID is the sole argument and is used to get the appropriate task 
        //info from the service.
        //The project ID is also the button name, and is used to identify where to place
        //the task information in the table.
        //
        //Project ID to pass to the event handler
        var projId = pid;
        //
        //Get the project reference
        var pProj = projects.getById(projId);
        //
        //Get the tasks collection reference associated with the project.
        var tasks = pProj.get_tasks();
        //
        projContext.load(tasks, 'Include(Id, Name, Start, ScheduledStart, Completion)');
        //
        //If the query succeeds, displayTasks presents the tasks to the user.
        projContext.executeQueryAsync(function () { displayTasks(tasks, projId) }, onRequestFailed);
    }

```

<span data-ttu-id="15a67-248">displayTasks 函数显示与项目项紧下方的指定项目相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="15a67-248">The displayTasks function displays the tasks associated with a specified project immediately beneath the project entry.</span></span>
  
```js
    //Insert tasks for the specified project immediately underneath the project entry 
    //in the table.
    function displayTasks(tasks, projId) {
        //selected project ID
        var pId = projId;
        //individual task
        var t;
        //Task table rows to publish collectively
        var tTable = [];
        var tEnum = tasks.getEnumerator();
        //Build table one task per row.
        while (tEnum.moveNext()) {
            t = tEnum.get_current();
            //
            //Items used in getting information for table rows:
            //Current task object, and ID and name
            // var task = t;
            // var taskId = t.get_id();
            // var taskName = t.get_name();
            
            //Continue processing/working with task object as needed.
        }
    }

```

> [!NOTE]
> <span data-ttu-id="15a67-249">while 循环访问任务 ID 和名称属性。</span><span class="sxs-lookup"><span data-stu-id="15a67-249">The while loop accesses the task ID and name properties.</span></span> <span data-ttu-id="15a67-250">这与调用函数的源代码项目略有不同, 后者又访问相同的属性。</span><span class="sxs-lookup"><span data-stu-id="15a67-250">This is slightly different than the source code project that calls a function that, in turn, accesses the same properties.</span></span> 
  
<span data-ttu-id="15a67-251">下面是单个项目的任务的示例输出。</span><span class="sxs-lookup"><span data-stu-id="15a67-251">Sample output for the tasks of a single project follows.</span></span>
  
<span data-ttu-id="15a67-252">![显示项目任务的输出的屏幕截图](media/f6500a3f-000b-4f3e-9be6-9a74d0bea15e.png "显示项目任务的输出的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="15a67-252">![Screen shot showing the output for a project task](media/f6500a3f-000b-4f3e-9be6-9a74d0bea15e.png "Screen shot showing the output for a project task")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="15a67-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15a67-253">See also</span></span>

<span data-ttu-id="15a67-254">有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/en-us/project)。</span><span class="sxs-lookup"><span data-stu-id="15a67-254">For documentation and samples related to Project Online and application development using CSOM, see the [Project Development Portal](https://developer.microsoft.com/en-us/project).</span></span>
    


