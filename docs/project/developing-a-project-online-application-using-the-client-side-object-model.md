---
title: 使用客户端对象模型开发 Project Online 应用程序
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
ms.assetid: 5740d0b2-5d36-40e4-9e83-577cb186359f
description: 本文介绍了如何使用 .NET Framework 4.0 开发 Microsoft Project Online 桌面应用程序。 本文中所述的应用程序将检索托管服务器的信息。
localization_priority: Priority
ms.openlocfilehash: 3d3c2dd5b896c10dab9a0494288f38610cbc99e1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712937"
---
# <a name="developing-a-project-online-application-using-the-client-side-object-model"></a><span data-ttu-id="c05ab-104">使用客户端对象模型开发 Project Online 应用程序</span><span class="sxs-lookup"><span data-stu-id="c05ab-104">Developing a Project Online application using the client-side object model</span></span>

<span data-ttu-id="c05ab-105">本文介绍了如何使用 .NET Framework 4.0 开发 Microsoft Project Online 桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="c05ab-105">This article describes Microsoft Project Online application development for desktop applications using the .NET Framework 4.0.</span></span> <span data-ttu-id="c05ab-106">本文中所述的应用程序将检索托管服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="c05ab-106">The application described in this article retrieves information from the hosting server.</span></span> 
  
## <a name="background"></a><span data-ttu-id="c05ab-107">背景</span><span class="sxs-lookup"><span data-stu-id="c05ab-107">Background</span></span>

<span data-ttu-id="c05ab-108">在 20 世纪 90 年代早期，Microsoft Project 已作为桌面应用程序推出。</span><span class="sxs-lookup"><span data-stu-id="c05ab-108">Microsoft Project started as desktop application in the early 1990's.</span></span> <span data-ttu-id="c05ab-109">如今，Project 要多得多，其多个不同的版本就是很好的证明：</span><span class="sxs-lookup"><span data-stu-id="c05ab-109">Today, Project is much more, as its several varieties attest:</span></span>
  
- <span data-ttu-id="c05ab-110">Project 标准版桌面应用程序可作为单独的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="c05ab-110">Project standard edition is a desktop application that runs as a stand-alone application.</span></span>
    
- <span data-ttu-id="c05ab-111">Project 专业版桌面应用程序可更大规模地与服务器交互和共享数据，以及执行 Project 标准版中的功能。</span><span class="sxs-lookup"><span data-stu-id="c05ab-111">Project professional edition is a desktop application that can interact and share data with a server on a larger scale, as well as perform the functionality found in Project standard edition.</span></span>
    
- <span data-ttu-id="c05ab-112">Project Online 是一种 Microsoft 托管的服务，可为公司提供 PMO 级解决方案，用于协调和管理项目、计划和项目组合。</span><span class="sxs-lookup"><span data-stu-id="c05ab-112">Project Online is a Microsoft-hosted service that provides companies with a PMO-level solution to coordinate and manage projects, programs, and portfolios.</span></span> <span data-ttu-id="c05ab-113">Project Online 是一款不同于桌面版本的产品，它可以在整个项目周期内维护和跟踪项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c05ab-113">A different offering than the desktop editions, Project Online can maintain and track project details throughout the life of a project.</span></span> 
    
- <span data-ttu-id="c05ab-114">Project Server 是一款企业托管的服务，企业可以通过它管理和保护含有项目、计划和项目组合信息的服务器。</span><span class="sxs-lookup"><span data-stu-id="c05ab-114">Project Server is an enterprise-hosted service in which the enterprise manages and secures the server containing project, program, and portfolio information.</span></span> <span data-ttu-id="c05ab-115">Project Server 可以保护内部服务器，因此，它可以提供外部托管的 Project Online 所具有的的项目、计划和项目组合功能，并且可以实现更大程度的自定义。</span><span class="sxs-lookup"><span data-stu-id="c05ab-115">Project Server, by virtue of securing the server in-house, offers the project, program, and portfolio oriented features of externally-hosted Project Online with a greater capacity for customization.</span></span>
    
<span data-ttu-id="c05ab-116">Project Online 具有三个在线 API 集：客户端对象模型 (CSOM)、JavaScript 对象模型 (JSOM) 和表述性状态转移 (REST)。</span><span class="sxs-lookup"><span data-stu-id="c05ab-116">Project Online has three online API sets: Client-side Object Model (CSOM), JavaScript Object Model (JSOM), and Representational State Transfer (REST).</span></span> 
  
- <span data-ttu-id="c05ab-117">开发与 Project Online 租户交互的 Windows 应用程序时，.NET CSOM 实施是首选界面。</span><span class="sxs-lookup"><span data-stu-id="c05ab-117">The .NET CSOM implementation is the preferred interface when developing Windows applications that interact with Project Online tenants.</span></span> <span data-ttu-id="c05ab-118">以用户为中心的应用程序的典型环境包括 Windows 桌面和 Microsoft Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="c05ab-118">Typical environments for user-centric applications include Windows desktops and Microsoft Surface devices.</span></span> <span data-ttu-id="c05ab-119">使用 .NET CSOM 编写的后端应用程序可连接至其他服务器，以获取 Project Online 外部业务逻辑和数据源。</span><span class="sxs-lookup"><span data-stu-id="c05ab-119">Back-end applications written with .NET CSOM can connect to other servers for business logic and data sources that are external to Project Online.</span></span> <span data-ttu-id="c05ab-120">至 Project Online 的检索请求使用类似于 LINQ 的查询系统，该系统在基本检索功能的基础上提供了多项增强功能。</span><span class="sxs-lookup"><span data-stu-id="c05ab-120">Retrieval requests to Project Online use a LINQ-like query system that offers several enhancements over basic retrieval functions.</span></span>
    
- <span data-ttu-id="c05ab-121">JavaScript 对象模型 (JSOM) 界面为 Project Online 加载项提供跨浏览器支持。加载项是指存储于 Project Online 租户中的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c05ab-121">The JavaScript Object Model (JSOM) interface provides cross-browser support for Project Online Add-ins. An add-in is a web application that is stored in the Project Online tenant.</span></span> <span data-ttu-id="c05ab-122">当用户想要运行加载项时，加载项代码将在用户计算机上的浏览器中下载和运行。</span><span class="sxs-lookup"><span data-stu-id="c05ab-122">When a user wants to run an add-in, the code for the add-in downloads and runs in the browser on the user machine.</span></span> 
    
- <span data-ttu-id="c05ab-123">REST/Odata 模型提供基于 HTTP 的通信，对于非 Windows 环境中的应用程序，推荐使用此界面。</span><span class="sxs-lookup"><span data-stu-id="c05ab-123">The REST/Odata model provides HTTP-based communication, This interface is recommended for applications in non-Windows environments.</span></span> <span data-ttu-id="c05ab-124">通信终结点为 Project Web 应用程序 (PWA) 网站中的对象。</span><span class="sxs-lookup"><span data-stu-id="c05ab-124">Communication endpoints are the objects in the Project Web Application (PWA) site.</span></span> <span data-ttu-id="c05ab-125">结果提供正常 HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="c05ab-125">Results provide normal HTTP status codes.</span></span>
    
<span data-ttu-id="c05ab-126">本文重点介绍使用 .NET CSOM 界面的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c05ab-126">This article focuses on an application that uses the .NET CSOM interface.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="c05ab-127">先决条件</span><span class="sxs-lookup"><span data-stu-id="c05ab-127">Prerequisites</span></span>

<span data-ttu-id="c05ab-128">从运行 Windows 10 的基本系统入手，并添加以下项：</span><span class="sxs-lookup"><span data-stu-id="c05ab-128">Start with a base system running Windows 10, and add the following items:</span></span>
  
