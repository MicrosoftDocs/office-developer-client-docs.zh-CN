---
title: 测试活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 98343c36-5e32-4d07-b474-adfeca693135
description: 本主题介绍了验证 Outlook Social Connector (.osc) 提供程序是否使用按需同步以适当地返回朋友和非好友活动的测试和方案。
ms.openlocfilehash: 0a40dca84681a9e758c2f17d2647c339ded70462
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436298"
---
# <a name="testing-activities"></a><span data-ttu-id="150e7-103">测试活动</span><span class="sxs-lookup"><span data-stu-id="150e7-103">Testing activities</span></span>

<span data-ttu-id="150e7-104">本主题介绍了验证 Outlook Social Connector (.osc) 提供程序是否使用按需同步以适当地返回朋友和非好友活动的测试和方案。</span><span class="sxs-lookup"><span data-stu-id="150e7-104">This topic describes tests and scenarios to verify that the Outlook Social Connector (OSC) provider uses on-demand synchronization to appropriately return activities of friends and non-friends.</span></span>

<span data-ttu-id="150e7-105"><a name="olosc_TestingActivities_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="150e7-105"></span></span>

## <a name="on-demand-synchronization"></a><span data-ttu-id="150e7-106">按需同步</span><span class="sxs-lookup"><span data-stu-id="150e7-106">On-demand synchronization</span></span>

<span data-ttu-id="150e7-107">一个 .osc 提供程序实现**ISocialProvider:: GetCapabilities**, 其中的 .osc 调用它可确定提供程序是否支持对朋友和非好友活动的按需同步。</span><span class="sxs-lookup"><span data-stu-id="150e7-107">An OSC provider implements **ISocialProvider::GetCapabilities**, which the OSC calls to determine whether the provider supports on-demand synchronization of activities of friends and non-friends.</span></span> <span data-ttu-id="150e7-108">对于在 Outlook 人员窗格中显示的人员, .osc 获取并散列其 SMTP 地址, 调用[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md), 并存储 (在内存中) 这些人员返回的活动数据。</span><span class="sxs-lookup"><span data-stu-id="150e7-108">For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md), and stores (in memory) the activities data returned for these persons.</span></span> 
  
### <a name="determining-activities-to-get"></a><span data-ttu-id="150e7-109">确定要获取的活动</span><span class="sxs-lookup"><span data-stu-id="150e7-109">Determining activities to get</span></span>

<span data-ttu-id="150e7-110">传递给**GetActivitiesEx**的哈希 SMTP 地址是确定 .osc 是否会为朋友或非好友获取活动的关键。</span><span class="sxs-lookup"><span data-stu-id="150e7-110">The hashed SMTP addresses passed to **GetActivitiesEx** are the key to determining whether the OSC will get activities for a friend or non-friend.</span></span> <span data-ttu-id="150e7-111">如果用户在其社交网络帐户中指定了该 SMTP 地址, 则 .osc 将获取这些活动。</span><span class="sxs-lookup"><span data-stu-id="150e7-111">The OSC gets activities for a person if the person specifies that SMTP address in his or her social network account.</span></span> <span data-ttu-id="150e7-112">如果此人在其社交网络帐户中不包含该 SMTP 地址, 或者如果该用户是社交网络中的其他电子邮件地址, 则**GetActivitiesEx**不会获取此人的活动。</span><span class="sxs-lookup"><span data-stu-id="150e7-112">If the person does not include that SMTP address in his or her social network account, or if that person is a friend but by a different email address on the social network, **GetActivitiesEx** does not get activities for that person.</span></span> <span data-ttu-id="150e7-113">此外, 对于不是友元但在其社交网络帐户中指定了 SMTP 地址的人, 返回的数据只包括该人员的隐私设置允许的非友元所提供的内容。</span><span class="sxs-lookup"><span data-stu-id="150e7-113">Also, for a person who is not a friend but specifies the SMTP addresses in his or her social network account, the data returned includes only what is available to a non-friend as allowed by the privacy settings of that person.</span></span> 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a><span data-ttu-id="150e7-114">为朋友和非好友创建测试主题</span><span class="sxs-lookup"><span data-stu-id="150e7-114">Creating test subjects for friends and non-friends</span></span>

