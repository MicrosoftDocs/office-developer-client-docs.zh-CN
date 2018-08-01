---
title: 开发 Project Online 应用程序使用的客户端对象模型
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5740d0b2-5d36-40e4-9e83-577cb186359f
description: 本文介绍使用.NET Framework 4.0 的桌面应用程序的 Microsoft Project Online 应用程序开发。 本文中描述的应用程序宿主服务器中检索信息。
ms.openlocfilehash: a0a2b4042d4db127c56c5ba873ebe25418344571
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779433"
---
# <a name="developing-a-project-online-application-using-the-client-side-object-model"></a>开发 Project Online 应用程序使用的客户端对象模型

本文介绍使用.NET Framework 4.0 的桌面应用程序的 Microsoft Project Online 应用程序开发。 本文中描述的应用程序宿主服务器中检索信息。 
  
## <a name="background"></a>背景

Microsoft Project 桌面应用程序中早期 20 世纪 90 年代开始。 如今，项目是更多，如证明其几个类别：
  
- Project standard edition 的桌面应用程序作为独立的应用程序运行。
    
- Project professional 版本是桌面应用程序可以进行交互和与上规模较大的服务器共享数据，以及执行 Project standard edition 中找到的功能。
    
- Project Online 是一种 Microsoft 承载的服务，公司提供的 PMO 级解决方案以进行协调和管理项目、 程序和项目组合。 桌面版本，Project Online 比其他产品可以维护和跟踪整个生命周期中的项目的项目详细信息。 
    
- Project Server 企业管理，并保护包含项目、 程序和项目组合信息的服务器的企业托管的服务。 Project Server、 源于保护内部，服务器提供项目、 程序和项目组合面向外部托管 Project Online 与更大容量的自定义功能。
    
Project Online 具有三个 online API 集： 客户端对象模型 (CSOM)、 JavaScript 对象模型 (JSOM) 和代表性状态传输 (REST)。 
  
- .NET CSOM 实现时开发与 Project Online 租户 Windows 应用程序交互的首选的接口。 以用户为中心的应用程序的典型环境包括 Windows 台式机和 Microsoft Surface 设备。 使用.NET CSOM 编写的后端应用程序可以连接到其他服务器的外部的 Project Online 的业务逻辑和数据源。 到 Project Online 的检索请求使用 LINQ 类似于查询系统的基本检索函数通过了若干个增强。
    
- JavaScript 对象模型 (JSOM) 接口提供了 Project Online 的加载项的跨浏览器支持。外接程序是存储在 Project Online 租户中的 web 应用程序。 当用户想要运行外接程序时外, 接程序的代码下载并在用户计算机上运行在浏览器中。 
    
- REST/Odata 模型提供了基于 HTTP 的通信，在非 Windows 环境中的应用程序建议使用此接口。 通信终结点是 Project Web 应用程序 (PWA) 网站中的对象。 结果提供一般 HTTP 状态代码。
    
本文重点介绍使用.NET CSOM 接口的应用程序。
  
## <a name="prerequisites"></a>先决条件

开始与基本系统运行 Windows 10，并添加以下各项：
  
- .Net framework 4.0 或更高版本-使用完整的框架。 下载站点是https://msdn.microsoft.com/en-us/vstudio/aa496123.aspx。
    
- Visual Studio 2013 或更高版本-是可以接受任何版本。 使用 Visual Studio 2015 的社区版本开发示例应用程序。 社区 edition 位于https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx。
    
- SharePoint 客户端组件 SDK-Project Online 和 Project Server 坐在 SharePoint 和 SharePoint 程序集。 SharePoint 客户端组件都包括在 Visual Studio 专业版和企业版。 如果您使用 Visual Studio 社区 edition，在以下网站中可用是最新版本的 Office 开发人员工具 SDK: https://www.microsoft.com/en-us/download/details.aspx?id=35585。
    
