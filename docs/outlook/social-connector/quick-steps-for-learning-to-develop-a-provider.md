---
title: 快速学习开发提供程序的步骤
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 13c0ae8c-d268-4bf0-942d-2a6160142f5e
description: 本主题提供了几个步骤，若要了解有关开发 Outlook Social Connector (OSC) 提供程序。
ms.openlocfilehash: 345e8600c704504be091ee23c66b7f85575cde90
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779327"
---
# <a name="quick-steps-for-learning-to-develop-a-provider"></a><span data-ttu-id="3af07-103">快速学习开发提供程序的步骤</span><span class="sxs-lookup"><span data-stu-id="3af07-103">Quick steps for learning to develop a provider</span></span>

<span data-ttu-id="3af07-104">若要开发 OSC 提供程序，您需要完成以下一般步骤：</span><span class="sxs-lookup"><span data-stu-id="3af07-104">To develop an OSC provider, you need to complete the following general steps:</span></span>
  
- <span data-ttu-id="3af07-105">实现四个强制接口： [ISocialProvider](isocialprovideriunknown.md)、 [ISocialSession](isocialsessioniunknown.md)、 [ISocialProfile](isocialprofileisocialperson.md)和[ISocialPerson](isocialpersoniunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="3af07-105">Implement the four mandatory interfaces: [ISocialProvider](isocialprovideriunknown.md), [ISocialSession](isocialsessioniunknown.md), [ISocialProfile](isocialprofileisocialperson.md), and [ISocialPerson](isocialpersoniunknown.md).</span></span> <span data-ttu-id="3af07-106">根据您的社交网络支持缓存社交网络中，或动态同步朋友和其活动，关注人员的登录凭据，您可能想要实现[ISocialSession2](isocialsession2iunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="3af07-106">Depending on your social network's support for caching logon credentials, following a person on the social network, or dynamically synchronizing friends and their activities, you might want to implement the [ISocialSession2](isocialsession2iunknown.md) interface.</span></span> 
    
- <span data-ttu-id="3af07-107">在实现接口的同时，测试和调试 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="3af07-107">In parallel with implementing interfaces, test and debug the OSC provider.</span></span> 

- <span data-ttu-id="3af07-108">部署 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="3af07-108">Deploy the OSC provider.</span></span>  

- <span data-ttu-id="3af07-109">执行操作之前版本的最终测试。</span><span class="sxs-lookup"><span data-stu-id="3af07-109">Do final testing before release.</span></span>
    
## <a name="step-a-implementing-interfaces"></a><span data-ttu-id="3af07-110">步骤答： 实现接口</span><span class="sxs-lookup"><span data-stu-id="3af07-110">Step A: Implementing interfaces</span></span>

<span data-ttu-id="3af07-111">OSC 提供程序实现接口，以便 OSC 可以使用这些接口以获取有关或从社交网络中，通过 OSC 提供程序所需的信息。</span><span class="sxs-lookup"><span data-stu-id="3af07-111">An OSC provider implements interfaces so that the OSC can use these interfaces to obtain necessary information about or from the social network, through the OSC provider.</span></span> <span data-ttu-id="3af07-112">此类信息包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="3af07-112">Such information includes the following:</span></span>
  
- <span data-ttu-id="3af07-113">如何向用户显示帐户登录对话框。</span><span class="sxs-lookup"><span data-stu-id="3af07-113">How to present the account logon dialog to a user.</span></span>    
- <span data-ttu-id="3af07-114">是否提供程序支持显示朋友或活动显示社交网络上。</span><span class="sxs-lookup"><span data-stu-id="3af07-114">Whether the provider supports showing friends or activities as displayed on the social network.</span></span>    
- <span data-ttu-id="3af07-115">如何在联系人卡片或 Outlook 人员窗格中显示朋友和活动。</span><span class="sxs-lookup"><span data-stu-id="3af07-115">How to display friends and activities in the Contact Card or Outlook People Pane.</span></span>     
- <span data-ttu-id="3af07-116">何时刷新朋友或活动信息的联系人卡片或人员窗格。</span><span class="sxs-lookup"><span data-stu-id="3af07-116">When to refresh friends or activities information on the Contact Card or People Pane.</span></span>
    
<span data-ttu-id="3af07-117">信息通常传递从提供程序给 OSC，作为接口方法的输出参数的 XML 字符串的形式。</span><span class="sxs-lookup"><span data-stu-id="3af07-117">The information is typically passed from the provider to the OSC, in the form of XML strings as output parameters of interface methods.</span></span> <span data-ttu-id="3af07-118">OSC 和 OSC 提供程序符合 OSC 提供程序的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="3af07-118">Both the OSC and an OSC provider comply with the OSC provider XML schema.</span></span> <span data-ttu-id="3af07-119">因此，在过程中实现的接口，您需要的 XML 架构如何允许您指定的信息，如上面列出更好地理解。</span><span class="sxs-lookup"><span data-stu-id="3af07-119">Therefore, in the course of implementing the interfaces, you need a good understanding of how the XML schema allows you to specify information as listed above.</span></span> 

<span data-ttu-id="3af07-120">以下资源介绍如何指定提供程序功能、 朋友和活动的 XML:</span><span class="sxs-lookup"><span data-stu-id="3af07-120">The following resources explain how to specify XML for provider capabilities, friends, and activities:</span></span>
  
- [<span data-ttu-id="3af07-121">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="3af07-121">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)    
- [<span data-ttu-id="3af07-122">同步朋友和活动</span><span class="sxs-lookup"><span data-stu-id="3af07-122">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)    
- [<span data-ttu-id="3af07-123">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="3af07-123">Capabilities XML Example</span></span>](capabilities-xml-example.md)   
- [<span data-ttu-id="3af07-124">功能 XML</span><span class="sxs-lookup"><span data-stu-id="3af07-124">XML for Capabilities</span></span>](xml-for-capabilities.md)    
- [<span data-ttu-id="3af07-125">朋友 XML 示例</span><span class="sxs-lookup"><span data-stu-id="3af07-125">Friends XML Example</span></span>](friends-xml-example.md)    
- [<span data-ttu-id="3af07-126">朋友 XML</span><span class="sxs-lookup"><span data-stu-id="3af07-126">XML for Friends</span></span>](xml-for-friends.md)   
- [<span data-ttu-id="3af07-127">活动源的 XML 示例</span><span class="sxs-lookup"><span data-stu-id="3af07-127">Activity Feed XML Example</span></span>](activity-feed-xml-example.md)   
- [<span data-ttu-id="3af07-128">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="3af07-128">XML for Activities</span></span>](xml-for-activities.md)
    
<span data-ttu-id="3af07-129">开始实施之前，还请参考以下主题以节省时间更高版本中调试过程：</span><span class="sxs-lookup"><span data-stu-id="3af07-129">Before you start implementation, also consult the following topics to save you time later in the debugging process:</span></span>
  
- [<span data-ttu-id="3af07-130">技术要求</span><span class="sxs-lookup"><span data-stu-id="3af07-130">Technical Requirements</span></span>](technical-requirements.md)    
- [<span data-ttu-id="3af07-131">开发提供程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="3af07-131">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)    
- [<span data-ttu-id="3af07-132">OSC 示例模板</span><span class="sxs-lookup"><span data-stu-id="3af07-132">OSC Sample Templates</span></span>](osc-sample-templates.md)
    
## <a name="step-b-debugging"></a><span data-ttu-id="3af07-133">步骤 b： 调试</span><span class="sxs-lookup"><span data-stu-id="3af07-133">Step B: Debugging</span></span>

<span data-ttu-id="3af07-134">主题[调试提供程序](debugging-a-provider.md)建议调试开发 OSC 提供程序时，可以使用的过程。</span><span class="sxs-lookup"><span data-stu-id="3af07-134">The topic [Debugging a Provider](debugging-a-provider.md) suggests debugging procedures you can use while developing an OSC provider.</span></span> 
  
<span data-ttu-id="3af07-135">时要开发，您还可以参考[获取准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)获得更好地了解在某些方案 （例如，基本和基于表单的身份验证） 的预期行为。</span><span class="sxs-lookup"><span data-stu-id="3af07-135">While you are developing, you can also refer to [Getting Ready to Release an OSC Provider](getting-ready-to-release-an-osc-provider.md) to gain a better understanding of the expected behavior in certain scenarios (for example, basic and forms-based authentication).</span></span> 
  
## <a name="step-c-deploying"></a><span data-ttu-id="3af07-136">步骤 c： 部署</span><span class="sxs-lookup"><span data-stu-id="3af07-136">Step C: Deploying</span></span>

<span data-ttu-id="3af07-137">请参阅以下主题以了解如何部署要求：</span><span class="sxs-lookup"><span data-stu-id="3af07-137">See the following topics to learn about deployment requirements:</span></span>
  
- [<span data-ttu-id="3af07-138">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="3af07-138">Deploying a Provider</span></span>](deploying-a-provider.md)    
- [<span data-ttu-id="3af07-139">注册提供程序</span><span class="sxs-lookup"><span data-stu-id="3af07-139">Registering a Provider</span></span>](registering-a-provider.md)   
- [<span data-ttu-id="3af07-140">安装清单</span><span class="sxs-lookup"><span data-stu-id="3af07-140">Installation Checklist</span></span>](installation-checklist.md)
    
## <a name="step-d-final-testing-before-release"></a><span data-ttu-id="3af07-141">步骤 d： 最终版本之前测试</span><span class="sxs-lookup"><span data-stu-id="3af07-141">Step D: Final testing before release</span></span>

<span data-ttu-id="3af07-142">根据您的社交网络和 OSC 提供程序，有通常特定于提供程序测试释放您的提供商之前应执行。</span><span class="sxs-lookup"><span data-stu-id="3af07-142">Depending on your social network and the OSC provider, there are usually provider-specific tests you should carry out before you release your provider.</span></span> <span data-ttu-id="3af07-143">测试的建议列表，请参阅[入门准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="3af07-143">For a suggested list of tests, see [Getting Ready to Release an OSC Provider](getting-ready-to-release-an-osc-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3af07-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3af07-144">See also</span></span>

- [<span data-ttu-id="3af07-145">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="3af07-145">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

