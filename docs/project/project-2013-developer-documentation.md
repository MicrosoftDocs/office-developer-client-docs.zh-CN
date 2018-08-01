---
title: Project 2013 开发人员文档
manager: soliver
ms.date: 04/04/2016
ms.audience: Developer
f1_keywords:
- Project
- Project 2013
- Project 2013 SDK
- Project programmability
- Project SDK
- SDK
- SDK Project
keywords:
- sdk，project 2013，Project 2013 SDK 概述
localization_priority: Normal
ms.assetid: f66adbf1-5cb5-4dd0-be08-45e1c88c010c
description: 查找文档、 代码示例、 操作方法文章和编程参考，以帮助您构建面向 Office 商店或专用应用程序目录，并以自定义和与其他桌面和业务的广泛集成 Project Server 和 Project 客户端企业项目管理应用程序。
ms.openlocfilehash: 490b5bd2fcbe2f92653b6ebc84d36e5c28cdc8c6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779549"
---
# <a name="project-2013-developer-documentation"></a>Project 2013 开发人员文档

查找文档、 代码示例、 操作方法文章和编程参考，以帮助您构建面向 Office 商店或专用应用程序目录，并以自定义和与其他桌面和业务的广泛集成 Project Server 和 Project 客户端企业项目管理应用程序。
  
欢迎使用 Microsoft Project 2013 软件开发工具包 (SDK)。 SDK 包含文档、 代码示例、 操作方法文章和编程参考，以帮助您构建相关应用程序的公用存储或专用应用程序目录，并以自定义和集成 Project Server 和 Project 客户端与其他桌面的各种和企业项目管理业务应用程序。
  