- Project Online 的帐户-这提供了对承载网站的访问。 有关获取 Project Online 帐户的详细信息，请参阅https://products.office.com/en-us/Project/project-online-portfolio-management。
    
- 承载的网站上的项目填充的信息
    
> [!NOTE]
> 标准.NET Framework （4.0 或更高版本） 是要使用的正确框架。 不要使用.NET Framework 4 客户端配置文件。 
  
## <a name="develop-the-application"></a>开发应用程序

在针对 SharePoint 进行开发桌面应用程序，首选的接口是 Project 客户端对象模型 (CSOM)。 
  
您可以下载完整的示例在https://github.com/OfficeDev/Project-CSOM-List-Projects-Tasks。
  
前两个主题涵盖基本问题： 使用适当的命名空间和程序集，创建 Visual Studio 项目和访问宿主服务器。 从一和多对象中检索信息通过 CSOM，处理的其余主题。 
  
从主机中检索信息是从客户端应用程序的两个操作过程。 首先，应用程序指定，并将一个或多个检索请求发送到服务器。 其次，应用程序向服务器执行提交的查询发出通知。 服务器响应通过将查询结果发送到客户端。
  
### <a name="set-up-the-visual-studio-project"></a>设置 Visual Studio 项目

应用程序安装由创建新项目、 链接相应的程序集和声明所需的命名空间组成。 Visual Studio 提供了几种类型的开发项目。 
  
#### <a name="select-a-visual-studio-project"></a>选择 Visual Studio 项目

1. 启动 Visual Studio，然后选择开始页上的**启动新项目**。 
    
   新建项目对话框中显示可用的应用程序模板和任何选定的模板的数据字段。 
    
2. 为此应用程序，指定以下各项。 在屏幕上遇到关键字具有粗体属性：
    
   1. 从已安装的模板的左窗格中，选择**C#** => **Windows** => **经典桌面**。 
    
   2. 在中央窗格的顶部，选择 **.NET Framework 4**。 
    
   3. 从应用程序类型在中央窗格中，选择**控制台应用程序**。 
    
   4. 在底部部分中，指定的名称和位置的项目，并解决方案名称。 
    
   5. 此外在底部部分中，检查**创建解决方案的目录**框中。 
    
3. 单击**确定**以创建初始项目。 
    
#### <a name="add-assemblies"></a>将程序集添加

VS 解决方案需要 ProjectServerClient 程序集从 Project 2103 SDK，几个来自 SharePoint SDK，程序集和.NET Framework System.Security 程序集。
  
1. VS 解决方案资源管理器，右键单击引用条目中，并选择**添加引用...** 从快捷菜单。 
    
2. 检查**Microsoft.ProjectServer.Client.dll**。 
    
   如果需要请单击**浏览...** 在对话框的底部按钮并导航到要定位程序集的 Project 2013 SDK 安装目录。 
    
3. 单击“确定”****。 
    
4. 将 PrjoctServer 客户端命名空间添加到.cs 文件中。
    
   ```cs
    using Microsoft.ProjectServer.Client;
   ```

添加使用 NuGet 程序包管理器控制台的 SharePoint 2013 SDK 程序集。 
  
1. 从 VS 工具菜单中，单击下列菜单：**工具 =\> NuGet 程序包管理器 =\>程序包管理器控制台**。 
    
2. 在程序包管理器控制台中，输入以下命令并按\<ENTER\>:
    
   ```cs
    Install-Package Microsoft.SharePointOnline.CSOM
   ```

   **程序包管理器控制台**提供命令结果; 的说明并 VS 解决方案资源管理器显示项目引用中的 SharePoint 程序集。 
    
3. 将命名空间添加到.cs 文件中：
    
   ```cs
    using Microsoft.SharePoint.Client;
   ```

System.Security 程序集是.NET Framework 的一部分，且已安装与框架。 该示例应用程序需要一个身份验证提供对承载系统的加密的字符串的多个命名空间。 身份验证后，应用程序可以访问承载系统的项目。 将 System.Security 命名空间添加到.cs 文件中这种方式：
  