- <span data-ttu-id="c05ab-129">.Net Framework 4.0 或更高版本 -- 使用完整的框架。</span><span class="sxs-lookup"><span data-stu-id="c05ab-129">.Net Framework 4.0 or later -- Use the complete framework.</span></span> <span data-ttu-id="c05ab-130">下载网站为 https://msdn.microsoft.com/vstudio/aa496123.aspx。</span><span class="sxs-lookup"><span data-stu-id="c05ab-130">The download site is https://msdn.microsoft.com/vstudio/aa496123.aspx.</span></span>
    
- <span data-ttu-id="c05ab-131">Visual Studio 2013 或更高版本 -- 接受任何版本。</span><span class="sxs-lookup"><span data-stu-id="c05ab-131">Visual Studio 2013 or later -- Any edition is acceptable.</span></span> <span data-ttu-id="c05ab-132">Visual Studio Community 2015 版用于开发实例应用程序。</span><span class="sxs-lookup"><span data-stu-id="c05ab-132">The community edition of Visual Studio 2015 was used to develop the sample application.</span></span> <span data-ttu-id="c05ab-133">Community 版可在 https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx 上获取。</span><span class="sxs-lookup"><span data-stu-id="c05ab-133">The community edition is available at https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx.</span></span>
    
- <span data-ttu-id="c05ab-134">SharePoint 客户端组件 SDK -- Project Online 和 Project Server 位于 SharePoint 和 SharePoint 程序集之上。</span><span class="sxs-lookup"><span data-stu-id="c05ab-134">SharePoint Client Components SDK -- Project Online and Project Server sit on top of SharePoint, and SharePoint assemblies.</span></span> <span data-ttu-id="c05ab-135">Visual Studio Professional 和 Enterprise 版中包含 SharePoint 客户端组件。</span><span class="sxs-lookup"><span data-stu-id="c05ab-135">The SharePoint Client Components are included in Visual Studio Professional and Enterprise editions.</span></span> <span data-ttu-id="c05ab-136">如果使用 Visual Studio Community 版，则可在以下网站上获取最新版 Office 开发人员工具 SDK：https://www.microsoft.com/en-us/download/details.aspx?id=35585</span><span class="sxs-lookup"><span data-stu-id="c05ab-136">If you use Visual Studio Community edition, the latest version of the Office Developer Tools SDK is available at the following site: https://www.microsoft.com/en-us/download/details.aspx?id=35585.</span></span>
    
- <span data-ttu-id="c05ab-137">Project Online 帐户 -- 可通过该账户访问托管网站。</span><span class="sxs-lookup"><span data-stu-id="c05ab-137">A Project Online account -- This provides access to the hosting site.</span></span> <span data-ttu-id="c05ab-138">有关获取 Project Online 帐户的详细信息，请参阅 https://products.office.com/en-us/Project/project-online-portfolio-management</span><span class="sxs-lookup"><span data-stu-id="c05ab-138">For more information about obtaining a Project Online account, see https://products.office.com/en-us/Project/project-online-portfolio-management.</span></span>
    
- <span data-ttu-id="c05ab-139">托管网站上已填充信息的项目</span><span class="sxs-lookup"><span data-stu-id="c05ab-139">Projects on the hosting site that are populated with information</span></span>
    
> [!NOTE]
> <span data-ttu-id="c05ab-140">要使用的正确框架为标准 .NET Framework（4.0 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="c05ab-140">The standard .NET Framework (4.0 or later) is the correct framework to use.</span></span> <span data-ttu-id="c05ab-141">请勿不使用 .NET Framework 4 Client Profile。</span><span class="sxs-lookup"><span data-stu-id="c05ab-141">Do not use the .NET Framework 4 Client Profile.</span></span> 
  
## <a name="develop-the-application"></a><span data-ttu-id="c05ab-142">开发应用程序</span><span class="sxs-lookup"><span data-stu-id="c05ab-142">Develop the application</span></span>

<span data-ttu-id="c05ab-143">开发 SharePoint 桌面应用程序时，首选界面为 Project 客户端对象模型 (CSOM)。</span><span class="sxs-lookup"><span data-stu-id="c05ab-143">In developing a desktop application for SharePoint, the preferred interface is the Project client side object model (CSOM).</span></span> 
  
<span data-ttu-id="c05ab-144">可以在 https://github.com/OfficeDev/Project-CSOM-List-Projects-Tasks 上下载完整的示例。</span><span class="sxs-lookup"><span data-stu-id="c05ab-144">You can download the completed sample at https://github.com/OfficeDev/Project-CSOM-List-Projects-Tasks.</span></span>
  
<span data-ttu-id="c05ab-145">前两个主题涵盖了基本问题：创建具有适当命名空间和程序集的 Visual Studio 项目；访问托管服务器。</span><span class="sxs-lookup"><span data-stu-id="c05ab-145">The first two topics cover basic issues: creating a Visual Studio project with appropriate namespaces and assemblies, and accessing the hosting server.</span></span> <span data-ttu-id="c05ab-146">其余主题介绍通过 CSOM 检索一个和多个对象中的信息。</span><span class="sxs-lookup"><span data-stu-id="c05ab-146">The remaining topics deal with retrieving information through the CSOM, from one and many objects.</span></span> 
  
<span data-ttu-id="c05ab-147">对于客户端应用程序，检索主机中的信息涉及两个操作步骤。</span><span class="sxs-lookup"><span data-stu-id="c05ab-147">Retrieving information from the host is a two-action process from client applications.</span></span> <span data-ttu-id="c05ab-148">首先，应用程序向服务器指定并发送一个或多个检索请求。</span><span class="sxs-lookup"><span data-stu-id="c05ab-148">First, the application specifies and sends one or more retrieval requests to the server.</span></span> <span data-ttu-id="c05ab-149">其次，应用程序向服务器发送执行所提交查询的通知。</span><span class="sxs-lookup"><span data-stu-id="c05ab-149">Second, the application issues a notification to the server to execute the submitted queries.</span></span> <span data-ttu-id="c05ab-150">服务器通过向客户端发送查询结果来响应。</span><span class="sxs-lookup"><span data-stu-id="c05ab-150">The server responds by sending the query results to the client.</span></span>
  
### <a name="set-up-the-visual-studio-project"></a><span data-ttu-id="c05ab-151">设置 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="c05ab-151">Step 1: Set up the Visual Studio project</span></span>

<span data-ttu-id="c05ab-152">应用程序设置由三个部分组成：新建项目、链接相应的程序集和声明所需命名空间。</span><span class="sxs-lookup"><span data-stu-id="c05ab-152">The application setup consists of creating a new project, linking the appropriate assemblies and declaring the needed namespaces.</span></span> <span data-ttu-id="c05ab-153">Visual Studio 提供有多种类型的开发项目。</span><span class="sxs-lookup"><span data-stu-id="c05ab-153">Visual Studio presents several types of development projects.</span></span> 
  
#### <a name="select-a-visual-studio-project"></a><span data-ttu-id="c05ab-154">选择 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="c05ab-154">Select a Visual Studio project</span></span>

1. <span data-ttu-id="c05ab-155">在“开始”页上启动 Visual Studio 并选择“**启动新项目**”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-155">Launch Visual Studio and select **Start A New Project** on the Start Page.</span></span> 
    
   <span data-ttu-id="c05ab-156">“新建项目”对话框显示可用应用程序模板以及任意选定模板中的数据字段。</span><span class="sxs-lookup"><span data-stu-id="c05ab-156">The New Project dialog displays available application templates, and data fields for any selected template.</span></span> 
    
