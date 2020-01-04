---
title: Project 2013 开发人员文档
manager: lindalu
ms.date: 12/19/2019
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
- sdk, project 2013, Project 2013, SDK 概述
ms.assetid: f66adbf1-5cb5-4dd0-be08-45e1c88c010c
description: 查找文档、代码示例、操作方法文章和编程参考以帮助构建针对 Office 的应用程序或私有应用程序目录，以及自定义 Project Server 和 Project 客户端并将其与各种其他桌面应用程序和业务应用程序集成以进行企业项目管理。
localization_priority: Priority
ms.openlocfilehash: 1b6227bb25810be04bc87abb418f9966b593bf1c
ms.sourcegitcommit: 55205b4ec1376713d31e75d195e031798fb2c6ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2019
ms.locfileid: "40825756"
---
# <a name="project-2013-developer-documentation"></a>Project 2013 开发人员文档

查找文档、代码样本、操作说明文章和编程参考，有助于生成 AppSource 应用程序。 了解如何自定义 Project Server 和 Project 客户端，并将它们与其他多种桌面和商业应用程序集成，以实现企业项目管理（EPM）。
   
> [!NOTE]
> Project Server 2013 基于 SharePoint Server 2013 平台，并且 Project 2013 中使用的大部分基础结构与其他 Office 2013 应用程序相同。 有关 SharePoint 加载项模型、基于 SharePoint 的工作流、Web 部件、其他 SharePoint 功能开发以及 Office 加载项的文档，请参阅 [SharePoint 加载项](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins)和 [Office 加载项](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)。 
  
## <a name="introduction-to-the-project-software-development-kit-sdk"></a>项目软件开发工具包 (SDK)简介
<a name="pj15_Welcome_IntroToSDK"> </a>

Project Server 2013 是一个平台，用于构建本地或基于云的企业项目解决方案以及用于构建最终用户可以通过 AppSource（前称 Office Store）发现和获取的应用程序。 Project Server 2013 体系结构基于 Microsoft Office Project Server 2007 中引入的平台，具有许多新增功能和增强功能。 新增功能包括支持访问 Project Online 的客户端对象模型 (CSOM)、用于在线访问 Project Server 报告数据的 OData 服务、远程事件接收器、基于 Windows Workflow Foundation (WF4) 版本 4 和 Office 加载项的工作流体系结构，这款常用的体系结构适用于 Microsoft Office 2013 客户端应用程序中的任务窗格扩展。
  
