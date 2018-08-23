---
title: 开发 Project Online 应用程序使用的客户端对象模型
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5740d0b2-5d36-40e4-9e83-577cb186359f
description: 本文介绍使用.NET Framework 4.0 的桌面应用程序的 Microsoft Project Online 应用程序开发。 本文中描述的应用程序宿主服务器中检索信息。
ms.openlocfilehash: a65dbbdedb371fae9b8f0b99ea113ae38cbaffb5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572877"
---
# <a name="developing-a-project-online-application-using-the-client-side-object-model"></a><span data-ttu-id="1c44d-104">开发 Project Online 应用程序使用的客户端对象模型</span><span class="sxs-lookup"><span data-stu-id="1c44d-104">Developing a Project Online application using the client-side object model</span></span>

<span data-ttu-id="1c44d-105">本文介绍使用.NET Framework 4.0 的桌面应用程序的 Microsoft Project Online 应用程序开发。</span><span class="sxs-lookup"><span data-stu-id="1c44d-105">This article describes Microsoft Project Online application development for desktop applications using the .NET Framework 4.0.</span></span> <span data-ttu-id="1c44d-106">本文中描述的应用程序宿主服务器中检索信息。</span><span class="sxs-lookup"><span data-stu-id="1c44d-106">The application described in this article retrieves information from the hosting server.</span></span> 
  
## <a name="background"></a><span data-ttu-id="1c44d-107">背景</span><span class="sxs-lookup"><span data-stu-id="1c44d-107">Background</span></span>

<span data-ttu-id="1c44d-108">Microsoft Project 桌面应用程序中早期 20 世纪 90 年代开始。</span><span class="sxs-lookup"><span data-stu-id="1c44d-108">Microsoft Project started as desktop application in the early 1990's.</span></span> <span data-ttu-id="1c44d-109">如今，项目是更多，如证明其几个类别：</span><span class="sxs-lookup"><span data-stu-id="1c44d-109">Today, Project is much more, as its several varieties attest:</span></span>
  
- <span data-ttu-id="1c44d-110">Project standard edition 的桌面应用程序作为独立的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="1c44d-110">Project standard edition is a desktop application that runs as a stand-alone application.</span></span>
    
- <span data-ttu-id="1c44d-111">Project professional 版本是桌面应用程序可以进行交互和与上规模较大的服务器共享数据，以及执行 Project standard edition 中找到的功能。</span><span class="sxs-lookup"><span data-stu-id="1c44d-111">Project professional edition is a desktop application that can interact and share data with a server on a larger scale, as well as perform the functionality found in Project standard edition.</span></span>
    
- <span data-ttu-id="1c44d-112">Project Online 是一种 Microsoft 承载的服务，公司提供的 PMO 级解决方案以进行协调和管理项目、 程序和项目组合。</span><span class="sxs-lookup"><span data-stu-id="1c44d-112">Project Online is a Microsoft-hosted service that provides companies with a PMO-level solution to coordinate and manage projects, programs, and portfolios.</span></span> <span data-ttu-id="1c44d-113">桌面版本，Project Online 比其他产品可以维护和跟踪整个生命周期中的项目的项目详细信息。</span><span class="sxs-lookup"><span data-stu-id="1c44d-113">A different offering than the desktop editions, Project Online can maintain and track project details throughout the life of a project.</span></span> 
    
- <span data-ttu-id="1c44d-114">Project Server 企业管理，并保护包含项目、 程序和项目组合信息的服务器的企业托管的服务。</span><span class="sxs-lookup"><span data-stu-id="1c44d-114">Project Server is an enterprise-hosted service in which the enterprise manages and secures the server containing project, program, and portfolio information.</span></span> <span data-ttu-id="1c44d-115">Project Server、 源于保护内部，服务器提供项目、 程序和项目组合面向外部托管 Project Online 与更大容量的自定义功能。</span><span class="sxs-lookup"><span data-stu-id="1c44d-115">Project Server, by virtue of securing the server in-house, offers the project, program, and portfolio oriented features of externally-hosted Project Online with a greater capacity for customization.</span></span>
    
<span data-ttu-id="1c44d-116">Project Online 具有三个 online API 集： 客户端对象模型 (CSOM)、 JavaScript 对象模型 (JSOM) 和代表性状态传输 (REST)。</span><span class="sxs-lookup"><span data-stu-id="1c44d-116">Project Online has three online API sets: Client-side Object Model (CSOM), JavaScript Object Model (JSOM), and Representational State Transfer (REST).</span></span> 
  
- <span data-ttu-id="1c44d-117">.NET CSOM 实现时开发与 Project Online 租户 Windows 应用程序交互的首选的接口。</span><span class="sxs-lookup"><span data-stu-id="1c44d-117">The .NET CSOM implementation is the preferred interface when developing Windows applications that interact with Project Online tenants.</span></span> <span data-ttu-id="1c44d-118">以用户为中心的应用程序的典型环境包括 Windows 台式机和 Microsoft Surface 设备。</span><span class="sxs-lookup"><span data-stu-id="1c44d-118">Typical environments for user-centric applications include Windows desktops and Microsoft Surface devices.</span></span> <span data-ttu-id="1c44d-119">使用.NET CSOM 编写的后端应用程序可以连接到其他服务器的外部的 Project Online 的业务逻辑和数据源。</span><span class="sxs-lookup"><span data-stu-id="1c44d-119">Back-end applications written with .NET CSOM can connect to other servers for business logic and data sources that are external to Project Online.</span></span> <span data-ttu-id="1c44d-120">到 Project Online 的检索请求使用 LINQ 类似于查询系统的基本检索函数通过了若干个增强。</span><span class="sxs-lookup"><span data-stu-id="1c44d-120">Retrieval requests to Project Online use a LINQ-like query system that offers several enhancements over basic retrieval functions.</span></span>
    
- <span data-ttu-id="1c44d-121">JavaScript 对象模型 (JSOM) 接口提供了 Project Online 的加载项的跨浏览器支持。外接程序是存储在 Project Online 租户中的 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c44d-121">The JavaScript Object Model (JSOM) interface provides cross-browser support for Project Online Add-ins. An add-in is a web application that is stored in the Project Online tenant.</span></span> <span data-ttu-id="1c44d-122">当用户想要运行外接程序时外, 接程序的代码下载并在用户计算机上运行在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="1c44d-122">When a user wants to run an add-in, the code for the add-in downloads and runs in the browser on the user machine.</span></span> 
    
- <span data-ttu-id="1c44d-123">REST/Odata 模型提供了基于 HTTP 的通信，在非 Windows 环境中的应用程序建议使用此接口。</span><span class="sxs-lookup"><span data-stu-id="1c44d-123">The REST/Odata model provides HTTP-based communication, This interface is recommended for applications in non-Windows environments.</span></span> <span data-ttu-id="1c44d-124">通信终结点是 Project Web 应用程序 (PWA) 网站中的对象。</span><span class="sxs-lookup"><span data-stu-id="1c44d-124">Communication endpoints are the objects in the Project Web Application (PWA) site.</span></span> <span data-ttu-id="1c44d-125">结果提供一般 HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="1c44d-125">Results provide normal HTTP status codes.</span></span>
    
