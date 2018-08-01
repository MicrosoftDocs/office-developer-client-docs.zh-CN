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
- project 2013、 EPM、 体系结构和 Project Server 体系结构和可编程性，可编程性 （英文）、 Project Server、 Project 2013 的好处
localization_priority: Normal
ms.assetid: 9ea3b3c1-fb90-454a-b8e6-abc44fca663d
description: 本节中的文章介绍了 Enterprise Project Management (EPM) 解决方案，从而结合使用 Project Professional 2013、 Project Server 2013、 Project Web App 和 SharePoint Server 2013 的整体体系结构。
ms.openlocfilehash: 6b5ab94968dbb996a370e0e5abb89813f5e41ef7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779554"
---
# <a name="project-server-2013-architecture-and-programmability"></a>Project Server 2013 体系结构和可编程性

本节中的文章介绍了 Enterprise Project Management (EPM) 解决方案，从而结合使用 Project Professional 2013、 Project Server 2013、 Project Web App 和 SharePoint Server 2013 的整体体系结构。
  
Project Server 2013 使用.NET Framework 4 和是 Project Server 提供的则返回 true 的多层体系结构的第三个主要版本。 云访问 Project Server 2013 中的 web 应用程序、 移动应用程序和 Silverlight 应用程序实现客户端对象模型 (CSOM) 和可用于报告的 OData 服务。 对于应用程序的本地客户端可以使用 CSOM 或 Project Server 接口 (PSI) 的服务。 
  
## <a name="introduction-to-project-server-architecture"></a>Project Server 体系结构简介

本节中的主题介绍 Enterprise Project Management (EPM) 解决方案，从而结合使用 Project Professional 2013、 Project Server 2013、 Project Web App 和 SharePoint Server 2013 的整体体系结构。
  
以编程方式访问 Project Server，您应与 Windows Communication Foundation (WCF) 接口中使用 CSOM 或 PSI 服务。 PSI 的 ASMX web 服务界面在 Project Server 2013 中已弃用，但仍有效。 PSI 使用数据集启用高效的访问，并可以创建的服务器端事件处理程序。 CSOM 本身使用 PSI 访问的 Project Server 业务对象层。 而不是四个 Project Server 数据库，Project Server 2013 使用数据访问层中的单个数据库。
  
Project Server 2013 与 SharePoint Server 2013 深集成。 Project 应用程序服务可与其他服务器场中的 SharePoint 网站集相关联。 Project Server 可以与运行并报告任务列表企业项目作为 SharePoint 任务列表中的网站集和可以也会获得 Project Server 其中导入和管理的完全控制。 Project Server 也使用的 Windows Workflow Foundation (WF4) 版本 4，并添加工作流活动的需求管理解决方案。
  
Project 2013 为开发人员提供的许多新功能和已被弃用的功能的讨论，请参阅[Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)。
  
## <a name="in-this-section"></a>本节内容

[Project Server 2013 architecture](project-server-2013-architecture.md)介绍 Project 2013 平台，包括客户端和服务器的主要部分。 
  
[Project Server programmability](project-server-programmability.md)讨论了 Project Server 2013，自定义 Project Web App 和 Project Server 的早期版本构建的升级应用程序的主要扩展性功能。 
  
[What the PSI does and does not do](what-the-psi-does-and-does-not-do.md)描述了可使用 PSI 的方案并列出了 PSI 不能实现的操作。 
  
[What the CSOM does and does not do](what-the-csom-does-and-does-not-do.md)描述了可使用 CSOM 的方案并列出了 CSOM 不能实现的操作。 
  
### <a name="topics-not-covered"></a>未涵盖的主题

*体系结构和可编程性*部分中的文章未记录 Project 桌面客户端 （Project Standard 2013 和 Project Professional 2013） 或 Project Web App 的功能。 
  
Visual Basic for Applications (VBA) 帮助在 Project Standard 和 Project Professional 中的 Visual Basic 编辑器中可用。
  
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [Project 2013 中面向开发人员的更新](updates-for-developers-in-project-2013.md)
    
- [开发 Project Server 工作流入门](getting-started-developing-project-server-workflows.md)
    

