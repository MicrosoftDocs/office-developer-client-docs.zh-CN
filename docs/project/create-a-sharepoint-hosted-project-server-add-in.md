---
title: 创建 SharePoint 托管的 Project Server 加载项
manager: lindalu
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: bb9c3c00-7121-41e1-9db3-75550d040ba8
description: 在你可以为 Project Online (自动托管、提供程序托管和 SharePoint 托管的) 创建的三种类型的应用中，SharePoint 承载的应用程序是创建和部署最简单的方法。
ms.openlocfilehash: 9b3b41eda40a8419ad72f11bb474acf7acaf81e9
ms.sourcegitcommit: 31b0a7373ff74fe1d6383c30bc67d7675b73d283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2020
ms.locfileid: "41773755"
---
# <a name="create-a-sharepoint-hosted-project-server-add-in"></a>创建 SharePoint 托管的 Project Server 加载项

在你可以为 Project Online (自动托管、提供程序托管和 SharePoint 托管的) 创建的三种类型的应用中，SharePoint 承载的应用程序是创建和部署最简单的方法。 托管SharePoint应用程序不需要 OAuth 身份验证，也不需要使用 Azure 或需要为提供程序托管的资源维护本地网站。 Visual Studio 中的 **"SharePoint 2013** 应用"模板是开发可在 Office 应用商店中发布和出售或部署到 SharePoint 上的专用应用目录的应用的便捷框架。 
  
在 Project 中，状态是一个流程，工作组成员可以使用 Project Web App 中的"任务"页提交已分配任务的状态，例如一周中每天工作该任务所花的小时数。 工作分配所有者 (项目经理) 审批或拒绝状态。 当状态为"已批准"时，Project重新计算计划。 **QuickStatus** 应用显示分配的任务，用户可以在这些任务中快速更新完成百分比并提交选定工作分配的状态进行审批。 尽管"任务"Project Web App的功能更多，**但 QuickStatus** 应用是一个提供简化界面的示例。 
  
