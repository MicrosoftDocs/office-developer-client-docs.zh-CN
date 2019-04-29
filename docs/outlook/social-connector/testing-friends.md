---
title: 测试好友
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 109c34b6-911b-4dfc-9799-aadf47172e84
description: 本主题介绍测试和方案, 以验证 Outlook Social Connector (.osc) 提供程序是否根据提供程序支持的同步模式, 适当地返回了朋友和非朋友的数据 (如果适用)。
ms.openlocfilehash: 1c97342fd5b219b15b1f58dbc065fc268f8e81d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433666"
---
# <a name="testing-friends"></a><span data-ttu-id="2e1af-103">测试好友</span><span class="sxs-lookup"><span data-stu-id="2e1af-103">Testing friends</span></span>

<span data-ttu-id="2e1af-104">本主题介绍测试和方案, 以验证 Outlook Social Connector (.osc) 提供程序是否根据提供程序支持的同步模式, 适当地返回了朋友和非朋友的数据 (如果适用)。</span><span class="sxs-lookup"><span data-stu-id="2e1af-104">This topic describes tests and scenarios to verify that the Outlook Social Connector (OSC) provider appropriately returns data of friends and non-friends, where applicable, depending on the synchronization mode supported by the provider.</span></span>

<span data-ttu-id="2e1af-105"><a name="olosc_TestingFriends_CachedSync"> </a></span><span class="sxs-lookup"><span data-stu-id="2e1af-105"></span></span>

## <a name="cached-synchronization"></a><span data-ttu-id="2e1af-106">缓存同步</span><span class="sxs-lookup"><span data-stu-id="2e1af-106">Cached synchronization</span></span>

<span data-ttu-id="2e1af-107">一个 .osc 提供程序实现[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md), 其中的 .osc 调用它可确定提供程序是否支持朋友数据的缓存同步。</span><span class="sxs-lookup"><span data-stu-id="2e1af-107">An OSC provider implements [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md), which the OSC calls to determine whether the provider supports cached synchronization of friends' data.</span></span> <span data-ttu-id="2e1af-108">在调用[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)后, .osc 将返回的朋友的数据存储在登录用户的默认 Outlook 存储中的社交网络特定的联系人文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2e1af-108">After calling [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md), the OSC stores the returned friends' data in a contacts folder specific to the social network in the logged-on user's default Outlook store.</span></span> <span data-ttu-id="2e1af-109">此外, .osc 还调用[ISocialSession:: GetPerson](isocialsession-getperson.md)和[ISocialPerson:: GetPicture](isocialperson-getpicture.md)以获取每个朋友的个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="2e1af-109">The OSC also calls [ISocialSession::GetPerson](isocialsession-getperson.md) and [ISocialPerson::GetPicture](isocialperson-getpicture.md) to obtain a profile picture for each friend.</span></span> 
  
### <a name="initiate-synchronization"></a><span data-ttu-id="2e1af-110">启动同步</span><span class="sxs-lookup"><span data-stu-id="2e1af-110">Initiate synchronization</span></span>

