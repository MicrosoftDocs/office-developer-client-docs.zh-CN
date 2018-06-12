---
title: 在项目中的基于 ASMX 的代码示例的先决条件
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
f1_keywords:
- code samples
- Project Server code samples
- Project Server programming
- PSI code samples
- PSI programming
keywords:
- 代码示例、 project server、 Project Server 编程 PSI，编译代码示例，PSI，编程 （英文）
localization_priority: Normal
ms.assetid: df584b25-4460-46c8-89a8-3b2c94d20bba
description: 了解可帮助您使用 Project Server 接口 (PSI) 参考主题中包含的基于 ASMX 的代码示例在 Visual Studio 中创建项目的信息。
ms.openlocfilehash: 73d097211dc3c68e1066c2ea1ad8d51a616184d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779558"
---
# <a name="prerequisites-for-asmx-based-code-samples-in-project"></a><span data-ttu-id="6ea3c-104">在项目中的基于 ASMX 的代码示例的先决条件</span><span class="sxs-lookup"><span data-stu-id="6ea3c-104">Prerequisites for ASMX-based code samples in Project</span></span>

<span data-ttu-id="6ea3c-105">了解可帮助您使用 Project Server 接口 (PSI) 参考主题中包含的基于 ASMX 的代码示例在 Visual Studio 中创建项目的信息。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-105">Learn information to help you create projects in Visual Studio by using the ASMX-based code samples that are included in the Project Server Interface (PSI) reference topics.</span></span>
  
<span data-ttu-id="6ea3c-106">[Project Server 2013 类类库和 web 服务引用](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)中包含的代码示例的许多原来创建的 Office Project 2007 SDK，并用于 ASMX web 服务的标准格式。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-106">Many of the code samples included in the [Project Server 2013 class library and web service reference](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx) were originally created for the Office Project 2007 SDK, and use a standard format for ASMX web services.</span></span> <span data-ttu-id="6ea3c-107">示例仍在 Project Server 2013 中工作，旨在复制到控制台应用程序和运行完整的单位。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-107">The samples still work in Project Server 2013 and are designed to be copied into a console application and run as a complete unit.</span></span> <span data-ttu-id="6ea3c-108">例外示例中进行说明。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-108">Exceptions are noted in the sample.</span></span> 
  
