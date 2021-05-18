---
title: 使用 Project Server JavaScript 创建、检索、更新和删除项目
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6b690938-05bc-46a3-a40e-30f081403767
description: 获取当前的 ProjectContext 实例;检索并访问服务器上已发布项目的集合;使用 Project Server JavaScript 对象模型创建、检索、签出和删除项目;并更改项目的属性。
ms.openlocfilehash: 10dac7edfa3e84cebfd0585bc8c4bff1ea22ea44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322664"
---
# <a name="create-retrieve-update-and-delete-projects-using-project-server-javascript"></a><span data-ttu-id="995fe-103">使用 Project Server JavaScript 创建、检索、更新和删除项目</span><span class="sxs-lookup"><span data-stu-id="995fe-103">Create, retrieve, update, and delete projects using Project Server JavaScript</span></span>

<span data-ttu-id="995fe-104">本文中的方案显示如何获取当前的 **ProjectContext** 实例;检索并访问服务器上已发布项目的集合;使用 Project Server JavaScript 对象模型创建、检索、签出和删除项目;并更改项目的属性。</span><span class="sxs-lookup"><span data-stu-id="995fe-104">The scenarios in this article show how to get the current **ProjectContext** instance; retrieve and iterate through the collection of published projects on the server; create, retrieve, check out, and delete a project by using the Project Server JavaScript object model; and change a project's properties.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="995fe-105">这些方案在 SharePoint 应用程序页的标记中定义自定义代码，但不使用 Visual Studio 2012 为页面创建的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="995fe-105">These scenarios define custom code in the markup of a SharePoint application page but do not use the code-behind file that Visual Studio 2012 creates for the page.</span></span> 
  
## <a name="prerequisites-for-working-with-project-server-2013-projects-in-the-javascript-object-model"></a><span data-ttu-id="995fe-106">在 JavaScript 对象模型中Project Server 2013 项目的先决条件</span><span class="sxs-lookup"><span data-stu-id="995fe-106">Prerequisites for working with Project Server 2013 projects in the JavaScript object model</span></span>

<span data-ttu-id="995fe-107">若要执行本文中介绍的方案，您必须安装并配置下列产品：</span><span class="sxs-lookup"><span data-stu-id="995fe-107">To perform the scenarios that are described in this article, you must install and configure the following products:</span></span>
  
- <span data-ttu-id="995fe-108">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="995fe-108">SharePoint Server 2013</span></span>
- <span data-ttu-id="995fe-109">Project Server 2013</span><span class="sxs-lookup"><span data-stu-id="995fe-109">Project Server 2013</span></span>
- <span data-ttu-id="995fe-110">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="995fe-110">Visual Studio 2012</span></span>
- <span data-ttu-id="995fe-111">Visual Studio 2012 Office 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="995fe-111">Office Developer Tools for Visual Studio 2012</span></span>
    
<span data-ttu-id="995fe-112">还必须有权将扩展部署到 SharePoint Server 2013 并参与项目。</span><span class="sxs-lookup"><span data-stu-id="995fe-112">You must also have permissions to deploy the extension to SharePoint Server 2013 and to contribute to projects.</span></span>
  
> [!NOTE]
> <span data-ttu-id="995fe-113">这些说明假定您是在运行 Project Server 2013 的计算机上进行开发。</span><span class="sxs-lookup"><span data-stu-id="995fe-113">These instructions assume that you are developing on the computer that is running Project Server 2013.</span></span> 
  
## <a name="create-the-visual-studio-solution"></a><span data-ttu-id="995fe-114">创建 Visual Studio 解决方案</span><span class="sxs-lookup"><span data-stu-id="995fe-114">Create the Visual Studio solution</span></span>
<span data-ttu-id="995fe-115"><a name="pj15_CRUDProjectsJSOM_Setup"> </a></span><span class="sxs-lookup"><span data-stu-id="995fe-115"><a name="pj15_CRUDProjectsJSOM_Setup"> </a></span></span>

