---
title: 使用 JavaScript 对象模型 (JSOM) 开发 Project Online 外接
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4a4b1ad2-de46-421d-a698-53c20c90b93a
description: 本文介绍 Microsoft project online 外接程序开发, 以增强你对 Project online 的体验。 开发项目作为演练实现。 用于本文的外接程序从 project Online 帐户读取和显示已发布项目的项目名称和 id, 并允许您向下钻取以检索与单个项目相关联的任务。
ms.openlocfilehash: 0a472a6300f18aaa65649f44d944445642a59e1a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322682"
---
# <a name="developing-a-project-online-add-in-using-the-javascript-object-model-jsom"></a>使用 JavaScript 对象模型 (JSOM) 开发 Project Online 外接

本文介绍 Microsoft project online 外接程序开发, 以增强你对 Project online 的体验。 开发项目作为演练实现。 用于本文的外接程序从 project Online 帐户读取和显示已发布项目的项目名称和 id, 并允许您向下钻取以检索与单个项目相关联的任务。
  
在运行时, 外接列表类似于下图:
  
![显示 JSOM 项目和任务列表的屏幕截图](media/766e5914-f048-48f4-9282-291f55e6e90d.png "显示 JSOM 项目和任务列表的屏幕截图")
  
此示例的重点是与 Project Online 的交互, 使查询和为服务中的每个请求设置上下文。 用户界面 (UI) 元素获得最少的注意。 相反, 源列表提供有关 UI 的注释。
  
> [!NOTE]
> 可从以下https://github.com/OfficeDev/Project-JSOM-List-Projects-Tasks....位置获取示例外接程序 (一个 Visual Studio 项目) 的源文件。 阅读本文时, 请务必将源文件作为参考, 因为每个文件都要补充另一个文件。 Visual Studio 项目中的文件以最少的更改生成并为可执行文件—将 project Online 租户的 URL 向下替换到 PWA 文件夹。 
  
## <a name="background"></a>背景

Project Online 是一种 Office 365 服务, 它为公司提供了项目组合管理 (PPM) 和项目管理办公室 (PMO) 解决方案, 以协调和管理项目组合、程序和项目。 project Online 与 project desktop 版本是不同的解决方案;然而, project Online 仍包含在项目的整个生命周期中维护和跟踪项目详细信息的功能。 Project online 是基于 SharePoint Online 建立的。
  
Project Online 托管加载项由与客户端对象模型 API 交互的 JavaScript 和资源文件组成。 当用户访问加载项时, JavaScript 和资源将下载并在浏览器中执行。 加载项进行异步调用 Project Online, 以与服务进行交互, 无论是创建、检索、更新还是删除数据。 
  
Project Online 执行另一个操作来保护属于来自外接程序的其他租户的信息;即, Project Online 将创建一个独立的网站, 以与外接程序中的请求进行交互。 不会在 Project Online 主机上运行任何自定义代码。 
  
Project Online 外接程序的开发设置使用 Visual Studio SharePoint 外接程序项目类型。 加载项以 JavaScript 的方式编写, 并使用项目 JavaScript 对象模型 (JSOM) 与 project Online service 进行交互。 JSOM 从 SharePoint JSOM 继承了大部分功能。
  
