---
title: 准备发布 OSC 提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a7d28349-3121-49ae-ad28-043789e2d205
description: 本节提供了建议之前您发布您的 Outlook Social Connector (OSC) 提供程序时，可以执行操作的测试。
ms.openlocfilehash: 5caf4144a8daed31d30c9ecbcf9cf21c2300ed8f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779207"
---
# <a name="getting-ready-to-release-an-osc-provider"></a><span data-ttu-id="f99e0-103">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="f99e0-103">Getting ready to release an OSC provider</span></span>

<span data-ttu-id="f99e0-104">本节提供了建议之前您发布您的 Outlook Social Connector (OSC) 提供程序时，可以执行操作的测试。</span><span class="sxs-lookup"><span data-stu-id="f99e0-104">This section suggests tests you can do before you release your Outlook Social Connector (OSC) provider.</span></span> <span data-ttu-id="f99e0-105">您可以启动引用此部分中的主题和执行一些这些测试您的开发和测试阶段，但您应该已经完成这些测试由释放的时间。</span><span class="sxs-lookup"><span data-stu-id="f99e0-105">You can start referring to the topics in this section and carry out some of these tests during your development and testing phases, but you should have completed these tests by the time you release.</span></span> 

<span data-ttu-id="f99e0-106">这些测试验证的相对于 OSC 提供程序指定的功能的 OSC 提供程序接口实现的基本功能。</span><span class="sxs-lookup"><span data-stu-id="f99e0-106">These tests verify the basic functionality of your implementation of the OSC provider interfaces with respect to the capabilities you specify for the OSC provider.</span></span> <span data-ttu-id="f99e0-107">此外，即使 OSC 是由多个 Office 客户端应用程序共享功能，这些测试用作 Outlook 客户端测试的基本功能。</span><span class="sxs-lookup"><span data-stu-id="f99e0-107">Also, even though the OSC is a feature shared by multiple Office client applications, these tests use Outlook as the client to test the fundamental functionality.</span></span> <span data-ttu-id="f99e0-108">您应该确定是否其他测试所需的特定功能为您提供程序。</span><span class="sxs-lookup"><span data-stu-id="f99e0-108">You should determine whether other tests are necessary for features specific to your provider.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f99e0-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="f99e0-109">In this section</span></span>

- <span data-ttu-id="f99e0-110">[测试部署](testing-deployment.md)： 介绍了您应测试解决安装和卸载 OSC 提供程序的方案。</span><span class="sxs-lookup"><span data-stu-id="f99e0-110">[Testing Deployment](testing-deployment.md): Describes scenarios you should test for around installing and uninstalling an OSC provider.</span></span>
    
- <span data-ttu-id="f99e0-111">[测试功能，Authentication，and 配置](testing-capabilities-authentication-and-configuration.md)： 描述用于获取功能，并配置帐户和验证社交网络的用户设置的方案的测试。</span><span class="sxs-lookup"><span data-stu-id="f99e0-111">[Testing Capabilities, Authentication, and Configuration](testing-capabilities-authentication-and-configuration.md): Describes tests for getting capabilities, and scenarios around configuring an account and authenticating a user for a social network.</span></span>
    
- <span data-ttu-id="f99e0-112">[以下测试和停止关注人员](testing-following-and-stop-following-persons.md)： 介绍了用于测试 OSC 提供程序的功能为朋友，添加一个人或朋友删除社交网络方案。</span><span class="sxs-lookup"><span data-stu-id="f99e0-112">[Testing Following and Stop-Following Persons](testing-following-and-stop-following-persons.md): Describes scenarios to test the OSC provider's ability to add a person as a friend, or to remove a friend from the social network.</span></span> 
    
- <span data-ttu-id="f99e0-113">[测试朋友](testing-friends.md)： 描述测试和验证 OSC 提供程序适当地返回数据的朋友和非朋友，如果适用，具体取决于提供程序支持的同步模式的方案。</span><span class="sxs-lookup"><span data-stu-id="f99e0-113">[Testing Friends](testing-friends.md): Describes tests and scenarios to verify that the OSC provider appropriately returns data of friends and non-friends, where applicable, depending on the synchronization mode that the provider supports.</span></span>
    
- <span data-ttu-id="f99e0-114">[测试活动](testing-activities.md)： 描述测试和验证 OSC 提供程序适当地返回朋友和非朋友活动，如果适用，具体取决于提供程序支持的同步模式的方案。</span><span class="sxs-lookup"><span data-stu-id="f99e0-114">[Testing Activities](testing-activities.md): Describes tests and scenarios to verify that the OSC provider appropriately returns activities of friends and non-friends, where applicable, depending on the synchronization mode that the provider supports.</span></span>
    
## <a name="reference"></a><span data-ttu-id="f99e0-115">参考</span><span class="sxs-lookup"><span data-stu-id="f99e0-115">Reference</span></span>

- [<span data-ttu-id="f99e0-116">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="f99e0-116">Outlook Social Connector Provider Reference</span></span>](outlook-social-connector-provider-reference-0.md)
  
## <a name="related-sections"></a><span data-ttu-id="f99e0-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="f99e0-117">Related sections</span></span>

- [<span data-ttu-id="f99e0-118">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="f99e0-118">OSC Sample Templates</span></span>](osc-sample-templates.md)
  
- [<span data-ttu-id="f99e0-119">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="f99e0-119">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)
  
- [<span data-ttu-id="f99e0-120">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="f99e0-120">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)
  
- [<span data-ttu-id="f99e0-121">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="f99e0-121">Debugging a Provider</span></span>](debugging-a-provider.md)
  
- [<span data-ttu-id="f99e0-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="f99e0-122">Deploying a Provider</span></span>](deploying-a-provider.md)
  

