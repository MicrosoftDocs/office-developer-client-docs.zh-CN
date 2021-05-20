---
title: 测试活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 98343c36-5e32-4d07-b474-adfeca693135
description: 本主题介绍用于验证 Outlook Social Connector (OSC) 提供程序是否使用按需同步正确返回好友和非好友的活动的测试和方案。
ms.openlocfilehash: 0a40dca84681a9e758c2f17d2647c339ded70462
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436298"
---
# <a name="testing-activities"></a><span data-ttu-id="3f885-103">测试活动</span><span class="sxs-lookup"><span data-stu-id="3f885-103">Testing activities</span></span>

<span data-ttu-id="3f885-104">本主题介绍用于验证 Outlook Social Connector (OSC) 提供程序是否使用按需同步正确返回好友和非好友的活动的测试和方案。</span><span class="sxs-lookup"><span data-stu-id="3f885-104">This topic describes tests and scenarios to verify that the Outlook Social Connector (OSC) provider uses on-demand synchronization to appropriately return activities of friends and non-friends.</span></span>

<span data-ttu-id="3f885-105"><a name="olosc_TestingActivities_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="3f885-105"><a name="olosc_TestingActivities_OnDemandSync"> </a></span></span>

## <a name="on-demand-synchronization"></a><span data-ttu-id="3f885-106">按需同步</span><span class="sxs-lookup"><span data-stu-id="3f885-106">On-demand synchronization</span></span>

<span data-ttu-id="3f885-107">OSC 提供程序实现 **ISocialProvider：：GetCapabilities，OSC** 将调用它以确定提供程序是否支持好友和非好友的活动按需同步。</span><span class="sxs-lookup"><span data-stu-id="3f885-107">An OSC provider implements **ISocialProvider::GetCapabilities**, which the OSC calls to determine whether the provider supports on-demand synchronization of activities of friends and non-friends.</span></span> <span data-ttu-id="3f885-108">对于 Outlook 人员窗格中显示的人员，OSC 获取其 SMTP 地址并哈希，调用[ISocialSession2：：GetActivitiesEx，](isocialsession2-getactivitiesex.md)将 (存储在内存中) 为这些人员返回的活动数据。</span><span class="sxs-lookup"><span data-stu-id="3f885-108">For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md), and stores (in memory) the activities data returned for these persons.</span></span> 
  
### <a name="determining-activities-to-get"></a><span data-ttu-id="3f885-109">确定要获取的活动</span><span class="sxs-lookup"><span data-stu-id="3f885-109">Determining activities to get</span></span>

<span data-ttu-id="3f885-110">传递给 **GetActivitiesEx** 的哈希 SMTP 地址是确定 OSC 是否将获取好友或非好友活动的关键。</span><span class="sxs-lookup"><span data-stu-id="3f885-110">The hashed SMTP addresses passed to **GetActivitiesEx** are the key to determining whether the OSC will get activities for a friend or non-friend.</span></span> <span data-ttu-id="3f885-111">如果某人在社交网络帐户中指定 SMTP 地址，OSC 将获取此人的活动。</span><span class="sxs-lookup"><span data-stu-id="3f885-111">The OSC gets activities for a person if the person specifies that SMTP address in his or her social network account.</span></span> <span data-ttu-id="3f885-112">如果用户的社交网络帐户中未包含该 SMTP 地址，或者此人是好友，但通过社交网络上的不同电子邮件地址， **则 GetActivitiesEx** 不会获取此人的活动。</span><span class="sxs-lookup"><span data-stu-id="3f885-112">If the person does not include that SMTP address in his or her social network account, or if that person is a friend but by a different email address on the social network, **GetActivitiesEx** does not get activities for that person.</span></span> <span data-ttu-id="3f885-113">此外，对于不是好友但指定其社交网络帐户中的 SMTP 地址的人，返回的数据仅包括非好友的隐私设置允许的可用内容。</span><span class="sxs-lookup"><span data-stu-id="3f885-113">Also, for a person who is not a friend but specifies the SMTP addresses in his or her social network account, the data returned includes only what is available to a non-friend as allowed by the privacy settings of that person.</span></span> 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a><span data-ttu-id="3f885-114">为好友和非好友创建测试主题</span><span class="sxs-lookup"><span data-stu-id="3f885-114">Creating test subjects for friends and non-friends</span></span>

