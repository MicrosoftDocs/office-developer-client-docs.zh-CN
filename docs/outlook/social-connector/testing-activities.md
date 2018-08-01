---
title: 测试活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 98343c36-5e32-4d07-b474-adfeca693135
description: 本主题介绍测试和验证 Outlook Social Connector (OSC) 提供程序使用按需同步适当地返回活动的朋友和非朋友组成的方案。
ms.openlocfilehash: 82d24b106e8d429d20a2d396eb60155cbb95f91f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779335"
---
# <a name="testing-activities"></a><span data-ttu-id="0013d-103">测试活动</span><span class="sxs-lookup"><span data-stu-id="0013d-103">Testing activities</span></span>

<span data-ttu-id="0013d-104">本主题介绍测试和验证 Outlook Social Connector (OSC) 提供程序使用按需同步适当地返回活动的朋友和非朋友组成的方案。</span><span class="sxs-lookup"><span data-stu-id="0013d-104">This topic describes tests and scenarios to verify that the Outlook Social Connector (OSC) provider uses on-demand synchronization to appropriately return activities of friends and non-friends.</span></span>

<span data-ttu-id="0013d-105"><a name="olosc_TestingActivities_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="0013d-105"></span></span>

## <a name="on-demand-synchronization"></a><span data-ttu-id="0013d-106">按需同步</span><span class="sxs-lookup"><span data-stu-id="0013d-106">On-demand synchronization</span></span>

<span data-ttu-id="0013d-107">OSC 提供程序实现**ISocialProvider::GetCapabilities**，后者 OSC 调用以确定提供程序是否支持活动的朋友和非朋友组成的按需同步。</span><span class="sxs-lookup"><span data-stu-id="0013d-107">An OSC provider implements **ISocialProvider::GetCapabilities**, which the OSC calls to determine whether the provider supports on-demand synchronization of activities of friends and non-friends.</span></span> <span data-ttu-id="0013d-108">在 Outlook 人员窗格中显示的人员，OSC 获取和哈希其 SMTP 地址，调用[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)，并将活动数据存储 （内存） 中返回这些人员。</span><span class="sxs-lookup"><span data-stu-id="0013d-108">For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md), and stores (in memory) the activities data returned for these persons.</span></span> 
  
### <a name="determining-activities-to-get"></a><span data-ttu-id="0013d-109">确定要获取的活动</span><span class="sxs-lookup"><span data-stu-id="0013d-109">Determining activities to get</span></span>

<span data-ttu-id="0013d-110">传递给**GetActivitiesEx**的哈希的 SMTP 地址是确定 OSC 是否会收到的朋友或非朋友活动的关键。</span><span class="sxs-lookup"><span data-stu-id="0013d-110">The hashed SMTP addresses passed to **GetActivitiesEx** are the key to determining whether the OSC will get activities for a friend or non-friend.</span></span> <span data-ttu-id="0013d-111">OSC 获取活动的人员，如果此人他/她的社交网络帐户中指定的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="0013d-111">The OSC gets activities for a person if the person specifies that SMTP address in his or her social network account.</span></span> <span data-ttu-id="0013d-112">如果此人不包含的 SMTP 地址中他/她的社交网络帐户，或如果这个人正朋友但社交网络上不同的电子邮件地址， **GetActivitiesEx**不会活动的人员。</span><span class="sxs-lookup"><span data-stu-id="0013d-112">If the person does not include that SMTP address in his or her social network account, or if that person is a friend but by a different email address on the social network, **GetActivitiesEx** does not get activities for that person.</span></span> <span data-ttu-id="0013d-113">此外，对于不朋友但他/她的社交网络帐户中指定的 SMTP 地址的人员，返回的数据包括仅什么是可用于非-朋友允许由该联系人的隐私设置。</span><span class="sxs-lookup"><span data-stu-id="0013d-113">Also, for a person who is not a friend but specifies the SMTP addresses in his or her social network account, the data returned includes only what is available to a non-friend as allowed by the privacy settings of that person.</span></span> 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a><span data-ttu-id="0013d-114">创建测试主题朋友和非朋友</span><span class="sxs-lookup"><span data-stu-id="0013d-114">Creating test subjects for friends and non-friends</span></span>

