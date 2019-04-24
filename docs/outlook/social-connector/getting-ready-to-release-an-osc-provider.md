---
title: 准备发布一个 .osc 提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a7d28349-3121-49ae-ad28-043789e2d205
description: 本节建议您在发布 Outlook Social Connector (.osc) 提供程序之前可以执行的测试。
ms.openlocfilehash: 8a36b13f8adc42a1834481d3a5942f0350c43cc3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327151"
---
# <a name="getting-ready-to-release-an-osc-provider"></a><span data-ttu-id="fbfa1-103">准备发布一个 .osc 提供程序</span><span class="sxs-lookup"><span data-stu-id="fbfa1-103">Getting ready to release an OSC provider</span></span>

<span data-ttu-id="fbfa1-104">本节建议您在发布 Outlook Social Connector (.osc) 提供程序之前可以执行的测试。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-104">This section suggests tests you can do before you release your Outlook Social Connector (OSC) provider.</span></span> <span data-ttu-id="fbfa1-105">您可以开始参考本节中的主题, 并在开发和测试阶段中执行这些测试中的部分测试, 但您在释放这些测试时应完成这些测试。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-105">You can start referring to the topics in this section and carry out some of these tests during your development and testing phases, but you should have completed these tests by the time you release.</span></span> 

<span data-ttu-id="fbfa1-106">这些测试将根据您为 .osc 提供程序指定的功能验证您的 .osc 提供程序接口实现的基本功能。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-106">These tests verify the basic functionality of your implementation of the OSC provider interfaces with respect to the capabilities you specify for the OSC provider.</span></span> <span data-ttu-id="fbfa1-107">此外, 尽管 .osc 是由多个 Office 客户端应用程序共享的功能, 但这些测试使用 Outlook 作为客户端来测试基本功能。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-107">Also, even though the OSC is a feature shared by multiple Office client applications, these tests use Outlook as the client to test the fundamental functionality.</span></span> <span data-ttu-id="fbfa1-108">您应确定特定于您的提供程序的功能是否需要其他测试。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-108">You should determine whether other tests are necessary for features specific to your provider.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="fbfa1-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="fbfa1-109">In this section</span></span>

- <span data-ttu-id="fbfa1-110">[测试部署](testing-deployment.md): 介绍在安装和卸载 .osc 提供程序方面应测试的方案。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-110">[Testing Deployment](testing-deployment.md): Describes scenarios you should test for around installing and uninstalling an OSC provider.</span></span>
    
- <span data-ttu-id="fbfa1-111">[测试功能、身份验证和配置](testing-capabilities-authentication-and-configuration.md): 介绍了用于获取功能的测试, 以及有关配置帐户和对社交网络的用户进行身份验证的方案。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-111">[Testing Capabilities, Authentication, and Configuration](testing-capabilities-authentication-and-configuration.md): Describes tests for getting capabilities, and scenarios around configuring an account and authenticating a user for a social network.</span></span>
    
- <span data-ttu-id="fbfa1-112">[测试关注和停止关注的人员](testing-following-and-stop-following-persons.md): 介绍用于测试 .osc 提供程序将人员添加为朋友的能力或从社交网络中删除好友的方案。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-112">[Testing Following and Stop-Following Persons](testing-following-and-stop-following-persons.md): Describes scenarios to test the OSC provider's ability to add a person as a friend, or to remove a friend from the social network.</span></span> 
    
- <span data-ttu-id="fbfa1-113">[测试朋友](testing-friends.md): 介绍了测试和方案, 以验证 .osc 提供程序是否根据提供程序所支持的同步模式, 适当地返回朋友和非好友的数据 (如果适用)。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-113">[Testing Friends](testing-friends.md): Describes tests and scenarios to verify that the OSC provider appropriately returns data of friends and non-friends, where applicable, depending on the synchronization mode that the provider supports.</span></span>
    
- <span data-ttu-id="fbfa1-114">[测试活动](testing-activities.md): 介绍了测试和方案, 以验证 .osc 提供程序是否根据提供程序支持的同步模式, 适当地返回朋友和非朋友的活动 (如果适用)。</span><span class="sxs-lookup"><span data-stu-id="fbfa1-114">[Testing Activities](testing-activities.md): Describes tests and scenarios to verify that the OSC provider appropriately returns activities of friends and non-friends, where applicable, depending on the synchronization mode that the provider supports.</span></span>
    
## <a name="reference"></a><span data-ttu-id="fbfa1-115">参考</span><span class="sxs-lookup"><span data-stu-id="fbfa1-115">Reference</span></span>

- [<span data-ttu-id="fbfa1-116">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="fbfa1-116">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="fbfa1-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="fbfa1-117">Related sections</span></span>

- [<span data-ttu-id="fbfa1-118">.osc 示例模板</span><span class="sxs-lookup"><span data-stu-id="fbfa1-118">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="fbfa1-119">.osc 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="fbfa1-119">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="fbfa1-120">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="fbfa1-120">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="fbfa1-121">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="fbfa1-121">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="fbfa1-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="fbfa1-122">Deploying a Provider</span></span>](deploying-a-provider.md)
  