<span data-ttu-id="1c44d-126">本文重点介绍使用.NET CSOM 接口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c44d-126">This article focuses on an application that uses the .NET CSOM interface.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="1c44d-127">先决条件</span><span class="sxs-lookup"><span data-stu-id="1c44d-127">Prerequisites</span></span>

<span data-ttu-id="1c44d-128">开始与基本系统运行 Windows 10，并添加以下各项：</span><span class="sxs-lookup"><span data-stu-id="1c44d-128">Start with a base system running Windows 10, and add the following items:</span></span>
  
- <span data-ttu-id="1c44d-129">.Net framework 4.0 或更高版本-使用完整的框架。</span><span class="sxs-lookup"><span data-stu-id="1c44d-129">.Net Framework 4.0 or later -- Use the complete framework.</span></span> <span data-ttu-id="1c44d-130">下载站点是https://msdn.microsoft.com/en-us/vstudio/aa496123.aspx。</span><span class="sxs-lookup"><span data-stu-id="1c44d-130">The download site is https://msdn.microsoft.com/en-us/vstudio/aa496123.aspx.</span></span>
    
- <span data-ttu-id="1c44d-131">Visual Studio 2013 或更高版本-是可以接受任何版本。</span><span class="sxs-lookup"><span data-stu-id="1c44d-131">Visual Studio 2013 or later -- Any edition is acceptable.</span></span> <span data-ttu-id="1c44d-132">使用 Visual Studio 2015 的社区版本开发示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c44d-132">The community edition of Visual Studio 2015 was used to develop the sample application.</span></span> <span data-ttu-id="1c44d-133">社区 edition 位于https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx。</span><span class="sxs-lookup"><span data-stu-id="1c44d-133">The community edition is available at https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx.</span></span>
    
- <span data-ttu-id="1c44d-134">SharePoint 客户端组件 SDK-Project Online 和 Project Server 坐在 SharePoint 和 SharePoint 程序集。</span><span class="sxs-lookup"><span data-stu-id="1c44d-134">SharePoint Client Components SDK -- Project Online and Project Server sit on top of SharePoint, and SharePoint assemblies.</span></span> <span data-ttu-id="1c44d-135">SharePoint 客户端组件都包括在 Visual Studio 专业版和企业版。</span><span class="sxs-lookup"><span data-stu-id="1c44d-135">The SharePoint Client Components are included in Visual Studio Professional and Enterprise editions.</span></span> <span data-ttu-id="1c44d-136">如果您使用 Visual Studio 社区 edition，在以下网站中可用是最新版本的 Office 开发人员工具 SDK: https://www.microsoft.com/en-us/download/details.aspx?id=35585。</span><span class="sxs-lookup"><span data-stu-id="1c44d-136">If you use Visual Studio Community edition, the latest version of the Office Developer Tools SDK is available at the following site: https://www.microsoft.com/en-us/download/details.aspx?id=35585.</span></span>
    
- <span data-ttu-id="1c44d-137">Project Online 的帐户-这提供了对承载网站的访问。</span><span class="sxs-lookup"><span data-stu-id="1c44d-137">A Project Online account -- This provides access to the hosting site.</span></span> <span data-ttu-id="1c44d-138">有关获取 Project Online 帐户的详细信息，请参阅https://products.office.com/en-us/Project/project-online-portfolio-management。</span><span class="sxs-lookup"><span data-stu-id="1c44d-138">For more information about obtaining a Project Online account, see https://products.office.com/en-us/Project/project-online-portfolio-management.</span></span>
    
- <span data-ttu-id="1c44d-139">承载的网站上的项目填充的信息</span><span class="sxs-lookup"><span data-stu-id="1c44d-139">Projects on the hosting site that are populated with information</span></span>
    
> [!NOTE]
> <span data-ttu-id="1c44d-140">标准.NET Framework （4.0 或更高版本） 是要使用的正确框架。</span><span class="sxs-lookup"><span data-stu-id="1c44d-140">The standard .NET Framework (4.0 or later) is the correct framework to use.</span></span> <span data-ttu-id="1c44d-141">不要使用.NET Framework 4 客户端配置文件。</span><span class="sxs-lookup"><span data-stu-id="1c44d-141">Do not use the .NET Framework 4 Client Profile.</span></span> 
  
## <a name="develop-the-application"></a><span data-ttu-id="1c44d-142">开发应用程序</span><span class="sxs-lookup"><span data-stu-id="1c44d-142">Develop the application</span></span>

<span data-ttu-id="1c44d-143">在针对 SharePoint 进行开发桌面应用程序，首选的接口是 Project 客户端对象模型 (CSOM)。</span><span class="sxs-lookup"><span data-stu-id="1c44d-143">In developing a desktop application for SharePoint, the preferred interface is the Project client side object model (CSOM).</span></span> 
  
<span data-ttu-id="1c44d-144">您可以下载完整的示例在https://github.com/OfficeDev/Project-CSOM-List-Projects-Tasks。</span><span class="sxs-lookup"><span data-stu-id="1c44d-144">You can download the complete sample at https://github.com/OfficeDev/Project-CSOM-List-Projects-Tasks.</span></span>
  
<span data-ttu-id="1c44d-145">前两个主题涵盖基本问题： 使用适当的命名空间和程序集，创建 Visual Studio 项目和访问宿主服务器。</span><span class="sxs-lookup"><span data-stu-id="1c44d-145">The first two topics cover basic issues: creating a Visual Studio project with appropriate namespaces and assemblies, and accessing the hosting server.</span></span> <span data-ttu-id="1c44d-146">从一和多对象中检索信息通过 CSOM，处理的其余主题。</span><span class="sxs-lookup"><span data-stu-id="1c44d-146">The remaining topics deal with retrieving information through the CSOM, from one and many objects.</span></span> 
  
<span data-ttu-id="1c44d-147">从主机中检索信息是从客户端应用程序的两个操作过程。</span><span class="sxs-lookup"><span data-stu-id="1c44d-147">Retrieving information from the host is a two-action process from client applications.</span></span> <span data-ttu-id="1c44d-148">首先，应用程序指定，并将一个或多个检索请求发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="1c44d-148">First, the application specifies and sends one or more retrieval requests to the server.</span></span> <span data-ttu-id="1c44d-149">其次，应用程序向服务器执行提交的查询发出通知。</span><span class="sxs-lookup"><span data-stu-id="1c44d-149">Second, the application issues a notification to the server to execute the submitted queries.</span></span> <span data-ttu-id="1c44d-150">服务器响应通过将查询结果发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="1c44d-150">The server responds by sending the query results to the client.</span></span>
  
