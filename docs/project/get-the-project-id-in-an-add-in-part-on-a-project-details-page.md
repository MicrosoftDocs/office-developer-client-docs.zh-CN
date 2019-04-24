---
title: 在 Project 详细信息页上获取加载项部件中的项目 ID
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 009cd997-c7e5-4078-b495-c40caa29a5fb
description: 外接程序部件托管在 iframe 元素中, 这些元素完全独立于承载页面。 若要从 "项目详细信息" 页 (PDP) 上的外接程序部件获取有关当前项目的信息, 可以使用 postMessage 方法、事件侦听器和从邮件中解析项目 ID 的事件处理程序。
ms.openlocfilehash: ffaf9cb7dac783a754b2d56b5ece4d5a7a0319be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322594"
---
# <a name="get-the-project-id-in-an-add-in-part-on-a-project-details-page"></a><span data-ttu-id="2be3d-104">在 Project 详细信息页上获取加载项部件中的项目 ID</span><span class="sxs-lookup"><span data-stu-id="2be3d-104">Get the project ID in an add-in part on a Project Details Page</span></span>

<span data-ttu-id="2be3d-105">外接程序部件托管在**iframe**元素中, 这些元素完全独立于承载页面。</span><span class="sxs-lookup"><span data-stu-id="2be3d-105">Add-in parts are hosted in **iframe** elements that are fully isolated from the hosting page.</span></span> <span data-ttu-id="2be3d-106">若要从 "项目详细信息" 页 (PDP) 上的外接程序部件获取有关当前项目的信息, 可以使用**postMessage**方法、事件侦听器和从邮件中解析项目 ID 的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2be3d-106">To get information about the current project from an add-in part on Project Details Page (PDP), you can use the **window.postMessage** method, an event listener, and an event handler that parses out the project ID from the message.</span></span> 
  
## <a name="prerequisites-for-creating-a-sharepoint-hosted-add-in-part-that-gets-the-project-id"></a><span data-ttu-id="2be3d-107">创建 SharePoint 托管的外接程序部件以获取项目 ID 的先决条件</span><span class="sxs-lookup"><span data-stu-id="2be3d-107">Prerequisites for creating a SharePoint-hosted add-in part that gets the project ID</span></span>
<span data-ttu-id="2be3d-108"><a name="Prereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="2be3d-108"></span></span>

<span data-ttu-id="2be3d-109">若要使用本文中的代码示例, 您需要以下各项之一:</span><span class="sxs-lookup"><span data-stu-id="2be3d-109">To use the code example in this article, you'll need either of the following:</span></span>
  
- <span data-ttu-id="2be3d-110">为加载项隔离配置的 SharePoint 2013 和 Project Server 2013。</span><span class="sxs-lookup"><span data-stu-id="2be3d-110">SharePoint 2013 and Project Server 2013, configured for add-in isolation.</span></span> <span data-ttu-id="2be3d-111">如果是远程开发, 则服务器必须支持外接程序的旁加载, 否则必须在开发人员网站上安装外接程序。</span><span class="sxs-lookup"><span data-stu-id="2be3d-111">If you're developing remotely, the server must support sideloading of add-ins or you must install the add-in on a Developer Site.</span></span>
  
