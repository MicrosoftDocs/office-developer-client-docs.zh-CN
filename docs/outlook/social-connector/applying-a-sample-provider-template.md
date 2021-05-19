---
title: 应用示例提供程序模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: da487569-f2f0-404c-b944-38ed1c1b82bb
description: '使用 OSC Outlook连接器 (OSC) 模板的示例为您提供了一个实现 OSC 提供程序的框架。 '
ms.openlocfilehash: 10fb21ab640e298bc655b8cad554fae789e2ad47
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425909"
---
# <a name="applying-a-sample-provider-template"></a>应用示例提供程序模板

使用 OSC Outlook连接器 (OSC) 模板的示例为您提供了一个实现 OSC 提供程序的框架。 提供程序模板以 C++、C# 和 Visual Basic 提供。 这些模板只是提供程序开发的起点;这些模板不编写提供程序的实现代码和为提供程序创建安装包。 以下过程演示如何在开始开发提供程序时应用 OSC 提供程序模板。
  
### <a name="to-apply-an-osc-provider-template"></a>应用 OSC 提供程序模板

1. 在"**开始"** 菜单上，右键单击 **"Microsoft Visual Studio 2010"，** 然后单击"以管理员 **角色运行"** 命令。 当系统提示时，单击 **"** 是"Visual Studio管理员运行此配置。 
    
2. 将模板中的项目名称和命名空间更改为项目名称和命名空间标识符。
    
3. 修改 **AssemblyInfo** 类以指定相应的程序集信息。 
    
4. 根据需要实现标记为 **微软待办并** 添加更多依赖项和引用。 
    
5. 生成项目。
    
6. 确保提供程序程序集 ProgID 在 下作为键列出  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` 。
    
7. 若要分发安装项目，请用自己Visual Studio或设置工具创建安装项目。
    
8. 安装项目应完成程序集的 COM 注册，并创建步骤 5 中列出的 ProgID 密钥。
    
## <a name="see-also"></a>另请参阅

- [下载示例](downloading-the-samples.md)
- [OSC 示例模板](osc-sample-templates.md)

