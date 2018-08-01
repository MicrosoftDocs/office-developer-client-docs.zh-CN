---
title: 将 OSC 与 Outlook 和社交网络关联起来
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f33705cc-8add-42be-9d9f-f4e9245d83f5
description: Outlook Social Connector (OSC) 可以在 Office 联系人卡片和 Outlook 人员窗格活动、 状态或照片更新显示同事、 朋友，或要与任何人。
ms.openlocfilehash: 6dc6221b89eca5303e7cf6a201927659d4ac9107
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779331"
---
# <a name="relating-the-osc-with-outlook-and-social-networks"></a><span data-ttu-id="d4d24-103">将 OSC 与 Outlook 和社交网络关联起来</span><span class="sxs-lookup"><span data-stu-id="d4d24-103">Relating the OSC with Outlook and social networks</span></span>

<span data-ttu-id="d4d24-104">Outlook Social Connector (OSC) 可以在 Office 联系人卡片和 Outlook 人员窗格活动、 状态或照片更新显示同事、 朋友，或要与任何人。</span><span class="sxs-lookup"><span data-stu-id="d4d24-104">The Outlook Social Connector (OSC) can display in the Office Contact Card and Outlook People Pane activities, status, or photo updates for a coworker, friend, or any person you are associated with.</span></span> <span data-ttu-id="d4d24-105">默认情况下 OSC 显示 Outlook 电子邮件，附件，并从所选人员会议请求收到。</span><span class="sxs-lookup"><span data-stu-id="d4d24-105">By default, the OSC displays the Outlook emails, attachments, and meeting requests received from a selected person.</span></span> <span data-ttu-id="d4d24-106">如果所选的人员和 Office 用户协作 SharePoint 网站上，OSC 还显示文档更新和 SharePoint 网站从其他网站活动。</span><span class="sxs-lookup"><span data-stu-id="d4d24-106">If the selected person and the Office user collaborate on a SharePoint site, the OSC also displays document updates and other site activities from that SharePoint site.</span></span> <span data-ttu-id="d4d24-107">Office 用户感兴趣的关联的上下文中，根据 Office 用户可以安装 OSC 提供程序的业务线应用程序、 内部企业网站或 professional 和社交网络站点，如 LinkedIn 各种Facebook 和 Windows Live。</span><span class="sxs-lookup"><span data-stu-id="d4d24-107">Depending on the contexts of association that the Office user is interested in, the Office user can install OSC providers for line-of-business applications, internal corporate websites, or a variety of professional and social network sites, such as LinkedIn, Facebook, and Windows Live.</span></span>
  
<span data-ttu-id="d4d24-108">若要支持在 Office 客户端应用程序之间共享功能，OSC 核心引擎实施 Office 的共享组件的一部分，人员窗格作为 Outlook 外接程序实现的。</span><span class="sxs-lookup"><span data-stu-id="d4d24-108">To support sharing of functionality across Office client applications, the OSC core engine is implemented as part of an Office shared component, and the People Pane is implemented as an Outlook add-in.</span></span> <span data-ttu-id="d4d24-109">若要使用 OSC，必须安装该客户端计算机上的 Outlook 并配置 Outlook 配置文件，以便 OSC 可以缓存联系人文件夹中的联系人的 Office 用户。</span><span class="sxs-lookup"><span data-stu-id="d4d24-109">To use the OSC, an Office user must have installed Outlook on that client computer and configured Outlook with a profile, so that the OSC can cache contacts in a Contacts folder.</span></span> 
  
<span data-ttu-id="d4d24-110">OSC 提供程序组件对象模型 (COM) 允许 OSC 访问一种方式独立于每个社交网络的 Api 中的社交网络数据的 DLL。</span><span class="sxs-lookup"><span data-stu-id="d4d24-110">An OSC provider is a Component Object Model (COM) DLL that allows the OSC to access social network data in a way that is independent of the APIs of each social network.</span></span> <span data-ttu-id="d4d24-111">OSC 提供程序 DLL 必须客户端计算机上本地安装。</span><span class="sxs-lookup"><span data-stu-id="d4d24-111">An OSC provider DLL must be installed locally on a client computer.</span></span> <span data-ttu-id="d4d24-112">社交网络的 OSC 提供程序连接 OSC，它是 Outlook 的一部分，Internet 上的社交网络。</span><span class="sxs-lookup"><span data-stu-id="d4d24-112">A social network's OSC provider connects the OSC, which is part of Outlook, with the social network on the Internet.</span></span>
  
