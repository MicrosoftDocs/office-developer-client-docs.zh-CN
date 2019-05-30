---
title: 开发具有 OSC XML 架构的提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0872b1b9-c21f-4bba-8cf1-4b010d8d7fb6
description: Outlook Social Connector (.OSC) 提供程序 XML 架构定义从社交网络通过网络的 .OSC 提供程序传递给 .OSC 的大量信息的格式。
ms.openlocfilehash: 2346e23beb2de1664ec90263a8f5db5d46c54e6f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539253"
---
# <a name="developing-a-provider-with-the-osc-xml-schema"></a>开发具有 OSC XML 架构的提供程序

Outlook Social Connector (.OSC) 提供程序 XML 架构定义从社交网络通过网络的 .OSC 提供程序传递给 .OSC 的大量信息的格式。 通过 XML 架构, .OSC 提供程序可以使用以下三个主要元素、**功能**、**好友**和**microsoft.office.server.activityfeed**, 在社交网络上指定提供者、好友和活动源项目的功能及其孩子单元. .OSC 提供程序在 .OSC 提供程序扩展性中实现接口及其方法, 将 XML 字符串作为符合 .OSC 提供程序 XML 架构的输出参数返回。 .OSC 调用这些方法来获取可理解的信息, 如 XML 架构所定义的那样。
  
> [!NOTE]
> .OSC 提供程序扩展性支持通过将`DebugProviders` `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`注册表项的值设置为1来调试提供程序。 启用提供程序调试后, .OSC 将根据您在**xmlns** xml 属性中指定的 .osc xml 架构的版本验证提供程序 xml。 对于自 Outlook Social Connector 2013 以来的 .osc 1.1 和 .OSC 版本, 请按如下所示指定**xmlns**属性:`xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`
  
## <a name="in-this-section"></a>本节内容

- [同步朋友和活动](synchronizing-friends-and-activities.md): 介绍了 .osc 提供商可在社交网络上同步朋友、非好友和活动的各种方式。 
    
- [.Osc 提供程序 XML 示例](osc-provider-xml-examples.md): 包括 xml 示例, 演示如何使用 .osc XML 架构在社交网络上指定 .osc 提供者、好友和活动源项目的功能。
    
- [XML for The 功能](xml-for-capabilities.md): 说明了[ISocialProvider:: GETCAPABILITIES](isocialprovider-getcapabilities.md)方法, .OSC 使用它从 .osc 提供程序获取功能 XML **** 中的功能信息。 本节还介绍了 .OSC 提供程序 XML 架构中的 XML 元素, 这些元素允许 .OSC 提供程序指定其功能, 包括如何对用户进行身份验证以及如何同步好友和活动。 
    
- [适用于好友的 XML](xml-for-friends.md): 提供了 .osc 用于获取来自 .osc 提供商的朋友信息的 api 示例**** 。 本节还介绍了**好友**XML 中的元素。 
    
- [XML 的活动](xml-for-activities.md): 提供了 .osc 用于从 .osc 提供程序获取活动信息 (以**microsoft.office.server.activityfeed** XML 表示) 的 api 示例。 本节还介绍了 .OSC 提供程序 XML 架构中的 XML 元素, 这些元素允许 .OSC 提供程序指定活动源。 活动源包括生成活动源项目的网络、每个活动源项目的详细信息 (如活动的所有者、类型和发布日期) 以及显示该活动的模板。 
    
## <a name="reference"></a>参考

- [Outlook Social Connector 提供程序参考](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关部分

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [.OSC 示例模板](osc-sample-templates.md)
  
- [.OSC 典型调用序列](osc-typical-calling-sequences.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  
- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a>另请参阅

- [调试提供程序](debugging-a-provider.md)

