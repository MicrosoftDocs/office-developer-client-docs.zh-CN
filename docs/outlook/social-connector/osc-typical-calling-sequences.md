---
title: OSC 典型调用序列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f61960f7-e018-4d2e-8e32-426ed46d9064
description: 本节介绍 OSC Outlook扩展 (实现) OSC 提供程序扩展性接口中的成员的典型调用序列。
ms.openlocfilehash: f7829b710d6840ccd1fa0f990d6e03b2eb879431
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413610"
---
# <a name="osc-typical-calling-sequences"></a>OSC 典型调用序列

本节介绍 OSC Outlook扩展 (实现) OSC 提供程序扩展性接口中的成员的典型调用序列。 典型的调用序列说明了 OSC 如何使用以及何时使用此类接口和方法，以便你可以更好地确定如何在提供程序扩展性接口上实现给定成员。 实际调用顺序可能因 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md) 方法返回的功能而异。 功能示例包括： 
  
- 提供程序支持从社交网络获取、缓存或动态查找好友和活动。
    
- OSC 应为用户登录显示的用户界面。
    
- 身份验证类型 (，例如，基于表单) OSC 应该使用的身份验证类型。
    
## <a name="in-this-section"></a>本节内容

- [基本身份验证](basic-authentication.md)：描述 OSC 的典型调用序列，以支持Office登录社交网络的用户（如果 OSC 提供程序支持基本身份验证）。
    
- [基于表单的身份验证](forms-based-authentication.md)：介绍 OSC 的典型调用序列，以支持登录到社交网络的 Office 用户（如果 OSC 提供程序支持基于表单的身份验证）。
    
- [获取活动](getting-activities.md)：描述 OSC 的典型调用序列，以同步 Office 用户的好友在社交网络中的活动（如果社交网络 OSC 提供程序支持同步活动）。
    
- [获取好友信息](getting-friends-information.md)：介绍 OSC 的典型调用序列，以从社交网络同步 Office 用户的好友列表（如果社交网络 OSC 提供程序支持联系人的缓存同步）。
    
## <a name="reference"></a>参考

- [OutlookSocial Connector Provider Reference](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关章节

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [OSC 示例模板](osc-sample-templates.md)
  
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  
- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a>另请参阅

- [功能的 XML](xml-for-capabilities.md)

