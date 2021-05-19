---
title: 测试关注和停止关注人员
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c603c3c6-62c8-4895-93e1-b2e146dfaa4f
description: 本主题介绍用于测试 Outlook Social Connector (OSC) 提供程序能否关注好友以及停止关注社交网络上的好友的方案。
ms.openlocfilehash: 06a2bc48fa723f4d4513376cace96a195cef9fa3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432448"
---
# <a name="testing-following-and-stop-following-persons"></a><span data-ttu-id="926cc-103">测试关注和停止关注人员</span><span class="sxs-lookup"><span data-stu-id="926cc-103">Testing following and stop-following persons</span></span>

<span data-ttu-id="926cc-104">本主题介绍用于测试 Outlook Social Connector (OSC) 提供程序能否关注好友以及停止关注社交网络上的好友的方案。</span><span class="sxs-lookup"><span data-stu-id="926cc-104">This topic describes scenarios to test the Outlook Social Connector (OSC) provider's ability to follow a friend, and to stop following a friend on the social network.</span></span>
  
## <a name="following-a-person"></a><span data-ttu-id="926cc-105">跟踪人员</span><span class="sxs-lookup"><span data-stu-id="926cc-105">Following a person</span></span>

<span data-ttu-id="926cc-106">关注某人是使用选定用户项目提供的 SMTP 地址，将某人添加为社交网络Outlook地址。</span><span class="sxs-lookup"><span data-stu-id="926cc-106">To follow a person is to add a person as a friend on the social network, using the SMTP address provided by the selected Outlook item.</span></span> <span data-ttu-id="926cc-107">在社交网络上跟踪某人通常涉及到通过电子邮件向该 SMTP 地址请求该人员的权限。</span><span class="sxs-lookup"><span data-stu-id="926cc-107">Following someone on a social network usually involves requesting permission from that person by an email to that SMTP address.</span></span> <span data-ttu-id="926cc-108">为了授予权限，该人员必须拥有已包含在其社交网络帐户中的 SMTP 地址，或者愿意将此 SMTP 添加到社交网络帐户。</span><span class="sxs-lookup"><span data-stu-id="926cc-108">In order to grant permission, that person must either have that SMTP address already included in his or her social network account, or be willing to add that SMTP to a social network account.</span></span> <span data-ttu-id="926cc-109">测试以下每个方案，验证 OSC 提供程序是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="926cc-109">Test each of the following scenarios to verify that your OSC provider behaves correctly.</span></span>
  
|<span data-ttu-id="926cc-110">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="926cc-110">**Scenario**</span></span>|<span data-ttu-id="926cc-111">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="926cc-111">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="926cc-112">尝试关注社交网络上存在的人。</span><span class="sxs-lookup"><span data-stu-id="926cc-112">Attempting to follow a person on the social network who exists on the social network.</span></span>  <br/> |<span data-ttu-id="926cc-113">对于不需要此人权限的社交网络，社交网络会立即将此人添加为好友。</span><span class="sxs-lookup"><span data-stu-id="926cc-113">For a social network that does not require permission from the person, the social network immediately adds the person as a friend.</span></span>  <br/> <span data-ttu-id="926cc-114">对于需要此人权限的网络，社交网络会发送通知。</span><span class="sxs-lookup"><span data-stu-id="926cc-114">For a network that requires permission from that person, the social network sends a notification.</span></span> <span data-ttu-id="926cc-115">"Outlook"窗格将显示此人的挂起图标。</span><span class="sxs-lookup"><span data-stu-id="926cc-115">The Outlook People Pane displays a pending icon for that person.</span></span>  <br/> |
|<span data-ttu-id="926cc-116">尝试关注社交网络上不存在的人。</span><span class="sxs-lookup"><span data-stu-id="926cc-116">Attempting to follow a person on the social network who does not exist on the social network.</span></span>  <br/> |<span data-ttu-id="926cc-117">OSC 提供程序在 [ISocialSession：：FollowPerson](isocialsession-followperson.md) 或 [ISocialSession2：：FollowPersonEx](isocialsession2-followpersonex.md)中显示相应的错误。</span><span class="sxs-lookup"><span data-stu-id="926cc-117">The OSC provider displays the appropriate error in [ISocialSession::FollowPerson](isocialsession-followperson.md) or [ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md).</span></span>  <br/> |
|<span data-ttu-id="926cc-118">在社交网络上跟踪好友。</span><span class="sxs-lookup"><span data-stu-id="926cc-118">Following a friend on the social network.</span></span>  <br/> |<span data-ttu-id="926cc-119">对于在人员窗格中选择的朋友，将显示社交网络的徽章和该社交网络的好友个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="926cc-119">For the friend selected in the People Pane, the social network's badge and the friend's profile picture for that social network are displayed.</span></span>  <br/> |
|<span data-ttu-id="926cc-120">选择指向好友的个人资料页面的链接。</span><span class="sxs-lookup"><span data-stu-id="926cc-120">Selecting the link to the profile page of a friend.</span></span>  <br/> |<span data-ttu-id="926cc-121">社交网络上好友的页面将在登录用户的默认浏览器中打开。</span><span class="sxs-lookup"><span data-stu-id="926cc-121">The friend's page on the social network opens in the logged-on user's default browser.</span></span>  <br/> |
   
## <a name="stop-following-a-person"></a><span data-ttu-id="926cc-122">停止跟踪某人</span><span class="sxs-lookup"><span data-stu-id="926cc-122">Stop following a person</span></span>

<span data-ttu-id="926cc-123">停止跟踪某人是作为社交网络上的好友删除该人员。</span><span class="sxs-lookup"><span data-stu-id="926cc-123">To stop following a person is to remove that person as a friend on the social network.</span></span> <span data-ttu-id="926cc-124">测试以下方案以验证您的 OSC 提供程序是否停止正确跟踪某人。</span><span class="sxs-lookup"><span data-stu-id="926cc-124">Test the following scenario to verify your OSC provider stops following a person properly.</span></span>
  
|<span data-ttu-id="926cc-125">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="926cc-125">**Scenario**</span></span>|<span data-ttu-id="926cc-126">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="926cc-126">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="926cc-127">尝试删除社交网络上作为好友的人。</span><span class="sxs-lookup"><span data-stu-id="926cc-127">Attempting to remove a person as a friend on the social network.</span></span>  <br/> |<span data-ttu-id="926cc-128">社交网络不再将该用户作为已登录用户帐户上的好友列出。</span><span class="sxs-lookup"><span data-stu-id="926cc-128">The social network no longer lists that person as a friend on the logged on user's account.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="926cc-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="926cc-129">See also</span></span>

- [<span data-ttu-id="926cc-130">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="926cc-130">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