### <a name="set-up-the-visual-studio-project"></a><span data-ttu-id="1c44d-151">设置 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="1c44d-151">Set up the Visual Studio project</span></span>

<span data-ttu-id="1c44d-152">应用程序安装由创建新项目、 链接相应的程序集和声明所需的命名空间组成。</span><span class="sxs-lookup"><span data-stu-id="1c44d-152">The application setup consists of creating a new project, linking the appropriate assemblies and declaring the needed namespaces.</span></span> <span data-ttu-id="1c44d-153">Visual Studio 提供了几种类型的开发项目。</span><span class="sxs-lookup"><span data-stu-id="1c44d-153">Visual Studio presents several types of development projects.</span></span> 
  
#### <a name="select-a-visual-studio-project"></a><span data-ttu-id="1c44d-154">选择 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="1c44d-154">Select a Visual Studio project</span></span>

1. <span data-ttu-id="1c44d-155">启动 Visual Studio，然后选择开始页上的**启动新项目**。</span><span class="sxs-lookup"><span data-stu-id="1c44d-155">Launch Visual Studio and select **Start A New Project** on the Start Page.</span></span> 
    
   <span data-ttu-id="1c44d-156">新建项目对话框中显示可用的应用程序模板和任何选定的模板的数据字段。</span><span class="sxs-lookup"><span data-stu-id="1c44d-156">The New Project dialog displays available application templates, and data fields for any selected template.</span></span> 
    
2. <span data-ttu-id="1c44d-157">为此应用程序，指定以下各项。</span><span class="sxs-lookup"><span data-stu-id="1c44d-157">For this application, specify the following items.</span></span> <span data-ttu-id="1c44d-158">在屏幕上遇到关键字具有粗体属性：</span><span class="sxs-lookup"><span data-stu-id="1c44d-158">Keywords encountered on the screen have a bold attribute:</span></span>
    
   1. <span data-ttu-id="1c44d-159">从已安装的模板的左窗格中，选择**C#** => **Windows** => **经典桌面**。</span><span class="sxs-lookup"><span data-stu-id="1c44d-159">From the Installed templates in the left pane, select **C#** => **Windows** => **Classic desktop**.</span></span> 
    
   2. <span data-ttu-id="1c44d-160">在中央窗格的顶部，选择 **.NET Framework 4**。</span><span class="sxs-lookup"><span data-stu-id="1c44d-160">At the top of the central pane, select **.NET Framework 4**.</span></span> 
    
   3. <span data-ttu-id="1c44d-161">从应用程序类型在中央窗格中，选择**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1c44d-161">From the application types in the central pane, choose **Console Application**.</span></span> 
    
   4. <span data-ttu-id="1c44d-162">在底部部分中，指定的名称和位置的项目，并解决方案名称。</span><span class="sxs-lookup"><span data-stu-id="1c44d-162">In the bottom section, specify a name and location for the project, and a solution name.</span></span> 
    
   5. <span data-ttu-id="1c44d-163">此外在底部部分中，检查**创建解决方案的目录**框中。</span><span class="sxs-lookup"><span data-stu-id="1c44d-163">Also in the bottom section, check the **Create directory for solution** box.</span></span> 
    
3. <span data-ttu-id="1c44d-164">单击**确定**以创建初始项目。</span><span class="sxs-lookup"><span data-stu-id="1c44d-164">Click **OK** to create the initial project.</span></span> 
    
#### <a name="add-assemblies"></a><span data-ttu-id="1c44d-165">将程序集添加</span><span class="sxs-lookup"><span data-stu-id="1c44d-165">Add assemblies</span></span>

<span data-ttu-id="1c44d-166">VS 解决方案需要 ProjectServerClient 程序集从 Project 2103 SDK，几个来自 SharePoint SDK，程序集和.NET Framework System.Security 程序集。</span><span class="sxs-lookup"><span data-stu-id="1c44d-166">The VS solution needs the ProjectServerClient assembly from the Project 2103 SDK, a couple of assemblies from the SharePoint SDK, and the .NET Framework System.Security assembly.</span></span>
  
1. <span data-ttu-id="1c44d-167">VS 解决方案资源管理器，右键单击引用条目中，并选择**添加引用...**</span><span class="sxs-lookup"><span data-stu-id="1c44d-167">In the VS Solution Explorer, right-click the References entry, and select **Add Reference…**</span></span> <span data-ttu-id="1c44d-168">从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="1c44d-168">from the shortcut menu.</span></span> 
    
2. <span data-ttu-id="1c44d-169">检查**Microsoft.ProjectServer.Client.dll**。</span><span class="sxs-lookup"><span data-stu-id="1c44d-169">Check the **Microsoft.ProjectServer.Client.dll**.</span></span> 
    
   <span data-ttu-id="1c44d-170">如果需要请单击**浏览...**</span><span class="sxs-lookup"><span data-stu-id="1c44d-170">If needed, click the **Browse…**</span></span> <span data-ttu-id="1c44d-171">在对话框的底部按钮并导航到要定位程序集的 Project 2013 SDK 安装目录。</span><span class="sxs-lookup"><span data-stu-id="1c44d-171">button at the bottom of the dialog and navigate to the Project 2013 SDK installation directory to locate the assembly.</span></span> 
    
3. <span data-ttu-id="1c44d-172">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1c44d-172">Click **OK**.</span></span> 
    
4. <span data-ttu-id="1c44d-173">将 PrjoctServer 客户端命名空间添加到.cs 文件中。</span><span class="sxs-lookup"><span data-stu-id="1c44d-173">Add the PrjoctServer Client namespace to the .cs file.</span></span>
    
   ```cs
    using Microsoft.ProjectServer.Client;
   ```

<span data-ttu-id="1c44d-174">添加使用 NuGet 程序包管理器控制台的 SharePoint 2013 SDK 程序集。</span><span class="sxs-lookup"><span data-stu-id="1c44d-174">Add the SharePoint 2013 SDK assemblies using the NuGet Package Manager Console.</span></span> 
  
1. <span data-ttu-id="1c44d-175">从 VS 工具菜单中，单击下列菜单：**工具 =\> NuGet 程序包管理器 =\>程序包管理器控制台**。</span><span class="sxs-lookup"><span data-stu-id="1c44d-175">From the VS Tools menu, click the following menus: **Tools =\> NuGet Package Manager =\> Package Manager Console**.</span></span> 
    
