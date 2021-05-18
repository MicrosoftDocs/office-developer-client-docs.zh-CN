---
title: 在 Project 详细信息页上获取加载项部件中的项目 ID
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 009cd997-c7e5-4078-b495-c40caa29a5fb
description: 外接程序部件托管在与托管页面完全隔离的 iframe 元素中。 若要从 Project 详细信息页面 (PDP) 上的外接程序部件获取有关当前项目的信息，可以使用 window.postMessage 方法、事件侦听器以及从消息中分析项目 ID 的事件处理程序。
ms.openlocfilehash: ffaf9cb7dac783a754b2d56b5ece4d5a7a0319be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322594"
---
# <a name="get-the-project-id-in-an-add-in-part-on-a-project-details-page"></a><span data-ttu-id="1e0fa-104">在 Project 详细信息页上获取加载项部件中的项目 ID</span><span class="sxs-lookup"><span data-stu-id="1e0fa-104">Get the project ID in an add-in part on a Project Details Page</span></span>

<span data-ttu-id="1e0fa-105">外接程序部件托管在与托管页面完全隔离的 **iframe** 元素中。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-105">Add-in parts are hosted in **iframe** elements that are fully isolated from the hosting page.</span></span> <span data-ttu-id="1e0fa-106">若要从 Project 详细信息页面 (PDP) 上的外接程序部件获取有关当前项目的信息，可以使用 **window.postMessage** 方法、事件侦听器以及从消息中分析项目 ID 的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-106">To get information about the current project from an add-in part on Project Details Page (PDP), you can use the **window.postMessage** method, an event listener, and an event handler that parses out the project ID from the message.</span></span> 
  
## <a name="prerequisites-for-creating-a-sharepoint-hosted-add-in-part-that-gets-the-project-id"></a><span data-ttu-id="1e0fa-107">创建用于SharePoint项目 ID 的托管加载项部件的先决条件</span><span class="sxs-lookup"><span data-stu-id="1e0fa-107">Prerequisites for creating a SharePoint-hosted add-in part that gets the project ID</span></span>
<span data-ttu-id="1e0fa-108"><a name="Prereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="1e0fa-108"><a name="Prereqs"> </a></span></span>

<span data-ttu-id="1e0fa-109">若要使用本文中的代码示例，您需要以下任一项：</span><span class="sxs-lookup"><span data-stu-id="1e0fa-109">To use the code example in this article, you'll need either of the following:</span></span>
  
- <span data-ttu-id="1e0fa-110">SharePoint 2013 和 Project Server 2013，配置为外接程序隔离。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-110">SharePoint 2013 and Project Server 2013, configured for add-in isolation.</span></span> <span data-ttu-id="1e0fa-111">如果要进行远程开发，服务器必须支持加载项的旁加载，或者必须在开发人员网站上安装加载项。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-111">If you're developing remotely, the server must support sideloading of add-ins or you must install the add-in on a Developer Site.</span></span>
  
- <span data-ttu-id="1e0fa-112">SharePoint联机和Project Online</span><span class="sxs-lookup"><span data-stu-id="1e0fa-112">SharePoint Online and Project Online</span></span>
    
    - <span data-ttu-id="1e0fa-113">Visual Studio 2013 2012 Visual Studio 2012 Office开发人员工具 for Visual Studio 2013 或 Napa</span><span class="sxs-lookup"><span data-stu-id="1e0fa-113">Visual Studio 2013, Visual Studio 2012 with Office Developer Tools for Visual Studio 2013, or Napa</span></span>
        
    - <span data-ttu-id="1e0fa-114">登录用户的足够权限：</span><span class="sxs-lookup"><span data-stu-id="1e0fa-114">Sufficient permissions for the logged-on user:</span></span>
        
        - <span data-ttu-id="1e0fa-115">开发计算机上的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-115">Local administrator permissions on the development computer.</span></span>
            
        - <span data-ttu-id="1e0fa-116">至少对一个项目的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-116">Read access to at least one project.</span></span>
            
        - <span data-ttu-id="1e0fa-117">编辑网站页面Project Web App权限。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-117">Permission to edit pages on the Project Web App site.</span></span>
            
        - <span data-ttu-id="1e0fa-118">您必须以系统帐户以外的人的身份登录。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-118">You must be logged on as someone other than the system account.</span></span> <span data-ttu-id="1e0fa-119">系统帐户没有安装外接程序的权限。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-119">The system account does not have permission to install an add-in.</span></span>
    
