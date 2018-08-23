---
title: 开发的 Project Online 外接程序使用 JavaScript 对象模型 (JSOM)
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4a4b1ad2-de46-421d-a698-53c20c90b93a
description: 本文介绍 Microsoft Project Online 的加载项开发来增强您使用 Project Online 的体验。 开发项目是作为演练实现的。 外接程序用于本文读取和显示的项目名称和 Id 的已发布项目从您的 Project Online 帐户并允许您以检索与各个项目的任务向下钻取。
ms.openlocfilehash: ea5c7e3f3d20aa6bf5b6bb77a18eb87d06f549e1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572541"
---
# <a name="developing-a-project-online-add-in-using-the-javascript-object-model-jsom"></a>开发的 Project Online 外接程序使用 JavaScript 对象模型 (JSOM)

本文介绍 Microsoft Project Online 的加载项开发来增强您使用 Project Online 的体验。 开发项目是作为演练实现的。 外接程序用于本文读取和显示的项目名称和 Id 的已发布项目从您的 Project Online 帐户并允许您以检索与各个项目的任务向下钻取。
  
在运行时外, 接程序列出看起来类似于下图：
  
![屏幕截图显示 JSOM 项目和任务的列表](media/766e5914-f048-48f4-9282-291f55e6e90d.png "屏幕截图显示 JSOM 项目和任务的列表")
  
该示例的重点是使用 Project Online，进行查询并从服务设置为每个请求的上下文的交互。 用户界面 (UI) 元素得到最少的关注。 而是源列表提供了有关用户界面的注释。
  
> [!NOTE]
> 示例加载项，Visual Studio 项目中，源文件位于： https://github.com/OfficeDev/Project-JSOM-List-Projects-Tasks....。 保留的源文件通过单一便捷式作为引用时您阅读此文章中，为每个补充另。 Visual Studio 中的文件 project 生成且可使用最少的更改执行 — 替换为您的 PWA 文件夹下的 Project Online 租户的 URL。 
  
## <a name="background"></a>背景

Project Online 是一种 Office 365 服务，公司提供的项目组合管理 (PPM) 和项目管理办公室 (PMO) 解决方案，以进行协调和管理项目组合、 程序和项目。 Project Online 是一种不同的产品比 Project 桌面版本;尚未，Project Online 仍包含的功能来维护和跟踪整个生命周期中的项目的项目详细信息。 Project Online 是基于 SharePoint Online。
  
Project Online 中托管的加载项包含与客户端对象模型 API 进行交互的 JavaScript 和资源文件。 当用户访问的加载项时，将下载并在浏览器中执行 JavaScript 和资源。 外接程序使到 Project Online 与服务进行交互，是否创建、 检索、 更新或删除数据的异步调用。 
  
Project Online 执行一个更多操作来保护信息属于其他租户中的外接程序;即，Project Online 中创建一个独立的网站，以与来自外接程序的请求进行交互。 Project Online 主机上不运行的任何自定义代码。 
  
Project Online 外接程序的开发设置使用 Visual Studio SharePoint 外接程序项目类型。 外接程序编写 JavaScript 中, 并使用项目 JavaScript 对象模型 (JSOM) 与 Project Online 服务进行交互。 JSOM 从 SharePoint JSOM 继承其大部分功能。
  
