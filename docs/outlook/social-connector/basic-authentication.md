---
title: 基本身份验证
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 89349d1e-365a-442e-9ba3-2df601d9323c
description: 'Outlook Social Connector (.osc) 调用 ISocialProvider:: GetCapabilities 方法来确定用于社交网络的 .osc 提供程序的功能。'
ms.openlocfilehash: 7f716df3ef2e82712374ce3d775cdf66eb07e8b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439924"
---
# <a name="basic-authentication"></a>基本身份验证

Outlook Social Connector (.osc) 调用[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法来确定用于社交网络的 .osc 提供程序的功能。 .osc 使用返回的功能来确定如何支持登录到此社交网络的 Office 用户。 如果返回的**功能**XML 中的**useLogonWebAuth**元素指示 .osc 提供程序支持基本身份验证, 则 .osc 可以进行以下呼叫序列, 以允许用户登录到该社交网络: 
  
1. [ISocialProvider:: Load](isocialprovider-load.md) — .osc 加载提供程序。 
    
2. [ISocialProvider:: Version](isocialprovider-version.md) — .osc 获取一个字符串, 表示 .osc 提供程序的版本号。 
    
3. [ISocialProvider:: SocialNetworkName](isocialprovider-socialnetworkname.md) — .osc 获取一个表示社交网络名称的字符串。 
    
4. [ISocialProvider:: SocialNetworkGuid](isocialprovider-socialnetworkguid.md) — .osc 获取表示社交网络的不可变的 GUID。 
    
5. [ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md) — .osc 获取一个字符串, 该字符串表示提供程序的功能, 并且符合**功能**元素的架构定义。 
    
6. [ISocialProvider:: SocialNetworkIcon](isocialprovider-socialnetworkicon.md) — .osc 获取一个字节数组, 表示社交网络网站的图标。 
    
7. [ISocialProvider:: GetSession](isocialprovider-getsession.md) — .osc 获取[ISocialSession](isocialsessioniunknown.md)接口。 
    
8. [ISocialSession:: Logon](isocialsession-logon.md) —通过使用指定的用户名和密码, .osc 将用户登录到社交网络网站。 
    
9. [ISocialSession:: GetLoggedOnUser](isocialsession-getloggedonuser.md) — .osc 获取一个代表已登录用户的[ISocialProfile](isocialprovideriunknown.md)接口。 
    
10. [ISocialSession:: GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) — .osc 获取一个字符串, 表示社交网络网站的唯一标识符。 网络标识符可以与网络名称等效。 
    
## <a name="see-also"></a>另请参阅

- [XML 的功能](xml-for-capabilities.md)
- [.osc 典型调用序列](osc-typical-calling-sequences.md)

