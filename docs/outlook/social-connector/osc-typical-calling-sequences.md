---
title: OSC 典型调用序列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f61960f7-e018-4d2e-8e32-426ed46d9064
description: 本节介绍 Outlook Social Connector (OSC) 典型调用序列 OSC 提供程序实现的 OSC 提供程序扩展性接口中的成员。
ms.openlocfilehash: 4a79e27fadb78933f41f26818cfab8b7f4a5aae7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779320"
---
# <a name="osc-typical-calling-sequences"></a><span data-ttu-id="7a57f-103">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="7a57f-103">OSC typical calling sequences</span></span>

<span data-ttu-id="7a57f-104">本节介绍 Outlook Social Connector (OSC) 典型调用序列 OSC 提供程序实现的 OSC 提供程序扩展性接口中的成员。</span><span class="sxs-lookup"><span data-stu-id="7a57f-104">This section describes the Outlook Social Connector (OSC) typical calling sequences of members in the OSC provider extensibility interfaces, which an OSC provider implements.</span></span> <span data-ttu-id="7a57f-105">典型调用序列说明如何以及何时 OSC 使用此类接口和方法，让您更好地确定如何在提供程序扩展性接口实现给定的成员。</span><span class="sxs-lookup"><span data-stu-id="7a57f-105">The typical calling sequences illustrate how and when the OSC uses such interfaces and methods, to let you better determine how to implement a given member on a provider extensibility interface.</span></span> <span data-ttu-id="7a57f-106">实际的调用序列取决于[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法返回的功能。</span><span class="sxs-lookup"><span data-stu-id="7a57f-106">The actual calling sequence can vary depending on the capabilities returned by the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method.</span></span> <span data-ttu-id="7a57f-107">功能的示例包括：</span><span class="sxs-lookup"><span data-stu-id="7a57f-107">Examples of capabilities include the following:</span></span> 
  
- <span data-ttu-id="7a57f-108">获取、 缓存，或动态查找朋友和活动从社交网络支持提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a57f-108">Provider support for getting, caching, or dynamically looking up friends and activities from the social network.</span></span>
    
- <span data-ttu-id="7a57f-109">OSC 应显示为用户登录用户界面。</span><span class="sxs-lookup"><span data-stu-id="7a57f-109">The user interface that the OSC should display for user logon.</span></span>
    
- <span data-ttu-id="7a57f-110">OSC 应使用的身份验证类型 （例如，基于表单的身份验证）。</span><span class="sxs-lookup"><span data-stu-id="7a57f-110">The authentication type (for example, forms-based authentication) that the OSC should use.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="7a57f-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="7a57f-111">In this section</span></span>

- <span data-ttu-id="7a57f-112">[基本身份验证](basic-authentication.md)： 介绍了支持的 Office 用户登录到社交网络中，如果 OSC 提供程序支持基本身份验证 OSC 典型调用序列。</span><span class="sxs-lookup"><span data-stu-id="7a57f-112">[Basic Authentication](basic-authentication.md): Describes the typical calling sequence of the OSC to support an Office user who is logging on to a social network, if the OSC provider supports basic authentication.</span></span>
    
- <span data-ttu-id="7a57f-113">[基于表单的身份验证](forms-based-authentication.md)： 介绍了支持的 Office 用户登录到社交网络中，如果 OSC 提供程序支持基于表单的身份验证 OSC 典型调用序列。</span><span class="sxs-lookup"><span data-stu-id="7a57f-113">[Forms-Based Authentication](forms-based-authentication.md): Describes the typical calling sequence of the OSC to support an Office user who is logging on to a social network, if the OSC provider supports forms-based authentication.</span></span>
    
- <span data-ttu-id="7a57f-114">[获取活动](getting-activities.md)： 介绍同步的从社交网络的 Office 用户的好友的活动 OSC 典型调用序列，如果社交网络 OSC 提供程序支持的活动同步。</span><span class="sxs-lookup"><span data-stu-id="7a57f-114">[Getting Activities](getting-activities.md): Describes the typical calling sequence of the OSC to synchronize the activities of the Office user's friends from a social network, if the social network OSC provider supports synchronization of activities.</span></span>
    
- <span data-ttu-id="7a57f-115">[获取好友信息](getting-friends-information.md)： 如果社交网络 OSC 提供程序支持的联系人的缓存的同步介绍同步社交网络中，从 Office 用户朋友列表 OSC 典型调用序列。</span><span class="sxs-lookup"><span data-stu-id="7a57f-115">[Getting Friends Information](getting-friends-information.md): Describes the typical calling sequence of the OSC to synchronize the Office user's friends list from a social network, if the social network OSC provider supports cached synchronization of contacts.</span></span>
    
## <a name="reference"></a><span data-ttu-id="7a57f-116">参考</span><span class="sxs-lookup"><span data-stu-id="7a57f-116">Reference</span></span>

- [<span data-ttu-id="7a57f-117">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="7a57f-117">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="7a57f-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="7a57f-118">Related sections</span></span>

- [<span data-ttu-id="7a57f-119">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="7a57f-119">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [<span data-ttu-id="7a57f-120">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="7a57f-120">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="7a57f-121">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="7a57f-121">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="7a57f-122">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="7a57f-122">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="7a57f-123">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="7a57f-123">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="7a57f-124">开发提供程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="7a57f-124">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="7a57f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a57f-125">See also</span></span>

- [<span data-ttu-id="7a57f-126">功能 XML</span><span class="sxs-lookup"><span data-stu-id="7a57f-126">XML for Capabilities</span></span>](xml-for-capabilities.md)

