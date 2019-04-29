---
title: 测试关注和停止关注人员
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c603c3c6-62c8-4895-93e1-b2e146dfaa4f
description: 本主题介绍了测试 Outlook Social Connector (.osc) 提供商能否关注好友以及停止关注社交网络上的好友的方案。
ms.openlocfilehash: 06a2bc48fa723f4d4513376cace96a195cef9fa3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432448"
---
# <a name="testing-following-and-stop-following-persons"></a><span data-ttu-id="63bcb-103">测试关注和停止关注人员</span><span class="sxs-lookup"><span data-stu-id="63bcb-103">Testing following and stop-following persons</span></span>

<span data-ttu-id="63bcb-104">本主题介绍了测试 Outlook Social Connector (.osc) 提供商能否关注好友以及停止关注社交网络上的好友的方案。</span><span class="sxs-lookup"><span data-stu-id="63bcb-104">This topic describes scenarios to test the Outlook Social Connector (OSC) provider's ability to follow a friend, and to stop following a friend on the social network.</span></span>
  
## <a name="following-a-person"></a><span data-ttu-id="63bcb-105">关注人员</span><span class="sxs-lookup"><span data-stu-id="63bcb-105">Following a person</span></span>

<span data-ttu-id="63bcb-106">若要关注某个人, 请使用所选 Outlook 项目提供的 SMTP 地址在社交网络上添加作为好友的人员。</span><span class="sxs-lookup"><span data-stu-id="63bcb-106">To follow a person is to add a person as a friend on the social network, using the SMTP address provided by the selected Outlook item.</span></span> <span data-ttu-id="63bcb-107">关注社交网络的人通常需要通过电子邮件向该 SMTP 地址请求获取权限。</span><span class="sxs-lookup"><span data-stu-id="63bcb-107">Following someone on a social network usually involves requesting permission from that person by an email to that SMTP address.</span></span> <span data-ttu-id="63bcb-108">为了授予权限, 该用户必须具有其社交网络帐户中已包含的 smtp 地址, 或者愿意将该 smtp 添加到社交网络帐户中。</span><span class="sxs-lookup"><span data-stu-id="63bcb-108">In order to grant permission, that person must either have that SMTP address already included in his or her social network account, or be willing to add that SMTP to a social network account.</span></span> <span data-ttu-id="63bcb-109">测试以下每个方案以验证您的 .osc 提供程序的行为是否正确。</span><span class="sxs-lookup"><span data-stu-id="63bcb-109">Test each of the following scenarios to verify that your OSC provider behaves correctly.</span></span>
  
|<span data-ttu-id="63bcb-110">**方案**</span><span class="sxs-lookup"><span data-stu-id="63bcb-110">**Scenario**</span></span>|<span data-ttu-id="63bcb-111">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="63bcb-111">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63bcb-112">尝试关注社交网络上存在的社交网络上的人员。</span><span class="sxs-lookup"><span data-stu-id="63bcb-112">Attempting to follow a person on the social network who exists on the social network.</span></span>  <br/> |<span data-ttu-id="63bcb-113">对于不需要此人授予权限的社交网络, 社交网络会立即将该人员添加为好友。</span><span class="sxs-lookup"><span data-stu-id="63bcb-113">For a social network that does not require permission from the person, the social network immediately adds the person as a friend.</span></span>  <br/> <span data-ttu-id="63bcb-114">对于需要来自此人的权限的网络, 社交网络发送通知。</span><span class="sxs-lookup"><span data-stu-id="63bcb-114">For a network that requires permission from that person, the social network sends a notification.</span></span> <span data-ttu-id="63bcb-115">"Outlook 人员" 窗格显示该人员的挂起图标。</span><span class="sxs-lookup"><span data-stu-id="63bcb-115">The Outlook People Pane displays a pending icon for that person.</span></span>  <br/> |
|<span data-ttu-id="63bcb-116">尝试关注社交网络上不存在的社交网络上的人员。</span><span class="sxs-lookup"><span data-stu-id="63bcb-116">Attempting to follow a person on the social network who does not exist on the social network.</span></span>  <br/> |<span data-ttu-id="63bcb-117">.osc 提供程序在[ISocialSession:: FollowPerson](isocialsession-followperson.md)或[ISocialSession2:: FollowPersonEx](isocialsession2-followpersonex.md)中显示相应的错误。</span><span class="sxs-lookup"><span data-stu-id="63bcb-117">The OSC provider displays the appropriate error in [ISocialSession::FollowPerson](isocialsession-followperson.md) or [ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md).</span></span>  <br/> |
|<span data-ttu-id="63bcb-118">关注社交网络上的某个好友。</span><span class="sxs-lookup"><span data-stu-id="63bcb-118">Following a friend on the social network.</span></span>  <br/> |<span data-ttu-id="63bcb-119">对于在 "人员" 窗格中选择的朋友, 会显示社交网络的徽章和该社交网络的好友个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="63bcb-119">For the friend selected in the People Pane, the social network's badge and the friend's profile picture for that social network are displayed.</span></span>  <br/> |
|<span data-ttu-id="63bcb-120">选择指向好友的配置文件页的链接。</span><span class="sxs-lookup"><span data-stu-id="63bcb-120">Selecting the link to the profile page of a friend.</span></span>  <br/> |<span data-ttu-id="63bcb-121">社交网络上的好友页面在登录用户的默认浏览器中打开。</span><span class="sxs-lookup"><span data-stu-id="63bcb-121">The friend's page on the social network opens in the logged-on user's default browser.</span></span>  <br/> |
   
## <a name="stop-following-a-person"></a><span data-ttu-id="63bcb-122">停止关注某个人</span><span class="sxs-lookup"><span data-stu-id="63bcb-122">Stop following a person</span></span>

<span data-ttu-id="63bcb-123">若要停止关注某个人, 请在社交网络上将其作为好友删除。</span><span class="sxs-lookup"><span data-stu-id="63bcb-123">To stop following a person is to remove that person as a friend on the social network.</span></span> <span data-ttu-id="63bcb-124">测试以下方案以验证您的您的 .osc 提供商是否已正确停止关注某个人。</span><span class="sxs-lookup"><span data-stu-id="63bcb-124">Test the following scenario to verify your OSC provider stops following a person properly.</span></span>
  
|<span data-ttu-id="63bcb-125">**方案**</span><span class="sxs-lookup"><span data-stu-id="63bcb-125">**Scenario**</span></span>|<span data-ttu-id="63bcb-126">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="63bcb-126">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63bcb-127">试图将某个人删除为社交网络上的好友。</span><span class="sxs-lookup"><span data-stu-id="63bcb-127">Attempting to remove a person as a friend on the social network.</span></span>  <br/> |<span data-ttu-id="63bcb-128">社交网络不再将此人列为登录用户帐户上的好友。</span><span class="sxs-lookup"><span data-stu-id="63bcb-128">The social network no longer lists that person as a friend on the logged on user's account.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="63bcb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63bcb-129">See also</span></span>

- [<span data-ttu-id="63bcb-130">准备发布一个 .osc 提供程序</span><span class="sxs-lookup"><span data-stu-id="63bcb-130">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