2. <span data-ttu-id="1c44d-176">在程序包管理器控制台中，输入以下命令并按\<ENTER\>:</span><span class="sxs-lookup"><span data-stu-id="1c44d-176">In the Package Manager Console, enter the following command and press \<ENTER\>:</span></span>
    
   ```cs
    Install-Package Microsoft.SharePointOnline.CSOM
   ```

   <span data-ttu-id="1c44d-177">**程序包管理器控制台**提供命令结果; 的说明并 VS 解决方案资源管理器显示项目引用中的 SharePoint 程序集。</span><span class="sxs-lookup"><span data-stu-id="1c44d-177">The **Package Manager Console** provides a description of the command results; and, the VS Solution Explorer displays the SharePoint assemblies in the project references.</span></span> 
    
3. <span data-ttu-id="1c44d-178">将命名空间添加到.cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="1c44d-178">Add the namespaces to the .cs file:</span></span>
    
   ```cs
    using Microsoft.SharePoint.Client;
   ```

<span data-ttu-id="1c44d-179">System.Security 程序集是.NET Framework 的一部分，且已安装与框架。</span><span class="sxs-lookup"><span data-stu-id="1c44d-179">The System.Security assembly is part of .NET Framework and was installed with the framework.</span></span> <span data-ttu-id="1c44d-180">该示例应用程序需要一个身份验证提供对承载系统的加密的字符串的多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="1c44d-180">The sample application needs one more namespace that provides an encrypted string to the hosting system for authentication.</span></span> <span data-ttu-id="1c44d-181">身份验证后，应用程序可以访问承载系统的项目。</span><span class="sxs-lookup"><span data-stu-id="1c44d-181">Once authenticated, the application can access projects on the hosting system.</span></span> <span data-ttu-id="1c44d-182">将 System.Security 命名空间添加到.cs 文件中这种方式：</span><span class="sxs-lookup"><span data-stu-id="1c44d-182">Add the System.Security namespace to the .cs file in this way:</span></span>
  
1. <span data-ttu-id="1c44d-183">VS 解决方案资源管理器，右键单击引用条目中，并选择**添加引用...**</span><span class="sxs-lookup"><span data-stu-id="1c44d-183">In the VS Solution Explorer, right-click the References entry, and select **Add Reference…**</span></span> <span data-ttu-id="1c44d-184">从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="1c44d-184">from the shortcut menu.</span></span> 
    
2. <span data-ttu-id="1c44d-185">选中**程序集 =\>框架**左窗格中的引用管理器对话框中，然后检查**System.Security**。</span><span class="sxs-lookup"><span data-stu-id="1c44d-185">Select **Assemblies =\> Framework** in the left pane of the References Manager dialog, then check **System.Security**.</span></span> 
    
3. <span data-ttu-id="1c44d-186">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1c44d-186">Click **OK**.</span></span> 
    
4. <span data-ttu-id="1c44d-187">将 System.Security 命名空间添加到.cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="1c44d-187">Add the System.Security namespace to the .cs file:</span></span>
    
   ```cs
    using System.Security;
   ```

<span data-ttu-id="1c44d-188">.Cs 文件的开头应包含以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="1c44d-188">The start of the .cs file should contain the following namespaces:</span></span>
  
- <span data-ttu-id="1c44d-189">系统</span><span class="sxs-lookup"><span data-stu-id="1c44d-189">System</span></span>
    
- <span data-ttu-id="1c44d-190">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="1c44d-190">System.Collections.Generic</span></span>
    
- <span data-ttu-id="1c44d-191">更改</span><span class="sxs-lookup"><span data-stu-id="1c44d-191">System.Linq</span></span>
    
- <span data-ttu-id="1c44d-192">System.Test</span><span class="sxs-lookup"><span data-stu-id="1c44d-192">System.Test</span></span>
    
- <span data-ttu-id="1c44d-193">Microsoft.ProjectServer.Client</span><span class="sxs-lookup"><span data-stu-id="1c44d-193">Microsoft.ProjectServer.Client</span></span>
    
- <span data-ttu-id="1c44d-194">Microsoft.SharePoint.Client</span><span class="sxs-lookup"><span data-stu-id="1c44d-194">Microsoft.SharePoint.Client</span></span>
    
- <span data-ttu-id="1c44d-195">System.Security</span><span class="sxs-lookup"><span data-stu-id="1c44d-195">System.Security</span></span>
    
### <a name="connect-to-the-host-system"></a><span data-ttu-id="1c44d-196">连接到主机系统</span><span class="sxs-lookup"><span data-stu-id="1c44d-196">Connect to the host system</span></span>

<span data-ttu-id="1c44d-197">Project Online 是 SharePoint 应用程序，因此使用 SharePoint 身份验证是正确的方法。</span><span class="sxs-lookup"><span data-stu-id="1c44d-197">Project Online is a SharePoint application, so using SharePoint authentication is the correct approach.</span></span> <span data-ttu-id="1c44d-198">下面的代码片段准备访问托管的环境。</span><span class="sxs-lookup"><span data-stu-id="1c44d-198">The following code fragment prepares to access the hosted environment.</span></span>
  
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

<span data-ttu-id="1c44d-199">若要访问托管的环境的准备工作包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="1c44d-199">Preparations to access the hosted environment include the following items:</span></span>
  
1. <span data-ttu-id="1c44d-200">创建一个 context 对象的项目--这包含在前面的代码片段的下面的代码。</span><span class="sxs-lookup"><span data-stu-id="1c44d-200">Create a context object for the projects -- this is contained in the following code of the preceding code fragment.</span></span> 
    
   ```cs
    private static ProjectContext projContext;
    
   ```

   <span data-ttu-id="1c44d-201">上下文被继承的其他组件，允许系统管理的 Project 对象模型上下文中。</span><span class="sxs-lookup"><span data-stu-id="1c44d-201">The context is inherited by other components, allowing the system to manage the context of the Project object model.</span></span>
    
2. <span data-ttu-id="1c44d-202">标识主机网站--这是在下面的代码从前面的代码片段。</span><span class="sxs-lookup"><span data-stu-id="1c44d-202">Identify the host site -- this is done in the following code from the preceding code fragment.</span></span>
    
   ```cs
    using (ProjectContext projContext = new ProjectContext("https://Contoso.sharepoint.com/sites/pwa"))
   ```

   <span data-ttu-id="1c44d-203">当实例化项目上下文，该应用程序需要提供的项目网站集的根目录。</span><span class="sxs-lookup"><span data-stu-id="1c44d-203">When instantiating the projects context, the application needs to provide the root of the Projects site collection.</span></span> <span data-ttu-id="1c44d-204">应用程序使用的项目的根 URL 的子字符串。</span><span class="sxs-lookup"><span data-stu-id="1c44d-204">The application uses a substring of the URL of the root of the Projects.</span></span> <span data-ttu-id="1c44d-205">使用下图中的一个红色矩形突出显示此位置的快照。</span><span class="sxs-lookup"><span data-stu-id="1c44d-205">A snapshot of this location is highlighted with a red rectangle in the following illustration.</span></span> <span data-ttu-id="1c44d-206">身份验证需要从其开始通过"pwa"的子字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="1c44d-206">The authentication needs the string from its start through the substring "pwa".</span></span> <span data-ttu-id="1c44d-207">在代码列表中，应用程序使用字符串"https://XXXXXXXX.sharepoint.com/sites/pwa"。</span><span class="sxs-lookup"><span data-stu-id="1c44d-207">In the code listing, the application uses the string "https://XXXXXXXX.sharepoint.com/sites/pwa".</span></span>
        
   <span data-ttu-id="1c44d-208">![屏幕截图红色的边框内的项目网站集的 URL。](media/d48c4894-5dba-46b6-886a-3c59bfb83c4d.png "屏幕截图的项目的 URL 的网站集内的红色的边框")</span><span class="sxs-lookup"><span data-stu-id="1c44d-208">![Screen shot of the URL of the Projects site collection within a red border.](media/d48c4894-5dba-46b6-886a-3c59bfb83c4d.png "Screen shot of the URL of the Projects site collection within a red border")</span></span>
  
