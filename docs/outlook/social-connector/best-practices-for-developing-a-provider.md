---
title: 开发提供程序的最佳做法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 22e3de8a-c4f2-41a4-a5b1-c5b1bf06f724
description: 开发 Outlook Social Connector 2013 (OSC) 提供程序时应遵循以下做法：
ms.openlocfilehash: a6ee9d54f33bbc855d178aba844a8f65ec92f964
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779196"
---
# <a name="best-practices-for-developing-a-provider"></a><span data-ttu-id="77f3e-103">开发提供程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="77f3e-103">Best practices for developing a provider</span></span>

<span data-ttu-id="77f3e-104">开发 Outlook Social Connector 2013 (OSC) 提供程序时应遵循以下做法：</span><span class="sxs-lookup"><span data-stu-id="77f3e-104">You should adhere to the following practices when you develop an Outlook Social Connector 2013 (OSC) provider:</span></span>
  
- <span data-ttu-id="77f3e-105">出于安全考虑，通过 Internet 与服务器进行通信的提供程序应使用 HTTPS (超文本传输协议 (HTTP) 使用安全套接字层 (SSL)) 协议。</span><span class="sxs-lookup"><span data-stu-id="77f3e-105">For security reasons, providers that communicate with servers over the Internet should use the HTTPS (Hypertext Transfer Protocol (HTTP) with Secure Socket Layer (SSL)) protocol.</span></span> <span data-ttu-id="77f3e-106">否则，将风险的电子邮件地址、 社交网络活动和其他用户无法截获或在传输过程中公开数据。</span><span class="sxs-lookup"><span data-stu-id="77f3e-106">Otherwise, there is a risk that email addresses, social network activities, and other user data could be intercepted or exposed while in transit.</span></span>
    
- <span data-ttu-id="77f3e-107">如果要开发 OSC 提供程序的第三方社交网络，您的提供商必须符合到社交网络的术语的服务。</span><span class="sxs-lookup"><span data-stu-id="77f3e-107">If you are developing an OSC provider for a third-party social network, your provider must adhere to the social network's terms of service.</span></span>
    
- <span data-ttu-id="77f3e-108">大程度地减少提供下载程序包的大小，请使用如 c + + 或任何其他可构建 COM 组件的工具本机编译器生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="77f3e-108">To minimize the size of the provider download package, build the provider by using a native compiler such as C++ or any other tool that can build a COM component.</span></span>
    
- <span data-ttu-id="77f3e-109">提供程序，创建唯一的用户代理发送到社交网络跟踪对到社交网络提供程序发出的呼叫。</span><span class="sxs-lookup"><span data-stu-id="77f3e-109">In your provider, create a unique user agent that is sent to the social network to track calls made by the provider to the social network.</span></span>
    
- <span data-ttu-id="77f3e-110">[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法不应依赖于通过 Internet 获取的功能提供程序的调用社交网络。</span><span class="sxs-lookup"><span data-stu-id="77f3e-110">The [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method should not rely on calling the social network over the Internet to get the capabilities of the provider.</span></span> <span data-ttu-id="77f3e-111">例如，用户可以开始 Outlook 脱机;如果没有网络连接 OSC 调用**GetCapabilities** ， **GetCapabilities**呼叫不会返回有效**功能**XML。</span><span class="sxs-lookup"><span data-stu-id="77f3e-111">For example, users can start Outlook offline; if the OSC calls **GetCapabilities** and there is no network connection, the **GetCapabilities** call will not return valid **capabilities** XML.</span></span> <span data-ttu-id="77f3e-112">最佳做法是为您提供程序中的资源存储**功能**XML。</span><span class="sxs-lookup"><span data-stu-id="77f3e-112">The best practice is to store **capabilities** XML as a resource in your provider.</span></span> 
    
- <span data-ttu-id="77f3e-113">OSC 提供程序可以生成大量到社交网络的呼叫。</span><span class="sxs-lookup"><span data-stu-id="77f3e-113">Your OSC provider can generate a significant volume of calls to a social network.</span></span> <span data-ttu-id="77f3e-114">这取决于您的社交网络服务条款，请考虑缓存到 Outlook 文件夹朋友以减少的呼叫数从到您的提供商 OSC 和，依次到社交网络提供商。</span><span class="sxs-lookup"><span data-stu-id="77f3e-114">Depending on the terms of service for your social network, consider caching friends to an Outlook folder to reduce the number of calls from the OSC to your provider and, in turn, from your provider to the social network.</span></span>
    
- <span data-ttu-id="77f3e-115">Office 2013 是 32 位和 64 位版本中提供。</span><span class="sxs-lookup"><span data-stu-id="77f3e-115">Office 2013 is available in both 32-bit and 64-bit versions.</span></span> <span data-ttu-id="77f3e-116">Office 2010 之前版本的是 office 的仅在 32 位版本中可用。</span><span class="sxs-lookup"><span data-stu-id="77f3e-116">Versions of Office prior to Office 2010 are available only in a 32-bit version.</span></span> <span data-ttu-id="77f3e-117">Office 2013 64 位 Windows 上的默认安装 32 位。</span><span class="sxs-lookup"><span data-stu-id="77f3e-117">The default installation of Office 2013 on 64-bit Windows is 32-bit.</span></span> <span data-ttu-id="77f3e-118">如果您想要支持 OSC 随 64 位 Office 2013 安装的 64 位版本，您还必须释放您的提供商的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="77f3e-118">If you intend to support the 64-bit version of the OSC that is installed with 64-bit Office 2013, you must also release a 64-bit version of your provider.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="77f3e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77f3e-119">See also</span></span>

- [<span data-ttu-id="77f3e-120">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="77f3e-120">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)  
- [<span data-ttu-id="77f3e-121">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="77f3e-121">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)  
- [<span data-ttu-id="77f3e-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="77f3e-122">Deploying a Provider</span></span>](deploying-a-provider.md)  
- [<span data-ttu-id="77f3e-123">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="77f3e-123">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

