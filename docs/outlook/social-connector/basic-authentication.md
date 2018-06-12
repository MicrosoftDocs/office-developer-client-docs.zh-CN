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
# <a name="basic-authentication"></a><span data-ttu-id="e660d-103">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="e660d-103">Basic authentication</span></span>

<span data-ttu-id="e660d-104">Outlook Social Connector (OSC) 调用[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法来确定社交网络 OSC 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="e660d-104">The Outlook Social Connector (OSC) calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method to determine the capabilities of the OSC provider for a social network.</span></span> <span data-ttu-id="e660d-105">OSC 使用返回的功能来确定如何支持的 Office 用户登录到此社交网络。</span><span class="sxs-lookup"><span data-stu-id="e660d-105">The OSC uses the returned capabilities to determine how to support an Office user who is logging on to this social network.</span></span> <span data-ttu-id="e660d-106">如果返回**功能**XML 中的**useLogonWebAuth**元素表示 OSC 提供程序支持基本身份验证，则 OSC 可以进行要允许用户登录到社交网络上的以下调用序列：</span><span class="sxs-lookup"><span data-stu-id="e660d-106">If the **useLogonWebAuth** element in the returned **capabilities** XML indicates that the OSC provider supports basic authentication, the OSC can make the following calling sequence to allow a user to log on to that social network:</span></span> 
  
1. <span data-ttu-id="e660d-107">[ISocialProvider::Load](isocialprovider-load.md) — OSC 加载提供程序。</span><span class="sxs-lookup"><span data-stu-id="e660d-107">[ISocialProvider::Load](isocialprovider-load.md) —The OSC loads the provider.</span></span> 
    
2. <span data-ttu-id="e660d-108">[ISocialProvider::Version](isocialprovider-version.md) — OSC 获取一个字符串，表示 OSC 提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="e660d-108">[ISocialProvider::Version](isocialprovider-version.md) —The OSC gets a string that represents the version number of the OSC provider.</span></span> 
    
3. <span data-ttu-id="e660d-109">[ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md) — OSC 获取表示社交网络名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="e660d-109">[ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md) —The OSC gets a string that represents the social network name.</span></span> 
    
4. <span data-ttu-id="e660d-110">[ISocialProvider::SocialNetworkGuid](isocialprovider-socialnetworkguid.md) — OSC 获取变 GUID 值，该值代表社交网络。</span><span class="sxs-lookup"><span data-stu-id="e660d-110">[ISocialProvider::SocialNetworkGuid](isocialprovider-socialnetworkguid.md) —The OSC gets an immutable GUID that represents the social network.</span></span> 
    
5. <span data-ttu-id="e660d-111">[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) — OSC 获取一个字符串，表示提供程序的功能和的符合**capabilities**元素的架构定义。</span><span class="sxs-lookup"><span data-stu-id="e660d-111">[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) —The OSC gets a string that represents the provider's capabilities and that complies with the schema definition for the **capabilities** element.</span></span> 
    
6. <span data-ttu-id="e660d-112">[ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md) — OSC 获取一个值，该值代表社交网络站点的图标的字节数组。</span><span class="sxs-lookup"><span data-stu-id="e660d-112">[ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md) —The OSC gets a byte array that represents the icon for the social network site.</span></span> 
    
7. <span data-ttu-id="e660d-113">[ISocialProvider::GetSession](isocialprovider-getsession.md) — OSC 获取[ISocialSession](isocialsessioniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e660d-113">[ISocialProvider::GetSession](isocialprovider-getsession.md) —The OSC gets an [ISocialSession](isocialsessioniunknown.md) interface.</span></span> 
    
8. <span data-ttu-id="e660d-114">[ISocialSession::Logon](isocialsession-logon.md) — OSC 日志用户登录到社交网络站点使用指定的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e660d-114">[ISocialSession::Logon](isocialsession-logon.md) —The OSC logs the user on to the social network site by using the specified user name and password.</span></span> 
    
9. <span data-ttu-id="e660d-115">[ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) — OSC 获取代表登录用户的[ISocialProfile](isocialprovideriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e660d-115">[ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) —The OSC gets an [ISocialProfile](isocialprovideriunknown.md) interface that represents the logged-on user.</span></span> 
    
10. <span data-ttu-id="e660d-116">[ISocialSession::GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) — OSC 获取一个字符串，表示社交网络站点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e660d-116">[ISocialSession::GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) —The OSC gets a string that represents a unique identifier for a social network site.</span></span> <span data-ttu-id="e660d-117">网络标识符可以是等价于网络名称。</span><span class="sxs-lookup"><span data-stu-id="e660d-117">The network identifier can be equivalent to the network name.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="e660d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e660d-118">See also</span></span>

- [<span data-ttu-id="e660d-119">功能 XML</span><span class="sxs-lookup"><span data-stu-id="e660d-119">XML for Capabilities</span></span>](xml-for-capabilities.md)
- [<span data-ttu-id="e660d-120">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="e660d-120">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)

