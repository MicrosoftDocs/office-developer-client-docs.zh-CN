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
# <a name="developing-a-project-online-add-in-using-the-javascript-object-model-jsom"></a>使用 JAVAScript Project Online JSOM 模型开发 (加载项) 

本文介绍如何Microsoft Project Online外接程序开发来增强使用加载项Project Online。 开发项目作为演练实现。 用于本文的外接程序从 Project Online 帐户读取并显示已发布项目的项目名称和 ID，并允许您向下钻取以检索与单个项目关联的任务。
  
运行时，外接程序列表类似于下图：
  
![显示 JSOM 项目和]任务列表的屏幕截图 显示(media/766e5914-f048-48f4-9282-291f55e6e90d.png "JSOM 项目和任务列表的屏幕截图")
  
该示例的重心是与 Project Online 交互，执行查询并设置服务中每个请求的上下文。 用户界面 (UI) 元素得到最少关注。 相反，源列表会提供有关 UI 的注释。
  
> [!NOTE]
> 示例外接程序的源文件是一个Visual Studio项目，可在以下位置获得 https://github.com/OfficeDev/Project-JSOM-List-Projects-Tasks.... ： 。 阅读文章时，请保持源文件方便作为参考，因为每个源文件相互补充。 项目生成Visual Studio中的文件可执行，只需进行最少的更改，即可将 Project Online 租户的 URL 向下PWA文件夹。 
  
## <a name="background"></a>背景

Project Online是一项 Office 365 服务，可为公司提供项目组合管理 (PPM) 和项目管理办公室 (PMO) 解决方案，以协调和管理项目组合、计划和项目。 Project Online桌面版与桌面Project不同;但是，Project Online仍包含用于在整个项目生命周期中维护和跟踪项目详细信息的功能。 Project Online基于 SharePoint Online 构建。
  
托管Project Online加载项由与客户端对象模型 API 交互的 JavaScript 和资源文件组成。 用户访问外接程序时，JavaScript 和资源在浏览器中下载和执行。 无论创建、检索、更新Project Online数据，加载项都对加载项进行异步调用，以与服务进行交互。 
  
Project Online执行另一个操作来保护属于其他租户的信息免受加载项影响;即，Project Online创建一个隔离网站以与来自外接程序的请求进行交互。 主机上没有运行自定义Project Online代码。 
  
加载项的开发设置Project Online加载项使用Visual Studio SharePoint加载项项目类型。 外接程序使用 JavaScript 编写，并使用 Project JavaScript 对象模型 (JSOM) 与 Project Online 服务交互。 JSOM 从 JSOM 继承大部分SharePoint功能。
  
