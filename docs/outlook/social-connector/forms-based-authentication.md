---
title: 基于表单的身份验证
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 282b2377-45ba-4f0c-a7d9-830fa3505c93
description: osC Outlook Social Connector (OSC) 调用 ISocialProvider：：GetCapabilities 方法来确定 OSC 提供程序用于社交网络的功能。
ms.openlocfilehash: 420f19a8d7632f2ab9b093eb929ffe879f8a2fc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435528"
---
# <a name="forms-based-authentication"></a>基于表单的身份验证

OUTLOOK Social Connector (OSC) 调用[ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法来确定 OSC 提供程序用于社交网络的功能。 OSC 使用返回的功能确定如何支持Office登录到此社交网络的用户。 

如果返回的功能 **XML** 中的 **useLogonWebAuth** 元素指示 OSC 提供程序支持基于表单的身份验证，则 OSC 可以按以下调用顺序允许用户登录到该社交网络： 
  
1. [ISocialProvider：：Load](isocialprovider-load.md) &ndash; OSC 加载提供程序。 
    
2. [ISocialProvider：：Version](isocialprovider-version.md) &ndash; OSC 获取一个字符串，该字符串表示此社交网络的提供程序的版本号。 
    
3. [ISocialProvider：：SocialNetworkName](isocialprovider-socialnetworkname.md) &ndash; OSC 获取一个代表社交网络名称的字符串。 
    
4. [ISocialProvider：：SocialNetworkGuid](isocialprovider-socialnetworkguid.md) &ndash; OSC 获取表示社交网络的不可变 GUID。 
    
5. [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md) &ndash; OSC 获取一个字符串，该字符串表示提供程序的功能，并且符合 **capabilities** 元素的架构定义。 
    
6. [ISocialProvider：：SocialNetworkIcon](isocialprovider-socialnetworkicon.md) &ndash; OSC 获取表示社交网络网站的图标的字节数组。 
    
7. [ISocialProvider：：GetSession](isocialprovider-getsession.md) &ndash; OSC 获取 [ISocialSession](isocialsessioniunknown.md) 接口。 
    
8. [ISocialSession：：LogonWeb](isocialsession-logonweb.md) &ndash; OSC 通过基于表单的身份验证初始化对社交网络网站的登录。 对于此初始登录调用，OSC **为** connectIn 参数传递 _null。_ 
    
9. [ISocialSession：：GetLogonUrl](isocialsession-getlogonurl.md) &ndash; OSC 获取在 Web 身份验证期间向用户显示基于浏览器的表单的 URL。 
    
10. [ISocialSession：：LogonWeb](isocialsession-logonweb.md) &ndash; OSC 使用基于表单的身份验证完成对社交网络网站的登录。 OSC 再次调用此方法，将登录表单的 URL 传递给  _connectIn_ 参数中的提供程序。 
    
11. [ISocialSession：：GetLoggedOnUser](isocialsession-getloggedonuser.md) &ndash; OSC 获取表示已登录用户的 [ISocialProfile](isocialprovideriunknown.md) 接口。 
    
12. [ISocialSession：：GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) &ndash; OSC 获取表示社交网络网站的唯一标识符的字符串。 网络标识符可以等同于网络名称。 
    
## <a name="see-also"></a>另请参阅

- [功能的 XML](xml-for-capabilities.md)
- [OSC 典型调用序列](osc-typical-calling-sequences.md)