<span data-ttu-id="995fe-116">以下步骤创建一个 Visual Studio 2012 解决方案，其中包含SharePoint应用程序页。</span><span class="sxs-lookup"><span data-stu-id="995fe-116">The following steps create a Visual Studio 2012 solution that contains a SharePoint project and an application page.</span></span> <span data-ttu-id="995fe-117">应用程序页包含适用于项目的逻辑。</span><span class="sxs-lookup"><span data-stu-id="995fe-117">The page contains the logic for working with projects.</span></span>
  
### <a name="to-create-the-sharepoint-project-in-visual-studio"></a><span data-ttu-id="995fe-118">创建 Visual Studio 中的 SharePoint 项目</span><span class="sxs-lookup"><span data-stu-id="995fe-118">To create the SharePoint project in Visual Studio</span></span>

1. <span data-ttu-id="995fe-119">在运行 Project Server 2013 的计算机上，Visual Studio 2012 运行 2012。</span><span class="sxs-lookup"><span data-stu-id="995fe-119">On the computer that is running Project Server 2013, run Visual Studio 2012 as an administrator.</span></span>
    
2. <span data-ttu-id="995fe-120">在菜单栏上，依次选择"文件"、"新建"、"项目"。</span><span class="sxs-lookup"><span data-stu-id="995fe-120">On the menu bar, choose **File**, **New**, **Project**.</span></span>
    
3. <span data-ttu-id="995fe-121">在“新建项目”对话框中，从对话框顶部的下拉列表中选择“.NET Framework 4.5”。</span><span class="sxs-lookup"><span data-stu-id="995fe-121">In the **New Project** dialog box, choose **.NET Framework 4.5** from the drop-down list at the top of the dialog box.</span></span> 
    
4. <span data-ttu-id="995fe-122">在“Office/SharePoint”模板类别中，选择“SharePoint 解决方案”，然后选择“SharePoint 2013 项目”模板。</span><span class="sxs-lookup"><span data-stu-id="995fe-122">In the **Office/SharePoint** template category, choose **SharePoint Solutions**, and then choose the **SharePoint 2013 Project** template.</span></span> 
    
5. <span data-ttu-id="995fe-123">将项目命名为 ProjectsJSOM，然后选择"确定 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="995fe-123">Name the project ProjectsJSOM, and then choose the **OK** button.</span></span> 
    
6. <span data-ttu-id="995fe-124">在"SharePoint 自定义向导"对话框中，选择"部署场解决方案"，然后选择"完成"按钮。</span><span class="sxs-lookup"><span data-stu-id="995fe-124">In the **SharePoint Customization Wizard** dialog box, choose **Deploy as a farm solution**, and then choose the **Finish** button.</span></span> 
    
7. <span data-ttu-id="995fe-125">编辑 **ProjectsJSOM** 项目的 **Site URL** 属性的值，以匹配 Project Web App 实例的 URL (例如 `https://ServerName/PWA` ，) 。</span><span class="sxs-lookup"><span data-stu-id="995fe-125">Edit the value of the **Site URL** property for the **ProjectsJSOM** project to match the URL of the Project Web App instance (for example,  `https://ServerName/PWA`).</span></span>
    
### <a name="to-create-the-application-page-in-visual-studio"></a><span data-ttu-id="995fe-126">创建 Visual Studio 中的应用程序页</span><span class="sxs-lookup"><span data-stu-id="995fe-126">To create the application page in Visual Studio</span></span>

1. <span data-ttu-id="995fe-127">在“解决方案资源管理器”中，打开 **ProjectsJSOM** 项目的快捷菜单，然后添加“SharePoint 的‘Layouts’映射文件夹”。</span><span class="sxs-lookup"><span data-stu-id="995fe-127">In **Solution Explorer**, open the shortcut menu for the **ProjectsJSOM** project, and then add a SharePoint "Layouts" mapped folder.</span></span> 
    
2. <span data-ttu-id="995fe-128">在 **Layouts** 文件夹中，打开 **ProjectsJSOM** 文件夹的快捷菜单，然后添加一个名为 ProjectsList.aspx SharePoint应用程序页。</span><span class="sxs-lookup"><span data-stu-id="995fe-128">In the **Layouts** folder, open the shortcut menu for the **ProjectsJSOM** folder, and then add a new SharePoint application page named ProjectsList.aspx.</span></span>
    
