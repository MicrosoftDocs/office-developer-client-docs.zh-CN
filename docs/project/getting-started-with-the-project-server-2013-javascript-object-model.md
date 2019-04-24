---
title: Project Server 2013 JavaScript 对象模型入门
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 30dc3194-7480-4e7c-b731-4a171d652ee0
description: 在 project Server 2013 中, JavaScript 对象模型可用于 Project Online、移动和内部部署开发中。 本主题简要概述了 javascript 对象模型, 然后介绍了如何使用 javascript 对象模型创建用于检索和循环访问项目的应用程序页。
ms.openlocfilehash: ec8a10e987276807dc4648bd8948b2285f76fd37
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360471"
---
# <a name="getting-started-with-the-project-server-2013-javascript-object-model"></a>Project Server 2013 JavaScript 对象模型入门

在 project Server 2013 中, JavaScript 对象模型可用于 Project Online、移动和内部部署开发中。 本主题简要概述了 javascript 对象模型, 然后介绍了如何使用 javascript 对象模型创建用于检索和循环访问项目的应用程序页。
  
## <a name="using-the-project-server-javascript-object-model"></a>使用 Project Server JavaScript 对象模型
<a name="pj15_GetStartedJSOM_UseJSOM"> </a>

使用 JavaScript 对象模型是创建运行客户端 (而不是需要远程运行的托管客户端代码) 的应用程序的绝佳方式。 应用可以通过向服务器发送异步调用来使用 JavaScript 对象模型检索或更改对象。 使用 JavaScript 对象模型的应用程序通常部署为自定义 SharePoint 外接程序、应用程序页和 Web 部件。 有关详细信息, 请参阅 sharepoint 2013 中的 "[主机 web、外接程序 web 和 sharepoint 组件](https://msdn.microsoft.com/library/b791cdf5-8aa2-47fa-bc4c-aee437354759%28Office.15%29.aspx)中可以在 sharepoint 相关应用程序中使用的 sharepoint 组件类型"。
  
javascript 对象模型实现了 Project Server 2013 的主要功能, 但 javascript 对象模型和服务器对象模型不具有一对一的奇偶校验。 JavaScript 对象模型的入口点是**ProjectContext**对象, 它表示 Project Server 2013 的客户端上下文, 并提供对服务器内容和功能的访问权限。 Project Server 2013 的 JavaScript 对象模型在 PS .js 文件中定义, 该文件位于应用程序服务器上的默认路径`%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS`中。 Project Server 2013 还安装 PS。在同一位置调试 .js 文件。 PS.Debug.js 是 PS.js 的未缩小版本，它提供了 IntelliSense 信息。 
  