<span data-ttu-id="1e0fa-120">有关[创建适用于 Project Server 2013](create-a-sharepoint-hosted-project-server-add-in.md#pj15_StatusingApp_Prerequisites)的外接程序Project。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-120">See [Prerequisites for creating an add-in for Project Server 2013](create-a-sharepoint-hosted-project-server-add-in.md#pj15_StatusingApp_Prerequisites) for more information about add-ins for Project.</span></span> <span data-ttu-id="1e0fa-121">请参阅[为 SharePoint](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/set-up-an-on-premises-development-environment-for-sharepoint-add-ins)外接程序设置本地开发环境，了解本地设置 (包括如何禁用环回检查（如有必要) ）。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-121">See [Set up an on-premises development environment for SharePoint Add-ins](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/set-up-an-on-premises-development-environment-for-sharepoint-add-ins) for guidance about on-premises setup (including how to disable the loopback check, if necessary).</span></span> <span data-ttu-id="1e0fa-122">如果要进行远程开发，请参阅在远程[SharePoint开发应用程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/develop-sharepoint-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-122">If you're developing remotely, see [Developing apps for SharePoint on a remote system](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/develop-sharepoint-add-ins).</span></span>
  
## <a name="create-the-sharepoint-hosted-add-in-and-client-web-part"></a><span data-ttu-id="1e0fa-123">创建SharePoint托管的外接程序和客户端 Web 部件</span><span class="sxs-lookup"><span data-stu-id="1e0fa-123">Create the SharePoint-hosted add-in and client web part</span></span>
<span data-ttu-id="1e0fa-124"><a name="CreateApp"> </a></span><span class="sxs-lookup"><span data-stu-id="1e0fa-124"><a name="CreateApp"> </a></span></span>

1. <span data-ttu-id="1e0fa-125">打开Visual Studio，然后选择"**文件**  >  **""新建**  >  **Project"。**</span><span class="sxs-lookup"><span data-stu-id="1e0fa-125">Open Visual Studio and choose **File** > **New** > **Project**.</span></span>
    
2. <span data-ttu-id="1e0fa-126">在“新建项目”对话框顶部的下拉列表中，选择“.NET Framework 4.5”。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-126">In the **New Project** dialog box, choose **.NET Framework 4.5** from the drop-down list at the top of the dialog box.</span></span> 
    
3. <span data-ttu-id="1e0fa-127">在 **"模板"列表中**，选择 **"visual C#**  >  **Office/SharePoint**  >    >  **2013 外接程序SharePoint外接程序"。**</span><span class="sxs-lookup"><span data-stu-id="1e0fa-127">In the **Templates** list, choose **Visual C#** > **Office/SharePoint** > **Add-ins** > **Add-in for SharePoint 2013**.</span></span>
    
4. <span data-ttu-id="1e0fa-128">将外接程序命名为 GetProjectIdAddinPart，然后选择" **确定"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-128">Name the add-in GetProjectIdAddinPart, and then choose the **OK** button.</span></span> 
    
5. <span data-ttu-id="1e0fa-129">在 **"** 新建 SharePoint 外接程序"对话框中，输入要用于调试的 PWA 网站的 URL， (例如 _https://contoso.com/sites/pwasite/_ ：) 。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-129">In the **New add-in for SharePoint** dialog box, enter the URL of the PWA site that you want to use for debugging (for example:  _https://contoso.com/sites/pwasite/_).</span></span>
    
6. <span data-ttu-id="1e0fa-130">选择 **SharePoint** 托管选项来托管外接程序，然后选择"完成 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-130">Choose the **SharePoint-hosted** option to host your add-in, and then choose the **Finish** button.</span></span> 
    
7. <span data-ttu-id="1e0fa-131">在 **"解决方案资源管理器**"中，打开 GetProjectIdAddinPart 项目的快捷菜单，然后选择"**添加新**  >  **项"。**</span><span class="sxs-lookup"><span data-stu-id="1e0fa-131">In **Solution Explorer**, open the shortcut menu for the GetProjectIdAddinPart project, and then choose **Add** > **New Item**.</span></span>
    
8. <span data-ttu-id="1e0fa-132">在" **添加新项** "对话框中，选择"客户端 Web (**主机 Web**) "，将 Web 部件命名为 GetProjectId，然后选择"添加 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-132">In the **Add New Item** dialog box, choose **Client web part (Host Web)**, name the web part GetProjectId, and then choose the **Add** button.</span></span> 
    
9. <span data-ttu-id="1e0fa-133">在" **创建客户端 Web 部件** "对话框中，选择" **新建客户端 Web** 部件页"选项，然后选择"完成 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-133">In the **Create Client web part** dialog box, choose the **Create a new client web part page** option, and then choose the **Finish** button.</span></span> 
    
## <a name="get-the-project-id-in-the-add-in-part"></a><span data-ttu-id="1e0fa-134">获取外接程序部件中的项目 ID</span><span class="sxs-lookup"><span data-stu-id="1e0fa-134">Get the project ID in the add-in part</span></span>
<span data-ttu-id="1e0fa-135"><a name="GetProjectId"> </a></span><span class="sxs-lookup"><span data-stu-id="1e0fa-135"><a name="GetProjectId"> </a></span></span>

<span data-ttu-id="1e0fa-136">GetProjectId 外接程序部件在客户端 Web 部件 GetProjectId.aspx 页面中定义其自定义代码。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-136">The GetProjectId add-in part defines its custom code in the GetProjectId.aspx page of the client web part.</span></span> <span data-ttu-id="1e0fa-137">接收和处理邮件的逻辑在页面的 **head** 元素中定义，页面控件在页面的 **body** 元素中定义。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-137">The logic that receives and handles the message is defined in the **head** element of the page and the page controls are defined in the **body** element of the page.</span></span> 
  
1. <span data-ttu-id="1e0fa-138">打开"页面"文件夹中的"getProjectId.aspx **(") 。**</span><span class="sxs-lookup"><span data-stu-id="1e0fa-138">Open the GetProjectId.aspx web part page (in the **Pages** folder).</span></span> 
    
2. <span data-ttu-id="1e0fa-139">在 **页面的 head** 元素中，将 **script** 标记之间的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-139">In the **head** element of the page, replace the code between the **script** tags with the following code.</span></span> 
    
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

3. <span data-ttu-id="1e0fa-140">在页面的 body 元素 **中添加** 以下代码。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-140">Add the following code in the **body** element of the page.</span></span> <span data-ttu-id="1e0fa-141">代码定义显示项目 ID 的 span 控件。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-141">The code defines a span control that displays the project ID.</span></span> 
    
   ```HTML
    <p>The ID for this project is:</p>
    <span id="projectUid"></span>
   ```

4. <span data-ttu-id="1e0fa-142">在Elements.xml文件中，可以选择更改外接程序部件的名称、标题、说明和默认大小。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-142">In the Elements.xml file, optionally change the name, title, description, and default size of the add-in part.</span></span> <span data-ttu-id="1e0fa-143">此示例使用默认值。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-143">This example uses the default values.</span></span>
    
5. <span data-ttu-id="1e0fa-144">若要测试外接程序部件，在菜单栏上，选择"调试"和"**开始调试"。**</span><span class="sxs-lookup"><span data-stu-id="1e0fa-144">To test the add-in part, on the menu bar, choose **Debug**, **Start Debugging**.</span></span> <span data-ttu-id="1e0fa-145">如果系统提示您修改 web.config 文件，请选择"确定"按钮。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-145">If you're prompted to modify the web.config file, choose the **OK** button.</span></span> 
    
   <span data-ttu-id="1e0fa-146">若要调试外接程序部件，在添加的脚本中设置适当的断点。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-146">To debug the add-in part, set appropriate breakpoints in the script that you added.</span></span>
    
6. <span data-ttu-id="1e0fa-147">浏览到 PDP 页面， **然后从** "工具"菜单中选择"编辑页面 (齿轮图标) 。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-147">Browse to a PDP page and choose **Edit page** from the Tools menu (gear icon).</span></span> 
    
7. <span data-ttu-id="1e0fa-148">将 **GetProjectId Title** 部件添加到页面上的 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-148">Add the **GetProjectId Title** part to a web part on the page.</span></span> <span data-ttu-id="1e0fa-149">项目 ID 显示在 Web 部件 **页上的 span** 控件中。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-149">The project ID displays in the **span** control on the web part page.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="1e0fa-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1e0fa-150">Next steps</span></span>
<span data-ttu-id="1e0fa-151"><a name="NextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="1e0fa-151"><a name="NextSteps"> </a></span></span>

<span data-ttu-id="1e0fa-152">此示例中的外接程序部件不访问 Project 或 SharePoint 数据。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-152">The add-in part in this example doesn't access Project Server data or SharePoint data.</span></span> <span data-ttu-id="1e0fa-153">可以使用产品 ID 通过客户端 API（如 JavaScript 对象模型或 REST 服务）获取有关当前项目的信息。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-153">You can use the product ID to get information about the current project by using a client API, such as the JavaScript object model or the REST service.</span></span>
  
<span data-ttu-id="1e0fa-154">在 AppManifest.xml 文件中，指定外接程序访问 Project 或 SharePoint 数据所需的权限。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-154">In the AppManifest.xml file, specify the permissions that your add-in needs to access Project Server data or SharePoint data.</span></span> 
  
<span data-ttu-id="1e0fa-155">请参阅[创建外接程序部件以随](https://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx)SharePoint 一起安装，了解如何设置外接程序部件的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-155">See [Create add-in parts to install with your SharePoint Add-in](https://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx) to learn how to set custom properties for an add-in part.</span></span> 
  
## <a name="example-getting-the-project-id-in-an-add-in-part-on-a-pdp-page"></a><span data-ttu-id="1e0fa-156">示例：在 PDP 页面上获取外接程序部件中的项目 ID</span><span class="sxs-lookup"><span data-stu-id="1e0fa-156">Example: Getting the project ID in an add-in part on a PDP page</span></span>
<span data-ttu-id="1e0fa-157"><a name="CodeExample"> </a></span><span class="sxs-lookup"><span data-stu-id="1e0fa-157"><a name="CodeExample"> </a></span></span>

<span data-ttu-id="1e0fa-158">以下示例是客户端 Web 部件 GetProjectID.aspx 页面中的完整代码。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-158">The following example is the complete code in the client web part's GetProjectID.aspx page.</span></span> <span data-ttu-id="1e0fa-159">代码注册事件侦听器和接收和分析包含项目 ID 的消息的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1e0fa-159">The code registers an event listener and an event handler that receives and parses a message that contains the project ID.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="1e0fa-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e0fa-160">See also</span></span>

- [<span data-ttu-id="1e0fa-161">Project 编程任务</span><span class="sxs-lookup"><span data-stu-id="1e0fa-161">Project programming tasks</span></span>](project-programming-tasks.md)
- [<span data-ttu-id="1e0fa-162">创建 SharePoint 托管的 Project Server 加载项</span><span class="sxs-lookup"><span data-stu-id="1e0fa-162">Create a SharePoint-hosted Project Server add-in</span></span>](create-a-sharepoint-hosted-project-server-add-in.md)
- [<span data-ttu-id="1e0fa-163">创建外接程序部件以安装 SharePoint 外接程序</span><span class="sxs-lookup"><span data-stu-id="1e0fa-163">Create add-in parts to install with your SharePoint Add-in</span></span>](https://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx)
    

