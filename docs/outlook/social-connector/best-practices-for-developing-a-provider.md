---
title: 开发提供程序的最佳做法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 22e3de8a-c4f2-41a4-a5b1-c5b1bf06f724
description: '在开发 Outlook Social Connector 2013 (.osc) 提供程序时, 应遵循以下做法:'
ms.openlocfilehash: 6a48a56d8065fb9a176ca6527340c99551cdb52a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281235"
---
# <a name="best-practices-for-developing-a-provider"></a><span data-ttu-id="c95b9-103">开发提供程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="c95b9-103">Best practices for developing a provider</span></span>

<span data-ttu-id="c95b9-104">在开发 Outlook Social Connector 2013 (.osc) 提供程序时, 应遵循以下做法:</span><span class="sxs-lookup"><span data-stu-id="c95b9-104">You should adhere to the following practices when you develop an Outlook Social Connector 2013 (OSC) provider:</span></span>
  
- <span data-ttu-id="c95b9-105">出于安全考虑, 通过 Internet 与服务器通信的提供程序应使用 HTTPS (带有安全套接字层 (SSL) 协议的超文本传输协议 (HTTP)) 协议。</span><span class="sxs-lookup"><span data-stu-id="c95b9-105">For security reasons, providers that communicate with servers over the Internet should use the HTTPS (Hypertext Transfer Protocol (HTTP) with Secure Socket Layer (SSL)) protocol.</span></span> <span data-ttu-id="c95b9-106">否则, 在传输过程中可能会发生电子邮件地址、社交网络活动以及其他用户数据可能会被截取或暴露的风险。</span><span class="sxs-lookup"><span data-stu-id="c95b9-106">Otherwise, there is a risk that email addresses, social network activities, and other user data could be intercepted or exposed while in transit.</span></span>
    
- <span data-ttu-id="c95b9-107">如果要为第三方社交网络开发一个 .osc 提供程序, 则提供商必须遵守社交网络的服务条款。</span><span class="sxs-lookup"><span data-stu-id="c95b9-107">If you are developing an OSC provider for a third-party social network, your provider must adhere to the social network's terms of service.</span></span>
    
- <span data-ttu-id="c95b9-108">若要最大限度地减少提供程序下载包的大小, 请使用本机编译器 (如 c + +) 或任何其他可生成 COM 组件的工具生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="c95b9-108">To minimize the size of the provider download package, build the provider by using a native compiler such as C++ or any other tool that can build a COM component.</span></span>
    
- <span data-ttu-id="c95b9-109">在您的提供程序中, 创建一个发送到社交网络的唯一用户代理, 以跟踪提供商向社交网络发出的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c95b9-109">In your provider, create a unique user agent that is sent to the social network to track calls made by the provider to the social network.</span></span>
    
- <span data-ttu-id="c95b9-110">[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法不应依赖于在 Internet 上调用社交网络来获取提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="c95b9-110">The [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method should not rely on calling the social network over the Internet to get the capabilities of the provider.</span></span> <span data-ttu-id="c95b9-111">例如, 用户可以脱机启动 Outlook;如果 .osc 调用**GetCapabilities**且没有网络连接, 则**GetCapabilities**调用将不会返回有效的**功能**XML。</span><span class="sxs-lookup"><span data-stu-id="c95b9-111">For example, users can start Outlook offline; if the OSC calls **GetCapabilities** and there is no network connection, the **GetCapabilities** call will not return valid **capabilities** XML.</span></span> <span data-ttu-id="c95b9-112">最佳做法是在提供程序中将**功能**XML 存储为资源。</span><span class="sxs-lookup"><span data-stu-id="c95b9-112">The best practice is to store **capabilities** XML as a resource in your provider.</span></span> 
    
- <span data-ttu-id="c95b9-113">你的 .osc 提供商可以生成大量呼叫社交网络的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c95b9-113">Your OSC provider can generate a significant volume of calls to a social network.</span></span> <span data-ttu-id="c95b9-114">根据你的社交网络的服务条款, 请考虑将好友缓存到 Outlook 文件夹, 以将来自 .osc 的呼叫数减少到提供商, 然后从你的提供商转到社交网络。</span><span class="sxs-lookup"><span data-stu-id="c95b9-114">Depending on the terms of service for your social network, consider caching friends to an Outlook folder to reduce the number of calls from the OSC to your provider and, in turn, from your provider to the social network.</span></span>
    
- <span data-ttu-id="c95b9-115">Office 2013 在32位和64位版本中均可用。</span><span class="sxs-lookup"><span data-stu-id="c95b9-115">Office 2013 is available in both 32-bit and 64-bit versions.</span></span> <span data-ttu-id="c95b9-116">office 2010 之前的 office 版本仅在32位版本中可用。</span><span class="sxs-lookup"><span data-stu-id="c95b9-116">Versions of Office prior to Office 2010 are available only in a 32-bit version.</span></span> <span data-ttu-id="c95b9-117">在64位 Windows 上安装的 Office 2013 的默认值为32位。</span><span class="sxs-lookup"><span data-stu-id="c95b9-117">The default installation of Office 2013 on 64-bit Windows is 32-bit.</span></span> <span data-ttu-id="c95b9-118">如果您打算支持与64位 Office 2013 一起安装的64位版本的 .osc, 则还必须发布提供程序的64位版本。</span><span class="sxs-lookup"><span data-stu-id="c95b9-118">If you intend to support the 64-bit version of the OSC that is installed with 64-bit Office 2013, you must also release a 64-bit version of your provider.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="c95b9-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c95b9-119">See also</span></span>

- [<span data-ttu-id="c95b9-120">.osc 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="c95b9-120">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)  
- [<span data-ttu-id="c95b9-121">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="c95b9-121">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)  
- [<span data-ttu-id="c95b9-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="c95b9-122">Deploying a Provider</span></span>](deploying-a-provider.md)  
- [<span data-ttu-id="c95b9-123">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="c95b9-123">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

