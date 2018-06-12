---
title: 开发 Project Server 工作流入门
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 735bbb04-a8c1-46c0-a346-42050f0ac9b1
description: 管理 Project Server 2013 中的过程包括帮助您的工作流的需求管理项目建议和项目组合分析。 本节包含演示如何为 Project Server 中创建工作流的文章。
ms.openlocfilehash: 275f61b7992423a5e10a7ba90b8c76433290343e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779409"
---
# <a name="getting-started-developing-project-server-workflows"></a>开发 Project Server 工作流入门

管理 Project Server 2013 中的过程包括帮助您的工作流的需求管理项目建议和项目组合分析。 本节包含演示如何为 Project Server 中创建工作流的文章。
  
Project Server 2013 工作流使用的 SharePoint Server 2013 工作流平台，基于版本 4 的 Windows Workflow Foundation (WF4)。 基于 WF4 的工作流是声明性，这意味着该工作流设计工具将工作流阶段、 操作、 条件和其他元素保存到 XAML 代码，解释在运行时。 您可以使用 SharePoint Designer 2013 或 Visual Studio 2012 创建声明性工作流。 工作流需要的工作流管理器客户端 1.0 执行引擎，可以在内部部署解决方案的本地服务器或 Project Online 的解决方案的远程服务器上。
  
您可以使用 SharePoint Designer 2013 创建相对简单的声明性工作流。 对于复杂的工作流的可重用工作流模板，您可以使用 Visual Studio 2012 开发和调试 Project Web app 的工作流。 有关详细信息，请参阅[创建 Project 工作流使用 Visual Studio 2012](http://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx)。
  
> [!IMPORTANT]
> 测试安装的 Project Server，生产安装，用于开发和测试工作流。 预发布版本的 Project Server 2013 开发的工作流必须要测试的发行版，并且可能需要再次创建和重新部署。 
  
## <a name="in-this-section"></a>本节内容

[创建用于命令管理的 Project Server 工作流](create-a-project-server-workflow-for-demand-management.md)
  
## <a name="see-also"></a>另请参阅



[批量更新自定义字段和从 Project Online 中的工作流创建项目网站](bulk-update-custom-fields-and-create-project-sites-from-workflow-in-project.md)


[SharePoint Designer 2013 和 Visio 2013 中的工作流开发](http://msdn.microsoft.com/en-us/library/jj163272%28office.15%29.aspx)
  
[SharePoint 工作流的新增功能](http://msdn.microsoft.com/en-us/library/jj163177.aspx)
  
[使用 Visual Studio 开发 SharePoint 2013 工作流](http://msdn.microsoft.com/en-us/library/jj163199.aspx)
  
[创建项目工作流使用 Visual Studio 2012](http://blogs.msdn.com/b/project_programmability/archive/2012/11/07/creating-project-workflows-using-visual-studio-2012.aspx)
  
[Windows Workflow Foundation](http://msdn.microsoft.com/en-us/library/dd489441.aspx)
  
[开发人员的简介到 Windows Workflow Foundation (WF).NET 4 中](http://msdn.microsoft.com/en-us/library/ee342461.aspx)
  
[(White paper) 的需求管理漫游指南](http://msdn.microsoft.com/en-us/library/ff973112.aspx)