1. VS 解决方案资源管理器，右键单击引用条目中，并选择**添加引用...** 从快捷菜单。 
    
2. 选中**程序集 =\>框架**左窗格中的引用管理器对话框中，然后检查**System.Security**。 
    
3. 单击“确定”****。 
    
4. 将 System.Security 命名空间添加到.cs 文件中：
    
   ```cs
    using System.Security;
   ```

.Cs 文件的开头应包含以下命名空间：
  
- 系统
    
- System.Collections.Generic
    
- 更改
    
- System.Test
    
- Microsoft.ProjectServer.Client
    
- Microsoft.SharePoint.Client
    
- System.Security
    
### <a name="connect-to-the-host-system"></a>连接到主机系统

Project Online 是 SharePoint 应用程序，因此使用 SharePoint 身份验证是正确的方法。 下面的代码片段准备访问托管的环境。
  
```cs
    class Program
    {
        private static ProjectContext projContext;
        static void Main (string[] args)
        {
            using (ProjectContext projContext = new ProjectContext("https://Contoso.sharepoint.com/sites/pwa"))
            {
                SecureString password - new SecureString();
                foreach (char c in "password".ToCharArray()) password.AppendChar(c);
                //Using SharePoint method to load Credentials
                projContext.Credentials = new SharePointOnlineCredentials("sarad@Contoso.onmicrosoft.com", password);

```

若要访问托管的环境的准备工作包括以下各项：
  
1. 创建一个 context 对象的项目--这包含在前面的代码片段的下面的代码。 
    
   ```cs
    private static ProjectContext projContext;
    
   ```

   上下文被继承的其他组件，允许系统管理的 Project 对象模型上下文中。
    
2. 标识主机网站--这是在下面的代码从前面的代码片段。
    
   ```cs
    using (ProjectContext projContext = new ProjectContext("https://Contoso.sharepoint.com/sites/pwa"))
   ```

   当实例化项目上下文，该应用程序需要提供的项目网站集的根目录。 应用程序使用的项目的根 URL 的子字符串。 使用下图中的一个红色矩形突出显示此位置的快照。 身份验证需要从其开始通过"pwa"的子字符串的字符串。 在代码列表中，应用程序使用字符串"https://XXXXXXXX.sharepoint.com/sites/pwa"。
        
   ![屏幕截图红色的边框内的项目网站集的 URL。](media/d48c4894-5dba-46b6-886a-3c59bfb83c4d.png "屏幕截图的项目的 URL 的网站集内的红色的边框")
  
3. 将密码放入安全字符串--这是在下面的代码从前面的代码片段。
    
   ```cs
    SecureString password - new SecureString();
    foreach (char c in "password".ToCharArray()) password.AppendChar(c);
    
   ```

   密码和用户帐户是访问主机网站的凭据。 
    
4. Context 对象的凭据部分中添加的用户帐户和密码--这是在下面的代码从前面的代码片段。
    
   ```cs
    projContext.Credentials = new SharePointOnlineCredentials("sarad@Contoso.onmicrosoft.com", password);
   ```

实例化的项目上下文已准备好使用。
  
### <a name="list-all-published-projects"></a>列出所有已发布的项目

Project Online 和 ProjectServer 使用代理服务器进行通信与服务器进行创建、 报表、 更新和删除 (CRUD) 操作。 主机服务器更有效地处理请求，并包含客户端与服务器通信中执行下列操作：
  
1. 建立上下文通信。 
    
   上下文使用项目集合，以及其他对象和通过继承，包括 tasks 集合、 assignments 集合、 阶段对象和自定义字段的集合。 
    
2. 使用对象模型指定的对象、 集合或要检索数据。
    
   此步骤中使用 LINQ 查询作为或方法。 规范控制您收到的内容。 通常，此步骤被嵌入作为正文 Load 方法 （第 3 步）。 
    
