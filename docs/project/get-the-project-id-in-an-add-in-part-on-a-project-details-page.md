---
title: 在 Project 详细信息页上获取加载项部件中的项目 ID
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 009cd997-c7e5-4078-b495-c40caa29a5fb
description: 外接程序部件承载宿主页上与完全隔离的 iframe 元素中。 若要从项目详细信息页面 (PDP) 中的外接程序部分获取有关当前项目的信息，可以使用 window.postMessage 方法和事件侦听器的事件处理程序解析出的项目 ID 从邮件。
ms.openlocfilehash: 6704dae7ded385f86d2da47a1334ae4c81622a74
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779411"
---
# <a name="get-the-project-id-in-an-add-in-part-on-a-project-details-page"></a><span data-ttu-id="ab7bd-104">在 Project 详细信息页上获取加载项部件中的项目 ID</span><span class="sxs-lookup"><span data-stu-id="ab7bd-104">Get the project ID in an add-in part on a Project Details Page</span></span>

<span data-ttu-id="ab7bd-105">外接程序部件承载宿主页上与完全隔离的**iframe**元素中。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-105">Add-in parts are hosted in **iframe** elements that are fully isolated from the hosting page.</span></span> <span data-ttu-id="ab7bd-106">若要从项目详细信息页面 (PDP) 中的外接程序部分获取有关当前项目的信息，可以使用**window.postMessage**方法和事件侦听器的事件处理程序解析出的项目 ID 从邮件。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-106">To get information about the current project from an add-in part on Project Details Page (PDP), you can use the **window.postMessage** method, an event listener, and an event handler that parses out the project ID from the message.</span></span> 
  
## <a name="prerequisites-for-creating-a-sharepoint-hosted-add-in-part-that-gets-the-project-id"></a><span data-ttu-id="ab7bd-107">创建一个 SharePoint 托管外接程序部件获取项目 ID 的先决条件</span><span class="sxs-lookup"><span data-stu-id="ab7bd-107">Prerequisites for creating a SharePoint-hosted add-in part that gets the project ID</span></span>
<span data-ttu-id="ab7bd-108"><a name="Prereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7bd-108"></span></span>

<span data-ttu-id="ab7bd-109">若要使用本文中的代码示例，您将需要以下任一项：</span><span class="sxs-lookup"><span data-stu-id="ab7bd-109">To use the code example in this article, you'll need either of the following:</span></span>
  
- <span data-ttu-id="ab7bd-110">SharePoint 2013 和 Project Server 2013 外, 接程序隔离的配置。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-110">SharePoint 2013 and Project Server 2013, configured for add-in isolation.</span></span> <span data-ttu-id="ab7bd-111">如果您正在远程开发的该服务器必须支持 sideloading 加载项或开发人员网站上必须安装外接程序。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-111">If you're developing remotely, the server must support sideloading of add-ins or you must install the add-in on a Developer Site.</span></span>
  
- <span data-ttu-id="ab7bd-112">SharePoint Online 和 Project Online</span><span class="sxs-lookup"><span data-stu-id="ab7bd-112">SharePoint Online and Project Online</span></span>
    
    - <span data-ttu-id="ab7bd-113">Visual Studio 2013 中，用于 Visual Studio 2013 或 Napa Visual Studio 2012 Office 开发人员使用的工具</span><span class="sxs-lookup"><span data-stu-id="ab7bd-113">Visual Studio 2013, Visual Studio 2012 with Office Developer Tools for Visual Studio 2013, or Napa</span></span>
        
    - <span data-ttu-id="ab7bd-114">登录用户的足够权限：</span><span class="sxs-lookup"><span data-stu-id="ab7bd-114">Sufficient permissions for the logged-on user:</span></span>
        
        - <span data-ttu-id="ab7bd-115">开发计算机上的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-115">Local administrator permissions on the development computer.</span></span>
            
        - <span data-ttu-id="ab7bd-116">至少一个项目的读取权限。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-116">Read access to at least one project.</span></span>
            
        - <span data-ttu-id="ab7bd-117">若要编辑 Project Web App 网站上的网页的权限。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-117">Permission to edit pages on the Project Web App site.</span></span>
            
        - <span data-ttu-id="ab7bd-118">您必须为某人之外系统帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-118">You must be logged on as someone other than the system account.</span></span> <span data-ttu-id="ab7bd-119">系统帐户没有安装外接程序的权限。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-119">The system account does not have permission to install an add-in.</span></span>
    