<span data-ttu-id="0013d-115">若要创建朋友的测试主题，确定谁他/她的社交网络帐户中包括该地址和谁有朋友状态与登录用户的网络上的人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="0013d-115">To create a test subject for a friend, identify the SMTP address of a person who includes that address in his or her social network account and who has a friend status with the logged-on user on that network.</span></span> <span data-ttu-id="0013d-116">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0013d-116">Create an email message that includes that SMTP address.</span></span> <span data-ttu-id="0013d-117">同样，若要创建非朋友的测试主题，确定谁不是按该地址，登录用户的朋友和谁具有他/她隐私设置，以允许非朋友社交网络上查看其配置文件中指定的人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="0013d-117">Similarly, to create a test subject for a non-friend, identify the SMTP address of a person who is not a friend of the logged-on user by that address, and who has specified in his or her privacy settings to allow non-friends to view their profile on the social network.</span></span> <span data-ttu-id="0013d-118">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0013d-118">Create an email message that includes that SMTP address.</span></span> 
  
<span data-ttu-id="0013d-119">在 Outlook 资源管理器中，选择电子邮件，其中包括朋友 （或非朋友） 中，人员窗格中显示的收件人。</span><span class="sxs-lookup"><span data-stu-id="0013d-119">In the Outlook explorer, when you select the email message that includes a friend (or non-friend), the People Pane displays the recipients.</span></span> <span data-ttu-id="0013d-120">在人员窗格中选择的好朋友 （或非朋友） 允许您测试提供程序提供了有关此人的信息。</span><span class="sxs-lookup"><span data-stu-id="0013d-120">Selecting the friend (or non-friend) in the People Pane allows you to test that the provider is providing information about the person.</span></span>
  
### <a name="test-scenarios"></a><span data-ttu-id="0013d-121">测试方案</span><span class="sxs-lookup"><span data-stu-id="0013d-121">Test scenarios</span></span>

<span data-ttu-id="0013d-122">若要验证您朋友和非朋友得到适当的活动，测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="0013d-122">To verify that you are getting appropriate activities for friends and non-friends, test for the following scenarios.</span></span>
  
|<span data-ttu-id="0013d-123">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="0013d-123">**Scenario**</span></span>|<span data-ttu-id="0013d-124">**预期的行为**</span><span class="sxs-lookup"><span data-stu-id="0013d-124">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0013d-125">在人员窗格中选择的人员是与社交网络上的登录用户朋友。</span><span class="sxs-lookup"><span data-stu-id="0013d-125">Person selected in the People Pane is a friend with the logged-on user on the social network.</span></span>  <br/> |<span data-ttu-id="0013d-126">人员窗格显示此人的配置文件和社交网络上发布配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="0013d-126">The People Pane displays that person's profile and profile picture as posted on the social network.</span></span>  <br/> |
|<span data-ttu-id="0013d-127">在人员窗格中选择的人员非朋友，登录用户的社交网络中，但已允许他/她非朋友通过查看的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0013d-127">Person selected in the People Pane is a non-friend of the logged-on user on the social network, but has allowed his or her profile to be viewed by non-friends.</span></span>  <br/> |<span data-ttu-id="0013d-128">人员窗格显示此人的配置文件和社交网络上发布配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="0013d-128">The People Pane displays that person's profile and profile picture as posted on the social network.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0013d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0013d-129">See also</span></span>

- [<span data-ttu-id="0013d-130">同步朋友和活动</span><span class="sxs-lookup"><span data-stu-id="0013d-130">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)  
- [<span data-ttu-id="0013d-131">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="0013d-131">XML for Activities</span></span>](xml-for-activities.md)
- [<span data-ttu-id="0013d-132">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="0013d-132">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