3. 从使用 Load() 或 LoadQuery() 方法在上一步中加载检索规范。
    
   加载集合和对象，使用 Load()。 为查询子句，如"位置"和"组"，使用 LoadQuery()。 
    
4. 执行使用 ExecuteQuery() 方法的请求。
    
   ExecuteQuery() 方法通知宿主准备好执行的查询。 一旦主机接收通知时，它将执行查询并将结果发送到客户端。 
    
在客户端的信息，该应用程序可以使用它。 下面的代码段的已发布项目中循环，并在主机上打印的 Id 和为每个已发布项目的名称。
  
```cs
// Get the list of projects in Project Web App.
var projects = projContext.Projects;
projContext.Load(projects);
projcontext.ExecuteQuery();
foreach (PublishedProject pubProj in projContext.Projects)
{
    Console.WriteLine("\n{0}. {1}   {2} \t{3} \n", j++, pubProj.Id, pubProj.Name, pubProj.CreatedDate);
}

```

输出：
  
```cs
Published Project count:2
1. be80a848-b2ef-e511-80f4-00155dc84e01   A second Project     3/21/2016 10:14:40 PM
2. 9d730a1a-60ed-e511-80f6-00155dc87d01   Ent_Proj_1   3/18/2016 11:21:14 PM

```

### <a name="make-a-request"></a>发出请求

使用上一代码片段中的操作，应用程序检索中指定的帐户承载网站上的项目列表。 
  
1. ProjectContext 指定列出的项目。 
    
   ```cs
    var projects = projContext.Projects;
   ```

2. 指定要检索的项。 
    
   ```cs
    projContext.Load(projects);
   ```

   通过仅说明集合，该服务器检索填充的默认属性集值的每个项目的项目集合。 访问属性的默认属性集的一部分提供成功的结果。 访问不是默认的一部分的属性设置将导致一个"未初始化"例外项。
    
3. 加载请求 (projContext.Load)。
    
   这是在上一步的一部分。
    
4. 执行查询 (ExecuteQuery)。 
    
   ```cs
    projContext.ExecuteQuery();
   ```

### <a name="retrieve-high-level-project-information"></a>检索高级项目信息

不是必须到服务器请求中指定的默认属性的属性。 下面的代码段加载与前面的示例的项目集上下文。 然后，规范请求要在结果中包括的其他非默认属性。 
  
```cs
var projects = projContext.Projects;
projContext.Load(projects,
    ps => ps.IncludeWithDefaultProperties(
        p => p.StartDate, p => p.Phase, p => p.Stage));
projContext.ExecuteQuery();

```

Load 语句指定的项目集上下文，并将阶段，StartDate 和阶段添加到查询结果。 其他属性可以是标量，对象或集合。 可以直接访问标量项目。 对象和集合需要进行其他处理，如下面的代码片段中所示。
  
```cs
// Using the previous definition and Load statement …
projContext.ExecuteQuery();
foreach (PublishedProject pubProj in projContext.Projects)
{
Console.WriteLine("\n\t{0}. \t{1} \n\t{2} \n\t{3} \n", j++, pubProj.Id, pubProj.Name,
    pubProj.CreatedDate);
             // The following statement generates an exception about the object 
             // reference not being set to an instance on the server. 
             // Console.WriteLine("\tCurrent Phase:\t{0}", pubProj.Phase.Name);
             // Phase and Stage are not published with the rest of the data. Need to pull these objects from the server.
             Phase oPhase = pubProj.Phase;
             projContext.Load(oPhase);
             projContext.ExecuteQuery();
             //if-else fails because the else case fails with "Microsoft.SharePoint.Client.ServerObjectNullReferenceException".
             //if (oPhase.ServerObjectIsNull != null)
             //Using try-catch instead
             try
             {
                  Console.WriteLine("\tCurrent Phase:\t{0}", oPhase.Name);
             }
             
             catch
             {
                  Console.WriteLine("\tCurrent Phase:\t Not available");
             }
             
             Stage oStage = pubProj.Stage;
             projContext.Load(oStage);
             projContext.ExecuteQuery();
             //Again, not using if-else combination for the same reason as above.
             try
             {
                  Console.WriteLine("\tCurrent Stage:\t{0}", oStage.Name);
             }
             
             catch
             {
                  Console.WriteLine("\tCurrent Stage:\t Not available");
    }

```

