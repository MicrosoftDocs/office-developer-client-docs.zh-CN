---
title: 应用示例提供程序模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: da487569-f2f0-404c-b944-38ed1c1b82bb
description: '示例 Outlook Social Connector (OSC) 提供程序模板为您提供一个框架，用于实现 OSC 提供程序。 '
ms.openlocfilehash: 2388da58690e1870434c576bfa68649937156c54
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779192"
---
# <a name="applying-a-sample-provider-template"></a>应用示例提供程序模板

示例 Outlook Social Connector (OSC) 提供程序模板为您提供一个框架，用于实现 OSC 提供程序。 C + + C# 和 Visual Basic 中提供了提供程序模板。 这些模板是只提供程序开发; 的起始点模板不能解决编写为提供程序的实现代码和创建提供程序的安装包。 下面的过程演示如何在您开始开发提供程序时应用的 OSC 提供程序模板。
  
### <a name="to-apply-an-osc-provider-template"></a>若要应用的 OSC 提供程序模板

1. 在**开始**菜单中，右键单击**Microsoft Visual Studio 2010** ，然后单击**以管理员身份运行**命令。 出现提示时，请单击**是**以管理员身份运行 Visual Studio。 
    
2. 将项目名称和模板中的命名空间更改为您的项目名称和命名空间标识符。
    
3. 修改**AssemblyInfo**类指定相应的程序集信息。 
    
4. 实现接口成员标记为**待办事项**并根据需要添加更多的依赖关系和参考。 
    
5. 生成项目。
    
6. 确保提供程序程序集 ProgID 列为下的键`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`。
    
7. 分发安装项目，请在 Visual Studio 或您选择的安装程序工具创建安装项目。
    
8. 安装项目应完成 COM 注册您的程序集，并还创建 ProgID 键，如步骤 5 中列出。
    
## <a name="see-also"></a>另请参阅

- [下载示例](downloading-the-samples.md)
- [OSC 示例模板](osc-sample-templates.md)

