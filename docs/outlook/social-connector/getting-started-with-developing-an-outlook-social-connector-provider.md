---
title: Outlook Social Connector 提供程序开发入门
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c65d2df-86a3-48d5-9fec-a9040f3b878c
description: Outlook Social Connector (OSC) 提供程序参考介绍如何使用 OSC 提供程序扩展性开发 OSC 提供程序。
ms.openlocfilehash: 19f5ffe8987d0b19017692ddb8f7888be2140033
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779194"
---
# <a name="getting-started-with-developing-an-outlook-social-connector-provider"></a><span data-ttu-id="1df28-103">Outlook Social Connector 提供程序开发入门</span><span class="sxs-lookup"><span data-stu-id="1df28-103">Getting started with developing an Outlook Social Connector provider</span></span>

<span data-ttu-id="1df28-104">Outlook Social Connector (OSC) 提供程序参考介绍如何使用 OSC 提供程序扩展性开发 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="1df28-104">The Outlook Social Connector (OSC) Provider Reference describes how to develop an OSC provider by using OSC provider extensibility.</span></span> <span data-ttu-id="1df28-105">如果您是新增开发 Outlook 解决方案，请参阅[选择的 API 或技术用于开发 Outlook 解决方案](http://msdn.microsoft.com/library/8295da20-e567-4d08-b8e4-5c9b4498edd4%28Office.15%29.aspx)来标识的 Api 和技术的最适合您的需求。</span><span class="sxs-lookup"><span data-stu-id="1df28-105">If you are new to developing solutions for Outlook, see [Selecting an API or Technology for Developing Outlook Solutions](http://msdn.microsoft.com/library/8295da20-e567-4d08-b8e4-5c9b4498edd4%28Office.15%29.aspx) to identify the APIs and technologies that are most appropriate for your needs.</span></span> 

<span data-ttu-id="1df28-106">本节提供 OSC、 OSC 提供程序可用于学习如何开发提供程序、 技术要求的开发提供程序，最佳实践的有用、 快速步骤和 what's new in 此发行版的概述。</span><span class="sxs-lookup"><span data-stu-id="1df28-106">This section gives an overview of the OSC, how an OSC provider can be useful, quick steps for learning to develop a provider, technical requirements, best practices for developing a provider, and what's new in this release.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="1df28-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="1df28-107">In this section</span></span>

- <span data-ttu-id="1df28-108">[What's New for 提供程序](what-s-new-for-providers.md)： 比较 OSC 功能在以前的和当前版本中，并介绍了接口成员和 XML 架构元素的已添加、 更改或弃用此版本中。</span><span class="sxs-lookup"><span data-stu-id="1df28-108">[What's New for Providers](what-s-new-for-providers.md): Compares OSC features in the previous and current release, and describes interface members and XML schema elements that have been added, changed, or deprecated in this release.</span></span> 
    
- <span data-ttu-id="1df28-109">[为什么开发 Outlook Social Connector 提供程序](why-develop-an-outlook-social-connector-provider.md)： 介绍如何 OSC 提供程序可用于常见社交网络站点和其他内部网络的工具。</span><span class="sxs-lookup"><span data-stu-id="1df28-109">[Why Develop an Outlook Social Connector Provider](why-develop-an-outlook-social-connector-provider.md): Describes how an OSC provider can be useful for common social network sites and other internal networking tools.</span></span>
    
- <span data-ttu-id="1df28-110">[有关使用 Outlook 与社交网络 OSC](relating-the-osc-with-outlook-and-social-networks.md)： 提供 OSC 社交网络的连接 Outlook 用户的方式的体系结构视图。</span><span class="sxs-lookup"><span data-stu-id="1df28-110">[Relating the OSC with Outlook and Social Networks](relating-the-osc-with-outlook-and-social-networks.md): Provides an architectural view of how the OSC connects Outlook users with social networks.</span></span> <span data-ttu-id="1df28-111">此外定义方式的常用术语，如"社交网络"，"朋友"、"非-朋友"和"contacts"使用此参考的其余部分中。</span><span class="sxs-lookup"><span data-stu-id="1df28-111">Also defines the way that common terms, like "social networks," "friends," "non-friends," and "contacts" are used in the rest of this reference.</span></span>
    
- <span data-ttu-id="1df28-112">[快速学习开发提供程序的步骤](quick-steps-for-learning-to-develop-a-provider.md)： 了解如何开发 OSC 提供程序的步骤概述了。</span><span class="sxs-lookup"><span data-stu-id="1df28-112">[Quick Steps for Learning to Develop a Provider](quick-steps-for-learning-to-develop-a-provider.md): Provides a summary of steps to learn to develop an OSC provider.</span></span>
    
- <span data-ttu-id="1df28-113">[技术要求](technical-requirements.md)： 描述受支持的编程语言、 COM 可见性要求，方法返回类型要求和 OSC 提供程序扩展性 DLL 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1df28-113">[Technical Requirements](technical-requirements.md): Describes the supported programming languages, COM visibility requirements, method return type requirements, and details of the OSC provider extensibility DLL.</span></span>
    
- <span data-ttu-id="1df28-114">[开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)： 提供开发 OSC 提供程序时应遵循最佳做法的列表。</span><span class="sxs-lookup"><span data-stu-id="1df28-114">[Best Practices for Developing a Provider](best-practices-for-developing-a-provider.md): Provides a list of best practices to follow while developing an OSC provider.</span></span>
    
## <a name="reference"></a><span data-ttu-id="1df28-115">参考</span><span class="sxs-lookup"><span data-stu-id="1df28-115">Reference</span></span>

- [<span data-ttu-id="1df28-116">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="1df28-116">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="1df28-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="1df28-117">Related sections</span></span>

- [<span data-ttu-id="1df28-118">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="1df28-118">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="1df28-119">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="1df28-119">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="1df28-120">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="1df28-120">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="1df28-121">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="1df28-121">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="1df28-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="1df28-122">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="1df28-123">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="1df28-123">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="1df28-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1df28-124">See also</span></span>

- [<span data-ttu-id="1df28-125">Microsoft Outlook Social Connector 32 位</span><span class="sxs-lookup"><span data-stu-id="1df28-125">Microsoft Outlook Social Connector 32-bit</span></span>](http://www.microsoft.com/downloads/details.aspx?FamilyID=b638cc14-11e5-448a-b5a6-4f553ce81b94)
- [<span data-ttu-id="1df28-126">Outlook Social Connector (KB983403) 32 位版本的更新</span><span class="sxs-lookup"><span data-stu-id="1df28-126">Update for Outlook Social Connector (KB983403), 32-Bit Edition</span></span>](http://www.microsoft.com/downloads/details.aspx?FamilyID=9886faca-f1c5-4579-83e2-c872c7abc61a)
- [<span data-ttu-id="1df28-127">Outlook Social Connector (KB983403) 64 位版本的更新</span><span class="sxs-lookup"><span data-stu-id="1df28-127">Update for Outlook Social Connector (KB983403), 64-bit Edition</span></span>](http://www.microsoft.com/downloads/details.aspx?FamilyID=72a506a7-8a91-4d56-8b27-bf3b3f58fe9a)
- [<span data-ttu-id="1df28-128">Outlook Social Connector 2013： 提供程序模板</span><span class="sxs-lookup"><span data-stu-id="1df28-128">Outlook Social Connector 2013: Provider templates</span></span>](http://code.msdn.microsoft.com/Outlook-Social-Connector-73fd8d2c)

