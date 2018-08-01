---
title: 测试关注和停止关注人员
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c603c3c6-62c8-4895-93e1-b2e146dfaa4f
description: 本主题介绍方案来测试按照朋友，并停止关注朋友社交网络上的 Outlook Social Connector (OSC) 提供程序的功能。
ms.openlocfilehash: 09652b658a2c20301b8b0568d373ae6fe841fe2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779324"
---
# <a name="testing-following-and-stop-following-persons"></a><span data-ttu-id="26659-103">测试关注和停止关注人员</span><span class="sxs-lookup"><span data-stu-id="26659-103">Testing following and stop-following persons</span></span>

<span data-ttu-id="26659-104">本主题介绍方案来测试按照朋友，并停止关注朋友社交网络上的 Outlook Social Connector (OSC) 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="26659-104">This topic describes scenarios to test the Outlook Social Connector (OSC) provider's ability to follow a friend, and to stop following a friend on the social network.</span></span>
  
## <a name="following-a-person"></a><span data-ttu-id="26659-105">关注人员</span><span class="sxs-lookup"><span data-stu-id="26659-105">Following a person</span></span>

<span data-ttu-id="26659-106">关注人员是将人员添加为朋友在社交网络中，使用提供所选 Outlook 项目的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="26659-106">To follow a person is to add a person as a friend on the social network, using the SMTP address provided by the selected Outlook item.</span></span> <span data-ttu-id="26659-107">通常在社交网络关注某人涉及权限从请求此人的电子邮件到该 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="26659-107">Following someone on a social network usually involves requesting permission from that person by an email to that SMTP address.</span></span> <span data-ttu-id="26659-108">若要授予权限，此人必须具有已包含在他或她社交网络帐户的 SMTP 地址或愿意添加到社交网络帐户的 SMTP。</span><span class="sxs-lookup"><span data-stu-id="26659-108">In order to grant permission, that person must either have that SMTP address already included in his or her social network account, or be willing to add that SMTP to a social network account.</span></span> <span data-ttu-id="26659-109">测试以下每个方案若要验证您 OSC 提供程序的行为正确。</span><span class="sxs-lookup"><span data-stu-id="26659-109">Test each of the following scenarios to verify that your OSC provider behaves correctly.</span></span>
  
|<span data-ttu-id="26659-110">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="26659-110">**Scenario**</span></span>|<span data-ttu-id="26659-111">**预期的行为**</span><span class="sxs-lookup"><span data-stu-id="26659-111">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26659-112">正在尝试按照用户社交网络上存在的社交网络上的人员。</span><span class="sxs-lookup"><span data-stu-id="26659-112">Attempting to follow a person on the social network who exists on the social network.</span></span>  <br/> |<span data-ttu-id="26659-113">对于不需要从此人权限社交网络，社交网络立即将此人添加为朋友。</span><span class="sxs-lookup"><span data-stu-id="26659-113">For a social network that does not require permission from the person, the social network immediately adds the person as a friend.</span></span>  <br/> <span data-ttu-id="26659-114">对于需要从该人的权限的网络，社交网络发送通知。</span><span class="sxs-lookup"><span data-stu-id="26659-114">For a network that requires permission from that person, the social network sends a notification.</span></span> <span data-ttu-id="26659-115">Outlook 人员窗格显示此人的待处理的图标。</span><span class="sxs-lookup"><span data-stu-id="26659-115">The Outlook People Pane displays a pending icon for that person.</span></span>  <br/> |
|<span data-ttu-id="26659-116">正在尝试按照用户社交网络上不存在社交网络上的人员。</span><span class="sxs-lookup"><span data-stu-id="26659-116">Attempting to follow a person on the social network who does not exist on the social network.</span></span>  <br/> |<span data-ttu-id="26659-117">OSC 提供程序[ISocialSession::FollowPerson](isocialsession-followperson.md)或[ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md)中显示相应的错误。</span><span class="sxs-lookup"><span data-stu-id="26659-117">The OSC provider displays the appropriate error in [ISocialSession::FollowPerson](isocialsession-followperson.md) or [ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md).</span></span>  <br/> |
|<span data-ttu-id="26659-118">跟踪社交网络上的朋友。</span><span class="sxs-lookup"><span data-stu-id="26659-118">Following a friend on the social network.</span></span>  <br/> |<span data-ttu-id="26659-119">在人员窗格中选择好友，显示社交网络的徽章和朋友的配置文件图片的社交网络。</span><span class="sxs-lookup"><span data-stu-id="26659-119">For the friend selected in the People Pane, the social network's badge and the friend's profile picture for that social network are displayed.</span></span>  <br/> |
|<span data-ttu-id="26659-120">选择指向朋友的配置文件页面的链接。</span><span class="sxs-lookup"><span data-stu-id="26659-120">Selecting the link to the profile page of a friend.</span></span>  <br/> |<span data-ttu-id="26659-121">在登录用户的默认浏览器中打开社交网络朋友的页面。</span><span class="sxs-lookup"><span data-stu-id="26659-121">The friend's page on the social network opens in the logged-on user's default browser.</span></span>  <br/> |
   
## <a name="stop-following-a-person"></a><span data-ttu-id="26659-122">停止关注人员</span><span class="sxs-lookup"><span data-stu-id="26659-122">Stop following a person</span></span>

<span data-ttu-id="26659-123">若要停止关注人员是删除该联系人为社交网络上朋友。</span><span class="sxs-lookup"><span data-stu-id="26659-123">To stop following a person is to remove that person as a friend on the social network.</span></span> <span data-ttu-id="26659-124">测试下列方案来确认您正确关注人员的 OSC 提供程序停止。</span><span class="sxs-lookup"><span data-stu-id="26659-124">Test the following scenario to verify your OSC provider stops following a person properly.</span></span>
  
|<span data-ttu-id="26659-125">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="26659-125">**Scenario**</span></span>|<span data-ttu-id="26659-126">**预期的行为**</span><span class="sxs-lookup"><span data-stu-id="26659-126">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26659-127">尝试删除为朋友社交网络上的人员。</span><span class="sxs-lookup"><span data-stu-id="26659-127">Attempting to remove a person as a friend on the social network.</span></span>  <br/> |<span data-ttu-id="26659-128">社交网络不再列出了为朋友登录的用户的帐户的人员。</span><span class="sxs-lookup"><span data-stu-id="26659-128">The social network no longer lists that person as a friend on the logged on user's account.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="26659-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26659-129">See also</span></span>

- [<span data-ttu-id="26659-130">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="26659-130">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

