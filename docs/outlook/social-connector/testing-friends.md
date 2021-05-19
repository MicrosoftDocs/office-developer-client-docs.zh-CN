---
title: 测试好友
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 109c34b6-911b-4dfc-9799-aadf47172e84
description: 本主题介绍用于验证 Outlook Social Connector (OSC) 提供程序是否适当返回好友和非好友的数据的测试和方案（如果适用，具体取决于提供程序支持的同步模式）。
ms.openlocfilehash: 1c97342fd5b219b15b1f58dbc065fc268f8e81d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433666"
---
# <a name="testing-friends"></a><span data-ttu-id="6892a-103">测试好友</span><span class="sxs-lookup"><span data-stu-id="6892a-103">Testing friends</span></span>

<span data-ttu-id="6892a-104">本主题介绍用于验证 Outlook Social Connector (OSC) 提供程序是否适当返回好友和非好友的数据的测试和方案（如果适用，具体取决于提供程序支持的同步模式）。</span><span class="sxs-lookup"><span data-stu-id="6892a-104">This topic describes tests and scenarios to verify that the Outlook Social Connector (OSC) provider appropriately returns data of friends and non-friends, where applicable, depending on the synchronization mode supported by the provider.</span></span>

<span data-ttu-id="6892a-105"><a name="olosc_TestingFriends_CachedSync"> </a></span><span class="sxs-lookup"><span data-stu-id="6892a-105"><a name="olosc_TestingFriends_CachedSync"> </a></span></span>

## <a name="cached-synchronization"></a><span data-ttu-id="6892a-106">缓存同步</span><span class="sxs-lookup"><span data-stu-id="6892a-106">Cached synchronization</span></span>

<span data-ttu-id="6892a-107">OSC 提供程序实现 [ISocialProvider：：GetCapabilities，OSC](isocialprovider-getcapabilities.md)将调用它来确定提供程序是否支持好友数据的缓存同步。</span><span class="sxs-lookup"><span data-stu-id="6892a-107">An OSC provider implements [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md), which the OSC calls to determine whether the provider supports cached synchronization of friends' data.</span></span> <span data-ttu-id="6892a-108">调用[ISocialPerson：：GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)后，OSC 将返回的好友数据存储在已登录用户的默认 Outlook 存储中特定于社交网络的联系人文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6892a-108">After calling [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md), the OSC stores the returned friends' data in a contacts folder specific to the social network in the logged-on user's default Outlook store.</span></span> <span data-ttu-id="6892a-109">OSC 还调用 [ISocialSession：：GetPerson](isocialsession-getperson.md) 和 [ISocialPerson：：GetPicture](isocialperson-getpicture.md) 以获取每个好友的个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="6892a-109">The OSC also calls [ISocialSession::GetPerson](isocialsession-getperson.md) and [ISocialPerson::GetPicture](isocialperson-getpicture.md) to obtain a profile picture for each friend.</span></span> 
  
### <a name="initiate-synchronization"></a><span data-ttu-id="6892a-110">启动同步</span><span class="sxs-lookup"><span data-stu-id="6892a-110">Initiate synchronization</span></span>