<span data-ttu-id="150e7-115">若要为友元创建测试主题, 请确定在其社交网络帐户中包含该地址的人员的 SMTP 地址, 以及该网络上具有登录用户的好友状态。</span><span class="sxs-lookup"><span data-stu-id="150e7-115">To create a test subject for a friend, identify the SMTP address of a person who includes that address in his or her social network account and who has a friend status with the logged-on user on that network.</span></span> <span data-ttu-id="150e7-116">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="150e7-116">Create an email message that includes that SMTP address.</span></span> <span data-ttu-id="150e7-117">同样, 若要为非友元创建测试主题, 请确定该地址不是已登录用户的好友的用户的 SMTP 地址, 以及在他或她的隐私设置中指定的用户, 以允许非好友在社交网络上查看其配置文件。</span><span class="sxs-lookup"><span data-stu-id="150e7-117">Similarly, to create a test subject for a non-friend, identify the SMTP address of a person who is not a friend of the logged-on user by that address, and who has specified in his or her privacy settings to allow non-friends to view their profile on the social network.</span></span> <span data-ttu-id="150e7-118">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="150e7-118">Create an email message that includes that SMTP address.</span></span> 
  
<span data-ttu-id="150e7-119">在 Outlook 资源管理器中, 当您选择包含朋友 (或非好友) 的电子邮件时, "人员" 窗格将显示收件人。</span><span class="sxs-lookup"><span data-stu-id="150e7-119">In the Outlook explorer, when you select the email message that includes a friend (or non-friend), the People Pane displays the recipients.</span></span> <span data-ttu-id="150e7-120">通过选择 "人员" 窗格中的好友 (或非好友), 您可以测试提供商是否提供有关此人的信息。</span><span class="sxs-lookup"><span data-stu-id="150e7-120">Selecting the friend (or non-friend) in the People Pane allows you to test that the provider is providing information about the person.</span></span>
  
### <a name="test-scenarios"></a><span data-ttu-id="150e7-121">测试方案</span><span class="sxs-lookup"><span data-stu-id="150e7-121">Test scenarios</span></span>

<span data-ttu-id="150e7-122">若要验证您是否正在为朋友和非好友获取适当的活动, 请测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="150e7-122">To verify that you are getting appropriate activities for friends and non-friends, test for the following scenarios.</span></span>
  
|<span data-ttu-id="150e7-123">**方案**</span><span class="sxs-lookup"><span data-stu-id="150e7-123">**Scenario**</span></span>|<span data-ttu-id="150e7-124">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="150e7-124">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="150e7-125">在 "人员" 窗格中选择的人是社交网络中已登录用户的好友。</span><span class="sxs-lookup"><span data-stu-id="150e7-125">Person selected in the People Pane is a friend with the logged-on user on the social network.</span></span>  <br/> |<span data-ttu-id="150e7-126">"人员" 窗格显示该用户的配置文件以及在社交网络中发布的个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="150e7-126">The People Pane displays that person's profile and profile picture as posted on the social network.</span></span>  <br/> |
|<span data-ttu-id="150e7-127">在 "人员" 窗格中选择的人是社交网络中已登录用户的非朋友, 但允许非好友查看他或她的个人资料。</span><span class="sxs-lookup"><span data-stu-id="150e7-127">Person selected in the People Pane is a non-friend of the logged-on user on the social network, but has allowed his or her profile to be viewed by non-friends.</span></span>  <br/> |<span data-ttu-id="150e7-128">"人员" 窗格显示该用户的配置文件以及在社交网络中发布的个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="150e7-128">The People Pane displays that person's profile and profile picture as posted on the social network.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="150e7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="150e7-129">See also</span></span>

- [<span data-ttu-id="150e7-130">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="150e7-130">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)  
- [<span data-ttu-id="150e7-131">适用于活动的 XML</span><span class="sxs-lookup"><span data-stu-id="150e7-131">XML for Activities</span></span>](xml-for-activities.md)
- [<span data-ttu-id="150e7-132">准备发布一个 .osc 提供程序</span><span class="sxs-lookup"><span data-stu-id="150e7-132">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

