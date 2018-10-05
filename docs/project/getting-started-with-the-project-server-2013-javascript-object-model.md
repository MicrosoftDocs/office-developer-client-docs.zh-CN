---
title: Project Server 2013 JavaScript 对象模型入门
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 30dc3194-7480-4e7c-b731-4a171d652ee0
description: 在 Project Server 2013 中的 JavaScript 对象模型可在 Project Online 的移动和本地开发。 本主题简要概述了 JavaScript 对象模型，然后介绍如何创建检索和循环使用 JavaScript 对象模型的项目的应用程序页。
ms.openlocfilehash: ec8a10e987276807dc4648bd8948b2285f76fd37
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388208"
---
# <a name="getting-started-with-the-project-server-2013-javascript-object-model"></a><span data-ttu-id="0e8b4-104">Project Server 2013 JavaScript 对象模型入门</span><span class="sxs-lookup"><span data-stu-id="0e8b4-104">Getting started with the Project Server 2013 JavaScript object model</span></span>

<span data-ttu-id="0e8b4-105">在 Project Server 2013 中的 JavaScript 对象模型可在 Project Online 的移动和本地开发。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-105">In Project Server 2013, the JavaScript object model can be used in Project Online, mobile, and on-premise development.</span></span> <span data-ttu-id="0e8b4-106">本主题简要概述了 JavaScript 对象模型，然后介绍如何创建检索和循环使用 JavaScript 对象模型的项目的应用程序页。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-106">This topic provides a brief overview of the JavaScript object model and then describes how to create an application page that retrieves and iterates through projects by using the JavaScript object model.</span></span>
  
## <a name="using-the-project-server-javascript-object-model"></a><span data-ttu-id="0e8b4-107">使用 Project Server JavaScript 对象模型</span><span class="sxs-lookup"><span data-stu-id="0e8b4-107">Using the Project Server JavaScript object model</span></span>
<span data-ttu-id="0e8b4-108"><a name="pj15_GetStartedJSOM_UseJSOM"> </a></span><span class="sxs-lookup"><span data-stu-id="0e8b4-108"></span></span>

