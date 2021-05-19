---
title: 准备发布 OSC 提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a7d28349-3121-49ae-ad28-043789e2d205
description: 本节建议在 OSC Outlook 发布您的 Outlook 连接器 (测试) 测试。
ms.openlocfilehash: 8a36b13f8adc42a1834481d3a5942f0350c43cc3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414660"
---
# <a name="getting-ready-to-release-an-osc-provider"></a>准备发布 OSC 提供程序

本节建议在 OSC Outlook 发布您的 Outlook 连接器 (测试) 测试。 你可以开始引用本节中的主题，在开发和测试阶段执行其中一些测试，但应在发布时完成这些测试。 

这些测试验证 OSC 提供程序接口实现的基本功能与为 OSC 提供程序指定的功能有关。 此外，即使 OSC 是由多个 Office 应用程序共享的功能，这些测试Outlook客户端来测试基本功能。 应确定特定于提供程序的功能是否需要其他测试。
  
## <a name="in-this-section"></a>本节内容

- [测试部署](testing-deployment.md)：介绍应测试的与安装和卸载 OSC 提供程序有关的方案。
    
- [测试功能、身份验证和配置](testing-capabilities-authentication-and-configuration.md)：介绍用于获取功能和有关为社交网络配置帐户和验证用户的方案的测试。
    
- [Testing Following and Stop-Following Person](testing-following-and-stop-following-persons.md)： Describes scenarios to test the OSC provider's ability to add a person as a friend， or to remove a friend from the social network. 
    
- [测试好友](testing-friends.md)：介绍用于验证 OSC 提供程序是否适当返回好友和非好友的数据的测试和方案（如果适用，具体取决于提供程序支持的同步模式）。
    
- [测试活动](testing-activities.md)：描述用于验证 OSC 提供程序是否适当返回好友和非好友的活动（如果适用，具体取决于提供程序支持的同步模式）的测试和方案。
    
## <a name="reference"></a>参考

- [OutlookSocial Connector Provider Reference](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关章节

- [OSC 示例模板](osc-sample-templates.md)
  
- [OSC 典型调用序列](osc-typical-calling-sequences.md)
  
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  