> [!NOTE]
> 加载项可以发布和销售的 Office 商店或部署到 SharePoint 上专用应用程序目录。 有关详细信息，请参阅[部署和发布 Office 外接程序](https://docs.microsoft.com/en-us/office/dev/add-ins/publish/publish)。
> 
> 使用本文中的外接程序是面向开发人员; 示例它不是为在生产环境中使用。 主要用途是显示 for Project Online 中的应用程序开发的示例。 
  
## <a name="prerequisites"></a>先决条件

向支持 Windows 环境中添加以下各项：
  
- **.NET framework 4.0 或更高版本**： 4.0 版从框架的完整版本的兼容。 下载站点是https://msdn.microsoft.com/en-us/vstudio/aa496123.aspx。
    
- **Visual Studio 2013 或更高版本**：  
    
   - Visual Studio 2015 专业版已准备好转出的框中，可在https://www.visualstudio.com/en-us/products/visual-studio-professional-with-msdn-vs.aspx。
    
   - 社区版本的 Visual Studio 2015 位于https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx。 此版本的 Visual Studio 需要手动安装 Microsoft Office 开发人员工具。
    
   Microsoft Visual Studio 的 Office 开发人员工具，可从https://www.visualstudio.com/en-us/features/office-tools-vs.aspx。
    
- **Project Online 帐户**： 这提供了对承载服务的访问。 有关获取 Project Online 帐户的详细信息，请参阅https://products.office.com/en-us/Project/project-online-portfolio-management。
    
   确保外接程序用户具有权限不足，无法访问 Project Online 租户中的某些项目。 
    
- **承载的网站上的项目**填充的信息。
    
> [!NOTE]
> 标准.NET Framework 是要使用的正确框架。 不要使用".NET Framework 4 客户端配置文件"。 
  
### <a name="set-up-the-visual-studio-project"></a>设置 Visual Studio 项目

应用程序安装由创建新项目、 链接合适的库和声明所需的命名空间组成。 Visual Studio 提供了几种类型的开发项目。 在部分，简要和非常基本。 值遇到信息合并在一个位置。
  
#### <a name="select-a-visual-studio-project"></a>选择 Visual Studio 项目

若要创建外接程序的适当类型的项目时，必须执行以下步骤。 在屏幕上遇到关键字具有**粗体**属性： 
  
1. 从文件菜单中，选择**文件** > **新建** > **项目**。 
    
2. 从已安装的模板的左窗格中，选择**C#** > **Office/SharePoint** > **Web 加载项**。 
    
3. 在中央窗格的顶部，选择 **.NET Framework 4**或更高版本;当前版本是 4.6。 
    
4. 从类型的应用程序的中央窗格中，选择**SharePoint 加载项**。 
    
5. 在底部部分中，指定的名称和位置的项目，并解决方案名称。 
    
6. 此外在底部部分中，检查**创建解决方案的目录**框中。 
    
7. 单击**确定**以创建初始项目。 
    
在两个遵循的对话框中，Visual Studio 向导会有关 Project Online 中设置网站 （称为 SharePoint 设置在该对话框） 询问几个后续问题。 下面是这些问题：
  
1. 要用于调试您的加载项将哪个 SharePoint 网站？ 指定您的 PWA 网站的 URL，如https://contoso.sharepoint.com/sites/pwa。
    
2. 您希望如何承载 SharePoint 外接程序？ 选择 [X] **SharePoint 承载**。
    
   有关 SharePoint 加载项的详细信息，包括承载选项，请参阅[SharePoint 加载项](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/sharepoint-add-ins)。
    
3. 单击“下一步”****。 
    
第二个其他对话框询问您指定的外接程序的 SharePoint Online 版本： 
  
1. 什么是您希望加载项到目标的 SharePoint 的最早版本？ 选择 [X] S **harePoint 联机**。 
    
2. 单击“完成”****。 
    
Visual Studio 创建项目并访问的 Project Online 网站。 
  
### <a name="enable-sideloading-on-the-project-online-site"></a>启用 Project Online 网站上的 sideloading

Sideloading 是用于测试和调试 Project Online 的加载项的机制。需要两个脚本 sideloading： 一个启用 sideloading 上 Project Online 网站，另一个用于禁用 sideloading 后完成测试和调试外接程序。
  
有关 sideloading 设置的详细信息，请参阅[启用应用程序 SideLoading 非开发人员网站集](https://blogs.msdn.microsoft.com/officeapps/2013/12/10/enable-app-sideloading-in-your-non-developer-site-collection/)。
  
> [!NOTE]
> Sideloading 应用程序是开发人员/测试功能。 它是**不用于生产用途**。 定期，不要不 sideload 应用程序或保留应用程序 sideloading 启用比您当前正在使用的功能更长时间。 
  
## <a name="add-content-to-the-add-in-project"></a>将内容添加到加载项项目

创建项目并设置调试机制之后, 将内容添加到应用程序包括以下任务：
  
- 设置应用程序范围
    
- 链接的 JSOM 库
    
- 将 UI 元素添加到加载项
    
- 初始化并连接到 Project Online 服务
    
- 检索项目和详细信息/属性
    
- 显示项目
    
- 显示任务项目
    
外接程序项目包含多个文件。 本示例中，您需要编辑以下文件： 
  
- AppManifest.xml
    
- Default.aspx
    
- App.js
    
- App.css-可选;包含开发加载项的样式定义
    
如果 Project Online 租户发生更改，如进入从试用订阅网站，您可以更新项目属性，包括服务器连接和网站 URL，使用属性窗口可通过**查看** > **属性窗口**命令。 
  
您还可以将文件添加到项目。 如果是这样，您需要更新位于同一组 （内容、 图像、 页面或脚本） 以包含新文件中的 Elements.xml 文件。 有关项目文件的详细信息，请参阅[了解应用程序清单结构和包的 SharePoint 外接程序](https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/explore-the-app-manifest-structure-and-the-package-of-a-sharepoint-add-in)。
  
### <a name="set-application-scope"></a>设置应用程序范围

外接程序需要该服务在查询结果中返回信息之前定义的范围或权限级别。 对于此外接程序，使用 Visual Studio 项目的以下范围。 对 AppManifest.xml 文件权限选项卡中进行此更改：

|范围|权限|
|:-----|:-----|
|多个项目 (Project Server)  <br/> |Read  <br/> |
   
设置应用程序范围后保存文件。 否则，将从服务不返回任何数据。 
  
### <a name="link-the-jsom-library"></a>链接 JSOM 库

运行时 Project Online 库，PS.js 和 PS.debug.js，提供的 Project Online 和始终是最新版本。 JavaScript 加载项使用 JSOM 必须与这些库之一链接。 在 Default.aspx 文件中添加链接的定义。 若要使用的 PS.js 和/或 PS.debug.js 的命令是代码的位于 App.js 文件中的一部分。
  
添加下面的命令中的 PS.js 或 PS.debug.js 定义`<asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead"`元素关注"sharepoint: Scriptlink"的 sp.js。 
  
```js
<SharePoint:ScriptLink name="PS.js" runat="server" OnDemand="false" LoadAfterUI="true" Localizable="false" />
```

> [!NOTE]
> PS.js 或 PS.debug.js **ondemand 时**属性设置为**false**。 
  
### <a name="add-ui-elements-to-the-add-in"></a>将 UI 元素添加到加载项

示例加载项包括几个组件。 静态元素说明位于 Default.aspx 文件中。 动态元素说明和代码的所有组件都位于 App.js 文件。 有关组件的注释，请参阅源代码清单。 下面是在外接程序的用户界面组件的列表：
  
- Title
    
- 介绍性措辞
    
- 若要从表中删除任务的按钮
    
- 列出项目 ID 和名称和任务信息的表。
    
- 任务导入到表中的任务数据的按钮 （克隆一次为每个项目）。
    
有关详细信息的用户界面中，如标题和页眉部分的项目表中，请参阅 Default.aspx 项目文件。
  
### <a name="initialize-and-connect-to-the-host-system"></a>初始化并连接到主机系统

App.js 文件包含 JavaScript 代码。 外接程序在浏览器中，加载 PS.js，然后调用 initializePage 函数。 InitializePage 检索到 Project Online 的终结点的上下文，并启动 loadProjects 函数。
  
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

### <a name="retrieve-the-projects"></a>检索项目

LoadProjects 函数查询的项目名称和 Id 的服务。 
  
应用程序检索的项目名称和项目 id。有关项目的其他信息并且可访问通过修改 load 方法来显式标识要检索的属性。 为注释代码中提供了示例。 
  
如果查询成功外, 接程序将继续通过调用 displayProjects。 
  
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

### <a name="display-the-projects"></a>显示项目

DisplayProjects 函数创建表格、 项目，每一行和按钮以显示特定项目的任务。 
  
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
> While 循环访问 ID 和 name 属性。 这是略有不同于源代码项目调用的函数，依次访问相同的属性。 
  
### <a name="display-the-tasks-for-a-project"></a>显示项目的任务

任务外, 接程序的一部分时不属于初始加载。 如果用户希望与项目关联的任务，单击"显示任务"按钮会使用 btnLoadTasks 事件处理程序的列表中显示的任务。 
  
BtnLoadTasks 事件处理程序中，具有适当的项目 ID，从服务器请求指定的项目的任务。 检索后，btnLoadTasks 会将任务列表传递给 displayTasks 演示屏幕上的任务。
  
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

DisplayTasks 函数显示与紧下方的项目项为指定项目的任务。
  
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
> While 循环访问的任务 ID 和 name 属性。 这是略有不同于源代码项目调用的函数，依次访问相同的属性。 
  
单个项目的任务的示例输出如下所示。
  
![显示项目任务的输出的屏幕截图](media/f6500a3f-000b-4f3e-9be6-9a74d0bea15e.png "显示项目任务的输出的屏幕截图")
  
## <a name="see-also"></a>另请参阅

有关文档和与 Project Online 和使用 CSOM 的应用程序开发相关的示例，请参阅[Project 开发门户](https://developer.microsoft.com/en-us/project)。
    