<span data-ttu-id="6ea3c-109">新 Project 2013 SDK 中的 PSI 示例符合使用 Windows Communication Foundation (WCF) 服务的格式。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-109">New PSI samples in the Project 2013 SDK conform to a format that uses Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="6ea3c-110">也可以修改用于 WCF 服务的基于 ASMX 的示例。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-110">The ASMX-based samples can also be adapted to use WCF services.</span></span> <span data-ttu-id="6ea3c-111">本文介绍如何使用 ASMX web 服务的示例。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-111">This article shows how to use the samples with ASMX web services.</span></span> <span data-ttu-id="6ea3c-112">有关使用这些示例使用 WCF 服务的信息，请参阅[项目中的基于 WCF 的代码示例的先决条件](prerequisites-for-wcf-based-code-samples-in-project.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-112">For information about using the samples with WCF services, see [Prerequisites for WCF-based code samples in Project](prerequisites-for-wcf-based-code-samples-in-project.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ea3c-113">PSI 的 ASMX web 服务界面在 Project Server 2013 中已弃用，但仍然支持。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-113">The ASMX web service interface of the PSI is deprecated in Project Server 2013, but is still supported.</span></span> <span data-ttu-id="6ea3c-114">如果客户端对象模型 (CSOM) 包括您的应用程序需要的方法，则应使用 CSOM 开发新应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-114">If the client-side object model (CSOM) includes the methods that your application requires, new applications should be developed with the CSOM.</span></span> <span data-ttu-id="6ea3c-115">CSOM 使应用程序与 Project Online 或 Project Server 2013 的本地安装一起使用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-115">The CSOM enables applications to work with Project Online or an on-premises installation of Project Server 2013.</span></span> <span data-ttu-id="6ea3c-116">否则，如果您的应用程序使用 PSI，它应使用 WCF 接口，这是建议的网络通信的技术。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-116">Otherwise, if your application uses the PSI, it should use the WCF interface, which is the technology that we recommend for network communications.</span></span> <span data-ttu-id="6ea3c-117">使用 ASMX 接口或 WCF 接口的应用程序可以处理仅用于 Project Server 2013 的本地安装。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-117">Applications that use the ASMX interface or the WCF interface can work only for on-premises installations of Project Server 2013.</span></span> <span data-ttu-id="6ea3c-118">有关 CSOM 的详细信息，请参阅[Project Server 2013 体系结构](project-server-2013-architecture.md)和[客户端对象模型 (CSOM) for Project 2013](client-side-object-model-csom-for-project-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-118">For more information about the CSOM, see [Project Server 2013 architecture](project-server-2013-architecture.md) and [Client-side object model (CSOM) for Project 2013](client-side-object-model-csom-for-project-2013.md).</span></span> 
  
<span data-ttu-id="6ea3c-119">在运行代码示例之前，必须先设置开发环境、配置应用程序并更改泛型常量值以匹配您的环境。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-119">Before running the code samples, you must set up the development environment, configure the application, and change generic constant values to match your environment.</span></span>
  
## <a name="setting-up-the-development-environment"></a><span data-ttu-id="6ea3c-120">设置开发环境</span><span class="sxs-lookup"><span data-stu-id="6ea3c-120">Setting up the development environment</span></span>
<span data-ttu-id="6ea3c-121"><a name="pj15_PrerequisitesASMX_Setup"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-121"></span></span>

1. <span data-ttu-id="6ea3c-122">**设置测试 Project Server 系统**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-122">**Set up a test Project Server system**.</span></span>
    
   <span data-ttu-id="6ea3c-p104">在进行开发或测试时，请使用测试 Project Server 系统。即使您的代码正常运行，项目间的相关性、报告或其他环境因素也会导致意想不到的结果。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-p104">Use a test Project Server system whenever you are developing or testing. Even when your code works perfectly, interproject dependencies, reporting, or other environmental factors can cause unintended consequences.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="6ea3c-125">确保您是有效的用户的服务器上，并确认您具有足够的权限的应用程序使用的 PSI 调用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-125">Ensure that you are a valid user on the server, and check that you have sufficient permissions for the PSI calls that your application uses.</span></span> <span data-ttu-id="6ea3c-126">每个 PSI 方法的参考主题包括 Project Server 权限表。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-126">The reference topic for each PSI method includes a Project Server Permissions table.</span></span> <span data-ttu-id="6ea3c-127">例如， [Project.QueueCreateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueCreateProject.aspx)方法要求**新建项目**全局权限和**SaveProjectTemplate**权限。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-127">For example, the [Project.QueueCreateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueCreateProject.aspx) method requires the global **NewProject** permission and the **SaveProjectTemplate** permission.</span></span> 
  
   <span data-ttu-id="6ea3c-128">在某些情况下，您可能需要执行远程调试服务器上。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-128">In some cases, you may have to do remote debugging on the server.</span></span> <span data-ttu-id="6ea3c-129">您可能还需要设置事件处理程序，通过在 SharePoint 场中每个 Project Server 计算机上安装事件处理程序程序集，然后使用中常规 Project Server 设置页上配置的事件处理程序的 Project Web App 实例SharePoint 管理中心的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-129">You may also have to set up an event handler by installing an event handler assembly on each Project Server computer in the SharePoint farm, and then configuring the event handler for the Project Web App instance by using the Project Server Settings page in the General Application Settings of SharePoint Central Administration.</span></span>
    
2. <span data-ttu-id="6ea3c-130">**设置开发计算机。**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-130">**Set up a development computer.**</span></span>
    
   <span data-ttu-id="6ea3c-p107">通常，您会通过网络访问 PSI。代码示例设计为在独立于服务器的客户端上运行，除非另有说明。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-p107">You usually access the PSI through a network. The code samples are designed to be run on a client that is separate from the server, except where noted.</span></span>
    
   1. <span data-ttu-id="6ea3c-133">**安装 Visual Studio 的正确版本。**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-133">**Install the correct version of Visual Studio.**</span></span> <span data-ttu-id="6ea3c-134">除非另有说明，代码示例会写入 Visual C# 中。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-134">Except where noted, the code samples are written in Visual C#.</span></span> <span data-ttu-id="6ea3c-135">它们可用于 Visual Studio 2010 或 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-135">They can be used with Visual Studio 2010 or Visual Studio 2012.</span></span> <span data-ttu-id="6ea3c-136">确保您已安装最新 service pack。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-136">Ensure that you have the most recent service pack installed.</span></span> 
        
   2. <span data-ttu-id="6ea3c-137">**将 Project Server Dll 复制到开发计算机。**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-137">**Copy Project Server DLLs to the development computer.**</span></span> <span data-ttu-id="6ea3c-138">复制以下程序集从`[Program Files]\Microsoft Office Servers\15.0\Bin`到开发计算机上的 Project Server 计算机上：</span><span class="sxs-lookup"><span data-stu-id="6ea3c-138">Copy the following assemblies from  `[Program Files]\Microsoft Office Servers\15.0\Bin` on the Project Server computer to the development computer:</span></span> 
        
      - <span data-ttu-id="6ea3c-139">Microsoft.Office.Project.Server.Events.Receivers.dll</span><span class="sxs-lookup"><span data-stu-id="6ea3c-139">Microsoft.Office.Project.Server.Events.Receivers.dll</span></span>
      - <span data-ttu-id="6ea3c-140">Microsoft.Office.Project.Server.Library.dll</span><span class="sxs-lookup"><span data-stu-id="6ea3c-140">Microsoft.Office.Project.Server.Library.dll</span></span>
        
   3. <span data-ttu-id="6ea3c-141">有关如何编译和使用 ProjectServerServices.dll 代理程序集中 PSI 的 ASMX web 服务的信息，请参阅[使用 PSI 代理程序集和 IntelliSense 说明](#pj15_PrerequisitesASMX_BuildingProxy)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-141">For information about how to compile and use the ProjectServerServices.dll proxy assembly for the ASMX web services in the PSI, see [Using a PSI proxy assembly and IntelliSense descriptions](#pj15_PrerequisitesASMX_BuildingProxy).</span></span>
    
3. <span data-ttu-id="6ea3c-142">**安装 IntelliSense 文件。**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-142">**Install the IntelliSense files.**</span></span>
    
    <span data-ttu-id="6ea3c-143">要用于 Project Server 程序集，副本中类和成员的 IntelliSense 说明从 Project 2013 SDK 更新的 IntelliSense XML 文件下载到 Project Server 程序集所在的同一目录。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-143">To use IntelliSense descriptions for classes and members in Project Server assemblies, copy the updated IntelliSense XML files from the Project 2013 SDK download to the same directory where the Project Server assemblies are located.</span></span> <span data-ttu-id="6ea3c-144">例如，将 Microsoft.Office.Project.Server.Library.xml 文件复制到您的应用程序将在其中设置 Microsoft.Office.Project.Server.Library.dll 程序集的引用的目录。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-144">For example, copy the Microsoft.Office.Project.Server.Library.xml file to the directory where your application will set a reference to the Microsoft.Office.Project.Server.Library.dll assembly.</span></span>
    
    <span data-ttu-id="6ea3c-145">IntelliSense 说明的 PSI web 服务需要使用 CompileASMXProxyAssembly.cmd 脚本创建 PSI 代理程序集`Documentation\IntelliSense\WSDL`Project 2013 SDK 下载中的子目录。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-145">IntelliSense descriptions for the PSI web services require that you create a PSI proxy assembly by using the CompileASMXProxyAssembly.cmd script in the  `Documentation\IntelliSense\WSDL` subdirectory in the Project 2013 SDK download.</span></span> <span data-ttu-id="6ea3c-146">该脚本创建基于 ASMX 的 ProjectServerServices.dll 代理程序集。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-146">The script creates the ASMX-based ProjectServerServices.dll proxy assembly.</span></span> <span data-ttu-id="6ea3c-147">有关详细信息，请参阅 SDK 下载中的 [ReadMe_IntelliSense] 文件。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-147">For more information, see the [ReadMe_IntelliSense] file in the SDK download.</span></span> 
    
## <a name="creating-the-application-and-adding-a-web-service-reference"></a><span data-ttu-id="6ea3c-148">创建应用程序并添加 Web 服务引用</span><span class="sxs-lookup"><span data-stu-id="6ea3c-148">Creating the application and adding a web service reference</span></span>
<span data-ttu-id="6ea3c-149"><a name="pj15_PrerequisitesASMX_Configure"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-149"></span></span>

1. <span data-ttu-id="6ea3c-150">**创建一个控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-150">**Create a console application**.</span></span>
    
   <span data-ttu-id="6ea3c-151">当您创建控制台应用程序，在**新建项目**对话框中下拉列表中时，选择 **.NET Framework 4**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-151">When you create a console application, in the drop-down list of the **New Project** dialog box, select **.NET Framework 4**.</span></span> <span data-ttu-id="6ea3c-152">您可以将 PSI 示例代码复制到新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-152">You can copy the PSI example code into the new application.</span></span>
    
2. <span data-ttu-id="6ea3c-153">**添加 ASMX 所需的引用。**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-153">**Add the reference required for ASMX.**</span></span>
    
   <span data-ttu-id="6ea3c-154">在解决方案资源管理器中，添加对**system.web.services 的引用**（见图 1）。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-154">In Solution Explorer, add a reference to **System.Web.Services** (see Figure 1).</span></span> 
    
   <span data-ttu-id="6ea3c-155">**图 1。在 Visual Studio 中添加引用**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-155">**Figure 1. Adding a reference in Visual Studio**</span></span>

   <span data-ttu-id="6ea3c-156">![添加在 Visual Studio 中的引用](media/pj15_PrerequisitesASMX_AddReference.gif "添加在 Visual Studio 中的引用")</span><span class="sxs-lookup"><span data-stu-id="6ea3c-156">![Adding a reference in Visual Studio](media/pj15_PrerequisitesASMX_AddReference.gif "Adding a reference in Visual Studio")</span></span>
  
3. <span data-ttu-id="6ea3c-157">**复制代码**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-157">**Copy the code**.</span></span>
    
   <span data-ttu-id="6ea3c-158">将完整的代码示例复制到控制台应用程序的 Program.cs 文件中。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-158">Copy the complete code example into the Program.cs file of the console application.</span></span>
    
4. <span data-ttu-id="6ea3c-159">**设置示例应用程序的命名空间**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-159">**Set the namespace for the sample application**.</span></span>
    
   <span data-ttu-id="6ea3c-p113">您可将示例顶部列出的命名空间更改为应用程序的默认命名空间，或更改默认的应用程序命名空间以与示例匹配。可以通过更改应用程序属性来更改默认应用程序命名空间。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-p113">You can either change the namespace listed at the top of the sample to the application default namespace, or change the default application namespace to match the sample. You can change the default application namespace by changing the application properties.</span></span>
    
   <span data-ttu-id="6ea3c-162">例如， [QueueRenameProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueRenameProject.aspx)的代码示例具有**Microsoft.SDK.Project.Samples.RenameProject**的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-162">For example, the code sample for [QueueRenameProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueRenameProject.aspx) has the namespace **Microsoft.SDK.Project.Samples.RenameProject**.</span></span> <span data-ttu-id="6ea3c-163">如果 Visual Studio 项目的名称， **RenameProject**从 Program.cs 文件中，复制该命名空间，然后打开项目**属性**窗格 （在**项目**菜单中选择**RenameProject 属性**）。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-163">If the name of the Visual Studio project is **RenameProject**, copy the namespace from the Program.cs file, and then open the project **Properties** pane (on the **Project** menu, choose **RenameProject Properties**).</span></span> <span data-ttu-id="6ea3c-164">在**应用程序**选项卡中，将命名空间复制到**默认命名空间**文本框。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-164">On the **Application** tab, copy the namespace into the **Default namespace** text box.</span></span> 
    
5. <span data-ttu-id="6ea3c-165">**设置 web 引用**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-165">**Set the web references**.</span></span>
    
   <span data-ttu-id="6ea3c-p115">大多数示例都需要对一个或多个 PSI Web 服务的引用。它们将在示例本身中或示例前面的注释中列出。若要获取 Web 引用的正确命名空间，请确保您先设置默认应用程序命名空间。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-p115">Most examples require a reference to one or more of the PSI web services. These are listed in the sample itself or in comments that precede the sample. To get the correct namespace of the web references, ensure that you first set the default application namespace.</span></span>
    
   <span data-ttu-id="6ea3c-169">可通过三种方式添加 PSI 的 ASMX Web 服务引用：</span><span class="sxs-lookup"><span data-stu-id="6ea3c-169">There are three ways to add an ASMX web service reference for the PSI:</span></span>
    
   - <span data-ttu-id="6ea3c-170">生成 PSI 代理程序集名为 ProjectServerServices.dll，并将程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-170">Build a PSI proxy assembly named ProjectServerServices.dll, and then set a reference to the assembly.</span></span> <span data-ttu-id="6ea3c-171">若要获取智能感知，这是建议的方式添加 PSI 引用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-171">To get IntelliSense, this is the recommended way to add a PSI reference.</span></span> <span data-ttu-id="6ea3c-172">请参阅[使用 PSI 代理程序集和 IntelliSense 说明](#pj15_PrerequisitesASMX_BuildingProxy)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-172">See [Using a PSI proxy assembly and IntelliSense descriptions](#pj15_PrerequisitesASMX_BuildingProxy).</span></span>
    
   - <span data-ttu-id="6ea3c-173">向 Visual Studio 解决方案从 wsdl.exe 输出添加代理文件。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-173">Add a proxy file from the wsdl.exe output to the Visual Studio solution.</span></span> <span data-ttu-id="6ea3c-174">请参阅[添加 PSI 代理文件](#pj15_PrerequisitesASMX_AddingProxyFile)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-174">See [Adding a PSI proxy file](#pj15_PrerequisitesASMX_AddingProxyFile).</span></span>
    
   - <span data-ttu-id="6ea3c-175">使用 Visual Studio 中添加 web 服务引用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-175">Add a web service reference by using Visual Studio.</span></span> <span data-ttu-id="6ea3c-176">请参阅[添加 web 服务引用](#pj15_PrerequisitesASMX_AddingServiceReference)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-176">See [Adding a web service reference](#pj15_PrerequisitesASMX_AddingServiceReference).</span></span>

<span data-ttu-id="6ea3c-177"><a name="pj15_PrerequisitesASMX_BuildingProxy"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-177"></span></span>

### <a name="using-a-psi-proxy-assembly-and-intellisense-descriptions"></a><span data-ttu-id="6ea3c-178">使用 PSI 代理程序集和 IntelliSense 说明</span><span class="sxs-lookup"><span data-stu-id="6ea3c-178">Using a PSI proxy assembly and IntelliSense descriptions</span></span>

<span data-ttu-id="6ea3c-179">您可以生成并通过 CompileASMXProxyAssembly.cmd 脚本中 PSI，所有基于 ASMX web 服务的使用 ProjectServerServices.dll 代理程序集`Documentation\IntelliSense\WSDL`Project 2013 SDK 下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-179">You can build and use the ProjectServerServices.dll proxy assembly for all ASMX-based web services in the PSI, by using the CompileASMXProxyAssembly.cmd script in the  `Documentation\IntelliSense\WSDL` folder of the Project 2013 SDK download.</span></span> <span data-ttu-id="6ea3c-180">下载链接，请参阅[Project 2013 开发人员文档](project-2013-developer-documentation.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-180">For a link to the download, see [Project 2013 developer documentation](project-2013-developer-documentation.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ea3c-181">当您从 Source.zip 提取代理源文件文件中的文件`Documentation\IntelliSense\WSDL\Source`文件夹的当前 Project 2013 SDK 下载的发布日期。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-181">When you extract the proxy source files from the Source.zip file, the files in the  `Documentation\IntelliSense\WSDL\Source` folder are current as of the publication date of the Project 2013 SDK download.</span></span> <span data-ttu-id="6ea3c-182">若要生成更新 Project Server 计算机上运行 GenASMXProxyAssembly.cmd 脚本的 PSI 代理源文件。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-182">To generate updated PSI proxy source files, run the GenASMXProxyAssembly.cmd script on the Project Server computer.</span></span> <span data-ttu-id="6ea3c-183">中的脚本`Documentation\IntelliSense\WCF`文件夹基于 ASMX 的应用程序不起作用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-183">The scripts in the  `Documentation\IntelliSense\WCF` folder do not work for ASMX-based applications.</span></span> <span data-ttu-id="6ea3c-184">GenWCFProxyAssembly.cmd 脚本调用 SvcUtil.exe，生成的 WCF 服务的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-184">The GenWCFProxyAssembly.cmd script calls SvcUtil.exe, which generates source code files for the WCF services.</span></span> <span data-ttu-id="6ea3c-185">WCF 代理文件包含不同的属性、 通道接口以及每个 PSI 服务的客户端类。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-185">The WCF proxy files include different attributes, the channel interface, and a client class for each PSI service.</span></span> <span data-ttu-id="6ea3c-186">例如，基于 WCF 的资源服务包括**ResourceChannel**接口、**资源**接口和**ResourceClient**类。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-186">For example, the WCF-based Resource service includes the **ResourceChannel** interface, the **Resource** interface, and the **ResourceClient** class.</span></span> <span data-ttu-id="6ea3c-187">基于 ASMX 的资源 web 包括**资源**类，该类具有一些不同的属性。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-187">The ASMX-based Resource web includes the **Resource** class with some different properties.</span></span> 
  
<span data-ttu-id="6ea3c-188">以下是 GenASMXProxyAssembly.cmd 脚本，该脚本为 PSI Web 服务生成 WSDL 输出文件，然后编译程序集。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-188">Following is the GenASMXProxyAssembly.cmd script that generates WSDL output files for the PSI web services, and then compiles the assembly.</span></span>
  
```MS-DOS
@echo off
@ECHO ---------------------------------------------------
@ECHO Creating C# files for the ASMX-based proxy assembly
@ECHO ---------------------------------------------------
REM Replace ServerName with the name of the server and 
REM the instance name of Project Web App. Do not use localhost.
(set VDIR=http://ServerName/pwa/_vti_bin/psi)
(set OUTDIR=.\Source)
REM ** Wsdl.exe is the same version in the v6.0A and v7.0A subdirectories. 
(set WSDL="C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0A\Bin\x64\wsdl.exe")
if not exist %OUTDIR% (
md %OUTDIR%
)
for /F %%i in (Classlist_asmx.txt) do %WSDL% /nologo /l:CS /namespace:Svc%%i /out:%OUTDIR%\wsdl.%%i.cs %VDIR%/%%i.asmx?wsdl 
@ECHO ----------------------------
@ECHO Compiling the proxy assembly
@ECHO ----------------------------
(set SOURCE=%OUTDIR%\wsdl)
(set CSC=%WINDIR%\Microsoft.NET\Framework64\v4.0.30319\csc.exe)
(set ASSEMBLY_NAME=ProjectServerServices.dll)
%CSC% /t:library /out:%ASSEMBLY_NAME% %SOURCE%*.cs
```

<span data-ttu-id="6ea3c-189">该脚本使用 ClassList_asmx.txt 文件，此文件包含可供第三方开发人员使用的 Web 服务的列表。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-189">The script uses the ClassList_asmx.txt file, which contains the list of web services that are available for third-party developers.</span></span>
  
```text
Admin
Archive
Calendar
CubeAdmin
CustomFields
Driver
Events
LoginForms
LoginWindows
LookupTable
Notifications
ObjectLinkProvider
PortfolioAnalyses
Project
QueueSystem
ResourcePlan
Resource
Security
Statusing
TimeSheet
Workflow
WssInterop
```

<span data-ttu-id="6ea3c-p121">该脚本创建一个名为 ProjectServerServices.dll 的程序集。请避免将该程序集与基于 WCF 的程序集的 ProjectServerServices.dll 混淆。这两个程序集的名称相同，若要启用任一程序集，请将其与 ProjectServerServices.xml IntelliSense 文件一起使用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-p121">The scripts create an assembly named ProjectServerServices.dll. Avoid confusing it with ProjectServerServices.dll for the WCF-based assembly. The assembly names are the same, to enable using either assembly with the ProjectServerServices.xml IntelliSense file.</span></span>
  
<span data-ttu-id="6ea3c-193">创建用于 ASMX web 服务和 WCF 服务的脚本的任意命名空间是相同，以便 ProjectServerServices.xml IntelliSense 文件处理任一程序集。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-193">The arbitrary namespace created by the scripts for both the ASMX web services and the WCF services is the same, so that the ProjectServerServices.xml IntelliSense file works with either assembly.</span></span> <span data-ttu-id="6ea3c-194">例如，资源服务在基于 WCF 的代理程序集和基于 ASMX 的代理程序集的命名空间为**SvcResource**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-194">For example, the namespace of the Resource service in the WCF-based proxy assembly and in the ASMX-based proxy assembly is **SvcResource**.</span></span> <span data-ttu-id="6ea3c-195">当然，可以更改命名空间名称 — 如果您确保它们匹配代理程序集和 ProjectServerServices.xml IntelliSense 文件中。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-195">You can, of course, change the namespace names—if you ensure that they match in the proxy assembly and in the ProjectServerServices.xml IntelliSense file.</span></span>
  
<span data-ttu-id="6ea3c-196">如果代码示例使用不同的 PSI web 服务命名空间名称，例如**ProjectWebSvc**的 IntelliSense 以正常运行，则必须更改的示例使用**SvcProject**以便命名空间匹配代理程序集。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-196">If a code sample uses a different name for a PSI web service namespace, for example **ProjectWebSvc**, for IntelliSense to work you must change the sample to use **SvcProject** so that the namespace matches the proxy assembly.</span></span> 
  
<span data-ttu-id="6ea3c-197">使用基于 ASMX 的代理程序集的优点在于，它包含所有 PSI web 服务命名空间;不需要创建多个 web 引用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-197">An advantage to using the ASMX-based proxy assembly is that it includes all PSI web service namespaces; you do not have to create multiple web references.</span></span> <span data-ttu-id="6ea3c-198">另一个优点是，如果将 ProjectServerServices.xml 文件添加到您在其中设置对 ProjectServerServices.dll 代理程序集的引用相同的目录，您可以获取 IntelliSense 说明的 PSI 类和成员。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-198">Another advantage is that, if you add the ProjectServerServices.xml file to the same directory where you set a reference to the ProjectServerServices.dll proxy assembly, you can get IntelliSense descriptions for the PSI classes and members.</span></span> <span data-ttu-id="6ea3c-199">图 2 显示了**Project.QueueCreateProject**方法的 IntelliSense 文本。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-199">Figure 2 shows the IntelliSense text for the **Project.QueueCreateProject** method.</span></span> <span data-ttu-id="6ea3c-200">有关详细信息，请参阅 Project 2013 SDK 下载的 IntelliSense 文件夹中的 [ReadMe_IntelliSense] 文件。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-200">For more information, see the [ReadMe_IntelliSense] file in the IntelliSense folder of the Project 2013 SDK download.</span></span> 
  
<span data-ttu-id="6ea3c-201">**图 2。在 Project web 服务方法使用 IntelliSense**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-201">**Figure 2. Using IntelliSense for a method in the Project web service**</span></span>

<span data-ttu-id="6ea3c-202">![PSI 服务中的方法使用 Intellisense](media/pj15_PrerequisitesASMX_Intellisense.gif "PSI 服务中的方法使用 Intellisense")</span><span class="sxs-lookup"><span data-stu-id="6ea3c-202">![Using Intellisense for a method in a PSI service](media/pj15_PrerequisitesASMX_Intellisense.gif "Using Intellisense for a method in a PSI service")</span></span>
  
<span data-ttu-id="6ea3c-p124">使用代理程序集的缺点是，解决方案更大并且您必须使用解决方案来分发和安装代理程序集。除非您将脚本和 ProjectServerServices.xml IntelliSense 文件更改为使用其他命名空间，否则还必须使用代理程序集和 IntelliSense 文件中的相同命名空间。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-p124">Disadvantages to using the proxy assembly are that the solution is larger and you must distribute and install the proxy assembly with the solution. You must also use the same namespaces that are in the proxy assembly and IntelliSense files, unless you change the script and ProjectServerServices.xml IntelliSense file to use different namespaces.</span></span>
  
### <a name="adding-a-psi-proxy-file"></a><span data-ttu-id="6ea3c-205">添加 PSI 代理文件</span><span class="sxs-lookup"><span data-stu-id="6ea3c-205">Adding a PSI proxy file</span></span>
<span data-ttu-id="6ea3c-206"><a name="pj15_PrerequisitesASMX_AddingProxyFile"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-206"></span></span>

<span data-ttu-id="6ea3c-207">Project 2013 SDK 下载包括 Wsdl.exe 命令生成的代理程序集的源文件。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-207">The Project 2013 SDK download includes the source files generated by the Wsdl.exe command for the proxy assembly.</span></span> <span data-ttu-id="6ea3c-208">源文件位于中 Source.zip`Documentation\IntelliSense\ASMX`子目录。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-208">The source files are in Source.zip in the  `Documentation\IntelliSense\ASMX` subdirectory.</span></span> <span data-ttu-id="6ea3c-209">而不是设置代理程序集的引用，可以将一个或多个的源文件添加到 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-209">Instead of setting a reference to the proxy assembly, you can add one or more of the source files to a Visual Studio solution.</span></span> <span data-ttu-id="6ea3c-210">例如，运行 GenASMXProxyAssembly.cmd 脚本后，添加 wsdl。向解决方案 Project.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-210">For example, after running the GenASMXProxyAssembly.cmd script, add the wsdl.Project.cs file to the solution.</span></span> <span data-ttu-id="6ea3c-211">而不是运行该脚本，您可以运行以下命令以生成单个源文件，例如：</span><span class="sxs-lookup"><span data-stu-id="6ea3c-211">Instead of running the script, you can run the following commands to generate a single source file, for example:</span></span> 
  
```MS-DOS
set VDIR=http://ServerName/ProjectServerName/_vti_bin/psi
set WSDL="C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0A\Bin\x64\wsdl.exe"
%WSDL% /nologo /l:cs /namespace:SvcProject /out:wsdl.Project.cs %VDIR%/Project.asmx?wsdl
```

<span data-ttu-id="6ea3c-212">若要将一个**Project**对象定义为名为**项目**的类变量中，使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-212">To define a **Project** object as a class variable named **project**, use the following code.</span></span> <span data-ttu-id="6ea3c-213">**AddContextInfo**方法添加到 Windows 身份验证和基于表单的身份验证的**项目**对象的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-213">The **AddContextInfo** method adds the context information to the **project** object for Windows authentication and Forms-based authentication.</span></span> 
  
```cs
private static SvcProject.Project project;
private static SvcLoginForms.LoginForms loginForms =
            new SvcLoginForms.LoginForms();
. . .
public void AddContextInfo()
{
    // Add the Url property.
    project.Url = "http://ServerName /ProjectServerName /_vti_bin/psi/project.asmx";
    // Add Windows credentials.
    project.Credentials = CredentialCache.DefaultCredentials;
    // If Forms authentication is used, add the Project Server cookie.
    project.CookieContainer = loginForms.CookieContainer;
}
```

> [!NOTE]
> <span data-ttu-id="6ea3c-214">无论是使用 PSI 代理程序集还是添加名为**SvcProject**的 Project 服务引用代理文件，将使用相同的代码创建一个**project**对象。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-214">Whether you use a PSI proxy assembly or add a proxy file for a Project service reference named **SvcProject**, you would use the same code to create a **project** object.</span></span> 
  
### <a name="adding-a-web-service-reference"></a><span data-ttu-id="6ea3c-215">添加 Web 服务引用</span><span class="sxs-lookup"><span data-stu-id="6ea3c-215">Adding a web service reference</span></span>
<span data-ttu-id="6ea3c-216"><a name="pj15_PrerequisitesASMX_AddingServiceReference"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-216"></span></span>

<span data-ttu-id="6ea3c-217">如果您不使用基于 ASMX 的代理程序集或添加 WSDL 输出文件，您可以设置一个或多个单独的 web 引用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-217">If you do not use the ASMX-based proxy assembly or add a WSDL output file, you can set one or more individual web references.</span></span> <span data-ttu-id="6ea3c-218">以下步骤演示如何使用 Visual Studio 2012 设置 web 引用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-218">The following steps show how to set a web reference by using Visual Studio 2012.</span></span>
  
1. <span data-ttu-id="6ea3c-219">在**解决方案资源管理器**中，右键单击**引用**文件夹，然后选择**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-219">In **Solution Explorer**, right-click the **References** folder, and then choose **Add Service Reference**.</span></span> 
    
2. <span data-ttu-id="6ea3c-220">在**添加服务引用**对话框中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-220">In the **Add Service Reference** dialog box, choose **Advanced**.</span></span>
    
3. <span data-ttu-id="6ea3c-221">在**服务引用设置**对话框中，选择**添加 Web 引用**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-221">In the **Service Reference Settings** dialog box, choose **Add Web Reference**.</span></span>
    
4. <span data-ttu-id="6ea3c-222">在**URL**文本框中，键入`http:// _ServerName_/ _ProjectServerName_/_vti_bin/psi/ _ServiceName_.asmx?wsdl`，然后按**Enter**或选择**转**图标。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-222">In the **URL** text box, type `http:// _ServerName_/ _ProjectServerName_/_vti_bin/psi/ _ServiceName_.asmx?wsdl`, and then press **Enter** or choose the **Go** icon.</span></span> <span data-ttu-id="6ea3c-223">如果您有安装安全套接字层 (SSL)，您应使用 HTTPS 协议而不是 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-223">If you have Secure Sockets Layer (SSL) installed, you should use the HTTPS protocol instead of the HTTP protocol.</span></span> 

   <span data-ttu-id="6ea3c-224">例如上的 Project 服务使用以下 URL `http://MyServer/pwa` Project Web app 网站：`http://MyServer/pwa/_vti_bin/psi/project.asmx?wsdl`</span><span class="sxs-lookup"><span data-stu-id="6ea3c-224">For example, use the following URL for the Project service on the  `http://MyServer/pwa` site for Project Web App: `http://MyServer/pwa/_vti_bin/psi/project.asmx?wsdl`</span></span>
    
   <span data-ttu-id="6ea3c-225">或者，打开 web 浏览器中，并导航到`http://ServerName/ProjectServerName/_vti_bin/psi/ServiceName.asmx?wsdl`。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-225">Or, open your web browser, and navigate to `http://ServerName/ProjectServerName/_vti_bin/psi/ServiceName.asmx?wsdl`.</span></span> <span data-ttu-id="6ea3c-226">将文件保存到本地目录，如`C:\Project\WebServices\ServiceName.wsdl`。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-226">Save the file to a local directory, such as `C:\Project\WebServices\ServiceName.wsdl`.</span></span> <span data-ttu-id="6ea3c-227">在**添加 Web 引用**对话框的**URL**，键入文件协议和文件的路径。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-227">In the **Add Web Reference** dialog box, for **URL**, type the file protocol and the path to the file.</span></span> <span data-ttu-id="6ea3c-228">例如，键入`file://C:\Project\WebServices\Project.wsdl`。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-228">For example, type `file://C:\Project\WebServices\Project.wsdl`.</span></span> 
    
5. <span data-ttu-id="6ea3c-229">解析引用后，请在**Web 引用名称**文本框中键入引用名称。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-229">After the reference resolves, type the reference name in the **Web reference name** text box.</span></span> <span data-ttu-id="6ea3c-230">Project 2013 开发人员文档中的代码示例使用任意标准引用名称_Svc **ServiceName**_。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-230">Code examples in the Project 2013 developer documentation use the arbitrary standard reference name **Svc _ServiceName_**.</span></span> <span data-ttu-id="6ea3c-231">例如，Project web 服务名为**SvcProject** （参见图 3）。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-231">For example, the Project web service is named **SvcProject** (see Figure 3).</span></span> 
    
   <span data-ttu-id="6ea3c-232">**图 3。添加 ASMX web 服务引用**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-232">**Figure 3. Adding an ASMX web service reference**</span></span>

   <span data-ttu-id="6ea3c-233">![添加 ASMX web 服务引用](media/pj15_PrerequisitesASMX_AddWebSvcReference.gif "添加 ASMX web 服务引用")</span><span class="sxs-lookup"><span data-stu-id="6ea3c-233">![Adding an ASMX web service reference](media/pj15_PrerequisitesASMX_AddWebSvcReference.gif "Adding an ASMX web service reference")</span></span>
  
<span data-ttu-id="6ea3c-234">对于必须在 Project Server 计算机运行的应用程序组件，使用模拟，或使用提升的权限，而不是 ASMX web 引用使用 WCF 服务引用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-234">For application components that must run on the Project Server computer, use impersonation, or have elevated permissions, use a WCF service reference instead of an ASMX web reference.</span></span> <span data-ttu-id="6ea3c-235">有关详细信息，请参阅[项目中的基于 WCF 的代码示例的先决条件](prerequisites-for-wcf-based-code-samples-in-project.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-235">For more information, see [Prerequisites for WCF-based code samples in Project](prerequisites-for-wcf-based-code-samples-in-project.md).</span></span>
  
## <a name="setting-other-references"></a><span data-ttu-id="6ea3c-236">设置其他引用</span><span class="sxs-lookup"><span data-stu-id="6ea3c-236">Setting other references</span></span>
<span data-ttu-id="6ea3c-237"><a name="pj15_PrerequisitesASMX_OtherReferences"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-237"></span></span>

<span data-ttu-id="6ea3c-238">Project Server 应用程序通常使用其他服务，例如 SharePoint Server 2013 web 服务。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-238">Project Server applications often use other services, such as SharePoint Server 2013 web services.</span></span> <span data-ttu-id="6ea3c-239">如果需要其他服务，它们是该示例中记下。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-239">If other services are required, they are noted in the example.</span></span>
  
<span data-ttu-id="6ea3c-240">代码示例的本地引用列出在示例顶部的**using**语句：</span><span class="sxs-lookup"><span data-stu-id="6ea3c-240">Local references for the code sample are listed in **using** statements at the top of the sample:</span></span> 
  
1. <span data-ttu-id="6ea3c-241">在**解决方案资源管理器**中，右键单击**引用**文件夹，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-241">In **Solution Explorer**, right-click the **References** folder, and then choose **Add Reference**.</span></span>
    
2. <span data-ttu-id="6ea3c-242">选择**浏览**，，然后浏览到您先前复制 Project Server Dll 存储的位置。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-242">Choose **Browse**, and then browse to the location where you stored the Project Server DLLs that you copied previously.</span></span> <span data-ttu-id="6ea3c-243">选择 Dll 您需要，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-243">Choose the DLLs you need, and then choose **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6ea3c-244">确保您的开发计算机上的程序集版本与目标 Project Server 计算机上的程序集版本完全匹配。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-244">Ensure that the assembly versions on your development computer exactly match those on the target Project Server computer.</span></span> 
  
## <a name="using-multiple-authentication"></a><span data-ttu-id="6ea3c-245">使用多身份验证</span><span class="sxs-lookup"><span data-stu-id="6ea3c-245">Using multiple authentication</span></span>
<span data-ttu-id="6ea3c-246"><a name="pj15_PrerequisitesASMX_ClaimsMultiAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-246"></span></span>

<span data-ttu-id="6ea3c-247">通过 Windows 身份验证或表单身份验证内部部署 Project Server 用户进行身份验证是通过 SharePoint Server 2013 中处理的声明。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-247">Authentication of on-premises Project Server users, whether by Windows authentication or Forms authentication, is done through claims processing in SharePoint Server 2013.</span></span> <span data-ttu-id="6ea3c-248">多个身份验证是指在其设置 Project Web App 的 web 应用程序支持 Windows 身份验证和基于表单的身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-248">Multiple authentication means that the web application on which Project Web App is provisioned supports both Windows authentication and Forms-based authentication.</span></span> <span data-ttu-id="6ea3c-249">如果是这样，使用 Windows 身份验证的 ASMX web 服务调用将失败并出现以下错误，因为声明过程无法确定哪种类型的用户进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="6ea3c-249">If that is the case, a call to an ASMX web service that uses Windows authentication will fail with the following error, because the claims process cannot determine which type of user to authenticate:</span></span>
  
`The server was unable to process the request due to an internal error. . . .`

<span data-ttu-id="6ea3c-250">为 ASMX 解决问题，PSI 方法的所有呼叫都应为派生类定义的每个 PSI web 服务。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-250">To fix the problem for ASMX, all calls to PSI methods should be to a derived class that is defined for each PSI web service.</span></span> <span data-ttu-id="6ea3c-251">派生的类还必须使用**SvcLoginWindows.LoginWindows**类获取派生的 PSI 服务类的 cookie。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-251">The derived class must also use the **SvcLoginWindows.LoginWindows** class to get a cookie for the derived PSI service class.</span></span> <span data-ttu-id="6ea3c-252">在以下示例中， **ProjectDerived**类派生自**SvcProject.Project**类。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-252">In the following example, the **ProjectDerived** class derives from the **SvcProject.Project** class.</span></span> <span data-ttu-id="6ea3c-253">派生的类添加**EnforceWindowsAuth**属性和替代 web 请求标头的每个呼叫中的**项目**类的方法。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-253">The derived class adds the **EnforceWindowsAuth** property and overrides the web request header for every call to a method in the **Project** class.</span></span> <span data-ttu-id="6ea3c-254">如果**EnforceWindowsAuth**属性为**true**，则**GetWebRequest**方法添加禁用表单的身份验证的标头。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-254">If the **EnforceWindowsAuth** property is **true**, the **GetWebRequest** method adds a header that disables Forms authentication.</span></span> <span data-ttu-id="6ea3c-255">如果**EnforceWindowsAuth**为**false**，可以继续进行表单身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-255">If **EnforceWindowsAuth** is **false**, Forms authentication can proceed.</span></span>
  
<span data-ttu-id="6ea3c-256">若要使用下面的**ASMXLogon_MultiAuth**示例，创建一个控制台应用程序，[创建应用程序并添加 web 服务引用](#pj15_PrerequisitesASMX_Configure)，请按照，然后添加 wsdl。LoginWindows.cs 代理文件和 wsdl。Project.cs 代理文件。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-256">To use the following **ASMXLogon_MultiAuth** sample, create a console application, follow the steps in [Creating the application and adding a web service reference](#pj15_PrerequisitesASMX_Configure), and then add the wsdl.LoginWindows.cs proxy file and the wsdl.Project.cs proxy file.</span></span> <span data-ttu-id="6ea3c-257">**在 Main**方法创建**ProjectDerived**类的**项目**实例。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-257">The **Main** method creates the **project** instance of the **ProjectDerived** class.</span></span> <span data-ttu-id="6ea3c-258">该示例必须使用派生的**LoginWindowsDerived**类获取**项目**CookieContainer**对象。CookieContainer**属性，用于区分表单身份验证从 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-258">The sample must use the derived **LoginWindowsDerived** class to get a **CookieContainer** object for the **project.CookieContainer** property, which distinguishes Forms authentication from Windows authentication.</span></span> <span data-ttu-id="6ea3c-259">然后可以使用**project**对象**SvcProject.Project**类中进行任何方法的调用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-259">The **project** object can then be used to make calls to any method in the **SvcProject.Project** class.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6ea3c-260">**LoginWindows**服务，则需要仅用于 ASMX 应用程序中的多个身份验证环境。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-260">The **LoginWindows** service is required only for ASMX applications in a multiple authentication environment.</span></span> <span data-ttu-id="6ea3c-261">在**ASMXLogon_MultiAuth**示例中， **GetLogonCookie**方法获取**loginWindows**对象的 cookie。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-261">In the **ASMXLogon_MultiAuth** sample, the **GetLogonCookie** method gets a cookie for the **loginWindows** object.</span></span> <span data-ttu-id="6ea3c-262">**项目中。CookieContainer**属性设置为**loginWindows.CookieContainer**值。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-262">The **project.CookieContainer** property is set to the **loginWindows.CookieContainer** value.</span></span> 
  
```cs
using System;
using System.Net;
using PSLibrary = Microsoft.Office.Project.Server.Library;
namespace ASMXLogon_MultiAuth
{
    class Program
    {
        private const string PROJECT_SERVER_URL = 
            "http://ServerName/ProjectServerName/_vti_bin/psi/";
        static void Main(string[] args)
        {
            bool isWindowsUser = true;
            // Create an instance of the project object.
            ProjectDerived project = new ProjectDerived();
            project.Url = PROJECT_SERVER_URL + "Project.asmx";
            project.Credentials = CredentialCache.DefaultCredentials;
            try
            {
                // The program works on a Windows-auth-only computer if you comment-out the
                // following line. The line is required for multiple authentication.
                project.CookieContainer = GetLogonCookie();
                project.EnforceWindowsAuth = isWindowsUser;
                // Get a list of all published projects. 
                // Use ReadProjectStatus instead of ReadProjectList,
                // because the permission requirements are lower.
                SvcProject.ProjectDataSet projectDs =
                    project.ReadProjectStatus(Guid.Empty,
                        SvcProject.DataStoreEnum.PublishedStore,
                        string.Empty,
                        (int)PSLibrary.Project.ProjectType.Project);
                Console.WriteLine(string.Format(
                    "There are {0} published projects.", 
                    projectDs.Project.Rows.Count));
            }
            catch (UnauthorizedAccessException ex)
            {
                Console.WriteLine(ex.Message);
            }
            catch (WebException ex)
            {
                Console.WriteLine(ex.Message);
            }
            finally
            {
                Console.Write("Press any key to continue...");
                Console.ReadKey(false);
            }
        }
        private static CookieContainer GetLogonCookie()
        {
            // Create an instance of the loginWindows object.
            LoginWindowsDerived loginWindows = new LoginWindowsDerived();
            loginWindows.EnforceWindowsAuth = true;
            loginWindows.Url = PROJECT_SERVER_URL + "LoginWindows.asmx";
            loginWindows.Credentials = CredentialCache.DefaultCredentials;
            loginWindows.CookieContainer = new CookieContainer();
            if (!loginWindows.Login())
            {
                // Login failed; throw an exception.
                throw new UnauthorizedAccessException("Login failed.");
            }
            return loginWindows.CookieContainer;
        }
    }
    // Derive from LoginWindows class; include additional property and 
    // override the web request header.
    class LoginWindowsDerived : SvcLoginWindows.LoginWindows
    {
        public bool EnforceWindowsAuth { get; set; }
        protected override WebRequest GetWebRequest(Uri uri)
        {
            WebRequest request = base.GetWebRequest(uri);
            if (this.EnforceWindowsAuth)
            {
                request.Headers.Add("X-FORMS_BASED_AUTH_ACCEPTED", "f");
            }
            return request;
        }
    }
    // Derive from Project class; include additional property and 
    // override the web request header.
    class ProjectDerived : SvcProject.Project
    {
        public bool EnforceWindowsAuth { get; set; }
        protected override WebRequest GetWebRequest(Uri uri)
        {
            WebRequest request = base.GetWebRequest(uri);
            if (this.EnforceWindowsAuth)
            {
                request.Headers.Add("X-FORMS_BASED_AUTH_ACCEPTED", "f");
            }
            return request;
        }
    }
}
```

<span data-ttu-id="6ea3c-263">在多个身份验证环境中运行的应用程序需要使用派生的**LoginWindows**类，并禁用表单身份验证 web 请求标头的 PSI 调用。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-263">Using the derived **LoginWindows** class, and making PSI calls with a web request header that disables Forms authentication, is required for applications that run in a multiple authentication environment.</span></span> <span data-ttu-id="6ea3c-264">如果 Project Server 使用仅声明身份验证，则没有必要派生类中添加 web 请求标头。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-264">If Project Server uses only claims authentication, it is not necessary to derive a class that adds a web request header.</span></span> <span data-ttu-id="6ea3c-265">在这两种环境中运行上面的示例。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-265">The previous example runs in both environments.</span></span> 
  
<span data-ttu-id="6ea3c-266">基于 WCF 的应用程序的解决方法是不同。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-266">The fix for a WCF-based application is different.</span></span> <span data-ttu-id="6ea3c-267">有关详细信息，请参阅[项目中的基于 WCF 的代码示例的先决条件](prerequisites-for-wcf-based-code-samples-in-project.md)中的*使用多个身份验证*部分。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-267">For more information, see the  *Using multiple authentication*  section in [Prerequisites for WCF-based code samples in Project](prerequisites-for-wcf-based-code-samples-in-project.md).</span></span>
  
## <a name="changing-the-values-of-generic-constants"></a><span data-ttu-id="6ea3c-268">更改泛型常量的值</span><span class="sxs-lookup"><span data-stu-id="6ea3c-268">Changing the values of generic constants</span></span>
<span data-ttu-id="6ea3c-269"><a name="pj15_PrerequisitesASMX_ChangeValues"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-269"></span></span>

<span data-ttu-id="6ea3c-270">大多数示例具有一个或多个必须更新示例以正确环境中的变量。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-270">Most samples have one or more variables that you must update for the sample to work properly in your environment.</span></span> <span data-ttu-id="6ea3c-271">在以下示例中，情况下，如果您有 SSL 安装，使用 HTTPS 协议而不是 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-271">In the following example, if you have SSL installed, use the HTTPS protocol instead of the HTTP protocol.</span></span> <span data-ttu-id="6ea3c-272">_ServerName_替换为您使用的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-272">Replace  _ServerName_ with the name of the server that you are using.</span></span> <span data-ttu-id="6ea3c-273">_ProjectServerName_替换为您的 Project Server 网站，如 PWA 的虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-273">Replace  _ProjectServerName_ with the virtual directory name of your Project Server site, such as PWA.</span></span> 
  
```cs
const string PROJECT_SERVER_URI = "http://ServerName/ProjectServerName/";
```

<span data-ttu-id="6ea3c-274">您必须更改的所有其他变量或其他先决条件均已在代码示例的顶部注明。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-274">Any other variables that you must change or other prerequisites are noted at the top of the code example.</span></span>
  
## <a name="verifying-the-results"></a><span data-ttu-id="6ea3c-275">验证结果</span><span class="sxs-lookup"><span data-stu-id="6ea3c-275">Verifying the results</span></span>
<span data-ttu-id="6ea3c-276"><a name="pj15_PrerequisitesASMX_Verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-276"></span></span>

<span data-ttu-id="6ea3c-277">获取和解释结果的代码示例并不总是变得非常简单。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-277">Getting and interpreting results from a code sample is not always straightforward.</span></span> <span data-ttu-id="6ea3c-278">例如，如果您创建的项目时，才可以显示在 Project Web App 中的项目中心页上必须发布项目。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-278">For example, if you create a project, you must publish the project before it can appear on the Project Center page in Project Web App.</span></span>
  
<span data-ttu-id="6ea3c-279">可以通过多种方式验证代码示例结果，例如：</span><span class="sxs-lookup"><span data-stu-id="6ea3c-279">You can verify code sample results in several ways, for example:</span></span>
  
- <span data-ttu-id="6ea3c-280">使用 Project Professional 2013 客户端从 Project Server 计算机中，打开项目并查看所需的项。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-280">Use the Project Professional 2013 client to open the project from the Project Server computer, and view the items that you want.</span></span>
    
- <span data-ttu-id="6ea3c-281">在 Project Web App 的项目中心页上查看已发布的项目 ( `http://ServerName/ProjectServerName/projects.aspx`)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-281">View published projects on the Project Center page of Project Web App ( `http://ServerName/ProjectServerName/projects.aspx`).</span></span>
    
- <span data-ttu-id="6ea3c-282">在 Project Web App 中查看队列日志。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-282">View the Queue log in Project Web App.</span></span> <span data-ttu-id="6ea3c-283">打开服务器设置页 （右上角选择**设置**图标），然后选择下**个人设置**部分**我的排队作业**( `http://ServerName/ProjectServerName/MyJobs.aspx`)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-283">Open the Server Settings page (choose the **Settings** icon in the top-right corner), and then choose **My Queued Jobs** under the **Personal Settings** section (  `http://ServerName/ProjectServerName/MyJobs.aspx`).</span></span> <span data-ttu-id="6ea3c-284">在**视图**下拉列表中，您可以按作业状态排序。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-284">In the **View** drop-down list, you can sort by the job status.</span></span> <span data-ttu-id="6ea3c-285">**正在进行和过去一周的失败作业**的默认状态。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-285">The default status is **In Progress and Failed Jobs in the Past Week**.</span></span> 
    
- <span data-ttu-id="6ea3c-286">使用 Project Web App 中的服务器设置页 ( `http://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`) 来管理所有队列作业和删除或强制签入企业对象。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-286">Use the Server Settings page in Project Web App ( `http://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`) to manage all queue jobs and delete or force check-in enterprise objects.</span></span> <span data-ttu-id="6ea3c-287">您必须具有管理权限才能访问这些服务器设置页上的链接。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-287">You must have administrative permissions to access those links on the Server Settings page.</span></span>
    
- <span data-ttu-id="6ea3c-288">使用**Microsoft SQL Server Management Studio**中的表中的项目数据库上运行查询。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-288">Use **Microsoft SQL Server Management Studio** to run a query on a table in the Project database.</span></span> <span data-ttu-id="6ea3c-289">例如，使用下面的查询选择 pub 前的 200 行。MSP_WORKFLOW_STAGE_PDPS 表以显示项目信息的详细信息页面 (Pdp) 中的工作流阶段。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-289">For example, use the following query to select the top 200 rows of the pub.MSP_WORKFLOW_STAGE_PDPS table to show information about the project detail pages (PDPs) in workflow stages.</span></span> 
    
   ```sql
    SELECT TOP 200 [STAGE_UID]
            ,[PDP_UID]
            ,[PDP_NAME]
            ,[PDP_POSITION]
            ,[PDP_ID]
            ,[PDP_STAGE_DESCRIPTION]
            ,[PDP_REQUIRES_ATTENTION]
        FROM [ProjectService].[pub].[MSP_WORKFLOW_STAGE_PDPS]
   ```

## <a name="cleaning-up"></a><span data-ttu-id="6ea3c-290">清理</span><span class="sxs-lookup"><span data-stu-id="6ea3c-290">Cleaning up</span></span>
<span data-ttu-id="6ea3c-291"><a name="pj15_PrerequisitesASMX_Cleanup"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-291"></span></span>

<span data-ttu-id="6ea3c-292">测试某些代码示例后，没有企业对象和设置应删除或重置。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-292">After you test some code samples, there are enterprise objects and settings that should be deleted or reset.</span></span> <span data-ttu-id="6ea3c-293">可以使用 Project Web App 中的服务器设置页来管理企业数据 ( `http://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`)。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-293">You can use the Server Settings page in Project Web App to manage enterprise data ( `http://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`).</span></span> <span data-ttu-id="6ea3c-294">在服务器设置页上的链接，可以删除旧项目、 强制签入项目、 管理作业队列的所有用户和执行其他管理任务。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-294">Links on the Server Settings page enable you to delete old items, force check-in projects, manage the job queue for all users, and perform other administrative tasks.</span></span>
  
<span data-ttu-id="6ea3c-295">以下是“服务器设置”页上的一些链接，可在运行完代码示例后使用这些链接进行典型的清理活动：</span><span class="sxs-lookup"><span data-stu-id="6ea3c-295">Following are some of the links on the Server Settings page that you can use for typical cleanup activities after running code samples:</span></span>
  
- <span data-ttu-id="6ea3c-296">**企业自定义域和查阅表格**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-296">**Enterprise Custom Fields and Lookup Tables**</span></span>
    
- <span data-ttu-id="6ea3c-297">**管理队列作业**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-297">**Manage Queue Jobs**</span></span>
    
- <span data-ttu-id="6ea3c-298">**删除企业对象**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-298">**Delete Enterprise Objects**</span></span>
    
- <span data-ttu-id="6ea3c-299">**强制签入企业对象**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-299">**Force Check-in Enterprise Objects**</span></span>
    
- <span data-ttu-id="6ea3c-300">**企业项目类型**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-300">**Enterprise Project Types**</span></span>
    
- <span data-ttu-id="6ea3c-301">**工作流阶段**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-301">**Workflow Phases**</span></span>
    
- <span data-ttu-id="6ea3c-302">**工作流阶段**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-302">**Workflow Stages**</span></span>
    
- <span data-ttu-id="6ea3c-303">**项目详细信息页面**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-303">**Project Detail Pages**</span></span>
    
- <span data-ttu-id="6ea3c-304">**时间报告阶段**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-304">**Time Reporting Periods**</span></span>
    
- <span data-ttu-id="6ea3c-305">**时间表设置值和默认值**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-305">**Timesheet Settings and Defaults**</span></span>
    
- <span data-ttu-id="6ea3c-306">**行分类**</span><span class="sxs-lookup"><span data-stu-id="6ea3c-306">**Line Classifications**</span></span>
    
<span data-ttu-id="6ea3c-307">通过 SharePoint Server 2013 的每个 Project Web App 实例，而不是按特定的 Project Web App 服务器设置页管理其他设置。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-307">Additional settings are managed by SharePoint Server 2013 for each Project Web App instance, rather than by a specific Project Web App Server Settings page.</span></span> <span data-ttu-id="6ea3c-308">在 SharePoint 管理中心应用程序中，选择**应用程序的常规设置**，选择**管理** **Project Server 设置**下，然后选择服务器设置页上的下拉列表中的 Project Web App 实例.</span><span class="sxs-lookup"><span data-stu-id="6ea3c-308">In the SharePoint Central Administration application, choose **General Application Settings**, choose **Manage** under **Project Server Settings**, and then choose the Project Web App instance in the drop-down list on the Server Settings page.</span></span> <span data-ttu-id="6ea3c-309">例如，选择**服务器端事件处理程序**添加或删除所选的 Project Web App 实例的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ea3c-309">For example, choose **Server Side Event Handlers** to add or delete event handlers for the selected Project Web App instance.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6ea3c-310">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea3c-310">See also</span></span>
<span data-ttu-id="6ea3c-311"><a name="pj15_PrerequisitesASMX_AR"> </a></span><span class="sxs-lookup"><span data-stu-id="6ea3c-311"></span></span>

- [<span data-ttu-id="6ea3c-312">在项目中的基于 WCF 的代码示例的先决条件</span><span class="sxs-lookup"><span data-stu-id="6ea3c-312">Prerequisites for WCF-based code samples in Project</span></span>](prerequisites-for-wcf-based-code-samples-in-project.md)
- [<span data-ttu-id="6ea3c-313">使用 WCF 模拟</span><span class="sxs-lookup"><span data-stu-id="6ea3c-313">Use Impersonation with WCF</span></span>](http://msdn.microsoft.com/library/e3597901-2f02-44a2-8076-d32aae540b38%28Office.15%29.aspx)
- [<span data-ttu-id="6ea3c-314">项目 PSI 参考概述</span><span class="sxs-lookup"><span data-stu-id="6ea3c-314">Project PSI reference overview</span></span>](project-psi-reference-overview.md)
- [<span data-ttu-id="6ea3c-315">SharePoint 开发中心</span><span class="sxs-lookup"><span data-stu-id="6ea3c-315">SharePoint Developer Center</span></span>](http://msdn.microsoft.com/en-us/sharepoint/default.aspx)
    

