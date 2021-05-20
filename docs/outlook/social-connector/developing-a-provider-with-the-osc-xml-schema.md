---
title: 开发具有 OSC XML 架构的提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0872b1b9-c21f-4bba-8cf1-4b010d8d7fb6
description: Outlook Social Connector (OSC) 提供程序 XML 架构定义大量信息的格式，这些信息通过网络的 OSC 提供程序从社交网络传递到 OSC。
ms.openlocfilehash: 2346e23beb2de1664ec90263a8f5db5d46c54e6f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539253"
---
# <a name="developing-a-provider-with-the-osc-xml-schema"></a><span data-ttu-id="ae0a6-103">开发具有 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="ae0a6-103">Developing a provider with the OSC XML schema</span></span>

<span data-ttu-id="ae0a6-104">Outlook Social Connector (OSC) 提供程序 XML 架构定义大量信息的格式，这些信息通过网络的 OSC 提供程序从社交网络传递到 OSC。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-104">The Outlook Social Connector (OSC) provider XML schema defines the format of a significant amount of information that is passed from a social network through the network's OSC provider to the OSC.</span></span> <span data-ttu-id="ae0a6-105">XML 架构允许 OSC 提供程序使用三个主要元素、功能、好友和 **activityFeed** 及其子元素指定社交网络上提供程序、好友和活动源项的功能。 </span><span class="sxs-lookup"><span data-stu-id="ae0a6-105">The XML schema allows an OSC provider to specify capabilities of the provider, friends, and activity feed items on the social network, by using the three main elements, **capabilities**, **friends**, and **activityFeed**, and their child elements.</span></span> <span data-ttu-id="ae0a6-106">OSC 提供程序在 OSC 提供程序扩展性中实现接口及其方法，返回 XML 字符串作为符合 OSC 提供程序 XML 架构的输出参数。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-106">The OSC provider implements interfaces and their methods in the OSC provider extensibility, returning XML strings as output parameters that comply with the OSC provider XML schema.</span></span> <span data-ttu-id="ae0a6-107">OSC 调用这些方法以获取它可以理解的信息，如 XML 架构所定义。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-107">The OSC calls these methods to obtain information that it can understand as defined by the XML schema.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae0a6-108">OSC 提供程序扩展性支持调试提供程序，将注册表项的值 `DebugProviders` 设置为  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector` 1。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-108">OSC provider extensibility supports debugging providers by setting the `DebugProviders` value of the  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector` registry key to 1.</span></span> <span data-ttu-id="ae0a6-109">打开提供程序调试时，OSC 将对照在 **xmlns** XML 属性中指定的 OSC XML 架构版本验证提供程序 XML。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-109">When you turn on provider debugging, the OSC validates the provider XML against the version of the OSC XML schema that you specify in the **xmlns** XML attribute.</span></span> <span data-ttu-id="ae0a6-110">对于 OSC 1.1 和自 Outlook Social Connector 2013 以来的 OSC 版本，如下所示指定 **xmlns** 属性：`xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`</span><span class="sxs-lookup"><span data-stu-id="ae0a6-110">For OSC 1.1 and versions of the OSC since Outlook Social Connector 2013, specify the **xmlns** attribute as follows: `xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ae0a6-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="ae0a6-111">In this section</span></span>

- <span data-ttu-id="ae0a6-112">[同步好友](synchronizing-friends-and-activities.md)和活动 ：介绍 OSC 提供程序在社交网络上同步好友、非好友和活动的各种方式。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-112">[Synchronizing Friends and Activities](synchronizing-friends-and-activities.md): Describes the various ways that OSC providers can synchronize friends, non-friends, and activities on a social network.</span></span> 
    
- <span data-ttu-id="ae0a6-113">[OSC 提供程序 XML 示例](osc-provider-xml-examples.md)：包括 XML 示例，这些示例显示如何使用 OSC XML 架构指定社交网络上的 OSC 提供程序、好友和活动源项的功能。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-113">[OSC Provider XML Examples](osc-provider-xml-examples.md): Includes XML examples that show how to specify capabilities of an OSC provider, friends, and activity feed items on a social network by using the OSC XML schema.</span></span>
    
- <span data-ttu-id="ae0a6-114">功能的 [XML](xml-for-capabilities.md)：介绍了 OSC 用于从 OSC 提供程序获取功能信息（以 **功能** XML 表示）的 - [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-114">[XML for Capabilities](xml-for-capabilities.md): Explains the - [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method that the OSC uses to obtain capabilities information, expressed in **capabilities** XML, from the OSC provider.</span></span> <span data-ttu-id="ae0a6-115">本节还介绍 OSC 提供程序 XML 架构中的 XML 元素，这些元素允许 OSC 提供程序指定其功能，包括它如何对用户进行身份验证以及同步好友和活动。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-115">This section also describes the XML elements in the OSC provider XML schema that allow an OSC provider to specify its functionality, including how it authenticates users and synchronizes friends and activities.</span></span> 
    
- <span data-ttu-id="ae0a6-116">[适用于好友的 XML：](xml-for-friends.md)提供 OSC 用于从 OSC 提供程序获取好友信息的 API（以 **好友** XML 表示）的示例。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-116">[XML for Friends](xml-for-friends.md): Gives examples of the APIs that the OSC uses to obtain friends' information, expressed in **friends** XML, from the OSC provider.</span></span> <span data-ttu-id="ae0a6-117">本节还介绍好友 XML **中的** 元素。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-117">This section also describes elements in the **friends** XML.</span></span> 
    
- <span data-ttu-id="ae0a6-118">[活动的 XML：](xml-for-activities.md)提供 OSC 用于从 OSC 提供程序获取活动信息（以 **activityFeed** XML 表示）的 API 的示例。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-118">[XML for Activities](xml-for-activities.md): Gives examples of the APIs that the OSC uses to obtain activities information, expressed in **activityFeed** XML, from the OSC provider.</span></span> <span data-ttu-id="ae0a6-119">本节还介绍 OSC 提供程序 XML 架构中的 XML 元素，这些元素允许 OSC 提供程序指定活动源。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-119">This section also describes the XML elements in the OSC provider XML schema that allow an OSC provider to specify an activity feed.</span></span> <span data-ttu-id="ae0a6-120">活动源包括源自活动源项的网络、每个活动源项目的详细信息 (如活动) 的所有者、类型和发布日期，以及用于显示活动的模板。</span><span class="sxs-lookup"><span data-stu-id="ae0a6-120">An activity feed includes the network where the activity feed items originated, details of each activity feed item (such as owner, type, and publish date of the activity), and the template to display the activity.</span></span> 
    
## <a name="reference"></a><span data-ttu-id="ae0a6-121">参考</span><span class="sxs-lookup"><span data-stu-id="ae0a6-121">Reference</span></span>

- [<span data-ttu-id="ae0a6-122">OutlookSocial Connector Provider Reference</span><span class="sxs-lookup"><span data-stu-id="ae0a6-122">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="ae0a6-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="ae0a6-123">Related sections</span></span>

- [<span data-ttu-id="ae0a6-124">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="ae0a6-124">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [<span data-ttu-id="ae0a6-125">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="ae0a6-125">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="ae0a6-126">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="ae0a6-126">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="ae0a6-127">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="ae0a6-127">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="ae0a6-128">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="ae0a6-128">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="ae0a6-129">开发提供程序的最佳实践</span><span class="sxs-lookup"><span data-stu-id="ae0a6-129">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="ae0a6-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae0a6-130">See also</span></span>

- [<span data-ttu-id="ae0a6-131">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="ae0a6-131">Debugging a Provider</span></span>](debugging-a-provider.md)