3. <span data-ttu-id="1c44d-209">将密码放入安全字符串--这是在下面的代码从前面的代码片段。</span><span class="sxs-lookup"><span data-stu-id="1c44d-209">Place the password in a secure string -- this is done in the following code from the preceding code fragment.</span></span>
    
   ```cs
    SecureString password - new SecureString();
    foreach (char c in "password".ToCharArray()) password.AppendChar(c);
    
   ```

   <span data-ttu-id="1c44d-210">密码和用户帐户是访问主机网站的凭据。</span><span class="sxs-lookup"><span data-stu-id="1c44d-210">The password and user account are the credentials to access the host site.</span></span> 
    
4. <span data-ttu-id="1c44d-211">Context 对象的凭据部分中添加的用户帐户和密码--这是在下面的代码从前面的代码片段。</span><span class="sxs-lookup"><span data-stu-id="1c44d-211">Add the user account and password to the credentials portion of the context object -- this is done in the following code from the preceding code fragment.</span></span>
    
   ```cs
    projContext.Credentials = new SharePointOnlineCredentials("sarad@Contoso.onmicrosoft.com", password);
   ```

<span data-ttu-id="1c44d-212">实例化的项目上下文已准备好使用。</span><span class="sxs-lookup"><span data-stu-id="1c44d-212">The instantiated project context is ready to use.</span></span>
  
### <a name="list-all-published-projects"></a><span data-ttu-id="1c44d-213">列出所有已发布的项目</span><span class="sxs-lookup"><span data-stu-id="1c44d-213">List all published projects</span></span>

<span data-ttu-id="1c44d-214">Project Online 和 ProjectServer 使用代理服务器进行通信与服务器进行创建、 报表、 更新和删除 (CRUD) 操作。</span><span class="sxs-lookup"><span data-stu-id="1c44d-214">Project Online and ProjectServer use proxies to communicate with the server for create, report, update, and delete (CRUD) operations.</span></span> <span data-ttu-id="1c44d-215">主机服务器更有效地处理请求，并包含客户端与服务器通信中执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1c44d-215">The host/server handles requests in an efficient manner and has the client perform the following actions in communicating with the server:</span></span>
  
1. <span data-ttu-id="1c44d-216">建立上下文通信。</span><span class="sxs-lookup"><span data-stu-id="1c44d-216">Establish a context for communication.</span></span> 
    
   <span data-ttu-id="1c44d-217">上下文使用项目集合，以及其他对象和通过继承，包括 tasks 集合、 assignments 集合、 阶段对象和自定义字段的集合。</span><span class="sxs-lookup"><span data-stu-id="1c44d-217">The context is used by the projects collection, as well as other objects and collections through inheritance, including the tasks collection, assignments collection, the stage object, and custom fields.</span></span> 
    
2. <span data-ttu-id="1c44d-218">使用对象模型指定的对象、 集合或要检索数据。</span><span class="sxs-lookup"><span data-stu-id="1c44d-218">Use the object model to specify an object, collection, or data to retrieve.</span></span>
    
   <span data-ttu-id="1c44d-219">此步骤中使用 LINQ 查询作为或方法。</span><span class="sxs-lookup"><span data-stu-id="1c44d-219">This step uses LINQ as a query or as a method.</span></span> <span data-ttu-id="1c44d-220">规范控制您收到的内容。</span><span class="sxs-lookup"><span data-stu-id="1c44d-220">The specification controls what you receive.</span></span> <span data-ttu-id="1c44d-221">通常，此步骤被嵌入作为正文 Load 方法 （第 3 步）。</span><span class="sxs-lookup"><span data-stu-id="1c44d-221">Often, this step is embedded as the body of the Load method (step 3).</span></span> 
    
3. <span data-ttu-id="1c44d-222">从使用 Load() 或 LoadQuery() 方法在上一步中加载检索规范。</span><span class="sxs-lookup"><span data-stu-id="1c44d-222">Load the retrieval specification from the previous step using the Load() or LoadQuery() method.</span></span>
    
   <span data-ttu-id="1c44d-223">加载集合和对象，使用 Load()。</span><span class="sxs-lookup"><span data-stu-id="1c44d-223">For loading collections and objects, use Load().</span></span> <span data-ttu-id="1c44d-224">为查询子句，如"位置"和"组"，使用 LoadQuery()。</span><span class="sxs-lookup"><span data-stu-id="1c44d-224">For queries with clauses such as "where" and "group", use LoadQuery().</span></span> 
    
4. <span data-ttu-id="1c44d-225">执行使用 ExecuteQuery() 方法的请求。</span><span class="sxs-lookup"><span data-stu-id="1c44d-225">Execute the request using the ExecuteQuery() method.</span></span>
    
   <span data-ttu-id="1c44d-226">ExecuteQuery() 方法通知宿主准备好执行的查询。</span><span class="sxs-lookup"><span data-stu-id="1c44d-226">The ExecuteQuery() method notifies the host that the query or queries are ready to execute.</span></span> <span data-ttu-id="1c44d-227">一旦主机接收通知时，它将执行查询并将结果发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="1c44d-227">Once the host receives notification, it executes the queries and sends the results to the client.</span></span> 
    
<span data-ttu-id="1c44d-228">在客户端的信息，该应用程序可以使用它。</span><span class="sxs-lookup"><span data-stu-id="1c44d-228">With the information at the client, the application can use it.</span></span> <span data-ttu-id="1c44d-229">下面的代码段的已发布项目中循环，并在主机上打印的 Id 和为每个已发布项目的名称。</span><span class="sxs-lookup"><span data-stu-id="1c44d-229">The following code fragment cycles through the published projects and prints the Id and Name for each published project on the host.</span></span>
  
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

<span data-ttu-id="1c44d-230">输出：</span><span class="sxs-lookup"><span data-stu-id="1c44d-230">Output:</span></span>
  
