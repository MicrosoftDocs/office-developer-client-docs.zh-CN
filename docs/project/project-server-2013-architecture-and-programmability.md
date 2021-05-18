---
title: Project Server 2013 体系结构和可编程性
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
f1_keywords:
- architecture
- platform
- Project
- Project architecture
- Project programmability
- Project Server architecture
- Project Server programmability
keywords:
- project 2013， architecture and programmability， Programmability， Project Server，Project 2013， benefits for EPM， Architecture， and Project Server
localization_priority: Normal
ms.assetid: 9ea3b3c1-fb90-454a-b8e6-abc44fca663d
description: 本节中的文章介绍 Enterprise Project Management (EPM) 解决方案的整体体系结构，该解决方案结合了 Project Professional 2013、Project Server 2013、Project Web App 和 SharePoint Server 2013。
ms.openlocfilehash: 44cd5a32b8d3de421ffe3b2d9bf0137146bc4c4e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413785"
---
# <a name="project-server-2013-architecture-and-programmability"></a>Project Server 2013 体系结构和可编程性

本节中的文章介绍 Enterprise Project Management (EPM) 解决方案的整体体系结构，该解决方案结合了 Project Professional 2013、Project Server 2013、Project Web App 和 SharePoint Server 2013。
  
ProjectServer 2013 使用 .NET Framework 4 构建，是 Project Server 的第三个主要版本，可提供真正的多层体系结构。 对于云访问，Project Server 2013 实现了客户端对象模型 (CSOM) 以及可用于 Web 应用程序、移动应用程序和 Silverlight 应用程序的报表的 OData 服务。 对于本地应用程序，客户端可使用 CSOM 或 Project Server 接口 (PSI) 服务。 
  
## <a name="introduction-to-project-server-architecture"></a>Project Server 体系结构简介

本节中的主题介绍 Enterprise Project Management (EPM) 解决方案的整体体系结构，该解决方案结合了 Project Professional 2013、Project Server 2013、Project Web App 和 SharePoint Server 2013。
  
若要以编程方式Project服务器，您应将 CSOM 或 PSI 服务与 Windows Communication Foundation (WCF) 接口一同使用。 PSI 的 ASMX Web 服务接口在 Project Server 2013 中已弃用，但仍可以正常工作。 利用 PSI，可使用数据集实现高效访问，并且可以为服务器端事件创建处理程序。 CSOM 本身使用 PSI 访问 Project Server 业务对象层。 Project Server 2013 使用数据访问层中的单个数据库，而不是四个 Project 服务器数据库。
  
ProjectServer 2013 与 SharePoint Server 2013 深度集成。 Project Application Service 可与服务器场中的其他 SharePoint 网站集关联。 Project Server 可对网站集中的 SharePoint 任务列表进行操作和报告，并可以获得完全控制权，这样一来，Project Server 便能将任务列表作为企业项目进行导入和管理。 Project服务器还使用 WF4 Windows Workflow Foundation (4) ，并添加需求管理解决方案的工作流活动。
  
有关 Project 2013 为开发人员提供的许多新功能以及已弃用的功能的讨论，请参阅[Project 2013](updates-for-developers-in-project-2013.md)中的开发人员更新。
  
## <a name="in-this-section"></a>本节内容

[Project Server 2013](project-server-2013-architecture.md)体系结构介绍了 Project 2013 平台的主要部分，包括客户端和服务器。 
  
[Project Server 可编程](project-server-programmability.md)性讨论 Project Server 2013 的主要扩展性功能、自定义 Project Web App 以及升级为以前的 Project Server 版本构建的应用程序。 
  
[What the PSI does and does not do](what-the-psi-does-and-does-not-do.md)描述了可使用 PSI 的方案并列出了 PSI 不能实现的操作。 
  
[What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md)描述了可使用 CSOM 的方案并列出了 CSOM 不能实现的操作。 
  
### <a name="topics-not-covered"></a>未涵盖的主题

体系结构和可编程性部分中的文章未记录 Project 桌面客户端 (Project Standard 2013 和 Project Professional 2013) 或 Project Web App 的功能。 
  
Visual Basic for Applications (VBA) 帮助在 Project Standard 和 Project Professional 中的 Visual Basic 编辑器中可用。
  
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)
    
- [开始开发 Project Server 工作流](getting-started-developing-project-server-workflows.md)
    