- <span data-ttu-id="2be3d-112">SharePoint online 和 Project online</span><span class="sxs-lookup"><span data-stu-id="2be3d-112">SharePoint Online and Project Online</span></span>
    
    - <span data-ttu-id="2be3d-113">visual studio 2013、visual studio 2012 (包含适用于 Visual Studio 2013 的 Office 开发人员工具) 或 Napa</span><span class="sxs-lookup"><span data-stu-id="2be3d-113">Visual Studio 2013, Visual Studio 2012 with Office Developer Tools for Visual Studio 2013, or Napa</span></span>
        
    - <span data-ttu-id="2be3d-114">登录用户的足够权限：</span><span class="sxs-lookup"><span data-stu-id="2be3d-114">Sufficient permissions for the logged-on user:</span></span>
        
        - <span data-ttu-id="2be3d-115">开发计算机上的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="2be3d-115">Local administrator permissions on the development computer.</span></span>
            
        - <span data-ttu-id="2be3d-116">至少对一个项目的读取权限。</span><span class="sxs-lookup"><span data-stu-id="2be3d-116">Read access to at least one project.</span></span>
            
        - <span data-ttu-id="2be3d-117">在 Project Web App 网站上编辑页面的权限。</span><span class="sxs-lookup"><span data-stu-id="2be3d-117">Permission to edit pages on the Project Web App site.</span></span>
            
        - <span data-ttu-id="2be3d-118">您必须以系统帐户以外的人的身份登录。</span><span class="sxs-lookup"><span data-stu-id="2be3d-118">You must be logged on as someone other than the system account.</span></span> <span data-ttu-id="2be3d-119">系统帐户没有安装加载项的权限。</span><span class="sxs-lookup"><span data-stu-id="2be3d-119">The system account does not have permission to install an add-in.</span></span>
    
