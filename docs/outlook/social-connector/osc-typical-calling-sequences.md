---
title: OSC 典型调用序列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f61960f7-e018-4d2e-8e32-426ed46d9064
description: 本节介绍了在 .osc 提供商实施的 .osc 提供程序扩展性接口中的 Outlook Social Connector (.osc) 典型的成员呼叫序列。
ms.openlocfilehash: f7829b710d6840ccd1fa0f990d6e03b2eb879431
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413610"
---
# <a name="osc-typical-calling-sequences"></a><span data-ttu-id="2b1a9-103">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="2b1a9-103">OSC typical calling sequences</span></span>

<span data-ttu-id="2b1a9-104">本节介绍了在 .osc 提供商实施的 .osc 提供程序扩展性接口中的 Outlook Social Connector (.osc) 典型的成员呼叫序列。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-104">This section describes the Outlook Social Connector (OSC) typical calling sequences of members in the OSC provider extensibility interfaces, which an OSC provider implements.</span></span> <span data-ttu-id="2b1a9-105">典型的呼叫序列说明了 .osc 如何以及何时使用这些接口和方法, 以便更好地确定如何在提供程序扩展性接口上实现给定成员。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-105">The typical calling sequences illustrate how and when the OSC uses such interfaces and methods, to let you better determine how to implement a given member on a provider extensibility interface.</span></span> <span data-ttu-id="2b1a9-106">实际调用顺序可能因[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法返回的功能而异。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-106">The actual calling sequence can vary depending on the capabilities returned by the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method.</span></span> <span data-ttu-id="2b1a9-107">这些功能的示例包括:</span><span class="sxs-lookup"><span data-stu-id="2b1a9-107">Examples of capabilities include the following:</span></span> 
  
- <span data-ttu-id="2b1a9-108">从社交网络获取、缓存或动态查找好友和活动的提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-108">Provider support for getting, caching, or dynamically looking up friends and activities from the social network.</span></span>
    
- <span data-ttu-id="2b1a9-109">供用户登录时, .osc 应显示的用户界面。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-109">The user interface that the OSC should display for user logon.</span></span>
    
- <span data-ttu-id="2b1a9-110">.osc 应使用的身份验证类型 (例如, 基于表单的身份验证)。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-110">The authentication type (for example, forms-based authentication) that the OSC should use.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="2b1a9-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="2b1a9-111">In this section</span></span>

- <span data-ttu-id="2b1a9-112">[基本身份验证](basic-authentication.md): 介绍在 .osc 提供商支持基本身份验证的情况下, 要支持登录到社交网络的 Office 用户, 您的 .osc 的典型呼叫序列。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-112">[Basic Authentication](basic-authentication.md): Describes the typical calling sequence of the OSC to support an Office user who is logging on to a social network, if the OSC provider supports basic authentication.</span></span>
    
- <span data-ttu-id="2b1a9-113">[基于表单的身份验证](forms-based-authentication.md): 介绍在 .osc 提供程序支持基于表单的身份验证的情况下, 用于支持登录到社交网络的 Office 用户的 .osc 的典型呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-113">[Forms-Based Authentication](forms-based-authentication.md): Describes the typical calling sequence of the OSC to support an Office user who is logging on to a social network, if the OSC provider supports forms-based authentication.</span></span>
    
- <span data-ttu-id="2b1a9-114">[获取活动](getting-activities.md): 介绍在社交网络 .osc 提供商支持活动同步的情况下, 从社交网络同步 Office 用户好友活动的 .osc 的典型呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-114">[Getting Activities](getting-activities.md): Describes the typical calling sequence of the OSC to synchronize the activities of the Office user's friends from a social network, if the social network OSC provider supports synchronization of activities.</span></span>
    
- <span data-ttu-id="2b1a9-115">[获取朋友信息](getting-friends-information.md): 如果社交网络 .osc 提供商支持对联系人的缓存同步, 则介绍了 .osc 的典型呼叫顺序, 以便从社交网络同步 Office 用户的好友列表。</span><span class="sxs-lookup"><span data-stu-id="2b1a9-115">[Getting Friends Information](getting-friends-information.md): Describes the typical calling sequence of the OSC to synchronize the Office user's friends list from a social network, if the social network OSC provider supports cached synchronization of contacts.</span></span>
    
## <a name="reference"></a><span data-ttu-id="2b1a9-116">参考</span><span class="sxs-lookup"><span data-stu-id="2b1a9-116">Reference</span></span>

- [<span data-ttu-id="2b1a9-117">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="2b1a9-117">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="2b1a9-118">相关部分</span><span class="sxs-lookup"><span data-stu-id="2b1a9-118">Related sections</span></span>

- [<span data-ttu-id="2b1a9-119">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="2b1a9-119">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [<span data-ttu-id="2b1a9-120">.osc 示例模板</span><span class="sxs-lookup"><span data-stu-id="2b1a9-120">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="2b1a9-121">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="2b1a9-121">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="2b1a9-122">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="2b1a9-122">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="2b1a9-123">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="2b1a9-123">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="2b1a9-124">开发提供程序的最佳实践</span><span class="sxs-lookup"><span data-stu-id="2b1a9-124">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="2b1a9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b1a9-125">See also</span></span>

- [<span data-ttu-id="2b1a9-126">XML 的功能</span><span class="sxs-lookup"><span data-stu-id="2b1a9-126">XML for Capabilities</span></span>](xml-for-capabilities.md)

