---
title: 准备发布 OSC 提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a7d28349-3121-49ae-ad28-043789e2d205
description: 本节建议在 OSC Outlook 发布您的 Outlook 连接器 (测试) 测试。
ms.openlocfilehash: 8a36b13f8adc42a1834481d3a5942f0350c43cc3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414660"
---
# <a name="getting-ready-to-release-an-osc-provider"></a><span data-ttu-id="fdc30-103">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="fdc30-103">Getting ready to release an OSC provider</span></span>

<span data-ttu-id="fdc30-104">本节建议在 OSC Outlook 发布您的 Outlook 连接器 (测试) 测试。</span><span class="sxs-lookup"><span data-stu-id="fdc30-104">This section suggests tests you can do before you release your Outlook Social Connector (OSC) provider.</span></span> <span data-ttu-id="fdc30-105">你可以开始引用本节中的主题，在开发和测试阶段执行其中一些测试，但应在发布时完成这些测试。</span><span class="sxs-lookup"><span data-stu-id="fdc30-105">You can start referring to the topics in this section and carry out some of these tests during your development and testing phases, but you should have completed these tests by the time you release.</span></span> 

<span data-ttu-id="fdc30-106">这些测试验证 OSC 提供程序接口实现的基本功能与为 OSC 提供程序指定的功能有关。</span><span class="sxs-lookup"><span data-stu-id="fdc30-106">These tests verify the basic functionality of your implementation of the OSC provider interfaces with respect to the capabilities you specify for the OSC provider.</span></span> <span data-ttu-id="fdc30-107">此外，即使 OSC 是由多个 Office 应用程序共享的功能，这些测试Outlook客户端来测试基本功能。</span><span class="sxs-lookup"><span data-stu-id="fdc30-107">Also, even though the OSC is a feature shared by multiple Office client applications, these tests use Outlook as the client to test the fundamental functionality.</span></span> <span data-ttu-id="fdc30-108">应确定特定于提供程序的功能是否需要其他测试。</span><span class="sxs-lookup"><span data-stu-id="fdc30-108">You should determine whether other tests are necessary for features specific to your provider.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="fdc30-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="fdc30-109">In this section</span></span>

- <span data-ttu-id="fdc30-110">[测试部署](testing-deployment.md)：介绍应测试的与安装和卸载 OSC 提供程序有关的方案。</span><span class="sxs-lookup"><span data-stu-id="fdc30-110">[Testing Deployment](testing-deployment.md): Describes scenarios you should test for around installing and uninstalling an OSC provider.</span></span>
    
- <span data-ttu-id="fdc30-111">[测试功能、身份验证和配置](testing-capabilities-authentication-and-configuration.md)：介绍用于获取功能和有关为社交网络配置帐户和验证用户的方案的测试。</span><span class="sxs-lookup"><span data-stu-id="fdc30-111">[Testing Capabilities, Authentication, and Configuration](testing-capabilities-authentication-and-configuration.md): Describes tests for getting capabilities, and scenarios around configuring an account and authenticating a user for a social network.</span></span>
    
- <span data-ttu-id="fdc30-112">[Testing Following and Stop-Following Person](testing-following-and-stop-following-persons.md)： Describes scenarios to test the OSC provider's ability to add a person as a friend， or to remove a friend from the social network.</span><span class="sxs-lookup"><span data-stu-id="fdc30-112">[Testing Following and Stop-Following Persons](testing-following-and-stop-following-persons.md): Describes scenarios to test the OSC provider's ability to add a person as a friend, or to remove a friend from the social network.</span></span> 
    
- <span data-ttu-id="fdc30-113">[测试好友](testing-friends.md)：介绍用于验证 OSC 提供程序是否适当返回好友和非好友的数据的测试和方案（如果适用，具体取决于提供程序支持的同步模式）。</span><span class="sxs-lookup"><span data-stu-id="fdc30-113">[Testing Friends](testing-friends.md): Describes tests and scenarios to verify that the OSC provider appropriately returns data of friends and non-friends, where applicable, depending on the synchronization mode that the provider supports.</span></span>
    
- <span data-ttu-id="fdc30-114">[测试活动](testing-activities.md)：描述用于验证 OSC 提供程序是否适当返回好友和非好友的活动（如果适用，具体取决于提供程序支持的同步模式）的测试和方案。</span><span class="sxs-lookup"><span data-stu-id="fdc30-114">[Testing Activities](testing-activities.md): Describes tests and scenarios to verify that the OSC provider appropriately returns activities of friends and non-friends, where applicable, depending on the synchronization mode that the provider supports.</span></span>
    
## <a name="reference"></a><span data-ttu-id="fdc30-115">参考</span><span class="sxs-lookup"><span data-stu-id="fdc30-115">Reference</span></span>

- [<span data-ttu-id="fdc30-116">OutlookSocial Connector Provider Reference</span><span class="sxs-lookup"><span data-stu-id="fdc30-116">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="fdc30-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="fdc30-117">Related sections</span></span>

- [<span data-ttu-id="fdc30-118">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="fdc30-118">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="fdc30-119">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="fdc30-119">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="fdc30-120">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="fdc30-120">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="fdc30-121">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="fdc30-121">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="fdc30-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="fdc30-122">Deploying a Provider</span></span>](deploying-a-provider.md)
  