<span data-ttu-id="2be3d-120">请参阅创建适用于[project Server 2013 的外](create-a-sharepoint-hosted-project-server-add-in.md#pj15_StatusingApp_Prerequisites)接程序的先决条件, 以了解有关 Project 外接程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2be3d-120">See [Prerequisites for creating an add-in for Project Server 2013](create-a-sharepoint-hosted-project-server-add-in.md#pj15_StatusingApp_Prerequisites) for more information about add-ins for Project.</span></span> <span data-ttu-id="2be3d-121">请参阅[设置 SharePoint 外接程序的本地开发环境](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/set-up-an-on-premises-development-environment-for-sharepoint-add-ins), 获取有关本地设置的指南 (包括如何在必要时禁用环回检查)。</span><span class="sxs-lookup"><span data-stu-id="2be3d-121">See [Set up an on-premises development environment for SharePoint Add-ins](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/set-up-an-on-premises-development-environment-for-sharepoint-add-ins) for guidance about on-premises setup (including how to disable the loopback check, if necessary).</span></span> <span data-ttu-id="2be3d-122">如果要远程开发, 请参阅[在远程系统上开发 SharePoint 相关应用程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/develop-sharepoint-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="2be3d-122">If you're developing remotely, see [Developing apps for SharePoint on a remote system](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/develop-sharepoint-add-ins).</span></span>
  
## <a name="create-the-sharepoint-hosted-add-in-and-client-web-part"></a><span data-ttu-id="2be3d-123">创建 SharePoint 托管的加载项和客户端 web 部件</span><span class="sxs-lookup"><span data-stu-id="2be3d-123">Create the SharePoint-hosted add-in and client web part</span></span>
<span data-ttu-id="2be3d-124"><a name="CreateApp"> </a></span><span class="sxs-lookup"><span data-stu-id="2be3d-124"></span></span>

1. <span data-ttu-id="2be3d-125">打开 Visual Studio 并选择 "**文件** > " "**新建** > **项目**"。</span><span class="sxs-lookup"><span data-stu-id="2be3d-125">Open Visual Studio and choose **File** > **New** > **Project**.</span></span>
    
2. <span data-ttu-id="2be3d-126">在"新建项目"对话框中，从对话框顶部的下拉列表中选择".NET Framework 4.5"。</span><span class="sxs-lookup"><span data-stu-id="2be3d-126">In the **New Project** dialog box, choose **.NET Framework 4.5** from the drop-down list at the top of the dialog box.</span></span> 
    
3. <span data-ttu-id="2be3d-127">在 "**模板**" 列表中, 选择 "**适用于 SharePoint 的** **Visual c #** > **Office/sharepoint** > **外** > 接程序" 2013。</span><span class="sxs-lookup"><span data-stu-id="2be3d-127">In the **Templates** list, choose **Visual C#** > **Office/SharePoint** > **Add-ins** > **Add-in for SharePoint 2013**.</span></span>
    
4. <span data-ttu-id="2be3d-128">将加载项命名为 "GetProjectIdAddinPart", 然后选择 **"确定"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="2be3d-128">Name the add-in GetProjectIdAddinPart, and then choose the **OK** button.</span></span> 
    
5. <span data-ttu-id="2be3d-129">在 "**新建 SharePoint 外接程序**" 对话框中, 输入要用于调试的 PWA 网站的 URL (例如: _https://contoso.com/sites/pwasite/_)。</span><span class="sxs-lookup"><span data-stu-id="2be3d-129">In the **New add-in for SharePoint** dialog box, enter the URL of the PWA site that you want to use for debugging (for example:  _https://contoso.com/sites/pwasite/_).</span></span>
    
6. <span data-ttu-id="2be3d-130">选择 " **SharePoint 托管**" 选项以托管您的外接程序, 然后选择 "**完成**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2be3d-130">Choose the **SharePoint-hosted** option to host your add-in, and then choose the **Finish** button.</span></span> 
    
7. <span data-ttu-id="2be3d-131">在 "**解决方案资源管理器**" 中, 打开 "GetProjectIdAddinPart" 项目的快捷菜单, 然后选择 "**添加** > **新项**"。</span><span class="sxs-lookup"><span data-stu-id="2be3d-131">In **Solution Explorer**, open the shortcut menu for the GetProjectIdAddinPart project, and then choose **Add** > **New Item**.</span></span>
    
8. <span data-ttu-id="2be3d-132">在 "**添加新项**" 对话框中, 选择 "**客户端 web 部件 (主机 web)**", 将 web 部件命名为 "GetProjectId", 然后选择 "**添加**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2be3d-132">In the **Add New Item** dialog box, choose **Client web part (Host Web)**, name the web part GetProjectId, and then choose the **Add** button.</span></span> 
    
9. <span data-ttu-id="2be3d-133">在 "**创建客户端 web 部件**" 对话框中, 选择 "**创建新的客户端 web 部件页**" 选项, 然后选择 "**完成**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2be3d-133">In the **Create Client web part** dialog box, choose the **Create a new client web part page** option, and then choose the **Finish** button.</span></span> 
    
## <a name="get-the-project-id-in-the-add-in-part"></a><span data-ttu-id="2be3d-134">获取加载项部件中的项目 ID</span><span class="sxs-lookup"><span data-stu-id="2be3d-134">Get the project ID in the add-in part</span></span>
<span data-ttu-id="2be3d-135"><a name="GetProjectId"> </a></span><span class="sxs-lookup"><span data-stu-id="2be3d-135"></span></span>

<span data-ttu-id="2be3d-136">GetProjectId 加载项部件在客户端 web 部件的 GetProjectId 页中定义其自定义代码。</span><span class="sxs-lookup"><span data-stu-id="2be3d-136">The GetProjectId add-in part defines its custom code in the GetProjectId.aspx page of the client web part.</span></span> <span data-ttu-id="2be3d-137">接收和处理邮件的逻辑在页面**头**元素中定义, 页面控件在页面的**body**元素中进行定义。</span><span class="sxs-lookup"><span data-stu-id="2be3d-137">The logic that receives and handles the message is defined in the **head** element of the page and the page controls are defined in the **body** element of the page.</span></span> 
  
1. <span data-ttu-id="2be3d-138">打开 "GetProjectId" web 部件页 (在 "**页面**" 文件夹中)。</span><span class="sxs-lookup"><span data-stu-id="2be3d-138">Open the GetProjectId.aspx web part page (in the **Pages** folder).</span></span> 
    
2. <span data-ttu-id="2be3d-139">在页面的**head**元素中, 将**script**标记之间的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="2be3d-139">In the **head** element of the page, replace the code between the **script** tags with the following code.</span></span> 
    
   ```js
        'use strict';
        // Define global variables.
        var hostUrl = '';
        var projectUid;
        // Set the style of the client web part page to be consistent with the host web.
                (function () {
                    var hostUrl = '';
                    var link = document.createElement('link');
                    link.setAttribute('rel', 'stylesheet');
                    if (document.URL.indexOf('?') != -1) {
                        var params = document.URL.split('?')[1].split('&');
                        for (var i = 0; i < params.length; i++) {
                            var p = decodeURIComponent(params[i]);
                            if (/^SPHostUrl=/i.test(p)) {
                                hostUrl = p.split('=')[1];
                                link.setAttribute('href', hostUrl + '/_layouts/15/defaultcss.ashx');
                                break;
                            }
                        }
                    }
                    if (hostUrl == '') {
                        link.setAttribute('href', '/_layouts/15/1033/styles/themable/corev15.css');
                    }
                    document.head.appendChild(link);
                })();
        // Get the message.
        function getProjectUid() {
            window.parent.postMessage('getprojectuid', hostUrl);
        }
        getProjectUid();
        // Add an event listener and register the event handler.
        // If the IE browser version is earlier than 9, use the attachEvent method.
        if (window.addEventListener) {
            window.addEventListener("message", onMessage, false);
        }
        else {
            if (window.attachEvent) {
                window.attachEvent("onmessage", onMessage);
            }
        }
        // Get the project ID from the message.
        function onMessage(event) {
            // Verify the message origin.
            if (hostUrl.indexOf(event.origin) != 0) return;
            // The expected message format is "<PDPProjectUid>00000000-0000-0000-0000-000000000000</PDPProjectUid>,"
            // so validate by using the length and the start and end tags.
            var length = event.data.length;
            if (length = 67) {
                var expectedStart = "<PDPProjectUid>";
                var expectedEnd = "</PDPProjectUid>";
                var endTagPosition = length - expectedEnd.length;
                var start = event.data.substr(0, expectedStart.length);
                var end = event.data.substr(endTagPosition, expectedEnd.length);
                // Parse out the project ID.
                if (start == expectedStart && end == expectedEnd) {
                    projectUid = event.data.substr(expectedStart.length, 36);
                    $get('projectUid').innerText = projectUid;
                }
            }
        }
   ```

3. <span data-ttu-id="2be3d-140">在页面的**body**元素中添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="2be3d-140">Add the following code in the **body** element of the page.</span></span> <span data-ttu-id="2be3d-141">代码定义了一个显示项目 ID 的 span 控件。</span><span class="sxs-lookup"><span data-stu-id="2be3d-141">The code defines a span control that displays the project ID.</span></span> 
    
   ```HTML
    <p>The ID for this project is:</p>
    <span id="projectUid"></span>
   ```

4. <span data-ttu-id="2be3d-142">在 "元素 .xml" 文件中, 可以选择更改加载项部件的名称、标题、说明和默认大小。</span><span class="sxs-lookup"><span data-stu-id="2be3d-142">In the Elements.xml file, optionally change the name, title, description, and default size of the add-in part.</span></span> <span data-ttu-id="2be3d-143">此示例使用默认值。</span><span class="sxs-lookup"><span data-stu-id="2be3d-143">This example uses the default values.</span></span>
    
5. <span data-ttu-id="2be3d-144">若要测试加载项部件, 请在菜单栏上, 依次选择 "**调试**"、"**启动调试**"。</span><span class="sxs-lookup"><span data-stu-id="2be3d-144">To test the add-in part, on the menu bar, choose **Debug**, **Start Debugging**.</span></span> <span data-ttu-id="2be3d-145">如果系统提示您修改 web.config 文件，请选择"确定"按钮。</span><span class="sxs-lookup"><span data-stu-id="2be3d-145">If you're prompted to modify the web.config file, choose the **OK** button.</span></span> 
    
   <span data-ttu-id="2be3d-146">若要调试外接程序部件, 请在添加的脚本中设置适当的断点。</span><span class="sxs-lookup"><span data-stu-id="2be3d-146">To debug the add-in part, set appropriate breakpoints in the script that you added.</span></span>
    
6. <span data-ttu-id="2be3d-147">浏览到 PDP 页面, 然后从 "工具" 菜单 (齿轮图标) 中选择 "**编辑页面**"。</span><span class="sxs-lookup"><span data-stu-id="2be3d-147">Browse to a PDP page and choose **Edit page** from the Tools menu (gear icon).</span></span> 
    
7. <span data-ttu-id="2be3d-148">将**GetProjectId 标题**部件添加到页面上的 web 部件。</span><span class="sxs-lookup"><span data-stu-id="2be3d-148">Add the **GetProjectId Title** part to a web part on the page.</span></span> <span data-ttu-id="2be3d-149">项目 ID 显示在 web 部件页上的**范围**控件中。</span><span class="sxs-lookup"><span data-stu-id="2be3d-149">The project ID displays in the **span** control on the web part page.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="2be3d-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2be3d-150">Next steps</span></span>
<span data-ttu-id="2be3d-151"><a name="NextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="2be3d-151"></span></span>

<span data-ttu-id="2be3d-152">此示例中的加载项部件不访问 Project Server 数据或 SharePoint 数据。</span><span class="sxs-lookup"><span data-stu-id="2be3d-152">The add-in part in this example doesn't access Project Server data or SharePoint data.</span></span> <span data-ttu-id="2be3d-153">您可以使用产品 ID, 通过使用客户端 API (如 JavaScript 对象模型或 REST 服务) 来获取有关当前项目的信息。</span><span class="sxs-lookup"><span data-stu-id="2be3d-153">You can use the product ID to get information about the current project by using a client API, such as the JavaScript object model or the REST service.</span></span>
  
<span data-ttu-id="2be3d-154">在 appmanifest.xml 文件中, 指定您的外接程序访问 Project Server 数据或 SharePoint 数据所需的权限。</span><span class="sxs-lookup"><span data-stu-id="2be3d-154">In the AppManifest.xml file, specify the permissions that your add-in needs to access Project Server data or SharePoint data.</span></span> 
  
<span data-ttu-id="2be3d-155">请参阅[创建外接程序部件以安装 SharePoint 外接程序](https://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx), 了解如何设置外接程序部件的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="2be3d-155">See [Create add-in parts to install with your SharePoint Add-in](https://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx) to learn how to set custom properties for an add-in part.</span></span> 
  
## <a name="example-getting-the-project-id-in-an-add-in-part-on-a-pdp-page"></a><span data-ttu-id="2be3d-156">示例: 在 PDP 页面上获取外接程序部件中的项目 ID</span><span class="sxs-lookup"><span data-stu-id="2be3d-156">Example: Getting the project ID in an add-in part on a PDP page</span></span>
<span data-ttu-id="2be3d-157"><a name="CodeExample"> </a></span><span class="sxs-lookup"><span data-stu-id="2be3d-157"></span></span>

<span data-ttu-id="2be3d-158">下面的示例是客户端 web 部件的 GetProjectID 页中的完整代码。</span><span class="sxs-lookup"><span data-stu-id="2be3d-158">The following example is the complete code in the client web part's GetProjectID.aspx page.</span></span> <span data-ttu-id="2be3d-159">该代码注册一个事件侦听器和一个事件处理程序, 该事件处理程序接收并分析包含项目 ID 的邮件。</span><span class="sxs-lookup"><span data-stu-id="2be3d-159">The code registers an event listener and an event handler that receives and parses a message that contains the project ID.</span></span>
  
```HTML
<%@ Page language="C#" Inherits="Microsoft.SharePoint.WebPartPages.WebPartPage, Microsoft.SharePoint, Version=15.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
<%@ Register Tagprefix="SharePoint" Namespace="Microsoft.SharePoint.WebControls" Assembly="Microsoft.SharePoint, Version=15.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
<%@ Register Tagprefix="Utilities" Namespace="Microsoft.SharePoint.Utilities" Assembly="Microsoft.SharePoint, Version=15.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
<%@ Register Tagprefix="WebPartPages" Namespace="Microsoft.SharePoint.WebPartPages" Assembly="Microsoft.SharePoint, Version=15.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>
<WebPartPages:AllowFraming ID="AllowFraming" runat="server" />
<html>
<head>
    <title></title>
    <script type="text/javascript" src="../Scripts/jquery-1.7.1.min.js"></script>
    <script type="text/javascript" src="/_layouts/15/MicrosoftAjax.js"></script>
    <script type="text/javascript" src="/_layouts/15/sp.runtime.js"></script>
    <script type="text/javascript" src="/_layouts/15/sp.js"></script>
    <script type="text/javascript">
        'use strict';
        // Define global variables.
        var hostUrl = '';
        var projectUid;
        // Set the style of the client web part page to be consistent with the host web.
        (function () {
            var hostUrl = '';
            var link = document.createElement('link');
            link.setAttribute('rel', 'stylesheet');
            if (document.URL.indexOf('?') != -1) {
                var params = document.URL.split('?')[1].split('&');
                for (var i = 0; i < params.length; i++) {
                    var p = decodeURIComponent(params[i]);
                    if (/^SPHostUrl=/i.test(p)) {
                        hostUrl = p.split('=')[1];
                        link.setAttribute('href', hostUrl + '/_layouts/15/defaultcss.ashx');
                        break;
                    }
                }
            }
            if (hostUrl == '') {
                link.setAttribute('href', '/_layouts/15/1033/styles/themable/corev15.css');
            }
            document.head.appendChild(link);
        })();
        // Get the message.
        function getProjectUid() {
            window.parent.postMessage('getprojectuid', hostUrl);
        }
        getProjectUid();
        // Add an event listener and register the event handler.
        // If the IE browser version is earlier than 9, use the attachEvent method.
        if (window.addEventListener) {
            window.addEventListener("message", onMessage, false);
        }
        else {
            if (window.attachEvent) {
                window.attachEvent("onmessage", onMessage);
            }
        }
        // Get the project ID from the message.
        function onMessage(event) {
            // Verify the message origin.
            if (hostUrl.indexOf(event.origin) != 0) return;
            // The expected message format is "<PDPProjectUid>00000000-0000-0000-0000-000000000000</PDPProjectUid>,"
            // so validate by using the length and the start and end tags.
            var length = event.data.length;
            if (length = 67) {
                var expectedStart = "<PDPProjectUid>";
                var expectedEnd = "</PDPProjectUid>";
                var endTagPosition = length - expectedEnd.length;
                var start = event.data.substr(0, expectedStart.length);
                var end = event.data.substr(endTagPosition, expectedEnd.length);
                // Parse out the project ID.
                if (start == expectedStart && end == expectedEnd) {
                    projectUid = event.data.substr(expectedStart.length, 36);
                    $get('projectUid').innerText = projectUid;
                }
            }
        }
    </script>
</head>
<body>
    <p>The ID for this project is:</p>
    <span id="projectUid"></span>
</body>
</html>

```

## <a name="see-also"></a><span data-ttu-id="2be3d-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2be3d-160">See also</span></span>

- [<span data-ttu-id="2be3d-161">Project 编程任务</span><span class="sxs-lookup"><span data-stu-id="2be3d-161">Project programming tasks</span></span>](project-programming-tasks.md)
- [<span data-ttu-id="2be3d-162">创建 SharePoint 托管的 Project Server 加载项</span><span class="sxs-lookup"><span data-stu-id="2be3d-162">Create a SharePoint-hosted Project Server add-in</span></span>](create-a-sharepoint-hosted-project-server-add-in.md)
- [<span data-ttu-id="2be3d-163">创建外接程序部件以安装 SharePoint 外接程序</span><span class="sxs-lookup"><span data-stu-id="2be3d-163">Create add-in parts to install with your SharePoint Add-in</span></span>](https://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx)
    