```cs
Published Project count:2
1. be80a848-b2ef-e511-80f4-00155dc84e01   A second Project     3/21/2016 10:14:40 PM
2. 9d730a1a-60ed-e511-80f6-00155dc87d01   Ent_Proj_1   3/18/2016 11:21:14 PM

```

### <a name="make-a-request"></a><span data-ttu-id="1c44d-231">发出请求</span><span class="sxs-lookup"><span data-stu-id="1c44d-231">Make a request</span></span>

<span data-ttu-id="1c44d-232">使用上一代码片段中的操作，应用程序检索中指定的帐户承载网站上的项目列表。</span><span class="sxs-lookup"><span data-stu-id="1c44d-232">Using the actions from the previous code fragment, the application retrieves the list of projects in the specified account on the hosting site.</span></span> 
  
1. <span data-ttu-id="1c44d-233">ProjectContext 指定列出的项目。</span><span class="sxs-lookup"><span data-stu-id="1c44d-233">The ProjectContext is specified for the projects to list.</span></span> 
    
   ```cs
    var projects = projContext.Projects;
   ```

2. <span data-ttu-id="1c44d-234">指定要检索的项。</span><span class="sxs-lookup"><span data-stu-id="1c44d-234">Specify the item to retrieve.</span></span> 
    
   ```cs
    projContext.Load(projects);
   ```

   <span data-ttu-id="1c44d-235">通过仅说明集合，该服务器检索填充的默认属性集值的每个项目的项目集合。</span><span class="sxs-lookup"><span data-stu-id="1c44d-235">By only stating the collection, the server retrieves the project collection, populating each project with values for the default set of properties.</span></span> <span data-ttu-id="1c44d-236">访问属性的默认属性集的一部分提供成功的结果。</span><span class="sxs-lookup"><span data-stu-id="1c44d-236">Accessing properties that are part of the default property set gives successful results.</span></span> <span data-ttu-id="1c44d-237">访问不是默认的一部分的属性设置将导致一个"未初始化"例外项。</span><span class="sxs-lookup"><span data-stu-id="1c44d-237">Accessing properties that are not part of the default set results in a "Not initialized" exception.</span></span>
    
3. <span data-ttu-id="1c44d-238">加载请求 (projContext.Load)。</span><span class="sxs-lookup"><span data-stu-id="1c44d-238">Load the request (projContext.Load).</span></span>
    
   <span data-ttu-id="1c44d-239">这是在上一步的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c44d-239">This is part of the previous step.</span></span>
    
4. <span data-ttu-id="1c44d-240">执行查询 (ExecuteQuery)。</span><span class="sxs-lookup"><span data-stu-id="1c44d-240">Execute the query (ExecuteQuery).</span></span> 
    
   ```cs
    projContext.ExecuteQuery();
   ```

### <a name="retrieve-high-level-project-information"></a><span data-ttu-id="1c44d-241">检索高级项目信息</span><span class="sxs-lookup"><span data-stu-id="1c44d-241">Retrieve high-level project information</span></span>

<span data-ttu-id="1c44d-242">不是必须到服务器请求中指定的默认属性的属性。</span><span class="sxs-lookup"><span data-stu-id="1c44d-242">Properties that are not default properties must be specified in the request to the server.</span></span> <span data-ttu-id="1c44d-243">下面的代码段加载与前面的示例的项目集上下文。</span><span class="sxs-lookup"><span data-stu-id="1c44d-243">The next code fragment loads the projects collection context as in the previous example.</span></span> <span data-ttu-id="1c44d-244">然后，规范请求要在结果中包括的其他非默认属性。</span><span class="sxs-lookup"><span data-stu-id="1c44d-244">Then, the specification requests additional non-default properties to include in the result.</span></span> 
  
```cs
var projects = projContext.Projects;
projContext.Load(projects,
    ps => ps.IncludeWithDefaultProperties(
        p => p.StartDate, p => p.Phase, p => p.Stage));
projContext.ExecuteQuery();

```

<span data-ttu-id="1c44d-245">Load 语句指定的项目集上下文，并将阶段，StartDate 和阶段添加到查询结果。</span><span class="sxs-lookup"><span data-stu-id="1c44d-245">The load statement specifies the projects collection context, and adds the StartDate, Phase, and Stage to the query result.</span></span> <span data-ttu-id="1c44d-246">其他属性可以是标量，对象或集合。</span><span class="sxs-lookup"><span data-stu-id="1c44d-246">The additional properties can be scalar, objects, or collections.</span></span> <span data-ttu-id="1c44d-247">可以直接访问标量项目。</span><span class="sxs-lookup"><span data-stu-id="1c44d-247">Scalar items can be accessed directly.</span></span> <span data-ttu-id="1c44d-248">对象和集合需要进行其他处理，如下面的代码片段中所示。</span><span class="sxs-lookup"><span data-stu-id="1c44d-248">Objects and collections require additional processing, as in the following code fragment.</span></span>
  
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

<span data-ttu-id="1c44d-249">前三个项目的输出：</span><span class="sxs-lookup"><span data-stu-id="1c44d-249">Output of the first three projects:</span></span>
  
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

### <a name="retrieve-all-tasks-in-a-project"></a><span data-ttu-id="1c44d-250">检索项目中的所有任务</span><span class="sxs-lookup"><span data-stu-id="1c44d-250">Retrieve all tasks in a project</span></span>

<span data-ttu-id="1c44d-251">每个项目中有多个任务。</span><span class="sxs-lookup"><span data-stu-id="1c44d-251">Each project has many tasks.</span></span> <span data-ttu-id="1c44d-252">因此，将单个项目的任务以下内容组成：</span><span class="sxs-lookup"><span data-stu-id="1c44d-252">So, pulling the tasks for a single project consists of the following:</span></span>
  
1. <span data-ttu-id="1c44d-253">建立项目集合的上下文。</span><span class="sxs-lookup"><span data-stu-id="1c44d-253">Establish the context of the projects collection.</span></span>
    
   ```cs
    var projects = projContext.Projects;
   ```

2. <span data-ttu-id="1c44d-254">检索的项目信息，包括任务属性。</span><span class="sxs-lookup"><span data-stu-id="1c44d-254">Retrieve the project information, including the Task properties.</span></span>
    
   ```cs
    projContext.Load(projects);
    ProjContext.ExecuteQuery();
    foreach (PublishedProject pubProj in projContext.Projects){
    
   ```

    <span data-ttu-id="1c44d-255">请注意，解决应用程序已发布的项目。</span><span class="sxs-lookup"><span data-stu-id="1c44d-255">Note that the application is addressing published projects.</span></span> <span data-ttu-id="1c44d-256">当前已发布的项目的上下文是 pubProj。</span><span class="sxs-lookup"><span data-stu-id="1c44d-256">The context for the current published project is pubProj.</span></span> 
    