JavaScript 对象模型允许进行表单身份验证, 并将所有请求都作为当前用户进行身份验证。 有关设计自定义应用程序和解决方案的安全和其他注意事项的详细信息, 请参阅[sharepoint 2013 中的身份验证、授权和安全性](https://msdn.microsoft.com/library/8734790c-eb75-4d78-9604-7cc23b33b693%28Office.15%29.aspx)、 [sharepoint 外接程序体系结构和开发的重要方面](https://msdn.microsoft.com/library/ae96572b-8f06-4fd3-854f-fc312f7f2d88%28Office.15%29.aspx)[与 sharepoint 解决方案相比, 横向和 sharepoint 外接程序进行了比较](https://msdn.microsoft.com/library/0e9efadb-aaf2-4c0d-afd5-d6cf25c4e7a8%28Office.15%29.aspx)。
  
> [!NOTE]
> 若要远程访问 sharepoint 网站中的数据, SharePoint 2013 提供了一个跨域库, 使您能够进行客户端跨域调用。 有关详细信息, 请参阅[使用跨域库从外接程序访问 SharePoint 2013 数据](https://msdn.microsoft.com/library/bc37ff5c-1285-40af-98ae-01286696242d%28Office.15%29.aspx)。 
  
有关使用 Project Server 2013 的 JavaScript 对象模型的许多概念和过程与相关客户端对象模型中的过程类似。 有关 Project Server 2013 托管客户端对象模型的详细信息, 请参阅**microsoft.projectserver.client**。 有关 sharepoint 2013JavaScript 对象模型和托管客户端对象模型的详细信息, 请参阅[使用 sharepoint 2013 中的 JavaScript 库代码完成基本操作](https://msdn.microsoft.com/library/29089af8-dbc0-49b7-a1a0-9e311f49c826%28Office.15%29.aspx)和[使用 SharePoint 2013 客户端完成基本操作库代码](https://msdn.microsoft.com/library/5a69c9e3-73bf-4ed5-bc19-182056bdb394%28Office.15%29.aspx)。
  
## <a name="walkthrough-creating-an-application-page-that-retrieves-and-iterates-through-projects"></a>演练：创建可检索和循环访问各个项目的应用程序页
<a name="pj15_GetStartedJSOM_UseJSOM"> </a>

了解如何创建可显示网站中每个已发布项目的 ID、名称和创建日期的应用程序页。
  
### <a name="prerequisites-for-creating-an-application-page-that-retrieves-and-iterates-through-projects"></a>创建可检索和循环访问各个项目的应用程序的先决条件
<a name="pj15_GetStartedJSOM_Prereqs"> </a>

若要开发本主题中描述的应用程序页，您必须安装和配置以下产品：
  
- SharePoint Server 2013
- 包含至少一个已发布项目的 project Server 2013
- Visual Studio 2008
- Visual Studio 2012 Office 开发人员工具
    
您还必须具有将扩展部署到 SharePoint Server 2013 和检索项目的权限。
  
> [!NOTE]
> 这些说明假定您在运行 Project Server 2013 的计算机上进行开发。 
  
### <a name="creating-the-application-page-in-visual-studio-2012"></a>在 Visual Studio 2012 中创建应用程序页
<a name="pj15_GetStartedJSOM_CreateVS"> </a>

以下步骤创建了一个 SharePoint 项目和一个包含表和标签的应用程序页。表显示了有关项目的信息，标签显示了错误消息。
  
1. 在运行 Project Server 2013 的计算机上, 以管理员身份运行 Visual Studio 2012。
    
2. 创建一个空的 SharePoint 2013 项目, 如下所示:
    
    1. 在“新建项目”**** 对话框中，从对话框顶部的下拉列表中选择“.NET Framework 4.5”****。 
        
    2. 在模板类别列表中，选择“Office SharePoint”**** 类别，然后选择“SharePoint 2013 项目”**** 模板。 
        
    3. 将项目命名为 "GetProjectsJSOM", 然后选择 **"确定"** 按钮。 
        
    4. 在“SharePoint 自定义向导”**** 对话框中，选择“部署为场解决方案”****，然后选择“确定”**** 按钮。 
    
3. 在 "解决方案资源管理器" 中, 编辑**ProjectsJSOM**项目的 "**网站 url** " 属性的值, 以匹配 project Web App 实例的 url ( `https://ServerName/PWA`例如,)。
    
4. 打开“GetProjectsJSOM”**** 项目的快捷菜单，然后添加 SharePoint“Layouts”映射文件夹。 
    
5. 在 "**布局**" 文件夹中, 打开 " **GetProjectsJSOM** " 文件夹的快捷菜单, 然后添加名为 "projectslist.aspx" 的新 SharePoint 应用程序页。
    
   > [!NOTE]
   > 此示例不使用 Visual Studio 2012 为应用程序页创建的代码隐藏文件。 
  
6. 打开 **ProjectsList.aspx** 页的快捷菜单，然后选择“设置为启动项”****。
    
7. 在 **ProjectsList.aspx** 页的标记中，在“主要”**asp:Content** 标记中定义一个表和一个消息占位符，如下所示。 
    
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

### <a name="retrieving-the-projects-collection"></a>检索项目集合
<a name="pj15_GetStartedJSOM_RetrieveProjs"> </a>

可通过以下步骤检索和初始化项目集合。
  
1. 在结束 **div** 标记的后面，添加一个引用 PS.js 文件的 **SharePoint:ScriptLink** 标记，如下所示。 
    
   ```HTML
    <SharePoint:ScriptLink name="PS.js" runat="server" ondemand="false" localizable="false" loadafterui="true" />
   ```

2. 在 **SharePoint:ScriptLink** 标记的下方，添加 **script** 标记，如下所示。 
    
   ```HTML
    <script type="text/javascript">
        // Paste the remaining code snippets here, in the order that they are presented.
    </script>
   ```

3. 声明一个全局变量以存储项目集合，如下所示。
    
   ```js
   var projects;
   ```

4. 调用 **SP.SOD.executeOrDelayUntilScriptLoaded** 方法以确保 PS.js 文件在您的自定义代码运行之前加载。 
    
   ```js
   SP.SOD.executeOrDelayUntilScriptLoaded(GetProjects, "PS.js");
   ```

5. 添加一个将连接到当前上下文并检索项目集合的函数，如下所示。
    
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

   您通过上下文检索的一些客户端对象在初始化之前不包含任何数据;也就是说, 在初始化对象之前, 不能访问对象的属性值。 此外, 对于**ValueObject**类型的属性, 您必须显式请求该属性, 然后才能访问它的值。 (如果尝试在初始化属性之前对其进行访问, 则会收到**PropertyOrFieldNotInitializedException**异常。) 
    
   若要初始化对象，您可以依次调用 **load** 方法（或 **loadQuery** 方法）和 **executeQueryAsync** 方法。 
    
   - 调用 **load** 函数或 **loadQuery** 函数将注册要在服务器上运行的请求。 您将传入一个表示要检索的对象的参数。 如果您使用的是 **ValueObject** 属性，则还要在参数中请求该属性。 
    
   - 调用 **executeQueryAsync** 函数会通过异步方式向服务器发送查询请求。 您将传入一个成功回调函数和一个失败回调函数，在收到服务器响应时将调用它们。 
    
   为了减少网络流量，在您调用 **load** 函数时仅请求要使用的属性。 此外，如果您使用了多个对象，则在调用 **executeQueryAsync** 函数之前，将针对 **load** 函数的多个调用进行分组（如果可能）。 
    
### <a name="iterating-through-the-projects-collection"></a>循环访问项目集合
<a name="pj15_GetStartedJSOM_IterateProjs"> </a>

可通过以下步骤循环访问项目集合（如果服务器调用成功）或呈现错误消息（如果调用失败）。
  
1. 添加一个可循环访问项目集合的成功回调函数，如下所示。
    
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

2. 添加一个可呈现错误消息的失败回调函数，如下所示。
    
    ```js
    function onQueryFailed(sender, args) {
        $get("spanMessage").innerText = 'Request failed: ' + args.get_message();
    }
    ```

3. 若要测试应用程序页，请在菜单栏上选择“调试”**** 和“启动调试”****。如果系统提示您修改 web.config 文件，请选择“确定”****。

<a name="pj15_GetStartedJSOM_CompleteExample"> </a>

## <a name="complete-code-example"></a>完整的代码示例

以下是 ProjectsList.aspx 文件中的完整代码。
  
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

<a name="pj15_GetStartedJSOM_AR"> </a>

## <a name="see-also"></a>另请参阅

- [使用 Project Server JavaScript 对象模型创建、检索、更新和删除项目](create-retrieve-update-delete-projects-using-project-server-javascript.md)  
- [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)
- [Project Server CSOM 和 .NET 入门](getting-started-with-the-project-server-csom-and-net.md)
    