2. <span data-ttu-id="c05ab-157">在此应用程序中，请指定以下项。</span><span class="sxs-lookup"><span data-stu-id="c05ab-157">For this application, specify the following items.</span></span> <span data-ttu-id="c05ab-158">屏幕上显示的关键字采用粗体属性：</span><span class="sxs-lookup"><span data-stu-id="c05ab-158">Keywords encountered on the screen have a bold attribute:</span></span>
    
   1. <span data-ttu-id="c05ab-159">从左侧窗格中的“已安装的模板”中，选择“**C#** => **Windows** => **经典桌面**”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-159">From the Installed templates in the left pane, select **C#** => **Windows** => **Classic desktop**.</span></span> 
    
   2. <span data-ttu-id="c05ab-160">在中间窗格顶部，选择“**.NET Framework 4**”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-160">At the top of the central pane, select **.NET Framework 4**.</span></span> 
    
   3. <span data-ttu-id="c05ab-161">从中间窗格的应用程序类型中，选择“**控制台应用程序**”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-161">From the application types in the central pane, choose **Console Application**.</span></span> 
    
   4. <span data-ttu-id="c05ab-162">在底部为项目指定名称和位置以及解决方案名称。</span><span class="sxs-lookup"><span data-stu-id="c05ab-162">In the bottom section, specify a name and location for the project, and a solution name.</span></span> 
    
   5. <span data-ttu-id="c05ab-163">此外，在底部选中“**创建解决方案的目录**”复选框。</span><span class="sxs-lookup"><span data-stu-id="c05ab-163">Also in the bottom section, check the **Create directory for solution** box.</span></span> 
    
3. <span data-ttu-id="c05ab-164">单击“**确定**”以创建初始项目。</span><span class="sxs-lookup"><span data-stu-id="c05ab-164">Click **OK** to create the workflow.</span></span> 
    
#### <a name="add-assemblies"></a><span data-ttu-id="c05ab-165">添加程序集</span><span class="sxs-lookup"><span data-stu-id="c05ab-165">Add assemblies</span></span>

<span data-ttu-id="c05ab-166">VS 解决方案需要使用 Project 2103 SDK 中的 ProjectServerClient 程序集、一些 SharePoint SDK 程序集和 .NET Framework System.Security 程序集。</span><span class="sxs-lookup"><span data-stu-id="c05ab-166">The VS solution needs the ProjectServerClient assembly from the Project 2103 SDK, a couple of assemblies from the SharePoint SDK, and the .NET Framework System.Security assembly.</span></span>
  
1. <span data-ttu-id="c05ab-167">在 VS 解决方案资源管理器中，右键单击“引用”条目，然后从快捷菜单中选择“**添加引用…**”</span><span class="sxs-lookup"><span data-stu-id="c05ab-167">In the VS Solution Explorer, right-click the References entry, and select **Add Reference…**</span></span> <span data-ttu-id="c05ab-168">。</span><span class="sxs-lookup"><span data-stu-id="c05ab-168">from the shortcut menu.</span></span> 
    
2. <span data-ttu-id="c05ab-169">选中“**Microsoft.ProjectServer.Client.dll**”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-169">Check the **Microsoft.ProjectServer.Client.dll**.</span></span> 
    
   <span data-ttu-id="c05ab-170">如果需要，单击对话框底部的“**浏览…**”</span><span class="sxs-lookup"><span data-stu-id="c05ab-170">If needed, click the **Browse…**</span></span> <span data-ttu-id="c05ab-171">按钮并导航至 Project 2013 SDK 安装目录，以找到程序集。</span><span class="sxs-lookup"><span data-stu-id="c05ab-171">button at the bottom of the dialog and navigate to the Project 2013 SDK installation directory to locate the assembly.</span></span> 
    
3. <span data-ttu-id="c05ab-172">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-172">Click **OK**.</span></span> 
    
4. <span data-ttu-id="c05ab-173">将 PrjoctServer 客户端名称空间添加到 .cs 文件。</span><span class="sxs-lookup"><span data-stu-id="c05ab-173">Add the PrjoctServer Client namespace to the .cs file.</span></span>
    
   ```cs
    using Microsoft.ProjectServer.Client;
   ```

<span data-ttu-id="c05ab-174">使用 NuGet 程序包管理器控制台添加 SharePoint 2013 SDK 程序集。</span><span class="sxs-lookup"><span data-stu-id="c05ab-174">Add the SharePoint 2013 SDK assemblies using the NuGet Package Manager Console.</span></span> 
  
1. <span data-ttu-id="c05ab-175">从 VS“工具”菜单中，单击以下菜单：**“工具”=\>“NuGet 程序包管理器”=\>“程序包管理器控制台”**。</span><span class="sxs-lookup"><span data-stu-id="c05ab-175">From the VS Tools menu, click the following menus: **Tools =\> NuGet Package Manager =\> Package Manager Console**.</span></span> 
    
2. <span data-ttu-id="c05ab-176">在“程序包管理器控制台”中，输入以下命令并按 \<ENTER\>：</span><span class="sxs-lookup"><span data-stu-id="c05ab-176">In the Package Manager Console, enter the following command and press \<ENTER\>:</span></span>
    
   ```cs
    Install-Package Microsoft.SharePointOnline.CSOM
   ```

   <span data-ttu-id="c05ab-177">“**程序包管理器控制台**”提供命令结果描述，“VS 解决方案资源管理器”的项目首选项中显示 SharePoint 程序集。</span><span class="sxs-lookup"><span data-stu-id="c05ab-177">The **Package Manager Console** provides a description of the command results; and, the VS Solution Explorer displays the SharePoint assemblies in the project references.</span></span> 
    
3. <span data-ttu-id="c05ab-178">价格命名空间添加到 .cs 文件：</span><span class="sxs-lookup"><span data-stu-id="c05ab-178">Add the namespaces to the .cs file:</span></span>
    
   ```cs
    using Microsoft.SharePoint.Client;
   ```

<span data-ttu-id="c05ab-179">System.Security 程序集是 .NET Framework 的一部分，与框架一起安装。</span><span class="sxs-lookup"><span data-stu-id="c05ab-179">The System.Security assembly is part of .NET Framework and was installed with the framework.</span></span> <span data-ttu-id="c05ab-180">示例应用程序需要使用另一个命名空间，该命名空间提供了一个至托管系统的加密字符串，以便进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c05ab-180">The sample application needs one more namespace that provides an encrypted string to the hosting system for authentication.</span></span> <span data-ttu-id="c05ab-181">通过身份验证后，应用程序即可访问托管系统上的项目。</span><span class="sxs-lookup"><span data-stu-id="c05ab-181">Once authenticated, the application can access projects on the hosting system.</span></span> <span data-ttu-id="c05ab-182">通过以下方式将 System.Security 命名空间添加到 .cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="c05ab-182">Add the System.Security namespace to the .cs file in this way:</span></span>
  
1. <span data-ttu-id="c05ab-183">在 VS 解决方案资源管理器中，右键单击“引用”条目，然后从快捷菜单中选择“**添加引用…**”</span><span class="sxs-lookup"><span data-stu-id="c05ab-183">In the VS Solution Explorer, right-click the References entry, and select **Add Reference…**</span></span> <span data-ttu-id="c05ab-184">。</span><span class="sxs-lookup"><span data-stu-id="c05ab-184">from the shortcut menu.</span></span> 
    
2. <span data-ttu-id="c05ab-185">在“引用管理器”对话框的左侧窗格中，选择 **“程序集”=\>“框架”**，然后选中“**System.Security**”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-185">Select **Assemblies =\> Framework** in the left pane of the References Manager dialog, then check **System.Security**.</span></span> 
    
3. <span data-ttu-id="c05ab-186">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-186">Click **OK**.</span></span> 
    
4. <span data-ttu-id="c05ab-187">将 System.Security 命名空间添加到 .cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="c05ab-187">Add the System.Security namespace to the .cs file:</span></span>
    
   ```cs
    using System.Security;
   ```

<span data-ttu-id="c05ab-188">.cs 文件的开头应包含以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="c05ab-188">The start of the .cs file should contain the following namespaces:</span></span>
  
- <span data-ttu-id="c05ab-189">System</span><span class="sxs-lookup"><span data-stu-id="c05ab-189">System</span></span>
    
