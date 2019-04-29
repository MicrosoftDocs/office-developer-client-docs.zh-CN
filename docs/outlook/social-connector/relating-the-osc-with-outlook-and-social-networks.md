---
title: 将 OSC 与 Outlook 和社交网络关联起来
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f33705cc-8add-42be-9d9f-f4e9245d83f5
description: outlook Social Connector (.osc) 可以显示在 Office 联系人卡片和 outlook 人员窗格活动、状态或与您相关联的任何人的照片更新中。
ms.openlocfilehash: 0ee9451e64f12e8ba371c1ba91a1379cff257313
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428009"
---
# <a name="relating-the-osc-with-outlook-and-social-networks"></a><span data-ttu-id="b54ed-103">将 OSC 与 Outlook 和社交网络关联起来</span><span class="sxs-lookup"><span data-stu-id="b54ed-103">Relating the OSC with Outlook and social networks</span></span>

<span data-ttu-id="b54ed-104">outlook Social Connector (.osc) 可以显示在 Office 联系人卡片和 outlook 人员窗格活动、状态或与您相关联的任何人的照片更新中。</span><span class="sxs-lookup"><span data-stu-id="b54ed-104">The Outlook Social Connector (OSC) can display in the Office Contact Card and Outlook People Pane activities, status, or photo updates for a coworker, friend, or any person you are associated with.</span></span> <span data-ttu-id="b54ed-105">默认情况下, .osc 显示从所选人员接收到的 Outlook 电子邮件、附件和会议请求。</span><span class="sxs-lookup"><span data-stu-id="b54ed-105">By default, the OSC displays the Outlook emails, attachments, and meeting requests received from a selected person.</span></span> <span data-ttu-id="b54ed-106">如果所选人员和 Office 用户在 sharepoint 网站上进行协作, 则该 .osc 还会显示来自该 sharepoint 网站的文档更新和其他网站活动。</span><span class="sxs-lookup"><span data-stu-id="b54ed-106">If the selected person and the Office user collaborate on a SharePoint site, the OSC also displays document updates and other site activities from that SharePoint site.</span></span> <span data-ttu-id="b54ed-107">根据 office 用户感兴趣的关联上下文, Office 用户可以为业务线应用程序、内部企业网站或各种专业和社交网络网站 (如 LinkedIn) 安装 .osc 提供程序。Facebook 和 Windows Live。</span><span class="sxs-lookup"><span data-stu-id="b54ed-107">Depending on the contexts of association that the Office user is interested in, the Office user can install OSC providers for line-of-business applications, internal corporate websites, or a variety of professional and social network sites, such as LinkedIn, Facebook, and Windows Live.</span></span>
  
<span data-ttu-id="b54ed-108">为了支持在 office 客户端应用程序之间共享功能, .osc 核心引擎作为 Office 共享组件的一部分实现, 而 "人员" 窗格以 Outlook 外接程序的形式实现。</span><span class="sxs-lookup"><span data-stu-id="b54ed-108">To support sharing of functionality across Office client applications, the OSC core engine is implemented as part of an Office shared component, and the People Pane is implemented as an Outlook add-in.</span></span> <span data-ttu-id="b54ed-109">若要使用 .osc, Office 用户必须已在该客户端计算机上安装 outlook, 并将 outlook 配置为使用配置文件, 以便该 .osc 可以缓存联系人文件夹中的联系人。</span><span class="sxs-lookup"><span data-stu-id="b54ed-109">To use the OSC, an Office user must have installed Outlook on that client computer and configured Outlook with a profile, so that the OSC can cache contacts in a Contacts folder.</span></span> 
  
<span data-ttu-id="b54ed-110">.osc 提供程序是一种组件对象模型 (COM) DLL, 它允许 .osc 以独立于每个社交网络的 api 的方式访问社交网络数据。</span><span class="sxs-lookup"><span data-stu-id="b54ed-110">An OSC provider is a Component Object Model (COM) DLL that allows the OSC to access social network data in a way that is independent of the APIs of each social network.</span></span> <span data-ttu-id="b54ed-111">必须在客户端计算机上本地安装一个 .osc 提供程序 DLL。</span><span class="sxs-lookup"><span data-stu-id="b54ed-111">An OSC provider DLL must be installed locally on a client computer.</span></span> <span data-ttu-id="b54ed-112">社交网络的 .osc 提供程序通过 Internet 上的社交网络连接的 .osc (Outlook 的一部分)。</span><span class="sxs-lookup"><span data-stu-id="b54ed-112">A social network's OSC provider connects the OSC, which is part of Outlook, with the social network on the Internet.</span></span>
  
