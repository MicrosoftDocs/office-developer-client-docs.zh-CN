---
title: 将 OSC 与 Outlook 和社交网络关联起来
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f33705cc-8add-42be-9d9f-f4e9245d83f5
description: the Outlook Social Connector (OSC) can display in the Office Contact Card and Outlook People Pane activities， status， or photo updates for a coworker， friend， or any person you are associated with.
ms.openlocfilehash: 0ee9451e64f12e8ba371c1ba91a1379cff257313
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428009"
---
# <a name="relating-the-osc-with-outlook-and-social-networks"></a><span data-ttu-id="7ebb3-103">将 OSC 与 Outlook 和社交网络关联起来</span><span class="sxs-lookup"><span data-stu-id="7ebb3-103">Relating the OSC with Outlook and social networks</span></span>

<span data-ttu-id="7ebb3-104">the Outlook Social Connector (OSC) can display in the Office Contact Card and Outlook People Pane activities， status， or photo updates for a coworker， friend， or any person you are associated with.</span><span class="sxs-lookup"><span data-stu-id="7ebb3-104">The Outlook Social Connector (OSC) can display in the Office Contact Card and Outlook People Pane activities, status, or photo updates for a coworker, friend, or any person you are associated with.</span></span> <span data-ttu-id="7ebb3-105">默认情况下，OSC 显示Outlook用户收到的电子邮件、附件和会议请求的信息。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-105">By default, the OSC displays the Outlook emails, attachments, and meeting requests received from a selected person.</span></span> <span data-ttu-id="7ebb3-106">如果所选用户和Office在网站中SharePoint协作，OSC 还将显示来自该站点的文档更新SharePoint活动。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-106">If the selected person and the Office user collaborate on a SharePoint site, the OSC also displays document updates and other site activities from that SharePoint site.</span></span> <span data-ttu-id="7ebb3-107">根据 Office 用户感兴趣的关联上下文，Office 用户可以为业务线应用程序、内部公司网站或各种专业和社交网络网站（如 LinkedIn、Facebook 和 Windows Live）安装 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-107">Depending on the contexts of association that the Office user is interested in, the Office user can install OSC providers for line-of-business applications, internal corporate websites, or a variety of professional and social network sites, such as LinkedIn, Facebook, and Windows Live.</span></span>
  
<span data-ttu-id="7ebb3-108">为了支持跨 Office 客户端应用程序共享功能，OSC 核心引擎作为 Office 共享组件的一部分实现，并且人员窗格作为 Outlook 外接程序实现。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-108">To support sharing of functionality across Office client applications, the OSC core engine is implemented as part of an Office shared component, and the People Pane is implemented as an Outlook add-in.</span></span> <span data-ttu-id="7ebb3-109">若要使用 OSC，Office用户必须在该客户端计算机上安装 Outlook 并使用配置文件配置 Outlook，以便 OSC 可以将联系人缓存到"联系人"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-109">To use the OSC, an Office user must have installed Outlook on that client computer and configured Outlook with a profile, so that the OSC can cache contacts in a Contacts folder.</span></span> 
  
<span data-ttu-id="7ebb3-110">OSC 提供程序是组件对象模型 (COM) DLL，它允许 OSC 以独立于每个社交网络的 API 的方式访问社交网络数据。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-110">An OSC provider is a Component Object Model (COM) DLL that allows the OSC to access social network data in a way that is independent of the APIs of each social network.</span></span> <span data-ttu-id="7ebb3-111">必须在客户端计算机上本地安装 OSC 提供程序 DLL。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-111">An OSC provider DLL must be installed locally on a client computer.</span></span> <span data-ttu-id="7ebb3-112">社交网络的 OSC 提供程序将 OSC（作为 Outlook的一部分）与 Internet 上的社交网络连接。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-112">A social network's OSC provider connects the OSC, which is part of Outlook, with the social network on the Internet.</span></span>
  
<span data-ttu-id="7ebb3-113">OSC 提供程序必须实现一组接口（定义为 OSC 提供程序扩展的一部分）以与 OSC 通信。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-113">An OSC provider must implement a set of interfaces, defined as part of the OSC provider extensibility, to communicate with the OSC.</span></span> <span data-ttu-id="7ebb3-114">OSC 提供程序扩展性作为开放平台提供。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-114">OSC provider extensibility is available as an open platform.</span></span>
  
<span data-ttu-id="7ebb3-115">OSC 的提供程序体系结构允许多个提供程序使用 OSC 核心引擎并聚合好友和活动等社交信息。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-115">The provider architecture of the OSC enables multiple providers to work with the OSC core engine and aggregate social information such as friends and activities.</span></span> <span data-ttu-id="7ebb3-116">图 1 说明了 OSC 提供程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-116">Figure 1 illustrates the OSC provider architecture.</span></span>
  
<span data-ttu-id="7ebb3-117">**图 1.OutlookSocial Connector 提供程序体系结构**</span><span class="sxs-lookup"><span data-stu-id="7ebb3-117">**Figure 1. Outlook Social Connector provider architecture**</span></span>

![社交网络、OSC 提供程序、OSC 和 Office](media/off15OSCRef_Architecture.gif)
  
## <a name="terminology"></a><span data-ttu-id="7ebb3-119">术语</span><span class="sxs-lookup"><span data-stu-id="7ebb3-119">Terminology</span></span>

<span data-ttu-id="7ebb3-120">在此Outlook连接器提供程序参考"中，社交网络用于引用以下类型的网站：</span><span class="sxs-lookup"><span data-stu-id="7ebb3-120">In this Outlook Social Connector Provider Reference, a social network is used to refer to the following types of sites:</span></span> 
  
- <span data-ttu-id="7ebb3-121">协作网站，如SharePoint。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-121">Collaborative sites such as SharePoint.</span></span>
    
- <span data-ttu-id="7ebb3-122">社交网络网站，如 Facebook 和 Windows Live。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-122">Social network sites such as Facebook and Windows Live.</span></span>
    
- <span data-ttu-id="7ebb3-123">Professional LinkedIn 等网络站点。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-123">Professional network sites such as LinkedIn.</span></span>
    
- <span data-ttu-id="7ebb3-124">用于网络的其他业务线应用程序或公司内部网站。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-124">Other line-of-business applications or corporate internal websites used for networking.</span></span>
    
<span data-ttu-id="7ebb3-125">术语"好友"通常用于包括好友、家庭、同事、连接以及 Office 用户在协作上下文（如 SharePoint）中关联或已添加到用户的社交网络帐户的任何人。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-125">The term friend is used generally to include friends, family, colleagues, connections, and anyone else an Office user is associated with in a collaborative context like SharePoint, or has added to the user's social network account.</span></span> <span data-ttu-id="7ebb3-126">非好友是好友活动更新中引用的人，但不是已添加到好友Office用户的社交网络帐户的好友。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-126">Non-friends are people referenced in friends' activity updates but are not friends who have been added to the Office user's social network account.</span></span> <span data-ttu-id="7ebb3-127">联系人是联系人文件夹中Outlook人员。</span><span class="sxs-lookup"><span data-stu-id="7ebb3-127">Contacts are people in an Outlook contact folder.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7ebb3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ebb3-128">See also</span></span>

- [<span data-ttu-id="7ebb3-129">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="7ebb3-129">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