<span data-ttu-id="d4d24-113">OSC 提供程序必须实现一组接口，定义为 OSC 提供程序扩展性，与 OSC 进行通信的一部分。</span><span class="sxs-lookup"><span data-stu-id="d4d24-113">An OSC provider must implement a set of interfaces, defined as part of the OSC provider extensibility, to communicate with the OSC.</span></span> <span data-ttu-id="d4d24-114">可用作开放平台 OSC 提供程序扩展性。</span><span class="sxs-lookup"><span data-stu-id="d4d24-114">OSC provider extensibility is available as an open platform.</span></span>
  
<span data-ttu-id="d4d24-115">OSC 提供程序体系结构允许多个提供程序使用 OSC 核心引擎和聚合社会性信息，如朋友和活动。</span><span class="sxs-lookup"><span data-stu-id="d4d24-115">The provider architecture of the OSC enables multiple providers to work with the OSC core engine and aggregate social information such as friends and activities.</span></span> <span data-ttu-id="d4d24-116">图 1 显示了 OSC 提供程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="d4d24-116">Figure 1 illustrates the OSC provider architecture.</span></span>
  
<span data-ttu-id="d4d24-117">**图 1。Outlook Social Connector 提供程序体系结构**</span><span class="sxs-lookup"><span data-stu-id="d4d24-117">**Figure 1. Outlook Social Connector provider architecture**</span></span>

![社交网络、OSC 提供程序、OSC 和 Office](media/off15OSCRef_Architecture.gif)
  
## <a name="terminology"></a><span data-ttu-id="d4d24-119">术语</span><span class="sxs-lookup"><span data-stu-id="d4d24-119">Terminology</span></span>

<span data-ttu-id="d4d24-120">在此 Outlook Social Connector 提供程序参考，社交网络用于引用以下类型的网站：</span><span class="sxs-lookup"><span data-stu-id="d4d24-120">In this Outlook Social Connector Provider Reference, a social network is used to refer to the following types of sites:</span></span> 
  
- <span data-ttu-id="d4d24-121">如 SharePoint 的协作网站。</span><span class="sxs-lookup"><span data-stu-id="d4d24-121">Collaborative sites such as SharePoint.</span></span>
    
- <span data-ttu-id="d4d24-122">Facebook 和 Windows Live 等的社交网络站点。</span><span class="sxs-lookup"><span data-stu-id="d4d24-122">Social network sites such as Facebook and Windows Live.</span></span>
    
- <span data-ttu-id="d4d24-123">如 LinkedIn 专业的网络站点。</span><span class="sxs-lookup"><span data-stu-id="d4d24-123">Professional network sites such as LinkedIn.</span></span>
    
- <span data-ttu-id="d4d24-124">其他业务线应用程序或用于网络的公司内部网站。</span><span class="sxs-lookup"><span data-stu-id="d4d24-124">Other line-of-business applications or corporate internal websites used for networking.</span></span>
    
<span data-ttu-id="d4d24-125">术语朋友通常用于包括朋友、 家人、 同事、 连接和任何其他人的 Office 用户相关联 SharePoint，如协作上下文中或已添加到用户的社交网络帐户。</span><span class="sxs-lookup"><span data-stu-id="d4d24-125">The term friend is used generally to include friends, family, colleagues, connections, and anyone else an Office user is associated with in a collaborative context like SharePoint, or has added to the user's social network account.</span></span> <span data-ttu-id="d4d24-126">非朋友是朋友的活动更新中引用的人员，而不是朋友已添加到 Office 用户的社交网络帐户。</span><span class="sxs-lookup"><span data-stu-id="d4d24-126">Non-friends are people referenced in friends' activity updates but are not friends who have been added to the Office user's social network account.</span></span> <span data-ttu-id="d4d24-127">联系人是 Outlook 联系人文件夹中的人。</span><span class="sxs-lookup"><span data-stu-id="d4d24-127">Contacts are people in an Outlook contact folder.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d4d24-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4d24-128">See also</span></span>

- [<span data-ttu-id="d4d24-129">Outlook Social Connector 提供程序开发入门（英文）</span><span class="sxs-lookup"><span data-stu-id="d4d24-129">Getting Started with Developing an Outlook Social Connector Provider</span></span>](getting-started-with-developing-an-outlook-social-connector-provider.md)