**QuickStatus** 应用是开发人员的示例;它不适合在生产环境使用。 主要用途是演示应用程序开发示例，Project Online，而不是创建功能齐全的状态应用。 有关更好的状态方法，请参阅下一步 [中的建议](#pj15_StatusingApp_NextSteps)。
  
有关状态的常规信息，请参阅任务 [进度](https://support.office.com/article/Find-information-about-Project-Server-2013-8b08a414-15a7-4076-b2db-c90d0214ea7f?ui=en-US&rs=en-US&ad=US#BKMK_TaskProgress)。 有关为 SharePoint 和 Project 服务器开发外接程序SharePoint[请参阅](https://msdn.microsoft.com/library/jj163230.aspx)外接程序。

<a name="pj15_StatusingApp_Prerequisites"> </a>

## <a name="prerequisites-for-creating-an-app-for-project-server-2013"></a>为 Project Server 2013 创建应用程序的先决条件

若要开发可部署到 Project Online 或 Project Server 2013 本地安装中的相对简单的应用，可以使用 Napa（提供联机开发环境）。 对于更复杂的应用、修改 Project Web App 功能区以及更轻松地在开发过程中进行调试，可以使用 Visual Studio 2012 或 Visual Studio 2013。 例如，对于本地安装，您可以手动检查草稿数据表，了解 Project 服务器数据库中的更改。 本文演示如何使用 Visual Studio 进行应用开发。
  
使用 Project 开发 Visual Studio Server 应用程序需要以下各项：
  
- 确保您已在本地开发计算机上安装最新的 Service Pack 和 Windows 更新。操作系统可以是 Windows 7、Windows 8、Windows Server 2008 或 Windows Server 2012。
    
- 必须拥有已安装 SharePoint Server 2013 和 Project Server 2013 的计算机，其中计算机配置为应用隔离和旁加载应用。 通过旁加载Visual Studio可以临时安装应用进行调试。 可以使用本地安装的 SharePoint 和 Project Server。 有关详细信息，请参阅为 SharePoint[应用程序设置本地开发SharePoint。](https://msdn.microsoft.com/library/fp179923%28Office.15%29.aspx)
    
   > [!NOTE]
   > 对于本地安装，在创建企业应用程序目录之前配置独立的应用程序域。 
  
- 开发计算机可以是安装了 Office Tools for Visual Studio 2012 的远程计算机。 确保已安装最新版本;请参阅 *应用* 应用和下载 [Office SharePoint部分](https://msdn.microsoft.com/office/apps/fp123627.aspx)。
    
- 验证Project Web App用于开发和测试的实例是否可在浏览器中访问。
    
有关使用联机工具的信息，请参阅在 Office 365 上设置用于开发 SharePoint[应用程序Office 365。](https://msdn.microsoft.com/library/fp161179.aspx) 有关为使用联机工具的 Project Server 生成简单应用的演练，请参阅 EPMSource 博客系列生成首个[Project Server 应用](https://epmsource.com/2012/11/20/building-your-first-project-server-app-part-zerothe-introduction/)。

<a name="pj15_StatusingApp_UsingVisualStudio"> </a>

## <a name="using-visual-studio-to-create-a-project-server-app"></a>使用 Visual Studio 创建 Project Server 应用

Office2012 Visual Studio开发人员工具包含一个模板，SharePoint可用于 Project Server 2013 的应用。 创建应用解决方案时，该解决方案包括自定义代码的以下文件：
  
- **AppManifest.xml** 包括应用程序标题、权限请求范围和其他属性的设置。 过程 1 包括使用清单设计器设置属性的步骤。 
    
- "页面"文件夹中的 **Default.aspx** 是应用程序的主页。 过程 2 演示如何为 **QuickStatus** 应用程序添加 HTML5 内容。 
    
- **App.js** 脚本文件夹中的脚本是自定义 JavaScript 代码的主文件。 过程 3 介绍了 **QuickStatus** 应用的 JavaScript 代码。 
    
   如果添加商业控件（如基于 jQuery 的网格或日期选取器），可以在 Default.aspx 文件中添加对其他 JavaScript 文件的引用。
    
- **内容文件夹中的 App.css** 是自定义 CSS3 样式的主文件。 过程 2 和过程 3 包括有关 **QuickStatus** (CSS) 样式的级联样式表的信息。 您可以在 Default.aspx 文件中添加对其他 CSS 文件的引用。 
    
- **AppIcon.png** 图像"文件夹中的图标是应用在 Office 应用商店或应用程序目录中显示的 96 x 96 图标。 
    
若要修改Project Web App功能区，可以添加功能区自定义操作。 [QuickStatus 应用程序](#pj15_StatusingApp_Example)部分的示例代码包括修改后的 Default.aspx、App.js、App.css、Elements.xml 和 AppManifest.xml 代码。 
  
### <a name="procedure-1-to-create-an-app-project-in-visual-studio"></a>程序 1. 在应用程序中创建应用Visual Studio

1. 以Visual Studio 2012 运行 2012，然后选择"Project"页上的"新建网站"。 
    
2. 在"**新建Project** 对话框中，展开"模板"、"Visual **C#"** 和 **"Office/SharePoint"** 节点，然后选择"应用 **"。**  在中心窗格顶部的.NET Framework框架下拉列表中，使用默认的 **"4.5"，** 然后选择 **"SharePoint 2013** ("，请参阅图 1) 。 
    
3. 在"**名称**"字段中，键入 QuickStatus，浏览到要保存应用的位置，然后选择"确定 **"。**
    
   **图 1.在 Project 创建 Visual Studio Server Visual Studio**

   ![在 Visual Studio 中创建 Project Server 应用程序](media/pj15_CreateStatusingApp_NewProject.gif "在 Visual Studio 中创建 Project Server 应用程序")
  
4. 在"**新建应用程序SharePoint** 对话框中，填写以下三个字段： 
    
   - 在顶部文本框中，键入希望应用在文本框中Project Web App。 例如，键入快速状态更新。
    
   - 对于要用于调试的网站，请键入 Project Web App URL。 例如，键入 (将 `https://ServerName/ProjectServerName` _ServerName_ 和 _ProjectServerName_ 替换为您自己的值) ，然后选择"验证 **"。** 如果一切顺利，Visual Studio连接 **成功**。 如果收到错误消息，请确保 Project Web App URL 正确，并确保 Project Server 计算机配置为应用隔离和旁加载应用。 有关详细信息，请参阅[为 Project Server 2013](#pj15_StatusingApp_Prerequisites)创建应用程序的先决条件部分。 
    
   - 在 **"如何托管应用程序以** 托管SharePoint下拉列表中，选择"SharePoint **托管"。**
    
   > [!CAUTION]
   > 如果您错误地选择了默认的提供程序承载的项目类型，Visual Studio解决方案创建两个项目 **：QuickStatus** 项目和 **QuickStatusWeb** 项目。 如果看到两个项目，请删除该解决方案，然后重新开始。 
  
5. 选择 **"确定** "创建 **QuickStatus** 解决方案 **、QuickStatus** 项目和默认文件。 
    
6. 打开"清单设计器" (例如，双击"清单设计器"AppManifest.xml文件) 。 在"**常规**"选项卡上，"标题"文本框应显示你在步骤 4 中键入的应用名称。 选择 **"权限"** 选项卡，为应用程序添加以下权限 (请参阅图 2) ： 
    
   - 在"权限 **请求"列表** 的第一行的"范围"**列中，** 选择下拉列表中的"状态"。 在"**权限"** 列中，选择 **"SubmitStatus"。**
    
   - 添加一行，**其中范围** 是 **多个项目**，**权限是****读取**。
    
   **图 2.设置状态应用程序的权限范围**

   ![为状态应用程序设置权限范围](media/pj15_CreateStatusingApp_PermissionScope.gif "为状态应用程序设置权限范围")
  
**QuickStatus** 应用使Project Web App用户可以从多个项目中读取该用户的工作分配、更改工作分配完成百分比并提交更新。 此应用不需要图 2 的下拉列表中显示的其他权限请求范围。 权限请求范围是应用程序代表用户请求的权限。 如果用户在应用中没有这些权限Project Web App，则应用不会运行。 应用可以有多个权限请求范围，包括其他权限SharePoint范围，但应仅具有应用功能所需的最小范围。 以下是与 Project 服务器相关的权限请求范围： 

- **Enterprise：** 资源管理器权限，用于读取或写入有关其他用户Project Web App的信息。
    
- **多个项目**：读取或写入多个项目，其中用户具有请求的权限。
    
- **Project服务器**：要求应用用户拥有对 Project Web App 的管理员权限。
    
- **报告**：读取 **ProjectData** OData 服务Project Web App (仅需要用户登录Project Web App) 。 
    
- **单Project：** 读取或写入用户具有所请求的权限的项目。
    
- **状态：** 提交工作分配状态的更新，如工作时间、完成百分比和新分配。
    
- **工作流**：如果用户有权运行 Project 服务器工作流，则应用程序随后会使用工作流的提升权限运行。
    
有关 Project Server 2013 的权限请求范围详细信息，请参阅 updates for developers in Project [2013](updates-for-developers-in-project-2013.md)中的 Project *apps* 部分和 [SharePoint 2013 中的应用程序权限](https://msdn.microsoft.com/library/fp142383.aspx)。


<a name="pj15_StatusingApp_HTML"> </a>

### <a name="creating-the-html-content-for-the-quickstatus-app"></a>为 QuickStatus 应用程序创建 HTML 内容

在开始编写 HTML 内容代码之前，请为 QuickStatus 应用程序设计用户界面和用户体验 (图 3 显示了已完成的页面示例) 。 设计还可以包含与 HTML 代码交互的 JavaScript 函数的大纲。 有关一般信息，请参阅[UX design for apps in SharePoint 2013。](https://msdn.microsoft.com/library/fp179934.aspx)
  
**图 3.QuickStatus 应用页面的设计**

![QuickStatus 应用程序页面的设计](media/pj15_CreateStatusingApp_AfterRefresh.gif "QuickStatus 应用程序页面的设计")
  
应用在顶部显示名称标题元素的值，即 AppManifest.xml。  
  
默认情况下，页面使用 HTML5。 下面是 **QuickStatus** 应用程序在页面正文中包含的主 UI 对象的标准 HTML 元素： 
  
- 表单 **元素** 包含所有其他 UI 元素。 
    
- **fieldset** 元素为工作分配表创建容器和边框;子 **图例** 元素为容器提供标签。 
    
- 表格 **元素** 包括标题和表格标题。 JavaScript 函数更改表格标题，并添加工作分配的行。 
    
   > [!NOTE]
   > 为了轻松添加分页和排序，生产应用可能使用基于 jQuery 的商业网格控件，而不是表格。 
  
   该表包含项目名称、带复选框的任务名称、实际工时、完成百分比、剩余工时和工作分配完成日期的列。 JavaScript 函数为每个任务的完成百分比创建复选框和文本输入字段。
    
- 文本框的 **输入** 元素可设置所有选定工作分配的完成百分比。 
    
- **button** 元素提交状态更改。 
    
- **按钮** 元素刷新页面。 
    
- button 元素退出应用并返回到应用中的"任务"Project Web App。 
    
底部文本框和 button 元素位于 **div** 元素内，以便 CSS 可以轻松管理 UI 对象的位置和外观。 JavaScript 函数在页面底部添加一个段落，其中包含状态更新成功或失败的结果。 
  
### <a name="procedure-2-to-create-the-html-content"></a>程序 2. 创建 HTML 内容

1. 在Visual Studio中，打开 Default.aspx 文件。
    
   文件包含两 **个 asp：Content** 元素：具有 属性的元素添加到页面页眉中，具有 属性的元素  `ContentPlaceHolderID="PlaceHolderAdditionalPageHead"`  `ContentPlaceHolderID="PlaceHolderMain"` 放置在页面 **正文** 元素中。 
    
2. 在页面标头的控件中，添加对 PS.js Server 计算机上 Project `<asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead" runat="server">` 文件的引用。 对于测试和调试，可以使用PS.debug.js。 
    
   ```HTML
     <script type="text/javascript" src="/_layouts/15/ps.debug.js"></script>
   ```

   应用程序基础结构使用 `/_layouts/15/` IIS 中网站SharePoint虚拟目录。 物理文件为  `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.debug.js` 。
    
   > [!NOTE]
   > 在部署应用以用于生产之前，请  `.debug` 从脚本引用中删除以提高性能。 
  
3. 在  `<asp:Content ContentPlaceHolderID="PlaceHolderMain" runat="server">` 页面正文的控件中，删除生成的 **div** 元素，然后添加 UI 对象的 HTML 代码。 **table** 元素仅包含标题行。 " **任务名称** "列包括复选框输入控件。 caption **元素的文本** 将替换为文件文件中 **getUserInfo** 函数的 **onGetUserNameSuccess** App.js回调。 
    
    ```HTML
    <form>
        <fieldset>
        <legend>Select assigned tasks</legend>
        <table id="assignmentsTable">
            <caption id="tableCaption">Replace caption</caption>
            <thead>
            <tr id="headerRow">
                <th>Project name</th>
                <th><input type="checkbox" id="headercheckbox" checked="checked" />Task name</th>
                <th>Actual work</th>
                <th>% complete</th>
                <th>Remaining work</th>
                <th>Due date</th>
            </tr>
            </thead>
        </table>
        </fieldset>
        <div id="inputPercentComplete" >
        Set percent complete for all selected assignments, or leave this
        <br /> field blank and set percent complete for individual assignments: 
        <input type="text" name="percentComplete" id="pctComplete" size="4"  maxlength="4" />
        </div>
        <div id="submitResult">
        <p><button id="btnSubmitUpdate" type="button" class="bottomButtons" ></button></p>
        <p id="message"></p>
        </div>
        <div id="refreshPage">
        <p><button id="btnRefresh" type="button" class="bottomButtons" >Refresh</button></p>
        </div>
        <div id="exitPage">
        <p><button id="btnExit" type="button" class="bottomButtons" >Exit</button></p>
        </div>
    </form>
    ```

4. 在 App.css 文件中，为 UI 元素的位置和外观添加 CSS 代码。 有关 **QuickStatus** 应用程序的完整 CSS 代码，请参阅 [QuickStatus](#pj15_StatusingApp_Example) 应用程序的示例代码部分。 
    
过程 3 添加 JavaScript 函数以读取工作分配和创建表行，以及更改和更新工作分配完成百分比。 在开发应用时，实际步骤会反复进行，你可以交替创建一些 HTML 代码，添加和测试相关的样式和 JavaScript 函数，修改或添加更多 HTML 代码，然后重复此过程。

<a name="pj15_StatusingApp_JavaScript"> </a>

### <a name="creating-the-javascript-functions-for-the-quickstatus-app"></a>为 QuickStatus 应用创建 JavaScript 函数

SharePoint Visual Studio应用的 Visual Studio 模板包括 App.js 文件，该文件包含获取 SharePoint 客户端上下文并演示应用程序页面的基本获取和设置操作的默认初始化代码。 客户端客户端库SharePoint JavaScript SP.js SP **。** 因为 Project Server 应用使用 PS.js 库，所以应用使用 **PS** 命名空间获取客户端上下文并访问 Project Server 的 JSOM。 
  
**QuickStatus 应用中的 JavaScript** 函数包括： 
  
- 文档就绪 **事件** 处理程序在实例化文档对象模型 (DOM) 运行时运行。 就绪 **事件** 处理程序执行以下四个步骤： 
    
    1. 使用 Project Server JSOM 和 **pwaWeb** 全局变量的客户端上下文初始化 **projContext** 全局变量。 
        
    2. 调用 **getUserInfo** 函数以初始化 **projUser 全局** 变量。 
        
    3. 调用 **getAssignments** 函数，该函数获取用户的指定工作分配数据。 
        
    4. 将单击事件处理程序绑定到表标题复选框以及表格每行中的复选框。 当用户选择或清除表中的任何复选框时，单击事件处理程序将管理复选框的 checked 属性。 
    
- 如果 **getAssignments** 函数成功，它将调用 **onGetAssignmentsSuccess** 函数。 该函数在每个赋值的表中插入一行，初始化每一行中的 HTML 控件，然后初始化底部按钮属性。 
    
- "更新"按钮的 **onClick** 事件处理程序调用 **updateAssignments** 函数。 该函数获取应用于每个选定工作分配的完成百分比值;或者，如果"完成百分比"文本框为空，则函数获取表中每个选定工作分配的完成百分比。 然后 **，updateAssignments** 函数保存并提交状态更新，然后将有关结果的消息写入页面底部。 
    
### <a name="procedure-3-to-create-the-javascript-functions"></a>过程 3. 创建 JavaScript 函数

1. In Visual Studio， open the App.js file， and then delete all the content in the file.
    
2. 添加全局变量和文档 **就绪** 事件处理程序。 文档 **对象** 是使用 jQuery 函数访问的。 
    
   表标题的单击事件处理程序复选框设置行复选框的选中状态。 如果选中所有行复选框或清除所有复选框，则行复选框的单击事件处理程序将设置标题复选框的选中状态。 单击事件处理程序还将页面底部的结果消息设置为空字符串。
    
   ```js
    var projContext;
    var pwaWeb;
    var projUser;
    // This code runs when the DOM is ready and creates a ProjectContext object.
    // The ProjectContext object is required to use the JSOM for Project Server.
    $(document).ready(function () {
        projContext = PS.ProjectContext.get_current();
        pwaWeb = projContext.get_web();
        getUserInfo();
        getAssignments();
        // Bind a click event handler to the table header check box, which sets the row check boxes
        // to the checked state of the header check box, and sets the results message to an empty string.
        $('#headercheckbox').live('click', function (event) {
            $('input:checkbox:not(#headercheckbox)').attr('checked', this.checked);
            $get("message").innerText = "";
        });
        // Bind a click event handler to the row check boxes. If any row check box is cleared, clear
        // the header check box. If all of the row check boxes are selected, select the header check box.
        $('input:checkbox:not(#headercheckbox)').live('click', function (event) {
            var isChecked = true;
            $('input:checkbox:not(#headercheckbox)').each(function () {
                if (this.checked == false) isChecked = false;
                $get("message").innerText = "";
            });
            $("#headercheckbox").attr('checked', isChecked);
        });
    });
   ```

3. 添加 **getUserInfo** 函数，如果查询成功，将调用 **onGetUserNameSuccess。** **onGetUserNameSuccess** 函数将标题段落的内容替换为包含用户名的表格标题。 
    
   ```js
        // Get information about the current user.
        function getUserInfo() {
            projUser = pwaWeb.get_currentUser();
            projContext.load(projUser);
            projContext.executeQueryAsync(onGetUserNameSuccess,
                // Anonymous function to execute if getUserInfo fails.
                function (sender, args) {
                    alert('Failed to get user name. Error: ' + args.get_message());
            });
        } 
        // This function is executed if the getUserInfo call is successful.
        function onGetUserNameSuccess() {
            var prefaceInfo = 'Assignments for ' + projUser.get_title();
            $('#tableCaption').text(prefaceInfo);
        }
   ```

4. 添加 **getAssignments** 函数，该函数调用 **getAssignmentsSuccess** (如果分配查询成功) 请参阅步骤 5。 Include 选项将查询限制为仅返回指定的字段。 
    
   ```js
    // Get the collection of assignments for the current user.
    function getAssignments() {
        assignments = PS.EnterpriseResource.getSelf(projContext).get_assignments();
        // Register the request that you want to run on the server. The optional "Include" parameter 
        // requests only the specified properties for each assignment in the collection.
        projContext.load(assignments,
            'Include(Project, Name, ActualWork, ActualWorkMilliseconds, PercentComplete, RemainingWork, Finish, Task)');
        // Run the request on the server.
        projContext.executeQueryAsync(onGetAssignmentsSuccess,
            // Anonymous function to execute if getAssignments fails.
            function (sender, args) {
                alert('Failed to get assignments. Error: ' + args.get_message());
            });
    }
   ```

5. 添加 **onGetAssignmentsSuccess** 函数，该函数将每个工作分配的行添加到表中。 **prevProjName** 变量用于确定行是否用于其他项目。 如果是，则项目名称以粗体显示;如果没有，则项目名称设置为空字符串。 
    
   > [!NOTE]
   > JSOM 不包括 **CSOM** 包括的 TimeSpan 属性，例如 **ActualWorkTimeSpan**。 相反，JSOM 使用以毫秒为单位的属性，如 [PS。StatusAssignment.actualWorkMilliseconds](https://msdn.microsoft.com/library/736bce1e-f734-0efe-6c5f-e0e891ab00ef%28Office.15%29.aspx) 属性。 获取该属性的方法是获取 **\_ actualWorkMilliseconds**，这将返回一个整数值。 > 方法 **get_actualWork** 返回一个字符串，如"3h"。 可以在 **QuickStatus** 应用中使用任一值，但显示方式不同。 工作分配查询包括这两个属性，因此您可以在调试期间测试该值。 如果删除 **actualWork** 变量，则还可以删除工作分配查询中的 **ActualWork** 属性。 
  
   最后 **，onGetAssignmentsSuccess** 函数使用单击事件处理程序初始化"更新"按钮和"刷新"按钮。 还可以在 HTML 代码中设置 **"** 更新"按钮的文本值。 
    
   ```js
        // Get the enumerator, iterate through the assignment collection, 
        // and add each assignment to the table.
        function onGetAssignmentsSuccess(sender, args) {
            if (assignments.get_count() > 0) {
                var assignmentsEnumerator = assignments.getEnumerator();
                var projName = "";
                var prevProjName = "3D2A8045-4920-4B31-B3E7-9D0C5195FC70"; // Any unique name.
                var taskNum = 0;
                var chkTask = "";
                var txtPctComplete = "";
                // Constants for creating input controls in the table.
                var INPUTCHK = '<input type="checkbox" class="chkTask" checked="checked" id="chk';
                var LBLCHK = '<label for="chk';
                var INPUTTXT = '<input type="text" size="4"  maxlength="4" class="txtPctComplete" id="txt';
                while (assignmentsEnumerator.moveNext()) {
                    var statusAssignment = assignmentsEnumerator.get_current();
                    projName = statusAssignment.get_project().get_name();
                    // Get an integer, such as 3600000.
                    var actualWorkMilliseconds = statusAssignment.get_actualWorkMilliseconds(); 
                    // Get a string, such as "1h". Not used here.
                    var actualWork = statusAssignment.get_actualWork();
                    if (projName === prevProjName) {
                        projName = "";
                    }
                    prevProjName = statusAssignment.get_project().get_name();
                    // Create a row for the assignment information.
                    var row = assignmentsTable.insertRow();
                    taskNum++;
                    // Create an HTML string with a check box and task name label, for example:
                    // <input type="checkbox" class="chkTask" checked="checked" id="chk1" /> <label for="chk1">Task 1</label>
                    chkTask = INPUTCHK + taskNum + '" /> ' + LBLCHK + taskNum + '">' 
                        + statusAssignment.get_name() + '</label>';
                    txtPctComplete = INPUTTXT + taskNum + '" />';
                    // Insert cells for the assignment properties.
                    row.insertCell().innerHTML = '<strong>' + projName + '</strong>';
                    row.insertCell().innerHTML = chkTask;
                    row.insertCell().innerText = actualWorkMilliseconds / 3600000 + 'h';
                    row.insertCell().innerHTML = txtPctComplete;
                    row.insertCell().innerText = statusAssignment.get_remainingWork();
                    row.insertCell().innerText = statusAssignment.get_finish();
                    // Initialize the percent complete cell.
                    $get("txt" + taskNum).innerText = statusAssignment.get_percentComplete() + '%'
                }
            }
            else {
                $('p#message').attr('style', 'color: #0f3fdb');     // Blue text.
                $get("message").innerText = projUser.get_title() + ' has no assignments'
            }
            // Initialize the button properties.
            $get("btnSubmitUpdate").onclick = function() { updateAssignments(); };
            $get("btnSubmitUpdate").innerText = 'Update';
            $get('btnRefresh').onclick = function () { window.location.reload(true); };
            $get('btnExit').onclick = function () { exitToPwa(); };
        }
   ```

6. 为 **"更新"按钮添加 updateAssignments** 单击 **事件** 处理程序。 当用户更改任务的完成百分比值，或在 **percentComplete** 文本框中添加值时，该值可以输入多种格式，例如"60"、"60%"或"60%"。 **getNumericValue** 方法返回输入文本的数值。 
    
   > [!NOTE]
   > 在专为生产用途设计的应用中，数值信息的输入值应包括字段验证和其他错误检查。 
  
   **updateAssignments** 示例包括一些基本错误检查，并显示页面底部的消息段落中的信息-如果更新查询成功，则为绿色;如果输入错误或更新查询不成功，则显示为红色。 
    
   在使用 **submitAllStatusUpdates** 方法之前，应用必须使用 PS 将更新保存到 **服务器。StatusAssignmentCollection.update** 方法。 
    
   ```js
        // Update all checked assignments. If the bottom percent complete field is blank,
        // use the value in the % complete field of each selected row in the table.
        function updateAssignments() {
            // Get percent complete from the bottom text box.
            var pctCompleteMain = getNumericValue($('#pctComplete').val()).trim();
            var pctComplete = pctCompleteMain;
            var assignmentsEnumerator = assignments.getEnumerator();
            var taskNum = 0;
            var taskRow = "";
            var indexPercent = "";
            var doSubmit = true;
            while (assignmentsEnumerator.moveNext()) {
                var pctCompleteRow = "";
                taskRow = "chk" + ++taskNum;
                if ($get(taskRow).checked) {
                    var statusAssignment = assignmentsEnumerator.get_current();
                    if (pctCompleteMain === "") {
                        // Get percent complete from the text box field in the table row.
                        pctCompleteRow = getNumericValue($('#txt' + taskNum).val());
                        pctComplete = pctCompleteRow;
                    }
                    // If both percent complete fields are empty, show an error.
                    if (pctCompleteMain === "" && pctCompleteRow === "") {
                        $('p#message').attr('style', 'color: #e11500');     // Red text.
                        $get("message").innerHTML =
                            '<b>Error:</b> Both <i>Percent complete</i> fields are empty, in row '
                            + taskNum
                            + ' and in the bottom textbox.<br/>One of those fields must have a valid percent.'
                            + '<p>Please refresh the page and try again.</p>';
                        doSubmit = false;
                        taskNum = 0;
                        break;
                    }
                    if (doSubmit) statusAssignment.set_percentComplete(pctComplete);
                }
            } 
            // Save and submit the assignment updates.
            if (doSubmit) {
                assignments.update();
                assignments.submitAllStatusUpdates();
                projContext.executeQueryAsync(function (source, args) {
                    $('p#message').attr('style', 'color: #0faa0d');     // Green text.
                    $get("message").innerText = 'Assignments have been updated.';
                }, function (source, args) {
                    $('p#message').attr('style', 'color: #e11500');     // Red text.
                    $get("message").innerText = 'Error updating assignments: ' + args.get_message();
                });
            }
        }
        // Get the numeric part for percent complete, from a string. For example, with "20 %", return "20".
        function getNumericValue(pctComplete) {
            pctComplete = pctComplete.trim();
            pctComplete = pctComplete.replace(/ /g, "");    // Remove interior spaces.
            indexPercent = pctComplete.indexOf('%', 0);
            if (indexPercent > -1) pctComplete = pctComplete.substring(0, indexPercent);
            return pctComplete;
        }
   ```

7. 添加 **exitToPwa** 函数，该函数使用 **SPHostUrl** 查询字符串参数作为网站宿主Project Web App URL。 若要导航回"任务"页，请  `"/Tasks.aspx"` 追加到 URL。 例如 **，spHostUrl** 变量将设置为  `https://ServerName/ProjectServerName/Tasks.aspx` 。
    
   **getQueryStringParameter** 函数拆分 **QuickStatus** 页的 URL，以提取和返回 URL 选项中的指定参数。 下面是一个文档 **示例。** **QuickStatus** 文档的 URL (全部位于一行) ： 
    
   ```HTML
    https://app-ef98082fa37e3c.servername.officeapps.selfhost.corp.microsoft.com/pwa/
        QuickStatus/Pages/Default.aspx
        ?SPHostUrl=https%3A%2F%2Fsphvm%2D85178%2Fpwa
        &SPLanguage=en%2DUS
        &SPClientTag=1
        &SPProductNumber=15%2E0%2E4420%2E1022
        &SPAppWebUrl=https%3A%2F%2Fapp%2Def98082fa37e3c%2Eservername
            %2Eofficeapps%2Eselfhost%2Ecorp%2Emicrosoft%2Ecom%2Fpwa%2FQuickStatus
   ```

   对于之前的 **URL，getQueryStringParameter** 函数返回 **SPHostUrl** 查询字符串值  `https://ServerName/pwa` 。 
    
   ```js
        // Exit the QuickStatus page and go back to the Tasks page in Project Web App.
        function exitToPwa() {
            // Get the SharePoint host URL, which is the top page of PWA, and add the Tasks page.
            var spHostUrl = decodeURIComponent(getQueryStringParameter('SPHostUrl'))
                            + "/Tasks.aspx";
            // Set the top window for the QuickStatus IFrame to the Tasks page.
            window.top.location.href = spHostUrl;
        }
        // Get a specified query string parameter from the {StandardTokens} URL option string.
        function getQueryStringParameter(urlParameterKey) {
            var docUrl = document.URL;
            var params = docUrl.split('?')[1].split('&');
            for (var i = 0; i < params.length; i++) {
                var theParam = params[i].split('=');
                if (theParam[0] == urlParameterKey)
                    return decodeURIComponent(theParam[1]);
            }
        }
   ```

如果此时发布 **QuickStatus** 应用并将其添加到 Project Web App，该应用可以从"网站内容"页运行，但用户无法轻松使用该应用程序。 若要帮助用户查找和运行该应用程序，可以将该应用的按钮添加到"任务"页上的功能区。 过程 4 演示如何添加功能区自定义操作。 

<a name="pj15_StatusingApp_ribbon"> </a>

### <a name="adding-a-ribbon-custom-action"></a>添加功能区自定义操作

在 pwaribbon.xml 文件中指定用于Project Web App的功能区选项卡、组和控件，该文件安装在运行 `[Program Files]\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\FEATURES\PWARibbon\listtemplates` Project Server 的计算机上目录中。 为了帮助设计 Project Web App 功能区的自定义操作，Project 2013 SDK 下载包括 pwaribbon.xml。 
  
Project Web App"任务"页使用不同的功能区定义，具体取决于 Project Web App 实例是否使用单输入模式，该模式使用户能够为时间表和任务状态输入值。 如果您具有对 Project Web App 的管理权限，若要确定输入模式，请选择PWA 设置右上角的下拉列表设置菜单中的"设置"。 On the PWA 设置 page， choose **Timesheet 设置 and Defaults**， and then look at the **Single Entry Mode** check box at the bottom of the page. 
  
关闭单输入模式时，"任务"页上的功能区由"我的工作"区域pwaribbon.xml： 
  
```XML
   <!-- REGION My Work Ribbon-->
   <CustomAction
      Id="Ribbon.ContextualTabs.MyWork"
      . . .
```

当单输入模式打开时，任务页面功能区由任务页中的"绑定模式"区域pwaribbon.xml： 
  
```XML
   <!-- REGION Tied Mode Ribbon-->
   <CustomAction
      Id="Ribbon.ContextualTabs.TiedMode"
      . . .
```

尽管每个区域中的组和控件看起来相似，但绑定模式的控件可以调用与非绑定模式相同的控件不同的函数。 过程 4 演示如何在单输入模式关闭时为 **QuickStatus** 应用添加按钮控件 ("单输入模式"复选框) 。 
  
> [!NOTE]
> 有关向功能区或 SharePoint 应用程序中的菜单添加自定义操作的常规信息，请参阅创建自定义操作以部署与[SharePoint。](https://msdn.microsoft.com/library/jj163954.aspx) 
  
### <a name="procedure-4-to-add-a-ribbon-custom-action-to-the-tasks-page"></a>过程 4. 将功能区自定义操作添加到"任务"页

1. 检查"任务"页上的功能区Project Web App。 选择功能 **区** 上的"任务"选项卡并规划如何修改它。 有七个组，如 **"提交"、"****任务**"和"**时间段"。** " **提交** "组有两个控件，一个 **"** 保存" **按钮和一** 个"发送状态"下拉菜单。 可以在组内的任何位置添加控件，在"任务"选项卡的任何位置添加包含新控件的组，或者添加另一个包含自定义组和控件的功能区选项卡。 此示例向"提交"组添加第三个按钮，其中按钮调用 **QuickStatus** 应用的 URL。 
    
2. 在"**解决方案资源管理器**"窗格中Visual Studio，右键单击 **QuickStatus** 项目，然后添加新项。 在" **添加新项"对话框中** ，选择"功能区 **自定义** 操作 (请参阅图 4) 。 例如，将自定义操作命名为 RibbonQuickStatusAction，然后选择"添加 **"。**
    
   **图 4.添加功能区自定义操作**

   ![添加功能区自定义操作](media/pj15_CreateStatusingApp_AddRibbonCustomAction.gif "添加功能区自定义操作")
  
3. 在"为功能区创建自定义操作"向导的第一页上，将"主机 **Web"** 选项保持选中状态，在自定义操作范围的下拉列表中选择"无"，然后选择"下一步 (参见图 5) 。 下拉列表中的项与列表项SharePoint，与Project服务器相关。 我们将替换自定义操作生成的大部分 XML，以便它适用于 Project Server。 
    
   **图 5.指定功能区自定义操作的属性**

   ![指定功能区自定义操作的属性](media/pj15_CreateStatusingApp_RibbonCustomAction2.gif "指定功能区自定义操作的属性")
  
4. 在"为功能区创建自定义操作"向导的下一页上，保留设置的所有默认值，然后选择"完成 (请参阅图6) 。 Visual Studio创建 **RibbonQuickStatusAction** 文件夹，其中包含Elements.xml文件。 
    
   **图 6.指定按钮控件的设置**

   ![指定按钮控件的设置](media/pj15_CreateStatusingApp_RibbonCustomAction3.gif "指定按钮控件的设置")
  
5. 修改功能区自定义操作Elements.xml文件中默认生成的代码。 以下是默认的 XML 代码：
    
   ```XML
    <?xml version="1.0" encoding="utf-8"?>
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">
        <CustomAction Id="21ea3aaf-79e5-4aac-9479-8eef14b4d9df.RibbonQuickStatusAction"
                    Location="CommandUI.Ribbon"
                    Sequence="10001"
                    Title="Invoke &apos;RibbonQuickStatusAction&apos; action">
        <CommandUIExtension>
            <!-- 
            Update the UI definitions below with the controls and the command actions
            that you want to enable for the custom action.
            -->
            <CommandUIDefinitions>
            <CommandUIDefinition Location="Ribbon.ListItem.Actions.Controls._children">
                <Button Id="Ribbon.ListItem.Actions.RibbonQuickStatusActionButton"
                        Alt="Request RibbonQuickStatusAction"
                        Sequence="100"
                        Command="Invoke_RibbonQuickStatusActionButtonRequest"
                        LabelText="Request RibbonQuickStatusAction"
                        TemplateAlias="o1"
                        Image32by32="_layouts/15/images/placeholder32x32.png"
                        Image16by16="_layouts/15/images/placeholder16x16.png" />
            </CommandUIDefinition>
            </CommandUIDefinitions>
            <CommandUIHandlers>
            <CommandUIHandler Command="Invoke_RibbonQuickStatusActionButtonRequest"
                                CommandAction="~appWebUrl/Pages/Default.aspx"/>
            </CommandUIHandlers>
        </CommandUIExtension >
        </CustomAction>
    </Elements>
   ```

   1. 在 **CustomAction 元素** 中，删除 **Sequence** 属性和 **Title** 属性。 
    
   2. 若要向"提交"组添加控件，请查找集合中的第一个组pwaribbon.xml文件，该文件是开始的元素 `Ribbon.ContextualTabs.MyWork.Home.Groups` `<Group Id="Ribbon.ContextualTabs.MyWork.Home.Page" Command="PageGroup" Sequence="10" Title="$Resources:pwafeatures,PAGE_PDP_CM_SUBMIT"` 。 若要将子控件添加到 **"** 提交"组，以下代码显示"提交"文件中 **CommandUIDefinition** 元素Elements.xml属性： 
    
      ```XML
        <CommandUIDefinitions>
          <CommandUIDefinition Location="Ribbon.ContextualTabs.MyWork.Home.Page.Controls._children">
             . . .
          </CommandUIDefinition>
        </CommandUIDefinitions>
      ```

   3. 更改子 **Button** 元素的属性值，如下所示： 
    
       ```XML
            <Button Id="Ribbon.ContextualTabs.MyWork.Home.Page.QuickStatus"
                    Alt="Quick Status app"
                    Sequence="30"
                    Command="Invoke_QuickStatus"
                    LabelText="Quick Status"
                    TemplateAlias="o1"
                    Image16by16="_layouts/15/1033/images/ps16x16.png" 
                    Image16by16Left="-80"
                    Image16by16Top="-144"
                    Image32by32="_layouts/15/1033/images/ps32x32.png" 
                    Image32by32Left="-32"
                    Image32by32Top="-288" 
                    ToolTipTitle="QuickStatus"
                    ToolTipDescription="Run the QuickStatus app" />
       ```

       - 若要使按钮成为组中第三个控件 **，Sequence** 属性可以比现有"发送状态"控件值高任意数字 (该控件是 pwaribbon.xml) 中的 `Sequence="20"` **FlyoutAnchor** 元素。  根据惯例，组和控件的序列号为 ，这允许  `10, 20, 30, …` 元素插入到中间位置。
    
       - Command 属性指定在 **CommandUIHandler** 元素中运行的命令 (请参阅以下步骤 5.d) 。 您可以简化命令名称，以便让下一位开发人员更轻松地操作。 例如  `Command="Invoke_QuickStatus"` ，比 更易于阅读  `Command="Invoke_RibbonQuickStatusActionButtonRequest"` 。
    
       - 图像属性指定按钮控件的 16 x 16 像素图标和 32 x 32 像素的图标。 在默认Elements.xml文件中  `Image32by32="_layouts/15/images/placeholder32x32.png"` ，指定一个橙色点。 可以从运行 (ps16x16.png Server ps32x32.png) 的目录中的图像映射文件中提取 `[Program Files]\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\1033\IMAGES` 图标Project文件。 例如，32 x 32 像素图标位于第二列图标的左侧，第十行从 ps32x32.png 图像映射的顶部向下 (该图标的顶部位于第九行的末尾之后;9 行 x 32 像素/行 = 288 像素) 。 
    
       - 若要显示按钮控件的工具提示，请添加 **ToolTipTitle** 属性和 **ToolTipDescription** 属性。 
    
    4. 更改 **CommandUIHandler 元素** 的属性。 例如，确保 **Command** 属性与 **Button** 元素的 Command **属性值相匹配** 。 对于 **CommandAction** 属性，  `~appWebUrl` 是 **QuickStatus** 网页的 URL 的占位符。 当功能区按钮调用 **QuickStatus** 应用时 **，{StandardTokens}** 令牌将替换为包含 SPHostUrl、SPLanguage、SPClientTag、SPProductNumber 和 **SPAppWebUrl** 的 URL 选项。    
    
        ```XML
            <CommandUIHandlers>
                <CommandUIHandler Command="Invoke_QuickStatus"
                                  CommandAction="~appWebUrl/Pages/Default.aspx?{StandardTokens}"/>
            </CommandUIHandlers>
        ```

6. 在 **"解决方案资源管理器**"中，打开 **Feature1.feature** 设计器，将"解决方案"窗格中的"项目"中的 **"RibbonQuickStatusAction"** 项移到"功能"**窗格中的"项**"。 如果随后打开 **Package.package** 设计器 **，RibbonQuickStatusAction** 项将包含于"程序包 **"窗格中的"项目** "中。 
    
在开发应用并添加功能区按钮时，通常会测试应用，在 JavaScript 代码中设置断点进行调试。 按 **F5** 开始调试时，Visual Studio 编译应用程序，将其部署到 **QuickStatus** 项目的 Site **URL** 属性中指定的网站，并显示询问您是否信任该应用程序的页面。 当你继续然后退出 **QuickStatus** 应用时，它将返回到 Project Web App 中的任务Project Web App。 

> [!NOTE]
> 图 7 显示功能 **区的** "任务" **选项卡上的** "快速状态"按钮已禁用。 在使用 Visual Studio多次调试部署后，当您继续在同一测试服务器上调试或部署已发布的应用时，自定义功能区控件可能会被阻止。 若要启用该按钮，请删除功能区中的 **RibbonQuickStatusAction** Visual Studio，然后创建一个名称和 ID 不同的新功能区操作。 如果无法解决问题，请尝试从测试实例中删除Project Web App，然后使用不同的应用 ID 重新创建应用。 
  
**图 7.查看已禁用的快速状态按钮的工具提示**

![查看禁用按钮的工具提示](media/pj15_CreateStatusingApp_ButtonToolTipDisabled.gif "查看禁用按钮的工具提示")
  
过程 5 显示如何部署和安装 **QuickStatus** 应用程序。 过程 6 显示安装应用后测试应用时的额外步骤。 

<a name="pj15_StatusingApp_Deploying"> </a>

## <a name="deploying-the-quickstatus-app"></a>部署 QuickStatus 应用

有几种方法将应用部署到 SharePoint Web 应用程序（如 Project Web App）。 使用哪种部署将取决于是希望将应用发布到专用 SharePoint 目录还是公共 Office 应用商店，以及 SharePoint 是在本地安装还是联机租赁。 过程 5 演示如何将 **QuickStatus** 应用程序部署到专用应用程序目录中的本地安装。 有关详细信息，请参阅 Install [and manage apps for SharePoint 2013](https://technet.microsoft.com/library/fp161232.aspx)和 Publish apps for [SharePoint](https://msdn.microsoft.com/library/jj164070.aspx)
  
> [!NOTE]
> 将应用程序添加到应用程序SharePoint需要SharePoint管理员权限。 
  
### <a name="procedure-5-to-deploy-the-quickstatus-app"></a>过程 5. 部署 QuickStatus 应用

1. In Visual Studio， save all of the files， and then right-click the **QuickStatus** project in the **Solution Explorer** and choose **Publish**.
    
2. 由于 **QuickStatus** 应用SharePoint托管，因此只有很少的发布 (请参阅图 8) 。 在"**发布Office和SharePoint** 对话框中，选择"完成 **"。**
    
   **图 8.发布 QuickStatus 应用**

   ![使用发布向导](media/pj15_CreateStatusingApp_PublishWizard.gif "使用发布向导")
  
3. 将 QuickStatus.app 文件从目录复制到本地计算机 (或 SharePoint 计算机上用于本地安装 `~\QuickStatus\bin\Debug\app.publish\1.0.0.0`) 。 
    
4. 在SharePoint管理中心"中 **，选择"** 快速启动"中的"应用程序"，然后选择"**管理应用程序目录"。**
    
5. 如果应用程序目录不存在，则按照在 SharePoint 2013 中管理应用程序目录中的为 Web 应用程序配置应用程序目录网站[部分操作，为应用程序目录创建网站](https://technet.microsoft.com/library/fp161234.aspx)集。
    
   如果存在应用程序目录，请导航到"管理应用程序目录"页上的网站 URL。 例如，在以下步骤中，应用程序目录网站为  `https://ServerName/sites/TestApps` 。
    
6. 在应用程序目录页面上，在"快速启动 **"SharePoint"** 应用程序应用程序"。 On the Apps for SharePoint page， on the **FILES** tab of the ribbon， choose **Upload Document**.
    
7. 在 **"添加文档"** 对话框中，浏览 QuickStatus.app 文件，添加版本的注释，然后选择"确定 **"。**
    
8. 添加应用时，还可以添加应用说明、图标和其他信息的本地信息。 在 **"SharePoint - QuickStatus.app"** 对话框中，添加要显示的应用程序在网站集中SharePoint的信息。 例如，添加以下信息： 
    
   1. **简短说明** 字段：键入快速状态测试应用程序。
    
   2. **说明** 字段：键入测试应用以更新多个项目中任务的完成百分比。
    
   3. **图标 URL** 字段：将应用图标的 96 x 96 像素图像添加到应用程序目录的网站资产。 例如，导航到 ，在"网站设置菜单中选择"网站内容"，选择"网站资产"，然后添加quickStatusApp.png `https://ServerName/sites/TestApps` 图像。    右键单击 **quickStatusApp** 项，选择"属性"，然后复制"属性" (**url**) "**值。** 例如，复制  `https://ServerName/sites/TestApps/SiteAssets/QuickStatusApp.png` ，然后将值粘贴到"图标 **URL** Web 地址"字段中。 键入图标的说明，例如 (如图 9 所示) QuickStatus 应用图标。 测试 URL 是否有效。
    
      **图 9.为 QuickStatus 应用添加图标 URL**

      ![在 SharePoint 中为应用程序设置属性](media/pj15_CreateStatusingApp_AddAppToSharePointSettings.gif "在 SharePoint 中为应用程序设置属性")
  
   4. **类别** 字段：选择现有类别，或指定您自己的值。 例如，键入 Statusing。
    
      > [!NOTE]
      > 名为 **Statusing** 的类别仅出于测试目的。 服务器应用的典型类别Project管理Project **类别**。 
  
   5. **Publisher名称** 字段：键入发布者的名称。 在此示例中，键入 Project SDK。
    
   6. **已启用** 字段：若要使应用对网站Project Web App可见，请选中"**已启用**"复选框。 
    
   7. 其他字段是可选的。 例如，你可以为应用详细信息页面添加一个支持 URL 和多个帮助图像。 在图 9 中，" **图像 URL 1"** 字段包括应用程序的屏幕截图的 URL 和屏幕截图的说明。 
    
   8. 在 **"SharePoint - QuickStatus.app"** 对话框中，选择"保存 **"。** 在图 9 中，"SharePoint 应用程序"库中的"快速状态更新"项已签出进行编辑，因此在对话框功能区的"编辑"选项卡上，可以选择"签入"以完成此过程 (请参阅图 10) 。  
    
      **图 10.QuickStatus 应用将添加到应用程序 for SharePoint 库。**

      ![将 QuickStatus 应用程序添加到 SharePoint](media/pj15_CreateStatusingApp_AddAppToSharePoint.gif "将 QuickStatus 应用程序添加到 SharePoint")
  
9. In Project Web App， in the **设置** drop-down menu， choose **Add an app**. 在"你的应用"页上的"快速启动"中，选择"**自你的** 组织"，然后选择"快速状态 **更新"应用的应用详细信息**。 图 11 显示了包含应用程序图标、屏幕截图以及你在上一步中添加的其他信息的详细信息页面。 
    
   **图 11.使用"快速状态更新详细信息"页Project Web App**

   ![将 QuickStatus 应用程序添加到 Project Web App](media/pj15_CreateStatusingApp_AddAppToPWA.gif "将 QuickStatus 应用程序添加到 Project Web App")
  
10. 在"快速状态更新详细信息"页上，选择"**添加 IT"。** Project Web App显示一个对话框，其中列出了 QuickStatus 应用可 (执行的操作，请参阅图 12) 。 操作列表派生自应用程序文件中 **AppPermissionRequest** AppManifest.xml元素。 
    
    **图 12.验证您是否信任快速状态应用程序**

    ![验证对 QuickStatus 应用程序的信任](media/pj15_CreateStatusingApp_AddAppToPWA2Trust.gif "验证对 QuickStatus 应用程序的信任")
  
11. 在"**是否信任快速状态更新**"对话框中，选择"**信任它"。** 应用程序已添加到"网站内容Project Web App页 (图 13) 。
    
    **图 13.在"网站内容"页上查看"快速状态"应用**

    ![在“网站内容”中查看 QuickStatus 应用程序](media/pj15_CreateStatusingApp_AddAppToPWA3.gif "在“网站内容”中查看 QuickStatus 应用程序")
  
在"网站内容"页上，可以选择"快速 **状态更新** "图标来运行应用程序。

> [!NOTE]
> 有关提供有关应用程序信息的其他命令，在"网站内容"页上，选择包含"快速状态更新"名称和省略号 (...) 。你可以查看应用的"关于"页面、查看包含有关应用程序错误的信息的"应用程序详细信息"页、查看应用程序权限页面，或者从应用程序中删除Project Web App。 
  
在"任务"页上Project Web App (参阅图 14) ，应在功能区上启用 **QuickStatus** 按钮。 如果 **禁用了** "快速状态"按钮，请尝试图 7 的注释中描述的操作。 

**图 14.从"任务"选项卡启动 QuickStatus 应用**

![从“任务”选项卡启动 QuickStatus 应用程序](media/pj15_CreateStatusingApp_TasksRibbon.gif "从“任务”选项卡启动 QuickStatus 应用程序")
  
过程 6 演示了使用 QuickStatus 应用要进行的一些测试。

<a name="pj15_StatusingApp_Testing"> </a>

## <a name="testing-the-quickstatus-app"></a>测试 QuickStatus 应用

在将应用部署到生产服务器或 Project Online 的生产租户之前，应在 Project Server 的测试安装上测试用户可能尝试在 **QuickStatus** 应用中执行的每一个操作。 通过测试安装，您可以更改和删除用户的分配，而不会影响实际项目。 测试还应涉及具有不同权限集的几个用户，例如管理员、项目经理和工作组成员。 全面的测试可以发现应在应用中所做的更改，这些更改在开发期间在测试中并不明显。 过程 6 列出了 **QuickStatus** 应用程序的多个测试，但不包括一系列详尽的测试。 
  
### <a name="procedure-6-to-test-the-quickstatus-app"></a>过程 6. 测试 QuickStatus 应用

1. 运行 **用户没有工作分配的 QuickStatus** 应用。 应用应在页面底部显示一条蓝色消息，例如，" **用户名"没有分配**。
    
   选择 **"更新**"，且对绿色"工作分配 **"的邮件更改已更新**。
    
   > [!NOTE]
   > 应更改应用行为，以便当没有分配时禁用"更新"按钮。 
  
2. 运行用户在多个不同项目中具有多个工作分配且某些工作分配无法完成的应用。 请注意应用程序的外观并执行如下操作 (参见图 15) ：
    
   1. **onGetAssignmentsSuccess** 函数在表中为当前用户的每个工作分配创建一行。 每个项目的第一个工作分配的项目名称只以粗体显示一次。 
    
   2. 清除"任务名称" **列标题** 中的复选框。 表标题单击事件处理程序清除任务行中的所有其他复选框。 
    
   3. 选择所有任务。 每行的单击事件处理程序确定是否选择了所有行，如果是，则选择 **"任务** 名称"列标题。 
    
   4. 再次清除所有复选框，然后选择一个剩余工时的工作分配。 例如，图 15 显示了顶部任务 T1 有 20% 的剩余工作要完成。
    
   5. 在"**设置完成百分比**"文本框中，键入 80，然后选择"更新 **"。** 页面底部应显示绿色消息， **分配已更新**。
    
      **图 15.在 QuickStatus 应用中更新分配**

      ![更新 QuickStatus 应用程序中的工作分配](media/pj15_CreateStatusingApp_Testing1Update.gif "更新 QuickStatus 应用程序中的工作分配")
  
3. 选择 **"刷新** (请参阅图 16) 。 将再次选择所有任务，顶部任务显示已完成 80%。 
    
      **图 16.刷新"快速状态更新"页**

      ![刷新 QuickStatus 页面](media/pj15_CreateStatusingApp_Testing2Refresh.gif "刷新 QuickStatus 页面")
  
4. 清除所有复选框，然后选择其他任务。 例如，从"新建 **任务"PWA。** 将"**设置完成百分比**"文本框保留为空，删除选定任务的"**完成百** 分比"列中的所有文本，然后选择"更新 **"。** 由于这两个文本框都为空，因此应用会显示一条红色 (请参阅图 17) 。
    
      **图 17.测试错误消息**

      ![测试错误消息](media/pj15_CreateStatusingApp_Testing3Error.gif "测试错误消息")
  
5. 将上一个任务更新为已完成 80%，然后选择"退出 **"。** **exitToPwa** 函数将浏览器窗口位置SharePoint主机应用程序中的"任务 (，即 URL 会更改 https://ServerName/pwa/Tasks.aspx) 。 图 18 显示 **T1** 任务和任务中的"新建 **PWA任务都** 显示 80% 已完成。 
    
      **图 18.验证任务是否已在任务Project Web App**

      ![验证 Project Web App 中的已更新任务](media/pj15_CreateStatusingApp_TasksUpdatedInPWA.gif "验证 Project Web App 中的已更新任务")
  
6. 在 2013 年 10 月更新状态Project Professional，必须提交更改进行审批，然后由项目经理批准。
    
测试显示应在 **QuickStatus** 应用中进行的其他一些更改，以提高可用性。 例如：

- 应进行其他错误检查和文本框值的验证。 目前，用户可以为完成百分比输入非数值或负值，这导致不友好的错误消息。 例如，对于负值，错误消息为错误更新 **分配： PJClientCallableException： StatusingSetDataValueInvalid**。
    
- 空白文本框的错误消息可能会列出项目和任务以及行号。
    
- 成功消息可能包括更新的任务列表;或者， **如果 updateAssignments** 函数成功，它可以执行自动页面刷新，并使用不同的颜色和粗体显示更新的任务或百分比。 
    
- 为避免表过大，工作分配表应限制为小于 100% 完成的任务。 或者，添加一个选项以显示所有任务。 使用基于 jQuery 的网格（而不是表）也可以解决此问题，可在其中轻松实现筛选和网格分页。
    
- 由于 **QuickStatus** 应用不提交状态，因此功能区"**任务**"选项卡上的"快速状态"图标在逻辑上更可能是"任务"组的第一个图标，而不是"提交"组中最后一 **个图标。** 
    
- 由于 **onGetAssignmentsSuccess** 函数初始化 **btnSubmitUpdate** 按钮文本，但其他按钮文本值以 HTML 格式初始化，因此在 **运行 getAssignments** 函数时，页面将处于部分初始化状态。 如果文本值全部以 HTML 格式初始化，则页面上的按钮看起来更加一致。 
    
最重要的是 **，QuickStatus** 应用使用的方法（更改作业的完成百分比）应在生产应用中进行修改。 有关详细信息，请参阅"下 [一步"](#pj15_StatusingApp_NextSteps) 部分。 

<a name="pj15_StatusingApp_Example"> </a>

## <a name="example-code-for-the-quickstatus-app"></a>QuickStatus 应用的示例代码

### <a name="defaultaspx-file"></a>Default.aspx 文件

以下代码位于  `Pages\Default.aspx` **QuickStatus** 项目的 文件中： 
  
```HTML
    <%-- The following lines are ASP.NET directives needed when using SharePoint components --%>
    <%@ Page Inherits="Microsoft.SharePoint.WebPartPages.WebPartPage, Microsoft.SharePoint, Version=15.0.0.0, 
    Culture=neutral, PublicKeyToken=71e9bce111e9429c" MasterPageFile="~masterurl/default.master" Language="C#" %>
    <%@ Register TagPrefix="Utilities" Namespace="Microsoft.SharePoint.Utilities" Assembly="Microsoft.SharePoint, Version=15.0.0.0, 
    Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
    <%@ Register TagPrefix="WebPartPages" Namespace="Microsoft.SharePoint.WebPartPages" Assembly="Microsoft.SharePoint, Version=15.0.0.0, 
    Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
    <%@ Register TagPrefix="SharePoint" Namespace="Microsoft.SharePoint.WebControls" Assembly="Microsoft.SharePoint, Version=15.0.0.0, 
    Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
    <%-- The markup and script in the following Content element will be placed in the <head> of the page.
        For production deployment, change the .debug.js JavaScript references to .js. --%>
    <asp:Content ContentPlaceHolderID="PlaceHolderAdditionalPageHead" runat="server">
    <script type="text/javascript" src="../Scripts/jquery-1.7.1.min.js"></script>
    <script type="text/javascript" src="/_layouts/15/sp.runtime.debug.js"></script>
    <script type="text/javascript" src="/_layouts/15/sp.debug.js"></script>
    <script type="text/javascript" src="/_layouts/15/ps.debug.js"></script>
    <!-- CSS styles -->
    <link rel="Stylesheet" type="text/css" href="../Content/App.css" />
    <!-- Add your JavaScript to the following file -->
    <script type="text/javascript" src="../Scripts/App.js"></script>
    </asp:Content>
    <%-- The markup and script in the following Content element will be placed in the <body> of the page --%>
    <asp:Content ContentPlaceHolderID="PlaceHolderMain" runat="server">
    <form>
        <fieldset>
        <legend>Select assigned tasks</legend>
        <table id="assignmentsTable">
            <caption id="tableCaption">Replace caption</caption>
            <thead>
            <tr id="headerRow">
                <th>Project name</th>
                <th><input type="checkbox" id="headercheckbox" checked="checked" />Task name</th>
                <th>Actual work</th>
                <th>% complete</th>
                <th>Remaining work</th>
                <th>Due date</th>
            </tr>
            </thead>
        </table>
        </fieldset>
        <div id="inputPercentComplete" >
        Set percent complete for all selected assignments, or leave this
        <br /> field blank and set percent complete for individual assignments: 
        <input type="text" name="percentComplete" id="pctComplete" size="4"  maxlength="4" />
        </div>
        <div id="submitResult">
        <p><button id="btnSubmitUpdate" type="button" class="bottomButtons" ></button></p>
        <p id="message"></p>
        </div>
        <div id="refreshPage">
        <p><button id="btnRefresh" type="button" class="bottomButtons" >Refresh</button></p>
        </div>
    <div id="exitPage">
        <p><button id="btnExit" type="button" class="bottomButtons" >Exit</button></p>
    </div>
    </form>
    </asp:Content>
```

<br/>

### <a name="appjs-file"></a>App.js文件

以下代码位于  `Scripts\App.js` **QuickStatus** 项目的 文件中： 
  
```js
    var projContext;
    var pwaWeb;
    var projUser;
    // This code runs when the DOM is ready and creates a ProjectContext object.
    // The ProjectContext object is required to use the JSOM for Project Server.
    $(document).ready(function () {
        projContext = PS.ProjectContext.get_current();
        pwaWeb = projContext.get_web();
        getUserInfo();
        getAssignments();
        // Bind a click event handler to the table header check box, which sets the row check boxes
        // to the selected state of the header check box, and sets the results message to an empty string.
        $('#headercheckbox').live('click', function (event) {
            $('input:checkbox:not(#headercheckbox)').attr('checked', this.checked);
            $get("message").innerText = "";
        });
        // Bind a click event handler to the row check boxes. If any row check box is cleared, clear
        // the header check box. If all of the row check boxes are selected, select the header check box.
        $('input:checkbox:not(#headercheckbox)').live('click', function (event) {
            var isChecked = true;
            $('input:checkbox:not(#headercheckbox)').each(function () {
                if (this.checked == false) isChecked = false;
                $get("message").innerText = "";
            });
            $("#headercheckbox").attr('checked', isChecked);
        });
    });
    // Get information about the current user.
    function getUserInfo() {
        projUser = pwaWeb.get_currentUser();
        projContext.load(projUser);
        projContext.executeQueryAsync(onGetUserNameSuccess,
            // Anonymous function to execute if getUserInfo fails.
            function (sender, args) {
                alert('Failed to get user name. Error: ' + args.get_message());
        });
    }
    // This function is executed if the getUserInfo call is successful.
    // Replace the contents of the 'caption' paragraph with the project user name.
    function onGetUserNameSuccess() {
        var prefaceInfo = 'Assignments for ' + projUser.get_title();
        $('#tableCaption').text(prefaceInfo);
    }
    // Get the collection of assignments for the current user.
    function getAssignments() {
        assignments = PS.EnterpriseResource.getSelf(projContext).get_assignments();
        // Register the request that you want to run on the server. The optional "Include" parameter 
        // requests only the specified properties for each assignment in the collection.
        projContext.load(assignments,
            'Include(Project, Name, ActualWork, ActualWorkMilliseconds, PercentComplete, RemainingWork, Finish, Task)');
        // Run the request on the server.
        projContext.executeQueryAsync(onGetAssignmentsSuccess,
            // Anonymous function to execute if getAssignments fails.
            function (sender, args) {
                alert('Failed to get assignments. Error: ' + args.get_message());
            });
    }
    // Get the enumerator, iterate through the assignment collection, 
    // and add each assignment to the table.
    function onGetAssignmentsSuccess(sender, args) {
        if (assignments.get_count() > 0) {
            var assignmentsEnumerator = assignments.getEnumerator();
            var projName = "";
            var prevProjName = "3D2A8045-4920-4B31-B3E7-9D0C5195FC70"; // Any unique name.
            var taskNum = 0;
            var chkTask = "";
            var txtPctComplete = "";
            // Constants for creating input controls in the table.
            var INPUTCHK = '<input type="checkbox" class="chkTask" checked="checked" id="chk';
            var LBLCHK = '<label for="chk';
            var INPUTTXT = '<input type="text" size="4"  maxlength="4" class="txtPctComplete" id="txt';
            while (assignmentsEnumerator.moveNext()) {
                var statusAssignment = assignmentsEnumerator.get_current();
                projName = statusAssignment.get_project().get_name();
                // Get an integer value for the number of milliseconds of actual work, such as 3600000.
                var actualWorkMilliseconds = statusAssignment.get_actualWorkMilliseconds();
                // Get a string value for the assignment actual work, such as "1h". Not used here.
                var actualWork = statusAssignment.get_actualWork();                         
                if (projName === prevProjName) {
                    projName = "";
                }
                prevProjName = statusAssignment.get_project().get_name();
                // Create a row for the assignment information.
                var row = assignmentsTable.insertRow();
                taskNum++;
                // Create an HTML string with a check box and task name label, for example:
                //     <input type="checkbox" class="chkTask" checked="checked" id="chk1" /> 
                //     <label for="chk1">Task 1</label>
                chkTask = INPUTCHK + taskNum + '" /> ' + LBLCHK + taskNum + '">'
                    + statusAssignment.get_name() + '</label>';
                txtPctComplete = INPUTTXT + taskNum + '" />';
                // Insert cells for the assignment properties.
                row.insertCell().innerHTML = '<strong>' + projName + '</strong>';
                row.insertCell().innerHTML = chkTask;
                row.insertCell().innerText = actualWorkMilliseconds / 3600000 + 'h';
                row.insertCell().innerHTML = txtPctComplete;
                row.insertCell().innerText = statusAssignment.get_remainingWork();
                row.insertCell().innerText = statusAssignment.get_finish();
                // Initialize the percent complete cell.
                $get("txt" + taskNum).innerText = statusAssignment.get_percentComplete() + '%'
            }
        }
        else {
            $('p#message').attr('style', 'color: #0f3fdb');     // Blue text.
            $get("message").innerText = projUser.get_title() + ' has no assignments'
        }
        // Initialize the button properties.
        $get("btnSubmitUpdate").onclick = function() { updateAssignments(); };
        $get("btnSubmitUpdate").innerText = 'Update';
        $get('btnRefresh').onclick = function () { window.location.reload(true); };
        $get('btnExit').onclick = function () { exitToPwa(); };
    }
    // Update all selected assignments. If the bottom percent complete field is blank,
    // use the value in the % complete field of each selected row in the table.
    function updateAssignments() {
        // Get percent complete from the bottom text box.
        var pctCompleteMain = getNumericValue($('#pctComplete').val()).trim();
        var pctComplete = pctCompleteMain;
        var assignmentsEnumerator = assignments.getEnumerator();
        var taskNum = 0;
        var taskRow = "";
        var indexPercent = "";
        var doSubmit = true;
        while (assignmentsEnumerator.moveNext()) {
            var pctCompleteRow = "";
            taskRow = "chk" + ++taskNum;
            if ($get(taskRow).checked) {
                var statusAssignment = assignmentsEnumerator.get_current();
                if (pctCompleteMain === "") {
                    // Get percent complete from the text box field in the table row.
                    pctCompleteRow = getNumericValue($('#txt' + taskNum).val());
                    pctComplete = pctCompleteRow;
                }
                // If both percent complete fields are empty, show an error.
                if (pctCompleteMain === "" && pctCompleteRow === "") {
                    $('p#message').attr('style', 'color: #e11500');     // Red text.
                    $get("message").innerHTML =
                        '<b>Error:</b> Both <i>Percent complete</i> fields are empty, in row '
                        + taskNum
                        + ' and in the bottom textbox.<br/>One of those fields must have a valid percent.'
                        + '<p>Please refresh the page and try again.</p>';
                    doSubmit = false;
                    taskNum = 0;
                    break;
                }
                if (doSubmit) statusAssignment.set_percentComplete(pctComplete);
            }
        } 
        // Save and submit the assignment updates.
        if (doSubmit) {
            assignments.update();
            assignments.submitAllStatusUpdates();
            projContext.executeQueryAsync(function (source, args) {
                $('p#message').attr('style', 'color: #0faa0d');     // Green text.
                $get("message").innerText = 'Assignments have been updated.';
            }, function (source, args) {
                $('p#message').attr('style', 'color: #e11500');     // Red text.
                $get("message").innerText = 'Error updating assignments: ' + args.get_message();
            });
        }
    }
    // Get the numeric part for percent complete, from a string. 
    // For example, with "20 %", return "20".
    function getNumericValue(pctComplete) {
        pctComplete = pctComplete.trim();
        pctComplete = pctComplete.replace(/ /g, "");    // Remove interior spaces.
        indexPercent = pctComplete.indexOf('%', 0);
        if (indexPercent > -1) pctComplete = pctComplete.substring(0, indexPercent);
        return pctComplete;
    }
    // Exit the QuickStatus page and go back to the Tasks page in Project Web App.
    function exitToPwa() {
        // Get the SharePoint host URL, which is the top page of PWA, and add the Tasks page.
        var spHostUrl = decodeURIComponent(getQueryStringParameter('SPHostUrl'))
                        + "/Tasks.aspx";
        // Set the top window for the QuickStatus IFrame to the Tasks page.
        window.top.location.href = spHostUrl;
    }
    // Get a specified query string parameter from the {StandardTokens} URL option string.
    function getQueryStringParameter(urlParameterKey) {
        var docUrl = document.URL;
        var params = docUrl.split('?')[1].split('&');
        for (var i = 0; i < params.length; i++) {
            var theParam = params[i].split('=');
            if (theParam[0] == urlParameterKey)
                return decodeURIComponent(theParam[1]);
        }
    }
```

<br/>

### <a name="appcss-file"></a>App.css 文件

以下 CSS 代码位于  `Content\App.css` **QuickStatus** 项目的文件中： 
  
```css
    /* Custom styles for the QuickStatus app. */
    /*============= Table elements ========================================*/
    table {
        width: 90%;
    }
    caption {
        font-size: 16px;
        padding-bottom: 5px;
        font-weight: bold;
        color: gray;
    }
    table th {
        background-color: gray;
        color: white;
    }
    table td, th {
        width: auto;
        text-align: left;
        padding: 2px;
        border: solid 1px whitesmoke;
        color: gray;
    }
    /*=== Class for check boxes added to rows 
    */
    .chkTask {
        width: 12px;
        height: 12px;
        color: gray;
    }
    /*========== DIV id for the Percent Complete text box ================*/
    #inputPercentComplete {
        position: fixed;
        top: auto;
        height: auto;
        padding-top: 20px;
        margin-left: 30px;
    }
    /*========== DIV id for the Submit Result button ====================*/
    #submitResult {
        position: fixed;
        top: auto;
        height: auto;
        padding-top: 60px;
    }
    /*========== DIV id for the Refresh Page button ====================*/
    #refreshPage {
        position: fixed;
        top: auto;
        height: auto;
        padding-top: 60px;
        margin-left: 120px;
    }
    /*========== DIV id for the Exit Page button ====================*/
    #exitPage {
        position: fixed;
        top: auto;
        height: auto;
        padding-top: 60px;
        margin-left: 240px;
    }
    /*========== Class for the buttons at the bottom of the page =======*/
    .bottomButtons {
        color: gray;
        font-weight: bold; 
        font-size: 12px; 
        border-color: darkgreen;
        border-width: thin;
    }
```

<br/>

### <a name="elementsxml-file-for-the-ribbon"></a>Elements.xml功能区创建文件

对于功能区上" **任务** "选项卡上添加的按钮，以下 XML 定义位于  `RibbonQuickStatusAction\Elements.xml` **QuickStatus 项目的** 文件中： 
  
```XML
    <?xml version="1.0" encoding="utf-8"?>
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">
    <CustomAction Id="21ea3aaf-79e5-4aac-9479-8eef14b4d9df.RibbonQuickStatusAction"
                    Location="CommandUI.Ribbon">
        <CommandUIExtension>
        <!-- 
        Add a button that invokes the QuickStatus app. The Quick Status button is displayed as  
        the third control in the Page group (the group title is "Submit").
        -->
        <CommandUIDefinitions>
            <CommandUIDefinition Location="Ribbon.ContextualTabs.MyWork.Home.Page.Controls._children">
            <Button Id="Ribbon.ContextualTabs.MyWork.Home.Page.QuickStatus"
                    Alt="Quick Status app"
                    Sequence="30"
                    Command="Invokae_QuickStatus"
                    LabelText="Quick Status"
                    TemplateAlias="o1"
                    Image16by16="_layouts/15/1033/images/ps16x16.png" 
                    Image16by16Left="-80"
                    Image16by16Top="-144"
                    Image32by32="_layouts/15/1033/images/ps32x32.png" 
                    Image32by32Left="-32"
                    Image32by32Top="-288" 
                    ToolTipTitle="Quick Status"
                    ToolTipDescription="Run the QuickStatus app" />
            </CommandUIDefinition>
        </CommandUIDefinitions>
        <CommandUIHandlers>
            <CommandUIHandler Command="Invoke_QuickStatus"
                            CommandAction="~appWebUrl/Pages/Default.aspx?{StandardTokens}"/>
        </CommandUIHandlers>
        </CommandUIExtension >
    </CustomAction>
    </Elements>
```

<br/>

### <a name="appmanifestxml-file"></a>AppManifest.xml 文件

下面是 **QuickStatus** 项目的应用程序清单的 XML，其中包括更新应用程序用户在多个项目中的工作分配状态所需的两个权限请求范围： 
  
```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <!--Created:cb85b80c-f585-40ff-8bfc-12ff4d0e34a9-->
    <App xmlns="http://schemas.microsoft.com/sharepoint/2012/app/manifest"
        Name="QuickStatus"
        ProductID="{bbc497e7-1221-4d7b-a0ae-141a99546008}"
        Version="1.0.0.0"
        SharePointMinVersion="15.0.0.0"
    >
    <Properties>
        <Title>Quick Status Update</Title>
        <StartPage>~appWebUrl/Pages/Default.aspx?{StandardTokens}</StartPage>
    </Properties>
    <AppPrincipal>
        <Internal />
    </AppPrincipal>
    <AppPermissionRequests>
        <AppPermissionRequest Scope="https://sharepoint/projectserver/statusing" Right="SubmitStatus" />
        <AppPermissionRequest Scope="https://sharepoint/projectserver/projects" Right="Read" />
    </AppPermissionRequests>
    </App>
```

<br/>

### <a name="appiconpng-file"></a>AppIcon.png文件

**QuickStatus** Visual Studio的完整解决方案包括自定义 AppIcon.png 文件。 该解决方案将包含在 Project 2013 SDK 下载中。 

<a name="pj15_StatusingApp_NextSteps"> </a>

## <a name="next-steps"></a>后续步骤

**QuickStatus** 应用是一个相对简单的示例，它演示了如何编写可安装在 Project Server 2013 和 Project Online。 测试 [QuickStatus 应用](#pj15_StatusingApp_Testing) 部分列出了为获得更好的可用性而进行的几个改进。 **QuickStatus** 应用使用 JavaScript 函数更新 Project Web App。 但是，不建议使用更改工作分配完成百分比的项目管理做法。 另一个方法是更新已分配任务的实际开始日期和剩余工期。 有关这些问题的讨论，请参阅 MPUG [新闻稿中的更新](https://www.mpug.com/articles/update-better) 更好。 

<a name="pj15_StatusingApp_AdditionalResources"> </a>

## <a name="see-also"></a>另请参阅

- [Project Server 编程任务](project-programming-tasks.md)
- [SharePoint 外接程序](https://msdn.microsoft.com/library/jj163230.aspx)
- [管理 Project Web App 中的任务更新](https://technet.microsoft.com/library/hh767481%28v=office.14%29.aspx)
- [创建自定义操作以部署 SharePoint 外接程序](https://msdn.microsoft.com/library/jj163954.aspx)
    