<span data-ttu-id="2e1af-111">若要启动同步, 可以在 Microsoft Office 熟知用户界面的功能区组件中打开和使用 "调试" 按钮**同步联系人**。</span><span class="sxs-lookup"><span data-stu-id="2e1af-111">To initiate synchronization, you can turn on and use the debug button **Sync Contacts** in the ribbon component of the Microsoft Office Fluent user interface.</span></span> <span data-ttu-id="2e1af-112">有关 .osc 调试按钮的详细信息, 请参阅[调试提供程序](debugging-a-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="2e1af-112">For more information about OSC debug buttons, see [Debugging a Provider](debugging-a-provider.md).</span></span> 
  
### <a name="test-scenarios"></a><span data-ttu-id="2e1af-113">测试方案</span><span class="sxs-lookup"><span data-stu-id="2e1af-113">Test scenarios</span></span>

<span data-ttu-id="2e1af-114">测试以下项目以验证是否正确缓存了朋友的数据。</span><span class="sxs-lookup"><span data-stu-id="2e1af-114">Test the following items to verify that friends' data is cached correctly.</span></span>
  
|<span data-ttu-id="2e1af-115">**要测试的项**</span><span class="sxs-lookup"><span data-stu-id="2e1af-115">**Item to test**</span></span>|<span data-ttu-id="2e1af-116">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="2e1af-116">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e1af-117">"联系人" 文件夹</span><span class="sxs-lookup"><span data-stu-id="2e1af-117">Contacts folder</span></span>  <br/> |<span data-ttu-id="2e1af-118">用户的默认 Outlook 存储中存在 "社交网络特定的联系人" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e1af-118">The social network-specific contacts folder exists in the user's default Outlook store.</span></span>  <br/> |
|<span data-ttu-id="2e1af-119">由 ISocialPerson 返回的好友数据 **:: GetFriendsAndColleagues**</span><span class="sxs-lookup"><span data-stu-id="2e1af-119">Friends' data returned by **ISocialPerson::GetFriendsAndColleagues**</span></span> <br/> |<span data-ttu-id="2e1af-120">每个朋友对应于特定于网络的 "联系人" 文件夹中的联系人。</span><span class="sxs-lookup"><span data-stu-id="2e1af-120">Each friend corresponds to a contact in the network-specific contacts folder.</span></span>  <br/> |
|<span data-ttu-id="2e1af-121">朋友的数据</span><span class="sxs-lookup"><span data-stu-id="2e1af-121">Friends' data</span></span>  <br/> |<span data-ttu-id="2e1af-122">每个好友的联系人字段都有正确的数据。</span><span class="sxs-lookup"><span data-stu-id="2e1af-122">Contact fields for each friend have the correct data.</span></span>  <br/> |
|<span data-ttu-id="2e1af-123">朋友的个人资料图片由**ISocialPerson 返回:: GetPicture**</span><span class="sxs-lookup"><span data-stu-id="2e1af-123">Friends' profile pictures returned by **ISocialPerson::GetPicture**</span></span> <br/> |<span data-ttu-id="2e1af-124">每个朋友的联系人项目包含个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="2e1af-124">The contact item for each friend contains the profile picture.</span></span>  <br/> |

<span data-ttu-id="2e1af-125"><a name="olosc_TestingFriends_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="2e1af-125"></span></span>

## <a name="on-demand-synchronization"></a><span data-ttu-id="2e1af-126">按需同步</span><span class="sxs-lookup"><span data-stu-id="2e1af-126">On-demand synchronization</span></span>

<span data-ttu-id="2e1af-127">一个 .osc 提供程序实现**ISocialProvider:: GetCapabilities**, 其中的 .osc 调用它可确定提供程序是否支持对朋友和非好友的按需同步。</span><span class="sxs-lookup"><span data-stu-id="2e1af-127">An OSC provider implements **ISocialProvider::GetCapabilities**, which the OSC calls to determine whether the provider supports on-demand synchronization of friends and non-friends.</span></span> <span data-ttu-id="2e1af-128">对于在 Outlook 人员窗格中显示的人员, .osc 获取并散列其 SMTP 地址, 调用[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md), 并存储 (在内存中) 这些人员返回的数据。</span><span class="sxs-lookup"><span data-stu-id="2e1af-128">For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls [ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md), and stores (in memory) the data returned for these persons.</span></span> 
  
### <a name="determining-friends-and-non-friends"></a><span data-ttu-id="2e1af-129">确定朋友和非好友</span><span class="sxs-lookup"><span data-stu-id="2e1af-129">Determining friends and non-friends</span></span>

<span data-ttu-id="2e1af-130">传递给**GetPeopleDetails**的哈希 SMTP 地址是用于确定某人是否为朋友或非朋友的关键。</span><span class="sxs-lookup"><span data-stu-id="2e1af-130">The hashed SMTP addresses passed to **GetPeopleDetails** are the key to determining whether a person is a friend or non-friend.</span></span> <span data-ttu-id="2e1af-131">如果某个人在其社交网络帐户中不包含该 SMTP 地址, 或者即使此人是社交网络中的其他电子邮件地址的朋友, **GetPeopleDetails**仍将此人的**nonfriend**返回为\*\*\*\* _personsCollection_参数中的 friendStatus。</span><span class="sxs-lookup"><span data-stu-id="2e1af-131">If a person does not include that SMTP address in his or her social network account, or even if that person is a friend by a different email address on the social network, **GetPeopleDetails** still returns **nonfriend** for that person as the **friendStatus** in the  _personsCollection_ parameter.</span></span> <span data-ttu-id="2e1af-132">此外, 对于不是友元但在其社交网络帐户中指定了 SMTP 地址的人, 返回的数据只包括该人员的隐私设置允许的非友元所提供的内容。</span><span class="sxs-lookup"><span data-stu-id="2e1af-132">Also, for a person who is not a friend but specifies the SMTP address in his or her social network account, the data returned includes only what is available to a non-friend as allowed by the privacy settings of that person.</span></span> 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a><span data-ttu-id="2e1af-133">为朋友和非好友创建测试主题</span><span class="sxs-lookup"><span data-stu-id="2e1af-133">Creating test subjects for friends and non-friends</span></span>

<span data-ttu-id="2e1af-134">若要为友元创建测试主题, 请确定在其社交网络帐户中包含该地址的人员的 SMTP 地址, 以及该网络上具有登录用户的好友状态。</span><span class="sxs-lookup"><span data-stu-id="2e1af-134">To create a test subject for a friend, identify the SMTP address of a person who includes that address in his or her social network account and who has a friend status with the logged-on user on that network.</span></span> <span data-ttu-id="2e1af-135">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2e1af-135">Create an email message that includes that SMTP address.</span></span> <span data-ttu-id="2e1af-136">同样, 若要为非友元创建测试主题, 请确定该地址不是已登录用户的友元的用户的 SMTP 地址, 并且尚未在他或她的隐私设置中指定的用户, 以允许非朋友在社交 networ 上查看其活动。kb.</span><span class="sxs-lookup"><span data-stu-id="2e1af-136">Similarly, to create a test subject for a non-friend, identify the SMTP address of a person who is not a friend of the logged-on user by that address, and yet who has specified in his or her privacy settings to allow non-friends to view their activities on the social network.</span></span> <span data-ttu-id="2e1af-137">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2e1af-137">Create an email message that includes that SMTP address.</span></span> 
  
<span data-ttu-id="2e1af-138">在 Outlook 资源管理器中, 当您选择包含朋友 (或非好友) 的电子邮件时, "人员" 窗格将显示收件人。</span><span class="sxs-lookup"><span data-stu-id="2e1af-138">In the Outlook explorer, when you select the email message that includes a friend (or non-friend), the People Pane displays the recipients.</span></span> <span data-ttu-id="2e1af-139">通过选择 "人员" 窗格中的好友 (或非好友), 您可以测试提供商是否提供有关此人的信息。</span><span class="sxs-lookup"><span data-stu-id="2e1af-139">Selecting the friend (or non-friend) in the People Pane allows you to test that the provider is providing information about the person.</span></span>
  
### <a name="test-scenarios"></a><span data-ttu-id="2e1af-140">测试方案</span><span class="sxs-lookup"><span data-stu-id="2e1af-140">Test scenarios</span></span>

<span data-ttu-id="2e1af-141">若要验证您的提供商是否已正确提供有关好友和非好友的信息, 请测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="2e1af-141">To verify that your provider is providing information about friends and non-friends appropriately, test for the following scenarios.</span></span>
  
|<span data-ttu-id="2e1af-142">**方案**</span><span class="sxs-lookup"><span data-stu-id="2e1af-142">**Scenario**</span></span>|<span data-ttu-id="2e1af-143">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="2e1af-143">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e1af-144">在 "人员" 窗格中选择的人是社交网络中已登录用户的好友。</span><span class="sxs-lookup"><span data-stu-id="2e1af-144">Person selected in the People Pane is a friend with the logged-on user on the social network.</span></span>  <br/> |<span data-ttu-id="2e1af-145">"人员" 窗格在社交网络上显示此人的活动。</span><span class="sxs-lookup"><span data-stu-id="2e1af-145">The People Pane displays that person's activities on the social network.</span></span>  <br/> |
|<span data-ttu-id="2e1af-146">在 "人员" 窗格中选择的人是社交网络中已登录用户的非朋友, 但允许非好友查看他或她的活动。</span><span class="sxs-lookup"><span data-stu-id="2e1af-146">Person selected in the People Pane is a non-friend of the logged-on user on the social network, but has allowed his or her activities to be viewed by non-friends.</span></span>  <br/> |<span data-ttu-id="2e1af-147">"人员" 窗格在社交网络上显示此人的活动。</span><span class="sxs-lookup"><span data-stu-id="2e1af-147">The People Pane displays that person's activities on the social network.</span></span>  <br/> |

<span data-ttu-id="2e1af-148"><a name="olosc_TestingFriends_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="2e1af-148"></span></span>

## <a name="hybrid-synchronization"></a><span data-ttu-id="2e1af-149">混合同步</span><span class="sxs-lookup"><span data-stu-id="2e1af-149">Hybrid synchronization</span></span>

<span data-ttu-id="2e1af-150">如果 .osc 提供商支持朋友和非好友的混合同步, 则 .osc 将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2e1af-150">If an OSC provider supports hybrid synchronization of friends and non-friends, the OSC does the following:</span></span> 
  
- <span data-ttu-id="2e1af-151">.osc 存储有关特定于社交网络的联系人文件夹中登录用户的好友信息。</span><span class="sxs-lookup"><span data-stu-id="2e1af-151">The OSC stores information for friends of the logged-on user in the social network-specific contact folder.</span></span>
    
- <span data-ttu-id="2e1af-152">.osc 从社交网络检索非朋友的信息, 并将其存储在内存中, 而不是文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2e1af-152">The OSC retrieves information for non-friends on-demand from the social network, and stores it only in memory, but not in a folder.</span></span>
    
<span data-ttu-id="2e1af-153">若要测试混合同步, 请按照针对好友的[缓存的同步](#olosc_TestingFriends_CachedSync)部分中的测试建议, 以及非好友的[点播同步](#olosc_TestingFriends_OnDemandSync)部分中的测试建议。</span><span class="sxs-lookup"><span data-stu-id="2e1af-153">To test hybrid synchronization, follow the testing suggestions in the [Cached Synchronization](#olosc_TestingFriends_CachedSync) section for friends, and those in the [On-Demand Synchronization](#olosc_TestingFriends_OnDemandSync) section for non-friends.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2e1af-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e1af-154">See also</span></span>

- [<span data-ttu-id="2e1af-155">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="2e1af-155">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md) 
- [<span data-ttu-id="2e1af-156">适用于好友的 XML</span><span class="sxs-lookup"><span data-stu-id="2e1af-156">XML for Friends</span></span>](xml-for-friends.md)
- [<span data-ttu-id="2e1af-157">准备发布一个 .osc 提供程序</span><span class="sxs-lookup"><span data-stu-id="2e1af-157">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

