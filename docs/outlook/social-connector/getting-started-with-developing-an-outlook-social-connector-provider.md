---
title: 开发 Outlook Social Connector 提供程序入门
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c65d2df-86a3-48d5-9fec-a9040f3b878c
description: Outlook Social Connector (.osc) Provider 参考介绍如何使用 .osc 提供程序可扩展性开发 .osc 提供程序。
ms.openlocfilehash: 24f8eabe33103f53e848f055b72fd402bc5dd89a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327158"
---
# <a name="getting-started-with-developing-an-outlook-social-connector-provider"></a><span data-ttu-id="386c6-103">开发 Outlook Social Connector 提供程序入门</span><span class="sxs-lookup"><span data-stu-id="386c6-103">Getting started with developing an Outlook Social Connector provider</span></span>

<span data-ttu-id="386c6-104">Outlook Social Connector (.osc) Provider 参考介绍如何使用 .osc 提供程序可扩展性开发 .osc 提供程序。</span><span class="sxs-lookup"><span data-stu-id="386c6-104">The Outlook Social Connector (OSC) Provider Reference describes how to develop an OSC provider by using OSC provider extensibility.</span></span> <span data-ttu-id="386c6-105">如果您不熟悉如何开发 outlook 解决方案, 请参阅[选择用于开发 outlook 解决方案的 api 或技术](https://msdn.microsoft.com/library/8295da20-e567-4d08-b8e4-5c9b4498edd4%28Office.15%29.aspx), 以确定最适合您需求的 api 和技术。</span><span class="sxs-lookup"><span data-stu-id="386c6-105">If you are new to developing solutions for Outlook, see [Selecting an API or Technology for Developing Outlook Solutions](https://msdn.microsoft.com/library/8295da20-e567-4d08-b8e4-5c9b4498edd4%28Office.15%29.aspx) to identify the APIs and technologies that are most appropriate for your needs.</span></span> 

<span data-ttu-id="386c6-106">本部分概述了 .osc、.osc 提供程序的有用程度、学习开发提供程序的快速步骤、技术要求、开发提供程序的最佳实践, 以及此版本中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="386c6-106">This section gives an overview of the OSC, how an OSC provider can be useful, quick steps for learning to develop a provider, technical requirements, best practices for developing a provider, and what's new in this release.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="386c6-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="386c6-107">In this section</span></span>

- <span data-ttu-id="386c6-108">[适用于提供程序的新增](what-s-new-for-providers.md)功能: 比较上一个和当前版本中的 .osc 功能, 并介绍在此版本中添加、更改或弃用的接口成员和 XML 架构元素。</span><span class="sxs-lookup"><span data-stu-id="386c6-108">[What's New for Providers](what-s-new-for-providers.md): Compares OSC features in the previous and current release, and describes interface members and XML schema elements that have been added, changed, or deprecated in this release.</span></span> 
    
- <span data-ttu-id="386c6-109">[为什么要开发 Outlook Social Connector 提供程序](why-develop-an-outlook-social-connector-provider.md): 介绍了 .osc 提供程序如何对常见的社交网络站点和其他内部网络工具有用。</span><span class="sxs-lookup"><span data-stu-id="386c6-109">[Why Develop an Outlook Social Connector Provider](why-develop-an-outlook-social-connector-provider.md): Describes how an OSC provider can be useful for common social network sites and other internal networking tools.</span></span>
    
- <span data-ttu-id="386c6-110">[将 .osc 与 Outlook 和社交网络关联](relating-the-osc-with-outlook-and-social-networks.md): 提供了有关 .osc 如何将 Outlook 用户与社交网络连接的体系结构视图。</span><span class="sxs-lookup"><span data-stu-id="386c6-110">[Relating the OSC with Outlook and Social Networks](relating-the-osc-with-outlook-and-social-networks.md): Provides an architectural view of how the OSC connects Outlook users with social networks.</span></span> <span data-ttu-id="386c6-111">还定义了常见术语, 如 "社交网络"、"好友"、"非好友" 和 "联系人" 在本参考的其余部分中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="386c6-111">Also defines the way that common terms, like "social networks," "friends," "non-friends," and "contacts" are used in the rest of this reference.</span></span>
    
- <span data-ttu-id="386c6-112">[学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md): 提供开发 .osc 提供程序所要学习的步骤的摘要。</span><span class="sxs-lookup"><span data-stu-id="386c6-112">[Quick Steps for Learning to Develop a Provider](quick-steps-for-learning-to-develop-a-provider.md): Provides a summary of steps to learn to develop an OSC provider.</span></span>
    
- <span data-ttu-id="386c6-113">[技术要求](technical-requirements.md): 介绍了受支持的编程语言、COM 可见性要求、方法返回类型要求以及 .osc 提供程序扩展性 DLL 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="386c6-113">[Technical Requirements](technical-requirements.md): Describes the supported programming languages, COM visibility requirements, method return type requirements, and details of the OSC provider extensibility DLL.</span></span>
    
- <span data-ttu-id="386c6-114">[开发提供程序的最佳实践](best-practices-for-developing-a-provider.md): 提供在开发 .osc 提供程序时要遵循的最佳实践列表。</span><span class="sxs-lookup"><span data-stu-id="386c6-114">[Best Practices for Developing a Provider](best-practices-for-developing-a-provider.md): Provides a list of best practices to follow while developing an OSC provider.</span></span>
    
## <a name="reference"></a><span data-ttu-id="386c6-115">参考</span><span class="sxs-lookup"><span data-stu-id="386c6-115">Reference</span></span>

- [<span data-ttu-id="386c6-116">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="386c6-116">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="386c6-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="386c6-117">Related sections</span></span>

- [<span data-ttu-id="386c6-118">.osc 示例模板</span><span class="sxs-lookup"><span data-stu-id="386c6-118">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="386c6-119">.osc 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="386c6-119">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="386c6-120">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="386c6-120">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="386c6-121">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="386c6-121">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="386c6-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="386c6-122">Deploying a Provider</span></span>](deploying-a-provider.md)
  
- [<span data-ttu-id="386c6-123">准备发布一个 .osc 提供程序</span><span class="sxs-lookup"><span data-stu-id="386c6-123">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)
  
## <a name="see-also"></a><span data-ttu-id="386c6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="386c6-124">See also</span></span>

- [<span data-ttu-id="386c6-125">Microsoft Outlook Social Connector 32-bit</span><span class="sxs-lookup"><span data-stu-id="386c6-125">Microsoft Outlook Social Connector 32-bit</span></span>](https://www.microsoft.com/downloads/details.aspx?FamilyID=b638cc14-11e5-448a-b5a6-4f553ce81b94)
- [<span data-ttu-id="386c6-126">Outlook Social Connector (KB983403) 的更新, 32 位版本</span><span class="sxs-lookup"><span data-stu-id="386c6-126">Update for Outlook Social Connector (KB983403), 32-Bit Edition</span></span>](https://www.microsoft.com/downloads/details.aspx?FamilyID=9886faca-f1c5-4579-83e2-c872c7abc61a)
- [<span data-ttu-id="386c6-127">Outlook Social Connector (KB983403) 的更新, 64 位版本</span><span class="sxs-lookup"><span data-stu-id="386c6-127">Update for Outlook Social Connector (KB983403), 64-bit Edition</span></span>](https://www.microsoft.com/downloads/details.aspx?FamilyID=72a506a7-8a91-4d56-8b27-bf3b3f58fe9a)
- [<span data-ttu-id="386c6-128">Outlook Social Connector 2013: 提供程序模板</span><span class="sxs-lookup"><span data-stu-id="386c6-128">Outlook Social Connector 2013: Provider templates</span></span>](https://code.msdn.microsoft.com/Outlook-Social-Connector-73fd8d2c)

