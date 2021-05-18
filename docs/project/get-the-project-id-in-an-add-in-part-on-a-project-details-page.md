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
# <a name="get-the-project-id-in-an-add-in-part-on-a-project-details-page"></a>在 Project 详细信息页上获取加载项部件中的项目 ID

外接程序部件托管在与托管页面完全隔离的 **iframe** 元素中。 若要从 Project 详细信息页面 (PDP) 上的外接程序部件获取有关当前项目的信息，可以使用 **window.postMessage** 方法、事件侦听器以及从消息中分析项目 ID 的事件处理程序。 
  
## <a name="prerequisites-for-creating-a-sharepoint-hosted-add-in-part-that-gets-the-project-id"></a>创建用于SharePoint项目 ID 的托管加载项部件的先决条件
<a name="Prereqs"> </a>

若要使用本文中的代码示例，您需要以下任一项：
  
- SharePoint 2013 和 Project Server 2013，配置为外接程序隔离。 如果要进行远程开发，服务器必须支持加载项的旁加载，或者必须在开发人员网站上安装加载项。
  
- SharePoint联机和Project Online
    
    - Visual Studio 2013 2012 Visual Studio 2012 Office开发人员工具 for Visual Studio 2013 或 Napa
        
    - 登录用户的足够权限：
        
        - 开发计算机上的本地管理员权限。
            
        - 至少对一个项目的读取访问权限。
            
        - 编辑网站页面Project Web App权限。
            
        - 您必须以系统帐户以外的人的身份登录。 系统帐户没有安装外接程序的权限。
    
有关[创建适用于 Project Server 2013](create-a-sharepoint-hosted-project-server-add-in.md#pj15_StatusingApp_Prerequisites)的外接程序Project。 请参阅[为 SharePoint](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/set-up-an-on-premises-development-environment-for-sharepoint-add-ins)外接程序设置本地开发环境，了解本地设置 (包括如何禁用环回检查（如有必要) ）。 如果要进行远程开发，请参阅在远程[SharePoint开发应用程序](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/develop-sharepoint-add-ins)。
  
## <a name="create-the-sharepoint-hosted-add-in-and-client-web-part"></a>创建SharePoint托管的外接程序和客户端 Web 部件
<a name="CreateApp"> </a>

1. 打开Visual Studio，然后选择"**文件**  >  **""新建**  >  **Project"。**
    
2. 在“新建项目”对话框顶部的下拉列表中，选择“.NET Framework 4.5”。 
    
3. 在 **"模板"列表中**，选择 **"visual C#**  >  **Office/SharePoint**  >    >  **2013 外接程序SharePoint外接程序"。**
    
4. 将外接程序命名为 GetProjectIdAddinPart，然后选择" **确定"** 按钮。 
    
5. 在 **"** 新建 SharePoint 外接程序"对话框中，输入要用于调试的 PWA 网站的 URL， (例如 _https://contoso.com/sites/pwasite/_ ：) 。
    
6. 选择 **SharePoint** 托管选项来托管外接程序，然后选择"完成 **"** 按钮。 
    
7. 在 **"解决方案资源管理器**"中，打开 GetProjectIdAddinPart 项目的快捷菜单，然后选择"**添加新**  >  **项"。**
    
8. 在" **添加新项** "对话框中，选择"客户端 Web (**主机 Web**) "，将 Web 部件命名为 GetProjectId，然后选择"添加 **"** 按钮。 
    
9. 在" **创建客户端 Web 部件** "对话框中，选择" **新建客户端 Web** 部件页"选项，然后选择"完成 **"** 按钮。 
    
## <a name="get-the-project-id-in-the-add-in-part"></a>获取外接程序部件中的项目 ID
<a name="GetProjectId"> </a>

GetProjectId 外接程序部件在客户端 Web 部件 GetProjectId.aspx 页面中定义其自定义代码。 接收和处理邮件的逻辑在页面的 **head** 元素中定义，页面控件在页面的 **body** 元素中定义。 
  
1. 打开"页面"文件夹中的"getProjectId.aspx **(") 。** 
    
2. 在 **页面的 head** 元素中，将 **script** 标记之间的代码替换为以下代码。 
    
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

3. 在页面的 body 元素 **中添加** 以下代码。 代码定义显示项目 ID 的 span 控件。 
    
   ```HTML
    <p>The ID for this project is:</p>
    <span id="projectUid"></span>
   ```

4. 在Elements.xml文件中，可以选择更改外接程序部件的名称、标题、说明和默认大小。 此示例使用默认值。
    
5. 若要测试外接程序部件，在菜单栏上，选择"调试"和"**开始调试"。** 如果系统提示您修改 web.config 文件，请选择"确定"按钮。 
    
   若要调试外接程序部件，在添加的脚本中设置适当的断点。
    
6. 浏览到 PDP 页面， **然后从** "工具"菜单中选择"编辑页面 (齿轮图标) 。 
    
7. 将 **GetProjectId Title** 部件添加到页面上的 Web 部件。 项目 ID 显示在 Web 部件 **页上的 span** 控件中。 
    
## <a name="next-steps"></a>后续步骤
<a name="NextSteps"> </a>

此示例中的外接程序部件不访问 Project 或 SharePoint 数据。 可以使用产品 ID 通过客户端 API（如 JavaScript 对象模型或 REST 服务）获取有关当前项目的信息。
  
在 AppManifest.xml 文件中，指定外接程序访问 Project 或 SharePoint 数据所需的权限。 
  
请参阅[创建外接程序部件以随](https://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx)SharePoint 一起安装，了解如何设置外接程序部件的自定义属性。 
  
## <a name="example-getting-the-project-id-in-an-add-in-part-on-a-pdp-page"></a>示例：在 PDP 页面上获取外接程序部件中的项目 ID
<a name="CodeExample"> </a>

以下示例是客户端 Web 部件 GetProjectID.aspx 页面中的完整代码。 代码注册事件侦听器和接收和分析包含项目 ID 的消息的事件处理程序。
  
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

## <a name="see-also"></a>另请参阅

- [Project 编程任务](project-programming-tasks.md)
- [创建 SharePoint 托管的 Project Server 加载项](create-a-sharepoint-hosted-project-server-add-in.md)
- [创建外接程序部件以安装 SharePoint 外接程序](https://msdn.microsoft.com/library/a2664289-6c56-4cb1-987a-22367fad55eb%28Office.15%29.aspx)
    

