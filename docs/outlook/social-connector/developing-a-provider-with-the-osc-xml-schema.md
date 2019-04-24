---
title: 开发具有 OSC XML 架构的提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0872b1b9-c21f-4bba-8cf1-4b010d8d7fb6
description: Outlook Social Connector (.osc) 提供程序 XML 架构定义从社交网络通过网络的 .osc 提供程序传递给 .osc 的大量信息的格式。
ms.openlocfilehash: 75809179131ce6c6b8bbe171d2670e59cebe3494
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281074"
---
# <a name="developing-a-provider-with-the-osc-xml-schema"></a><span data-ttu-id="271c5-103">开发具有 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="271c5-103">Developing a provider with the OSC XML schema</span></span>

<span data-ttu-id="271c5-104">Outlook Social Connector (.osc) 提供程序 XML 架构定义从社交网络通过网络的 .osc 提供程序传递给 .osc 的大量信息的格式。</span><span class="sxs-lookup"><span data-stu-id="271c5-104">The Outlook Social Connector (OSC) provider XML schema defines the format of a significant amount of information that is passed from a social network through the network's OSC provider to the OSC.</span></span> <span data-ttu-id="271c5-105">通过 XML 架构, .osc 提供程序可以使用以下三个主要元素、**功能**、**好友**和**microsoft.office.server.activityfeed**, 在社交网络上指定提供者、好友和活动源项目的功能及其孩子单元.</span><span class="sxs-lookup"><span data-stu-id="271c5-105">The XML schema allows an OSC provider to specify capabilities of the provider, friends, and activity feed items on the social network, by using the three main elements, **capabilities**, **friends**, and **activityFeed**, and their child elements.</span></span> <span data-ttu-id="271c5-106">.osc 提供程序在 .osc 提供程序扩展性中实现接口及其方法, 将 XML 字符串作为符合 .osc 提供程序 XML 架构的输出参数返回。</span><span class="sxs-lookup"><span data-stu-id="271c5-106">The OSC provider implements interfaces and their methods in the OSC provider extensibility, returning XML strings as output parameters that comply with the OSC provider XML schema.</span></span> <span data-ttu-id="271c5-107">.osc 调用这些方法来获取可理解的信息, 如 XML 架构所定义的那样。</span><span class="sxs-lookup"><span data-stu-id="271c5-107">The OSC calls these methods to obtain information that it can understand as defined by the XML schema.</span></span>
  
> [!NOTE]
> <span data-ttu-id="271c5-108">.osc 提供程序扩展性支持通过将`DebugProviders` `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`注册表项的值设置为1来调试提供程序。</span><span class="sxs-lookup"><span data-stu-id="271c5-108">OSC provider extensibility supports debugging providers by setting the `DebugProviders` value of the  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector` registry key to 1.</span></span> <span data-ttu-id="271c5-109">启用提供程序调试后, .osc 将根据您在**xmlns** xml 属性中指定的 .osc xml 架构的版本验证提供程序 xml。</span><span class="sxs-lookup"><span data-stu-id="271c5-109">When you turn on provider debugging, the OSC validates the provider XML against the version of the OSC XML schema that you specify in the **xmlns** XML attribute.</span></span> <span data-ttu-id="271c5-110">对于自 Outlook Social Connector 2013 以来的 .osc 1.1 和 .osc 版本, 请按如下所示指定**xmlns**属性:`xmlns="https://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`</span><span class="sxs-lookup"><span data-stu-id="271c5-110">For OSC 1.1 and versions of the OSC since Outlook Social Connector 2013, specify the **xmlns** attribute as follows: `xmlns="https://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="271c5-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="271c5-111">In this section</span></span>

- <span data-ttu-id="271c5-112">[同步朋友和活动](synchronizing-friends-and-activities.md): 介绍了 .osc 提供商可在社交网络上同步朋友、非好友和活动的各种方式。</span><span class="sxs-lookup"><span data-stu-id="271c5-112">[Synchronizing Friends and Activities](synchronizing-friends-and-activities.md): Describes the various ways that OSC providers can synchronize friends, non-friends, and activities on a social network.</span></span> 
    
