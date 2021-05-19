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
# <a name="forms-based-authentication"></a><span data-ttu-id="2c36a-103">基于表单的身份验证</span><span class="sxs-lookup"><span data-stu-id="2c36a-103">Forms-based authentication</span></span>

<span data-ttu-id="2c36a-104">OUTLOOK Social Connector (OSC) 调用[ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法来确定 OSC 提供程序用于社交网络的功能。</span><span class="sxs-lookup"><span data-stu-id="2c36a-104">The Outlook Social Connector (OSC) calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method to determine the capabilities of the OSC provider for a social network.</span></span> <span data-ttu-id="2c36a-105">OSC 使用返回的功能确定如何支持Office登录到此社交网络的用户。</span><span class="sxs-lookup"><span data-stu-id="2c36a-105">The OSC uses the returned capabilities to determine how to support an Office user who is logging on to this social network.</span></span> 

<span data-ttu-id="2c36a-106">如果返回的功能 **XML** 中的 **useLogonWebAuth** 元素指示 OSC 提供程序支持基于表单的身份验证，则 OSC 可以按以下调用顺序允许用户登录到该社交网络：</span><span class="sxs-lookup"><span data-stu-id="2c36a-106">If the **useLogonWebAuth** element in the returned **capabilities** XML indicates that the OSC provider supports forms-based authentication, the OSC can make the following calling sequence to allow a user to log on to that social network:</span></span> 
  
1. <span data-ttu-id="2c36a-107">[ISocialProvider：：Load](isocialprovider-load.md) &ndash; OSC 加载提供程序。</span><span class="sxs-lookup"><span data-stu-id="2c36a-107">[ISocialProvider::Load](isocialprovider-load.md) &ndash; The OSC loads the provider.</span></span> 
    
2. <span data-ttu-id="2c36a-108">[ISocialProvider：：Version](isocialprovider-version.md) &ndash; OSC 获取一个字符串，该字符串表示此社交网络的提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="2c36a-108">[ISocialProvider::Version](isocialprovider-version.md) &ndash; The OSC gets a string that represents the version number of the provider for this social network.</span></span> 
    
3. <span data-ttu-id="2c36a-109">[ISocialProvider：：SocialNetworkName](isocialprovider-socialnetworkname.md) &ndash; OSC 获取一个代表社交网络名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="2c36a-109">[ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md) &ndash; The OSC gets a string that represents the social network name.</span></span> 
    
4. <span data-ttu-id="2c36a-110">[ISocialProvider：：SocialNetworkGuid](isocialprovider-socialnetworkguid.md) &ndash; OSC 获取表示社交网络的不可变 GUID。</span><span class="sxs-lookup"><span data-stu-id="2c36a-110">[ISocialProvider::SocialNetworkGuid](isocialprovider-socialnetworkguid.md) &ndash; The OSC gets an immutable GUID that represents the social network.</span></span> 
    
5. <span data-ttu-id="2c36a-111">[ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md) &ndash; OSC 获取一个字符串，该字符串表示提供程序的功能，并且符合 **capabilities** 元素的架构定义。</span><span class="sxs-lookup"><span data-stu-id="2c36a-111">[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) &ndash; The OSC gets a string that represents the provider's capabilities and that complies with the schema definition for the **capabilities** element.</span></span> 
    
6. <span data-ttu-id="2c36a-112">[ISocialProvider：：SocialNetworkIcon](isocialprovider-socialnetworkicon.md) &ndash; OSC 获取表示社交网络网站的图标的字节数组。</span><span class="sxs-lookup"><span data-stu-id="2c36a-112">[ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md) &ndash; The OSC gets a byte array that represents the icon for the social network site.</span></span> 
    
7. <span data-ttu-id="2c36a-113">[ISocialProvider：：GetSession](isocialprovider-getsession.md) &ndash; OSC 获取 [ISocialSession](isocialsessioniunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="2c36a-113">[ISocialProvider::GetSession](isocialprovider-getsession.md) &ndash; The OSC gets an [ISocialSession](isocialsessioniunknown.md) interface.</span></span> 
    
8. <span data-ttu-id="2c36a-114">[ISocialSession：：LogonWeb](isocialsession-logonweb.md) &ndash; OSC 通过基于表单的身份验证初始化对社交网络网站的登录。</span><span class="sxs-lookup"><span data-stu-id="2c36a-114">[ISocialSession::LogonWeb](isocialsession-logonweb.md) &ndash; The OSC initializes logging on to the social network site by forms-based authentication.</span></span> <span data-ttu-id="2c36a-115">对于此初始登录调用，OSC **为** connectIn 参数传递 _null。_</span><span class="sxs-lookup"><span data-stu-id="2c36a-115">For this initial logon call, the OSC passes **null** for the  _connectIn_ parameter.</span></span> 
    
9. <span data-ttu-id="2c36a-116">[ISocialSession：：GetLogonUrl](isocialsession-getlogonurl.md) &ndash; OSC 获取在 Web 身份验证期间向用户显示基于浏览器的表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="2c36a-116">[ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md) &ndash; The OSC gets the URL to display a browser-based form to the user during web authentication.</span></span> 
    
10. <span data-ttu-id="2c36a-117">[ISocialSession：：LogonWeb](isocialsession-logonweb.md) &ndash; OSC 使用基于表单的身份验证完成对社交网络网站的登录。</span><span class="sxs-lookup"><span data-stu-id="2c36a-117">[ISocialSession::LogonWeb](isocialsession-logonweb.md) &ndash; The OSC completes the logon to the social network site by using forms-based authentication.</span></span> <span data-ttu-id="2c36a-118">OSC 再次调用此方法，将登录表单的 URL 传递给  _connectIn_ 参数中的提供程序。</span><span class="sxs-lookup"><span data-stu-id="2c36a-118">The OSC calls this method a second time, passing the URL of the logon form to the provider in the  _connectIn_ parameter.</span></span> 
    
11. <span data-ttu-id="2c36a-119">[ISocialSession：：GetLoggedOnUser](isocialsession-getloggedonuser.md) &ndash; OSC 获取表示已登录用户的 [ISocialProfile](isocialprovideriunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="2c36a-119">[ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) &ndash; The OSC gets an [ISocialProfile](isocialprovideriunknown.md) interface that represents the logged-on user.</span></span> 
    
12. <span data-ttu-id="2c36a-120">[ISocialSession：：GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) &ndash; OSC 获取表示社交网络网站的唯一标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="2c36a-120">[ISocialSession::GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) &ndash; The OSC gets a string that represents a unique identifier for a social network site.</span></span> <span data-ttu-id="2c36a-121">网络标识符可以等同于网络名称。</span><span class="sxs-lookup"><span data-stu-id="2c36a-121">The network identifier can be equivalent to the network name.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="2c36a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c36a-122">See also</span></span>

- [<span data-ttu-id="2c36a-123">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="2c36a-123">XML for Capabilities</span></span>](xml-for-capabilities.md)
- [<span data-ttu-id="2c36a-124">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="2c36a-124">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)

