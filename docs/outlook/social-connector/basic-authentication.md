---
title: 基本身份验证
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 89349d1e-365a-442e-9ba3-2df601d9323c
description: Outlook Social Connector (OSC) 调用 ISocialProvider::GetCapabilities 方法来确定社交网络 OSC 提供程序的功能。
ms.openlocfilehash: 8287133445a4e8fa928f6b7724ab41ca9b58baf9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779224"
---
# <a name="basic-authentication"></a>基本身份验证

Outlook Social Connector (OSC) 调用[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法来确定社交网络 OSC 提供程序的功能。 OSC 使用返回的功能来确定如何支持的 Office 用户登录到此社交网络。 如果返回**功能**XML 中的**useLogonWebAuth**元素表示 OSC 提供程序支持基本身份验证，则 OSC 可以进行要允许用户登录到社交网络上的以下调用序列： 
  
1. [ISocialProvider::Load](isocialprovider-load.md) — OSC 加载提供程序。 
    
2. [ISocialProvider::Version](isocialprovider-version.md) — OSC 获取一个字符串，表示 OSC 提供程序的版本号。 
    
3. [ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md) — OSC 获取表示社交网络名称的字符串。 
    
4. [ISocialProvider::SocialNetworkGuid](isocialprovider-socialnetworkguid.md) — OSC 获取变 GUID 值，该值代表社交网络。 
    
5. [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) — OSC 获取一个字符串，表示提供程序的功能和的符合**capabilities**元素的架构定义。 
    
6. [ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md) — OSC 获取一个值，该值代表社交网络站点的图标的字节数组。 
    
7. [ISocialProvider::GetSession](isocialprovider-getsession.md) — OSC 获取[ISocialSession](isocialsessioniunknown.md)接口。 
    
8. [ISocialSession::Logon](isocialsession-logon.md) — OSC 日志用户登录到社交网络站点使用指定的用户名和密码。 
    
9. [ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) — OSC 获取代表登录用户的[ISocialProfile](isocialprovideriunknown.md)接口。 
    
10. [ISocialSession::GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) — OSC 获取一个字符串，表示社交网络站点的唯一标识符。 网络标识符可以是等价于网络名称。 
    
## <a name="see-also"></a>另请参阅

- [功能 XML](xml-for-capabilities.md)
- [OSC 典型调用序列 （英文)](osc-typical-calling-sequences.md)

