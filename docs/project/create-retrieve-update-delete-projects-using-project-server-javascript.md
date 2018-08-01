---
title: 创建、 检索、 更新和删除项目使用 Project Server JavaScript
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6b690938-05bc-46a3-a40e-30f081403767
description: 获取当前 ProjectContext 实例;检索和循环访问的服务器; 上的已发布项目的集合创建、 检索、 签出和使用 Project Server JavaScript 对象模型; 删除项目并更改项目的属性。
ms.openlocfilehash: 966c1298d210cb608001e4ce2b390611a75bdb24
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779414"
---
# <a name="create-retrieve-update-and-delete-projects-using-project-server-javascript"></a>创建、 检索、 更新和删除项目使用 Project Server JavaScript

本文中的方案演示如何获取当前**ProjectContext**实例;检索和循环访问的服务器; 上的已发布项目的集合创建、 检索、 签出和使用 Project Server JavaScript 对象模型; 删除项目并更改项目的属性。 
  
> [!NOTE]
> 这些方案的 SharePoint 应用程序页标记中定义自定义代码，但是没有为该页面使用 Visual Studio 2012 创建的代码隐藏文件。 
  
## <a name="prerequisites-for-working-with-project-server-2013-projects-in-the-javascript-object-model"></a>使用 Project Server 2013 JavaScript 对象模型中的项目的先决条件

若要执行本文中介绍的方案，您必须安装并配置下列产品：
  
- SharePoint Server 2013
- Project Server 2013
- Visual Studio 2012
- Visual Studio 2012 Office 开发人员工具
    
您还必须具有将扩展部署到 SharePoint Server 2013 以及参与项目的权限。
  
> [!NOTE]
> 这些说明假定您在运行 Project Server 2013 的计算机上开发。 
  
## <a name="create-the-visual-studio-solution"></a>创建 Visual Studio 解决方案
<a name="pj15_CRUDProjectsJSOM_Setup"> </a>

以下步骤创建一个包含 SharePoint 项目和应用程序页上的 Visual Studio 2012 解决方案。 页面包含用于处理的项目的逻辑。
  
### <a name="to-create-the-sharepoint-project-in-visual-studio"></a>创建 Visual Studio 中的 SharePoint 项目

1. 在计算机上运行 Project Server 2013，以管理员身份运行 Visual Studio 2012。
    
2. 在菜单栏上，依次选择"文件"、"新建"、"项目"。
    
3. 在"新建项目"对话框中，从对话框顶部的下拉列表中选择".NET Framework 4.5"。 
    
4. 在“Office/SharePoint”**** 模板类别中，选择“SharePoint 解决方案”****，然后选择“SharePoint 2013 项目”**** 模板。 
    
5. 将项目命名为 ProjectsJSOM，，然后选择**确定**按钮。 
    
6. 在"SharePoint 自定义向导"对话框中，选择"部署场解决方案"，然后选择"完成"按钮。 
    
7. 编辑**ProjectsJSOM**项目与 Project Web App 实例的 URL 匹配的**Site URL**属性的值 (例如， `http://ServerName/PWA`)。
    
### <a name="to-create-the-application-page-in-visual-studio"></a>创建 Visual Studio 中的应用程序页

1. 在“解决方案资源管理器”**** 中，打开 **ProjectsJSOM** 项目的快捷菜单，然后添加“SharePoint 的‘Layouts’映射文件夹”。 
    
2. 在**Layouts**文件夹中，打开**ProjectsJSOM**文件夹的快捷菜单，然后添加一个新的名为 ProjectsList.aspx 的 SharePoint 应用程序页。
    
3. 打开 **ProjectsList.aspx** 页的快捷菜单，然后选择“设置为启动项”****。
    
4. 在 **ProjectsList.aspx** 页的标记中，将用户界面控件定义在“Main”**asp:Content** 标记内，如下所示： 
    
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
   > 可能不会在每个方案中使用这些控件。例如，“Create projects”方案不会使用 **textarea** 和 **button** 控件。 
  
5. 在闭合 **span** 标记后，添加一个 **SharePoint:ScriptLink** 标记、一个 **SharePoint:FormDigest** 标记和一些 **script** 标记，如下所示。 
    
   ```HTML
    <SharePoint:ScriptLink id="ScriptLink" name="PS.js" runat="server" ondemand="false" localizable="false" loadafterui="true" />
    <SharePoint:FormDigest id="FormDigest" runat="server" />
    <script type="text/javascript">
        // Replace this comment with the code for your scenario.
    </script>
   ```

   **Sharepoint: Scriptlink**标记引用 PS.js 文件，它定义用于 Project Server 2013 JavaScript 对象模型。 **SharePoint:FormDigest**标记生成消息摘要的安全验证时所需的更新服务器内容的操作。 
    