3. <span data-ttu-id="995fe-129">打开 **ProjectsList.aspx** 页的快捷菜单，然后选择“设置为启动项”。</span><span class="sxs-lookup"><span data-stu-id="995fe-129">Open the shortcut menu for the **ProjectsList.aspx** page and choose **Set as Startup Item**.</span></span>
    
4. <span data-ttu-id="995fe-130">在 **ProjectsList.aspx** 页的标记中，将用户界面控件定义在“Main”**asp:Content** 标记内，如下所示：</span><span class="sxs-lookup"><span data-stu-id="995fe-130">In the markup for the **ProjectsList.aspx** page, define user interface controls inside the "Main" **asp:Content** tags, as follows.</span></span> 
    
   ```HTML
    <table width="100%" id="tblProjects">
        <tr id="headerRow">
            <th width="25%" align="left">Name</th>
            <th width="25%" align="left">Description</th>
            <th width="25%" align="left">Start Date</th>
            <th width="25%" align="left">ID</th>
        </tr>
    </table>
    <textarea id="txtGuid" rows="1" cols="35">Paste the project GUID here.</textarea>
    <button id="btnSend" type="button"></button><br />
    <span id="spanMessage" style="color: #FF0000;"></span>
   ```

   > [!NOTE]
   > <span data-ttu-id="995fe-p102">可能不会在每个方案中使用这些控件。例如，“Create projects”方案不会使用 **textarea** 和 **button** 控件。</span><span class="sxs-lookup"><span data-stu-id="995fe-p102">These controls may not be used in every scenario. For example, the "Create projects" scenario does not use the **textarea** and **button** controls.</span></span> 
  
5. <span data-ttu-id="995fe-133">在闭合 **span** 标记后，添加一个 **SharePoint:ScriptLink** 标记、一个 **SharePoint:FormDigest** 标记和一些 **script** 标记，如下所示。</span><span class="sxs-lookup"><span data-stu-id="995fe-133">After the closing **span** tag, add a **SharePoint:ScriptLink** tag, a **SharePoint:FormDigest** tag, and **script** tags, as follows.</span></span> 
    
   ```HTML
    <SharePoint:ScriptLink id="ScriptLink" name="PS.js" runat="server" ondemand="false" localizable="false" loadafterui="true" />
    <SharePoint:FormDigest id="FormDigest" runat="server" />
    <script type="text/javascript">
        // Replace this comment with the code for your scenario.
    </script>
   ```

   <span data-ttu-id="995fe-134">the **SharePoint：ScriptLink** tag references the PS.js file， which defines the JavaScript object model for Project Server 2013.</span><span class="sxs-lookup"><span data-stu-id="995fe-134">The **SharePoint:ScriptLink** tag references the PS.js file, which defines the JavaScript object model for Project Server 2013.</span></span> <span data-ttu-id="995fe-135">如果更新服务器内容的操作需要，**SharePoint:FormDigest** 标记将为安全验证生成一个哈希。</span><span class="sxs-lookup"><span data-stu-id="995fe-135">The **SharePoint:FormDigest** tag generates a message digest for security validation when required by operations that update server content.</span></span> 
    