前三个项目的输出：
  
```cs
Project counts:31
1. Project ID:  957d5fcd-5cbf-e111-9f1e-00155d022681
        Name:           Acquisition Target Analysis
        CreatedDate:            3/22/2016 5:14:34 PM
        Current Phase:  3. Plan
        Current Stage:  6. Plan
2. Project ID:  16905202-5fbf-e111-9f1e-00155d022681
        Name:           Apparel ERP Upgrade
        CreatedDate:            3/22/2016 5:36:40 PM
        Current Phase:  3. Plan
        Current Stage:  6. Plan
3. Project ID:  dce23152-63bf-e111-9f1e-00155d022681
        Name:           Audit Tracking Solution
        CreatedDate:            3/22/2016 5:02:24 PM
        Current Phase:  2. Select
        Current Stage:  4. Select Gate

```

### <a name="retrieve-all-tasks-in-a-project"></a>检索项目中的所有任务

每个项目中有多个任务。 因此，将单个项目的任务以下内容组成：
  
1. 建立项目集合的上下文。
    
   ```cs
    var projects = projContext.Projects;
   ```

2. 检索的项目信息，包括任务属性。
    
   ```cs
    projContext.Load(projects);
    ProjContext.ExecuteQuery();
    foreach (PublishedProject pubProj in projContext.Projects){
    
   ```

    请注意，解决应用程序已发布的项目。 当前已发布的项目的上下文是 pubProj。 
    
3. 建立 Tasks 集合的上下文。
    
   ```cs
    PublishedTaskCollection collTask = pubProj.Tasks;
   ```

   `pubProj.Tasks`属性引用当前已发布的项目的任务。 
    
4. 加载规范若要检索任务集合，包括相应的非默认属性。
    
   ```cs
    projContext.Load(collTask,
        tsk => tsk.IncludeWithDefaultProperties(
            t => t.Id, t => t.Name, t => t.Start,
            t => t.ScheduledStart, t => t.Completion));
    
   ```

5. 执行查询来检索与相应的属性的任务集合。
    
   ```cs
    projContext.ExecuteQuery();
   ```

现在，本地信息。 下面的代码段的信息写入控制台来处理发布的 tasks 集合。
  
```cs
    Console.WriteLine("Task collection count: {0}", collTask.Count.ToString());
    if (collTask.Count > 0)
    {
        int k = 1;    //Task counter.
        foreach (PublishedTask t in collTask)
        {
            Console.WriteLine("{0}. Id:{1} \tName:{2}", k++, t.Id, t.Name);
            Console.WriteLine("\t ScheduledStart:{0} \tStart:{1} \tCompletion:{2}", k, t.ScheduledStart, t.Start, t.Completion);
        }
    }

```

一个项目的任务的输出：
  
```cs
Task collection count: 5
1. Id:256fa850-b2ef-e511-80f6-00155dc87d01      Name:Load software onto computer
         ScheduledStart:2       Start:4/4/2016 8:00:00 AM       Completion:4/4/2016 8:00:00 AM
2. Id:266fa850-b2ef-e511-80f6-00155dc87d01      Name:Locate and load Project Online SDK
         ScheduledStart:3       Start:4/5/2016 8:00:00 AM       Completion:4/5/2016 8:00:00 AM
3. Id:276fa850-b2ef-e511-80f6-00155dc87d01      Name:Locate and load SP SDK
         ScheduledStart:4       Start:4/5/2016 1:00:00 PM       Completion:4/5/2016 1:00:00 PM
4. Id:286fa850-b2ef-e511-80f6-00155dc87d01      Name:Build app that accesses Proj Online
         ScheduledStart:5       Start:4/6/2016 8:00:00 AM       Completion:4/6/2016 8:00:00 AM
5. Id:296fa850-b2ef-e511-80f6-00155dc87d01      Name:Build app that accesses task assignments
         ScheduledStart:6       Start:4/7/2016 8:00:00 AM       Completion:4/7/2016 8:00:00 AM

```