6. 将占位符注释替换为下列过程之一中的代码：
    
   - [使用 JavaScript 对象模型创建 Project Server 2013 项目](#pj15_CRUDProjectsJSOM_CreateProjects)
    
   - [使用 JavaScript 对象模型更新 Project Server 2013 项目](#pj15_CRUDProjectsJSOM_UpdateProjects)
    
   - [使用 JavaScript 对象模型删除 Project Server 2013 项目](#pj15_CRUDProjectsJSOM_DeleteProjects)
    
7. 若要测试应用程序页，请在菜单栏上选择“调试”**** 和“启动调试”****。如果系统提示您修改 web.config 文件，请选择“确定”****。
    
## <a name="create-project-server-2013-projects-by-using-the-javascript-object-model"></a>使用 JavaScript 对象模型创建 Project Server 2013 项目
<a name="pj15_CRUDProjectsJSOM_CreateProjects"> </a>

本节中的过程使用 JavaScript 对象模型创建项目。 过程包括以下高级步骤：
  
1. 获取当前 **ProjectContext** 实例。 
    
2. 创建 **ProjectCreationInformation** 对象以指定项目的初始属性。使用 **ProjectCreationInformation.set_name** 函数指定必需的 **name** 属性。 
    
3. 使用 **ProjectContext.get_projects** 函数从服务器中检索已发布项目。**get_projects** 函数将返回一个 **ProjectCollection** 对象。 
    
4. 使用 **ProjectCollection.add** 函数并将该函数粘贴在 **ProjectCreationInformation** 对象中以将新项目添加到集合中。 
    
5. 使用 **ProjectCollection.update** 函数和 **ProjectContext.waitForQueueAsync** 函数更新此集合。**update** 函数将返回您将传递到 **waitForQueueAsync** 的 **QueueJob** 对象。此调用还将发布项目。
    
将下列代码粘贴到您在**创建 Visual Studio 中的应用程序页**过程中添加的 **script** 标记之间。 
  
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

## <a name="update-project-server-2013-projects-by-using-the-javascript-object-model"></a>使用 JavaScript 对象模型更新 Project Server 2013 项目
<a name="pj15_CRUDProjectsJSOM_UpdateProjects"> </a>

本节中的过程使用 JavaScript 对象模型更新项目的**startDate**属性。 过程包括以下高级步骤： 
  
1. 获取当前 **ProjectContext** 实例。 
    
2. 使用 **ProjectContext.get_projects** 函数从服务器中检索已发布项目。**get_projects** 函数将返回一个 **ProjectCollection** 对象。 
    
3. 使用 **ProjectContext.load** 函数和 **ProjectContext.executeQueryAsync** 函数运行对服务器的请求。 
    
4. 使用 **ProjectContext.getById** 函数检索 **PublishedProject** 对象。 
    
5. 使用 **Project.checkOut** 函数签出目标项目。**checkOut** 函数将返回已发布项目的草稿版本。 
    
6. 使用 **DraftProject.set_startDate** 函数更改项目的开始日期。 
    
7. 使用 **DraftProject.publish** 函数和 **ProjectContext.waitForQueueAsync** 函数发布项目。**publish** 函数将返回您将传递到 **waitForQueueAsync** 的 **QueueJob** 对象。
    
将下列代码粘贴到您在**创建 Visual Studio 中的应用程序页**过程中添加的 **script** 标记之间。 
  
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

## <a name="delete-project-server-2013-projects-by-using-the-javascript-object-model"></a>使用 JavaScript 对象模型删除 Project Server 2013 项目
<a name="pj15_CRUDProjectsJSOM_DeleteProjects"> </a>

本节中的过程使用 JavaScript 对象模型中删除项目。 过程包括以下高级步骤：
  
1. 获取当前 **ProjectContext** 实例。 
    
2. 使用 **ProjectContext.get_projects** 函数从服务器中检索已发布项目。**get_projects** 函数将返回一个 **ProjectCollection** 对象。 
    
3. 使用 **ProjectContext.load** 函数和 **ProjectContext.executeQueryAsync** 函数运行对服务器的请求。 
    
4. 使用 **ProjectCollection.getById** 函数检索 **PublishedProject** 对象。 
    
5. 通过将项目粘贴到 **ProjectCollection.remove** 函数中来删除项目。 
    
6. 使用 **ProjectCollection.update** 函数和 **ProjectContext.waitForQueueAsync** 函数更新此集合。**update** 函数将返回您将传递到 **waitForQueueAsync** 的 **QueueJob** 对象。
    
将下列代码粘贴到您在**创建 Visual Studio 中的应用程序页**过程中添加的 **script** 标记之间。 
  
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

<a name="pj15_CRUDProjectsJSOM_AR"> </a>

## <a name="see-also"></a>另请参阅

- [Project 编程任务](project-programming-tasks.md)
- [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)
    