3. <span data-ttu-id="1c44d-257">建立 Tasks 集合的上下文。</span><span class="sxs-lookup"><span data-stu-id="1c44d-257">Establish the context for the Tasks collection.</span></span>
    
   ```cs
    PublishedTaskCollection collTask = pubProj.Tasks;
   ```

   <span data-ttu-id="1c44d-258">`pubProj.Tasks`属性引用当前已发布的项目的任务。</span><span class="sxs-lookup"><span data-stu-id="1c44d-258">The `pubProj.Tasks` property references the tasks of the current published project.</span></span> 
    
4. <span data-ttu-id="1c44d-259">加载规范若要检索任务集合，包括相应的非默认属性。</span><span class="sxs-lookup"><span data-stu-id="1c44d-259">Load the specification to retrieve Task collection, including the appropriate non-default properties.</span></span>
    
   ```cs
    projContext.Load(collTask,
        tsk => tsk.IncludeWithDefaultProperties(
            t => t.Id, t => t.Name, t => t.Start,
            t => t.ScheduledStart, t => t.Completion));
    
   ```

5. <span data-ttu-id="1c44d-260">执行查询来检索与相应的属性的任务集合。</span><span class="sxs-lookup"><span data-stu-id="1c44d-260">Execute the query to retrieve the Task collection with the appropriate properties.</span></span>
    
   ```cs
    projContext.ExecuteQuery();
   ```

<span data-ttu-id="1c44d-261">现在，本地信息。</span><span class="sxs-lookup"><span data-stu-id="1c44d-261">The information is now local.</span></span> <span data-ttu-id="1c44d-262">下面的代码段的信息写入控制台来处理发布的 tasks 集合。</span><span class="sxs-lookup"><span data-stu-id="1c44d-262">The following code fragment processes the published tasks collection by writing the information to the console.</span></span>
  
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

<span data-ttu-id="1c44d-263">一个项目的任务的输出：</span><span class="sxs-lookup"><span data-stu-id="1c44d-263">Output of tasks for one project:</span></span>
  
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

### <a name="access-information-at-multiple-levels"></a><span data-ttu-id="1c44d-264">在多个级别的访问信息</span><span class="sxs-lookup"><span data-stu-id="1c44d-264">Access information at multiple levels</span></span>

<span data-ttu-id="1c44d-265">每项任务 （也可以有一个或多个人员</span><span class="sxs-lookup"><span data-stu-id="1c44d-265">Each task can have one or more persons (a.k.a.</span></span> <span data-ttu-id="1c44d-266">资源） 有影响其完成。</span><span class="sxs-lookup"><span data-stu-id="1c44d-266">resource) contributing toward its completion.</span></span> <span data-ttu-id="1c44d-267">分配和资源的集合包含每个任务此信息。</span><span class="sxs-lookup"><span data-stu-id="1c44d-267">The Assignments and Resources collections contain this information for each task.</span></span> 
  
<span data-ttu-id="1c44d-268">处理由以下内容组成：</span><span class="sxs-lookup"><span data-stu-id="1c44d-268">The processing consists of the following:</span></span>
  
1. <span data-ttu-id="1c44d-269">获取项目任务的上下文。</span><span class="sxs-lookup"><span data-stu-id="1c44d-269">Obtaining a context for the project task.</span></span>
    
2. <span data-ttu-id="1c44d-270">生成一个请求和负载绑定到任务的分配请求。</span><span class="sxs-lookup"><span data-stu-id="1c44d-270">Build a request and load the request for the assignments tied to the task.</span></span> 
    
3. <span data-ttu-id="1c44d-271">执行将工作分配的查询。</span><span class="sxs-lookup"><span data-stu-id="1c44d-271">Execute the query for the assignments.</span></span>
    
4. <span data-ttu-id="1c44d-272">生成一个请求和负载与单个工作分配关联的资源的请求。</span><span class="sxs-lookup"><span data-stu-id="1c44d-272">Build a request and load the request for the resource associated with an individual assignment.</span></span> 
    
5. <span data-ttu-id="1c44d-273">执行资源的查询。</span><span class="sxs-lookup"><span data-stu-id="1c44d-273">Execute the query for the resource.</span></span>
    
> [!NOTE] 
> - <span data-ttu-id="1c44d-274">从服务器的信息中显式请求 Assignments 集合，因为它不是在 Tasks 集合的默认属性。</span><span class="sxs-lookup"><span data-stu-id="1c44d-274">The Assignments collection is explicitly requested in the information from the server because it is not a default property of the Tasks collection.</span></span> <span data-ttu-id="1c44d-275">作为集合，后续查询进行拉从服务器的集合。</span><span class="sxs-lookup"><span data-stu-id="1c44d-275">As a collection, a subsequent query is made to pull the collection from the server.</span></span> 
> - <span data-ttu-id="1c44d-276">资源是一个对象。</span><span class="sxs-lookup"><span data-stu-id="1c44d-276">The Resource is an object.</span></span> <span data-ttu-id="1c44d-277">工作分配的查询包括与工作分配关联的资源名称。</span><span class="sxs-lookup"><span data-stu-id="1c44d-277">The query for an assignment includes the resource name associated with the assignment.</span></span>
    
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

<span data-ttu-id="1c44d-278">任务 52、 75 和 76 项目的输出：</span><span class="sxs-lookup"><span data-stu-id="1c44d-278">Output for tasks 52, 75, and 76 of a project:</span></span>
  
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

### <a name="access-custom-enterprise-level-fields"></a><span data-ttu-id="1c44d-279">访问自定义企业级字段</span><span class="sxs-lookup"><span data-stu-id="1c44d-279">Access custom enterprise-level fields</span></span>

<span data-ttu-id="1c44d-280">自定义域 for Project Online 中存在。</span><span class="sxs-lookup"><span data-stu-id="1c44d-280">Custom fields exist for Project Online.</span></span> <span data-ttu-id="1c44d-281">这些是可以与单个项目相关联的企业级字段。</span><span class="sxs-lookup"><span data-stu-id="1c44d-281">These are enterprise-level fields that can be associated with individual project.</span></span> <span data-ttu-id="1c44d-282">本节介绍如何访问这些字段。</span><span class="sxs-lookup"><span data-stu-id="1c44d-282">This section describes how to access these fields.</span></span> 
  
<span data-ttu-id="1c44d-283">自定义域不包含在与项目关联的属性的默认设置。</span><span class="sxs-lookup"><span data-stu-id="1c44d-283">Custom fields are not included in the default set of properties associated with a project.</span></span> <span data-ttu-id="1c44d-284">因此，他们需要检索规范中的显式标识。</span><span class="sxs-lookup"><span data-stu-id="1c44d-284">So, they need explicit identification in the retrieval specification.</span></span> <span data-ttu-id="1c44d-285">概括的过程包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="1c44d-285">The high-level view of the process consists of the following items:</span></span>
  
