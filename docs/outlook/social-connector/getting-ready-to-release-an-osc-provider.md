---
title: 准备发布一个 .osc 提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a7d28349-3121-49ae-ad28-043789e2d205
description: 本节建议您在发布 Outlook Social Connector (.osc) 提供程序之前可以执行的测试。
ms.openlocfilehash: 8a36b13f8adc42a1834481d3a5942f0350c43cc3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327151"
---
# <a name="getting-ready-to-release-an-osc-provider"></a>准备发布一个 .osc 提供程序

本节建议您在发布 Outlook Social Connector (.osc) 提供程序之前可以执行的测试。 您可以开始参考本节中的主题, 并在开发和测试阶段中执行这些测试中的部分测试, 但您在释放这些测试时应完成这些测试。 

这些测试将根据您为 .osc 提供程序指定的功能验证您的 .osc 提供程序接口实现的基本功能。 此外, 尽管 .osc 是由多个 Office 客户端应用程序共享的功能, 但这些测试使用 Outlook 作为客户端来测试基本功能。 您应确定特定于您的提供程序的功能是否需要其他测试。
  
## <a name="in-this-section"></a>本节内容

- [测试部署](testing-deployment.md): 介绍在安装和卸载 .osc 提供程序方面应测试的方案。
    
- [测试功能、身份验证和配置](testing-capabilities-authentication-and-configuration.md): 介绍了用于获取功能的测试, 以及有关配置帐户和对社交网络的用户进行身份验证的方案。
    
- [测试关注和停止关注的人员](testing-following-and-stop-following-persons.md): 介绍用于测试 .osc 提供程序将人员添加为朋友的能力或从社交网络中删除好友的方案。 
    
- [测试朋友](testing-friends.md): 介绍了测试和方案, 以验证 .osc 提供程序是否根据提供程序所支持的同步模式, 适当地返回朋友和非好友的数据 (如果适用)。
    
- [测试活动](testing-activities.md): 介绍了测试和方案, 以验证 .osc 提供程序是否根据提供程序支持的同步模式, 适当地返回朋友和非朋友的活动 (如果适用)。
    
## <a name="reference"></a>参考

- [Outlook Social Connector 提供程序参考](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关章节

- [.osc 示例模板](osc-sample-templates.md)
  
- [.osc 典型调用序列](osc-typical-calling-sequences.md)
  
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  

