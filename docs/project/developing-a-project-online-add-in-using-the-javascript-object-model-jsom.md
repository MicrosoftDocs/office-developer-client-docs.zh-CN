---
title: '使用 JAVAScript Project Online JSOM 模型开发 (加载项) '
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4a4b1ad2-de46-421d-a698-53c20c90b93a
description: 本文介绍Microsoft Project Online外接程序开发，以增强使用加载项Project Online。 开发项目作为演练实现。 用于本文的外接程序从 Project Online 帐户读取并显示已发布项目的项目名称和 ID，并允许您向下钻取以检索与单个项目关联的任务。
ms.openlocfilehash: 0a472a6300f18aaa65649f44d944445642a59e1a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322682"
---
# <a name="developing-a-project-online-add-in-using-the-javascript-object-model-jsom"></a><span data-ttu-id="0b99d-105">使用 JAVAScript Project Online JSOM 模型开发 (加载项) </span><span class="sxs-lookup"><span data-stu-id="0b99d-105">Developing a Project Online add-in using the JavaScript Object Model (JSOM)</span></span>

<span data-ttu-id="0b99d-106">本文介绍如何Microsoft Project Online外接程序开发来增强使用加载项Project Online。</span><span class="sxs-lookup"><span data-stu-id="0b99d-106">This article describes Microsoft Project Online Add-in development to enhance your experience with the Project Online.</span></span> <span data-ttu-id="0b99d-107">开发项目作为演练实现。</span><span class="sxs-lookup"><span data-stu-id="0b99d-107">The development project is implemented as a walkthrough.</span></span> <span data-ttu-id="0b99d-108">用于本文的外接程序从 Project Online 帐户读取并显示已发布项目的项目名称和 ID，并允许您向下钻取以检索与单个项目关联的任务。</span><span class="sxs-lookup"><span data-stu-id="0b99d-108">The add-in used for this article reads and displays the project names and IDs of the published projects from your Project Online account and allows you to drill down to retrieve tasks associated with individual projects.</span></span>
  
<span data-ttu-id="0b99d-109">运行时，外接程序列表类似于下图：</span><span class="sxs-lookup"><span data-stu-id="0b99d-109">At run time, the add-in listing looks similar to the following illustration:</span></span>
  
