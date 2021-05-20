---
title: 开发具有 OSC XML 架构的提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0872b1b9-c21f-4bba-8cf1-4b010d8d7fb6
description: Outlook Social Connector (OSC) 提供程序 XML 架构定义大量信息的格式，这些信息通过网络的 OSC 提供程序从社交网络传递到 OSC。
ms.openlocfilehash: 2346e23beb2de1664ec90263a8f5db5d46c54e6f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539253"
---
# <a name="developing-a-provider-with-the-osc-xml-schema"></a>开发具有 OSC XML 架构的提供程序

Outlook Social Connector (OSC) 提供程序 XML 架构定义大量信息的格式，这些信息通过网络的 OSC 提供程序从社交网络传递到 OSC。 XML 架构允许 OSC 提供程序使用三个主要元素、功能、好友和 **activityFeed** 及其子元素指定社交网络上提供程序、好友和活动源项的功能。  OSC 提供程序在 OSC 提供程序扩展性中实现接口及其方法，返回 XML 字符串作为符合 OSC 提供程序 XML 架构的输出参数。 OSC 调用这些方法以获取它可以理解的信息，如 XML 架构所定义。
  
> [!NOTE]
> OSC 提供程序扩展性支持调试提供程序，将注册表项的值 `DebugProviders` 设置为  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector` 1。 打开提供程序调试时，OSC 将对照在 **xmlns** XML 属性中指定的 OSC XML 架构版本验证提供程序 XML。 对于 OSC 1.1 和自 Outlook Social Connector 2013 以来的 OSC 版本，如下所示指定 **xmlns** 属性：`xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`
  
## <a name="in-this-section"></a>本节内容

- [同步好友](synchronizing-friends-and-activities.md)和活动 ：介绍 OSC 提供程序在社交网络上同步好友、非好友和活动的各种方式。 
    
- [OSC 提供程序 XML 示例](osc-provider-xml-examples.md)：包括 XML 示例，这些示例显示如何使用 OSC XML 架构指定社交网络上的 OSC 提供程序、好友和活动源项的功能。
    
- 功能的 [XML](xml-for-capabilities.md)：介绍了 OSC 用于从 OSC 提供程序获取功能信息（以 **功能** XML 表示）的 - [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法。 本节还介绍 OSC 提供程序 XML 架构中的 XML 元素，这些元素允许 OSC 提供程序指定其功能，包括它如何对用户进行身份验证以及同步好友和活动。 
    
- [适用于好友的 XML：](xml-for-friends.md)提供 OSC 用于从 OSC 提供程序获取好友信息的 API（以 **好友** XML 表示）的示例。 本节还介绍好友 XML **中的** 元素。 
    
- [活动的 XML：](xml-for-activities.md)提供 OSC 用于从 OSC 提供程序获取活动信息（以 **activityFeed** XML 表示）的 API 的示例。 本节还介绍 OSC 提供程序 XML 架构中的 XML 元素，这些元素允许 OSC 提供程序指定活动源。 活动源包括源自活动源项的网络、每个活动源项目的详细信息 (如活动) 的所有者、类型和发布日期，以及用于显示活动的模板。 
    
## <a name="reference"></a>参考

- [OutlookSocial Connector Provider Reference](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关章节

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [OSC 示例模板](osc-sample-templates.md)
  
- [OSC 典型调用序列](osc-typical-calling-sequences.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  
- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a>另请参阅

- [调试提供程序](debugging-a-provider.md)

