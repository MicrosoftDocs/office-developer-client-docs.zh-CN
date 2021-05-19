---
title: 开始开发 Project Server 工作流
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 735bbb04-a8c1-46c0-a346-42050f0ac9b1
description: Project Server 2013 中的需求管理流程包括可帮助您管理项目建议和项目组合分析的工作流。 本节中的文章说明了如何为 Project Server 创建工作流。
ms.openlocfilehash: 0a09022e63528f50ee4f0c8bd69bd6c34c5d8753
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344469"
---
# <a name="getting-started-developing-project-server-workflows"></a>开始开发 Project Server 工作流

Project Server 2013 中的需求管理流程包括可帮助您管理项目建议和项目组合分析的工作流。 本节中的文章说明了如何为 Project Server 创建工作流。
  
Project服务器 2013 工作流使用 SharePoint Server 2013 工作流平台，该平台基于 Windows Workflow Foundation (WF4 版本 4) 。 基于 WF4 的工作流是声明性工作流，这意味着工作流设计工具将工作流阶段、操作、条件和其他元素保存到 XAML 代码中，这将运行时进行解释。 可以使用 Designer 2013 或 SharePoint 2012 Visual Studio声明性工作流。 工作流需要 工作流管理器 Client 1.0 执行引擎，该引擎可以位于本地解决方案的本地服务器上，也可以位于远程服务器上Project Online解决方案。
  
您可以使用 SharePoint Designer 2013 创建相对简单的声明性工作流。 对于可以重复使用的复杂工作流和工作流模板，您可以使用 Visual Studio 2012 开发和调试 Project Web App。 有关详细信息，请参阅[Creating Project Workflows using Visual Studio 2012](https://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx)。
  
> [!IMPORTANT]
> 使用 Project Server 的测试安装而非生产安装来开发和测试工作流。 必须为发布版本测试为 Project Server 2013 的预发行版开发的工作流，并且可能需要再次创建和重新部署。 
  
## <a name="in-this-section"></a>本节内容

[为需求Project创建一个 Project Server 工作流](create-a-project-server-workflow-for-demand-management.md)
  
## <a name="see-also"></a>另请参阅



[批量更新自定义域，然后从工作流创建Project Online网站](bulk-update-custom-fields-and-create-project-sites-from-workflow-in-project.md)


[SharePoint Designer 2013 和 Visio 2013 中的工作流开发](https://msdn.microsoft.com/library/jj163272%28office.15%29.aspx)
  
[SharePoint 工作流的新增功能](https://msdn.microsoft.com/library/jj163177.aspx)
  
[使用 Visual Studio 开发 SharePoint 2013 工作流](https://msdn.microsoft.com/library/jj163199.aspx)
  
[使用 Project 2012 创建Visual Studio工作流](https://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx)
  
[Windows Workflow Foundation](https://msdn.microsoft.com/library/dd489441.aspx)
  
[开发人员对 .NET 4 Windows Workflow Foundation (WF) 简介](https://msdn.microsoft.com/library/ee342461.aspx)
  
[将需求管理指南 (白皮书) ](https://msdn.microsoft.com/library/ff973112.aspx)

