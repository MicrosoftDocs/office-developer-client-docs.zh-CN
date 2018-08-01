---
title: 开发具有 OSC XML 架构的提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0872b1b9-c21f-4bba-8cf1-4b010d8d7fb6
description: Outlook Social Connector (OSC) 提供程序的 XML 架构定义大量信息的从社交网络通过传递网络的 OSC 提供程序为 OSC 的格式。
ms.openlocfilehash: 93df682751146b501a316be62641b8cfd47a74a8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779215"
---
# <a name="developing-a-provider-with-the-osc-xml-schema"></a><span data-ttu-id="dfd8a-103">开发具有 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="dfd8a-103">Developing a provider with the OSC XML schema</span></span>

<span data-ttu-id="dfd8a-104">Outlook Social Connector (OSC) 提供程序的 XML 架构定义大量信息的从社交网络通过传递网络的 OSC 提供程序为 OSC 的格式。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-104">The Outlook Social Connector (OSC) provider XML schema defines the format of a significant amount of information that is passed from a social network through the network's OSC provider to the OSC.</span></span> <span data-ttu-id="dfd8a-105">XML 架构允许 OSC 提供程序指定的提供程序、 朋友和活动源项目的社交网络上使用的三个主元素、**功能**、**朋友**和**activityFeed**和及其子功能元素。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-105">The XML schema allows an OSC provider to specify capabilities of the provider, friends, and activity feed items on the social network, by using the three main elements, **capabilities**, **friends**, and **activityFeed**, and their child elements.</span></span> <span data-ttu-id="dfd8a-106">OSC 提供程序实现接口和它们的方法中 OSC 提供程序扩展性，作为遵守 OSC 提供程序的 XML 架构的输出参数返回 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-106">The OSC provider implements interfaces and their methods in the OSC provider extensibility, returning XML strings as output parameters that comply with the OSC provider XML schema.</span></span> <span data-ttu-id="dfd8a-107">OSC 调用这些方法来获取它可以了解该 XML 架构定义的信息。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-107">The OSC calls these methods to obtain information that it can understand as defined by the XML schema.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dfd8a-108">OSC 提供程序扩展性支持调试提供程序通过设置`DebugProviders`的值`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`为 1 的注册表项。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-108">OSC provider extensibility supports debugging providers by setting the `DebugProviders` value of the  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector` registry key to 1.</span></span> <span data-ttu-id="dfd8a-109">当您打开调试提供程序时，OSC 验证提供程序 XML 针对**xmlns** XML 属性中指定的 OSC XML 架构的版本。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-109">When you turn on provider debugging, the OSC validates the provider XML against the version of the OSC XML schema that you specify in the **xmlns** XML attribute.</span></span> <span data-ttu-id="dfd8a-110">OSC 1.1 和版本的 Outlook Social Connector 2013 相 OSC，指定**xmlns**属性，如下所示：`xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`</span><span class="sxs-lookup"><span data-stu-id="dfd8a-110">For OSC 1.1 and versions of the OSC since Outlook Social Connector 2013, specify the **xmlns** attribute as follows: `xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd"`</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="dfd8a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="dfd8a-111">In this section</span></span>

- <span data-ttu-id="dfd8a-112">[同步朋友和活动](synchronizing-friends-and-activities.md)： 介绍了朋友、 非朋友和社交网络上的活动，可以同步 OSC 提供程序的各种方法。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-112">[Synchronizing Friends and Activities](synchronizing-friends-and-activities.md): Describes the various ways that OSC providers can synchronize friends, non-friends, and activities on a social network.</span></span> 
    
- <span data-ttu-id="dfd8a-113">[OSC 提供程序 XML 示例](osc-provider-xml-examples.md)： 包括 XML 示例演示如何指定功能的 OSC 提供程序、 朋友和活动源社交网络上使用 OSC XML 架构的项目。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-113">[OSC Provider XML Examples](osc-provider-xml-examples.md): Includes XML examples that show how to specify capabilities of an OSC provider, friends, and activity feed items on a social network by using the OSC XML schema.</span></span>
    
- <span data-ttu-id="dfd8a-114">[功能 XML](xml-for-capabilities.md)： 说明 OSC 使用获取功能信息，表示在**功能**XML 中，从 OSC 提供程序- [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-114">[XML for Capabilities](xml-for-capabilities.md): Explains the - [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method that the OSC uses to obtain capabilities information, expressed in **capabilities** XML, from the OSC provider.</span></span> <span data-ttu-id="dfd8a-115">本节还介绍 OSC 提供程序的 XML 架构中的允许 OSC 提供程序指定其功能，包括如何对用户进行身份验证和同步朋友和活动的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-115">This section also describes the XML elements in the OSC provider XML schema that allow an OSC provider to specify its functionality, including how it authenticates users and synchronizes friends and activities.</span></span> 
    
- <span data-ttu-id="dfd8a-116">[XML 朋友](xml-for-friends.md)： 提供 OSC 使用获取朋友的信息，表示在**朋友**XML 中，从 OSC 提供程序的 Api 的示例。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-116">[XML for Friends](xml-for-friends.md): Gives examples of the APIs that the OSC uses to obtain friends' information, expressed in **friends** XML, from the OSC provider.</span></span> <span data-ttu-id="dfd8a-117">本节还介绍**朋友**XML 中的元素。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-117">This section also describes elements in the **friends** XML.</span></span> 
    
- <span data-ttu-id="dfd8a-118">[活动的 XML](xml-for-activities.md)： 提供 OSC 使用获取活动信息，表示在**activityFeed** XML 中，从 OSC 提供程序的 Api 的示例。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-118">[XML for Activities](xml-for-activities.md): Gives examples of the APIs that the OSC uses to obtain activities information, expressed in **activityFeed** XML, from the OSC provider.</span></span> <span data-ttu-id="dfd8a-119">本节还介绍允许 OSC 提供程序指定活动源中的 OSC 提供程序的 XML 架构的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-119">This section also describes the XML elements in the OSC provider XML schema that allow an OSC provider to specify an activity feed.</span></span> <span data-ttu-id="dfd8a-120">活动源包括的网络其中活动源项目产生，每个活动源项的详细信息 （如所有者，键入，和活动的发布日期），并显示活动的模板。</span><span class="sxs-lookup"><span data-stu-id="dfd8a-120">An activity feed includes the network where the activity feed items originated, details of each activity feed item (such as owner, type, and publish date of the activity), and the template to display the activity.</span></span> 
    
## <a name="reference"></a><span data-ttu-id="dfd8a-121">参考</span><span class="sxs-lookup"><span data-stu-id="dfd8a-121">Reference</span></span>

- [<span data-ttu-id="dfd8a-122">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="dfd8a-122">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="dfd8a-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="dfd8a-123">Related sections</span></span>

- [<span data-ttu-id="dfd8a-124">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="dfd8a-124">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)
  
- [<span data-ttu-id="dfd8a-125">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="dfd8a-125">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="dfd8a-126">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="dfd8a-126">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="dfd8a-127">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="dfd8a-127">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="dfd8a-128">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="dfd8a-128">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="dfd8a-129">开发提供程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="dfd8a-129">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="dfd8a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfd8a-130">See also</span></span>

- [<span data-ttu-id="dfd8a-131">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="dfd8a-131">Debugging a Provider</span></span>](debugging-a-provider.md)