6. <span data-ttu-id="995fe-136">将占位符注释替换为下列过程之一中的代码：</span><span class="sxs-lookup"><span data-stu-id="995fe-136">Replace the placeholder comment with the code from one of the following procedures:</span></span>
    
   - [<span data-ttu-id="995fe-137">使用 javaScript Project模型创建 Project Server 2013 项目</span><span class="sxs-lookup"><span data-stu-id="995fe-137">Create Project Server 2013 projects by using the JavaScript object model</span></span>](#pj15_CRUDProjectsJSOM_CreateProjects)
    
   - [<span data-ttu-id="995fe-138">使用 javaScript Project模型更新 Project Server 2013 项目</span><span class="sxs-lookup"><span data-stu-id="995fe-138">Update Project Server 2013 projects by using the JavaScript object model</span></span>](#pj15_CRUDProjectsJSOM_UpdateProjects)
    
   - [<span data-ttu-id="995fe-139">使用 JavaScript Project删除 Project Server 2013 项目</span><span class="sxs-lookup"><span data-stu-id="995fe-139">Delete Project Server 2013 projects by using the JavaScript object model</span></span>](#pj15_CRUDProjectsJSOM_DeleteProjects)
    
7. <span data-ttu-id="995fe-p104">若要测试应用程序页，请在菜单栏上选择“调试”和“启动调试”。如果系统提示您修改 web.config 文件，请选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="995fe-p104">To test the application page, on the menu bar, choose **Debug**, **Start Debugging**. If you are prompted to modify the web.config file, choose **OK**.</span></span>
    
## <a name="create-project-server-2013-projects-by-using-the-javascript-object-model"></a><span data-ttu-id="995fe-142">使用 javaScript Project模型创建 Project Server 2013 项目</span><span class="sxs-lookup"><span data-stu-id="995fe-142">Create Project Server 2013 projects by using the JavaScript object model</span></span>
<span data-ttu-id="995fe-143"><a name="pj15_CRUDProjectsJSOM_CreateProjects"> </a></span><span class="sxs-lookup"><span data-stu-id="995fe-143"><a name="pj15_CRUDProjectsJSOM_CreateProjects"> </a></span></span>

<span data-ttu-id="995fe-144">本节中的过程使用 JavaScript 对象模型创建项目。</span><span class="sxs-lookup"><span data-stu-id="995fe-144">The procedure in this section creates projects by using the JavaScript object model.</span></span> <span data-ttu-id="995fe-145">此过程包括下列高级步骤：</span><span class="sxs-lookup"><span data-stu-id="995fe-145">The procedure includes the following high-level steps:</span></span>
  
1. <span data-ttu-id="995fe-146">获取当前 **ProjectContext** 实例。</span><span class="sxs-lookup"><span data-stu-id="995fe-146">Get the current **ProjectContext** instance.</span></span> 
    
2. <span data-ttu-id="995fe-p106">创建 **ProjectCreationInformation** 对象以指定项目的初始属性。使用 **ProjectCreationInformation.set_name** 函数指定必需的 **name** 属性。</span><span class="sxs-lookup"><span data-stu-id="995fe-p106">Create a **ProjectCreationInformation** object to specify initial properties for your project. Specify the required **name** property by using the **ProjectCreationInformation.set_name** function.</span></span> 
    
3. <span data-ttu-id="995fe-p107">使用 **ProjectContext.get_projects** 函数从服务器中检索已发布项目。**get_projects** 函数将返回一个 **ProjectCollection** 对象。</span><span class="sxs-lookup"><span data-stu-id="995fe-p107">Retrieve the published projects from the server by using the **ProjectContext.get_projects** function. The **get_projects** function returns a **ProjectCollection** object.</span></span> 
    
4. <span data-ttu-id="995fe-151">使用 **ProjectCollection.add** 函数并将该函数粘贴在 **ProjectCreationInformation** 对象中以将新项目添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="995fe-151">Add the new project to the collection by using the **ProjectCollection.add** function and passing in the **ProjectCreationInformation** object.</span></span> 
    
5. <span data-ttu-id="995fe-p108">使用 **ProjectCollection.update** 函数和 **ProjectContext.waitForQueueAsync** 函数更新此集合。**update** 函数将返回您将传递到 **waitForQueueAsync** 的 **QueueJob** 对象。此调用还将发布项目。</span><span class="sxs-lookup"><span data-stu-id="995fe-p108">Update the collection by using the **ProjectCollection.update** function and the **ProjectContext.waitForQueueAsync** function. The **update** function returns a **QueueJob** object that you pass to **waitForQueueAsync**. This call also publishes the project.</span></span>
    
<span data-ttu-id="995fe-155">将下列代码粘贴到您在 **创建 Visual Studio 中的应用程序页** 过程中添加的 **script** 标记之间。</span><span class="sxs-lookup"><span data-stu-id="995fe-155">Paste the following code between the **script** tags that you added in the **To create the application page in Visual Studio** procedure.</span></span> 
  
```js
    // Declare a global variable to store the project collection.
    var projects;
    // Ensure that the PS.js file is loaded before your custom code runs.
    SP.SOD.executeOrDelayUntilScriptLoaded(CreateProject, "PS.js");
    // Add a project the projects collection.
    function CreateProject() {
        
        // Initialize the current client context.
        var projContext = PS.ProjectContext.get_current();
        // Initialize a ProjectCreationInformation object and specify properties
        // for the new project.
        // The Name property is required and must be unique.
        var creationInfo = new PS.ProjectCreationInformation();
        creationInfo.set_name("Test Project 1");
        // Specify optional properties for the new project.
        // If not specified, the Start property uses the current date and the
        // EnterpriseProjectTypeId property uses the default EPT.
        creationInfo.set_description("Created through the JSOM.");
        creationInfo.set_start("2013-10-01 09:00:00.000");
        // Get the projects collection.
        projects = projContext.get_projects();
        // Add the new project to the projects collection.
        projects.add(creationInfo);
        // Add a second project to use in the deleting projects procedure.
        creationInfo.set_name("Test Project 2");
        projects.add(creationInfo);
        // Submit the request to update the collection on the server
        var updateJob = projects.update();
        projContext.waitForQueueAsync(updateJob, 10, GetProjects);
    }
    // Get the projects collection.
    function GetProjects(response) {
        // This call demonstrates that you can get the context from the 
        // ProjectCollection object.
        var projContext = projects.get_context();
        // Register the request for information that you want to run on the server.
        // This call includes an optional "Include" parameter to request only the Name, Description,
        // StartDate, and Id properties of the projects in the collection.
        projContext.load(projects, 'Include(Name, Description, StartDate, Id)');
        // Run the request on the server.
        projContext.executeQueryAsync(IterateThroughProjects, QueryFailed);
    }
    // Iterate through the projects collection.
    function IterateThroughProjects(response) {
        // Get the enumerator and iterate through the collection.
        var enumerator = projects.getEnumerator();
        while (enumerator.moveNext()) {
            var project = enumerator.get_current();
            // Create and populate a row with the values for the project's Name, Description,
            // StartDate, and Id properties.
            var row = tblProjects.insertRow();
            row.insertCell().innerText = project.get_name();
            row.insertCell().innerText = project.get_description();
            row.insertCell().innerText = project.get_startDate();
            row.insertCell().innerText = project.get_id();
        }
        // This scenario does not use the textarea or button controls.
        $get("txtGuid").disabled = true;
        $get("btnSend").disabled = true;
    }
    function QueryFailed(sender, args) {
        $get("spanMessage").innerText = 'Request failed: ' + args.get_message();
    }
```

## <a name="update-project-server-2013-projects-by-using-the-javascript-object-model"></a><span data-ttu-id="995fe-156">使用 javaScript Project模型更新 Project Server 2013 项目</span><span class="sxs-lookup"><span data-stu-id="995fe-156">Update Project Server 2013 projects by using the JavaScript object model</span></span>
<span data-ttu-id="995fe-157"><a name="pj15_CRUDProjectsJSOM_UpdateProjects"> </a></span><span class="sxs-lookup"><span data-stu-id="995fe-157"><a name="pj15_CRUDProjectsJSOM_UpdateProjects"> </a></span></span>

<span data-ttu-id="995fe-158">本节中的过程使用 JavaScript 对象模型更新项目的 **startDate** 属性。</span><span class="sxs-lookup"><span data-stu-id="995fe-158">The procedure in this section updates the **startDate** property of a project by using the JavaScript object model.</span></span> <span data-ttu-id="995fe-159">此过程包括下列高级步骤：</span><span class="sxs-lookup"><span data-stu-id="995fe-159">The procedure includes the following high-level steps:</span></span> 
  
1. <span data-ttu-id="995fe-160">获取当前 **ProjectContext** 实例。</span><span class="sxs-lookup"><span data-stu-id="995fe-160">Get the current **ProjectContext** instance.</span></span> 
    
2. <span data-ttu-id="995fe-p110">使用 **ProjectContext.get_projects** 函数从服务器中检索已发布项目。**get_projects** 函数将返回一个 **ProjectCollection** 对象。</span><span class="sxs-lookup"><span data-stu-id="995fe-p110">Retrieve the published projects from the server by using the **ProjectContext.get_projects** function. The **get_projects** function returns a **ProjectCollection** object.</span></span> 
    
3. <span data-ttu-id="995fe-163">使用 **ProjectContext.load** 函数和 **ProjectContext.executeQueryAsync** 函数运行对服务器的请求。</span><span class="sxs-lookup"><span data-stu-id="995fe-163">Run the request on the server by using the **ProjectContext.load** function and the **ProjectContext.executeQueryAsync** function.</span></span> 
    
4. <span data-ttu-id="995fe-164">使用 **ProjectContext.getById** 函数检索 **PublishedProject** 对象。</span><span class="sxs-lookup"><span data-stu-id="995fe-164">Retrieve a **PublishedProject** object by using the **ProjectContext.getById** function.</span></span> 
    
5. <span data-ttu-id="995fe-p111">使用 **Project.checkOut** 函数签出目标项目。**checkOut** 函数将返回已发布项目的草稿版本。</span><span class="sxs-lookup"><span data-stu-id="995fe-p111">Check out the target project by using the **Project.checkOut** function. The **checkOut** function returns the draft version of the published project.</span></span> 
    
6. <span data-ttu-id="995fe-167">使用 **DraftProject.set_startDate** 函数更改项目的开始日期。</span><span class="sxs-lookup"><span data-stu-id="995fe-167">Change the project's start date by using the **DraftProject.set_startDate** function.</span></span> 
    
7. <span data-ttu-id="995fe-p112">使用 **DraftProject.publish** 函数和 **ProjectContext.waitForQueueAsync** 函数发布项目。**publish** 函数将返回您将传递到 **waitForQueueAsync** 的 **QueueJob** 对象。</span><span class="sxs-lookup"><span data-stu-id="995fe-p112">Publish the project by using the **DraftProject.publish** function and the **ProjectContext.waitForQueueAsync** function. The **publish** function returns a **QueueJob** object that you pass to **waitForQueueAsync**.</span></span>
    
<span data-ttu-id="995fe-170">将下列代码粘贴到您在 **创建 Visual Studio 中的应用程序页** 过程中添加的 **script** 标记之间。</span><span class="sxs-lookup"><span data-stu-id="995fe-170">Paste the following code between the **script** tags that you added in the **To create the application page in Visual Studio** procedure.</span></span> 
  
```js
    // Declare global variables.
    var projContext;
    var projects;
    // Ensure that the PS.js file is loaded before your custom code runs.
    SP.SOD.executeOrDelayUntilScriptLoaded(GetProjects, "PS.js");
    // Get the projects collection.
    function GetProjects() {
        // Initialize the current client context.
        projContext = PS.ProjectContext.get_current();
        // Get the projects collection.
        projects = projContext.get_projects();
        // Register the request for information that you want to run on the server.
        // This call includes an optional "Include" parameter to request only the Name, Description,
        // StartDate, and Id properties of the projects in the collection.
        projContext.load(projects, 'Include(Name, Description, StartDate, Id)');
        // Run the request on the server.
        projContext.executeQueryAsync(IterateThroughProjects, QueryFailed);
    }
    // Iterate through the projects collection.
    function IterateThroughProjects(response) {
        // Get the enumerator and iterate through the collection.
        var enumerator = projects.getEnumerator();
        while (enumerator.moveNext()) {
            var project = enumerator.get_current();
            // Create and populate a row with the values for the project's Name, Description,
            // StartDate, and Id properties.
            var row = tblProjects.insertRow();
            row.insertCell().innerText = project.get_name();
            row.insertCell().innerText = project.get_description();
            row.insertCell().innerText = project.get_startDate();
            row.insertCell().innerText = project.get_id();
        }
        // Initialize button properties.
        $get("btnSend").onclick = function () { ChangeProject(); };
        $get("btnSend").innerText = "Update";
    }
    // Change the project's start date.
    function ChangeProject() {
        // Get the identifier of the target project.
        var targetGuid = $get("txtGuid").innerText;
        // Get the target project and then check it out. The checkOut function
        // returns the draft version of the project.
        var project = projects.getById(targetGuid);
        var draftProject = project.checkOut();
        // Set the new property value and then publish the project.
        // Specify "true" to also check the project in.
        draftProject.set_startDate("2013-12-31 09:00:00.000");
        var publishJob = draftProject.publish(true);
        // Register the job that you want to run on the server and specify the
        // timeout duration and callback function.
        projContext.waitForQueueAsync(publishJob, 10, QueueJobSent);
    }
    // Print the JobState return code, which gives the status of the queue job.
    function QueueJobSent(response) {
        $get("spanMessage").innerText = 'JobState = ' + response + '. Wait a few seconds, then refresh the page to see your changes.';
    }
    function QueryFailed(sender, args) {
        $get("spanMessage").innerText = 'Request failed: ' + args.get_message();
    }
```

## <a name="delete-project-server-2013-projects-by-using-the-javascript-object-model"></a><span data-ttu-id="995fe-171">使用 JavaScript Project删除 Project Server 2013 项目</span><span class="sxs-lookup"><span data-stu-id="995fe-171">Delete Project Server 2013 projects by using the JavaScript object model</span></span>
<span data-ttu-id="995fe-172"><a name="pj15_CRUDProjectsJSOM_DeleteProjects"> </a></span><span class="sxs-lookup"><span data-stu-id="995fe-172"><a name="pj15_CRUDProjectsJSOM_DeleteProjects"> </a></span></span>

<span data-ttu-id="995fe-173">本节中的过程使用 JavaScript 对象模型删除项目。</span><span class="sxs-lookup"><span data-stu-id="995fe-173">The procedure in this section deletes a project by using the JavaScript object model.</span></span> <span data-ttu-id="995fe-174">此过程包括下列高级步骤：</span><span class="sxs-lookup"><span data-stu-id="995fe-174">The procedure includes the following high-level steps:</span></span>
  
1. <span data-ttu-id="995fe-175">获取当前 **ProjectContext** 实例。</span><span class="sxs-lookup"><span data-stu-id="995fe-175">Get the current **ProjectContext** instance.</span></span> 
    
2. <span data-ttu-id="995fe-p114">使用 **ProjectContext.get_projects** 函数从服务器中检索已发布项目。**get_projects** 函数将返回一个 **ProjectCollection** 对象。</span><span class="sxs-lookup"><span data-stu-id="995fe-p114">Retrieve the published projects from the server by using the **ProjectContext.get_projects** function. The **get_projects** function returns a **ProjectCollection** object.</span></span> 
    
3. <span data-ttu-id="995fe-178">使用 **ProjectContext.load** 函数和 **ProjectContext.executeQueryAsync** 函数运行对服务器的请求。</span><span class="sxs-lookup"><span data-stu-id="995fe-178">Run the request on the server by using the **ProjectContext.load** function and the **ProjectContext.executeQueryAsync** function.</span></span> 
    
4. <span data-ttu-id="995fe-179">使用 **ProjectCollection.getById** 函数检索 **PublishedProject** 对象。</span><span class="sxs-lookup"><span data-stu-id="995fe-179">Retrieve a **PublishedProject** object by using the **ProjectCollection.getById** function.</span></span> 
    
5. <span data-ttu-id="995fe-180">通过将项目粘贴到 **ProjectCollection.remove** 函数中来删除项目。</span><span class="sxs-lookup"><span data-stu-id="995fe-180">Delete the project by passing it to the **ProjectCollection.remove** function.</span></span> 
    
6. <span data-ttu-id="995fe-p115">使用 **ProjectCollection.update** 函数和 **ProjectContext.waitForQueueAsync** 函数更新此集合。**update** 函数将返回您将传递到 **waitForQueueAsync** 的 **QueueJob** 对象。</span><span class="sxs-lookup"><span data-stu-id="995fe-p115">Update the collection by using the **ProjectCollection.update** function and the **ProjectContext.waitForQueueAsync** function. The **update** function returns a **QueueJob** object that you pass to **waitForQueueAsync**.</span></span>
    
<span data-ttu-id="995fe-183">将下列代码粘贴到您在 **创建 Visual Studio 中的应用程序页** 过程中添加的 **script** 标记之间。</span><span class="sxs-lookup"><span data-stu-id="995fe-183">Paste the following code between the **script** tags that you added in the **To create the application page in Visual Studio** procedure.</span></span> 
  
```js
    // Declare global variables.
    var projContext;
    var projects;
    // Ensure that the PS.js file is loaded before your custom code runs.
    SP.SOD.executeOrDelayUntilScriptLoaded(GetProjects, "PS.js");
    // Get the projects collection.
    function GetProjects() {
        // Initialize the current client context.
        projContext = PS.ProjectContext.get_current();
        // Get the projects collection.
        projects = projContext.get_projects();
        // Register the request for information that you want to run on the server.
        // This call includes an optional "Include" parameter to request only the Name, Description,
        // StartDate, and Id properties of the projects in the collection.
        projContext.load(projects, 'Include(Name, Description, StartDate, Id)');
        // Run the request on the server.
        projContext.executeQueryAsync(IterateThroughProjects, QueryFailed);
    }
    // Iterate through the projects collection.
    function IterateThroughProjects(response) {
        // Get the enumerator and iterate through the collection.
        var enumerator = projects.getEnumerator();
        while (enumerator.moveNext()) {
            var project = enumerator.get_current();
            // Create and populate a row with the values for the project's Name, Description,
            // StartDate, and Id properties.
            var row = tblProjects.insertRow();
            row.insertCell().innerText = project.get_name();
            row.insertCell().innerText = project.get_description();
            row.insertCell().innerText = project.get_startDate();
            row.insertCell().innerText = project.get_id();
        }
        // Initialize button properties.
        $get("btnSend").onclick = function () { DeleteProject(); };
        $get("btnSend").innerText = "Delete";
    }
    // Delete the project.
    function DeleteProject() {
        // Get the identifier of the target project.
        var targetGuid = $get("txtGuid").innerText;
        // Get the target project and then remove it from the collection.
        var project = projects.getById(targetGuid);
        projects.remove(project);
        var removeJob = projects.update();
        // Register the job that you want to run on the server and specify the
        // timeout duration and callback function.
        projContext.waitForQueueAsync(removeJob, 10, QueueJobSent);
    }
    // Print the JobState return code, which gives the status of the queue job.
    function QueueJobSent(response) {
        $get("spanMessage").innerText = 'JobState = ' + response + '. Wait a few seconds, then refresh the page to see your changes.';
    }
    function QueryFailed(sender, args) {
        $get("spanMessage").innerText = 'Request failed: ' + args.get_message();
    }
```

<span data-ttu-id="995fe-184"><a name="pj15_CRUDProjectsJSOM_AR"> </a></span><span class="sxs-lookup"><span data-stu-id="995fe-184"><a name="pj15_CRUDProjectsJSOM_AR"> </a></span></span>

## <a name="see-also"></a><span data-ttu-id="995fe-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="995fe-185">See also</span></span>

- [<span data-ttu-id="995fe-186">Project 编程任务</span><span class="sxs-lookup"><span data-stu-id="995fe-186">Project programming tasks</span></span>](project-programming-tasks.md)
- [<span data-ttu-id="995fe-187">Project 2013 的客户端对象模型 (CSOM)</span><span class="sxs-lookup"><span data-stu-id="995fe-187">Client-side object model (CSOM) for Project 2013</span></span>](client-side-object-model-csom-for-project-2013.md)
    