Project Server 2013 中的主要变化在于使用单个数据库代替 Project Server 2010 中的“草稿”、“已发布”、“存档”和“报告”数据库。 有关新增功能和弃用功能的详细信息，请参阅 [Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)。 有关 Project Server 平台中的变化的信息，请参阅 [Project Server 2013 体系结构](project-server-2013-architecture.md)。 有关 Project Server 2010 中存在的基于 Project Server 2013 的开发平台概述，请参阅 MSDN 上的 [Project 2010 开发入门](https://msdn.microsoft.com/library/gg607685.aspx)。 
  
Project Server 2013 基于 Microsoft .NET Framework 4 和 Microsoft SharePoint Server 2013。 可以从此 SDK 中的文档和示例入手，开始开发自定义解决方案和应用程序；它们无法提供 Project Server 或 Project Professional 的可编程性功能。 可以通过 [Project 开发人员中心](https://msdn.microsoft.com/library/4e5245c3-4891-455b-b321-1819cdd77247.aspx)的链接访问 Project 文章、博客、视频、广播、可视化操作方法文档和其他资源。 
  
Project 2013 SDK 中包括 Project Server 2013、Project Web App、Project Professional 2013 和 Project Standard 2013 的开发人员信息。 SDK 文章旨在帮助开发人员和管理员评估 Project 和 Project Server，以便扩展和规划自定义解决方案。
  
### <a name="feedback"></a>反馈
<a name="pj15_Welcome_Feedback"> </a>

欢迎大家向我们提供反馈。 在 MSDN 的联机主题上，你可以在每个页面底部的“**社区内容**”部分添加备注、代码示例或将内容标记为错误。 安装 Project 2013 SDK 下载时，每篇本地文档文章的标题下方均有一个“*发送反馈*”的链接。 阅读 SDK 时，可随时选择该链接向 SDK 团队发送电子邮件。 可以发送校正、澄清或代码示例请求或者其他评论，帮助我们优化内容。 
  
### <a name="download"></a>下载
<a name="pj15_Welcome_Download"> </a>

可以在 [Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=30435%20) (`https://www.microsoft.com/en-us/download/details.aspx?id=30435%20`) 获取 Project 2013 SDK下载。 下载包括 Project2013SDK.HxS（包含此文章的文件）、相关代码示例、可再发行程序集和其他资源。 但是，Project 2013 SDK 中不包括报告数据表引用。
  
### <a name="whats-new-in-the-project-sdk"></a>Project SDK 中的新增功能
<a name="pj15_Welcome_WhatsNew"> </a>

Project 2013 SDK 的主要目的在于提供 CSOM 和相关功能的可编程性和文档概述，以便创建应用程序、Project Server Interface (PSI) 接口服务和适用于 Project Professional 2013 的任务窗格应用程序。 Project 2013 SDK 中包含自定义 Project Server 2013 和 Project 客户端（Project Standard 2013、Project Professional 2013 和 Project Web App）的关键部分的分步示例。 文档目前上不完整；在以后的版本中将会添加更多内容。 
  
网络通信的基础技术是 Project Server 2013 中的 Windows Communication Foundation (WCF)，包括使用 Project Server CSOM 的云方案和使用 PSI 的本地开发。 旧版 ASMX Web 服务引用也是基于 WCF 体系结构。 在 Project Server 2013 中设置 PSI Web 服务引用（ASMX 文件）需要在路径中附加 `?wsdl` URL 选项。 例如，`https://ServerName/ProjectServerName/_vti_bin/PSI/Resource.asmx?wsdl`。
  
> [!NOTE]
> 尽管它仅提供了最常用的 Project Server 功能，但对于本地和云中的应用程序，我们建议你尽可能使用 CSOM。 适用于 PSI 的 ASMX 接口已弃用，但 Project Server 2013 中仍提供了此接口。 对于需要完全访问 PSI 的本地应用程序，应使用适用于 PSI 的 WCF 接口，而不是 ASMX 接口。 
  
通过将适用于 Project Server 2013 和 SharePoint Server 2013 的 CSOM 程序集复制到开发计算机来支持在 Windows 7 计算机上进行开发。 SDK 下载中包括适用于 Project Server 的程序集和可再发行的许可证。 若要获取 SharePoint CSOM 程序集，请参阅 [SharePoint Server 2013 客户端组件 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=35585).
  
对于使用 WCF 服务进行的开发，您可以设置对 PSI 代理程序集的引用或向解决方案添加 PSI 代理文件。可以设置对来自同一域中远程计算机的前端 Project Server ASMX Web 服务的直接引用，也可以使用代理程序集或代理文件。SDK 下载包括 WCF 服务和 ASMX Web 服务的代理文件，以及用于构建代理程序集和生成更新的代理文件的脚本。
  
在 Project Server 2013 中，可使用适合于本地和联机使用的 Microsoft SharePoint Designer 2013 创建声明性 Project Server。 SharePoint Designer 2013 使用 CSOM 中的工作流活动属性和方法。 仅在 Project Server 计算机上支持开发和部署包含 Project Server Web 部件或 Project Web App 自定义项的 Visual Studio 2012 解决方案。
  
有关 Project Server 2013 中的新增可编程性功能和弃用功能的概述，请参阅 [Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)。 Project Server 2013 中的另一个主要变化是使用基于 WF4 的工作流来管理基于企业项目版本的项目方案的创建和审批。 
  
新主题包括以下内容：
  
- [创建 SharePoint 托管的 Project Server 加载项](create-a-sharepoint-hosted-project-server-add-in.md)介绍了如何使用 Visual Studio 远程部署可与 Project Server 2013 和 Project Online 搭配使用的应用程序。 
    
- [Project Server 2013 体系结构](project-server-2013-architecture.md)介绍了 Project Server 平台的主要新增功能。 
    
- [Project Server 2013 JavaScript 对象模型入门](getting-started-with-the-project-server-2013-javascript-object-model.md)介绍了如何开发可访问 Project Server 的 Web 应用程序。 
    
- [Project Server CSOM 和 .NET 入门](getting-started-with-the-project-server-csom-and-net.md)介绍了如何使用客户端对象模型开发应用程序，而无需使用 PSI 服务。 
    
- [Project Professional 任务窗格应用程序](task-pane-add-ins-for-project.md)介绍了 Project 2013 中应用的 Office 加载项。 Office 2013 SDK 中包含有用于介绍如何开发适用于 Project 和其他 Office 2013 客户端的任务窗格应用程序的文章。 
    
- [创建 Project Server 工作流以用于需求管理](create-a-project-server-workflow-for-demand-management.md)演示了如何使用 SharePoint Designer 2013 创建 Project Server 工作流。 
    
- [ProjectData - Project OData 服务参考](https://msdn.microsoft.com/library/office/jj163015.aspx)包括适用于 Project Server 报告的 OData 接口的概述，以及针对 **ProjectData** 服务的 XML 参考主题。 
    
只有少量文档主题涉及 PSI 服务中的 **Microsoft.ProjectServer.Client** 命名空间和新方法。 大多数 PSI 服务参考主题与 2011 年 7 月发行的 Project 2010 SDK 保持相同。 
  
### <a name="future-sdk-releases"></a>未来的 SDK 版本
<a name="pj15_Welcome_FutureReleases"> </a>

Project 2013 SDK 将随公开发行版的新文章和参考内容一起更新。
  
## <a name="sections-in-the-project-sdk"></a>Project SDK 中的章节
<a name="pj15_Welcome_SectionsInTheSDK"> </a>

Project 2013 SDK 中具有两个顶级章节：
  
- [Project 概念和操作方法文章](project-conceptual-and-how-to-articles.md)一节包含主要功能的概述和有关开发的分步步骤的文章。 
    
- [Project Server 2013 类库和 Web 服务引用](https://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)一节记录了公共程序集的对象模型、CSOM 的 Microsoft.ProjectServer.Client.dll 程序集和 PSI 服务。 
    
**概念和操作方法文档**一节包括以下小节： 
  
- [面向开发人员的新增功能和已弃用功能](updates-for-developers-in-project-2013.md)介绍了 Project 2013 中主要的新可编程性功能和已弃用功能。 
    
- [面向开发人员的 Project 概述](https://msdn.microsoft.com/library/8da91ab0-af4f-429f-8241-490600e3f7bd%28Office.15%29.aspx)包括有关 Project Server 体系结构的文章、说明如何开始使用 CSOM 进行开发的文章、有关 VBA for Project 中的新增功能的信息，以及对 Office 2013 SDK 的参考（其中包含有关为 Project Professional 2013 开发任务窗格应用程序的主题）。 
    
- [Project 编程任务](project-programming-tasks.md)包括有关创建适用于 Project Server 的应用程序、使用 JavaScript 和 CSOM 以及创建适用于需求管理的项目方案和工作流的操作方法文章。 
    
- [Project 2013 编程参考](project-2013-programming-references.md)介绍了 Project Server 2013 的 PSI 参考、有关 Project Server 错误代码的信息以及 **ProjectData** 服务的 OData 架构参考。 
    
> [!NOTE]
>  以下是开发和部署与 Project Server 2013 集成的 AppSource 中的 EPM 解决方案和应用程序的要求：> 必须在开发计算机和部署计算机上安装 .NET Framework 4 或 .NET Framework 4.5。 若要确定是否安装了正确的版本，请在 Windows 控制面板中打开“**程序和功能**”。 > Visual Studio 2012 安装和使用 .NET Framework 4.5。 创建 Visual Studio 项目时，可以在”**新建项目**”对话框的下拉列表中选择 **.NET Framework 4.0** 或 **NET Framework 4.5**。 也可以在项目“**属性**”窗口的“**应用程序**”选项卡上选择“**目标框架**”。 > 对于使用 CSOM 或 PSI 的应用程序以及 Project 任务窗格应用程序，可以使用 Visual Studio 2010。 但是，Visual Studio 2010 不包含 Office 加载项模板、Office 开发工具或适用于 Office 2013 的 SharePoint 开发工具。 若要下载 Visual Studio 2012 以及包含 Office 和 SharePoint 开发工具的 Web 平台安装程序 (WebPI)，请参阅 [Office 和 SharePoint 应用程序下载](https://msdn.microsoft.com/office/apps/fp123627)。 > 建议你在测试环境中开发自定义解决方案。 如果在当前版本的 Project Server 2013 和 Project 2013 中开发解决方案，则会使用更新后的参考重新编译这些解决方案，这可能需要进行额外的更改才适用于后续版本。 针对任何预发行版本开发的解决方案可能不适用于公开发行的版本。 
  
## <a name="see-also"></a>另请参阅
<a name="pj15_Welcome_AR"> </a>

- [Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)
    
- [Project Server 2013 体系结构](project-server-2013-architecture.md)
    
- [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435%20)
    
- [SharePoint Server 2013 客户端组件 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=35585)
    
- [面向开发人员的 Project](https://msdn.microsoft.com/project)
    
- [Office 开发人员文档](https://msdn.microsoft.com/office)
    
- [Project 2010 开发入门](https://msdn.microsoft.com/library/gg607685.aspx)
    
- [文档约定](https://msdn.microsoft.com/library/6b38829f-1a9d-4fb6-ad3b-01182628080a.aspx)
    
- [SharePoint 2013 中的辅助功能](https://msdn.microsoft.com/library/jj841103.aspx)
    
- [Microsoft Office 365 中的辅助功能](https://www.microsoft.com/enable/products/office365/)
    
- [Microsoft Online 隐私声明](https://privacy.microsoft.com/zh-CN/privacystatement)
    

