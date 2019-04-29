---
title: OSC 典型调用序列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f61960f7-e018-4d2e-8e32-426ed46d9064
description: 本节介绍了在 .osc 提供商实施的 .osc 提供程序扩展性接口中的 Outlook Social Connector (.osc) 典型的成员呼叫序列。
ms.openlocfilehash: f7829b710d6840ccd1fa0f990d6e03b2eb879431
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413610"
---
# <a name="osc-typical-calling-sequences"></a>OSC 典型调用序列

本节介绍了在 .osc 提供商实施的 .osc 提供程序扩展性接口中的 Outlook Social Connector (.osc) 典型的成员呼叫序列。 典型的呼叫序列说明了 .osc 如何以及何时使用这些接口和方法, 以便更好地确定如何在提供程序扩展性接口上实现给定成员。 实际调用顺序可能因[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法返回的功能而异。 这些功能的示例包括: 
  
- 从社交网络获取、缓存或动态查找好友和活动的提供程序支持。
    
- 供用户登录时, .osc 应显示的用户界面。
    
- .osc 应使用的身份验证类型 (例如, 基于表单的身份验证)。
    
## <a name="in-this-section"></a>本节内容

- [基本身份验证](basic-authentication.md): 介绍在 .osc 提供商支持基本身份验证的情况下, 要支持登录到社交网络的 Office 用户, 您的 .osc 的典型呼叫序列。
    
- [基于表单的身份验证](forms-based-authentication.md): 介绍在 .osc 提供程序支持基于表单的身份验证的情况下, 用于支持登录到社交网络的 Office 用户的 .osc 的典型呼叫顺序。
    
- [获取活动](getting-activities.md): 介绍在社交网络 .osc 提供商支持活动同步的情况下, 从社交网络同步 Office 用户好友活动的 .osc 的典型呼叫顺序。
    
- [获取朋友信息](getting-friends-information.md): 如果社交网络 .osc 提供商支持对联系人的缓存同步, 则介绍了 .osc 的典型呼叫顺序, 以便从社交网络同步 Office 用户的好友列表。
    
## <a name="reference"></a>参考

- [Outlook Social Connector 提供程序参考](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关部分

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [.osc 示例模板](osc-sample-templates.md)
  
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  
- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a>另请参阅

- [XML 的功能](xml-for-capabilities.md)