> [!NOTE]
> Project Server 2013 构建在 SharePoint Server 2013 平台上，并且 Project 2013 包括何种为其他 Office 2013 应用程序相同的基础结构。 有关文档模型的 SharePoint 加载项，基于 SharePoint 的工作流，Web 部件开发与其他 SharePoint 功能和文档的 Office 加载项，请参阅[Office 和 SharePoint 相关应用程序](http://msdn.microsoft.com/en-us/library/fp161507%28office.15%29.aspx)。 
  
## <a name="introduction-to-the-project-sdk"></a>Project SDK 的简介
<a name="pj15_Welcome_IntroToSDK"> </a>

Project Server 2013 是一个用于生成内部部署或基于云的企业项目管理解决方案和用于生成的最终用户能够发现并通过公用存储或专用应用程序目录获取应用程序的平台。 Project Server 2013 体系结构基于 Microsoft Office Project Server 2007 中, 引入的许多新增和改进的平台。 新增功能包括一个客户端对象模型 (CSOM) 若要启用对 Project Online，联机访问 Project Server 报告数据的远程事件接收器、 基于 4 版 Windows 工作流的工作流体系结构的 OData 服务的访问Foundation (WF4) 和 Office 加载项，它是在 Microsoft Office 2013 客户端应用程序中的任务窗格扩展的常见的体系结构。
  
Project Server 2013 中的主要更改是使用单个数据库代替 Project Server 2010 中的草稿、 已发布、 存档和报告数据库。 有关新功能和已弃用的功能的详细信息，请参阅[Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)。 有关 Project Server 平台中的更改的信息，请参阅[Project Server 2013 体系结构](project-server-2013-architecture.md)。 存在于 Project Server 2010 和 Project Server 2013 所基于的开发平台的概述，请参阅 MSDN 上的[Project 2010 开发入门](http://msdn.microsoft.com/en-us/library/gg607685.aspx)。 
  
Project Server 2013 基于 Microsoft.NET Framework 4 和 Microsoft SharePoint Server 2013。 文章和此 SDK 中的示例提供的起始位置用于开发自定义解决方案和应用程序;他们不能解决 Project Server 或 Project Professional 的所有可编程性功能。 [Project 开发中心](http://msdn.microsoft.com/library/4e5245c3-4891-455b-b321-1819cdd77247.aspx)包括项目文章、 博客 （英文）、 视频、 网络广播、 visual 操作方法文章和其他资源的链接。 
  
Project 2013 SDK 包括 Project Server 2013、 Project Web App、 Project Professional 2013 和 Project Standard 2013 开发人员的信息。 SDK 文章旨在帮助开发人员和可扩展性和自定义解决方案的规划评估 Project 和 Project Server 管理员。
  
### <a name="feedback"></a>反馈
<a name="pj15_Welcome_Feedback"> </a>

我们希望听到您。 在 MSDN 上 online 主题中，可以添加注释，代码示例，或为每个页面底部**社区内容**部分中的 bug 标记内容。 在安装 Project 2013 SDK 下载时，每个本地文档文章具有位于标题下方的*发送反馈*链接。 在阅读 SDK 中的任何位置，选择向 SDK 团队发送电子邮件链接。 可以发送更正、 澄清的请求或的代码示例或其他注释，并帮助我们使内容更强。 
  
### <a name="download"></a>下载
<a name="pj15_Welcome_Download"> </a>

Project 2013 SDK 下载位于[Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=30435%20)( `https://www.microsoft.com/en-us/download/details.aspx?id=30435%20`)。 下载包括 Project2013SDK.HxS （包括这篇文章的文件），相关代码示例、 可再发行程序集和其他资源。 Project 2013 SDK 尚未包含该报告数据表引用。
  
### <a name="whats-new-in-the-project-sdk"></a>Project SDK 中的新增内容
<a name="pj15_Welcome_WhatsNew"> </a>

Project 2013 SDK 的主要用途是可编程性的创建 Project Professional 2013 的应用程序、 Project Server 接口 (PSI) 服务和任务窗格应用程序提供的概述和 CSOM 和相关的功能的文档。 Project 2013 SDK 包含关键 Project Server 2013 和 Project 客户端 （Project Standard 2013、 Project Professional 2013 和 Project Web App） 的自定义区域的分步的示例。 文档不完整;将以后的发行版中添加更多的内容。 
  
作为网络通信的基础技术是 Project Server 2013，包括使用 Project Server CSOM 和使用 PSI 的内部部署开发的云应用场景中的 Windows Communication Foundation (WCF)。 旧的 ASMX web 服务引用还基于 WCF 体系结构。 Project Server 2013 中设置对 PSI web 服务 （ASMX 文件） 的引用需要追加`?wsdl`的路径的 URL 选项。 例如，`http://ServerName/ProjectServerName/_vti_bin/PSI/Resource.asmx?wsdl`。
  
> [!NOTE]
> 尽管该地址仅最常用的 Project Server 功能，但我们建议您使用 CSOM 尽可能应用程序在部署和云中。 虽然仍可在 Project Server 2013，PSI 的 ASMX 接口已被弃用。 对于需要对 PSI 的完全访问权限的内部部署应用程序，您应使用 psi 的 WCF 接口而不是 ASMX 接口。 
  
Windows 7 的计算机上开发支持通过复制到开发计算机的 CSOM 程序集的 Project Server 2013 和 SharePoint Server 2013。 SDK 下载包括用于 Project Server 和再发行许可证 CSOM 程序集。 若要获取 SharePoint CSOM 程序集，请参阅[SharePoint Server 2013 客户端组件 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=35585)。
  
对于使用 WCF 服务进行的开发，您可以设置对 PSI 代理程序集的引用或向解决方案添加 PSI 代理文件。可以设置对来自同一域中远程计算机的前端 Project Server ASMX Web 服务的直接引用，也可以使用代理程序集或代理文件。SDK 下载包括 WCF 服务和 ASMX Web 服务的代理文件，以及用于构建代理程序集和生成更新的代理文件的脚本。
  
Project Server 2013 中可以使用内部部署 Microsoft SharePoint Designer 2013 中创建声明性的 Project Server 工作流并在线使用。 SharePoint Designer 2013 在 CSOM 中使用的工作流活动属性和方法。 只能在 Project Server 计算机上支持开发和部署 Visual Studio 2012 解决方案，包括 Project Server Web 部件或 Project Web App 的自定义项。
  
有关新可编程性功能和 Project Server 2013 中弃用的功能的概述，请参阅[Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)。 使用基于 WF4 的工作流来管理创建并根据企业项目模板的项目建议的审批，另一个 Project Server 2013 中的主要更改。 
  
新主题包括：
  
- [创建 SharePoint 承载的 Project Server 外接程序](create-a-sharepoint-hosted-project-server-add-in.md)显示如何使用 Visual Studio 进行远程开发的应用程序可用于 Project Server 2013 和 Project Online。 
    
- [Project Server 2013 architecture](project-server-2013-architecture.md)说明了 Project Server 平台的主要新功能。 
    
- [Getting started with Project Server 2013 JavaScript 对象模型](getting-started-with-the-project-server-2013-javascript-object-model.md)说明如何开发可访问 Project Server 的 web 应用程序。 
    
- [与 Project Server CSOM 和.NET 入门](getting-started-with-the-project-server-csom-and-net.md)演示如何使用客户端对象模型开发应用程序，而不是使用 PSI 服务。 
    
- [Project Professional 任务窗格应用程序](task-pane-add-ins-for-project.md)引入了 Office 加载项，如应用于 Project 2013。 Office 2013 SDK 包含演示如何项目和其他 Office 2013 客户端开发任务窗格应用程序的文章。 
    
- [创建用于需求管理的 Project Server 工作流](create-a-project-server-workflow-for-demand-management.md)显示如何使用 SharePoint Designer 2013 创建 Project Server 工作流。 
    
- [ProjectData-Project OData 服务引用](https://msdn.microsoft.com/en-us/library/office/jj163015.aspx)包括概述的 OData 接口用于 Project Server 报告，以及针对**ProjectData**服务的 XML 参考主题。 
    
**Microsoft.ProjectServer.Client**命名空间中的主题和 PSI 服务中的新方法具有仅最少量文档。 从 2011 年 7 月发布的 Project 2010 SDK 未更改了大部分 PSI 服务的参考主题。 
  
### <a name="future-sdk-releases"></a>将来 SDK 版本
<a name="pj15_Welcome_FutureReleases"> </a>

Project 2013 SDK 将使用新文章和参考内容的正式发布版本的更新。
  
## <a name="sections-in-the-project-sdk"></a>Project SDK 中的各节
<a name="pj15_Welcome_SectionsInTheSDK"> </a>

Project 2013 SDK 中有两个首要节：
  
- [项目概念性和帮助文章](project-conceptual-and-how-to-articles.md)节包含主要功能和开发的分步步骤的文章的概述。 
    
- [Project Server 2013 类类库和 web 服务引用](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)部分的 PSI 服务 CSOM，以及文档的公共程序集、 Microsoft.ProjectServer.Client.dll 程序的对象模型。 
    
“概念和操作方法文章”**** 一节包括： 
  
- [新增功能和删除的功能的开发人员](updates-for-developers-in-project-2013.md)介绍主要的新可编程性功能和弃用的 Project 2013 中的功能。 
    
- [面向开发人员的 project 概述](http://msdn.microsoft.com/library/8da91ab0-af4f-429f-8241-490600e3f7bd%28Office.15%29.aspx)包括有关 Project Server 体系结构，这些文章说明如何开始使用 CSOM、 有关项目，VBA 中的新功能的信息和 Office 2013 SDK，其中包含一个引用开发的文章有关开发 Project Professional 2013 任务窗格应用程序的主题。 
    
- [编程任务的项目](project-programming-tasks.md)包含有关为 Project Server，使用 JavaScript CSOM，以及创建项目建议和工作流的需求管理创建应用程序的操作方法文章。 
    
- [Project 2013 编程参考](project-2013-programming-references.md)包括 Project Server 2013，Project Server 错误代码的信息和**ProjectData**服务的 OData 架构引用的 PSI 引用简介。 
    
> [!NOTE]
>  以下是开发和部署 EPM 解决方案和与 Project Server 2013 集成从公共 Office 商店的应用程序的要求： > 和部署开发计算机上必须安装.NET Framework 4 或.NET Framework 4.5计算机。 若要确定是否安装了正确的版本，请打开 Windows 控制面板中的**程序和功能**。 > Visual Studio 2012 安装，并使用.NET Framework 4.5。 时创建 Visual Studio 项目时，您可以选择**新建项目**对话框的下拉列表列表中的 **.NET Framework 4.0**或**NET Framework 4.5** 。 您还可以选择项目**属性**窗口的**应用程序**选项卡上的**目标框架**。 > 使用 CSOM 或 PSI，应用程序和项目任务窗格应用程序，您可以使用 Visual Studio 2010。 但是，Visual Studio 2010 不包含 Office 加载项模板、 Office 开发工具或 Office 2013 的 SharePoint 开发工具。 若要下载 Visual Studio 2012 和包括 Office 和 SharePoint 开发工具 Web 平台安装程序 (WebPI)，请参阅[下载 Office 和 SharePoint 相关应用程序](http://msdn.microsoft.com/en-us/office/apps/fp123627)。 > 我们建议您开发的测试环境中的自定义解决方案。 如果您要开发解决方案的当前版本的 Project Server 2013 和 Project 2013，他们应重新编译通过更新的引用，并可能需要进行其他更改，以使用以后的发行版。 开发任何预发布版本的解决方案可能不适用于的已发布版本。 
  
## <a name="see-also"></a>另请参阅
<a name="pj15_Welcome_AR"> </a>

- [Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)
    
- [Project Server 2013 体系结构](project-server-2013-architecture.md)
    
- [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435%20)
    
- [SharePoint Server 2013 客户端组件 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=35585)
    
- [面向开发人员的 project](http://msdn.microsoft.com/project)
    
- [Office 开发人员文档](http://msdn.microsoft.com/office)
    
- [开始针对 Project 2010 进行开发](http://msdn.microsoft.com/en-us/library/gg607685.aspx)
    
- [文档约定](http://msdn.microsoft.com/library/6b38829f-1a9d-4fb6-ad3b-01182628080a.aspx)
    
- [SharePoint 2013 中的辅助功能](http://msdn.microsoft.com/en-us/library/jj841103.aspx)
    
- [Microsoft Office 365 中的辅助功能](http://www.microsoft.com/enable/products/office365/)
    
- [Microsoft 联机隐私声明](https://privacy.microsoft.com/en-us/privacystatement)
    

