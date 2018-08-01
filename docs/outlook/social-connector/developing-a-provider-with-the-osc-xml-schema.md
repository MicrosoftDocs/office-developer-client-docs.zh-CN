---
title: 开发具有 OSC XML 架构的提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0872b1b9-c21f-4bba-8cf1-4b010d8d7fb6
description: Outlook Social Connector (OSC) 提供程序的 XML 架构定义大量信息的从社交网络通过传递网络的 OSC 提供程序为 OSC 的格式。
ms.openlocfilehash: 93df682751146b501a316be62641b8cfd47a74a8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779215"
---
# <a name="developing-a-provider-with-the-osc-xml-schema"></a>开发具有 OSC XML 架构的提供程序

Outlook Social Connector (OSC) 提供程序的 XML 架构定义大量信息的从社交网络通过传递网络的 OSC 提供程序为 OSC 的格式。 XML 架构允许 OSC 提供程序指定的提供程序、 朋友和活动源项目的社交网络上使用的三个主元素、**功能**、**朋友**和**activityFeed**和及其子功能元素。 OSC 提供程序实现接口和它们的方法中 OSC 提供程序扩展性，作为遵守 OSC 提供程序的 XML 架构的输出参数返回 XML 字符串。 OSC 调用这些方法来获取它可以了解该 XML 架构定义的信息。
  
> [!NOTE]
> OSC 提供程序扩展性支持调试提供程序通过设置`DebugProviders`的值`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`为 1 的注册表项。 当您打开调试提供程序时，OSC 验证提供程序 XML 针对**xmlns** XML 属性中指定的 OSC XML 架构的版本。 OSC 1.1 和版本的 Outlook Social Connector 2013 相 OSC，指定**xmlns**属性，如下所示：`xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`
  
## <a name="in-this-section"></a>本节内容

- [同步朋友和活动](synchronizing-friends-and-activities.md)： 介绍了朋友、 非朋友和社交网络上的活动，可以同步 OSC 提供程序的各种方法。 
    
- [OSC 提供程序 XML 示例](osc-provider-xml-examples.md)： 包括 XML 示例演示如何指定功能的 OSC 提供程序、 朋友和活动源社交网络上使用 OSC XML 架构的项目。
    
- [功能 XML](xml-for-capabilities.md)： 说明 OSC 使用获取功能信息，表示在**功能**XML 中，从 OSC 提供程序- [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法。 本节还介绍 OSC 提供程序的 XML 架构中的允许 OSC 提供程序指定其功能，包括如何对用户进行身份验证和同步朋友和活动的 XML 元素。 
    
- [XML 朋友](xml-for-friends.md)： 提供 OSC 使用获取朋友的信息，表示在**朋友**XML 中，从 OSC 提供程序的 Api 的示例。 本节还介绍**朋友**XML 中的元素。 
    
- [活动的 XML](xml-for-activities.md)： 提供 OSC 使用获取活动信息，表示在**activityFeed** XML 中，从 OSC 提供程序的 Api 的示例。 本节还介绍允许 OSC 提供程序指定活动源中的 OSC 提供程序的 XML 架构的 XML 元素。 活动源包括的网络其中活动源项目产生，每个活动源项的详细信息 （如所有者，键入，和活动的发布日期），并显示活动的模板。 
    
## <a name="reference"></a>参考

- [Outlook Social Connector 提供程序参考](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关章节

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [OSC 示例模板](osc-sample-templates.md)
  
- [OSC 典型调用序列 （英文)](osc-typical-calling-sequences.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  
- [开发提供程序的最佳做法](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a>另请参阅

- [调试提供程序](debugging-a-provider.md)