<span data-ttu-id="6892a-111">若要启动同步，您可以打开并使用调试按钮 **Sync Contacts** in the ribbon component of the Microsoft Office Fluent user interface.</span><span class="sxs-lookup"><span data-stu-id="6892a-111">To initiate synchronization, you can turn on and use the debug button **Sync Contacts** in the ribbon component of the Microsoft Office Fluent user interface.</span></span> <span data-ttu-id="6892a-112">有关 OSC 调试按钮详细信息，请参阅 [调试提供程序](debugging-a-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="6892a-112">For more information about OSC debug buttons, see [Debugging a Provider](debugging-a-provider.md).</span></span> 
  
### <a name="test-scenarios"></a><span data-ttu-id="6892a-113">测试方案</span><span class="sxs-lookup"><span data-stu-id="6892a-113">Test scenarios</span></span>

<span data-ttu-id="6892a-114">测试以下项以验证好友的数据是否缓存正确。</span><span class="sxs-lookup"><span data-stu-id="6892a-114">Test the following items to verify that friends' data is cached correctly.</span></span>
  
|<span data-ttu-id="6892a-115">**要测试的项目**</span><span class="sxs-lookup"><span data-stu-id="6892a-115">**Item to test**</span></span>|<span data-ttu-id="6892a-116">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="6892a-116">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6892a-117">"联系人"文件夹</span><span class="sxs-lookup"><span data-stu-id="6892a-117">Contacts folder</span></span>  <br/> |<span data-ttu-id="6892a-118">特定于社交网络的联系人文件夹位于用户的默认联系人Outlook存储区中。</span><span class="sxs-lookup"><span data-stu-id="6892a-118">The social network-specific contacts folder exists in the user's default Outlook store.</span></span>  <br/> |
|<span data-ttu-id="6892a-119">**ISocialPerson：：GetFriendsAndColleagues** 返回的好友数据</span><span class="sxs-lookup"><span data-stu-id="6892a-119">Friends' data returned by **ISocialPerson::GetFriendsAndColleagues**</span></span> <br/> |<span data-ttu-id="6892a-120">每个好友对应于特定于网络的联系人文件夹中的一个联系人。</span><span class="sxs-lookup"><span data-stu-id="6892a-120">Each friend corresponds to a contact in the network-specific contacts folder.</span></span>  <br/> |
|<span data-ttu-id="6892a-121">好友数据</span><span class="sxs-lookup"><span data-stu-id="6892a-121">Friends' data</span></span>  <br/> |<span data-ttu-id="6892a-122">每个好友的联系人字段具有正确的数据。</span><span class="sxs-lookup"><span data-stu-id="6892a-122">Contact fields for each friend have the correct data.</span></span>  <br/> |
|<span data-ttu-id="6892a-123">**ISocialPerson：：GetPicture** 返回的好友个人资料图片</span><span class="sxs-lookup"><span data-stu-id="6892a-123">Friends' profile pictures returned by **ISocialPerson::GetPicture**</span></span> <br/> |<span data-ttu-id="6892a-124">每个好友的联系人项目都包含个人资料图片。</span><span class="sxs-lookup"><span data-stu-id="6892a-124">The contact item for each friend contains the profile picture.</span></span>  <br/> |

<span data-ttu-id="6892a-125"><a name="olosc_TestingFriends_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="6892a-125"><a name="olosc_TestingFriends_OnDemandSync"> </a></span></span>

## <a name="on-demand-synchronization"></a><span data-ttu-id="6892a-126">按需同步</span><span class="sxs-lookup"><span data-stu-id="6892a-126">On-demand synchronization</span></span>

<span data-ttu-id="6892a-127">OSC 提供程序实现 **ISocialProvider：：GetCapabilities，OSC** 将调用它以确定提供程序是否支持好友和非好友的按需同步。</span><span class="sxs-lookup"><span data-stu-id="6892a-127">An OSC provider implements **ISocialProvider::GetCapabilities**, which the OSC calls to determine whether the provider supports on-demand synchronization of friends and non-friends.</span></span> <span data-ttu-id="6892a-128">对于 Outlook 人员窗格中显示的人员，OSC 获取其 SMTP 地址并哈希，调用[ISocialSession2：：GetPeopleDetails，](isocialsession2-getpeopledetails.md)将 (存储在内存中) 为这些人员返回的数据。</span><span class="sxs-lookup"><span data-stu-id="6892a-128">For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls [ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md), and stores (in memory) the data returned for these persons.</span></span> 
  
### <a name="determining-friends-and-non-friends"></a><span data-ttu-id="6892a-129">确定好友和非好友</span><span class="sxs-lookup"><span data-stu-id="6892a-129">Determining friends and non-friends</span></span>

<span data-ttu-id="6892a-130">传递给 **GetPeopleDetails** 的哈希 SMTP 地址是确定某个人是好友还是非好友的关键。</span><span class="sxs-lookup"><span data-stu-id="6892a-130">The hashed SMTP addresses passed to **GetPeopleDetails** are the key to determining whether a person is a friend or non-friend.</span></span> <span data-ttu-id="6892a-131">如果某人的社交网络帐户中未包含该 SMTP 地址，或者即使此人是社交网络上其他电子邮件地址的好友 **，GetPeopleDetails** 仍将此人的不好友作为 _personCollection_ 参数中的 **friendStatus** 返回。 </span><span class="sxs-lookup"><span data-stu-id="6892a-131">If a person does not include that SMTP address in his or her social network account, or even if that person is a friend by a different email address on the social network, **GetPeopleDetails** still returns **nonfriend** for that person as the **friendStatus** in the  _personsCollection_ parameter.</span></span> <span data-ttu-id="6892a-132">此外，对于不是好友但在社交网络帐户中指定 SMTP 地址的人，返回的数据仅包括非好友的隐私设置允许的可用内容。</span><span class="sxs-lookup"><span data-stu-id="6892a-132">Also, for a person who is not a friend but specifies the SMTP address in his or her social network account, the data returned includes only what is available to a non-friend as allowed by the privacy settings of that person.</span></span> 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a><span data-ttu-id="6892a-133">为好友和非好友创建测试主题</span><span class="sxs-lookup"><span data-stu-id="6892a-133">Creating test subjects for friends and non-friends</span></span>

<span data-ttu-id="6892a-134">若要为好友创建测试主题，请确定其社交网络帐户中包含该地址的用户的 SMTP 地址，以及该网络上登录用户具有好友状态的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="6892a-134">To create a test subject for a friend, identify the SMTP address of a person who includes that address in his or her social network account and who has a friend status with the logged-on user on that network.</span></span> <span data-ttu-id="6892a-135">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6892a-135">Create an email message that includes that SMTP address.</span></span> <span data-ttu-id="6892a-136">同样，若要为非好友创建测试主题，请通过该地址标识非登录用户好友的用户的 SMTP 地址，以及已使用其隐私设置指定以允许非好友查看其社交网络上的活动的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="6892a-136">Similarly, to create a test subject for a non-friend, identify the SMTP address of a person who is not a friend of the logged-on user by that address, and yet who has specified in his or her privacy settings to allow non-friends to view their activities on the social network.</span></span> <span data-ttu-id="6892a-137">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6892a-137">Create an email message that includes that SMTP address.</span></span> 
  
<span data-ttu-id="6892a-138">在Outlook资源管理器中，选择包含好友或非好友 (的电子邮件时，) 窗格将显示收件人。</span><span class="sxs-lookup"><span data-stu-id="6892a-138">In the Outlook explorer, when you select the email message that includes a friend (or non-friend), the People Pane displays the recipients.</span></span> <span data-ttu-id="6892a-139">在人员 (选择好友或) 联系人，可以测试提供商是否提供有关该人员的信息。</span><span class="sxs-lookup"><span data-stu-id="6892a-139">Selecting the friend (or non-friend) in the People Pane allows you to test that the provider is providing information about the person.</span></span>
  
### <a name="test-scenarios"></a><span data-ttu-id="6892a-140">测试方案</span><span class="sxs-lookup"><span data-stu-id="6892a-140">Test scenarios</span></span>

<span data-ttu-id="6892a-141">若要验证你的提供商是否适当地提供有关好友和非好友的信息，请测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="6892a-141">To verify that your provider is providing information about friends and non-friends appropriately, test for the following scenarios.</span></span>
  
|<span data-ttu-id="6892a-142">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="6892a-142">**Scenario**</span></span>|<span data-ttu-id="6892a-143">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="6892a-143">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6892a-144">在人员窗格中选择的人是社交网络上登录的用户的好友。</span><span class="sxs-lookup"><span data-stu-id="6892a-144">Person selected in the People Pane is a friend with the logged-on user on the social network.</span></span>  <br/> |<span data-ttu-id="6892a-145">人员窗格在社交网络上显示此人的活动。</span><span class="sxs-lookup"><span data-stu-id="6892a-145">The People Pane displays that person's activities on the social network.</span></span>  <br/> |
|<span data-ttu-id="6892a-146">在人员窗格中选择的用户是社交网络上已登录用户的非好友，但允许非好友查看其活动。</span><span class="sxs-lookup"><span data-stu-id="6892a-146">Person selected in the People Pane is a non-friend of the logged-on user on the social network, but has allowed his or her activities to be viewed by non-friends.</span></span>  <br/> |<span data-ttu-id="6892a-147">人员窗格在社交网络上显示此人的活动。</span><span class="sxs-lookup"><span data-stu-id="6892a-147">The People Pane displays that person's activities on the social network.</span></span>  <br/> |

<span data-ttu-id="6892a-148"><a name="olosc_TestingFriends_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="6892a-148"><a name="olosc_TestingFriends_OnDemandSync"> </a></span></span>

## <a name="hybrid-synchronization"></a><span data-ttu-id="6892a-149">混合同步</span><span class="sxs-lookup"><span data-stu-id="6892a-149">Hybrid synchronization</span></span>

<span data-ttu-id="6892a-150">如果 OSC 提供程序支持好友和非好友的混合同步，OSC 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6892a-150">If an OSC provider supports hybrid synchronization of friends and non-friends, the OSC does the following:</span></span> 
  
- <span data-ttu-id="6892a-151">OSC 将登录用户的好友信息存储在特定于社交网络的联系人文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6892a-151">The OSC stores information for friends of the logged-on user in the social network-specific contact folder.</span></span>
    
- <span data-ttu-id="6892a-152">OSC 从社交网络检索非好友按需信息，并仅将该信息存储在内存中，而不是存储在文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6892a-152">The OSC retrieves information for non-friends on-demand from the social network, and stores it only in memory, but not in a folder.</span></span>
    
<span data-ttu-id="6892a-153">若要测试混合同步，请按照"缓存同步"部分（[](#olosc_TestingFriends_CachedSync)对于好友）和非好友的"按需同步"部分[](#olosc_TestingFriends_OnDemandSync)中的测试建议操作。</span><span class="sxs-lookup"><span data-stu-id="6892a-153">To test hybrid synchronization, follow the testing suggestions in the [Cached Synchronization](#olosc_TestingFriends_CachedSync) section for friends, and those in the [On-Demand Synchronization](#olosc_TestingFriends_OnDemandSync) section for non-friends.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6892a-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6892a-154">See also</span></span>

- [<span data-ttu-id="6892a-155">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="6892a-155">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md) 
- [<span data-ttu-id="6892a-156">好友 XML</span><span class="sxs-lookup"><span data-stu-id="6892a-156">XML for Friends</span></span>](xml-for-friends.md)
- [<span data-ttu-id="6892a-157">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="6892a-157">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

