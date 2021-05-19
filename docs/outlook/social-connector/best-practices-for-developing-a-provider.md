---
title: 开发提供程序的最佳做法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 22e3de8a-c4f2-41a4-a5b1-c5b1bf06f724
description: 在 OSC 提供程序中开发 Outlook Social Connector 2013 (应遵循) 做法：
ms.openlocfilehash: 6a48a56d8065fb9a176ca6527340c99551cdb52a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425916"
---
# <a name="best-practices-for-developing-a-provider"></a><span data-ttu-id="d4aad-103">开发提供程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d4aad-103">Best practices for developing a provider</span></span>

<span data-ttu-id="d4aad-104">在 OSC 提供程序中开发 Outlook Social Connector 2013 (应遵循) 做法：</span><span class="sxs-lookup"><span data-stu-id="d4aad-104">You should adhere to the following practices when you develop an Outlook Social Connector 2013 (OSC) provider:</span></span>
  
- <span data-ttu-id="d4aad-105">出于安全考虑，通过 Internet 与服务器通信的提供程序应该将 HTTPS (超文本传输协议 (HTTP) 与安全套接字层 (SSL) ) 协议一同使用。</span><span class="sxs-lookup"><span data-stu-id="d4aad-105">For security reasons, providers that communicate with servers over the Internet should use the HTTPS (Hypertext Transfer Protocol (HTTP) with Secure Socket Layer (SSL)) protocol.</span></span> <span data-ttu-id="d4aad-106">否则，在传输过程中可能会截获或公开电子邮件地址、社交网络活动和其他用户数据。</span><span class="sxs-lookup"><span data-stu-id="d4aad-106">Otherwise, there is a risk that email addresses, social network activities, and other user data could be intercepted or exposed while in transit.</span></span>
    
- <span data-ttu-id="d4aad-107">如果要为第三方社交网络开发 OSC 提供程序，提供商必须遵守社交网络的服务条款。</span><span class="sxs-lookup"><span data-stu-id="d4aad-107">If you are developing an OSC provider for a third-party social network, your provider must adhere to the social network's terms of service.</span></span>
    
- <span data-ttu-id="d4aad-108">若要最大程度地减小提供程序下载包的大小，可以使用本机编译器（如 C++）或可以生成 COM 组件的其他工具生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="d4aad-108">To minimize the size of the provider download package, build the provider by using a native compiler such as C++ or any other tool that can build a COM component.</span></span>
    
- <span data-ttu-id="d4aad-109">在提供程序中，创建发送到社交网络的唯一用户代理，以跟踪提供商对社交网络的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d4aad-109">In your provider, create a unique user agent that is sent to the social network to track calls made by the provider to the social network.</span></span>
    
- <span data-ttu-id="d4aad-110">[ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法不应依赖通过 Internet 调用社交网络获取提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="d4aad-110">The [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method should not rely on calling the social network over the Internet to get the capabilities of the provider.</span></span> <span data-ttu-id="d4aad-111">例如，用户可以脱机启动Outlook;如果 OSC 调用 **GetCapabilities** 并且没有网络连接，**则 GetCapabilities** 调用不会返回 **有效的功能** XML。</span><span class="sxs-lookup"><span data-stu-id="d4aad-111">For example, users can start Outlook offline; if the OSC calls **GetCapabilities** and there is no network connection, the **GetCapabilities** call will not return valid **capabilities** XML.</span></span> <span data-ttu-id="d4aad-112">最佳做法是，将 **功能** XML 存储为提供程序中的资源。</span><span class="sxs-lookup"><span data-stu-id="d4aad-112">The best practice is to store **capabilities** XML as a resource in your provider.</span></span> 
    
- <span data-ttu-id="d4aad-113">OSC 提供程序可以生成大量对社交网络的调用。</span><span class="sxs-lookup"><span data-stu-id="d4aad-113">Your OSC provider can generate a significant volume of calls to a social network.</span></span> <span data-ttu-id="d4aad-114">根据社交网络的服务条款，请考虑将好友缓存到 Outlook 文件夹，以减少从 OSC 到提供程序的呼叫数，进而减少从提供程序到社交网络的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="d4aad-114">Depending on the terms of service for your social network, consider caching friends to an Outlook folder to reduce the number of calls from the OSC to your provider and, in turn, from your provider to the social network.</span></span>
    
- <span data-ttu-id="d4aad-115">Office 2013 有 32 位和 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="d4aad-115">Office 2013 is available in both 32-bit and 64-bit versions.</span></span> <span data-ttu-id="d4aad-116">2010 Office 2010 Office版本仅在 32 位版本中可用。</span><span class="sxs-lookup"><span data-stu-id="d4aad-116">Versions of Office prior to Office 2010 are available only in a 32-bit version.</span></span> <span data-ttu-id="d4aad-117">64 位Office 2013 的默认安装Windows 32 位。</span><span class="sxs-lookup"><span data-stu-id="d4aad-117">The default installation of Office 2013 on 64-bit Windows is 32-bit.</span></span> <span data-ttu-id="d4aad-118">如果打算支持随 64 位 Office 2013 一起安装的 64 位版本的 OSC，还必须发布 64 位版本的提供程序。</span><span class="sxs-lookup"><span data-stu-id="d4aad-118">If you intend to support the 64-bit version of the OSC that is installed with 64-bit Office 2013, you must also release a 64-bit version of your provider.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="d4aad-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4aad-119">See also</span></span>

- [<span data-ttu-id="d4aad-120">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="d4aad-120">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)  
- [<span data-ttu-id="d4aad-121">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="d4aad-121">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)  
- [<span data-ttu-id="d4aad-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="d4aad-122">Deploying a Provider</span></span>](deploying-a-provider.md)  
- [<span data-ttu-id="d4aad-123">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="d4aad-123">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

