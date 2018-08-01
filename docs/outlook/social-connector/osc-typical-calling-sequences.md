---
title: OSC 典型调用序列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f61960f7-e018-4d2e-8e32-426ed46d9064
description: 本节介绍 Outlook Social Connector (OSC) 典型调用序列 OSC 提供程序实现的 OSC 提供程序扩展性接口中的成员。
ms.openlocfilehash: 4a79e27fadb78933f41f26818cfab8b7f4a5aae7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779320"
---
# <a name="osc-typical-calling-sequences"></a>OSC 典型调用序列

本节介绍 Outlook Social Connector (OSC) 典型调用序列 OSC 提供程序实现的 OSC 提供程序扩展性接口中的成员。 典型调用序列说明如何以及何时 OSC 使用此类接口和方法，让您更好地确定如何在提供程序扩展性接口实现给定的成员。 实际的调用序列取决于[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法返回的功能。 功能的示例包括： 
  
- 获取、 缓存，或动态查找朋友和活动从社交网络支持提供程序。
    
- OSC 应显示为用户登录用户界面。
    
- OSC 应使用的身份验证类型 （例如，基于表单的身份验证）。
    
## <a name="in-this-section"></a>本节内容

- [基本身份验证](basic-authentication.md)： 介绍了支持的 Office 用户登录到社交网络中，如果 OSC 提供程序支持基本身份验证 OSC 典型调用序列。
    
- [基于表单的身份验证](forms-based-authentication.md)： 介绍了支持的 Office 用户登录到社交网络中，如果 OSC 提供程序支持基于表单的身份验证 OSC 典型调用序列。
    
- [获取活动](getting-activities.md)： 介绍同步的从社交网络的 Office 用户的好友的活动 OSC 典型调用序列，如果社交网络 OSC 提供程序支持的活动同步。
    
- [获取好友信息](getting-friends-information.md)： 如果社交网络 OSC 提供程序支持的联系人的缓存的同步介绍同步社交网络中，从 Office 用户朋友列表 OSC 典型调用序列。
    
## <a name="reference"></a>参考

- [Outlook Social Connector 提供程序参考](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a>相关章节

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [OSC 示例模板](osc-sample-templates.md)
  
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)
  
- [调试提供程序](debugging-a-provider.md)
  
- [部署提供程序](deploying-a-provider.md)
  
- [开发提供程序的最佳做法](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a>另请参阅

- [功能 XML](xml-for-capabilities.md)

