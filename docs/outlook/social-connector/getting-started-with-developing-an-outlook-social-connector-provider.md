---
title: 开发社交连接器Outlook入门
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c65d2df-86a3-48d5-9fec-a9040f3b878c
description: OSC Outlook SosC (提供程序参考) 使用 OSC 提供程序扩展性开发 OSC 提供程序。
ms.openlocfilehash: 24f8eabe33103f53e848f055b72fd402bc5dd89a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327158"
---
# <a name="getting-started-with-developing-an-outlook-social-connector-provider"></a><span data-ttu-id="fff97-103">开发社交连接器Outlook入门</span><span class="sxs-lookup"><span data-stu-id="fff97-103">Getting started with developing an Outlook Social Connector provider</span></span>

<span data-ttu-id="fff97-104">OSC Outlook SosC (提供程序参考) 使用 OSC 提供程序扩展性开发 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="fff97-104">The Outlook Social Connector (OSC) Provider Reference describes how to develop an OSC provider by using OSC provider extensibility.</span></span> <span data-ttu-id="fff97-105">如果你对开发适用于 Outlook 的解决方案很了解，请参阅选择用于开发 Outlook 解决方案的[API](https://msdn.microsoft.com/library/8295da20-e567-4d08-b8e4-5c9b4498edd4%28Office.15%29.aspx)或技术，以确定最适合你需求的 API 和技术。</span><span class="sxs-lookup"><span data-stu-id="fff97-105">If you are new to developing solutions for Outlook, see [Selecting an API or Technology for Developing Outlook Solutions](https://msdn.microsoft.com/library/8295da20-e567-4d08-b8e4-5c9b4498edd4%28Office.15%29.aspx) to identify the APIs and technologies that are most appropriate for your needs.</span></span> 

<span data-ttu-id="fff97-106">本节概述了 OSC、OSC 提供程序如何有用、学习开发提供程序的快速步骤、技术要求、开发提供程序的最佳实践以及此版本中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="fff97-106">This section gives an overview of the OSC, how an OSC provider can be useful, quick steps for learning to develop a provider, technical requirements, best practices for developing a provider, and what's new in this release.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="fff97-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="fff97-107">In this section</span></span>

- <span data-ttu-id="fff97-108">[提供程序的](what-s-new-for-providers.md)新增功能：比较上一版本和当前版本中的 OSC 功能，并介绍此版本中已添加、更改或弃用的接口成员和 XML 架构元素。</span><span class="sxs-lookup"><span data-stu-id="fff97-108">[What's New for Providers](what-s-new-for-providers.md): Compares OSC features in the previous and current release, and describes interface members and XML schema elements that have been added, changed, or deprecated in this release.</span></span> 
    
- <span data-ttu-id="fff97-109">[Why Develop an Outlook Social Connector Provider](why-develop-an-outlook-social-connector-provider.md)： Describes how an OSC provider can be useful for common social network sites and other internal networking tools.</span><span class="sxs-lookup"><span data-stu-id="fff97-109">[Why Develop an Outlook Social Connector Provider](why-develop-an-outlook-social-connector-provider.md): Describes how an OSC provider can be useful for common social network sites and other internal networking tools.</span></span>
    
- <span data-ttu-id="fff97-110">[将 OSC 与Outlook](relating-the-osc-with-outlook-and-social-networks.md)社交网络相关：提供 OSC 如何将Outlook社交网络连接的体系结构视图。</span><span class="sxs-lookup"><span data-stu-id="fff97-110">[Relating the OSC with Outlook and Social Networks](relating-the-osc-with-outlook-and-social-networks.md): Provides an architectural view of how the OSC connects Outlook users with social networks.</span></span> <span data-ttu-id="fff97-111">还定义了常见术语（如"社交网络"、"好友"、"非好友"和"联系人"）在此参考的其余部分中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="fff97-111">Also defines the way that common terms, like "social networks," "friends," "non-friends," and "contacts" are used in the rest of this reference.</span></span>
    
- <span data-ttu-id="fff97-112">[学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)：提供学习开发 OSC 提供程序的步骤摘要。</span><span class="sxs-lookup"><span data-stu-id="fff97-112">[Quick Steps for Learning to Develop a Provider](quick-steps-for-learning-to-develop-a-provider.md): Provides a summary of steps to learn to develop an OSC provider.</span></span>
    
- <span data-ttu-id="fff97-113">[技术要求](technical-requirements.md)：介绍支持的编程语言、COM 可见性要求、方法返回类型要求以及 OSC 提供程序扩展 DLL 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fff97-113">[Technical Requirements](technical-requirements.md): Describes the supported programming languages, COM visibility requirements, method return type requirements, and details of the OSC provider extensibility DLL.</span></span>
    
- <span data-ttu-id="fff97-114">[开发提供程序的](best-practices-for-developing-a-provider.md)最佳实践：提供开发 OSC 提供程序时要遵循的最佳实践列表。</span><span class="sxs-lookup"><span data-stu-id="fff97-114">[Best Practices for Developing a Provider](best-practices-for-developing-a-provider.md): Provides a list of best practices to follow while developing an OSC provider.</span></span>
    
## <a name="reference"></a><span data-ttu-id="fff97-115">参考</span><span class="sxs-lookup"><span data-stu-id="fff97-115">Reference</span></span>

- [<span data-ttu-id="fff97-116">OutlookSocial Connector Provider Reference</span><span class="sxs-lookup"><span data-stu-id="fff97-116">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="fff97-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="fff97-117">Related sections</span></span>

- [<span data-ttu-id="fff97-118">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="fff97-118">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="fff97-119">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="fff97-119">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="fff97-120">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="fff97-120">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="fff97-121">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="fff97-121">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="fff97-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="fff97-122">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="fff97-123">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="fff97-123">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="fff97-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fff97-124">See also</span></span>

- [<span data-ttu-id="fff97-125">Microsoft Outlook Social Connector 32 位</span><span class="sxs-lookup"><span data-stu-id="fff97-125">Microsoft Outlook Social Connector 32-bit</span></span>](https://www.microsoft.com/downloads/details.aspx?FamilyID=b638cc14-11e5-448a-b5a6-4f553ce81b94)
- [<span data-ttu-id="fff97-126">Outlook Social Connector (KB983403) ，32 位版本</span><span class="sxs-lookup"><span data-stu-id="fff97-126">Update for Outlook Social Connector (KB983403), 32-Bit Edition</span></span>](https://www.microsoft.com/downloads/details.aspx?FamilyID=9886faca-f1c5-4579-83e2-c872c7abc61a)
- [<span data-ttu-id="fff97-127">Outlook Social Connector (KB983403) ，64 位版本</span><span class="sxs-lookup"><span data-stu-id="fff97-127">Update for Outlook Social Connector (KB983403), 64-bit Edition</span></span>](https://www.microsoft.com/downloads/details.aspx?FamilyID=72a506a7-8a91-4d56-8b27-bf3b3f58fe9a)
- [<span data-ttu-id="fff97-128">OutlookSocial Connector 2013：提供程序模板</span><span class="sxs-lookup"><span data-stu-id="fff97-128">Outlook Social Connector 2013: Provider templates</span></span>](https://code.msdn.microsoft.com/Outlook-Social-Connector-73fd8d2c)