<span data-ttu-id="0b99d-110">![显示 JSOM 项目和]任务列表的屏幕截图 显示(media/766e5914-f048-48f4-9282-291f55e6e90d.png "JSOM 项目和任务列表的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="0b99d-110">![Screen shot showing a listing of JSOM projects and tasks](media/766e5914-f048-48f4-9282-291f55e6e90d.png "Screen shot showing a listing of JSOM projects and tasks")</span></span>
  
<span data-ttu-id="0b99d-111">该示例的重心是与 Project Online 交互，执行查询并设置服务中每个请求的上下文。</span><span class="sxs-lookup"><span data-stu-id="0b99d-111">The focus of the example is the interaction with the Project Online, making queries and setting the context for each request from the service.</span></span> <span data-ttu-id="0b99d-112">用户界面 (UI) 元素得到最少关注。</span><span class="sxs-lookup"><span data-stu-id="0b99d-112">User interface (UI) elements receive minimal attention.</span></span> <span data-ttu-id="0b99d-113">相反，源列表会提供有关 UI 的注释。</span><span class="sxs-lookup"><span data-stu-id="0b99d-113">Instead, the source listings provide comments regarding the UI.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b99d-114">示例外接程序的源文件是一个Visual Studio项目，可在以下位置获得 https://github.com/OfficeDev/Project-JSOM-List-Projects-Tasks.... ： 。</span><span class="sxs-lookup"><span data-stu-id="0b99d-114">The source files for the example add-in, a Visual Studio project, are available at: https://github.com/OfficeDev/Project-JSOM-List-Projects-Tasks.....</span></span> <span data-ttu-id="0b99d-115">阅读文章时，请保持源文件方便作为参考，因为每个源文件相互补充。</span><span class="sxs-lookup"><span data-stu-id="0b99d-115">Keep the source files handy as a reference while you read the article, as each complements the other.</span></span> <span data-ttu-id="0b99d-116">项目生成Visual Studio中的文件可执行，只需进行最少的更改，即可将 Project Online 租户的 URL 向下PWA文件夹。</span><span class="sxs-lookup"><span data-stu-id="0b99d-116">The files in the Visual Studio project build and are executable with minimal changes—substituting the URL for your Project Online tenant down to the PWA folder.</span></span> 
  
## <a name="background"></a><span data-ttu-id="0b99d-117">背景</span><span class="sxs-lookup"><span data-stu-id="0b99d-117">Background</span></span>

<span data-ttu-id="0b99d-118">Project Online是一项 Office 365 服务，可为公司提供项目组合管理 (PPM) 和项目管理办公室 (PMO) 解决方案，以协调和管理项目组合、计划和项目。</span><span class="sxs-lookup"><span data-stu-id="0b99d-118">Project Online is a Office 365 service that provides companies with a project portfolio management (PPM) and project management office (PMO) solution to coordinate and manage portfolios, programs, and projects.</span></span> <span data-ttu-id="0b99d-119">Project Online桌面版与桌面Project不同;但是，Project Online仍包含用于在整个项目生命周期中维护和跟踪项目详细信息的功能。</span><span class="sxs-lookup"><span data-stu-id="0b99d-119">Project Online is a different offering than the Project desktop editions; yet, Project Online still contains the functionality to maintain and track project details throughout the life of a project.</span></span> <span data-ttu-id="0b99d-120">Project Online基于 SharePoint Online 构建。</span><span class="sxs-lookup"><span data-stu-id="0b99d-120">Project Online is built on SharePoint Online.</span></span>
  
<span data-ttu-id="0b99d-121">托管Project Online加载项由与客户端对象模型 API 交互的 JavaScript 和资源文件组成。</span><span class="sxs-lookup"><span data-stu-id="0b99d-121">A Project Online hosted add-in consists of JavaScript and resource files that interact with the Client-Side-Object-Model API.</span></span> <span data-ttu-id="0b99d-122">用户访问外接程序时，JavaScript 和资源在浏览器中下载和执行。</span><span class="sxs-lookup"><span data-stu-id="0b99d-122">When the user visits the add-in, the JavaScript and resources are downloaded and executed within the browser.</span></span> <span data-ttu-id="0b99d-123">无论创建、检索、更新Project Online数据，加载项都对加载项进行异步调用，以与服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="0b99d-123">The add-In makes asynchronous calls to Project Online to interact with the service, whether creating, retrieving, updating, or deleting data.</span></span> 
  
<span data-ttu-id="0b99d-124">Project Online执行另一个操作来保护属于其他租户的信息免受加载项影响;即，Project Online创建一个隔离网站以与来自外接程序的请求进行交互。</span><span class="sxs-lookup"><span data-stu-id="0b99d-124">Project Online performs one more action to protect information that belongs to other tenants from the add-in; namely, Project Online creates an isolated site to interact with the requests from the add-in.</span></span> <span data-ttu-id="0b99d-125">主机上没有运行自定义Project Online代码。</span><span class="sxs-lookup"><span data-stu-id="0b99d-125">No custom code runs on the Project Online host.</span></span> 
  
<span data-ttu-id="0b99d-126">加载项的开发设置Project Online加载项使用Visual Studio SharePoint加载项项目类型。</span><span class="sxs-lookup"><span data-stu-id="0b99d-126">The development setup for Project Online add-ins uses the Visual Studio SharePoint Add-in project type.</span></span> <span data-ttu-id="0b99d-127">外接程序使用 JavaScript 编写，并使用 Project JavaScript 对象模型 (JSOM) 与 Project Online 服务交互。</span><span class="sxs-lookup"><span data-stu-id="0b99d-127">The add-in is written in JavaScript, and uses the Project JavaScript object model (JSOM) to interact with the Project Online service.</span></span> <span data-ttu-id="0b99d-128">JSOM 从 JSOM 继承大部分SharePoint功能。</span><span class="sxs-lookup"><span data-stu-id="0b99d-128">The JSOM inherits much of its functionality from the SharePoint JSOM.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b99d-129">加载项可以在应用商店中发布和出售Office或部署到 SharePoint 上的专用应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="0b99d-129">Add-ins can be published and sold in the Office Store or deployed to a private app catalog on SharePoint.</span></span> <span data-ttu-id="0b99d-130">有关详细信息，请参阅[部署和发布Office加载项。](https://docs.microsoft.com/office/dev/add-ins/publish/publish)</span><span class="sxs-lookup"><span data-stu-id="0b99d-130">For more information, see [Deploy and publish your Office Add-in](https://docs.microsoft.com/office/dev/add-ins/publish/publish).</span></span>
> 
> <span data-ttu-id="0b99d-131">本文中使用的外接程序是开发人员的示例;它不适合在生产环境使用。</span><span class="sxs-lookup"><span data-stu-id="0b99d-131">The add-in used in this article is a sample for developers; it is not intended for use in a production environment.</span></span> <span data-ttu-id="0b99d-132">主要用途是展示一个应用开发示例，Project Online。</span><span class="sxs-lookup"><span data-stu-id="0b99d-132">The primary purpose is to show an example of app development for Project Online.</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="0b99d-133">必备条件</span><span class="sxs-lookup"><span data-stu-id="0b99d-133">Prerequisites</span></span>

<span data-ttu-id="0b99d-134">将以下项添加到受支持的Windows环境中：</span><span class="sxs-lookup"><span data-stu-id="0b99d-134">Add the following items to a supported Windows environment:</span></span>
  
- <span data-ttu-id="0b99d-135">**.NET Framework 4.0 或** 更高版本：兼容 4.0 版框架的完整版本。</span><span class="sxs-lookup"><span data-stu-id="0b99d-135">**.NET Framework 4.0 or later**: Complete versions of the framework from version 4.0 are compatible.</span></span> <span data-ttu-id="0b99d-136">下载网站为 https://msdn.microsoft.com/vstudio/aa496123.aspx。</span><span class="sxs-lookup"><span data-stu-id="0b99d-136">The download site is https://msdn.microsoft.com/vstudio/aa496123.aspx.</span></span>
    
- <span data-ttu-id="0b99d-137">**Visual Studio 2013或更高版本**：</span><span class="sxs-lookup"><span data-stu-id="0b99d-137">**Visual Studio 2013 or later**:</span></span>  
    
   - <span data-ttu-id="0b99d-138">the professional edition of Visual Studio 2015 is ready to out-of the box and is available at https://www.visualstudio.com/en-us/products/visual-studio-professional-with-msdn-vs.aspx .</span><span class="sxs-lookup"><span data-stu-id="0b99d-138">The professional edition of Visual Studio 2015 is ready to go out-of-the box and is available at https://www.visualstudio.com/en-us/products/visual-studio-professional-with-msdn-vs.aspx.</span></span>
    
   - <span data-ttu-id="0b99d-139">2015 年 Visual Studio社区版可在 上获得 https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx 。</span><span class="sxs-lookup"><span data-stu-id="0b99d-139">The community edition of Visual Studio 2015 is available at https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx.</span></span> <span data-ttu-id="0b99d-140">此版本要求手动安装 Microsoft Office 开发人员工具Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="0b99d-140">This edition requires manual installation of the Microsoft Office Developer Tools for Visual Studio.</span></span>
    
   <span data-ttu-id="0b99d-141">有关Microsoft Office开发人员工具Visual Studio可在 上获得 https://www.visualstudio.com/en-us/features/office-tools-vs.aspx 。</span><span class="sxs-lookup"><span data-stu-id="0b99d-141">The Microsoft Office Developer Tools for Visual Studio are available at https://www.visualstudio.com/en-us/features/office-tools-vs.aspx.</span></span>
    
- <span data-ttu-id="0b99d-142">**A Project Online account**： This provides access to the hosting service.</span><span class="sxs-lookup"><span data-stu-id="0b99d-142">**A Project Online account**: This provides access to the hosting service.</span></span> <span data-ttu-id="0b99d-143">有关获取 Project Online 帐户的详细信息，请参阅 https://products.office.com/en-us/Project/project-online-portfolio-management</span><span class="sxs-lookup"><span data-stu-id="0b99d-143">For more information about obtaining a Project Online account, see https://products.office.com/en-us/Project/project-online-portfolio-management.</span></span>
    
   <span data-ttu-id="0b99d-144">确保加载项用户具有足够的授权，可以访问加载项租户中的Project Online项目。</span><span class="sxs-lookup"><span data-stu-id="0b99d-144">Ensure that the add-in user has sufficient authorization to access some projects in the Project Online tenant.</span></span> 
    
- <span data-ttu-id="0b99d-145">**使用信息填充的** 宿主网站上的项目。</span><span class="sxs-lookup"><span data-stu-id="0b99d-145">**Projects on the hosting site** that are populated with information.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0b99d-146">标准.NET Framework使用正确的框架。</span><span class="sxs-lookup"><span data-stu-id="0b99d-146">The standard .NET Framework is the correct framework to use.</span></span> <span data-ttu-id="0b99d-147">请勿使用".NET Framework 4 客户端配置文件"。</span><span class="sxs-lookup"><span data-stu-id="0b99d-147">Do not use the ".NET Framework 4 Client Profile".</span></span> 
  
### <a name="set-up-the-visual-studio-project"></a><span data-ttu-id="0b99d-148">设置 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="0b99d-148">Set up the Visual Studio project</span></span>

<span data-ttu-id="0b99d-149">应用程序设置包括创建新项目、链接相应的库和声明所需的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0b99d-149">The application setup consists of creating a new project, linking the appropriate libraries and declaring the needed namespaces.</span></span> <span data-ttu-id="0b99d-150">Visual Studio 提供有多种类型的开发项目。</span><span class="sxs-lookup"><span data-stu-id="0b99d-150">Visual Studio presents several types of development projects.</span></span> <span data-ttu-id="0b99d-151">此部分简短且非常基本。</span><span class="sxs-lookup"><span data-stu-id="0b99d-151">The section is brief and very basic.</span></span> <span data-ttu-id="0b99d-152">值使信息在一处进行并组织。</span><span class="sxs-lookup"><span data-stu-id="0b99d-152">The value is having the information is coalesced in one place.</span></span>
  
#### <a name="select-a-visual-studio-project"></a><span data-ttu-id="0b99d-153">选择 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="0b99d-153">Select a Visual Studio project</span></span>

<span data-ttu-id="0b99d-154">若要为加载项创建适当类型的项目，必须执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="0b99d-154">To create a project of the appropriate type for the add-in, you must do the following steps.</span></span> <span data-ttu-id="0b99d-155">屏幕上显示的关键字具有 **粗体** 属性：</span><span class="sxs-lookup"><span data-stu-id="0b99d-155">Keywords encountered on the screen have a **bold** attribute:</span></span> 
  
1. <span data-ttu-id="0b99d-156">从"文件"菜单中，选择"**文件**  >  **""**  >  **新建Project"。**</span><span class="sxs-lookup"><span data-stu-id="0b99d-156">From the File menu, choose **File** > **New** > **Project**.</span></span> 
    
2. <span data-ttu-id="0b99d-157">从左窗格中的"已安装的模板"中  >  **，C#Office/SharePoint**  >  **Web 加载项"。**</span><span class="sxs-lookup"><span data-stu-id="0b99d-157">From the Installed templates in the left pane, select **C#** > **Office/SharePoint** > **Web Add-ins**.</span></span> 
    
3. <span data-ttu-id="0b99d-158">在中央窗格顶部，选择".NET Framework **4** 或更高版本;当前版本为 4.6。</span><span class="sxs-lookup"><span data-stu-id="0b99d-158">At the top of the central pane, select **.NET Framework 4** or later; the current version is 4.6.</span></span> 
    
4. <span data-ttu-id="0b99d-159">从中央窗格中的应用程序类型中，SharePoint **外接程序"。**</span><span class="sxs-lookup"><span data-stu-id="0b99d-159">From the application types in the central pane, choose **SharePoint Add-in**.</span></span> 
    
5. <span data-ttu-id="0b99d-160">在底部为项目指定名称和位置以及解决方案名称。</span><span class="sxs-lookup"><span data-stu-id="0b99d-160">In the bottom section, specify a name and location for the project, and a solution name.</span></span> 
    
6. <span data-ttu-id="0b99d-161">此外，在底部选中“**创建解决方案的目录**”复选框。</span><span class="sxs-lookup"><span data-stu-id="0b99d-161">Also in the bottom section, check the **Create directory for solution** box.</span></span> 
    
7. <span data-ttu-id="0b99d-162">单击“**确定**”以创建初始项目。</span><span class="sxs-lookup"><span data-stu-id="0b99d-162">Click **OK** to create the initial project.</span></span> 
    
<span data-ttu-id="0b99d-163">"Visual Studio 向导"会询问一些有关 Project Online 设置网站 (（称为"SharePoint 设置）"的) 在下列几个对话框中。</span><span class="sxs-lookup"><span data-stu-id="0b99d-163">The Visual Studio Wizard asks a few follow-up questions about the Project Online settings site (called SharePoint settings in the dialogs) in a couple of dialogs that follow.</span></span> <span data-ttu-id="0b99d-164">以下是问题：</span><span class="sxs-lookup"><span data-stu-id="0b99d-164">Here are the questions:</span></span>
  
1. <span data-ttu-id="0b99d-165">SharePoint调试外接程序时要使用哪些网站？</span><span class="sxs-lookup"><span data-stu-id="0b99d-165">What SharePoint site do you want to use for debugging your add-in?</span></span> <span data-ttu-id="0b99d-166">指定指向网站PWA URL，例如 https://contoso.sharepoint.com/sites/pwa 。</span><span class="sxs-lookup"><span data-stu-id="0b99d-166">Specify the URL to your PWA site, such as https://contoso.sharepoint.com/sites/pwa.</span></span>
    
2. <span data-ttu-id="0b99d-167">您希望如何托管您的SharePoint外接程序？</span><span class="sxs-lookup"><span data-stu-id="0b99d-167">How do you want to host your SharePoint Add-in?</span></span> <span data-ttu-id="0b99d-168">选择"[X] **SharePoint托管的 "。**</span><span class="sxs-lookup"><span data-stu-id="0b99d-168">Choose [X] **SharePoint-hosted**.</span></span>
    
   <span data-ttu-id="0b99d-169">有关外接程序SharePoint（包括托管选项）的详细信息，请参阅 SharePoint[外接程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="0b99d-169">For more information about SharePoint Add-ins, including hosting options, see [SharePoint Add-ins](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins).</span></span>
    
3. <span data-ttu-id="0b99d-170">点击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="0b99d-170">Click **Next**.</span></span> 
    
<span data-ttu-id="0b99d-171">第二个附加对话框要求你为SharePoint指定 SharePoint Online 版本：</span><span class="sxs-lookup"><span data-stu-id="0b99d-171">The second additional dialog asks you to specify the SharePoint Online version for the add-in:</span></span> 
  
1. <span data-ttu-id="0b99d-172">您希望外接程序面向SharePoint的最早版本是什么？</span><span class="sxs-lookup"><span data-stu-id="0b99d-172">What's the earliest version of SharePoint that you want your add-in to target?</span></span> <span data-ttu-id="0b99d-173">选择[X] S **harePoint-Online**。</span><span class="sxs-lookup"><span data-stu-id="0b99d-173">Choose [X] S **harePoint-Online**.</span></span> 
    
2. <span data-ttu-id="0b99d-174">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="0b99d-174">Click **Finish**.</span></span> 
    
<span data-ttu-id="0b99d-175">Visual Studio创建项目并访问Project Online网站。</span><span class="sxs-lookup"><span data-stu-id="0b99d-175">Visual Studio creates the project and accesses the Project Online site.</span></span> 
  
### <a name="enable-sideloading-on-the-project-online-site"></a><span data-ttu-id="0b99d-176">在网站中启用Project Online加载</span><span class="sxs-lookup"><span data-stu-id="0b99d-176">Enable sideloading on the Project Online site</span></span>

<span data-ttu-id="0b99d-177">旁加载是测试和调试加载项Project Online机制。需要两个脚本进行旁加载：一个在 Project Online 网站上启用旁加载，另一个脚本用于完成加载项测试和调试后禁用旁加载。</span><span class="sxs-lookup"><span data-stu-id="0b99d-177">Sideloading is the mechanism for testing and debugging Project Online add-ins. You need two scripts for sideloading: one to enable sideloading on your Project Online site and another to disable sideloading once you finish testing and debugging the add-in.</span></span>
  
<span data-ttu-id="0b99d-178">有关设置旁加载的信息，请参阅在非开发人员网站集中 [启用应用旁加载](https://blogs.msdn.microsoft.com/officeapps/2013/12/10/enable-app-sideloading-in-your-non-developer-site-collection/)。</span><span class="sxs-lookup"><span data-stu-id="0b99d-178">For more information about setting up sideloading, see [Enable app SideLoading in your non-developer site collection](https://blogs.msdn.microsoft.com/officeapps/2013/12/10/enable-app-sideloading-in-your-non-developer-site-collection/).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b99d-179">旁加载应用是一项开发人员/测试功能。</span><span class="sxs-lookup"><span data-stu-id="0b99d-179">Sideloading apps is a developer/test feature.</span></span> <span data-ttu-id="0b99d-180">它 **不适合生产用途**。</span><span class="sxs-lookup"><span data-stu-id="0b99d-180">It is **not intended for production use**.</span></span> <span data-ttu-id="0b99d-181">不要定期旁加载应用，或使应用旁加载的启用时间比主动使用该功能的时间长。</span><span class="sxs-lookup"><span data-stu-id="0b99d-181">Do not sideload apps regularly, or keep app sideloading enabled for longer than you are actively using the feature.</span></span> 
  
## <a name="add-content-to-the-add-in-project"></a><span data-ttu-id="0b99d-182">向加载项项目添加内容</span><span class="sxs-lookup"><span data-stu-id="0b99d-182">Add content to the add-in project</span></span>

<span data-ttu-id="0b99d-183">创建项目并设置调试机制后，向应用添加内容包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="0b99d-183">After creating a project and setting up the debugging mechanism, adding content to the app includes the following tasks:</span></span>
  
- <span data-ttu-id="0b99d-184">设置应用程序范围</span><span class="sxs-lookup"><span data-stu-id="0b99d-184">Setting the application scope</span></span>
    
- <span data-ttu-id="0b99d-185">链接 JSOM 库</span><span class="sxs-lookup"><span data-stu-id="0b99d-185">Linking the JSOM library</span></span>
    
- <span data-ttu-id="0b99d-186">将 UI 元素添加到外接程序</span><span class="sxs-lookup"><span data-stu-id="0b99d-186">Adding UI Elements to the add-in</span></span>
    
- <span data-ttu-id="0b99d-187">初始化并连接到 Project Online 服务</span><span class="sxs-lookup"><span data-stu-id="0b99d-187">Initializing and connecting to the Project Online service</span></span>
    
- <span data-ttu-id="0b99d-188">检索项目和详细信息/属性</span><span class="sxs-lookup"><span data-stu-id="0b99d-188">Retrieving projects and details/properties</span></span>
    
- <span data-ttu-id="0b99d-189">显示项目</span><span class="sxs-lookup"><span data-stu-id="0b99d-189">Displaying projects</span></span>
    
- <span data-ttu-id="0b99d-190">显示任务Project</span><span class="sxs-lookup"><span data-stu-id="0b99d-190">Displaying tasks for a Project</span></span>
    
<span data-ttu-id="0b99d-191">加载项项目由多个文件组成。</span><span class="sxs-lookup"><span data-stu-id="0b99d-191">The add-in project consists of many files.</span></span> <span data-ttu-id="0b99d-192">本示例中，需要编辑以下文件：</span><span class="sxs-lookup"><span data-stu-id="0b99d-192">In this example, you'll need to edit the following files:</span></span> 
  
- <span data-ttu-id="0b99d-193">AppManifest.xml</span><span class="sxs-lookup"><span data-stu-id="0b99d-193">AppManifest.xml</span></span>
    
- <span data-ttu-id="0b99d-194">Default.aspx</span><span class="sxs-lookup"><span data-stu-id="0b99d-194">Default.aspx</span></span>
    
- <span data-ttu-id="0b99d-195">App.js</span><span class="sxs-lookup"><span data-stu-id="0b99d-195">App.js</span></span>
    
- <span data-ttu-id="0b99d-196">App.css - 可选;包含为外接程序开发的样式定义</span><span class="sxs-lookup"><span data-stu-id="0b99d-196">App.css - optional; contains style definitions developed for the add-in</span></span>
    
<span data-ttu-id="0b99d-197">如果 Project Online租户发生更改（例如从试用版移动到订阅网站）中，可以使用可通过"查看属性窗口"命令使用"属性窗口"更新项目属性，包括"服务器连接"和"网站 URL"。   >  </span><span class="sxs-lookup"><span data-stu-id="0b99d-197">If the Project Online tenant changes, such as moving from a trial to a subscription site, you can update the project properties, including the Server Connection and Site URL, using the Properties Window available through the **View** > **Properties Window** command.</span></span> 
  
<span data-ttu-id="0b99d-198">您还可以将文件添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="0b99d-198">You can also add files to the project.</span></span> <span data-ttu-id="0b99d-199">如果是，则需要更新位于同一组的 Elements.xml 文件 (内容、图像、页面或脚本) 以包含新文件。</span><span class="sxs-lookup"><span data-stu-id="0b99d-199">If so, you'll need to update the Elements.xml file located in the same group (Content, Images, Pages, or Scripts) to include the new files.</span></span> <span data-ttu-id="0b99d-200">有关项目文件详细信息，请参阅浏览应用程序清单结构和加载项SharePoint[包](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/explore-the-app-manifest-structure-and-the-package-of-a-sharepoint-add-in)。</span><span class="sxs-lookup"><span data-stu-id="0b99d-200">For more information about the project files, see [Explore the app manifest structure and the package of a SharePoint Add-in](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/explore-the-app-manifest-structure-and-the-package-of-a-sharepoint-add-in).</span></span>
  
### <a name="set-application-scope"></a><span data-ttu-id="0b99d-201">设置应用程序范围</span><span class="sxs-lookup"><span data-stu-id="0b99d-201">Set application scope</span></span>

<span data-ttu-id="0b99d-202">外接程序需要先定义范围或权限级别，然后服务才能在查询结果中返回信息。</span><span class="sxs-lookup"><span data-stu-id="0b99d-202">The add-in needs scope or permission levels defined before the service returns information in query results.</span></span> <span data-ttu-id="0b99d-203">对于此外接程序，请使用以下范围来访问Visual Studio项目。</span><span class="sxs-lookup"><span data-stu-id="0b99d-203">For this add-in, use the following scope to the Visual Studio project.</span></span> <span data-ttu-id="0b99d-204">对"权限"选项卡AppManifest.xml文件进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="0b99d-204">This change is made to the AppManifest.xml file in the Permissions tab:</span></span>

|<span data-ttu-id="0b99d-205">范围</span><span class="sxs-lookup"><span data-stu-id="0b99d-205">Scope</span></span>|<span data-ttu-id="0b99d-206">权限</span><span class="sxs-lookup"><span data-stu-id="0b99d-206">Permission</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b99d-207">多个 Projects (Project Server) </span><span class="sxs-lookup"><span data-stu-id="0b99d-207">Multiple Projects (Project Server)</span></span>  <br/> |<span data-ttu-id="0b99d-208">阅读</span><span class="sxs-lookup"><span data-stu-id="0b99d-208">Read</span></span>  <br/> |
   
<span data-ttu-id="0b99d-209">在设置应用程序作用域后保存文件。</span><span class="sxs-lookup"><span data-stu-id="0b99d-209">Save the file after setting the application scope.</span></span> <span data-ttu-id="0b99d-210">否则，不会从服务返回任何数据。</span><span class="sxs-lookup"><span data-stu-id="0b99d-210">Otherwise, no data will be returned from the service.</span></span> 
  
### <a name="link-the-jsom-library"></a><span data-ttu-id="0b99d-211">链接 JSOM 库</span><span class="sxs-lookup"><span data-stu-id="0b99d-211">Link the JSOM library</span></span>

<span data-ttu-id="0b99d-212">运行时Project Online库PS.jsPS.debug.js，由 Project Online 提供，并且始终是最新版本。</span><span class="sxs-lookup"><span data-stu-id="0b99d-212">The runtime Project Online libraries, PS.js and PS.debug.js, are provided by Project Online and are always the most recent version.</span></span> <span data-ttu-id="0b99d-213">使用 JSOM 的 JavaScript 加载项必须与这些库之一链接。</span><span class="sxs-lookup"><span data-stu-id="0b99d-213">JavaScript add-ins that use JSOM must link with one of these libraries.</span></span> <span data-ttu-id="0b99d-214">链接定义将添加到 Default.aspx 文件中。</span><span class="sxs-lookup"><span data-stu-id="0b99d-214">The linking definitions are added in the Default.aspx file.</span></span> <span data-ttu-id="0b99d-215">用于命令和PS.js/或PS.debug.js是位于文件的代码的一App.js部分。</span><span class="sxs-lookup"><span data-stu-id="0b99d-215">The commands to use the PS.js and/or PS.debug.js are part of the code located in the App.js file.</span></span>
  
<span data-ttu-id="0b99d-216">在元素中添加以下PS.js或PS.debug.js定义，该元素遵循 `<asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead"` "SharePoint：ScriptLink"sp.js。</span><span class="sxs-lookup"><span data-stu-id="0b99d-216">Add the following command for PS.js or PS.debug.js definition in the  `<asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead"` element following the "SharePoint:ScriptLink" for sp.js.</span></span> 
  
```js
<SharePoint:ScriptLink name="PS.js" runat="server" OnDemand="false" LoadAfterUI="true" Localizable="false" />
```

> [!NOTE]
> <span data-ttu-id="0b99d-217">属性 **的 OnDemand** PS.js或PS.debug.js设置为 **false**。</span><span class="sxs-lookup"><span data-stu-id="0b99d-217">The **OnDemand** attribute for PS.js or PS.debug.js set to **false**.</span></span> 
  
### <a name="add-ui-elements-to-the-add-in"></a><span data-ttu-id="0b99d-218">将 UI 元素添加到外接程序</span><span class="sxs-lookup"><span data-stu-id="0b99d-218">Add UI elements to the add-in</span></span>

<span data-ttu-id="0b99d-219">示例外接程序由几个组件组成。</span><span class="sxs-lookup"><span data-stu-id="0b99d-219">The example add-in consists of a few components.</span></span> <span data-ttu-id="0b99d-220">静态元素说明位于 Default.aspx 文件中。</span><span class="sxs-lookup"><span data-stu-id="0b99d-220">Static element descriptions are located in the Default.aspx file.</span></span> <span data-ttu-id="0b99d-221">所有组件的动态元素说明和代码都位于App.js文件中。</span><span class="sxs-lookup"><span data-stu-id="0b99d-221">Dynamic element descriptions and code for all components are located in the App.js file.</span></span> <span data-ttu-id="0b99d-222">有关组件的评论，请参阅源代码列表。</span><span class="sxs-lookup"><span data-stu-id="0b99d-222">For comments regarding the components, refer to the source code listings.</span></span> <span data-ttu-id="0b99d-223">下面是外接程序中的 UI 组件列表：</span><span class="sxs-lookup"><span data-stu-id="0b99d-223">Here is a list of the UI components in the add-in:</span></span>
  
- <span data-ttu-id="0b99d-224">标题</span><span class="sxs-lookup"><span data-stu-id="0b99d-224">Title</span></span>
    
- <span data-ttu-id="0b99d-225">介绍性动词</span><span class="sxs-lookup"><span data-stu-id="0b99d-225">Introductory verbiage</span></span>
    
- <span data-ttu-id="0b99d-226">用于从表中删除任务的按钮</span><span class="sxs-lookup"><span data-stu-id="0b99d-226">Button to remove tasks from the table</span></span>
    
- <span data-ttu-id="0b99d-227">列出项目 ID 和名称以及任务信息的表。</span><span class="sxs-lookup"><span data-stu-id="0b99d-227">Table that lists the project ID and name, and the task information.</span></span>
    
- <span data-ttu-id="0b99d-228">任务按钮 (每个将任务数据导入到) 的项目中克隆一次。</span><span class="sxs-lookup"><span data-stu-id="0b99d-228">Tasks Button (cloned once for each project) that imports task data into the table.</span></span>
    
<span data-ttu-id="0b99d-229">有关用户界面的详细信息（如项目表的标题和标题部分），请参阅 Default.aspx 项目文件。</span><span class="sxs-lookup"><span data-stu-id="0b99d-229">For details of the user interface, such as the title and the header portion of the project table, see the Default.aspx project file.</span></span>
  
### <a name="initialize-and-connect-to-the-host-system"></a><span data-ttu-id="0b99d-230">初始化并连接到主机系统</span><span class="sxs-lookup"><span data-stu-id="0b99d-230">Initialize and connect to the host system</span></span>

<span data-ttu-id="0b99d-231">The App.js file contains the JavaScript code.</span><span class="sxs-lookup"><span data-stu-id="0b99d-231">The App.js file contains the JavaScript code.</span></span> <span data-ttu-id="0b99d-232">外接程序在浏览器中PS.js，然后调用 initializePage 函数。</span><span class="sxs-lookup"><span data-stu-id="0b99d-232">The add-in loads PS.js in the browser, and then calls the initializePage function.</span></span> <span data-ttu-id="0b99d-233">InitializePage 检索到 Project Online 的上下文，并启动 loadProjects 函数。</span><span class="sxs-lookup"><span data-stu-id="0b99d-233">InitializePage retrieves a context to the Project Online endpoint and starts the loadProjects function.</span></span>
  
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

### <a name="retrieve-the-projects"></a><span data-ttu-id="0b99d-234">检索项目</span><span class="sxs-lookup"><span data-stu-id="0b99d-234">Retrieve the projects</span></span>

<span data-ttu-id="0b99d-235">loadProjects 函数查询服务中的项目名称和 ID。</span><span class="sxs-lookup"><span data-stu-id="0b99d-235">The loadProjects function queries the service for the project names and IDs.</span></span> 
  
<span data-ttu-id="0b99d-236">应用程序检索项目名称和项目 ID。有关项目的其他信息可用，可通过修改 load 方法以显式标识要检索的属性来访问该信息。</span><span class="sxs-lookup"><span data-stu-id="0b99d-236">The application retrieves the project name and project Id. Other information about the project is available and can be accessed by modifying the load method to identify explicitly the properties to retrieve.</span></span> <span data-ttu-id="0b99d-237">代码中提供了一个示例作为注释。</span><span class="sxs-lookup"><span data-stu-id="0b99d-237">An example is provided in the code as a comment.</span></span> 
  
<span data-ttu-id="0b99d-238">如果查询成功，加载项将继续调用 displayProjects。</span><span class="sxs-lookup"><span data-stu-id="0b99d-238">If the query succeeds, the add-in continues by calling displayProjects.</span></span> 
  
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

### <a name="display-the-projects"></a><span data-ttu-id="0b99d-239">显示项目</span><span class="sxs-lookup"><span data-stu-id="0b99d-239">Display the projects</span></span>

<span data-ttu-id="0b99d-240">displayProjects 函数创建一个表（每个项目一行）和一个按钮以显示特定项目的任务。</span><span class="sxs-lookup"><span data-stu-id="0b99d-240">The displayProjects function creates a table, one row per project, and a button to show the tasks for the specific project.</span></span> 
  
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
> <span data-ttu-id="0b99d-241">while 循环访问 ID 和 name 属性。</span><span class="sxs-lookup"><span data-stu-id="0b99d-241">The while loop accesses the ID and name properties.</span></span> <span data-ttu-id="0b99d-242">这与调用函数（反过来又访问相同属性）的源代码项目略有不同。</span><span class="sxs-lookup"><span data-stu-id="0b99d-242">This is slightly different than the source code project that calls a function that, in turn, accesses the same properties.</span></span> 
  
### <a name="display-the-tasks-for-a-project"></a><span data-ttu-id="0b99d-243">显示项目的任务</span><span class="sxs-lookup"><span data-stu-id="0b99d-243">Display the tasks for a project</span></span>

<span data-ttu-id="0b99d-244">虽然任务是加载项的一部分，但任务不是初始加载的一部分。</span><span class="sxs-lookup"><span data-stu-id="0b99d-244">The tasks, while part of the add-in, are not part of the initial loading.</span></span> <span data-ttu-id="0b99d-245">如果用户对与项目关联的任务感兴趣，单击"显示任务"按钮将导致任务使用 btnLoadTasks 事件处理程序显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="0b99d-245">If the user is interested in the tasks associated with a project, clicking the "Show Tasks" button causes the tasks to display in the list using the btnLoadTasks event handler.</span></span> 
  
<span data-ttu-id="0b99d-246">btnLoadTasks 事件处理程序（具有相应的项目 ID）从服务器请求指定项目的任务。</span><span class="sxs-lookup"><span data-stu-id="0b99d-246">The btnLoadTasks event handler, with the appropriate project ID, requests the tasks for the specified project from the server.</span></span> <span data-ttu-id="0b99d-247">检索到后，btnLoadTasks 将传递任务列表以显示任务，以在屏幕上显示任务。</span><span class="sxs-lookup"><span data-stu-id="0b99d-247">Once retrieved, btnLoadTasks passes the task list to displayTasks to present the tasks onscreen.</span></span>
  
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

<span data-ttu-id="0b99d-248">displayTasks 函数显示在项目项正下方与指定项目关联的任务。</span><span class="sxs-lookup"><span data-stu-id="0b99d-248">The displayTasks function displays the tasks associated with a specified project immediately beneath the project entry.</span></span>
  
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
> <span data-ttu-id="0b99d-249">while 循环访问任务 ID 和名称属性。</span><span class="sxs-lookup"><span data-stu-id="0b99d-249">The while loop accesses the task ID and name properties.</span></span> <span data-ttu-id="0b99d-250">这与调用函数（反过来又访问相同属性）的源代码项目略有不同。</span><span class="sxs-lookup"><span data-stu-id="0b99d-250">This is slightly different than the source code project that calls a function that, in turn, accesses the same properties.</span></span> 
  
<span data-ttu-id="0b99d-251">以下是单个项目的任务的示例输出。</span><span class="sxs-lookup"><span data-stu-id="0b99d-251">Sample output for the tasks of a single project follows.</span></span>
  
<span data-ttu-id="0b99d-252">![显示项目任务输出]的屏幕截图(media/f6500a3f-000b-4f3e-9be6-9a74d0bea15e.png "显示项目任务输出的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="0b99d-252">![Screen shot showing the output for a project task](media/f6500a3f-000b-4f3e-9be6-9a74d0bea15e.png "Screen shot showing the output for a project task")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b99d-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b99d-253">See also</span></span>

<span data-ttu-id="0b99d-254">有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/en-us/project)。</span><span class="sxs-lookup"><span data-stu-id="0b99d-254">For documentation and samples related to Project Online and application development using CSOM, see the [Project Development Portal](https://developer.microsoft.com/en-us/project).</span></span>
    