- <span data-ttu-id="271c5-113">[.osc 提供程序 XML 示例](osc-provider-xml-examples.md): 包括 xml 示例, 演示如何使用 .osc XML 架构在社交网络上指定 .osc 提供者、好友和活动源项目的功能。</span><span class="sxs-lookup"><span data-stu-id="271c5-113">[OSC Provider XML Examples](osc-provider-xml-examples.md): Includes XML examples that show how to specify capabilities of an OSC provider, friends, and activity feed items on a social network by using the OSC XML schema.</span></span>
    
- <span data-ttu-id="271c5-114">[XML for the 功能](xml-for-capabilities.md): 说明了[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法, .osc 使用它从 .osc 提供程序获取功能 XML \*\*\*\* 中的功能信息。</span><span class="sxs-lookup"><span data-stu-id="271c5-114">[XML for Capabilities](xml-for-capabilities.md): Explains the - [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method that the OSC uses to obtain capabilities information, expressed in **capabilities** XML, from the OSC provider.</span></span> <span data-ttu-id="271c5-115">本节还介绍了 .osc 提供程序 xml 架构中的 xml 元素, 这些元素允许 .osc 提供程序指定其功能, 包括如何对用户进行身份验证以及如何同步好友和活动。</span><span class="sxs-lookup"><span data-stu-id="271c5-115">This section also describes the XML elements in the OSC provider XML schema that allow an OSC provider to specify its functionality, including how it authenticates users and synchronizes friends and activities.</span></span> 
    
- <span data-ttu-id="271c5-116">[适用于好友的 XML](xml-for-friends.md): 提供了 .osc 用于获取来自 .osc 提供商的朋友信息的 api 示例\*\*\*\* 。</span><span class="sxs-lookup"><span data-stu-id="271c5-116">[XML for Friends](xml-for-friends.md): Gives examples of the APIs that the OSC uses to obtain friends' information, expressed in **friends** XML, from the OSC provider.</span></span> <span data-ttu-id="271c5-117">本节还介绍了**好友**XML 中的元素。</span><span class="sxs-lookup"><span data-stu-id="271c5-117">This section also describes elements in the **friends** XML.</span></span> 
    
- <span data-ttu-id="271c5-118">[XML 的活动](xml-for-activities.md): 提供了 .osc 用于从 .osc 提供程序获取活动信息 (以**microsoft.office.server.activityfeed** XML 表示) 的 api 示例。</span><span class="sxs-lookup"><span data-stu-id="271c5-118">[XML for Activities](xml-for-activities.md): Gives examples of the APIs that the OSC uses to obtain activities information, expressed in **activityFeed** XML, from the OSC provider.</span></span> <span data-ttu-id="271c5-119">本节还介绍了 .osc 提供程序 xml 架构中的 xml 元素, 这些元素允许 .osc 提供程序指定活动源。</span><span class="sxs-lookup"><span data-stu-id="271c5-119">This section also describes the XML elements in the OSC provider XML schema that allow an OSC provider to specify an activity feed.</span></span> <span data-ttu-id="271c5-120">活动源包括生成活动源项目的网络、每个活动源项目的详细信息 (如活动的所有者、类型和发布日期) 以及显示该活动的模板。</span><span class="sxs-lookup"><span data-stu-id="271c5-120">An activity feed includes the network where the activity feed items originated, details of each activity feed item (such as owner, type, and publish date of the activity), and the template to display the activity.</span></span> 
    
## <a name="reference"></a><span data-ttu-id="271c5-121">参考</span><span class="sxs-lookup"><span data-stu-id="271c5-121">Reference</span></span>

- [<span data-ttu-id="271c5-122">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="271c5-122">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="271c5-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="271c5-123">Related sections</span></span>

- [<span data-ttu-id="271c5-124">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="271c5-124">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [<span data-ttu-id="271c5-125">.osc 示例模板</span><span class="sxs-lookup"><span data-stu-id="271c5-125">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="271c5-126">.osc 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="271c5-126">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="271c5-127">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="271c5-127">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="271c5-128">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="271c5-128">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="271c5-129">开发提供程序的最佳实践</span><span class="sxs-lookup"><span data-stu-id="271c5-129">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="271c5-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="271c5-130">See also</span></span>

- [<span data-ttu-id="271c5-131">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="271c5-131">Debugging a Provider</span></span>](debugging-a-provider.md)

