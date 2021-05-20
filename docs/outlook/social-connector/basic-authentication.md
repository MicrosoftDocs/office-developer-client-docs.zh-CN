---
title: 基本身份验证
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 89349d1e-365a-442e-9ba3-2df601d9323c
description: osC Outlook Social Connector (OSC) 调用 ISocialProvider：：GetCapabilities 方法来确定 OSC 提供程序用于社交网络的功能。
ms.openlocfilehash: 7f716df3ef2e82712374ce3d775cdf66eb07e8b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439924"
---
# <a name="basic-authentication"></a>基本身份验证

OUTLOOK Social Connector (OSC) 调用[ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法来确定 OSC 提供程序用于社交网络的功能。 OSC 使用返回的功能确定如何支持Office登录到此社交网络的用户。 如果返回的功能 **XML** 中的 **useLogonWebAuth** 元素指示 OSC 提供程序支持基本身份验证，则 OSC 可以执行以下调用序列以允许用户登录到该社交网络： 
  
1. [ISocialProvider：：Load](isocialprovider-load.md) — OSC 加载提供程序。 
    
2. [ISocialProvider：：Version](isocialprovider-version.md) — OSC 获取表示 OSC 提供程序的版本号的字符串。 
    
3. [ISocialProvider：：SocialNetworkName](isocialprovider-socialnetworkname.md) — OSC 获取表示社交网络名称的字符串。 
    
4. [ISocialProvider：：SocialNetworkGuid](isocialprovider-socialnetworkguid.md) — OSC 获取表示社交网络的不可变 GUID。 
    
5. [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md) — OSC 获取表示提供程序功能且符合 **capabilities** 元素的架构定义的字符串。 
    
6. [ISocialProvider：：SocialNetworkIcon](isocialprovider-socialnetworkicon.md) — OSC 获取表示社交网络网站的图标的字节数组。 
    
7. [ISocialProvider：：GetSession](isocialprovider-getsession.md) — OSC 获取 [ISocialSession](isocialsessioniunknown.md) 接口。 
    
8. [ISocialSession：：Logon](isocialsession-logon.md) — OSC 使用指定的用户名和密码将用户登录到社交网络网站。 
    
9. [ISocialSession：：GetLoggedOnUser](isocialsession-getloggedonuser.md) — OSC 获取表示已登录用户的 [ISocialProfile](isocialprovideriunknown.md) 接口。 
    
10. [ISocialSession：：GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) — OSC 获取表示社交网络网站的唯一标识符的字符串。 网络标识符可以等同于网络名称。 
    
## <a name="see-also"></a>另请参阅

- [功能的 XML](xml-for-capabilities.md)
- [OSC 典型调用序列](osc-typical-calling-sequences.md)

