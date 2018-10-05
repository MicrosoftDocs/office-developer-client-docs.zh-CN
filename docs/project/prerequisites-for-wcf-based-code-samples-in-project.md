---
title: 在项目中的基于 WCF 的代码示例的先决条件
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 60d2afc8-10b6-465d-8ce8-c073da6e5054
description: 了解可帮助您使用 Project Server 接口 (PSI) 参考主题中包含的基于 WCF 的代码示例在 Visual Studio 中创建项目的信息。
ms.openlocfilehash: 2222e1b3651044c41f45e57481f80093aac67bdb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383378"
---
# <a name="prerequisites-for-wcf-based-code-samples-in-project"></a><span data-ttu-id="e0ee1-103">在项目中的基于 WCF 的代码示例的先决条件</span><span class="sxs-lookup"><span data-stu-id="e0ee1-103">Prerequisites for WCF-based code samples in Project</span></span>

<span data-ttu-id="e0ee1-104">了解可帮助您使用 Project Server 接口 (PSI) 参考主题中包含的基于 WCF 的代码示例在 Visual Studio 中创建项目的信息。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-104">Learn information to help you create projects in Visual Studio by using the WCF-based code samples that are included in the Project Server Interface (PSI) reference topics.</span></span>
   
<span data-ttu-id="e0ee1-105">[Project Server 2013 类类库和 web 服务引用](https://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)中包含的基于 WCF 的代码示例的许多原来创建的 Project 2010 开发人员文档，并标准格式用于 WCF web 服务。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-105">Many of the WCF-based code samples included in the [Project Server 2013 class library and web service reference](https://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx) were originally created for the Project 2010 developer documentation, and use a standard format for WCF web services.</span></span> <span data-ttu-id="e0ee1-106">示例仍在 Project Server 2013 中工作，旨在复制到控制台应用程序和运行完整的单位。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-106">The samples still work in Project Server 2013 and are designed to be copied into a console application and run as a complete unit.</span></span> <span data-ttu-id="e0ee1-107">例外示例中进行说明。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-107">Exceptions are noted in the sample.</span></span> 
  
<span data-ttu-id="e0ee1-108">Project 2013 开发人员文档中保持不变从为 Office Project Server 2007 开发的示例的代码示例使用 ASMX Web 服务。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-108">Code samples in the Project 2013 developer documentation that are unchanged from the samples developed for Office Project Server 2007 use ASMX Web services.</span></span> <span data-ttu-id="e0ee1-109">也可以修改用于 WCF 服务的基于 ASMX 的示例。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-109">The ASMX-based samples can also be adapted to use WCF services.</span></span> <span data-ttu-id="e0ee1-110">本文介绍如何使用 WCF 服务示例。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-110">This article shows how to use the samples with WCF services.</span></span> <span data-ttu-id="e0ee1-111">有关如何使用示例的 ASMX web 服务的信息，请参阅[项目中的基于 ASMX 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-111">For information about how to use the samples with ASMX web services, see [Prerequisites for ASMX-based code samples in Project](prerequisites-for-asmx-based-code-samples-in-project.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e0ee1-112">如果客户端对象模型 (CSOM) 包括您的应用程序需要的方法，则应使用 CSOM 开发新应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-112">If the client-side object model (CSOM) includes the methods that your application requires, new applications should be developed with the CSOM.</span></span> <span data-ttu-id="e0ee1-113">CSOM 使应用程序与 Project Online 或 Project Server 2013 的本地安装一起使用。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-113">The CSOM enables applications to work with Project Online or an on-premises installation of Project Server 2013.</span></span> <span data-ttu-id="e0ee1-114">否则，如果您的应用程序使用 PSI，它应使用 WCF 接口，这是建议的网络通信的技术。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-114">Otherwise, if your application uses the PSI, it should use the WCF interface, which is the technology that we recommend for network communications.</span></span> <span data-ttu-id="e0ee1-115">使用 ASMX 接口或 WCF 接口的应用程序可以处理仅用于 Project Server 2013 的本地安装。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-115">Applications that use the ASMX interface or the WCF interface can work only for on-premises installations of Project Server 2013.</span></span> 
>
> <span data-ttu-id="e0ee1-116">有关 CSOM 的详细信息，请参阅[Project Server 2013 体系结构](project-server-2013-architecture.md)和[客户端对象模型 (CSOM) for Project 2013](client-side-object-model-csom-for-project-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-116">For more information about the CSOM, see [Project Server 2013 architecture](project-server-2013-architecture.md) and [Client-side object model (CSOM) for Project 2013](client-side-object-model-csom-for-project-2013.md).</span></span> 
  
<span data-ttu-id="e0ee1-117">在运行代码示例之前，您必须设置开发环境、配置应用程序、添加服务配置文件（或以编程方式配置 WCF 服务）并更改泛型常量值以与您的环境匹配。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-117">Before running the code samples, you must set up the development environment, configure the application, add a service configuration file (or configure the WCF services programmatically), and change generic constant values to match your environment.</span></span>
  
## <a name="setting-up-the-development-environment"></a><span data-ttu-id="e0ee1-118">设置开发环境</span><span class="sxs-lookup"><span data-stu-id="e0ee1-118">Setting up the development environment</span></span>
<span data-ttu-id="e0ee1-119"><a name="pj15_PrerequisitesWCF_Setup"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-119"></span></span>

1. <span data-ttu-id="e0ee1-120">**设置测试 Project Server 系统。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-120">**Set up a test Project Server system.**</span></span>
    
    <span data-ttu-id="e0ee1-p104">在进行开发或测试时，请使用测试 Project Server 系统。即使您的代码正常运行，项目间的相关性、报告或其他环境因素也会导致意想不到的结果。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p104">Use a test Project Server system whenever you are developing or testing. Even when your code works perfectly, interproject dependencies, reporting, or other environmental factors can cause unintended consequences.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e0ee1-123">确保您是有效的用户的服务器上，并确认您具有足够的权限的应用程序使用的 PSI 调用。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-123">Ensure that you are a valid user on the server, and check that you have sufficient permissions for the PSI calls that your application uses.</span></span> <span data-ttu-id="e0ee1-124">每个 PSI 方法的开发人员文档主题包括 Project Server 权限表。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-124">The developer documentation topic for each PSI method includes a Project Server Permissions table.</span></span> <span data-ttu-id="e0ee1-125">例如， [Project.QueueCreateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueCreateProject.aspx)方法要求**新建项目**全局权限和**SaveProjectTemplate**权限。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-125">For example, the [Project.QueueCreateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueCreateProject.aspx) method requires the global **NewProject** permission and the **SaveProjectTemplate** permission.</span></span> 
  
    <span data-ttu-id="e0ee1-126">在某些情况下，您可能需要执行远程调试服务器上。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-126">In some cases, you may have to do remote debugging on the server.</span></span> <span data-ttu-id="e0ee1-127">您可能还需要设置事件处理程序，通过在 SharePoint 场中每个 Project Server 计算机上安装事件处理程序程序集，然后使用中常规 Project Server 设置页上配置的事件处理程序的 Project Web App 实例SharePoint 管理中心的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-127">You may also have to set up an event handler by installing an event handler assembly on each Project Server computer in the SharePoint farm, and then configuring the event handler for the Project Web App instance by using the Project Server Settings page in the General Application Settings of SharePoint Central Administration.</span></span>
    
2. <span data-ttu-id="e0ee1-128">**设置开发计算机。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-128">**Set up a development computer.**</span></span>
    
    <span data-ttu-id="e0ee1-p107">通常，您会通过网络访问 PSI。代码示例设计为在独立于服务器的客户端上运行，除非另有说明。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p107">You usually access the PSI through a network. The code samples are designed to be run on a client that is separate from the server, except where noted.</span></span>
    
    1. <span data-ttu-id="e0ee1-131">**安装 Visual Studio 的正确版本。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-131">**Install the correct version of Visual Studio.**</span></span> <span data-ttu-id="e0ee1-132">除非另有说明，代码示例会写入 Visual C# 中。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-132">Except where noted, the code samples are written in Visual C#.</span></span> <span data-ttu-id="e0ee1-133">它们可用于 Visual Studio 2010 或 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-133">They can be used with Visual Studio 2010 or Visual Studio 2012.</span></span> <span data-ttu-id="e0ee1-134">确保您已安装最新 service pack。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-134">Ensure that you have the most recent service pack installed.</span></span> 
    
    2. <span data-ttu-id="e0ee1-135">**将 Project Server Dll 复制到开发计算机。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-135">**Copy Project Server DLLs to the development computer.**</span></span> <span data-ttu-id="e0ee1-136">复制以下程序集从`[Program Files]\Microsoft Office Servers\15.0\Bin`到开发计算机上的 Project Server 计算机上：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-136">Copy the following assemblies from  `[Program Files]\Microsoft Office Servers\15.0\Bin` on the Project Server computer to the development computer:</span></span> 
    
       - <span data-ttu-id="e0ee1-137">Microsoft.Office.Project.Server.Events.Receivers.dll</span><span class="sxs-lookup"><span data-stu-id="e0ee1-137">Microsoft.Office.Project.Server.Events.Receivers.dll</span></span>
    
       - <span data-ttu-id="e0ee1-138">Microsoft.Office.Project.Server.Library.dll</span><span class="sxs-lookup"><span data-stu-id="e0ee1-138">Microsoft.Office.Project.Server.Library.dll</span></span>
    
    3. <span data-ttu-id="e0ee1-139">有关如何在 PSI 中编译 ProjectServerServices.dll 代理程序集并将其用于 WCF 服务的信息，请参阅[使用 PSI 代理程序集和 IntelliSense 说明](#pj15_PrerequisitesWCF_BuildingProxy)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-139">For information about how to compile and use the ProjectServerServices.dll proxy assembly for the WCF services in the PSI, see [Using a PSI proxy assembly and IntelliSense descriptions](#pj15_PrerequisitesWCF_BuildingProxy).</span></span>
    
3. <span data-ttu-id="e0ee1-140">**安装 IntelliSense 文件。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-140">**Install the IntelliSense files.**</span></span>
    
    <span data-ttu-id="e0ee1-141">要用于 Project Server 程序集，副本中类和成员的 IntelliSense 说明从 Project 2013 SDK 更新的 IntelliSense XML 文件下载到 Project Server 程序集所在的同一目录。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-141">To use IntelliSense descriptions for classes and members in Project Server assemblies, copy the updated IntelliSense XML files from the Project 2013 SDK download to the same directory where the Project Server assemblies are located.</span></span> <span data-ttu-id="e0ee1-142">例如，将 Microsoft.Office.Project.Server.Library.xml 文件复制到您的应用程序将在其中设置 Microsoft.Office.Project.Server.Library.dll 程序集的引用的目录。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-142">For example, copy the Microsoft.Office.Project.Server.Library.xml file to the directory where your application will set a reference to the Microsoft.Office.Project.Server.Library.dll assembly.</span></span>
    
    <span data-ttu-id="e0ee1-143">PSI 服务的 IntelliSense 说明需要使用 CompileWCFProxyAssembly.cmd 脚本创建 PSI 代理程序集`Documentation\IntelliSense\WCF`Project 2013 SDK 下载中的子目录。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-143">IntelliSense descriptions for the PSI services require that you create a PSI proxy assembly by using the CompileWCFProxyAssembly.cmd script in the  `Documentation\IntelliSense\WCF` subdirectory in the Project 2013 SDK download.</span></span> <span data-ttu-id="e0ee1-144">该脚本创建基于 WCF 的 ProjectServerServices.dll 代理程序集。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-144">The script creates the WCF-based ProjectServerServices.dll proxy assembly.</span></span> <span data-ttu-id="e0ee1-145">有关详细信息，请参阅 SDK 下载中的 [ReadMe_IntelliSense].mht 文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-145">For more information, see the [ReadMe_IntelliSense].mht file in the SDK download.</span></span> 
    
## <a name="creating-the-application-and-adding-a-service-reference"></a><span data-ttu-id="e0ee1-146">创建应用程序并添加服务引用</span><span class="sxs-lookup"><span data-stu-id="e0ee1-146">Creating the application and adding a service reference</span></span>
<span data-ttu-id="e0ee1-147"><a name="pj15_PrerequisitesWCF_Configure"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-147"></span></span>

1. <span data-ttu-id="e0ee1-148">**创建一个控制台应用程序。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-148">**Create a console application.**</span></span>
    
    <span data-ttu-id="e0ee1-p112">创建控制台应用程序时，请在“新建项目”\*\*\*\* 对话框的下拉列表中，选择“.NET Framework 4”\*\*\*\*。可以将 PSI 示例代码复制到新的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p112">When you create a console application, in the drop-down list of the **New Project** dialog box, select **.NET Framework 4**. You can copy the PSI example code into the new application.</span></span>
    
2. <span data-ttu-id="e0ee1-151">**添加 WCF 所需的引用。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-151">**Add references required for WCF.**</span></span>
    
    <span data-ttu-id="e0ee1-152">在解决方案资源管理器中，添加对**System.ServiceModel**引用 （见图 1）。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-152">In Solution Explorer, add a reference to **System.ServiceModel** (see Figure 1).</span></span> <span data-ttu-id="e0ee1-153">Web 应用程序将使用**System.ServiceModel.Web**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-153">A web application would use **System.ServiceModel.Web**.</span></span>
    
    <span data-ttu-id="e0ee1-154">此外，添加对 **System.Runtime.Serialization** 的引用。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-154">Also add a reference to **System.Runtime.Serialization**.</span></span>
    
    <span data-ttu-id="e0ee1-155">**图 1. 在 Visual Studio 中添加对基于 WCF 的应用程序的引用**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-155">**Figure 1. Adding the references in Visual Studio for a WCF-based application**</span></span>

    <span data-ttu-id="e0ee1-156">![添加 WCF 引用](media/pj15_PrerequisitesWCF_AddReference.gif "添加 WCF 引用")</span><span class="sxs-lookup"><span data-stu-id="e0ee1-156">![Adding references for WCF](media/pj15_PrerequisitesWCF_AddReference.gif "Adding references for WCF")</span></span>
  
3. <span data-ttu-id="e0ee1-157">**复制代码**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-157">**Copy the code**.</span></span>
    
    <span data-ttu-id="e0ee1-158">将完整的代码示例复制到控制台应用程序的 Program.cs 文件中。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-158">Copy the complete code example into the Program.cs file of the console application.</span></span>
    
4. <span data-ttu-id="e0ee1-159">**设置示例应用程序的命名空间。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-159">**Set the namespace for the sample application.**</span></span>
    
    <span data-ttu-id="e0ee1-p114">您可将示例顶部列出的命名空间更改为应用程序的默认命名空间，或更改默认的应用程序命名空间以与示例匹配。可以通过更改应用程序属性来更改默认应用程序命名空间。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p114">You can either change the namespace listed at the top of the sample to the application default namespace, or change the default application namespace to match the sample. You can change the default application namespace by changing the application properties.</span></span> 
    
    <span data-ttu-id="e0ee1-162">例如， [ReadResource](https://msdn.microsoft.com/library/WebSvcResource.Resource.ReadResource.aspx)的代码示例具有**Microsoft.SDK.Project.Samples.CreateResourceTest**的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-162">For example, the code sample for [ReadResource](https://msdn.microsoft.com/library/WebSvcResource.Resource.ReadResource.aspx) has the namespace **Microsoft.SDK.Project.Samples.CreateResourceTest**.</span></span> <span data-ttu-id="e0ee1-163">如果 Visual Studio 项目的名称， **ResourceTest**从 Program.cs 文件中，复制该命名空间，然后打开项目**属性**窗格 （在**项目**菜单中选择**ResourceTest 属性**）。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-163">If the name of the Visual Studio project is **ResourceTest**, copy the namespace from the Program.cs file, and then open the project **Properties** pane (on the **Project** menu, choose **ResourceTest Properties**).</span></span> <span data-ttu-id="e0ee1-164">在**应用程序**选项卡中，将命名空间复制到**默认命名空间**文本框。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-164">On the **Application** tab, copy the namespace into the **Default namespace** text box.</span></span> 
    
5. <span data-ttu-id="e0ee1-165">**设置服务引用。**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-165">**Set the service references.**</span></span>
    
    <span data-ttu-id="e0ee1-p116">许多示例都需要对一个或多个 PSI 服务的引用。它们将在示例本身中或示例前面的注释中列出。若要获取正确的服务引用的命名空间，请确保您先设置了默认应用程序命名空间。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p116">Many examples require a reference to one or more of the PSI services. These are listed in the sample itself or in comments that precede the sample. To get the correct namespace of the service references, ensure that you first set the default application namespace.</span></span>
    
    <span data-ttu-id="e0ee1-169">添加 WCF 服务引用的方法有下列三种：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-169">There are three ways to add a WCF service reference:</span></span>
    
    - <span data-ttu-id="e0ee1-p117">生成一个名为 ProjectServerServices.dll 的 PSI 代理程序集，然后设置对该程序集的引用。请参阅[使用 PSI 代理程序集和 IntelliSense 说明](#pj15_PrerequisitesWCF_BuildingProxy)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p117">Build a PSI proxy assembly named ProjectServerServices.dll, and then set a reference to the assembly. See [Using a PSI proxy assembly and IntelliSense descriptions](#pj15_PrerequisitesWCF_BuildingProxy).</span></span>
    
    - <span data-ttu-id="e0ee1-p118">将 svcutil.exe 输出中的代理文件添加到 Visual Studio 解决方案。请参阅[添加 PSI 代理文件](#pj15_PrerequisitesWCF_AddingProxyFile)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p118">Add a proxy file from the svcutil.exe output to the Visual Studio solution. See [Adding a PSI proxy file](#pj15_PrerequisitesWCF_AddingProxyFile).</span></span>
    
    - <span data-ttu-id="e0ee1-p119">使用 Visual Studio 添加服务引用。请参阅[添加服务引用](#pj15_PrerequisitesWCF_AddingServiceReference)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p119">Add a service reference by using Visual Studio. See [Adding a service reference](#pj15_PrerequisitesWCF_AddingServiceReference).</span></span>
    
### <a name="using-a-psi-proxy-assembly-and-intellisense-descriptions"></a><span data-ttu-id="e0ee1-176">使用 PSI 代理程序集和 IntelliSense 说明</span><span class="sxs-lookup"><span data-stu-id="e0ee1-176">Using a PSI proxy assembly and IntelliSense descriptions</span></span>
<span data-ttu-id="e0ee1-177"><a name="pj15_PrerequisitesWCF_BuildingProxy"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-177"></span></span>

<span data-ttu-id="e0ee1-178">代理程序集可用于在 PSI 中的所有公共 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-178">You can use a proxy assembly for all public WCF services in the PSI.</span></span> <span data-ttu-id="e0ee1-179">使用编译 ProjectServerServices.dll 代理程序集`Documentation\IntelliSense\WCF\CompileWCFProxyAssembly.cmd`脚本在 Project 2013 SDK 下载中，然后将代理程序集复制到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-179">Compile the ProjectServerServices.dll proxy assembly by using the  `Documentation\IntelliSense\WCF\CompileWCFProxyAssembly.cmd` script in the Project 2013 SDK download, and then copy the proxy assembly to your development computer.</span></span> <span data-ttu-id="e0ee1-180">将智能感知 ProjectServerServices.xml 文件复制到相同的位置。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-180">Copy the ProjectServerServices.xml file for IntelliSense to the same location.</span></span> <span data-ttu-id="e0ee1-181">在 Visual Studio 中，设置对 ProjectServerServices.dll 代理程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-181">In Visual Studio, set a reference to the ProjectServerServices.dll proxy assembly.</span></span> 
  
<span data-ttu-id="e0ee1-182">Project Server service pack 和更新，您可以更新代理源文件和 GenWCFProxyAssembly.cmd 脚本使用相同的 SDK 下载文件夹中创建新的代理程序集。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-182">For Project Server service packs and updates, you can update the proxy source files and create a new proxy assembly by using the GenWCFProxyAssembly.cmd script in the same SDK download folder.</span></span> <span data-ttu-id="e0ee1-183">SDK 下载链接，请参阅[Project 2013 开发人员文档](project-2013-developer-documentation.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-183">For a link to the SDK download, see [Project 2013 developer documentation](project-2013-developer-documentation.md).</span></span> <span data-ttu-id="e0ee1-184">有关详细信息，请参阅[添加服务引用](#pj15_PrerequisitesWCF_AddingServiceReference)部分。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-184">For more information, see the [Adding a service reference](#pj15_PrerequisitesWCF_AddingServiceReference) section.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e0ee1-185">当您从 Source.zip 提取代理源文件文件中的文件`Documentation\IntelliSense\WCF\Source`文件夹的当前 Project 2013 SDK 下载的发布日期。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-185">When you extract the proxy source files from the Source.zip file, the files in the  `Documentation\IntelliSense\WCF\Source` folder are current as of the publication date of the Project 2013 SDK download.</span></span> <span data-ttu-id="e0ee1-186">若要生成更新 Project Server 计算机上运行 GenASMXProxyAssembly.cmd 脚本的 PSI 代理源文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-186">To generate updated PSI proxy source files, run the GenASMXProxyAssembly.cmd script on the Project Server computer.</span></span> <span data-ttu-id="e0ee1-187">有关详细信息，请参阅[添加服务引用](#pj15_PrerequisitesWCF_AddingServiceReference)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-187">For more information, see [Adding a service reference](#pj15_PrerequisitesWCF_AddingServiceReference).</span></span> 
> 
> <span data-ttu-id="e0ee1-188">中的脚本`Documentation\IntelliSense\ASMX`文件夹基于 WCF 的应用程序不起作用。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-188">The scripts in the  `Documentation\IntelliSense\ASMX` folder do not work for WCF-based applications.</span></span> <span data-ttu-id="e0ee1-189">GenASMXProxyAssembly.cmd 脚本调用 Wsdl.exe，生成的 ASMX 服务的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-189">The GenASMXProxyAssembly.cmd script calls Wsdl.exe, which generates source code files for the ASMX services.</span></span> <span data-ttu-id="e0ee1-190">ASMX 代理文件包括不同的类和属性。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-190">The ASMX proxy files include different classes and properties.</span></span> <span data-ttu-id="e0ee1-191">例如，基于 ASMX 的资源的 web 服务包含**资源**类，而基于 WCF 的资源服务包括**资源**接口、 **ResourceChannel**接口以及**ResourceClient**类。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-191">For example, the ASMX-based Resource web service includes the **Resource** class, whereas the WCF-based Resource service includes the **Resource** interface, the **ResourceChannel** interface, and the **ResourceClient** class.</span></span> 
  
<span data-ttu-id="e0ee1-p124">为 ASMX Web 服务和 WCF 服务创建的任意命名空间都是相同的，以便 IntelliSense 的 ProjectServerServices.xml 文件可用于任一程序集。例如，基于 WCF 的代理程序集和基于 ASMX 的代理程序集中的 Resource 服务的命名空间为 **SvcResource**。当然，如果您确保命名空间名称在代理程序集和 ProjectServerServices.xml IntelliSense 文件中是匹配的，则可更改它们。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p124">The arbitrary namespaces created for both the ASMX web services and the WCF services are the same, so that the ProjectServerServices.xml file for IntelliSense works with either assembly. For example, the namespace of the Resource service in the WCF-based proxy assembly and in the ASMX-based proxy assembly is **SvcResource**. You can, of course, change the namespace names— if you ensure that they match in the proxy assembly and in the ProjectServerServices.xml IntelliSense file.</span></span>
  
<span data-ttu-id="e0ee1-195">如果代码示例的 PSI 服务命名空间使用的名称不同，例如 **ProjectWebSvc**，若要 IntelliSense 起作用，您必须更改示例才能使用 **SvcProject**，以便命名空间与代理程序集匹配。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-195">If a code sample uses a different name for a PSI service namespace, for example **ProjectWebSvc**, for IntelliSense to work you must change the sample to use **SvcProject** so that the namespace matches the proxy assembly.</span></span> 
  
<span data-ttu-id="e0ee1-196">使用基于 WCF 的代理程序集的优势如下：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-196">Advantages to using the WCF-based proxy assembly include the following:</span></span>
  
- <span data-ttu-id="e0ee1-p125">您可在 Project Server 计算机之外的其他计算机上使用代理程序集开发大多数解决方案。设置独立服务引用需要在 Project Server 计算机上进行开发。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p125">You can develop most solutions with the proxy assembly on a different computer than the Project Server computer. Setting an individual service reference requires development on the Project Server computer.</span></span>
    
- <span data-ttu-id="e0ee1-199">代理程序集包含所有 PSI 服务命名空间，因此您无需添加多个代理文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-199">The proxy assembly includes all PSI service namespaces, so you do not have to add multiple proxy files.</span></span>
    
- <span data-ttu-id="e0ee1-200">如果将 ProjectServerServices.xml 文件添加到您在其中设置对 ProjectServerServices.dll 代理程序集的引用相同的目录，可以获取 PSI 类和成员的 IntelliSense 说明。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-200">If you add the ProjectServerServices.xml file to the same directory where you set a reference to the ProjectServerServices.dll proxy assembly, you can get IntelliSense descriptions for the PSI classes and members.</span></span> <span data-ttu-id="e0ee1-201">有关详细信息，请参阅中的 [ReadMe_IntelliSense] 文件`Documentation\IntelliSense`Project 2013 SDK 下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-201">For more information, see the [ReadMe_IntelliSense] file in the  `Documentation\IntelliSense` folder of the Project 2013 SDK download.</span></span> 
    
<span data-ttu-id="e0ee1-202">**图 2. 将 IntelliSense 用于 Resource 服务中的方法**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-202">**Figure 2. Using IntelliSense for a method in the Resource service**</span></span>

<span data-ttu-id="e0ee1-203">![对 ReadResource 方法使用 Intellisense](media/pj15_PrerequisitesWCF_Intellisense.gif "对 ReadResource 方法使用 Intellisense")</span><span class="sxs-lookup"><span data-stu-id="e0ee1-203">![Using Intellisense for the ReadResource method](media/pj15_PrerequisitesWCF_Intellisense.gif "Using Intellisense for the ReadResource method")</span></span>
  
<span data-ttu-id="e0ee1-p127">使用代理程序集的缺点是，解决方案更大并且您必须使用解决方案来分发和安装代理程序集。还必须使用同位于代理程序集和 IntelliSense 文件的命名空间，除非您将脚本更改为生成代理程序集并将 ProjectServerServices.xml IntelliSense 文件更改为使用其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p127">Disadvantages to using the proxy assembly are that the solution is larger and you must distribute and install the proxy assembly with the solution. You must also use the same namespaces that are in the proxy assembly and IntelliSense files, unless you change the script to build a proxy assembly and change the ProjectServerServices.xml IntelliSense file to use different namespaces.</span></span>
  
### <a name="adding-a-psi-proxy-file"></a><span data-ttu-id="e0ee1-206">添加 PSI 代理文件</span><span class="sxs-lookup"><span data-stu-id="e0ee1-206">Adding a PSI proxy file</span></span>
<span data-ttu-id="e0ee1-207"><a name="pj15_PrerequisitesWCF_AddingProxyFile"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-207"></span></span>

<span data-ttu-id="e0ee1-208">Project 2013 SDK 下载包括为代理程序集由 SvcUtil.exe 命令生成的源文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-208">The Project 2013 SDK download includes the source files that are generated by the SvcUtil.exe command for the proxy assembly.</span></span> <span data-ttu-id="e0ee1-209">源文件位于 Source.zip 文件`Documentation\IntelliSense\WCF`子目录。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-209">The source files are in the Source.zip file in the  `Documentation\IntelliSense\WCF` subdirectory.</span></span> <span data-ttu-id="e0ee1-210">而不是设置代理程序集的引用，可以将一个或多个的源文件添加到 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-210">Instead of setting a reference to the proxy assembly, you can add one or more of the source files to a Visual Studio solution.</span></span> <span data-ttu-id="e0ee1-211">例如，若要使用的 Project 服务和资源服务，添加 wcf。Project.cs 和 wcf。向解决方案 Resource.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-211">For example, to use the Project service and the Resource service, add the wcf.Project.cs and wcf.Resource.cs files to the solution.</span></span> 
  
<span data-ttu-id="e0ee1-p129">在 WCF 中，每个 PSI 服务中的主类都是由接口定义的，并且在客户端类中实现，以获取对成员的访问权限。例如，**SvcProject.Resource** 接口是在 **SvcProject.ResourceClient** 类中实现的。例如，若要将 **ResourceClient** 对象定义为名为 **resourceClient** 的类变量，请使用下列代码。在此示例中，**SetClientEndpoints** 方法将创建一个使用 **basicHttp_Project** 终结点（其是在 app.config 文件中定义的）的 **resourceClient** 对象。有关 app.config 文件的详细信息，请参阅[添加服务配置文件](#pj15_PrerequisitesWCF_AddConfig)部分。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p129">In WCF, the primary class in each PSI service is defined by an interface and implemented in a client class for access to the members. For example, the **SvcProject.Resource** interface is implemented in the **SvcProject.ResourceClient** class. To define a **ResourceClient** object as a class variable named **resourceClient**, for example, use the following code. In the example, the **SetClientEndpoints** method creates a **resourceClient** object that uses the **basicHttp_Project** endpoint, which is defined in the app.config file. For more information about the app.config file, see the [Adding a service configuration file](#pj15_PrerequisitesWCF_AddConfig) section.</span></span> 
  
```cs
private static SvcResource.ResourceClient resourceClient;
. . .
private static void SetClientEndpoints()
{
  resourceClient = new SvcResource.ResourceClient("basicHttp_Resource");
  . . .
}
public void DisposeClients()
{
  resourceClient.Close();
  . . .
}
```

> [!NOTE]
> <span data-ttu-id="e0ee1-217">无论您为名为 **SvcResource** 的 Project 服务引用使用 PSI 代理程序集还是添加代理文件，都将使用相同的代码创建和释放 **resourceClient** 对象。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-217">Whether you use a PSI proxy assembly or add a proxy file for a Project service reference named **SvcResource**, you would use the same code to create and dispose a **resourceClient** object.</span></span> 
  
### <a name="adding-a-service-reference"></a><span data-ttu-id="e0ee1-218">添加服务引用</span><span class="sxs-lookup"><span data-stu-id="e0ee1-218">Adding a service reference</span></span>
<span data-ttu-id="e0ee1-219"><a name="pj15_PrerequisitesWCF_AddingServiceReference"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-219"></span></span>

<span data-ttu-id="e0ee1-220">如果您不使用基于 WCF 的代理程序集或添加 PSI 服务代理文件，您可以直接在 Visual Studio 中设置一个或多个单独的服务引用。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-220">If you do not use the WCF-based proxy assembly or add a proxy file for a PSI service, you can set one or more individual service references directly in Visual Studio.</span></span> <span data-ttu-id="e0ee1-221">您可以使用以下过程的步骤 1 创建更新的代理文件，若要准备`Documentation\IntelliSense\WCF\GenWCFProxyAssembly.cmd`脚本的 Project 2013 SDK 下载中包含。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-221">You can also use step 1 of the following procedure to create updated proxy files, to prepare for the  `Documentation\IntelliSense\WCF\GenWCFProxyAssembly.cmd` script that is included in the Project 2013 SDK download.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e0ee1-p131">若要设置服务引用，您必须在 Project Server 计算机上使用 Visual Studio。建议您使用 ProjectServerServices.dll 代理程序集或添加代理源文件，而不是直接在 Visual Studio 中添加服务引用。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p131">To set a service reference, you must use Visual Studio on the Project Server computer. We recommend that you use the ProjectServerServices.dll proxy assembly or add proxy source files, instead of directly adding service references in Visual Studio.</span></span> 
  
<span data-ttu-id="e0ee1-224">以下步骤演示如何通过运行测试安装的 Project Server 的计算机上使用 Visual Studio 2012 设置服务引用：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-224">The following steps show how to set a service reference by using Visual Studio 2012 on a computer running a test installation of Project Server:</span></span>
  
1. <span data-ttu-id="e0ee1-225">若要获取对后端 WCF 服务的访问权限，请在 Project Server 计算机上运行 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-225">To get access to the back-end WCF services, run Visual Studio on the Project Server computer.</span></span>
    
2. <span data-ttu-id="e0ee1-226">在“解决方案资源管理器”\*\*\*\* 中，右键单击“引用”\*\*\*\* 文件夹，然后选择“添加服务引用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-226">In **Solution Explorer**, right-click the **References** folder, and then choose **Add Service Reference**.</span></span> 
    
3. <span data-ttu-id="e0ee1-227">在**添加服务引用**对话框中**地址**文本框中，键入https://localhost:32843/ _GUID_/psi/ _ServiceName_.svc，并按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-227">In the **Add Service Reference** dialog box, in the **Address** text box, type https://localhost:32843/ _GUID_/psi/ _ServiceName_.svc, and then press **Enter**.</span></span> <span data-ttu-id="e0ee1-228">Project Server service 应用程序，如 534c37eb00d74ccfadcecf9827e95239 的虚拟目录名称中替换_GUID_ 。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-228">Replace  _GUID_ with the virtual directory name of the Project Server service application, such as 534c37eb00d74ccfadcecf9827e95239.</span></span> <span data-ttu-id="e0ee1-229">_ServiceName_替换该服务，如资源的名称 （请参阅图 3）。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-229">Replace  _ServiceName_ with the name of the service, such as Resource (see Figure 3).</span></span> 
    
   <span data-ttu-id="e0ee1-230">您可通过下列方式之一获取 Project Server Service 虚拟目录的名称：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-230">You can get the name of the Project Server Service virtual directory in one of the following ways:</span></span>
    
   - <span data-ttu-id="e0ee1-231">在浏览器中打开 SharePoint 2013 管理中心应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-231">Open the SharePoint 2013 Central Administration application in your browser.</span></span> <span data-ttu-id="e0ee1-232">选择**管理服务应用程序**，然后选择所需的 Project Server PSI 服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-232">Choose **Manage service applications**, and then choose the Project Server PSI Service application that you want.</span></span> <span data-ttu-id="e0ee1-233">例如，选择**ProjectServerService**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-233">For example, choose **ProjectServerService**.</span></span> <span data-ttu-id="e0ee1-234">管理 Project Web App 网站页的 URL 包含虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-234">The URL of the Manage Project Web App Sites page contains the virtual directory name.</span></span> <span data-ttu-id="e0ee1-235">例如，在`https://ServerName:8080/_admin/pwa/managepwa.aspx?appid=534c37eb-00d7-4ccf-adce-cf9827e95239`，虚拟目录名即`534c37eb00d74ccfadcecf9827e95239`（目录名称包含任何虚线）。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-235">For example, in  `https://ServerName:8080/_admin/pwa/managepwa.aspx?appid=534c37eb-00d7-4ccf-adce-cf9827e95239`, the virtual directory name is  `534c37eb00d74ccfadcecf9827e95239` (the directory name contains no dashes).</span></span> 
    
   - <span data-ttu-id="e0ee1-p134">在 Project Server 计算机上打开“Internet Information Services (IIS) 管理器”\*\*\*\* 对话框。在“连接”\*\*\*\* 窗格的“SharePoint Web 服务”\*\*\*\* 节点，然后展开该节点下的服务虚拟目录，直到您发现目录包含 PSI 文件夹。选择目录，然后选择“操作”\*\*\*\* 窗格中的“高级设置”\*\*\*\*，然后将目录名称复制在“虚拟路径”\*\*\*\* 字段中。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p134">Open the **Internet Information Services (IIS) Manager** dialog box on the Project Server computer. Expand the **SharePoint Web Services** node in the **Connections** pane, and then expand the service virtual directories below that, until you find the directory that includes a PSI folder. Select the directory, choose **Advanced Settings** in the **Actions** pane, and then copy the directory name in the **Virtual Path** field.</span></span> 
    
      > [!NOTE]
      > <span data-ttu-id="e0ee1-239">可以有多个 Project Server Service 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-239">There can be more than one Project Server Service virtual directory.</span></span> <span data-ttu-id="e0ee1-240">确保您选择包含所需的 Project Web App 实例的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-240">Ensure that you choose the virtual directory that contains the Project Web App instance that you want.</span></span> 
  
   - <span data-ttu-id="e0ee1-241">与 SharePoint 2013 一起安装的 Windows PowerShell 中使用**Get-spserviceapplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-241">Use the **get-SPServiceApplication** cmdlet in Windows PowerShell that is installed with SharePoint 2013.</span></span> <span data-ttu-id="e0ee1-242">在任务栏上的**开始**菜单上，选择**所有程序**、 都选择**Microsoft SharePoint 2013 产品**，然后都选择**SharePoint 2013 Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-242">On the taskbar **Start** menu, choose **All Programs**, choose **Microsoft SharePoint 2013 Products**, and then choose **SharePoint 2013 Management Shell**.</span></span> <span data-ttu-id="e0ee1-243">下面是命令以及**SharePoint 2013get-命令行管理程序**窗口 （您 Guid 将不同） 的定义的服务应用程序中的结果。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-243">Following is the command and the results in the **SharePoint 2013get- Management Shell** window for the defined service applications (your GUIDs will be different).</span></span> <span data-ttu-id="e0ee1-244">将复制的 Project Server service 应用程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-244">Copy the GUID for the Project Server service application.</span></span> 
    
        ```powershell
            PS > get-SPServiceApplication
            DisplayName          TypeName             Id
            -----------          --------             --
            State Service        State Service        04041cfa-4ab3-4473-8bc8-3967b02eff39
            ProjectServerSer...  Project Server PS... 534c37eb-00d7-4ccf-adce-cf9827e95239
            Security Token Se... Security Token Se... 7243732e-edea-405d-8cc8-1716b99faef5
            Application Disco... Application Disco... 3bfbdeb0-bc20-4a21-801c-cc6f1ce6c643
            SharePoint Server... SharePoint Server... 09912f49-3b72-462f-a44c-6533b578286a  
        ```

      <span data-ttu-id="e0ee1-245">如果您知道 Project Server Service Application 的全名，则可使用它获取 GUID 值，例如：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-245">If you know the full name of the Project Server Service application, you can use it to get the GUID value, for example:</span></span>
    
        ```powershell
        PS > $projectService = "ProjectServerService"
        PS > (get-SPServiceApplication -Name $projectService).Id
        Guid
        ----
        534c37eb-00d7-4ccf-adce-cf9827e95239
       ```

      > [!NOTE]
      > <span data-ttu-id="e0ee1-246">删除 GUID 中的短划线以获取虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-246">Remove the dashes in the GUID to get the virtual directory name.</span></span> 
  
   <span data-ttu-id="e0ee1-247">例如，Url`https://localhost:32843/534c37eb00d74ccfadcecf9827e95239/PSI/Resource.svc`是标准的 Project Server 服务。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-247">URLs such as  `https://localhost:32843/534c37eb00d74ccfadcecf9827e95239/PSI/Resource.svc` are standard for Project Server services.</span></span> 
    
4. <span data-ttu-id="e0ee1-248">服务引用解析后，请在**Namespace**文本框中键入引用名称。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-248">After the service reference resolves, type the reference name in the **Namespace** text box.</span></span> <span data-ttu-id="e0ee1-249">Project 2013 开发人员文档中的代码示例使用任意命名空间名称**Svc _ServiceName_**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-249">Code examples in the Project 2013 developer documentation use the arbitrary namespace name **Svc _ServiceName_**.</span></span> <span data-ttu-id="e0ee1-250">例如，资源服务的代码示例在名为**SvcResource**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-250">For example, the Resource service in the code examples is named **SvcResource**.</span></span>
    
    <span data-ttu-id="e0ee1-251">**图 3. 添加基于 WCF 的 Resource 服务引用**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-251">**Figure 3. Adding the WCF-based Resource service reference**</span></span>

    <span data-ttu-id="e0ee1-252">![添加基于 WCF 的资源服务引用](media/pj15_PrerequisitesWCF_AddSvcReference.gif "添加基于 WCF 的资源服务引用")</span><span class="sxs-lookup"><span data-stu-id="e0ee1-252">![Adding the WCF-based Resource service reference](media/pj15_PrerequisitesWCF_AddSvcReference.gif "Adding the WCF-based Resource service reference")</span></span>
  
5. <span data-ttu-id="e0ee1-253">替换原始 （重命名为 web.config），为 Project Service 目录中的临时 web.config 文件，然后重新运行`iisreset`。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-253">Replace the temporary web.config file in the Project Service directory with the original (renamed to web.config), and then rerun  `iisreset`.</span></span>
    
## <a name="setting-other-references"></a><span data-ttu-id="e0ee1-254">设置其他引用</span><span class="sxs-lookup"><span data-stu-id="e0ee1-254">Setting other references</span></span>
<span data-ttu-id="e0ee1-255"><a name="pj15_PrerequisitesWCF_OtherReferences"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-255"></span></span>

<span data-ttu-id="e0ee1-256">Project Server 应用程序通常使用其他服务，例如 SharePoint 2013 web 服务。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-256">Project Server applications often use other services, such as SharePoint 2013 web services.</span></span> <span data-ttu-id="e0ee1-257">需要其他服务或引用时，所述的代码示例。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-257">If other services or references are required, they are noted in the code example.</span></span>
  
<span data-ttu-id="e0ee1-258">代码示例的本地引用列出在示例顶部的**using**语句。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-258">Local references for the code sample are listed in **using** statements at the top of the sample.</span></span> 
  
1. <span data-ttu-id="e0ee1-259">在“解决方案资源管理器”\*\*\*\* 中，右键单击“引用”\*\*\*\* 文件夹，然后选择“添加引用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-259">In **Solution Explorer**, right-click the **References** folder, and then choose **Add Reference**.</span></span>
    
2. <span data-ttu-id="e0ee1-p139">选择“浏览”\*\*\*\*，然后浏览到之前复制的 Project Server DLL 的存储位置。选择所需 DLL，然后选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p139">Choose **Browse**, and then browse to the location where you stored the Project Server DLLs that you copied previously. Choose the DLLs that you want, and then choose **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e0ee1-262">确保您的开发计算机上的程序集版本与目标 Project Server 计算机上的程序集版本完全匹配。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-262">Ensure that the assembly versions on your development computer exactly match those on the target Project Server computer.</span></span> 
  
## <a name="adding-a-service-configuration-file"></a><span data-ttu-id="e0ee1-263">添加服务配置文件</span><span class="sxs-lookup"><span data-stu-id="e0ee1-263">Adding a service configuration file</span></span>
<span data-ttu-id="e0ee1-264"><a name="pj15_PrerequisitesWCF_AddConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-264"></span></span>

<span data-ttu-id="e0ee1-p140">如果应用程序以编程方式配置 WCF 服务，则将不会使用服务配置文件。否则，Windows 应用程序或控制台应用程序将使用 app.config 文件中的 **system.serviceModel** 元素；Web 应用程序的 web.config 中包含 **system.serviceModel**。有关使用 app.config 文件或以编程方式配置 WCF 服务的详细信息，请参阅[演练：使用 WCF 开发 PSI 应用程序](https://msdn.microsoft.com/library/65707234-c3da-44e4-8364-32a6be28f645%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p140">If an application programmatically configures the WCF services, it does not use a service configuration file. Otherwise, a Windows application or console application uses the **system.serviceModel** element in an app.config file; a web application includes **system.serviceModel** in web.config. For more information about using an app.config file or programmatically configuring the WCF services, see [Walkthrough: Developing PSI applications using WCF](https://msdn.microsoft.com/library/65707234-c3da-44e4-8364-32a6be28f645%28Office.15%29.aspx).</span></span>
  
<span data-ttu-id="e0ee1-267">在生成服务代理源文件时, SvcUtil.exe 命令还将创建 app.config 文件中的默认**system.serviceModel**元素的基础 output.config 文件或 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-267">When it generates a service proxy source file, the SvcUtil.exe command also creates an output.config file that is the basis for the default **system.serviceModel** element in an app.config file or web.config file.</span></span> <span data-ttu-id="e0ee1-268">Project 2013 SDK 下载包括中的示例 output.config 文件`Documentation\IntelliSense\WCF\Source.zip`。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-268">The Project 2013 SDK download includes a sample output.config file in  `Documentation\IntelliSense\WCF\Source.zip`.</span></span> <span data-ttu-id="e0ee1-269">例如，资源服务 SvcUtil.exe 创建的默认 output.config 文件包含两个的绑定，名为**BasicHttpBinding_Resource**和**BasicHttpBinding_Resource1**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-269">For example, the default output.config file that SvcUtil.exe creates for the Resource service includes two bindings, named **BasicHttpBinding_Resource** and **BasicHttpBinding_Resource1**.</span></span> <span data-ttu-id="e0ee1-270">**客户端**元素包含两个默认终结点。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-270">The **client** element includes two default endpoints.</span></span> <span data-ttu-id="e0ee1-271">一个终结点端口 32843 上的 HTTP 地址安全访问，其他为普通访问端口 32843，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-271">One endpoint is for the secure access to the HTTP address on port 32843 and the other is for normal access on port 32843, as follows:</span></span> 
  
```XML
<client>
    <endpoint address="https://ServerName.domain:32843/GUID/PSI/Resource.svc/secure"
        binding="basicHttpBinding" bindingConfiguration="BasicHttpBinding_Resource"
        contract="SvcResource.Resource" name="BasicHttpBinding_Resource" />
address="https://ServerName.domain:32843/GUID/PSI/Resource.svc"
        binding="basicHttpBinding" bindingConfiguration="BasicHttpBinding_Resource1"
        contract="SvcResource.Resource" name="BasicHttpBinding_Resource1" />
</client>
```

<span data-ttu-id="e0ee1-p142">PSI 服务配置不会使用默认绑定和终结点。Project Server 需要应用程序通过前端 ProjectServer.svc（其充当用于调用后端服务的传送器）访问 PSI 服务。若要创建 app.config 文件，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p142">PSI service configuration does not use the default bindings and endpoints. Project Server requires that applications access PSI services through the front-end ProjectServer.svc, which acts as a router for calls to the back-end services. To create the app.config file, do the following steps:</span></span>
  
1. <span data-ttu-id="e0ee1-275">如果您设置引用 ProjectServerServices.dll 代理程序集，或添加服务的代理源文件，应用程序不包含 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-275">If you set a reference to the ProjectServerServices.dll proxy assembly, or add the proxy source file for a service, the application does not contain an app.config file.</span></span> <span data-ttu-id="e0ee1-276">向 Visual Studio 项目中添加新项。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-276">Add a new item to the Visual Studio project.</span></span> <span data-ttu-id="e0ee1-277">在**添加新项**对话框中，选择**应用程序配置文件**模板、 app.config，将其命名，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-277">In the **Add New Item** dialog box, choose the **Application Configuration File** template, name it app.config, and then choose **Add**.</span></span>
    
2. <span data-ttu-id="e0ee1-278">删除在 app.config 文件中，所有文本，然后将以下代码复制到该文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-278">Delete all text in the app.config file, and then copy the following code into the file.</span></span> <span data-ttu-id="e0ee1-279">您可以使用相同的绑定，例如`basicHttpConf`，每个服务终结点。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-279">You can use the same binding, for example  `basicHttpConf`, for each service endpoint.</span></span> <span data-ttu-id="e0ee1-280">如果您想要使用多个的绑定，例如，要绑定 HTTP 和 HTTPS 协议，您必须创建每个协议的绑定。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-280">If you want to use more than one binding, for example, to bind both HTTP and HTTPS protocols, you must create a binding for each protocol.</span></span>
    
    ```XML
        <?xml version="1.0" encoding="utf-8" ?>
        <configuration>
            <system.serviceModel>
                <behaviors>
                    <endpointBehaviors>
                        <behavior name="basicHttpBehavior">
                            <clientCredentials>
                                <windows allowedImpersonationLevel="Impersonation" />
                            </clientCredentials>
                        </behavior>
                    </endpointBehaviors>
                </behaviors>
                <bindings>
                    <basicHttpBinding>
                        <binding name="basicHttpConf" sendTimeout="01:00:00" 
                            maxBufferSize="500000000" maxReceivedMessageSize="500000000">
                            <readerQuotas maxDepth="32" maxStringContentLength="8192" 
                                maxArrayLength="16384" maxBytesPerRead="4096" 
                                maxNameTableCharCount="500000000" />
                            <security mode="TransportCredentialOnly">
                                <transport clientCredentialType="Ntlm" realm="https://SecurityDomain" />
                            </security>
                        </binding>
                    </basicHttpBinding>
                </bindings>
                <client>
                    <endpoint address="https://ServerName/ProjectServerName/_vti_bin/PSI/ProjectServer.svc"
                        behaviorConfiguration="basicHttpBehavior" binding="basicHttpBinding"
                        bindingConfiguration="basicHttpConf" 
                        contract="SvcServiceName.ServiceName"
                        name="basicHttp_ServiceName" />
                </client>
            </system.serviceModel>
        </configuration>
    ```

3. <span data-ttu-id="e0ee1-281">替换`ServerName/ProjectServerName`中的服务器和 Project Web App 实例名称的客户端终结点地址。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-281">Replace  `ServerName/ProjectServerName` in the client endpoint address with the name of your server and Project Web App instance.</span></span> 
    
4. <span data-ttu-id="e0ee1-282">替换`ServiceName`PSI 服务，如资源的名称。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-282">Replace  `ServiceName` with the name of the PSI service, such as Resource.</span></span> <span data-ttu-id="e0ee1-283">确保您替换所有三个实例的服务名称，例如：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-283">Ensure that you replace all three instances of the service name, for example:</span></span>
    
    ```XML
        <endpoint address="https://myserver/pwa/_vti_bin/PSI/ProjectServer.svc"
            behaviorConfiguration="basicHttpBehavior" binding="basicHttpBinding"
            bindingConfiguration="basicHttpConf" 
            contract="SvcResource.Resource"
            name="basicHttp_Resource" />
    ```

5. <span data-ttu-id="e0ee1-p146">若要使用多个 PSI 服务，请为每个服务以及服务使用的每个 **binding** 元素创建一个 **endpoint** 元素。例如，下列终结点将客户端配置为对 Project 服务和 QueueSystem 服务使用 HTTP 绑定。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p146">To use more than one PSI service, create one **endpoint** element for each service, and for each **binding** element that service uses. For example, the following endpoints configure the client to use the basic HTTP binding for the Project service and the QueueSystem service.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e0ee1-286">如果运行应用程序时收到“服务器太忙”或“HTTP 请求未经授权”的错误，请确保 app.config 文件中的终结点地址正确。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-286">If you run an application and get an error that the server is too busy, or that the HTTP request is unauthorized, ensure that the endpoint addresses are correct in the app.config file.</span></span> 
  
    ```XML
        <client>
        <endpoint address="https://ServerName/pwa/_vti_bin/PSI/ProjectServer.svc"
            behaviorConfiguration="basicHttpBehavior" binding="basicHttpBinding"
            bindingConfiguration="basicHttpConf" 
            contract="SvcProject.Project"
            name="basicHttp_Project" />
        <endpoint address="https://ServerName/pwa/_vti_bin/PSI/ProjectServer.svc"
            behaviorConfiguration="basicHttpBehavior" binding="basicHttpBinding"
            bindingConfiguration="basicHttpConf" 
            contract="SvcQueueSystem.QueueSystem"
            name="basicHttp_QueueSystem" />
        </client>
    ```

<span data-ttu-id="e0ee1-287">您可以通过使用 Visual Studio 中 （在**工具**菜单中） 的**WCF 服务配置编辑器**编辑 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-287">You can edit an app.config file by using the **WCF Service Configuration Editor** in Visual Studio (on the **Tools** menu).</span></span> <span data-ttu-id="e0ee1-288">图 4 显示了如何在**Microsoft 服务配置编辑器**对话框中设置的**合同**元素。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-288">Figure 4 shows how to set the **contract** element in the **Microsoft Service Configuration Editor** dialog box.</span></span> <span data-ttu-id="e0ee1-289">如果解决方案使用 PSI 代理程序集，打开在 ProjectServerServices.dll`bin\debug`目录的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-289">If the solution is using the PSI proxy assembly, open ProjectServerServices.dll in the  `bin\debug` directory of the Visual Studio solution.</span></span> <span data-ttu-id="e0ee1-290">**合同类型浏览器**对话框中显示的所有 WCF 服务协定 （参见图 5）。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-290">The **Contract Type Browser** dialog box shows all of the WCF service contracts (see Figure 5).</span></span> 
  
<span data-ttu-id="e0ee1-291">**图 4. 使用 WCF 服务配置编辑器**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-291">**Figure 4. Using the WCF Service Configuration Editor**</span></span>

<span data-ttu-id="e0ee1-292">![使用 WCF 服务配置编辑器](media/pj15_PrerequisitesWCF_ServiceConfigurationEditor.gif "使用 WCF 服务配置编辑器")</span><span class="sxs-lookup"><span data-stu-id="e0ee1-292">![Using the WCF Service Configuration Editor](media/pj15_PrerequisitesWCF_ServiceConfigurationEditor.gif "Using the WCF Service Configuration Editor")</span></span>
  
<span data-ttu-id="e0ee1-293">如果解决方案使用的服务代理文件，如 wcfResource.cs，编译应用程序，然后打开中的可执行文件`bin\debug`目录。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-293">If the solution is using a service proxy file, such as wcfResource.cs, compile the application and then open the executable file in the  `bin\debug` directory.</span></span> <span data-ttu-id="e0ee1-294">有关编辑 app.config 文件的详细信息，请参阅[演练： 使用 WCF 开发 PSI 应用程序](https://msdn.microsoft.com/library/65707234-c3da-44e4-8364-32a6be28f645%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-294">For more information about editing the app.config file, see [Walkthrough: Developing PSI applications using WCF](https://msdn.microsoft.com/library/65707234-c3da-44e4-8364-32a6be28f645%28Office.15%29.aspx).</span></span>
  
<span data-ttu-id="e0ee1-295">**图 5. 使用 WCF 服务配置编辑器中的合同类型浏览器**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-295">**Figure 5. Using the Contract Type Browser in the WCF Service Configuration Editor**</span></span>

<span data-ttu-id="e0ee1-296">![使用合同类型浏览器](media/pj15_PrerequisitesWCF_ContractTypeBrowser.gif "使用合同类型浏览器")</span><span class="sxs-lookup"><span data-stu-id="e0ee1-296">![Using the Contract Type Browser](media/pj15_PrerequisitesWCF_ContractTypeBrowser.gif "Using the Contract Type Browser")</span></span>
  
## <a name="using-multiple-authentication"></a><span data-ttu-id="e0ee1-297">使用多身份验证</span><span class="sxs-lookup"><span data-stu-id="e0ee1-297">Using multiple authentication</span></span>
<span data-ttu-id="e0ee1-298"><a name="pj15_PrerequisitesWCF_ClaimsMultiAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-298"></span></span>

<span data-ttu-id="e0ee1-299">通过 Windows 身份验证或表单身份验证的内部部署 Project Server 用户身份验证是通过在 SharePoint 中处理的声明。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-299">Authentication of on-premises Project Server users, whether by Windows authentication or Forms authentication, is done through claims processing in SharePoint.</span></span> <span data-ttu-id="e0ee1-300">多个身份验证是指在其设置 Project Web App 的 web 应用程序支持 Windows 身份验证和基于表单的身份验证。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-300">Multiple authentication means that the web application on which Project Web App is provisioned supports both Windows authentication and Forms-based authentication.</span></span> <span data-ttu-id="e0ee1-301">如果是这样，对 WCF 服务使用 Windows 身份验证任何调用将失败并出现以下错误，因为声明过程无法确定哪种类型的用户进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-301">If that is the case, any call to a WCF service that uses Windows authentication will fail with the following error, because the claims process cannot determine which type of user to authenticate:</span></span>
  
`The server was unable to process the request due to an internal error. For more information about the error, either turn on Include ExceptionDetailInFaults (either from ServiceBehaviorAttribute or from the <serviceDebug> configuration behavior) on the server in order to send the exception information back to the client, or turn on tracing as per the Microsoft .NET Framework 3.0 SDK documentation and inspect the server trace logs.`

<span data-ttu-id="e0ee1-p150">若要修复此 WCF 问题，对 PSI 方法的任何调用因位于为每个 PSI 服务定义的 **OperationContextScope** 中。请勿嵌套多个服务的域；例如，对 Resource 服务和 Project 服务使用调用时，每组呼叫应位于其自己的域中。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p150">To fix the problem for WCF, all calls to PSI methods should be within an **OperationContextScope** that is defined for each PSI service. Do not nest scopes for multiple services; for example, when using calls to the Resource and Project services, each set of calls should be within its own scope.</span></span> 
  
<span data-ttu-id="e0ee1-304">在以下示例中，可从应用程序中的每个**OperationContextScope**部分调用**DisableFormsAuth**方法。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-304">In the following example, the **DisableFormsAuth** method can be called from every **OperationContextScope** section in an application.</span></span> <span data-ttu-id="e0ee1-305">则方法删除以前禁用表单身份验证，因此如果_isWindowsAuth_参数为**false**，可以继续进行表单身份验证的任何标题值。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-305">The method removes any header value that previously disabled Forms authentication, so that Forms authentication can proceed if the  _isWindowsAuth_ parameter is **false**.</span></span> <span data-ttu-id="e0ee1-306">如果_isWindowsAuth_为**true**，则**DisableFormsAuth**方法禁用表单身份验证。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-306">If  _isWindowsAuth_ is **true**, the **DisableFormsAuth** method disables Forms authentication.</span></span> 
  
<span data-ttu-id="e0ee1-307">在 **WcfSample** 方法中，**projectClient** 对象是 PSI **SvcProject.ProjectClient** 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-307">In the **WcfSample** method, the **projectClient** object is an instance of the PSI **SvcProject.ProjectClient** class.</span></span> 
  
```cs
// Class variable that determines whether to disable Forms authentication.
private bool isWindowsUser = true;
public void DisableFormsAuth(bool isWindowsAuth)
{
    WebOperationContext.Current.OutgoingRequest.Headers.Remove(
        "X-FORMS_BASED_AUTH_ACCEPTED");
    if (isWindowsAuth)
    {
        // Disable Forms authentication, to enable Windows authentication.
        WebOperationContext.Current.OutgoingRequest.Headers.Add(
            "X-FORMS_BASED_AUTH_ACCEPTED", "f");
    }
}
private void WcfSample()
{
    // Limit the scope of WCF calls to the client channel. 
    using (OperationContextScope scope = new OperationContextScope(projectClient.InnerChannel))
    {
        // Add a web request header to enable Windows authentication in 
        // multiple authentication installations.
        DisableFormsAuth(isWindowsUser);
        // Add calls to the projectClient methods here:
        // . . .
    }
}
```

> [!NOTE]
> <span data-ttu-id="e0ee1-p152">在 **OperationContextScope** 中调用 PSI 只需在多身份验证环境中运行的应用程序。如果 Project Server 仅使用 Windows 身份验证，则无需设置域和添加禁用表单身份验证的 Web 请求头。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p152">Making PSI calls within an **OperationContextScope** is required only for applications that run in a multiple authentication environment. If Project Server uses only Windows authentication, it is not necessary to set a scope and add a web request header that disables Forms authentication.</span></span> 
> 
> <span data-ttu-id="e0ee1-310">基于 ASMX 的应用程序的解决方法是不同。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-310">The fix for an ASMX-based application is different.</span></span> <span data-ttu-id="e0ee1-311">有关详细信息，请参阅*使用多身份验证*部分中[项目中的基于 ASMX 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-311">For more information, see the  *Using multiple-authentication*  section in [Prerequisites for ASMX-based code samples in Project](prerequisites-for-asmx-based-code-samples-in-project.md).</span></span> 
  
## <a name="changing-values-of-generic-constants"></a><span data-ttu-id="e0ee1-312">更改泛型常量值</span><span class="sxs-lookup"><span data-stu-id="e0ee1-312">Changing values of generic constants</span></span>
<span data-ttu-id="e0ee1-313"><a name="pj15_PrerequisitesWCF_ChangeValues"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-313"></span></span>

<span data-ttu-id="e0ee1-314">大多数示例具有一个或多个必须更新示例以正确环境中的变量。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-314">Most samples have one or more variables that you must update for the sample to work properly in your environment.</span></span> <span data-ttu-id="e0ee1-315">在以下示例中，情况下，如果您有 SSL 安装，使用 HTTPS 协议而不是 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-315">In the following example, if you have SSL installed, use the HTTPS protocol instead of the HTTP protocol.</span></span> <span data-ttu-id="e0ee1-316">_ServerName_替换为您使用的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-316">Replace  _ServerName_ with the name of the server that you are using.</span></span> <span data-ttu-id="e0ee1-317">_ProjectServerName_替换为 project server 网站，如 PWA 的虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-317">Replace  _ProjectServerName_ with the virtual directory name of your project server site, such as PWA.</span></span> 
  
```cs
const string PROJECT_SERVER_URI = "https://ServerName/ProjectServerName/";
```

<span data-ttu-id="e0ee1-318">代码示例顶部记录了必须更改的其他变量。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-318">Any other variables that you must change are noted at the top of the code example.</span></span>
  
## <a name="verifying-the-results"></a><span data-ttu-id="e0ee1-319">验证结果</span><span class="sxs-lookup"><span data-stu-id="e0ee1-319">Verifying the results</span></span>
<span data-ttu-id="e0ee1-320"><a name="pj15_PrerequisitesWCF_Verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-320"></span></span>

<span data-ttu-id="e0ee1-321">获取和解释结果的代码示例并不总是变得非常简单。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-321">Getting and interpreting results from a code sample is not always straightforward.</span></span> <span data-ttu-id="e0ee1-322">例如，如果您创建的项目时，才可以显示在 Project Web App 中的项目中心页上必须发布项目。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-322">For example, if you create a project, you must publish the project before it can appear on the Project Center page in Project Web App.</span></span>
  
<span data-ttu-id="e0ee1-323">可以通过多种方式验证代码示例结果，例如：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-323">You can verify code sample results in several ways, for example:</span></span>
  
- <span data-ttu-id="e0ee1-324">使用 Project Professional 2013 客户端从 Project Server 计算机中，打开项目并查看所需的项。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-324">Use the Project Professional 2013 client to open the project from the Project Server computer, and view the items that you want.</span></span>
    
- <span data-ttu-id="e0ee1-325">在 Project Web App 的项目中心页上查看已发布的项目 ( `https://ServerName/ProjectServerName/projects.aspx`)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-325">View published projects on the Project Center page of Project Web App ( `https://ServerName/ProjectServerName/projects.aspx`).</span></span>
    
- <span data-ttu-id="e0ee1-326">在 Project Web App 中查看队列日志。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-326">View the Queue log in Project Web App.</span></span> <span data-ttu-id="e0ee1-327">打开服务器设置页 （右上角选择**设置**图标），然后选择下**个人设置**部分**我的排队作业**( `https://ServerName/ProjectServerName/MyJobs.aspx`)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-327">Open the Server Settings page (choose the **Settings** icon in the top-right corner), and then choose **My Queued Jobs** under the **Personal Settings** section (  `https://ServerName/ProjectServerName/MyJobs.aspx`).</span></span> <span data-ttu-id="e0ee1-328">在**视图**下拉列表中，您可以按作业状态排序。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-328">In the **View** drop-down list, you can sort by the job status.</span></span> <span data-ttu-id="e0ee1-329">**正在进行和过去一周的失败作业**的默认状态。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-329">The default status is **In Progress and Failed Jobs in the Past Week**.</span></span> 
    
- <span data-ttu-id="e0ee1-330">使用 Project Web App 中的服务器设置页 ( `https://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`) 来管理所有队列作业和删除或强制签入企业对象。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-330">Use the Server Settings page in Project Web App ( `https://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`) to manage all queue jobs and delete or force check-in enterprise objects.</span></span> <span data-ttu-id="e0ee1-331">您必须具有管理权限才能访问这些服务器设置页上的链接。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-331">You must have administrative permissions to access those links on the Server Settings page.</span></span>
    
- <span data-ttu-id="e0ee1-p158">使用“Microsoft SQL Server Management Studio”\*\*\*\* 运行针对 Project Server 数据库的表的查询。例如，使用以下查询选择 MSP_WORKFLOW_STAGE_PDPS 表的前 200 行来显示有关工作流容器中项目详细信息页 (PDP) 的信息。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-p158">Use **Microsoft SQL Server Management Studio** to run a query on a table of a Project Server database. For example, use the following query to select the top 200 rows of the MSP_WORKFLOW_STAGE_PDPS table to show information about the project detail pages (PDPs) in workflow stages.</span></span> 
    
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

## <a name="cleaning-up"></a><span data-ttu-id="e0ee1-334">清理</span><span class="sxs-lookup"><span data-stu-id="e0ee1-334">Cleaning up</span></span>
<span data-ttu-id="e0ee1-335"><a name="pj15_PrerequisitesWCF_Cleanup"> </a></span><span class="sxs-lookup"><span data-stu-id="e0ee1-335"></span></span>

<span data-ttu-id="e0ee1-336">测试某些代码示例后，没有企业对象和设置应删除或重置。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-336">After you test some code samples, there are enterprise objects and settings that should be deleted or reset.</span></span> <span data-ttu-id="e0ee1-337">可以使用 Project Web App 中的服务器设置页来管理企业数据 ( `https://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`)。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-337">You can use the Server Settings page in Project Web App to manage enterprise data ( `https://ServerName/ProjectServerName/_layouts/15/pwa/admin/admin.aspx`).</span></span> <span data-ttu-id="e0ee1-338">在服务器设置页上的链接，可以删除旧项目、 强制签入项目、 管理作业队列的所有用户和执行其他管理任务。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-338">Links on the Server Settings page enable you to delete old items, force check-in projects, manage the job queue for all users, and perform other administrative tasks.</span></span>
  
<span data-ttu-id="e0ee1-339">下面是“服务器设置”页上的部分链接，可用于在运行代码示例之后进行常规清理活动：</span><span class="sxs-lookup"><span data-stu-id="e0ee1-339">Following are some of the links on the Server Settings page to use for typical cleanup activities after running code samples:</span></span>
  
- <span data-ttu-id="e0ee1-340">**企业自定义域和查阅表格**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-340">**Enterprise Custom Fields and Lookup Tables**</span></span>
    
- <span data-ttu-id="e0ee1-341">**管理队列作业**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-341">**Manage Queue Jobs**</span></span>
    
- <span data-ttu-id="e0ee1-342">**删除企业对象**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-342">**Delete Enterprise Objects**</span></span>
    
- <span data-ttu-id="e0ee1-343">**强制签入企业对象**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-343">**Force Check-in Enterprise Objects**</span></span>
    
- <span data-ttu-id="e0ee1-344">**企业项目类型**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-344">**Enterprise Project Types**</span></span>
    
- <span data-ttu-id="e0ee1-345">**工作流阶段**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-345">**Workflow Phases**</span></span>
    
- <span data-ttu-id="e0ee1-346">**工作流阶段**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-346">**Workflow Stages**</span></span>
    
- <span data-ttu-id="e0ee1-347">**项目详细信息页**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-347">**Project Detail Pages**</span></span>
    
- <span data-ttu-id="e0ee1-348">**时间报告阶段**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-348">**Time Reporting Periods**</span></span>
    
- <span data-ttu-id="e0ee1-349">**时间表设置和默认值**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-349">**Timesheet Settings and Defaults**</span></span>
    
- <span data-ttu-id="e0ee1-350">**行分类**</span><span class="sxs-lookup"><span data-stu-id="e0ee1-350">**Line Classifications**</span></span>
    
<span data-ttu-id="e0ee1-351">通过 SharePoint Server 2013 的每个 Project Web App 实例，而不是按特定的 Project Web App 服务器设置页管理其他设置。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-351">Additional settings are managed by SharePoint Server 2013 for each Project Web App instance, rather than by a specific Project Web App Server Settings page.</span></span> <span data-ttu-id="e0ee1-352">在 SharePoint 管理中心应用程序中，选择**应用程序的常规设置**，选择**管理** **Project Server 设置**下，然后选择服务器设置页上的下拉列表中的 Project Web App 实例.</span><span class="sxs-lookup"><span data-stu-id="e0ee1-352">In the SharePoint Central Administration application, choose **General Application Settings**, choose **Manage** under **Project Server Settings**, and then choose the Project Web App instance in the drop-down list on the Server Settings page.</span></span> <span data-ttu-id="e0ee1-353">例如，选择**服务器端事件处理程序**添加或删除所选的 Project Web App 实例的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e0ee1-353">For example, choose **Server Side Event Handlers** to add or delete event handlers for the selected Project Web App instance.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e0ee1-354">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ee1-354">See also</span></span>

- [<span data-ttu-id="e0ee1-355">在项目中的基于 ASMX 的代码示例的先决条件</span><span class="sxs-lookup"><span data-stu-id="e0ee1-355">Prerequisites for ASMX-based code samples in Project</span></span>](prerequisites-for-asmx-based-code-samples-in-project.md)   
- [<span data-ttu-id="e0ee1-356">演练： 开发使用 WCF 的 PSI 应用程序</span><span class="sxs-lookup"><span data-stu-id="e0ee1-356">Walkthrough: Developing PSI applications using WCF</span></span>](https://msdn.microsoft.com/library/65707234-c3da-44e4-8364-32a6be28f645%28Office.15%29.aspx)   
- [<span data-ttu-id="e0ee1-357">使用 WCF 模拟</span><span class="sxs-lookup"><span data-stu-id="e0ee1-357">Use Impersonation with WCF</span></span>](https://msdn.microsoft.com/library/e3597901-2f02-44a2-8076-d32aae540b38%28Office.15%29.aspx)  
- [<span data-ttu-id="e0ee1-358">项目 PSI 参考概述</span><span class="sxs-lookup"><span data-stu-id="e0ee1-358">Project PSI reference overview</span></span>](project-psi-reference-overview.md) 
- [<span data-ttu-id="e0ee1-359">SharePoint 开发中心</span><span class="sxs-lookup"><span data-stu-id="e0ee1-359">SharePoint Developer Center</span></span>](https://msdn.microsoft.com/sharepoint/default.aspx)
    