### <a name="access-information-at-multiple-levels"></a>在多个级别的访问信息

每项任务 （也可以有一个或多个人员 资源） 有影响其完成。 分配和资源的集合包含每个任务此信息。 
  
处理由以下内容组成：
  
1. 获取项目任务的上下文。
    
2. 生成一个请求和负载绑定到任务的分配请求。 
    
3. 执行将工作分配的查询。
    
4. 生成一个请求和负载与单个工作分配关联的资源的请求。 
    
5. 执行资源的查询。
    
> [!NOTE] 
> - 从服务器的信息中显式请求 Assignments 集合，因为它不是在 Tasks 集合的默认属性。 作为集合，后续查询进行拉从服务器的集合。 
> - 资源是一个对象。 工作分配的查询包括与工作分配关联的资源名称。
    
```cs
PublishedTaskCollection collTask = pubProj.Tasks;
    projContext.Load(collTask,
        tsk => tsk.IncludeWithDefaultProperties(
            t => t.Id, t => t.Name, 
            t => t.Assignments));
    projContext.Load(collTask);
    projContext.ExecuteQuery();
    Console.WriteLine("Task collection count: {0}", collTask.Count.ToString());
    if (collTask.Count > 0)
    {
        int k = 1;    //Task counter.
        //Processing task list for current project
        foreach (PublishedTask t in collTask)
        {
            Console.WriteLine("{0}. Id:{1} \tName:{2}", k, t.Id, t.Name);
            k++;
            //Define and retrieve Assignments for current task
            PublishedAssignmentCollection collAssgns = t.Assignments;
            projContext.Load(collAssgns);
            projContext.ExecuteQuery();
            Console.WriteLine("    Assignment collection count: {0}", collAssgns.Count);
            if (collAssgns.Count > 0)
            {
                //Output string for resources assigned to task
                StringBuilder output = new StringBuilder();
                output.AppendFormat("\t Assignments: ");
                foreach (PublishedAssignment a in collAssgns)
                {
                    //Define and retrieve resource name for current assignment 
                    //(an object)
                    projContext.Load(a,
                        b => b.Resource.Name);
                    projContext.ExecuteQuery();
                    output.AppendFormat("{0}, ", a.Resource.Name);
                }
                Console.WriteLine(output);
            }
            else
            {
                Console.WriteLine("\t Assignments: None");
            }
        }
    }   // endif

```

任务 52、 75 和 76 项目的输出：
  
```cs
52. Id:2c729e96-54f0-e511-80c6-000d3a33235f     Name:Develop training materials
    Assignment collection count: 1
         Assignments: Robert Lyon,
75. Id:43729e96-54f0-e511-80c6-000d3a33235f     Name:Determine final deployment strategy
    Assignment collection count: 0
         Assignments: None
76. Id:44729e96-54f0-e511-80c6-000d3a33235f     Name:Develop deployment methodology
    Assignment collection count: 4
         Assignments: Molly Dempsey, Sara Davis, Shammi Mohamed, Zainal Arifin, 

```

### <a name="access-custom-enterprise-level-fields"></a>访问自定义企业级字段

自定义域 for Project Online 中存在。 这些是可以与单个项目相关联的企业级字段。 本节介绍如何访问这些字段。 
  
自定义域不包含在与项目关联的属性的默认设置。 因此，他们需要检索规范中的显式标识。 概括的过程包括以下各项：
  
1. 隧道到使用公用名称的自定义字段。
    