<span data-ttu-id="0e8b4-109">使用 JavaScript 对象模型是创建运行客户端 （如相对需要远程运行托管客户端代码） 的应用程序的好方法。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-109">Using the JavaScript object model is a great way to create an app that runs client-side (as opposed to managed client code which needs to run remotely).</span></span> <span data-ttu-id="0e8b4-110">应用程序可以使用 JavaScript 对象模型来检索或更改通过发送到服务器的异步调用的对象。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-110">Apps can use the JavaScript object model to retrieve or change objects by sending asynchronous calls to the server.</span></span> <span data-ttu-id="0e8b4-111">使用 JavaScript 对象模型的应用程序通常是作为自定义 SharePoint 加载项、 应用程序页和 Web 部件部署。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-111">Apps that use the JavaScript object model are typically deployed as custom SharePoint Add-ins, application pages, and Web Parts.</span></span> <span data-ttu-id="0e8b4-112">有关详细信息，请参阅在[主机 web、 外接程序 web 和 SharePoint 组件在 SharePoint 2013 中](https://msdn.microsoft.com/library/b791cdf5-8aa2-47fa-bc4c-aee437354759%28Office.15%29.aspx)的"类型的 SharePoint 组件可在 SharePoint 相关应用程序"。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-112">For more information, see "Types of SharePoint components that can be in an app for SharePoint" in [Host webs, add-in webs, and SharePoint components in SharePoint 2013](https://msdn.microsoft.com/library/b791cdf5-8aa2-47fa-bc4c-aee437354759%28Office.15%29.aspx).</span></span>
  
<span data-ttu-id="0e8b4-113">JavaScript 对象模型实现的主要功能的 Project Server 2013，但 JavaScript 对象模型和服务器对象模型没有一对一的奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-113">The JavaScript object model implements the main functionality of Project Server 2013, but the JavaScript object model and the server object model do not have one-to-one parity.</span></span> <span data-ttu-id="0e8b4-114">JavaScript 对象模型的入口点是**ProjectContext**对象，它代表 Project Server 2013 的客户端上下文，并提供对服务器内容和功能的访问。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-114">The entry point to the JavaScript object model is the **ProjectContext** object, which represents the client context for Project Server 2013 and provides access to server content and functionality.</span></span> <span data-ttu-id="0e8b4-115">Project Server 2013 JavaScript 对象模型在位于默认路径中的 PS.js 文件中定义`%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS`应用程序服务器上。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-115">The JavaScript object model for Project Server 2013 is defined in the PS.js file, which is located in the default path  `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS` on the application server.</span></span> <span data-ttu-id="0e8b4-116">Project Server 2013 还会安装 PS.为相同位置中的 Debug.js 文件。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-116">Project Server 2013 also installs the PS.Debug.js file in the same location.</span></span> <span data-ttu-id="0e8b4-117">PS.Debug.js 是提供 IntelliSense 信息的 PS.js unminified 的版本。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-117">PS.Debug.js is an unminified version of PS.js that provides IntelliSense information.</span></span> 
  
<span data-ttu-id="0e8b4-118">JavaScript 对象模型允许表单身份验证，并为当前用户的所有请求人均通过身份都验证。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-118">The JavaScript object model allows Forms authentication, and all requests are authenticated as the current user.</span></span> <span data-ttu-id="0e8b4-119">有关安全性和设计自定义应用程序和解决方案的其他注意事项的详细信息，请参阅[身份验证、 授权和 SharePoint 2013 中的安全性](https://msdn.microsoft.com/library/8734790c-eb75-4d78-9604-7cc23b33b693%28Office.15%29.aspx)、[的 SharePoint 外接程序体系结构和开发的重要方面横向](https://msdn.microsoft.com/library/ae96572b-8f06-4fd3-854f-fc312f7f2d88%28Office.15%29.aspx)，并[与 SharePoint 解决方案比较的 SharePoint 加载项](https://msdn.microsoft.com/library/0e9efadb-aaf2-4c0d-afd5-d6cf25c4e7a8%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-119">For more information about security and other considerations for designing custom apps and solutions, see [Authentication, authorization, and security in SharePoint 2013](https://msdn.microsoft.com/library/8734790c-eb75-4d78-9604-7cc23b33b693%28Office.15%29.aspx), [Important aspects of the SharePoint Add-in architecture and development landscape](https://msdn.microsoft.com/library/ae96572b-8f06-4fd3-854f-fc312f7f2d88%28Office.15%29.aspx), and [SharePoint Add-ins compared with SharePoint solutions](https://msdn.microsoft.com/library/0e9efadb-aaf2-4c0d-afd5-d6cf25c4e7a8%28Office.15%29.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e8b4-120">若要从 SharePoint 网站远程访问数据，SharePoint 2013 提供了使您可以进行客户端跨域调用的跨域库。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-120">To access data from a SharePoint site remotely, SharePoint 2013 provides a cross-domain library that enables you to make client-side cross-domain calls.</span></span> <span data-ttu-id="0e8b4-121">有关详细信息，请参阅[从加载项使用跨域库访问 SharePoint 2013 数据](https://msdn.microsoft.com/library/bc37ff5c-1285-40af-98ae-01286696242d%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-121">For more information, see [Access SharePoint 2013 data from add-ins using the cross-domain library](https://msdn.microsoft.com/library/bc37ff5c-1285-40af-98ae-01286696242d%28Office.15%29.aspx).</span></span> 
  
<span data-ttu-id="0e8b4-122">许多概念和 Project Server 2013 使用 JavaScript 对象模型的过程类似于那些相关的客户端对象模型中。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-122">Many concepts and processes for using the JavaScript object model for Project Server 2013 resemble those in related client object models.</span></span> <span data-ttu-id="0e8b4-123">有关 Project Server 2013 托管客户端对象模型的详细信息，请参阅**Microsoft.ProjectServer.Client**。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-123">For more information about the Project Server 2013 managed client object model, see **Microsoft.ProjectServer.Client**.</span></span> <span data-ttu-id="0e8b4-124">有关 SharePoint 2013JavaScript 对象模型和托管客户端对象模型的详细信息，请参阅[完成基本操作使用 SharePoint 2013 中的 JavaScript 库代码](https://msdn.microsoft.com/library/29089af8-dbc0-49b7-a1a0-9e311f49c826%28Office.15%29.aspx)和[完成基本操作使用 SharePoint 2013 客户端库代码](https://msdn.microsoft.com/library/5a69c9e3-73bf-4ed5-bc19-182056bdb394%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-124">For more information about the SharePoint 2013JavaScript object model and managed client object model, see [Complete basic operations using JavaScript library code in SharePoint 2013](https://msdn.microsoft.com/library/29089af8-dbc0-49b7-a1a0-9e311f49c826%28Office.15%29.aspx) and [Complete basic operations using SharePoint 2013 client library code](https://msdn.microsoft.com/library/5a69c9e3-73bf-4ed5-bc19-182056bdb394%28Office.15%29.aspx).</span></span>
  
## <a name="walkthrough-creating-an-application-page-that-retrieves-and-iterates-through-projects"></a><span data-ttu-id="0e8b4-125">演练：创建可检索和循环访问各个项目的应用程序页</span><span class="sxs-lookup"><span data-stu-id="0e8b4-125">Walkthrough: Creating an application page that retrieves and iterates through projects</span></span>
<span data-ttu-id="0e8b4-126"><a name="pj15_GetStartedJSOM_UseJSOM"> </a></span><span class="sxs-lookup"><span data-stu-id="0e8b4-126"></span></span>

<span data-ttu-id="0e8b4-127">了解如何创建可显示网站中每个已发布项目的 ID、名称和创建日期的应用程序页。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-127">Learn how to create an application page that displays the ID, name, and created date of each published project in a site.</span></span>
  
### <a name="prerequisites-for-creating-an-application-page-that-retrieves-and-iterates-through-projects"></a><span data-ttu-id="0e8b4-128">创建可检索和循环访问各个项目的应用程序的先决条件</span><span class="sxs-lookup"><span data-stu-id="0e8b4-128">Prerequisites for creating an application page that retrieves and iterates through projects</span></span>
<span data-ttu-id="0e8b4-129"><a name="pj15_GetStartedJSOM_Prereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="0e8b4-129"></span></span>

<span data-ttu-id="0e8b4-130">若要开发本主题中描述的应用程序页，您必须安装和配置以下产品：</span><span class="sxs-lookup"><span data-stu-id="0e8b4-130">To develop the application page that is described in this topic, you must install and configure the following products:</span></span>
  
- <span data-ttu-id="0e8b4-131">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e8b4-131">SharePoint Server 2013</span></span>
- <span data-ttu-id="0e8b4-132">至少一个已发布项目与 project Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e8b4-132">Project Server 2013 with at least one published project</span></span>
- <span data-ttu-id="0e8b4-133">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="0e8b4-133">Visual Studio 2012</span></span>
- <span data-ttu-id="0e8b4-134">Visual Studio 2012 Office 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="0e8b4-134">Office Developer Tools for Visual Studio 2012</span></span>
    
<span data-ttu-id="0e8b4-135">您还必须具有将扩展部署到 SharePoint Server 2013 和检索项目的权限。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-135">You must also have permissions to deploy the extension to SharePoint Server 2013 and to retrieve projects.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e8b4-136">这些说明假定您在运行 Project Server 2013 的计算机上开发。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-136">These instructions assume that you are developing on the computer that is running Project Server 2013.</span></span> 
  
### <a name="creating-the-application-page-in-visual-studio-2012"></a><span data-ttu-id="0e8b4-137">在 Visual Studio 2012 中创建的应用程序页</span><span class="sxs-lookup"><span data-stu-id="0e8b4-137">Creating the application page in Visual Studio 2012</span></span>
<span data-ttu-id="0e8b4-138"><a name="pj15_GetStartedJSOM_CreateVS"> </a></span><span class="sxs-lookup"><span data-stu-id="0e8b4-138"></span></span>

<span data-ttu-id="0e8b4-p108">以下步骤创建了一个 SharePoint 项目和一个包含表和标签的应用程序页。表显示了有关项目的信息，标签显示了错误消息。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-p108">The following steps create a SharePoint project and an application page that contains a table and label. The table displays information about the projects and the label displays error messages.</span></span>
  
1. <span data-ttu-id="0e8b4-141">在计算机上运行 Project Server 2013，以管理员身份运行 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-141">On the computer that is running Project Server 2013, run Visual Studio 2012 as an administrator.</span></span>
    
2. <span data-ttu-id="0e8b4-142">创建一个空的 SharePoint 2013 项目，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e8b4-142">Create an empty SharePoint 2013 project, as follows:</span></span>
    
    1. <span data-ttu-id="0e8b4-143">在"新建项目"对话框中，从对话框顶部的下拉列表中选择".NET Framework 4.5"。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-143">In the **New Project** dialog box, choose **.NET Framework 4.5** from the drop-down list at the top of the dialog box.</span></span> 
        
    2. <span data-ttu-id="0e8b4-144">在模板类别列表中，选择“Office SharePoint”\*\*\*\* 类别，然后选择“SharePoint 2013 项目”\*\*\*\* 模板。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-144">In the list of template categories, choose the **Office SharePoint** category, and then choose the **SharePoint 2013 Project** template.</span></span> 
        
    3. <span data-ttu-id="0e8b4-145">将项目命名为 GetProjectsJSOM，，然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-145">Name the project GetProjectsJSOM, and then choose the **OK** button.</span></span> 
        
    4. <span data-ttu-id="0e8b4-146">在“SharePoint 自定义向导”\*\*\*\* 对话框中，选择“部署为场解决方案”\*\*\*\*，然后选择“确定”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-146">In the **SharePoint Customization Wizard** dialog box, choose **Deploy as a farm solution**, and then choose the **OK** button.</span></span> 
    
3. <span data-ttu-id="0e8b4-147">在解决方案资源管理器中编辑**ProjectsJSOM**项目与 Project Web App 实例的 URL 匹配的**Site URL**属性的值 (例如， `https://ServerName/PWA`)。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-147">In Solution Explorer, edit the value of the **Site URL** property for the **ProjectsJSOM** project to match the URL of the Project Web App instance (for example,  `https://ServerName/PWA`).</span></span>
    
4. <span data-ttu-id="0e8b4-148">打开“GetProjectsJSOM”\*\*\*\* 项目的快捷菜单，然后添加 SharePoint“Layouts”映射文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-148">Open the shortcut menu for the **GetProjectsJSOM** project, and then add a SharePoint "Layouts" mapped folder.</span></span> 
    
5. <span data-ttu-id="0e8b4-149">在**Layouts**文件夹中，打开**GetProjectsJSOM**文件夹的快捷菜单，然后添加一个新的名为 ProjectsList.aspx 的 SharePoint 应用程序页。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-149">In the **Layouts** folder, open the shortcut menu for the **GetProjectsJSOM** folder, and then add a new SharePoint application page named ProjectsList.aspx.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="0e8b4-150">本示例不使用的应用程序页上的 Visual Studio 2012 创建的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-150">This example does not use the code-behind file that Visual Studio 2012 creates for the application page.</span></span> 
  
6. <span data-ttu-id="0e8b4-151">打开 **ProjectsList.aspx** 页的快捷菜单，然后选择“设置为启动项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-151">Open the shortcut menu for the **ProjectsList.aspx** page and choose **Set as Startup Item**.</span></span>
    
7. <span data-ttu-id="0e8b4-152">在 **ProjectsList.aspx** 页的标记中，在“主要”**asp:Content** 标记中定义一个表和一个消息占位符，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-152">In the markup for the **ProjectsList.aspx** page, define a table and a message placeholder inside the "Main" **asp:Content** tags, as follows.</span></span> 
    
    ```HTML
    <table width="100%" id="tblProjects">
        <tr id="headerRow">
            <th width="25%" align="left">Project name</th>
            <th width="25%" align="left">Created date</th>
            <th width="50%" align="left">Project ID</th>
        </tr>
    </table>
    <div id="divMessage">
        <br/>
        <span id="spanMessage" style="color: #FF0000;"></span>
    </div>
    ```

### <a name="retrieving-the-projects-collection"></a><span data-ttu-id="0e8b4-153">检索项目集合</span><span class="sxs-lookup"><span data-stu-id="0e8b4-153">Retrieving the projects collection</span></span>
<span data-ttu-id="0e8b4-154"><a name="pj15_GetStartedJSOM_RetrieveProjs"> </a></span><span class="sxs-lookup"><span data-stu-id="0e8b4-154"></span></span>

<span data-ttu-id="0e8b4-155">可通过以下步骤检索和初始化项目集合。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-155">The following steps retrieve and initialize the projects collection.</span></span>
  
1. <span data-ttu-id="0e8b4-156">在结束 **div** 标记的后面，添加一个引用 PS.js 文件的 **SharePoint:ScriptLink** 标记，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-156">After the closing **div** tag, add a **SharePoint:ScriptLink** tag that references the PS.js file, as follows.</span></span> 
    
   ```HTML
    <SharePoint:ScriptLink name="PS.js" runat="server" ondemand="false" localizable="false" loadafterui="true" />
   ```

2. <span data-ttu-id="0e8b4-157">在 **SharePoint:ScriptLink** 标记的下方，添加 **script** 标记，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-157">Below the **SharePoint:ScriptLink** tag, add **script** tags, as follows.</span></span> 
    
   ```HTML
    <script type="text/javascript">
        // Paste the remaining code snippets here, in the order that they are presented.
    </script>
   ```

3. <span data-ttu-id="0e8b4-158">声明一个全局变量以存储项目集合，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-158">Declare a global variable to store the projects collection, as follows.</span></span>
    
   ```js
   var projects;
   ```

4. <span data-ttu-id="0e8b4-159">调用 **SP.SOD.executeOrDelayUntilScriptLoaded** 方法以确保 PS.js 文件在您的自定义代码运行之前加载。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-159">Call the **SP.SOD.executeOrDelayUntilScriptLoaded** method to ensure that the PS.js file is loaded before your custom code runs.</span></span> 
    
   ```js
   SP.SOD.executeOrDelayUntilScriptLoaded(GetProjects, "PS.js");
   ```

5. <span data-ttu-id="0e8b4-160">添加一个将连接到当前上下文并检索项目集合的函数，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-160">Add a function that connects to the current context and retrieves the projects collection, as follows.</span></span>
    
   ```js
    function GetProjects() {
        // Initialize the current client context.
        var projContext = PS.ProjectContext.get_current();
        // Get the projects collection.
        projects = projContext.get_projects();
        // Register the request that you want to run on the server.
        // This call includes an optional "Include" parameter to request only the
        // Name, CreatedDate, and Id properties of the projects in the collection.
        projContext.load(projects, 'Include(Name, CreatedDate, Id)');
        // Run the request on the server.
        projContext.executeQueryAsync(onQuerySucceeded, onQueryFailed);
    }
   ```

   <span data-ttu-id="0e8b4-p109">通过上下文检索到的一些客户端对象在初始化之前不包含数据；也就是说，在初始化对象之前，您无法访问对象的属性值。此外，对于类型 **ValueObject** 的属性，您必须先显式请求该属性，然后才能访问其值。（如果您尝试在属性初始化之前访问它，则将收到一个 **PropertyOrFieldNotInitializedException** 异常。）</span><span class="sxs-lookup"><span data-stu-id="0e8b4-p109">Some client objects that you retrieve through the context contain no data until they are initialized; that is, you cannot access the property values of the object until the object is initialized. Moreover, for properties of type **ValueObject**, you must explicitly request the property before you can access its value. (If you try to access a property before it is initialized, you receive a **PropertyOrFieldNotInitializedException** exception.)</span></span> 
    
   <span data-ttu-id="0e8b4-164">若要初始化对象，您可以依次调用 **load** 方法（或 **loadQuery** 方法）和 **executeQueryAsync** 方法。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-164">To initialize an object, you call the **load** method (or the **loadQuery** method) and then the **executeQueryAsync** method.</span></span> 
    
   - <span data-ttu-id="0e8b4-p110">调用 **load** 函数或 **loadQuery** 函数将注册要在服务器上运行的请求。您将传入一个表示要检索的对象的参数。如果您使用的是 **ValueObject** 属性，则还要在参数中请求该属性。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-p110">Calling the **load** function or the **loadQuery** function registers a request that you want to run on the server. You pass in a parameter that represents the object that you want to retrieve. If you are working with a **ValueObject** property, then you also request the property in the parameter.</span></span> 
    
   - <span data-ttu-id="0e8b4-p111">调用 **executeQueryAsync** 函数会通过异步方式向服务器发送查询请求。您将传入一个成功回调函数和一个失败回调函数，在收到服务器响应时将调用它们。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-p111">Calling the **executeQueryAsync** function sends the query request to the server asynchronously. You pass in a success callback function and a failure callback function to invoke when the server response is received.</span></span> 
    
   <span data-ttu-id="0e8b4-p112">为了减少网络流量，在您调用 **load** 函数时仅请求要使用的属性。此外，如果您使用了多个对象，则在调用 **executeQueryAsync** 函数之前，将针对 **load** 函数的多个调用进行分组（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-p112">To reduce network traffic, request only the properties that you want to work with when you call the **load** function. In addition, if you are working with multiple objects, group multiple calls to the **load** function before you call the **executeQueryAsync** function when it is possible.</span></span> 
    
### <a name="iterating-through-the-projects-collection"></a><span data-ttu-id="0e8b4-172">循环访问项目集合</span><span class="sxs-lookup"><span data-stu-id="0e8b4-172">Iterating through the projects collection</span></span>
<span data-ttu-id="0e8b4-173"><a name="pj15_GetStartedJSOM_IterateProjs"> </a></span><span class="sxs-lookup"><span data-stu-id="0e8b4-173"></span></span>

<span data-ttu-id="0e8b4-174">可通过以下步骤循环访问项目集合（如果服务器调用成功）或呈现错误消息（如果调用失败）。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-174">The following steps iterate through the projects collection (if the server call is successful) or render an error message (if the call fails).</span></span>
  
1. <span data-ttu-id="0e8b4-175">添加一个可循环访问项目集合的成功回调函数，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-175">Add a success callback function that iterates through the projects collection, as follows.</span></span>
    
   ```js
    function onQuerySucceeded(sender, args) {
        // Get the enumerator and iterate through the collection.
        var projectEnumerator = projects.getEnumerator();
        while (projectEnumerator.moveNext()) {
            var project = projectEnumerator.get_current();
            // Create the row for the project's information.
            var row = tblProjects.insertRow();
            // Insert cells for the Id, Name, and CreatedDate properties.
            row.insertCell().innerText = project.get_name();
            row.insertCell().innerText = project.get_createdDate();
            row.insertCell().innerText = project.get_id();
        }
    }
   ```

2. <span data-ttu-id="0e8b4-176">添加一个可呈现错误消息的失败回调函数，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-176">Add a failure callback function that renders an error message, as follows.</span></span>
    
    ```js
    function onQueryFailed(sender, args) {
        $get("spanMessage").innerText = 'Request failed: ' + args.get_message();
    }
    ```

3. <span data-ttu-id="0e8b4-p113">若要测试应用程序页，请在菜单栏上选择“调试”\*\*\*\* 和“启动调试”\*\*\*\*。如果系统提示您修改 web.config 文件，请选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-p113">To test the application page, on the menu bar, choose **Debug**, **Start Debugging**. If you are prompted to modify the web.config file, choose **OK**.</span></span>

<span data-ttu-id="0e8b4-179"><a name="pj15_GetStartedJSOM_CompleteExample"> </a></span><span class="sxs-lookup"><span data-stu-id="0e8b4-179"></span></span>

## <a name="complete-code-example"></a><span data-ttu-id="0e8b4-180">完整的代码示例</span><span class="sxs-lookup"><span data-stu-id="0e8b4-180">Complete code example</span></span>

<span data-ttu-id="0e8b4-181">以下是 ProjectsList.aspx 文件中的完整代码。</span><span class="sxs-lookup"><span data-stu-id="0e8b4-181">Following is the complete code from the ProjectsList.aspx file.</span></span>
  
```js
<%@ Assembly Name="$SharePoint.Project.AssemblyFullName$" %>
<%@ Import Namespace="Microsoft.SharePoint.ApplicationPages" %>
<%@ Register Tagprefix="SharePoint" Namespace="Microsoft.SharePoint.WebControls" Assembly="Microsoft.SharePoint, Version=15.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
<%@ Register Tagprefix="Utilities" Namespace="Microsoft.SharePoint.Utilities" Assembly="Microsoft.SharePoint, Version=15.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
<%@ Register Tagprefix="asp" Namespace="System.Web.UI" Assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" %>
<%@ Import Namespace="Microsoft.SharePoint" %>
<%@ Assembly Name="Microsoft.Web.CommandUI, Version=15.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="ProjectsList.aspx.cs" Inherits="GetProjectsJSOM.Layouts.GetProjectsJSOM.ProjectsList" DynamicMasterPageFile="~masterurl/default.master" %>
<asp:Content ID="PageHead" ContentPlaceHolderID="PlaceHolderAdditionalPageHead" runat="server">
</asp:Content>
<asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">
    <table width="100%" id="tblProjects">
    <tr id="headerRow">
        <th width="25%" align="left">Project name</th>
        <th width="25%" align="left">Created date</th>
        <th width="50%" align="left">Project ID</th>
    </tr>
</table>
<div id="divMessage">
    <br/>
    <span id="spanMessage" style="color: #FF0000;"></span>
</div>
<SharePoint:ScriptLink name="PS.js" runat="server" ondemand="false" localizable="false" loadafterui="true" />
<script type="text/javascript">
    // Declare a variable to store the published projects that exist
    // in the current context.
    var projects;
    // Ensure that the PS.js file is loaded before your custom code runs.
    SP.SOD.executeOrDelayUntilScriptLoaded(GetProjects, "PS.js");
    // Get the projects collection.
    function GetProjects() {
        // Initialize the current client context.
        var projContext = PS.ProjectContext.get_current();
        // Get the projects collection.
        projects = projContext.get_projects();
        // Register the request that you want to run on the server.
        // This call includes an optional "Include" parameter to request only the
        // Name, CreatedDate, and Id properties of the projects in the collection.
        projContext.load(projects, 'Include(Name, CreatedDate, Id)');
        // Run the request on the server.
        projContext.executeQueryAsync(onQuerySucceeded, onQueryFailed);
    }
    function onQuerySucceeded(sender, args) {
        // Get the enumerator and iterate through the collection.
        var projectEnumerator = projects.getEnumerator();
        while (projectEnumerator.moveNext()) {
            var project = projectEnumerator.get_current();
            // Create the row for the project's information.
            var row = tblProjects.insertRow();
            // Insert cells for the Id, Name, and CreatedDate properties.
            row.insertCell().innerText = project.get_name();
            row.insertCell().innerText = project.get_createdDate();
            row.insertCell().innerText = project.get_id();
        }
    }
    function onQueryFailed(sender, args) {
        $get("spanMessage").innerText = 'Request failed: ' + args.get_message();
    }
</script>
</asp:Content>
<asp:Content ID="PageTitle" ContentPlaceHolderID="PlaceHolderPageTitle" runat="server">
Application Page
</asp:Content>
<asp:Content ID="PageTitleInTitleArea" ContentPlaceHolderID="PlaceHolderPageTitleInTitleArea" runat="server" >
My Application Page
</asp:Content>

```

<span data-ttu-id="0e8b4-182"><a name="pj15_GetStartedJSOM_AR"> </a></span><span class="sxs-lookup"><span data-stu-id="0e8b4-182"></span></span>

## <a name="see-also"></a><span data-ttu-id="0e8b4-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e8b4-183">See also</span></span>

- [<span data-ttu-id="0e8b4-184">创建、 检索、 更新和删除项目使用 Project Server JavaScript 对象模型</span><span class="sxs-lookup"><span data-stu-id="0e8b4-184">Create, retrieve, update, and delete projects by using the Project Server JavaScript object model</span></span>](create-retrieve-update-delete-projects-using-project-server-javascript.md)  
- [<span data-ttu-id="0e8b4-185">Project 2013 的客户端对象模型 (CSOM)</span><span class="sxs-lookup"><span data-stu-id="0e8b4-185">Client-side object model (CSOM) for Project 2013</span></span>](client-side-object-model-csom-for-project-2013.md)
- [<span data-ttu-id="0e8b4-186">Project Server CSOM 和 .NET 入门</span><span class="sxs-lookup"><span data-stu-id="0e8b4-186">Getting started with the Project Server CSOM and .NET</span></span>](getting-started-with-the-project-server-csom-and-net.md)
    