> [!NOTE]
> 加载项可以在应用商店中发布和出售Office或部署到 SharePoint 上的专用应用程序目录。 有关详细信息，请参阅[部署和发布Office加载项。](https://docs.microsoft.com/office/dev/add-ins/publish/publish)
> 
> 本文中使用的外接程序是开发人员的示例;它不适合在生产环境使用。 主要用途是展示一个应用开发示例，Project Online。 
  
## <a name="prerequisites"></a>必备条件

将以下项添加到受支持的Windows环境中：
  
- **.NET Framework 4.0 或** 更高版本：兼容 4.0 版框架的完整版本。 下载网站为 https://msdn.microsoft.com/vstudio/aa496123.aspx。
    
- **Visual Studio 2013或更高版本**：  
    
   - the professional edition of Visual Studio 2015 is ready to out-of the box and is available at https://www.visualstudio.com/en-us/products/visual-studio-professional-with-msdn-vs.aspx .
    
   - 2015 年 Visual Studio社区版可在 上获得 https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx 。 此版本要求手动安装 Microsoft Office 开发人员工具Visual Studio。
    
   有关Microsoft Office开发人员工具Visual Studio可在 上获得 https://www.visualstudio.com/en-us/features/office-tools-vs.aspx 。
    
- **A Project Online account**： This provides access to the hosting service. 有关获取 Project Online 帐户的详细信息，请参阅 https://products.office.com/en-us/Project/project-online-portfolio-management
    
   确保加载项用户具有足够的授权，可以访问加载项租户中的Project Online项目。 
    
- **使用信息填充的** 宿主网站上的项目。
    
> [!NOTE]
> 标准.NET Framework使用正确的框架。 请勿使用".NET Framework 4 客户端配置文件"。 
  
### <a name="set-up-the-visual-studio-project"></a>设置 Visual Studio 项目

应用程序设置包括创建新项目、链接相应的库和声明所需的命名空间。 Visual Studio 提供有多种类型的开发项目。 此部分简短且非常基本。 值使信息在一处进行并组织。
  
#### <a name="select-a-visual-studio-project"></a>选择 Visual Studio 项目

若要为加载项创建适当类型的项目，必须执行以下步骤。 屏幕上显示的关键字具有 **粗体** 属性： 
  
1. 从"文件"菜单中，选择"**文件**  >  **""**  >  **新建Project"。** 
    
2. 从左窗格中的"已安装的模板"中  >  **，C#Office/SharePoint**  >  **Web 加载项"。** 
    
3. 在中央窗格顶部，选择".NET Framework **4** 或更高版本;当前版本为 4.6。 
    
4. 从中央窗格中的应用程序类型中，SharePoint **外接程序"。** 
    
5. 在底部为项目指定名称和位置以及解决方案名称。 
    
6. 此外，在底部选中“**创建解决方案的目录**”复选框。 
    
7. 单击“**确定**”以创建初始项目。 
    
"Visual Studio 向导"会询问一些有关 Project Online 设置网站 (（称为"SharePoint 设置）"的) 在下列几个对话框中。 以下是问题：
  
1. SharePoint调试外接程序时要使用哪些网站？ 指定指向网站PWA URL，例如 https://contoso.sharepoint.com/sites/pwa 。
    
2. 您希望如何托管您的SharePoint外接程序？ 选择"[X] **SharePoint托管的 "。**
    
   有关外接程序SharePoint（包括托管选项）的详细信息，请参阅 SharePoint[外接程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)。
    
3. 点击 **“下一步”**。 
    
第二个附加对话框要求你为SharePoint指定 SharePoint Online 版本： 
  
1. 您希望外接程序面向SharePoint的最早版本是什么？ 选择[X] S **harePoint-Online**。 
    
2. 单击“完成”。 
    
Visual Studio创建项目并访问Project Online网站。 
  
### <a name="enable-sideloading-on-the-project-online-site"></a>在网站中启用Project Online加载

旁加载是测试和调试加载项Project Online机制。需要两个脚本进行旁加载：一个在 Project Online 网站上启用旁加载，另一个脚本用于完成加载项测试和调试后禁用旁加载。
  
有关设置旁加载的信息，请参阅在非开发人员网站集中 [启用应用旁加载](https://blogs.msdn.microsoft.com/officeapps/2013/12/10/enable-app-sideloading-in-your-non-developer-site-collection/)。
  
> [!NOTE]
> 旁加载应用是一项开发人员/测试功能。 它 **不适合生产用途**。 不要定期旁加载应用，或使应用旁加载的启用时间比主动使用该功能的时间长。 
  
## <a name="add-content-to-the-add-in-project"></a>向加载项项目添加内容

创建项目并设置调试机制后，向应用添加内容包括以下任务：
  
- 设置应用程序范围
    
- 链接 JSOM 库
    
- 将 UI 元素添加到外接程序
    
- 初始化并连接到 Project Online 服务
    
- 检索项目和详细信息/属性
    
- 显示项目
    
- 显示任务Project
    
加载项项目由多个文件组成。 本示例中，需要编辑以下文件： 
  
- AppManifest.xml
    
- Default.aspx
    
- App.js
    
- App.css - 可选;包含为外接程序开发的样式定义
    
如果 Project Online租户发生更改（例如从试用版移动到订阅网站）中，可以使用可通过"查看属性窗口"命令使用"属性窗口"更新项目属性，包括"服务器连接"和"网站 URL"。   >   
  
您还可以将文件添加到项目中。 如果是，则需要更新位于同一组的 Elements.xml 文件 (内容、图像、页面或脚本) 以包含新文件。 有关项目文件详细信息，请参阅浏览应用程序清单结构和加载项SharePoint[包](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/explore-the-app-manifest-structure-and-the-package-of-a-sharepoint-add-in)。
  
### <a name="set-application-scope"></a>设置应用程序范围

外接程序需要先定义范围或权限级别，然后服务才能在查询结果中返回信息。 对于此外接程序，请使用以下范围来访问Visual Studio项目。 对"权限"选项卡AppManifest.xml文件进行以下更改：

|范围|权限|
|:-----|:-----|
|多个 Projects (Project Server)   <br/> |阅读  <br/> |
   
在设置应用程序作用域后保存文件。 否则，不会从服务返回任何数据。 
  
### <a name="link-the-jsom-library"></a>链接 JSOM 库

运行时Project Online库PS.jsPS.debug.js，由 Project Online 提供，并且始终是最新版本。 使用 JSOM 的 JavaScript 加载项必须与这些库之一链接。 链接定义将添加到 Default.aspx 文件中。 用于命令和PS.js/或PS.debug.js是位于文件的代码的一App.js部分。
  
在元素中添加以下PS.js或PS.debug.js定义，该元素遵循 `<asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead"` "SharePoint：ScriptLink"sp.js。 
  
```js
<SharePoint:ScriptLink name="PS.js" runat="server" OnDemand="false" LoadAfterUI="true" Localizable="false" />
```

> [!NOTE]
> 属性 **的 OnDemand** PS.js或PS.debug.js设置为 **false**。 
  
### <a name="add-ui-elements-to-the-add-in"></a>将 UI 元素添加到外接程序

示例外接程序由几个组件组成。 静态元素说明位于 Default.aspx 文件中。 所有组件的动态元素说明和代码都位于App.js文件中。 有关组件的评论，请参阅源代码列表。 下面是外接程序中的 UI 组件列表：
  
- 标题
    
- 介绍性动词
    
- 用于从表中删除任务的按钮
    
- 列出项目 ID 和名称以及任务信息的表。
    
- 任务按钮 (每个将任务数据导入到) 的项目中克隆一次。
    
有关用户界面的详细信息（如项目表的标题和标题部分），请参阅 Default.aspx 项目文件。
  
### <a name="initialize-and-connect-to-the-host-system"></a>初始化并连接到主机系统

The App.js file contains the JavaScript code. 外接程序在浏览器中PS.js，然后调用 initializePage 函数。 InitializePage 检索到 Project Online 的上下文，并启动 loadProjects 函数。
  
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

loadProjects 函数查询服务中的项目名称和 ID。 
  
应用程序检索项目名称和项目 ID。有关项目的其他信息可用，可通过修改 load 方法以显式标识要检索的属性来访问该信息。 代码中提供了一个示例作为注释。 
  
如果查询成功，加载项将继续调用 displayProjects。 
  
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

displayProjects 函数创建一个表（每个项目一行）和一个按钮以显示特定项目的任务。 
  
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
> while 循环访问 ID 和 name 属性。 这与调用函数（反过来又访问相同属性）的源代码项目略有不同。 
  
### <a name="display-the-tasks-for-a-project"></a>显示项目的任务

虽然任务是加载项的一部分，但任务不是初始加载的一部分。 如果用户对与项目关联的任务感兴趣，单击"显示任务"按钮将导致任务使用 btnLoadTasks 事件处理程序显示在列表中。 
  
btnLoadTasks 事件处理程序（具有相应的项目 ID）从服务器请求指定项目的任务。 检索到后，btnLoadTasks 将传递任务列表以显示任务，以在屏幕上显示任务。
  
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

displayTasks 函数显示在项目项正下方与指定项目关联的任务。
  
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
> while 循环访问任务 ID 和名称属性。 这与调用函数（反过来又访问相同属性）的源代码项目略有不同。 
  
以下是单个项目的任务的示例输出。
  
![显示项目任务输出]的屏幕截图(media/f6500a3f-000b-4f3e-9be6-9a74d0bea15e.png "显示项目任务输出的屏幕截图")
  
## <a name="see-also"></a>另请参阅

有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/en-us/project)。
    