<span data-ttu-id="3f885-115">若要为好友创建测试主题，请确定其社交网络帐户中包含该地址的用户的 SMTP 地址，以及该网络上登录用户具有好友状态的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="3f885-115">To create a test subject for a friend, identify the SMTP address of a person who includes that address in his or her social network account and who has a friend status with the logged-on user on that network.</span></span> <span data-ttu-id="3f885-116">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3f885-116">Create an email message that includes that SMTP address.</span></span> <span data-ttu-id="3f885-117">同样，若要为非好友创建测试主题，请通过该地址标识非登录用户好友的用户的 SMTP 地址，以及已使用其隐私设置指定以允许非好友在社交网络上查看其个人资料的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="3f885-117">Similarly, to create a test subject for a non-friend, identify the SMTP address of a person who is not a friend of the logged-on user by that address, and who has specified in his or her privacy settings to allow non-friends to view their profile on the social network.</span></span> <span data-ttu-id="3f885-118">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3f885-118">Create an email message that includes that SMTP address.</span></span> 
  
<span data-ttu-id="3f885-119">在Outlook资源管理器中，选择包含好友或非好友 (的电子邮件时，) 窗格将显示收件人。</span><span class="sxs-lookup"><span data-stu-id="3f885-119">In the Outlook explorer, when you select the email message that includes a friend (or non-friend), the People Pane displays the recipients.</span></span> <span data-ttu-id="3f885-120">在人员 (选择好友或) 联系人，可以测试提供商是否提供有关该人员的信息。</span><span class="sxs-lookup"><span data-stu-id="3f885-120">Selecting the friend (or non-friend) in the People Pane allows you to test that the provider is providing information about the person.</span></span>
  
### <a name="test-scenarios"></a><span data-ttu-id="3f885-121">测试方案</span><span class="sxs-lookup"><span data-stu-id="3f885-121">Test scenarios</span></span>

<span data-ttu-id="3f885-122">若要验证是否正在获取好友和非好友的适当活动，请测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="3f885-122">To verify that you are getting appropriate activities for friends and non-friends, test for the following scenarios.</span></span>
  
|<span data-ttu-id="3f885-123">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="3f885-123">**Scenario**</span></span>|<span data-ttu-id="3f885-124">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="3f885-124">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f885-125">在人员窗格中选择的人是社交网络上登录的用户的好友。</span><span class="sxs-lookup"><span data-stu-id="3f885-125">Person selected in the People Pane is a friend with the logged-on user on the social network.</span></span>  <br/> |<span data-ttu-id="3f885-126">人员窗格在社交网络上显示此人的个人资料和个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="3f885-126">The People Pane displays that person's profile and profile picture as posted on the social network.</span></span>  <br/> |
|<span data-ttu-id="3f885-127">在人员窗格中选择的人是社交网络上已登录用户的非好友，但允许非好友查看其个人资料。</span><span class="sxs-lookup"><span data-stu-id="3f885-127">Person selected in the People Pane is a non-friend of the logged-on user on the social network, but has allowed his or her profile to be viewed by non-friends.</span></span>  <br/> |<span data-ttu-id="3f885-128">人员窗格在社交网络上显示此人的个人资料和个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="3f885-128">The People Pane displays that person's profile and profile picture as posted on the social network.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3f885-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f885-129">See also</span></span>

- [<span data-ttu-id="3f885-130">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="3f885-130">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)  
- [<span data-ttu-id="3f885-131">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="3f885-131">XML for Activities</span></span>](xml-for-activities.md)
- [<span data-ttu-id="3f885-132">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="3f885-132">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

