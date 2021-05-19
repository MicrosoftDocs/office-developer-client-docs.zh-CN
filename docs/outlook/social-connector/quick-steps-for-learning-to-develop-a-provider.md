---
title: 学习开发提供程序的快速步骤
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 13c0ae8c-d268-4bf0-942d-2a6160142f5e
description: 本主题推荐了几个步骤，以了解如何在 OSC Outlook提供程序 (社交) 连接器。
ms.openlocfilehash: 581997ab257d59062761d97bfef49a88b90bb1e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424215"
---
# <a name="quick-steps-for-learning-to-develop-a-provider"></a><span data-ttu-id="48d33-103">学习开发提供程序的快速步骤</span><span class="sxs-lookup"><span data-stu-id="48d33-103">Quick steps for learning to develop a provider</span></span>

<span data-ttu-id="48d33-104">若要开发 OSC 提供程序，您需要完成以下常规步骤：</span><span class="sxs-lookup"><span data-stu-id="48d33-104">To develop an OSC provider, you need to complete the following general steps:</span></span>
  
- <span data-ttu-id="48d33-105">实现四个强制接口：ISocialProvider、ISocialSession、ISocialProfile 和[ISocialPerson。](isocialpersoniunknown.md) [](isocialprovideriunknown.md) [](isocialsessioniunknown.md) [](isocialprofileisocialperson.md)</span><span class="sxs-lookup"><span data-stu-id="48d33-105">Implement the four mandatory interfaces: [ISocialProvider](isocialprovideriunknown.md), [ISocialSession](isocialsessioniunknown.md), [ISocialProfile](isocialprofileisocialperson.md), and [ISocialPerson](isocialpersoniunknown.md).</span></span> <span data-ttu-id="48d33-106">根据社交网络对缓存登录凭据、跟踪社交网络上的人员或动态同步好友及其活动的支持，您可能需要实现 [ISocialSession2](isocialsession2iunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="48d33-106">Depending on your social network's support for caching logon credentials, following a person on the social network, or dynamically synchronizing friends and their activities, you might want to implement the [ISocialSession2](isocialsession2iunknown.md) interface.</span></span> 
    
- <span data-ttu-id="48d33-107">与实现接口并行，测试和调试 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="48d33-107">In parallel with implementing interfaces, test and debug the OSC provider.</span></span> 

- <span data-ttu-id="48d33-108">部署 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="48d33-108">Deploy the OSC provider.</span></span>  

- <span data-ttu-id="48d33-109">在发布前执行最终测试。</span><span class="sxs-lookup"><span data-stu-id="48d33-109">Do final testing before release.</span></span>
    
## <a name="step-a-implementing-interfaces"></a><span data-ttu-id="48d33-110">步骤 A：实现接口</span><span class="sxs-lookup"><span data-stu-id="48d33-110">Step A: Implementing interfaces</span></span>

<span data-ttu-id="48d33-111">OSC 提供程序实现接口，以便 OSC 可以通过 OSC 提供程序使用这些接口获取有关社交网络或从社交网络获取必要信息。</span><span class="sxs-lookup"><span data-stu-id="48d33-111">An OSC provider implements interfaces so that the OSC can use these interfaces to obtain necessary information about or from the social network, through the OSC provider.</span></span> <span data-ttu-id="48d33-112">这些信息包括：</span><span class="sxs-lookup"><span data-stu-id="48d33-112">Such information includes the following:</span></span>
  
- <span data-ttu-id="48d33-113">如何向用户显示帐户登录对话框。</span><span class="sxs-lookup"><span data-stu-id="48d33-113">How to present the account logon dialog to a user.</span></span>    
- <span data-ttu-id="48d33-114">提供程序是否支持在社交网络上显示好友或活动。</span><span class="sxs-lookup"><span data-stu-id="48d33-114">Whether the provider supports showing friends or activities as displayed on the social network.</span></span>    
- <span data-ttu-id="48d33-115">如何在联系人卡片或联系人窗格中显示好友Outlook活动。</span><span class="sxs-lookup"><span data-stu-id="48d33-115">How to display friends and activities in the Contact Card or Outlook People Pane.</span></span>     
- <span data-ttu-id="48d33-116">何时刷新联系人卡片或人员窗格上的好友或活动信息。</span><span class="sxs-lookup"><span data-stu-id="48d33-116">When to refresh friends or activities information on the Contact Card or People Pane.</span></span>
    
<span data-ttu-id="48d33-117">该信息通常以 XML 字符串形式作为接口方法的输出参数从提供程序传递到 OSC。</span><span class="sxs-lookup"><span data-stu-id="48d33-117">The information is typically passed from the provider to the OSC, in the form of XML strings as output parameters of interface methods.</span></span> <span data-ttu-id="48d33-118">OSC 和 OSC 提供程序均符合 OSC 提供程序 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="48d33-118">Both the OSC and an OSC provider comply with the OSC provider XML schema.</span></span> <span data-ttu-id="48d33-119">因此，在实施接口的过程中，您需要深入了解 XML 架构如何允许您指定上面列出的信息。</span><span class="sxs-lookup"><span data-stu-id="48d33-119">Therefore, in the course of implementing the interfaces, you need a good understanding of how the XML schema allows you to specify information as listed above.</span></span> 

<span data-ttu-id="48d33-120">以下资源说明如何为提供程序功能、好友和活动指定 XML：</span><span class="sxs-lookup"><span data-stu-id="48d33-120">The following resources explain how to specify XML for provider capabilities, friends, and activities:</span></span>
  
- [<span data-ttu-id="48d33-121">OSC 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="48d33-121">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)    
- [<span data-ttu-id="48d33-122">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="48d33-122">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)    
- [<span data-ttu-id="48d33-123">Capabilities XML 示例</span><span class="sxs-lookup"><span data-stu-id="48d33-123">Capabilities XML Example</span></span>](capabilities-xml-example.md)   
- [<span data-ttu-id="48d33-124">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="48d33-124">XML for Capabilities</span></span>](xml-for-capabilities.md)    
- [<span data-ttu-id="48d33-125">好友 XML 示例</span><span class="sxs-lookup"><span data-stu-id="48d33-125">Friends XML Example</span></span>](friends-xml-example.md)    
- [<span data-ttu-id="48d33-126">好友 XML</span><span class="sxs-lookup"><span data-stu-id="48d33-126">XML for Friends</span></span>](xml-for-friends.md)   
- [<span data-ttu-id="48d33-127">活动源 XML 示例</span><span class="sxs-lookup"><span data-stu-id="48d33-127">Activity Feed XML Example</span></span>](activity-feed-xml-example.md)   
- [<span data-ttu-id="48d33-128">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="48d33-128">XML for Activities</span></span>](xml-for-activities.md)
    
<span data-ttu-id="48d33-129">在开始实现之前，还请查阅以下主题，以便以后在调试过程中节省时间：</span><span class="sxs-lookup"><span data-stu-id="48d33-129">Before you start implementation, also consult the following topics to save you time later in the debugging process:</span></span>
  
- [<span data-ttu-id="48d33-130">技术要求</span><span class="sxs-lookup"><span data-stu-id="48d33-130">Technical Requirements</span></span>](technical-requirements.md)    
- [<span data-ttu-id="48d33-131">开发提供程序的最佳实践</span><span class="sxs-lookup"><span data-stu-id="48d33-131">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)    
- [<span data-ttu-id="48d33-132">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="48d33-132">OSC Sample Templates</span></span>](osc-sample-templates.md)
    
## <a name="step-b-debugging"></a><span data-ttu-id="48d33-133">步骤 B：调试</span><span class="sxs-lookup"><span data-stu-id="48d33-133">Step B: Debugging</span></span>

<span data-ttu-id="48d33-134">调试 [提供程序主题](debugging-a-provider.md) 建议了在开发 OSC 提供程序时可以使用的调试过程。</span><span class="sxs-lookup"><span data-stu-id="48d33-134">The topic [Debugging a Provider](debugging-a-provider.md) suggests debugging procedures you can use while developing an OSC provider.</span></span> 
  
<span data-ttu-id="48d33-135">在开发时，还可以参阅准备发布 [OSC](getting-ready-to-release-an-osc-provider.md) 提供程序，以更好地了解在某些情况下的预期行为 (例如基本身份验证和基于表单的身份验证) 。</span><span class="sxs-lookup"><span data-stu-id="48d33-135">While you are developing, you can also refer to [Getting Ready to Release an OSC Provider](getting-ready-to-release-an-osc-provider.md) to gain a better understanding of the expected behavior in certain scenarios (for example, basic and forms-based authentication).</span></span> 
  
## <a name="step-c-deploying"></a><span data-ttu-id="48d33-136">步骤 C：部署</span><span class="sxs-lookup"><span data-stu-id="48d33-136">Step C: Deploying</span></span>

<span data-ttu-id="48d33-137">请参阅以下主题以了解部署要求：</span><span class="sxs-lookup"><span data-stu-id="48d33-137">See the following topics to learn about deployment requirements:</span></span>
  
- [<span data-ttu-id="48d33-138">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="48d33-138">Deploying a Provider</span></span>](deploying-a-provider.md)    
- [<span data-ttu-id="48d33-139">注册提供程序</span><span class="sxs-lookup"><span data-stu-id="48d33-139">Registering a Provider</span></span>](registering-a-provider.md)   
- [<span data-ttu-id="48d33-140">安装清单</span><span class="sxs-lookup"><span data-stu-id="48d33-140">Installation Checklist</span></span>](installation-checklist.md)
    
## <a name="step-d-final-testing-before-release"></a><span data-ttu-id="48d33-141">步骤 D：发布前的最终测试</span><span class="sxs-lookup"><span data-stu-id="48d33-141">Step D: Final testing before release</span></span>

<span data-ttu-id="48d33-142">根据社交网络和 OSC 提供程序，在发布提供程序之前，通常应执行特定于提供程序的测试。</span><span class="sxs-lookup"><span data-stu-id="48d33-142">Depending on your social network and the OSC provider, there are usually provider-specific tests you should carry out before you release your provider.</span></span> <span data-ttu-id="48d33-143">有关建议的测试列表，请参阅准备发布 [OSC 提供程序](getting-ready-to-release-an-osc-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="48d33-143">For a suggested list of tests, see [Getting Ready to Release an OSC Provider](getting-ready-to-release-an-osc-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="48d33-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48d33-144">See also</span></span>

- [<span data-ttu-id="48d33-145">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="48d33-145">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