<span data-ttu-id="ab7bd-120">有关加载项项目的详细信息，请参阅[Project Server 2013 的加载项创建的先决条件](create-a-sharepoint-hosted-project-server-add-in.md#pj15_StatusingApp_Prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-120">See [Prerequisites for creating an add-in for Project Server 2013](create-a-sharepoint-hosted-project-server-add-in.md#pj15_StatusingApp_Prerequisites) for more information about add-ins for Project.</span></span> <span data-ttu-id="ab7bd-121">有关本地安装程序 （包括如何禁用环回检查，如有必要） 的指南，请参阅[设置本地开发环境的 SharePoint 加载项的设置](http://msdn.microsoft.com/library/b0878c12-27c9-4eea-ae3b-7e79e5a8838d%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-121">See [Set up an on-premises development environment for SharePoint Add-ins](http://msdn.microsoft.com/library/b0878c12-27c9-4eea-ae3b-7e79e5a8838d%28Office.15%29.aspx) for guidance about on-premises setup (including how to disable the loopback check, if necessary).</span></span> <span data-ttu-id="ab7bd-122">如果您正在远程开发，请参阅[Developing SharePoint 相关应用程序在远程系统上](http://msdn.microsoft.com/library/bf35d59c-9b84-42e5-877e-fa6881a7b6fc%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-122">If you're developing remotely, see [Developing apps for SharePoint on a remote system](http://msdn.microsoft.com/library/bf35d59c-9b84-42e5-877e-fa6881a7b6fc%28Office.15%29.aspx).</span></span>
  
## <a name="create-the-sharepoint-hosted-add-in-and-client-web-part"></a><span data-ttu-id="ab7bd-123">创建 SharePoint 托管外接程序和客户端 web 部件</span><span class="sxs-lookup"><span data-stu-id="ab7bd-123">Create the SharePoint-hosted add-in and client web part</span></span>
<span data-ttu-id="ab7bd-124"><a name="CreateApp"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7bd-124"></span></span>

1. <span data-ttu-id="ab7bd-125">打开 Visual Studio 并选择**文件** > **新建** > **项目**。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-125">Open Visual Studio and choose **File** > **New** > **Project**.</span></span>
    
2. <span data-ttu-id="ab7bd-126">在"新建项目"对话框中，从对话框顶部的下拉列表中选择".NET Framework 4.5"。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-126">In the **New Project** dialog box, choose **.NET Framework 4.5** from the drop-down list at the top of the dialog box.</span></span> 
    
3. <span data-ttu-id="ab7bd-127">在**模板**列表中，选择**Visual C#** > **Office/SharePoint** > **加载** > **外接程序 SharePoint 2013**。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-127">In the **Templates** list, choose **Visual C#** > **Office/SharePoint** > **Add-ins** > **Add-in for SharePoint 2013**.</span></span>
    
4. <span data-ttu-id="ab7bd-128">名称外接程序 GetProjectIdAddinPart，，然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-128">Name the add-in GetProjectIdAddinPart, and then choose the **OK** button.</span></span> 
    
5. <span data-ttu-id="ab7bd-129">在**新外接程序 SharePoint**对话框中，输入您想要用于调试的 PWA 网站的 URL (例如： _https://contoso.com/sites/pwasite/_)。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-129">In the **New add-in for SharePoint** dialog box, enter the URL of the PWA site that you want to use for debugging (for example:  _https://contoso.com/sites/pwasite/_).</span></span>
    
6. <span data-ttu-id="ab7bd-130">选择外接程序，承载的**SharePoint 承载**选项，然后选择**完成**按钮。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-130">Choose the **SharePoint-hosted** option to host your add-in, and then choose the **Finish** button.</span></span> 
    
7. <span data-ttu-id="ab7bd-131">在**解决方案资源管理器**中，打开 GetProjectIdAddinPart 项目的快捷菜单，然后选择**添加** > **新项目**。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-131">In **Solution Explorer**, open the shortcut menu for the GetProjectIdAddinPart project, and then choose **Add** > **New Item**.</span></span>
    
8. <span data-ttu-id="ab7bd-132">**添加新项**对话框中，选择**客户端 web 部件 (主机 Web)** 和命名 web 部件 GetProjectId，然后选择**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-132">In the **Add New Item** dialog box, choose **Client web part (Host Web)**, name the web part GetProjectId, and then choose the **Add** button.</span></span> 
    
9. <span data-ttu-id="ab7bd-133">**创建客户端 web 部件**对话框中，选择**创建新的客户端 web 部件页**选项，然后选择**完成**按钮。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-133">In the **Create Client web part** dialog box, choose the **Create a new client web part page** option, and then choose the **Finish** button.</span></span> 
    
## <a name="get-the-project-id-in-the-add-in-part"></a><span data-ttu-id="ab7bd-134">外接程序部件中获取项目 ID</span><span class="sxs-lookup"><span data-stu-id="ab7bd-134">Get the project ID in the add-in part</span></span>
<span data-ttu-id="ab7bd-135"><a name="GetProjectId"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7bd-135"></span></span>

<span data-ttu-id="ab7bd-136">GetProjectId 外接程序部件客户端 web 部件的 GetProjectId.aspx 页中定义其自定义代码。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-136">The GetProjectId add-in part defines its custom code in the GetProjectId.aspx page of the client web part.</span></span> <span data-ttu-id="ab7bd-137">在页上的**head**元素中定义接收并处理邮件的逻辑和页的**body**元素中定义的页面控件。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-137">The logic that receives and handles the message is defined in the **head** element of the page and the page controls are defined in the **body** element of the page.</span></span> 
  
1. <span data-ttu-id="ab7bd-138">打开 GetProjectId.aspx web 部件页 （在**页面**文件夹中）。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-138">Open the GetProjectId.aspx web part page (in the **Pages** folder).</span></span> 
    
2. <span data-ttu-id="ab7bd-139">在页面的**head**元素中，将替换为以下代码的**script**标记间的代码。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-139">In the **head** element of the page, replace the code between the **script** tags with the following code.</span></span> 
    
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

3. <span data-ttu-id="ab7bd-140">页的**body**元素内添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-140">Add the following code in the **body** element of the page.</span></span> <span data-ttu-id="ab7bd-141">代码定义一个范围内的控件，显示项目 id。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-141">The code defines a span control that displays the project ID.</span></span> 
    
   ```HTML
    <p>The ID for this project is:</p>
    <span id="projectUid"></span>
   ```

4. <span data-ttu-id="ab7bd-142">在 Elements.xml 文件中，（可选） 更改名称、 标题、 说明和外接程序部件的默认大小。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-142">In the Elements.xml file, optionally change the name, title, description, and default size of the add-in part.</span></span> <span data-ttu-id="ab7bd-143">此示例使用默认值。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-143">This example uses the default values.</span></span>
    
5. <span data-ttu-id="ab7bd-144">若要测试的外接程序部分中，在菜单栏上，选择**调试**，**启动调试**。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-144">To test the add-in part, on the menu bar, choose **Debug**, **Start Debugging**.</span></span> <span data-ttu-id="ab7bd-145">如果提示您修改 web.config 文件，选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-145">If you're prompted to modify the web.config file, choose the **OK** button.</span></span> 
    
   <span data-ttu-id="ab7bd-146">若要调试外接程序部件，请在您添加的脚本设置相应断点。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-146">To debug the add-in part, set appropriate breakpoints in the script that you added.</span></span>
    
6. <span data-ttu-id="ab7bd-147">浏览到 PDP 页面，并从工具菜单的 （齿轮图标） 中选择**编辑页面**。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-147">Browse to a PDP page and choose **Edit page** from the Tools menu (gear icon).</span></span> 
    
7. <span data-ttu-id="ab7bd-148">**GetProjectId 标题**部件添加到页面上的 web 部件。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-148">Add the **GetProjectId Title** part to a web part on the page.</span></span> <span data-ttu-id="ab7bd-149">在 web 部件页上的**跨**控件中显示的项目 ID。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-149">The project ID displays in the **span** control on the web part page.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="ab7bd-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ab7bd-150">Next steps</span></span>
<span data-ttu-id="ab7bd-151"><a name="NextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7bd-151"></span></span>

<span data-ttu-id="ab7bd-152">在此示例中的外接程序部件不访问 Project Server 数据或 SharePoint 数据。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-152">The add-in part in this example doesn't access Project Server data or SharePoint data.</span></span> <span data-ttu-id="ab7bd-153">产品 ID 可用于通过使用客户端 API，例如 JavaScript 对象模型或 REST 服务来获取有关当前项目的信息。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-153">You can use the product ID to get information about the current project by using a client API, such as the JavaScript object model or the REST service.</span></span>
  
<span data-ttu-id="ab7bd-154">在 AppManifest.xml 文件中，指定加载项需要访问 Project Server 数据或 SharePoint 数据的权限。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-154">In the AppManifest.xml file, specify the permissions that your add-in needs to access Project Server data or SharePoint data.</span></span> 
  
<span data-ttu-id="ab7bd-155">请参阅[创建与 SharePoint 外接程序安装外接程序部件](http://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx)以了解如何设置外接程序部件的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-155">See [Create add-in parts to install with your SharePoint Add-in](http://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx) to learn how to set custom properties for an add-in part.</span></span> 
  
## <a name="example-getting-the-project-id-in-an-add-in-part-on-a-pdp-page"></a><span data-ttu-id="ab7bd-156">示例： 在 PDP 页面上的外接程序部分中获取项目 ID</span><span class="sxs-lookup"><span data-stu-id="ab7bd-156">Example: Getting the project ID in an add-in part on a PDP page</span></span>
<span data-ttu-id="ab7bd-157"><a name="CodeExample"> </a></span><span class="sxs-lookup"><span data-stu-id="ab7bd-157"></span></span>

<span data-ttu-id="ab7bd-158">下面的示例是在客户端 web 部件 GetProjectID.aspx 页中的完整代码。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-158">The following example is the complete code in the client web part's GetProjectID.aspx page.</span></span> <span data-ttu-id="ab7bd-159">代码注册事件侦听器和的事件处理程序接收并分析的邮件包含项目 id。</span><span class="sxs-lookup"><span data-stu-id="ab7bd-159">The code registers an event listener and an event handler that receives and parses a message that contains the project ID.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="ab7bd-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab7bd-160">See also</span></span>

- [<span data-ttu-id="ab7bd-161">Project 编程任务</span><span class="sxs-lookup"><span data-stu-id="ab7bd-161">Project programming tasks</span></span>](project-programming-tasks.md)
- [<span data-ttu-id="ab7bd-162">创建 SharePoint 托管的 Project Server 加载项</span><span class="sxs-lookup"><span data-stu-id="ab7bd-162">Create a SharePoint-hosted Project Server add-in</span></span>](create-a-sharepoint-hosted-project-server-add-in.md)
- [<span data-ttu-id="ab7bd-163">创建外接程序部件以与 SharePoint 外接程序一起安装</span><span class="sxs-lookup"><span data-stu-id="ab7bd-163">Create add-in parts to install with your SharePoint Add-in</span></span>](http://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx)
    