> [!NOTE]
> 可以在 Office 应用商店中发布和销售外接程序, 也可以将其部署到 SharePoint 上的专用应用程序目录中。 有关详细信息, 请参阅[部署和发布 Office 外接程序](https://docs.microsoft.com/office/dev/add-ins/publish/publish)。
> 
> 本文中使用的外接程序是开发人员的示例;它不应在生产环境中使用。 主要目的是显示 Project Online 应用程序开发的一个示例。 
  
## <a name="prerequisites"></a>先决条件

将以下项添加到受支持的 Windows 环境:
  
- **.net Framework 4.0 或更高**版本: 版本4.0 中的 Framework 的完整版本是兼容的。 下载网站为 https://msdn.microsoft.com/vstudio/aa496123.aspx。
    
- **Visual Studio 2013 或更高版本**:  
    
   - Visual Studio 2015 专业版已准备就绪, 可在https://www.visualstudio.com/en-us/products/visual-studio-professional-with-msdn-vs.aspx中找到。
    
   - 可从https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx获取 Visual Studio 2015 的社区版。 此版本需要手动安装适用于 Visual Studio 的 Microsoft Office 开发人员工具。
    
   中提供了适用于 Visual Studio 的 Microsoft Office 开发https://www.visualstudio.com/en-us/features/office-tools-vs.aspx人员工具。
    
- **Project Online 帐户**: 它提供对托管服务的访问权限。 有关获取 Project Online 帐户的详细信息，请参阅 https://products.office.com/en-us/Project/project-online-portfolio-management
    
   确保加载项用户具有足够的权限来访问 Project Online 租户中的某些项目。 
    
- **托管网站上**使用信息填充的项目。
    
> [!NOTE]
> 标准 .net Framework 是要使用的正确框架。 请勿使用 ".net Framework 4 客户端配置文件"。 
  
### <a name="set-up-the-visual-studio-project"></a>设置 Visual Studio 项目

应用程序安装程序由创建新项目、链接适当的库和声明所需的命名空间组成。 Visual Studio 提供有多种类型的开发项目。 该部分是简短且非常基本的部分。 值是将信息合并到一个位置。
  
#### <a name="select-a-visual-studio-project"></a>选择 Visual Studio 项目

若要为外接程序创建适当类型的项目, 您必须执行以下步骤。 在屏幕上遇到的关键字具有**bold**属性: 
  
1. 从 "文件" 菜单中选择 "**文件** > " "**新建** > **项目**"。 
    
2. 从左侧窗格中的 "已安装的模板" 中, 选择 " **c #** > **Office/SharePoint** > **Web 外接程序**"。 
    
3. 在中央窗格顶部, 选择 " **.net Framework 4** " 或 "更高版本";当前版本是4.6。 
    
4. 从中央窗格中的应用程序类型中, 选择 " **SharePoint 外接程序**"。 
    
5. 在底部为项目指定名称和位置以及解决方案名称。 
    
6. 此外，在底部选中“**创建解决方案的目录**”复选框。 
    
7. 单击“**确定**”以创建初始项目。 
    
Visual Studio 向导会在下面几个对话框中询问有关 Project Online 设置网站的几个后续问题 (在对话框中称为 "SharePoint 设置")。 以下是问题:
  
1. 您要使用哪个 SharePoint 网站调试外接程序？ 指定 PWA 网站的 URL, 例如https://contoso.sharepoint.com/sites/pwa。
    
2. 你希望如何托管 SharePoint 外接程序？ 选择 "[X] **SharePoint 托管**"。
    
   有关 SharePoint 外接程序 (包括托管选项) 的详细信息, 请参阅[SharePoint 外接程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)。
    
3. 单击“下一步”。**** 
    
第二个附加对话框要求您为外接程序指定 SharePoint Online 版本: 
  
1. 您希望外接程序定位的最早版本的 SharePoint 是什么？ 选择 [X] S **harePoint-Online**。 
    
2. 单击“完成”****。 
    
Visual Studio 将创建项目并访问 project Online 网站。 
  
### <a name="enable-sideloading-on-the-project-online-site"></a>在 Project Online 网站上启用旁加载

旁加载是用于测试和调试 Project Online 外接程序的机制。您需要有两个用于旁加载的脚本: 一个用于在 Project Online 网站上启用旁加载, 另一个用于在完成测试和调试外接程序后禁用旁加载。
  
有关设置旁加载的详细信息, 请参阅[在非开发人员网站集中启用应用程序旁加载](https://blogs.msdn.microsoft.com/officeapps/2013/12/10/enable-app-sideloading-in-your-non-developer-site-collection/)。
  
> [!NOTE]
> 旁加载应用程序是一项开发/测试功能。 它**不用于生产用途**。 请勿定期旁加载应用程序, 或保持应用程序旁加载的时间超过您主动使用该功能所需的时间。 
  
## <a name="add-content-to-the-add-in-project"></a>将内容添加到加载项项目

创建项目并设置调试机制后, 向应用程序添加内容包括以下任务:
  
- 设置应用程序范围
    
- 链接 JSOM 库
    
- 向加载项添加 UI 元素
    
- 初始化和连接到 Project Online 服务
    
- 检索项目和详细信息/属性
    
- 显示项目
    
- 显示项目的任务
    
加载项项目由多个文件组成。 在此示例中, 需要编辑以下文件: 
  
- appmanifest.xml
    
- default.aspx
    
- node.js
    
- "应用程序"。 css-可选;包含为外接程序开发的样式定义
    
如果 project Online 租户发生更改 (例如, 从试用版移动到订阅网站), 则可以使用 "属性" 窗口通过**视图** > 属性更新项目属性, 包括服务器连接和网站 URL。**Window**命令。 
  
您还可以将文件添加到项目中。 如果是这样, 您需要更新位于同一组 (内容、图像、页面或脚本) 中的元素 .xml 文件, 以包含新文件。 有关项目文件的详细信息, 请参阅[探究应用部件清单 (manifest) 结构和 SharePoint 加载项的包](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/explore-the-app-manifest-structure-and-the-package-of-a-sharepoint-add-in)。
  
### <a name="set-application-scope"></a>设置应用程序范围

外接端需要在服务返回查询结果中的信息之前定义的范围或权限级别。 对于此外接程序, 请使用 Visual Studio 项目的以下范围。 对 "权限" 选项卡中的 appmanifest.xml 文件进行此更改:

|Scope|权限|
|:-----|:-----|
|多个项目 (Project Server)  <br/> |读取  <br/> |
   
在设置应用程序范围后保存文件。 否则, 服务将不会返回任何数据。 
  
### <a name="link-the-jsom-library"></a>链接 JSOM 库

运行时 project online 库、.ps 和 .ps 是由 Project online 提供的, 并且始终是最新版本。 使用 JSOM 的 JavaScript 加载项必须与这些库中的一个相链接。 将链接定义添加到默认 .aspx 文件中。 使用 PS .js 和/或 .ps 的命令是位于 app.config 文件中的代码的一部分。
  
在 ScriptLink 的 "SharePoint:" 后面的`<asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead"`元素中为 .ps 或 .ps 定义添加以下命令。 
  
```js
<SharePoint:ScriptLink name="PS.js" runat="server" OnDemand="false" LoadAfterUI="true" Localizable="false" />
```

> [!NOTE]
> 将 .ps 或 ps. .js 的**OnDemand**属性设置为**false**。 
  
### <a name="add-ui-elements-to-the-add-in"></a>向加载项添加 UI 元素

该示例加载项由几个组件组成。 静态元素说明位于默认的 .aspx 文件中。 所有组件的动态元素说明和代码都位于 app.config 文件中。 有关这些组件的注释, 请参考源代码清单。 下面是加载项中的 UI 组件的列表:
  
- 标题
    
- 介绍性措辞
    
- 用于从表格中删除任务的按钮
    
- 列出项目 ID 和名称以及任务信息的表。
    
- 将任务数据导入表中的 "任务" 按钮 (为每个项目克隆一次)。
    
有关用户界面的详细信息, 如项目表的标题和标头部分, 请参阅 default.aspx 项目文件。
  
### <a name="initialize-and-connect-to-the-host-system"></a>初始化并连接到主机系统

应用 .js 文件包含 JavaScript 代码。 加载项在浏览器中加载 PS .js, 然后调用 initializePage 函数。 InitializePage 检索 Project Online 终结点的上下文并启动 loadProjects 函数。
  
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

loadProjects 函数查询服务中的项目名称和 id。 
  
应用程序将检索项目名称和项目 Id。可通过修改 load 方法以显式标识要检索的属性来访问有关项目的其他信息。 代码中提供了一个示例作为注释。 
  
如果查询成功, 则外接程序会通过调用 displayProjects 继续进行。 
  
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

displayProjects 函数创建一个表, 每个项目一行, 并使用一个按钮来显示特定项目的任务。 
  
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
> while 循环访问 ID 和 name 属性。 这与调用函数的源代码项目略有不同, 后者又访问相同的属性。 
  
### <a name="display-the-tasks-for-a-project"></a>显示项目的任务

加载项的一部分任务不是初始加载的一部分。 如果用户对与项目相关联的任务感兴趣, 则单击 "显示任务" 按钮会导致任务使用 btnLoadTasks 事件处理程序在列表中显示。 
  
btnLoadTasks 事件处理程序 (具有相应的项目 ID) 从服务器请求指定项目的任务。 检索后, btnLoadTasks 会将任务列表传递给 displayTasks, 以在屏幕上显示任务。
  
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

displayTasks 函数显示与项目项紧下方的指定项目相关联的任务。
  
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
> while 循环访问任务 ID 和名称属性。 这与调用函数的源代码项目略有不同, 后者又访问相同的属性。 
  
下面是单个项目的任务的示例输出。
  
![显示项目任务的输出的屏幕截图](media/f6500a3f-000b-4f3e-9be6-9a74d0bea15e.png "显示项目任务的输出的屏幕截图")
  
## <a name="see-also"></a>另请参阅

有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/en-us/project)。
    


