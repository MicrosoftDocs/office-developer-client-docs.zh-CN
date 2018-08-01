---
title: 准备发布 OSC 提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a7d28349-3121-49ae-ad28-043789e2d205
description: 本节提供了建议之前您发布您的 Outlook Social Connector (OSC) 提供程序时，可以执行操作的测试。
ms.openlocfilehash: 5caf4144a8daed31d30c9ecbcf9cf21c2300ed8f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779207"
---
# <a name="getting-ready-to-release-an-osc-provider"></a>准备发布 OSC 提供程序

本节提供了建议之前您发布您的 Outlook Social Connector (OSC) 提供程序时，可以执行操作的测试。 您可以启动引用此部分中的主题和执行一些这些测试您的开发和测试阶段，但您应该已经完成这些测试由释放的时间。 

这些测试验证的相对于 OSC 提供程序指定的功能的 OSC 提供程序接口实现的基本功能。 此外，即使 OSC 是由多个 Office 客户端应用程序共享功能，这些测试用作 Outlook 客户端测试的基本功能。 您应该确定是否其他测试所需的特定功能为您提供程序。
  
## <a name="in-this-section"></a>本节内容

- [测试部署](testing-deployment.md)： 介绍了您应测试解决安装和卸载 OSC 提供程序的方案。
    
- [测试功能，Authentication，and 配置](testing-capabilities-authentication-and-configuration.md)： 描述用于获取功能，并配置帐户和验证社交网络的用户设置的方案的测试。
    
- [以下测试和停止关注人员](testing-following-and-stop-following-persons.md)： 介绍了用于测试 OSC 提供程序的功能为朋友，添加一个人或朋友删除社交网络方案。 
    
- [测试朋友](testing-friends.md)： 描述测试和验证 OSC 提供程序适当地返回数据的朋友和非朋友，如果适用，具体取决于提供程序支持的同步模式的方案。
    
- [测试活动](testing-activities.md)： 描述测试和验证 OSC 提供程序适当地返回朋友和非朋友活动，如果适用，具体取决于提供程序支持的同步模式的方案。
    
## <a name="reference"></a>参考

- [Outlook Social Connector 提供程序参考](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关章节

- [OSC 示例模板](osc-sample-templates.md)
  
- [OSC 典型调用序列 （英文)](osc-typical-calling-sequences.md)
  
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  