1. <span data-ttu-id="1c44d-286">隧道到使用公用名称的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="1c44d-286">Tunnel to the custom field using its common name.</span></span>
    
2. <span data-ttu-id="1c44d-287">检索自定义字段的内部名称。</span><span class="sxs-lookup"><span data-stu-id="1c44d-287">Retrieve the internal name of the custom field.</span></span>
    
3. <span data-ttu-id="1c44d-288">返回到全局上下文和查询使用自定义字段的内部名称的系统。</span><span class="sxs-lookup"><span data-stu-id="1c44d-288">Return to the global context and query the system using the internal name of the custom field.</span></span>
    
#### <a name="tunnel-to-the-custom-field-retrieve-its-internal-name-and-used-it-to-query-the-system"></a><span data-ttu-id="1c44d-289">隧道到自定义字段、 检索其内部名称，并使用它来查询系统</span><span class="sxs-lookup"><span data-stu-id="1c44d-289">Tunnel to the custom field, retrieve its internal name, and used it to query the system</span></span>

<span data-ttu-id="1c44d-290">此任务指定非默认属性使用一个增加了详细信息检索。</span><span class="sxs-lookup"><span data-stu-id="1c44d-290">This task specifies a retrieval that uses a non-default property with one added detail.</span></span>
  
1. <span data-ttu-id="1c44d-291">开始使用项目上下文，如本文开头所述。</span><span class="sxs-lookup"><span data-stu-id="1c44d-291">Begin by using the projects context, as described at the beginning of this article.</span></span>
    
   ```cs
    // Get the list of published projects in Project Web App.
    var projects = projContext.Projects;
    
   ```

2. <span data-ttu-id="1c44d-292">将两个项目添加到项目集合检索除了任何其他非默认属性用于检索请求：</span><span class="sxs-lookup"><span data-stu-id="1c44d-292">Add two items to the projects collection retrieval request in addition to any other non-default properties to retrieve:</span></span>
    
   ```cs
    projContext.Load(projects,
        ps => ps.IncludeWithDefaultProperties(
            p => p.Phase, p => p.Stage,                  // Other nondefault properties
            p => p.IncludeCustomFields,                  // Gets PublishedProject object 
                                                        // that contains custom fields
            p => p.IncludeCustomFields.CustomFields));   // Populates the custom fields
                    projContext.ExecuteQuery();
    
   ```

   <span data-ttu-id="1c44d-293">`p => p.IncludeCustomFields`子句标识需要使用支持自定义字段项目对象。</span><span class="sxs-lookup"><span data-stu-id="1c44d-293">The  `p => p.IncludeCustomFields` clause identifies the need to use a project object that supports custom fields.</span></span> 
    
   <span data-ttu-id="1c44d-294">`p => p.IncludeCustomFields.CustomFields`子句请求包含在查询结果中的自定义字段数据。</span><span class="sxs-lookup"><span data-stu-id="1c44d-294">The  `p => p.IncludeCustomFields.CustomFields` clause requests the inclusion of custom field data in the query result.</span></span> <span data-ttu-id="1c44d-295">检索自定义字段内部名称后，将使用此信息。</span><span class="sxs-lookup"><span data-stu-id="1c44d-295">This information is used after the custom field internal name is retrieved.</span></span> 
    
3. <span data-ttu-id="1c44d-296">加载该请求。</span><span class="sxs-lookup"><span data-stu-id="1c44d-296">Load the request.</span></span>
    
   <span data-ttu-id="1c44d-297">这是在上一步的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c44d-297">This is part of the previous step.</span></span>
    
4. <span data-ttu-id="1c44d-298">执行查询。</span><span class="sxs-lookup"><span data-stu-id="1c44d-298">Execute the Query.</span></span>
    
   ```cs
    projContext.ExecuteQuery()
   ```

5. <span data-ttu-id="1c44d-299">使用此客户端上的信息，生成请求检索与当前项目关联的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="1c44d-299">With this information on the client, build a request to retrieve the custom fields associated with the current project.</span></span>
    
   ```cs
    foreach (PublishedProject pubProj in projContext.Projects)
    {
        //Console.WriteLine("\n\t{0}. \t{1} \n\t\t{2} \n\t\t{3} \n", 
                j++, pubProj.Id, pubProj.Name, pubProj.CreatedDate);
        CustomFieldCollection collCustF = pubProj.CustomFields;
                        
        projContext.Load(collCustF);
        projContext.ExecuteQuery();
    
   ```

6. <span data-ttu-id="1c44d-300">找到相应的自定义字段和检索的字段的内部名称。</span><span class="sxs-lookup"><span data-stu-id="1c44d-300">Locate the appropriate custom field and retrieve the internal name of the field.</span></span> 
    
   ```cs
        foreach (CustomField oCF in collCustF)
        {
            if (oCF.Name == "Project Health")
            {
                Console.WriteLine("Name: {0}", oCF.Name);
                Console.WriteLine("InternalName: {0}", oCF.InternalName);
    
   ```

   <span data-ttu-id="1c44d-301">检索自定义字段的内部名称。</span><span class="sxs-lookup"><span data-stu-id="1c44d-301">The internal name of the custom field is retrieved.</span></span> <span data-ttu-id="1c44d-302">高级项目 1 和 2 现在已完成。</span><span class="sxs-lookup"><span data-stu-id="1c44d-302">High-level items 1 and 2 are now complete.</span></span>
    
7. <span data-ttu-id="1c44d-303">返回到项目上下文并检索的自定义域的值。</span><span class="sxs-lookup"><span data-stu-id="1c44d-303">Return to the project context and retrieve the value of the custom field.</span></span>
    
   ```cs
    Console.WriteLine("Value: {0}", 
        pubProj.IncludeCustomFields.FieldValues[oCF.InternalName]);
    
   ```

   > [!NOTE]
   > <span data-ttu-id="1c44d-304">自定义字段的值是作为索引使用的内部名称检索的。</span><span class="sxs-lookup"><span data-stu-id="1c44d-304">The value of the custom field is retrieved using the internal name as an index.</span></span> 
  
<span data-ttu-id="1c44d-305">项目 ID、 项目名称、 自定义域名称、 自定义字段内部名称和自定义域值组成的三个项目的输出。</span><span class="sxs-lookup"><span data-stu-id="1c44d-305">Output of three projects consisting of project ID, project Name, custom field name, custom field internal name, and custom field value.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="1c44d-306">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c44d-306">See also</span></span>

<span data-ttu-id="1c44d-307">有关文档和与 Project Online 和使用 CSOM 的应用程序开发相关的示例，请参阅[Project 开发门户](https://developer.microsoft.com/en-us/project)。</span><span class="sxs-lookup"><span data-stu-id="1c44d-307">For documentation and samples related to Project Online and application development using CSOM, see the [Project Development Portal](https://developer.microsoft.com/en-us/project).</span></span>
    