- <span data-ttu-id="c05ab-190">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="c05ab-190">System.Collections.Generic</span></span>
    
- <span data-ttu-id="c05ab-191">System.Linq</span><span class="sxs-lookup"><span data-stu-id="c05ab-191">System.Linq</span></span>
    
- <span data-ttu-id="c05ab-192">System.Test</span><span class="sxs-lookup"><span data-stu-id="c05ab-192">System.Test</span></span>
    
- <span data-ttu-id="c05ab-193">Microsoft.ProjectServer.Client</span><span class="sxs-lookup"><span data-stu-id="c05ab-193">Microsoft.ProjectServer.Client</span></span>
    
- <span data-ttu-id="c05ab-194">Microsoft.SharePoint.Client</span><span class="sxs-lookup"><span data-stu-id="c05ab-194">Microsoft.SharePoint.Client</span></span>
    
- <span data-ttu-id="c05ab-195">System.Security</span><span class="sxs-lookup"><span data-stu-id="c05ab-195">System.Security</span></span>
    
### <a name="connect-to-the-host-system"></a><span data-ttu-id="c05ab-196">连接至主机系统</span><span class="sxs-lookup"><span data-stu-id="c05ab-196">Connect to the host system</span></span>

<span data-ttu-id="c05ab-197">Project Online 是一款 SharePoint 应用程序，因此，使用 SharePoint 身份验证是正确方法。</span><span class="sxs-lookup"><span data-stu-id="c05ab-197">Project Online is a SharePoint application, so using SharePoint authentication is the correct approach.</span></span> <span data-ttu-id="c05ab-198">以下代码片段准备访问托管环境。</span><span class="sxs-lookup"><span data-stu-id="c05ab-198">The following code fragment prepares to access the hosted environment.</span></span>
  
```cs
    class Program
    {
        private static ProjectContext projContext;
        static void Main (string[] args)
        {
            using (ProjectContext projContext = new ProjectContext("https://Contoso.sharepoint.com/sites/pwa"))
            {
                SecureString password - new SecureString();
                foreach (char c in "password".ToCharArray()) password.AppendChar(c);
                //Using SharePoint method to load Credentials
                projContext.Credentials = new SharePointOnlineCredentials("sarad@Contoso.onmicrosoft.com", password);

```

<span data-ttu-id="c05ab-199">访问托管环境的准备工作包括以下事项：</span><span class="sxs-lookup"><span data-stu-id="c05ab-199">Preparations to access the hosted environment include the following items:</span></span>
  
1. <span data-ttu-id="c05ab-200">为项目创建上下文对象 -- 这包含在前面代码片段的以下代码中。</span><span class="sxs-lookup"><span data-stu-id="c05ab-200">Create a context object for the projects -- this is contained in the following code of the preceding code fragment.</span></span> 
    
   ```cs
    private static ProjectContext projContext;
    
   ```

   <span data-ttu-id="c05ab-201">其他组件将继承此上下文，从而使得系统能够管理 Project 对象模型的上下文。</span><span class="sxs-lookup"><span data-stu-id="c05ab-201">The context is inherited by other components, allowing the system to manage the context of the Project object model.</span></span>
    
