---
title: OSC 典型调用序列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f61960f7-e018-4d2e-8e32-426ed46d9064
description: 本节介绍 OSC Outlook扩展 (实现) OSC 提供程序扩展性接口中的成员的典型调用序列。
ms.openlocfilehash: f7829b710d6840ccd1fa0f990d6e03b2eb879431
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413610"
---
# <a name="osc-typical-calling-sequences"></a><span data-ttu-id="936dc-103">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="936dc-103">OSC typical calling sequences</span></span>

<span data-ttu-id="936dc-104">本节介绍 OSC Outlook扩展 (实现) OSC 提供程序扩展性接口中的成员的典型调用序列。</span><span class="sxs-lookup"><span data-stu-id="936dc-104">This section describes the Outlook Social Connector (OSC) typical calling sequences of members in the OSC provider extensibility interfaces, which an OSC provider implements.</span></span> <span data-ttu-id="936dc-105">典型的调用序列说明了 OSC 如何使用以及何时使用此类接口和方法，以便你可以更好地确定如何在提供程序扩展性接口上实现给定成员。</span><span class="sxs-lookup"><span data-stu-id="936dc-105">The typical calling sequences illustrate how and when the OSC uses such interfaces and methods, to let you better determine how to implement a given member on a provider extensibility interface.</span></span> <span data-ttu-id="936dc-106">实际调用顺序可能因 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md) 方法返回的功能而异。</span><span class="sxs-lookup"><span data-stu-id="936dc-106">The actual calling sequence can vary depending on the capabilities returned by the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method.</span></span> <span data-ttu-id="936dc-107">功能示例包括：</span><span class="sxs-lookup"><span data-stu-id="936dc-107">Examples of capabilities include the following:</span></span> 
  
- <span data-ttu-id="936dc-108">提供程序支持从社交网络获取、缓存或动态查找好友和活动。</span><span class="sxs-lookup"><span data-stu-id="936dc-108">Provider support for getting, caching, or dynamically looking up friends and activities from the social network.</span></span>
    
- <span data-ttu-id="936dc-109">OSC 应为用户登录显示的用户界面。</span><span class="sxs-lookup"><span data-stu-id="936dc-109">The user interface that the OSC should display for user logon.</span></span>
    
- <span data-ttu-id="936dc-110">身份验证类型 (，例如，基于表单) OSC 应该使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="936dc-110">The authentication type (for example, forms-based authentication) that the OSC should use.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="936dc-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="936dc-111">In this section</span></span>

- <span data-ttu-id="936dc-112">[基本身份验证](basic-authentication.md)：描述 OSC 的典型调用序列，以支持Office登录社交网络的用户（如果 OSC 提供程序支持基本身份验证）。</span><span class="sxs-lookup"><span data-stu-id="936dc-112">[Basic Authentication](basic-authentication.md): Describes the typical calling sequence of the OSC to support an Office user who is logging on to a social network, if the OSC provider supports basic authentication.</span></span>
    
- <span data-ttu-id="936dc-113">[基于表单的身份验证](forms-based-authentication.md)：介绍 OSC 的典型调用序列，以支持登录到社交网络的 Office 用户（如果 OSC 提供程序支持基于表单的身份验证）。</span><span class="sxs-lookup"><span data-stu-id="936dc-113">[Forms-Based Authentication](forms-based-authentication.md): Describes the typical calling sequence of the OSC to support an Office user who is logging on to a social network, if the OSC provider supports forms-based authentication.</span></span>
    
- <span data-ttu-id="936dc-114">[获取活动](getting-activities.md)：描述 OSC 的典型调用序列，以同步 Office 用户的好友在社交网络中的活动（如果社交网络 OSC 提供程序支持同步活动）。</span><span class="sxs-lookup"><span data-stu-id="936dc-114">[Getting Activities](getting-activities.md): Describes the typical calling sequence of the OSC to synchronize the activities of the Office user's friends from a social network, if the social network OSC provider supports synchronization of activities.</span></span>
    
- <span data-ttu-id="936dc-115">[获取好友信息](getting-friends-information.md)：介绍 OSC 的典型调用序列，以从社交网络同步 Office 用户的好友列表（如果社交网络 OSC 提供程序支持联系人的缓存同步）。</span><span class="sxs-lookup"><span data-stu-id="936dc-115">[Getting Friends Information](getting-friends-information.md): Describes the typical calling sequence of the OSC to synchronize the Office user's friends list from a social network, if the social network OSC provider supports cached synchronization of contacts.</span></span>
    
## <a name="reference"></a><span data-ttu-id="936dc-116">参考</span><span class="sxs-lookup"><span data-stu-id="936dc-116">Reference</span></span>

- [<span data-ttu-id="936dc-117">OutlookSocial Connector Provider Reference</span><span class="sxs-lookup"><span data-stu-id="936dc-117">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="936dc-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="936dc-118">Related sections</span></span>

- [<span data-ttu-id="936dc-119">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="936dc-119">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [<span data-ttu-id="936dc-120">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="936dc-120">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="936dc-121">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="936dc-121">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="936dc-122">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="936dc-122">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="936dc-123">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="936dc-123">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="936dc-124">开发提供程序的最佳实践</span><span class="sxs-lookup"><span data-stu-id="936dc-124">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="936dc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="936dc-125">See also</span></span>

- [<span data-ttu-id="936dc-126">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="936dc-126">XML for Capabilities</span></span>](xml-for-capabilities.md)

