---
title: 基于表单的身份验证
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 282b2377-45ba-4f0c-a7d9-830fa3505c93
description: 'Outlook Social Connector (.osc) 调用 ISocialProvider:: GetCapabilities 方法来确定用于社交网络的 .osc 提供程序的功能。'
ms.openlocfilehash: 420f19a8d7632f2ab9b093eb929ffe879f8a2fc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435528"
---
# <a name="forms-based-authentication"></a>基于表单的身份验证

Outlook Social Connector (.osc) 调用[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法来确定用于社交网络的 .osc 提供程序的功能。 .osc 使用返回的功能来确定如何支持登录到此社交网络的 Office 用户。 

如果返回的**功能**XML 中的**useLogonWebAuth**元素指示 .osc 提供程序支持基于表单的身份验证, 则 .osc 可以进行以下呼叫序列, 以允许用户登录到该社交网络: 
  
1. [ISocialProvider:: Load](isocialprovider-load.md)&ndash; .osc 将加载提供程序。 
    
2. [ISocialProvider:: Version](isocialprovider-version.md)&ndash; .osc 获取一个字符串, 表示此社交网络提供程序的版本号。 
    
3. [ISocialProvider:: SocialNetworkName](isocialprovider-socialnetworkname.md)&ndash; .osc 获取一个表示社交网络名称的字符串。 
    
4. [ISocialProvider:: SocialNetworkGuid](isocialprovider-socialnetworkguid.md)&ndash; .osc 获取表示社交网络的不可变的 GUID。 
    
5. [ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)&ndash; .osc 获取一个字符串, 该字符串表示提供程序的功能, 并且符合**功能**元素的架构定义。 
    
6. [ISocialProvider:: SocialNetworkIcon](isocialprovider-socialnetworkicon.md)&ndash; .osc 获取一个字节数组, 表示社交网络网站的图标。 
    
7. [ISocialProvider:: GetSession](isocialprovider-getsession.md)&ndash; .osc 获取一个[ISocialSession](isocialsessioniunknown.md)接口。 
    
8. [ISocialSession:: LogonWeb](isocialsession-logonweb.md)&ndash; .osc 根据基于表单的身份验证对社交网络网站进行日志记录初始化。 对于此初始登录调用, .osc 传递的_connectIn_参数为**null** 。 
    
9. [ISocialSession:: GetLogonUrl](isocialsession-getlogonurl.md)&ndash; .osc 获取在 web 身份验证过程中向用户显示基于浏览器的表单的 URL。 
    
10. [ISocialSession:: LogonWeb](isocialsession-logonweb.md)&ndash;通过使用基于表单的身份验证, .osc 完成登录到社交网络网站。 .osc 在第二次调用此方法时, 将登录表单的 URL 传递给_connectIn_参数中的提供程序。 
    
11. [ISocialSession:: GetLoggedOnUser](isocialsession-getloggedonuser.md)&ndash; .osc 获取一个[ISocialProfile](isocialprovideriunknown.md)接口, 该接口代表已登录的用户。 
    
12. [ISocialSession:: GetNetworkIdentifier](isocialsession-getnetworkidentifier.md)&ndash; .osc 获取一个字符串, 表示社交网络网站的唯一标识符。 网络标识符可以与网络名称等效。 
    
## <a name="see-also"></a>另请参阅

- [XML 的功能](xml-for-capabilities.md)
- [.osc 典型调用序列](osc-typical-calling-sequences.md)