2. 检索自定义字段的内部名称。
    
3. 返回到全局上下文和查询使用自定义字段的内部名称的系统。
    
#### <a name="tunnel-to-the-custom-field-retrieve-its-internal-name-and-used-it-to-query-the-system"></a>隧道到自定义字段、 检索其内部名称，并使用它来查询系统

此任务指定非默认属性使用一个增加了详细信息检索。
  
1. 开始使用项目上下文，如本文开头所述。
    
   ```cs
    // Get the list of published projects in Project Web App.
    var projects = projContext.Projects;
    
   ```

2. 将两个项目添加到项目集合检索除了任何其他非默认属性用于检索请求：
    
   ```cs
    projContext.Load(projects,
        ps => ps.IncludeWithDefaultProperties(
            p => p.Phase, p => p.Stage,                  // Other nondefault properties
            p => p.IncludeCustomFields,                  // Gets PublishedProject object 
                                                        // that contains custom fields
            p => p.IncludeCustomFields.CustomFields));   // Populates the custom fields
                    projContext.ExecuteQuery();
    
   ```

   `p => p.IncludeCustomFields`子句标识需要使用支持自定义字段项目对象。 
    
   `p => p.IncludeCustomFields.CustomFields`子句请求包含在查询结果中的自定义字段数据。 检索自定义字段内部名称后，将使用此信息。 
    
3. 加载该请求。
    
   这是在上一步的一部分。
    
4. 执行查询。
    
   ```cs
    projContext.ExecuteQuery()
   ```

5. 使用此客户端上的信息，生成请求检索与当前项目关联的自定义字段。
    
   ```cs
    foreach (PublishedProject pubProj in projContext.Projects)
    {
        //Console.WriteLine("\n\t{0}. \t{1} \n\t\t{2} \n\t\t{3} \n", 
                j++, pubProj.Id, pubProj.Name, pubProj.CreatedDate);
        CustomFieldCollection collCustF = pubProj.CustomFields;
                        
        projContext.Load(collCustF);
        projContext.ExecuteQuery();
    
   ```

6. 找到相应的自定义字段和检索的字段的内部名称。 
    
   ```cs
        foreach (CustomField oCF in collCustF)
        {
            if (oCF.Name == "Project Health")
            {
                Console.WriteLine("Name: {0}", oCF.Name);
                Console.WriteLine("InternalName: {0}", oCF.InternalName);
    
   ```

   检索自定义字段的内部名称。 高级项目 1 和 2 现在已完成。
    
7. 返回到项目上下文并检索的自定义域的值。
    
   ```cs
    Console.WriteLine("Value: {0}", 
        pubProj.IncludeCustomFields.FieldValues[oCF.InternalName]);
    
   ```

   > [!NOTE]
   > 自定义字段的值是作为索引使用的内部名称检索的。 
  
项目 ID、 项目名称、 自定义域名称、 自定义字段内部名称和自定义域值组成的三个项目的输出。
  
```cs
Project counts:31
1. Project ID:  957d5fcd-5cbf-e111-9f1e-00155d022681
        Name:           Acquisition Target Analysis
Name: Project Health
InternalName: Custom_745de6dfcfb4e11195dc00155d02c97f
Value: Green
2. Project ID:  16905202-5fbf-e111-9f1e-00155d022681
        Name:           Apparel ERP Upgrade
Name: Project Health
InternalName: Custom_745de6dfcfb4e11195dc00155d02c97f
Value: Green
3. Project ID:  dce23152-63bf-e111-9f1e-00155d022681
        Name:           Audit Tracking Solution
Name: Project Health
InternalName: Custom_745de6dfcfb4e11195dc00155d02c97f
Value: Red

```

## <a name="see-also"></a>另请参阅

有关文档和与 Project Online 和使用 CSOM 的应用程序开发相关的示例，请参阅[Project 开发门户](http://dev.office.com/project.aspx)。
    

