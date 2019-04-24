---
title: 应用示例提供程序模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: da487569-f2f0-404c-b944-38ed1c1b82bb
description: '示例 Outlook Social Connector (.osc) 提供程序模板为您提供了实现 .osc 提供程序的框架。 '
ms.openlocfilehash: 10fb21ab640e298bc655b8cad554fae789e2ad47
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281125"
---
# <a name="applying-a-sample-provider-template"></a>应用示例提供程序模板

示例 Outlook Social Connector (.osc) 提供程序模板为您提供了实现 .osc 提供程序的框架。 提供程序模板在 c + +、c # 和 Visual Basic 中可用。 这些模板只是提供程序开发的起始点;这些模板不会对提供程序的实现代码进行地址编写, 也不会为提供程序创建安装程序包。 下面的过程演示如何在开始开发提供程序时应用 .osc 提供程序模板。
  
### <a name="to-apply-an-osc-provider-template"></a>应用一个 .osc 提供程序模板

1. 在 "**开始**" 菜单上, 右键单击 " **Microsoft Visual Studio 2010** ", 然后单击 "**以管理员身份运行**" 命令。 出现提示时, 单击 **"是"** 以管理员身份运行 Visual Studio。 
    
2. 将模板中的项目名称和命名空间更改为项目名称和命名空间标识符。
    
3. 修改**AssemblyInfo**类以指定适当的程序集信息。 
    
4. 根据需要, 实现标记为待办**任务**并添加更多依赖项和引用的接口成员。 
    
5. 生成项目。
    
6. 确保提供程序集 ProgID 作为`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`中的键列出。
    
7. 若要分发安装项目, 请在 Visual Studio 中创建一个安装项目或您选择的安装工具。
    
8. 您的安装项目应完成对程序集的 COM 注册, 并创建第5步中列出的 ProgID 键。
    
## <a name="see-also"></a>另请参阅

- [下载示例](downloading-the-samples.md)
- [.osc 示例模板](osc-sample-templates.md)

