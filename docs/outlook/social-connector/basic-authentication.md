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
# <a name="basic-authentication"></a><span data-ttu-id="055e8-103">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="055e8-103">Basic authentication</span></span>

<span data-ttu-id="055e8-104">Outlook Social Connector (.osc) 调用[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法来确定用于社交网络的 .osc 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="055e8-104">The Outlook Social Connector (OSC) calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method to determine the capabilities of the OSC provider for a social network.</span></span> <span data-ttu-id="055e8-105">.osc 使用返回的功能来确定如何支持登录到此社交网络的 Office 用户。</span><span class="sxs-lookup"><span data-stu-id="055e8-105">The OSC uses the returned capabilities to determine how to support an Office user who is logging on to this social network.</span></span> <span data-ttu-id="055e8-106">如果返回的**功能**XML 中的**useLogonWebAuth**元素指示 .osc 提供程序支持基本身份验证, 则 .osc 可以进行以下呼叫序列, 以允许用户登录到该社交网络:</span><span class="sxs-lookup"><span data-stu-id="055e8-106">If the **useLogonWebAuth** element in the returned **capabilities** XML indicates that the OSC provider supports basic authentication, the OSC can make the following calling sequence to allow a user to log on to that social network:</span></span> 
  
1. <span data-ttu-id="055e8-107">[ISocialProvider:: Load](isocialprovider-load.md) — .osc 加载提供程序。</span><span class="sxs-lookup"><span data-stu-id="055e8-107">[ISocialProvider::Load](isocialprovider-load.md) —The OSC loads the provider.</span></span> 
    
2. <span data-ttu-id="055e8-108">[ISocialProvider:: Version](isocialprovider-version.md) — .osc 获取一个字符串, 表示 .osc 提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="055e8-108">[ISocialProvider::Version](isocialprovider-version.md) —The OSC gets a string that represents the version number of the OSC provider.</span></span> 
    
3. <span data-ttu-id="055e8-109">[ISocialProvider:: SocialNetworkName](isocialprovider-socialnetworkname.md) — .osc 获取一个表示社交网络名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="055e8-109">[ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md) —The OSC gets a string that represents the social network name.</span></span> 
    
4. <span data-ttu-id="055e8-110">[ISocialProvider:: SocialNetworkGuid](isocialprovider-socialnetworkguid.md) — .osc 获取表示社交网络的不可变的 GUID。</span><span class="sxs-lookup"><span data-stu-id="055e8-110">[ISocialProvider::SocialNetworkGuid](isocialprovider-socialnetworkguid.md) —The OSC gets an immutable GUID that represents the social network.</span></span> 
    
5. <span data-ttu-id="055e8-111">[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md) — .osc 获取一个字符串, 该字符串表示提供程序的功能, 并且符合**功能**元素的架构定义。</span><span class="sxs-lookup"><span data-stu-id="055e8-111">[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) —The OSC gets a string that represents the provider's capabilities and that complies with the schema definition for the **capabilities** element.</span></span> 
    
6. <span data-ttu-id="055e8-112">[ISocialProvider:: SocialNetworkIcon](isocialprovider-socialnetworkicon.md) — .osc 获取一个字节数组, 表示社交网络网站的图标。</span><span class="sxs-lookup"><span data-stu-id="055e8-112">[ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md) —The OSC gets a byte array that represents the icon for the social network site.</span></span> 
    
7. <span data-ttu-id="055e8-113">[ISocialProvider:: GetSession](isocialprovider-getsession.md) — .osc 获取[ISocialSession](isocialsessioniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="055e8-113">[ISocialProvider::GetSession](isocialprovider-getsession.md) —The OSC gets an [ISocialSession](isocialsessioniunknown.md) interface.</span></span> 
    
8. <span data-ttu-id="055e8-114">[ISocialSession:: Logon](isocialsession-logon.md) —通过使用指定的用户名和密码, .osc 将用户登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="055e8-114">[ISocialSession::Logon](isocialsession-logon.md) —The OSC logs the user on to the social network site by using the specified user name and password.</span></span> 
    
9. <span data-ttu-id="055e8-115">[ISocialSession:: GetLoggedOnUser](isocialsession-getloggedonuser.md) — .osc 获取一个代表已登录用户的[ISocialProfile](isocialprovideriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="055e8-115">[ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) —The OSC gets an [ISocialProfile](isocialprovideriunknown.md) interface that represents the logged-on user.</span></span> 
    
10. <span data-ttu-id="055e8-116">[ISocialSession:: GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) — .osc 获取一个字符串, 表示社交网络网站的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="055e8-116">[ISocialSession::GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) —The OSC gets a string that represents a unique identifier for a social network site.</span></span> <span data-ttu-id="055e8-117">网络标识符可以与网络名称等效。</span><span class="sxs-lookup"><span data-stu-id="055e8-117">The network identifier can be equivalent to the network name.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="055e8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="055e8-118">See also</span></span>

- [<span data-ttu-id="055e8-119">XML 的功能</span><span class="sxs-lookup"><span data-stu-id="055e8-119">XML for Capabilities</span></span>](xml-for-capabilities.md)
- [<span data-ttu-id="055e8-120">.osc 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="055e8-120">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)