<span data-ttu-id="b54ed-113">一个 .osc 提供程序必须实现一组接口 (定义为 .osc 提供程序可扩展性的一部分), 以便与 .osc 进行通信。</span><span class="sxs-lookup"><span data-stu-id="b54ed-113">An OSC provider must implement a set of interfaces, defined as part of the OSC provider extensibility, to communicate with the OSC.</span></span> <span data-ttu-id="b54ed-114">.osc 提供程序可扩展性可用作开放平台。</span><span class="sxs-lookup"><span data-stu-id="b54ed-114">OSC provider extensibility is available as an open platform.</span></span>
  
<span data-ttu-id="b54ed-115">使用 .osc 的提供程序体系结构, 多个提供程序可以使用 .osc 核心引擎和聚合社会信息 (如好友和活动)。</span><span class="sxs-lookup"><span data-stu-id="b54ed-115">The provider architecture of the OSC enables multiple providers to work with the OSC core engine and aggregate social information such as friends and activities.</span></span> <span data-ttu-id="b54ed-116">图1说明了 .osc 提供程序的体系结构。</span><span class="sxs-lookup"><span data-stu-id="b54ed-116">Figure 1 illustrates the OSC provider architecture.</span></span>
  
<span data-ttu-id="b54ed-117">**图1。Outlook Social Connector 提供程序体系结构**</span><span class="sxs-lookup"><span data-stu-id="b54ed-117">**Figure 1. Outlook Social Connector provider architecture**</span></span>

![社交网络、OSC 提供程序、OSC 和 Office](media/off15OSCRef_Architecture.gif)
  
## <a name="terminology"></a><span data-ttu-id="b54ed-119">术语</span><span class="sxs-lookup"><span data-stu-id="b54ed-119">Terminology</span></span>

<span data-ttu-id="b54ed-120">在此 Outlook Social Connector 提供程序参考中, 社交网络用于引用以下类型的网站:</span><span class="sxs-lookup"><span data-stu-id="b54ed-120">In this Outlook Social Connector Provider Reference, a social network is used to refer to the following types of sites:</span></span> 
  
- <span data-ttu-id="b54ed-121">协作网站 (如 SharePoint)。</span><span class="sxs-lookup"><span data-stu-id="b54ed-121">Collaborative sites such as SharePoint.</span></span>
    
- <span data-ttu-id="b54ed-122">诸如 Facebook 和 Windows Live 等社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="b54ed-122">Social network sites such as Facebook and Windows Live.</span></span>
    
- <span data-ttu-id="b54ed-123">专业网络站点, 如 LinkedIn。</span><span class="sxs-lookup"><span data-stu-id="b54ed-123">Professional network sites such as LinkedIn.</span></span>
    
- <span data-ttu-id="b54ed-124">用于联网的其他业务线应用程序或公司内部网站。</span><span class="sxs-lookup"><span data-stu-id="b54ed-124">Other line-of-business applications or corporate internal websites used for networking.</span></span>
    
<span data-ttu-id="b54ed-125">"友元" 这一术语通常用于包括朋友、家人、同事、连接和任何其他 Office 用户在 SharePoint 等协作上下文中的关联, 或已添加到用户的社交网络帐户中。</span><span class="sxs-lookup"><span data-stu-id="b54ed-125">The term friend is used generally to include friends, family, colleagues, connections, and anyone else an Office user is associated with in a collaborative context like SharePoint, or has added to the user's social network account.</span></span> <span data-ttu-id="b54ed-126">非好友是朋友的活动更新中引用的人员, 但它们不是已添加到 Office 用户的社交网络帐户中的好友。</span><span class="sxs-lookup"><span data-stu-id="b54ed-126">Non-friends are people referenced in friends' activity updates but are not friends who have been added to the Office user's social network account.</span></span> <span data-ttu-id="b54ed-127">联系人是 Outlook 联系人文件夹中的人员。</span><span class="sxs-lookup"><span data-stu-id="b54ed-127">Contacts are people in an Outlook contact folder.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b54ed-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b54ed-128">See also</span></span>

- [<span data-ttu-id="b54ed-129">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="b54ed-129">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