2. <span data-ttu-id="c05ab-202">识别主机网站 -- 此操作在前面代码片段的以下代码中完成。</span><span class="sxs-lookup"><span data-stu-id="c05ab-202">Identify the host site -- this is done in the following code from the preceding code fragment.</span></span>
    
   ```cs
    using (ProjectContext projContext = new ProjectContext("https://Contoso.sharepoint.com/sites/pwa"))
   ```

   <span data-ttu-id="c05ab-203">实例化项目上下文时，应用程序需要提供项目网站集的根网站。</span><span class="sxs-lookup"><span data-stu-id="c05ab-203">When instantiating the projects context, the application needs to provide the root of the Projects site collection.</span></span> <span data-ttu-id="c05ab-204">应用程序使用项目根网站的 URL 子字符串。</span><span class="sxs-lookup"><span data-stu-id="c05ab-204">The application uses a substring of the URL of the root of the Projects.</span></span> <span data-ttu-id="c05ab-205">在下面的示例图中，用红色矩形突出显示了此位置的快照。</span><span class="sxs-lookup"><span data-stu-id="c05ab-205">A snapshot of this location is highlighted with a red rectangle in the following illustration.</span></span> <span data-ttu-id="c05ab-206">身份验证需要从开头到子字符串“pwa”的字符串。</span><span class="sxs-lookup"><span data-stu-id="c05ab-206">The authentication needs the string from its start through the substring "pwa".</span></span> <span data-ttu-id="c05ab-207">在代码列表中，应用程序使用字符串“https://XXXXXXXX.sharepoint.com/sites/pwa”。</span><span class="sxs-lookup"><span data-stu-id="c05ab-207">In the code listing, the application uses the string "https://XXXXXXXX.sharepoint.com/sites/pwa".</span></span>
        
   <span data-ttu-id="c05ab-208">![红色边框内的项目网站集的 URL 屏幕截图。](media/d48c4894-5dba-46b6-886a-3c59bfb83c4d.png "红色边框内的项目网站集的 URL 屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="c05ab-208">![Screen shot of the URL of the Projects site collection within a red border.](media/d48c4894-5dba-46b6-886a-3c59bfb83c4d.png "Screen shot of the URL of the Projects site collection within a red border")</span></span>
  
3. <span data-ttu-id="c05ab-209">将密码置于安全的字符串中 -- 此操作在前面代码片段的以下代码中完成。</span><span class="sxs-lookup"><span data-stu-id="c05ab-209">Place the password in a secure string -- this is done in the following code from the preceding code fragment.</span></span>
    
   ```cs
    SecureString password - new SecureString();
    foreach (char c in "password".ToCharArray()) password.AppendChar(c);
    
   ```

   <span data-ttu-id="c05ab-210">密码和用户帐户是访问主机网站的凭据。</span><span class="sxs-lookup"><span data-stu-id="c05ab-210">The password and user account are the credentials to access the host site.</span></span> 
    
4. <span data-ttu-id="c05ab-211">将用户帐户和密码添加到上下文对象的凭据部分 -- 此操作在前面代码片段的以下代码中完成。</span><span class="sxs-lookup"><span data-stu-id="c05ab-211">Add the user account and password to the credentials portion of the context object -- this is done in the following code from the preceding code fragment.</span></span>
    
   ```cs
    projContext.Credentials = new SharePointOnlineCredentials("sarad@Contoso.onmicrosoft.com", password);
   ```

<span data-ttu-id="c05ab-212">已实例化的项目上下文已可供使用。</span><span class="sxs-lookup"><span data-stu-id="c05ab-212">The instantiated project context is ready to use.</span></span>
  
### <a name="list-all-published-projects"></a><span data-ttu-id="c05ab-213">列出所有已发布的项目</span><span class="sxs-lookup"><span data-stu-id="c05ab-213">List all published projects</span></span>

<span data-ttu-id="c05ab-214">Project Online 和 ProjectServer 使用代理来预服务器通信，以完成创建、报告、更新和删除 (CRUD) 操作。</span><span class="sxs-lookup"><span data-stu-id="c05ab-214">Project Online and ProjectServer use proxies to communicate with the server for create, report, update, and delete (CRUD) operations.</span></span> <span data-ttu-id="c05ab-215">与服务器通信时，主机/服务器高效处理请求，并让客户端执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c05ab-215">The host/server handles requests in an efficient manner and has the client perform the following actions in communicating with the server:</span></span>
  
1. <span data-ttu-id="c05ab-216">建立通信上下文。</span><span class="sxs-lookup"><span data-stu-id="c05ab-216">Establish a context for communication.</span></span> 
    
   <span data-ttu-id="c05ab-217">此上下文供项目集合以及通过继承获得的其他对象和集合（包括任务集合、工作分配集合、阶段对象和自定义字段）使用。</span><span class="sxs-lookup"><span data-stu-id="c05ab-217">The context is used by the projects collection, as well as other objects and collections through inheritance, including the tasks collection, assignments collection, the stage object, and custom fields.</span></span> 
    
2. <span data-ttu-id="c05ab-218">使用对象模型指定要检索的对象、集合或数据。</span><span class="sxs-lookup"><span data-stu-id="c05ab-218">Use the object model to specify an object to retrieve or from which to retrieve data.</span></span>
    
   <span data-ttu-id="c05ab-219">此步骤将 LINQ 用作查询或方法。</span><span class="sxs-lookup"><span data-stu-id="c05ab-219">This step uses LINQ as a query or as a method.</span></span> <span data-ttu-id="c05ab-220">规范用于控制检索的内容。</span><span class="sxs-lookup"><span data-stu-id="c05ab-220">The specification controls what you receive.</span></span> <span data-ttu-id="c05ab-221">通常情况下，此步骤已作为 Load 方法主体嵌入（步骤 3）。</span><span class="sxs-lookup"><span data-stu-id="c05ab-221">Often, this step is embedded as the body of the Load method (step 3).</span></span> 
    
3. <span data-ttu-id="c05ab-222">使用 Load() 或 LoadQuery() 方法加载上一步中的检索规范。</span><span class="sxs-lookup"><span data-stu-id="c05ab-222">Load the retrieval specification from the previous step using the Load() or LoadQuery() method.</span></span>
    
   <span data-ttu-id="c05ab-223">对于加载集合和对象，请使用 Load()。</span><span class="sxs-lookup"><span data-stu-id="c05ab-223">For loading collections and objects, use Load().</span></span> <span data-ttu-id="c05ab-224">对于具有子句（如“where”和“group”）的查询，请使用 LoadQuery()。</span><span class="sxs-lookup"><span data-stu-id="c05ab-224">For queries with clauses such as "where" and "group", use LoadQuery().</span></span> 
    
4. <span data-ttu-id="c05ab-225">使用 ExecuteQuery() 方法执行请求。</span><span class="sxs-lookup"><span data-stu-id="c05ab-225">Execute the request using the ExecuteQuery() method.</span></span>
    
   <span data-ttu-id="c05ab-226">ExecuteQuery() 方法将在可执行查询时通知主机。</span><span class="sxs-lookup"><span data-stu-id="c05ab-226">The ExecuteQuery() method notifies the host that the query or queries are ready to execute.</span></span> <span data-ttu-id="c05ab-227">收到通知后，主机将执行查询并将结果发送至客户端。</span><span class="sxs-lookup"><span data-stu-id="c05ab-227">Once the host receives notification, it executes the queries and sends the results to the client.</span></span> 
    
<span data-ttu-id="c05ab-228">客户端收到结果信息之后，应用程序即可使用该信息。</span><span class="sxs-lookup"><span data-stu-id="c05ab-228">With the information at the client, the application can use it.</span></span> <span data-ttu-id="c05ab-229">下面的代码片段将会循环显示已发布的项目，并打印主机上每个已发布项目的 ID 和名称。</span><span class="sxs-lookup"><span data-stu-id="c05ab-229">The following code fragment cycles through the published projects and prints the Id and Name for each published project on the host.</span></span>
  
```cs
// Get the list of projects in Project Web App.
var projects = projContext.Projects;
projContext.Load(projects);
projcontext.ExecuteQuery();
foreach (PublishedProject pubProj in projContext.Projects)
{
    Console.WriteLine("\n{0}. {1}   {2} \t{3} \n", j++, pubProj.Id, pubProj.Name, pubProj.CreatedDate);
}

```

<span data-ttu-id="c05ab-230">输出：</span><span class="sxs-lookup"><span data-stu-id="c05ab-230">Output</span></span>
  
```cs
Published Project count:2
1. be80a848-b2ef-e511-80f4-00155dc84e01   A second Project     3/21/2016 10:14:40 PM
2. 9d730a1a-60ed-e511-80f6-00155dc87d01   Ent_Proj_1   3/18/2016 11:21:14 PM

```

### <a name="make-a-request"></a><span data-ttu-id="c05ab-231">发出请求</span><span class="sxs-lookup"><span data-stu-id="c05ab-231">Make a request to the OneDrive API</span></span>

<span data-ttu-id="c05ab-232">通过使用上一代码片段中的操作，应用程序可以在托管网站上检索指定账户中的项目列表。</span><span class="sxs-lookup"><span data-stu-id="c05ab-232">Using the actions from the previous code fragment, the application retrieves the list of projects in the specified account on the hosting site.</span></span> 
  
1. <span data-ttu-id="c05ab-233">ProjectContext 已指定为要列出的项目。</span><span class="sxs-lookup"><span data-stu-id="c05ab-233">The ProjectContext is specified for the projects to list.</span></span> 
    
   ```cs
    var projects = projContext.Projects;
   ```

2. <span data-ttu-id="c05ab-234">指定要检索的项目。</span><span class="sxs-lookup"><span data-stu-id="c05ab-234">Specify the item to retrieve.</span></span> 
    
   ```cs
    projContext.Load(projects);
   ```

   <span data-ttu-id="c05ab-235">只需指定集合，服务器即可检索项目集合，并用默认属性集中的值填充每个项目。</span><span class="sxs-lookup"><span data-stu-id="c05ab-235">By only stating the collection, the server retrieves the project collection, populating each project with values for the default set of properties.</span></span> <span data-ttu-id="c05ab-236">如果访问的属性是默认属性集的一部分，则获得成功结果。</span><span class="sxs-lookup"><span data-stu-id="c05ab-236">Accessing properties that are part of the default property set gives successful results.</span></span> <span data-ttu-id="c05ab-237">如果访问的属性不是默认属性集的一部分，则会出现“未初始化”异常。</span><span class="sxs-lookup"><span data-stu-id="c05ab-237">Accessing properties that are not part of the default set results in a "Not initialized" exception.</span></span>
    
3. <span data-ttu-id="c05ab-238">加载请求 (projContext.Load)。</span><span class="sxs-lookup"><span data-stu-id="c05ab-238">Load the request (projContext.Load).</span></span>
    
   <span data-ttu-id="c05ab-239">这是上一步骤的一部分。</span><span class="sxs-lookup"><span data-stu-id="c05ab-239">This is part of the previous step.</span></span>
    
4. <span data-ttu-id="c05ab-240">执行查询 (ExecuteQuery)。</span><span class="sxs-lookup"><span data-stu-id="c05ab-240">Execute the query.</span></span> 
    
   ```cs
    projContext.ExecuteQuery();
   ```

### <a name="retrieve-high-level-project-information"></a><span data-ttu-id="c05ab-241">检索高级项目信息</span><span class="sxs-lookup"><span data-stu-id="c05ab-241">Retrieve high-level project information</span></span>

<span data-ttu-id="c05ab-242">必须在发送到服务器的请求中指定非默认属性的属性。</span><span class="sxs-lookup"><span data-stu-id="c05ab-242">Properties that are not default properties must be specified in the request to the server.</span></span> <span data-ttu-id="c05ab-243">在上一示例中，下一代码片段将加载项目集合上下文。</span><span class="sxs-lookup"><span data-stu-id="c05ab-243">The next code fragment loads the projects collection context as in the previous example.</span></span> <span data-ttu-id="c05ab-244">然后，规范将会请求要包括在结果中的其他非默认。</span><span class="sxs-lookup"><span data-stu-id="c05ab-244">Then, the specification requests additional non-default properties to include in the result.</span></span> 
  
```cs
var projects = projContext.Projects;
projContext.Load(projects,
    ps => ps.IncludeWithDefaultProperties(
        p => p.StartDate, p => p.Phase, p => p.Stage));
projContext.ExecuteQuery();

```

<span data-ttu-id="c05ab-245">load 语句指定项目集合上下文，并将 StartDate、Phase 和 Stage 添加到查询结果中。</span><span class="sxs-lookup"><span data-stu-id="c05ab-245">The load statement specifies the projects collection context, and adds the StartDate, Phase, and Stage to the query result.</span></span> <span data-ttu-id="c05ab-246">其他属性可以是标量、对象或集合。</span><span class="sxs-lookup"><span data-stu-id="c05ab-246">The additional properties can be scalar, objects, or collections.</span></span> <span data-ttu-id="c05ab-247">可直接访问标量项。</span><span class="sxs-lookup"><span data-stu-id="c05ab-247">Scalar items can be accessed directly.</span></span> <span data-ttu-id="c05ab-248">对象和集合需要按照以下代码片段所示进行额外的处理。</span><span class="sxs-lookup"><span data-stu-id="c05ab-248">Objects and collections require additional processing, as in the following code fragment.</span></span>
  
```cs
// Using the previous definition and Load statement …
projContext.ExecuteQuery();
foreach (PublishedProject pubProj in projContext.Projects)
{
Console.WriteLine("\n\t{0}. \t{1} \n\t{2} \n\t{3} \n", j++, pubProj.Id, pubProj.Name,
    pubProj.CreatedDate);
             // The following statement generates an exception about the object 
             // reference not being set to an instance on the server. 
             // Console.WriteLine("\tCurrent Phase:\t{0}", pubProj.Phase.Name);
             // Phase and Stage are not published with the rest of the data. Need to pull these objects from the server.
             Phase oPhase = pubProj.Phase;
             projContext.Load(oPhase);
             projContext.ExecuteQuery();
             //if-else fails because the else case fails with "Microsoft.SharePoint.Client.ServerObjectNullReferenceException".
             //if (oPhase.ServerObjectIsNull != null)
             //Using try-catch instead
             try
             {
                  Console.WriteLine("\tCurrent Phase:\t{0}", oPhase.Name);
             }
             
             catch
             {
                  Console.WriteLine("\tCurrent Phase:\t Not available");
             }
             
             Stage oStage = pubProj.Stage;
             projContext.Load(oStage);
             projContext.ExecuteQuery();
             //Again, not using if-else combination for the same reason as above.
             try
             {
                  Console.WriteLine("\tCurrent Stage:\t{0}", oStage.Name);
             }
             
             catch
             {
                  Console.WriteLine("\tCurrent Stage:\t Not available");
    }

```

<span data-ttu-id="c05ab-249">前三个项目输出：</span><span class="sxs-lookup"><span data-stu-id="c05ab-249">Output of the first three projects:</span></span>
  
```cs
Project counts:31
1. Project ID:  957d5fcd-5cbf-e111-9f1e-00155d022681
        Name:           Acquisition Target Analysis
        CreatedDate:            3/22/2016 5:14:34 PM
        Current Phase:  3. Plan
        Current Stage:  6. Plan
2. Project ID:  16905202-5fbf-e111-9f1e-00155d022681
        Name:           Apparel ERP Upgrade
        CreatedDate:            3/22/2016 5:36:40 PM
        Current Phase:  3. Plan
        Current Stage:  6. Plan
3. Project ID:  dce23152-63bf-e111-9f1e-00155d022681
        Name:           Audit Tracking Solution
        CreatedDate:            3/22/2016 5:02:24 PM
        Current Phase:  2. Select
        Current Stage:  4. Select Gate

```

### <a name="retrieve-all-tasks-in-a-project"></a><span data-ttu-id="c05ab-250">检索项目中的所有任务</span><span class="sxs-lookup"><span data-stu-id="c05ab-250">Retrieve all tasks in a project</span></span>

<span data-ttu-id="c05ab-251">每个项目都包含许多个任务。</span><span class="sxs-lookup"><span data-stu-id="c05ab-251">Each project has many tasks.</span></span> <span data-ttu-id="c05ab-252">因此，拉取单个项目中的任务包含以下几个步骤：</span><span class="sxs-lookup"><span data-stu-id="c05ab-252">So, pulling the tasks for a single project consists of the following:</span></span>
  
1. <span data-ttu-id="c05ab-253">建立项目集合的上下文。</span><span class="sxs-lookup"><span data-stu-id="c05ab-253">Establish the context of the projects collection.</span></span>
    
   ```cs
    var projects = projContext.Projects;
   ```

2. <span data-ttu-id="c05ab-254">检索项目信息，包括任务属性。</span><span class="sxs-lookup"><span data-stu-id="c05ab-254">Retrieve the project information, including the Task properties.</span></span>
    
   ```cs
    projContext.Load(projects);
    ProjContext.ExecuteQuery();
    foreach (PublishedProject pubProj in projContext.Projects){
    
   ```

    <span data-ttu-id="c05ab-255">请注意，应用程序将对已发布的项目进行寻址。</span><span class="sxs-lookup"><span data-stu-id="c05ab-255">Note that the application is addressing published projects.</span></span> <span data-ttu-id="c05ab-256">当前已发布项目的上下文为 pubProj。</span><span class="sxs-lookup"><span data-stu-id="c05ab-256">The context for the current published project is pubProj.</span></span> 
    
3. <span data-ttu-id="c05ab-257">建立“任务”集合的上下文。</span><span class="sxs-lookup"><span data-stu-id="c05ab-257">Establish the context for the Tasks collection.</span></span>
    
   ```cs
    PublishedTaskCollection collTask = pubProj.Tasks;
   ```

   <span data-ttu-id="c05ab-258">`pubProj.Tasks` 属性将引用当前已发布项目的任务。</span><span class="sxs-lookup"><span data-stu-id="c05ab-258">The `pubProj.Tasks` property references the tasks of the current published project.</span></span> 
    
4. <span data-ttu-id="c05ab-259">加载规范以检索“任务”集合，包括相应的非默认属性。</span><span class="sxs-lookup"><span data-stu-id="c05ab-259">Load the specification to retrieve Task collection, including the appropriate non-default properties.</span></span>
    
   ```cs
    projContext.Load(collTask,
        tsk => tsk.IncludeWithDefaultProperties(
            t => t.Id, t => t.Name, t => t.Start,
            t => t.ScheduledStart, t => t.Completion));
    
   ```

5. <span data-ttu-id="c05ab-260">执行查询以检索具有相应属性的“任务”集合。</span><span class="sxs-lookup"><span data-stu-id="c05ab-260">Execute the query to retrieve the Task collection with the appropriate properties.</span></span>
    
   ```cs
    projContext.ExecuteQuery();
   ```

<span data-ttu-id="c05ab-261">信息现已位于本地机上。</span><span class="sxs-lookup"><span data-stu-id="c05ab-261">The information is now local.</span></span> <span data-ttu-id="c05ab-262">下面的代码片段通过将信息写入到控制台来处理已发布的“任务”集合。</span><span class="sxs-lookup"><span data-stu-id="c05ab-262">The following code fragment processes the published tasks collection by writing the information to the console.</span></span>
  
```cs
    Console.WriteLine("Task collection count: {0}", collTask.Count.ToString());
    if (collTask.Count > 0)
    {
        int k = 1;    //Task counter.
        foreach (PublishedTask t in collTask)
        {
            Console.WriteLine("{0}. Id:{1} \tName:{2}", k++, t.Id, t.Name);
            Console.WriteLine("\t ScheduledStart:{0} \tStart:{1} \tCompletion:{2}", k, t.ScheduledStart, t.Start, t.Completion);
        }
    }

```

<span data-ttu-id="c05ab-263">一个项目的任务输出：</span><span class="sxs-lookup"><span data-stu-id="c05ab-263">Output of tasks for one project:</span></span>
  
```cs
Task collection count: 5
1. Id:256fa850-b2ef-e511-80f6-00155dc87d01      Name:Load software onto computer
         ScheduledStart:2       Start:4/4/2016 8:00:00 AM       Completion:4/4/2016 8:00:00 AM
2. Id:266fa850-b2ef-e511-80f6-00155dc87d01      Name:Locate and load Project Online SDK
         ScheduledStart:3       Start:4/5/2016 8:00:00 AM       Completion:4/5/2016 8:00:00 AM
3. Id:276fa850-b2ef-e511-80f6-00155dc87d01      Name:Locate and load SP SDK
         ScheduledStart:4       Start:4/5/2016 1:00:00 PM       Completion:4/5/2016 1:00:00 PM
4. Id:286fa850-b2ef-e511-80f6-00155dc87d01      Name:Build app that accesses Proj Online
         ScheduledStart:5       Start:4/6/2016 8:00:00 AM       Completion:4/6/2016 8:00:00 AM
5. Id:296fa850-b2ef-e511-80f6-00155dc87d01      Name:Build app that accesses task assignments
         ScheduledStart:6       Start:4/7/2016 8:00:00 AM       Completion:4/7/2016 8:00:00 AM

```

### <a name="access-information-at-multiple-levels"></a><span data-ttu-id="c05ab-264">访问多个级别的信息</span><span class="sxs-lookup"><span data-stu-id="c05ab-264">Access information at multiple levels</span></span>

<span data-ttu-id="c05ab-265">每个任务中涉及一个或多个人员（a.k.a.</span><span class="sxs-lookup"><span data-stu-id="c05ab-265">Each task can have one or more persons (a.k.a.</span></span> <span data-ttu-id="c05ab-266">资源）来完成任务。</span><span class="sxs-lookup"><span data-stu-id="c05ab-266">resource) contributing toward its completion.</span></span> <span data-ttu-id="c05ab-267">对于每个任务，“工作分配”和“资源”集合均包含此信息。</span><span class="sxs-lookup"><span data-stu-id="c05ab-267">The Assignments and Resources collections contain this information for each task.</span></span> 
  
<span data-ttu-id="c05ab-268">涉及以下几个处理步骤：</span><span class="sxs-lookup"><span data-stu-id="c05ab-268">The crawl and content processing architecture consists of the following:</span></span>
  
1. <span data-ttu-id="c05ab-269">获取项目任务的上下文。</span><span class="sxs-lookup"><span data-stu-id="c05ab-269">Obtaining a context for the project task.</span></span>
    
2. <span data-ttu-id="c05ab-270">生成请求并加载绑定到此任务的工作分配请求。</span><span class="sxs-lookup"><span data-stu-id="c05ab-270">Build a request and load the request for the assignments tied to the task.</span></span> 
    
3. <span data-ttu-id="c05ab-271">执行工作分配查询。</span><span class="sxs-lookup"><span data-stu-id="c05ab-271">Execute the query for the assignments.</span></span>
    
4. <span data-ttu-id="c05ab-272">生成请求并加载与单个工作分配关联的资源请求。</span><span class="sxs-lookup"><span data-stu-id="c05ab-272">Build a request and load the request for the resource associated with an individual assignment.</span></span> 
    
5. <span data-ttu-id="c05ab-273">执行资源查询。</span><span class="sxs-lookup"><span data-stu-id="c05ab-273">Execute the query for the resource.</span></span>
    
> [!NOTE] 
> - <span data-ttu-id="c05ab-274">已显式请求服务器信息中的“工作分配”集合，因为它不是“任务”集合的默认属性。</span><span class="sxs-lookup"><span data-stu-id="c05ab-274">The Assignments collection is explicitly requested in the information from the server because it is not a default property of the Tasks collection.</span></span> <span data-ttu-id="c05ab-275">作为集合，可以进行后续查询以拉取服务器中的集合。</span><span class="sxs-lookup"><span data-stu-id="c05ab-275">As a collection, a subsequent query is made to pull the collection from the server.</span></span> 
> - <span data-ttu-id="c05ab-276">“资源”为对象。</span><span class="sxs-lookup"><span data-stu-id="c05ab-276">The Resource is an object.</span></span> <span data-ttu-id="c05ab-277">工作分配查询包括与此工作分配关联的资源名称。</span><span class="sxs-lookup"><span data-stu-id="c05ab-277">The query for an assignment includes the resource name associated with the assignment.</span></span>
    
```cs
PublishedTaskCollection collTask = pubProj.Tasks;
    projContext.Load(collTask,
        tsk => tsk.IncludeWithDefaultProperties(
            t => t.Id, t => t.Name, 
            t => t.Assignments));
    projContext.Load(collTask);
    projContext.ExecuteQuery();
    Console.WriteLine("Task collection count: {0}", collTask.Count.ToString());
    if (collTask.Count > 0)
    {
        int k = 1;    //Task counter.
        //Processing task list for current project
        foreach (PublishedTask t in collTask)
        {
            Console.WriteLine("{0}. Id:{1} \tName:{2}", k, t.Id, t.Name);
            k++;
            //Define and retrieve Assignments for current task
            PublishedAssignmentCollection collAssgns = t.Assignments;
            projContext.Load(collAssgns);
            projContext.ExecuteQuery();
            Console.WriteLine("    Assignment collection count: {0}", collAssgns.Count);
            if (collAssgns.Count > 0)
            {
                //Output string for resources assigned to task
                StringBuilder output = new StringBuilder();
                output.AppendFormat("\t Assignments: ");
                foreach (PublishedAssignment a in collAssgns)
                {
                    //Define and retrieve resource name for current assignment 
                    //(an object)
                    projContext.Load(a,
                        b => b.Resource.Name);
                    projContext.ExecuteQuery();
                    output.AppendFormat("{0}, ", a.Resource.Name);
                }
                Console.WriteLine(output);
            }
            else
            {
                Console.WriteLine("\t Assignments: None");
            }
        }
    }   // endif

```

<span data-ttu-id="c05ab-278">项目的任务 52、75 和 76 的输出：</span><span class="sxs-lookup"><span data-stu-id="c05ab-278">Output for tasks 52, 75, and 76 of a project:</span></span>
  
```cs
52. Id:2c729e96-54f0-e511-80c6-000d3a33235f     Name:Develop training materials
    Assignment collection count: 1
         Assignments: Robert Lyon,
75. Id:43729e96-54f0-e511-80c6-000d3a33235f     Name:Determine final deployment strategy
    Assignment collection count: 0
         Assignments: None
76. Id:44729e96-54f0-e511-80c6-000d3a33235f     Name:Develop deployment methodology
    Assignment collection count: 4
         Assignments: Molly Dempsey, Sara Davis, Shammi Mohamed, Zainal Arifin, 

```

### <a name="access-custom-enterprise-level-fields"></a><span data-ttu-id="c05ab-279">访问自定义企业级字段</span><span class="sxs-lookup"><span data-stu-id="c05ab-279">Access custom enterprise-level fields</span></span>

<span data-ttu-id="c05ab-280">Project Online 存在自定义字段。</span><span class="sxs-lookup"><span data-stu-id="c05ab-280">Custom fields exist for Project Online.</span></span> <span data-ttu-id="c05ab-281">这些企业级字段可与单个项目关联在一起。</span><span class="sxs-lookup"><span data-stu-id="c05ab-281">These are enterprise-level fields that can be associated with individual project.</span></span> <span data-ttu-id="c05ab-282">本节介绍如何访问这些字段。</span><span class="sxs-lookup"><span data-stu-id="c05ab-282">This section describes how to access these fields.</span></span> 
  
<span data-ttu-id="c05ab-283">自定义字段不包括在与项目关联的默认属性集中。</span><span class="sxs-lookup"><span data-stu-id="c05ab-283">Custom fields are not included in the default set of properties associated with a project.</span></span> <span data-ttu-id="c05ab-284">因此，它们需要检索规范中的显式标识。</span><span class="sxs-lookup"><span data-stu-id="c05ab-284">So, they need explicit identification in the retrieval specification.</span></span> <span data-ttu-id="c05ab-285">此过程的高级视图有以下项目组成：</span><span class="sxs-lookup"><span data-stu-id="c05ab-285">The high-level view of the process consists of the following items:</span></span>
  
1. <span data-ttu-id="c05ab-286">以隧道方式连接到使用公用名的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="c05ab-286">Tunnel to the custom field using its common name.</span></span>
    
2. <span data-ttu-id="c05ab-287">检索自定义字段的内部名称。</span><span class="sxs-lookup"><span data-stu-id="c05ab-287">Retrieve the internal name of the custom field.</span></span>
    
3. <span data-ttu-id="c05ab-288">返回至全局上下文并查询使用自定义字段的内部名称的系统。</span><span class="sxs-lookup"><span data-stu-id="c05ab-288">Return to the global context and query the system using the internal name of the custom field.</span></span>
    
#### <a name="tunnel-to-the-custom-field-retrieve-its-internal-name-and-used-it-to-query-the-system"></a><span data-ttu-id="c05ab-289">以隧道方式连接到自定义字段，检索其内部名称并用其查询系统</span><span class="sxs-lookup"><span data-stu-id="c05ab-289">Tunnel to the custom field, retrieve its internal name, and used it to query the system</span></span>

<span data-ttu-id="c05ab-290">此任务指定使用带一条新增详细信息的非默认属性的检索。</span><span class="sxs-lookup"><span data-stu-id="c05ab-290">This task specifies a retrieval that uses a non-default property with one added detail.</span></span>
  
1. <span data-ttu-id="c05ab-291">如本文开头所述，从使用项目上下文开始。</span><span class="sxs-lookup"><span data-stu-id="c05ab-291">Begin by using the projects context, as described at the beginning of this article.</span></span>
    
   ```cs
    // Get the list of published projects in Project Web App.
    var projects = projContext.Projects;
    
   ```

2. <span data-ttu-id="c05ab-292">除了要检索的任何其他非默认属性外，再向项目集合检索请求添加两个项目：</span><span class="sxs-lookup"><span data-stu-id="c05ab-292">Add two items to the projects collection retrieval request in addition to any other non-default properties to retrieve:</span></span>
    
   ```cs
    projContext.Load(projects,
        ps => ps.IncludeWithDefaultProperties(
            p => p.Phase, p => p.Stage,                  // Other nondefault properties
            p => p.IncludeCustomFields,                  // Gets PublishedProject object 
                                                        // that contains custom fields
            p => p.IncludeCustomFields.CustomFields));   // Populates the custom fields
                    projContext.ExecuteQuery();
    
   ```

   <span data-ttu-id="c05ab-293">`p => p.IncludeCustomFields` 子句标识需要使用支持自定义字段的项目对象。</span><span class="sxs-lookup"><span data-stu-id="c05ab-293">The  `p => p.IncludeCustomFields` clause identifies the need to use a project object that supports custom fields.</span></span> 
    
   <span data-ttu-id="c05ab-294">`p => p.IncludeCustomFields.CustomFields` 子句请求将自定义字段数据包含在查询结果中。</span><span class="sxs-lookup"><span data-stu-id="c05ab-294">The  `p => p.IncludeCustomFields.CustomFields` clause requests the inclusion of custom field data in the query result.</span></span> <span data-ttu-id="c05ab-295">在检索自定义字段内部名称后，将使用此信息。</span><span class="sxs-lookup"><span data-stu-id="c05ab-295">This information is used after the custom field internal name is retrieved.</span></span> 
    
3. <span data-ttu-id="c05ab-296">加载请求。</span><span class="sxs-lookup"><span data-stu-id="c05ab-296">Load the request.</span></span>
    
   <span data-ttu-id="c05ab-297">这是上一步骤的一部分。</span><span class="sxs-lookup"><span data-stu-id="c05ab-297">This is part of the previous step.</span></span>
    
4. <span data-ttu-id="c05ab-298">执行查询。</span><span class="sxs-lookup"><span data-stu-id="c05ab-298">Execute the query.</span></span>
    
   ```cs
    projContext.ExecuteQuery()
   ```

5. <span data-ttu-id="c05ab-299">客户端收到此信息后，构建检索与当前项目关联的自定义字段的请求。</span><span class="sxs-lookup"><span data-stu-id="c05ab-299">With this information on the client, build a request to retrieve the custom fields associated with the current project.</span></span>
    
   ```cs
    foreach (PublishedProject pubProj in projContext.Projects)
    {
        //Console.WriteLine("\n\t{0}. \t{1} \n\t\t{2} \n\t\t{3} \n", 
                j++, pubProj.Id, pubProj.Name, pubProj.CreatedDate);
        CustomFieldCollection collCustF = pubProj.CustomFields;
                        
        projContext.Load(collCustF);
        projContext.ExecuteQuery();
    
   ```

6. <span data-ttu-id="c05ab-300">查找相应的自定义字段并检索字段的内部名称。</span><span class="sxs-lookup"><span data-stu-id="c05ab-300">Locate the appropriate custom field and retrieve the internal name of the field.</span></span> 
    
   ```cs
        foreach (CustomField oCF in collCustF)
        {
            if (oCF.Name == "Project Health")
            {
                Console.WriteLine("Name: {0}", oCF.Name);
                Console.WriteLine("InternalName: {0}", oCF.InternalName);
    
   ```

   <span data-ttu-id="c05ab-301">检索自定义字段的内部名称。</span><span class="sxs-lookup"><span data-stu-id="c05ab-301">The internal name of the custom field is retrieved.</span></span> <span data-ttu-id="c05ab-302">高级项 1 和 2 现已完成。</span><span class="sxs-lookup"><span data-stu-id="c05ab-302">High-level items 1 and 2 are now complete.</span></span>
    
7. <span data-ttu-id="c05ab-303">返回项目上下文并检索自定义字段的值。</span><span class="sxs-lookup"><span data-stu-id="c05ab-303">Return to the project context and retrieve the value of the custom field.</span></span>
    
   ```cs
    Console.WriteLine("Value: {0}", 
        pubProj.IncludeCustomFields.FieldValues[oCF.InternalName]);
    
   ```

   > [!NOTE]
   > <span data-ttu-id="c05ab-304">将内部名称用作索引，检索自定义字段的值。</span><span class="sxs-lookup"><span data-stu-id="c05ab-304">The value of the custom field is retrieved using the internal name as an index.</span></span> 
  
<span data-ttu-id="c05ab-305">三个项目的输出包括项目 ID、项目名称、自定义字段内部名称和自定义字段值。</span><span class="sxs-lookup"><span data-stu-id="c05ab-305">Output of three projects consisting of project ID, project Name, custom field name, custom field internal name, and custom field value.</span></span>
  
```cs
Project counts:31
1. Project ID:  957d5fcd-5cbf-e111-9f1e-00155d022681
        Name:           Acquisition Target Analysis
Name: Project Health
InternalName: Custom_745de6dfcfb4e11195dc00155d02c97f
Value: Green
2. Project ID:  16905202-5fbf-e111-9f1e-00155d022681
        Name:           Apparel ERP Upgrade
Name: Project Health
InternalName: Custom_745de6dfcfb4e11195dc00155d02c97f
Value: Green
3. Project ID:  dce23152-63bf-e111-9f1e-00155d022681
        Name:           Audit Tracking Solution
Name: Project Health
InternalName: Custom_745de6dfcfb4e11195dc00155d02c97f
Value: Red

```

## <a name="see-also"></a><span data-ttu-id="c05ab-306">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c05ab-306">See also</span></span>

<span data-ttu-id="c05ab-307">有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/zh-CN/project)。</span><span class="sxs-lookup"><span data-stu-id="c05ab-307">For documentation and samples related to Project Online and application development using CSOM, see the [Project Development Portal](https://developer.microsoft.com/zh-CN/project).</span></span>
    

