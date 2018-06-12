---
title: 测试朋友
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 109c34b6-911b-4dfc-9799-aadf47172e84
description: 本主题介绍测试和方案，验证 Outlook Social Connector (OSC) 提供程序适当地返回数据的朋友和非朋友，如果适用，具体取决于提供程序支持的同步模式。
ms.openlocfilehash: 232977836833a9ef981ebef38c9ee243ea2dd2ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779350"
---
# <a name="testing-friends"></a><span data-ttu-id="fae47-103">测试朋友</span><span class="sxs-lookup"><span data-stu-id="fae47-103">Testing friends</span></span>

<span data-ttu-id="fae47-104">本主题介绍测试和方案，验证 Outlook Social Connector (OSC) 提供程序适当地返回数据的朋友和非朋友，如果适用，具体取决于提供程序支持的同步模式。</span><span class="sxs-lookup"><span data-stu-id="fae47-104">This topic describes tests and scenarios to verify that the Outlook Social Connector (OSC) provider appropriately returns data of friends and non-friends, where applicable, depending on the synchronization mode supported by the provider.</span></span>

<span data-ttu-id="fae47-105"><a name="olosc_TestingFriends_CachedSync"> </a></span><span class="sxs-lookup"><span data-stu-id="fae47-105"></span></span>

## <a name="cached-synchronization"></a><span data-ttu-id="fae47-106">高速缓存的同步</span><span class="sxs-lookup"><span data-stu-id="fae47-106">Cached synchronization</span></span>

<span data-ttu-id="fae47-107">OSC 提供程序实现[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)，后者 OSC 调用以确定提供程序是否支持朋友的数据缓存的同步。</span><span class="sxs-lookup"><span data-stu-id="fae47-107">An OSC provider implements [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md), which the OSC calls to determine whether the provider supports cached synchronization of friends' data.</span></span> <span data-ttu-id="fae47-108">调用[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)后, OSC 将返回的朋友的数据存储中特定于登录用户的默认 Outlook 存储区中的社交网络联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="fae47-108">After calling [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md), the OSC stores the returned friends' data in a contacts folder specific to the social network in the logged-on user's default Outlook store.</span></span> <span data-ttu-id="fae47-109">OSC 还调用[ISocialSession::GetPerson](isocialsession-getperson.md)和[ISocialPerson::GetPicture](isocialperson-getpicture.md)来获取每个朋友配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="fae47-109">The OSC also calls [ISocialSession::GetPerson](isocialsession-getperson.md) and [ISocialPerson::GetPicture](isocialperson-getpicture.md) to obtain a profile picture for each friend.</span></span> 
  
### <a name="initiate-synchronization"></a><span data-ttu-id="fae47-110">启动同步</span><span class="sxs-lookup"><span data-stu-id="fae47-110">Initiate synchronization</span></span>

<span data-ttu-id="fae47-111">若要启动同步，您可以打开和使用 Microsoft Office Fluent 用户界面的功能区组件中的调试按钮**同步联系人**。</span><span class="sxs-lookup"><span data-stu-id="fae47-111">To initiate synchronization, you can turn on and use the debug button **Sync Contacts** in the ribbon component of the Microsoft Office Fluent user interface.</span></span> <span data-ttu-id="fae47-112">有关 OSC 调试按钮的详细信息，请参阅[调试提供程序](debugging-a-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="fae47-112">For more information about OSC debug buttons, see [Debugging a Provider](debugging-a-provider.md).</span></span> 
  
### <a name="test-scenarios"></a><span data-ttu-id="fae47-113">测试方案</span><span class="sxs-lookup"><span data-stu-id="fae47-113">Test scenarios</span></span>

<span data-ttu-id="fae47-114">测试以下各项验证朋友的数据缓存正确。</span><span class="sxs-lookup"><span data-stu-id="fae47-114">Test the following items to verify that friends' data is cached correctly.</span></span>
  
|<span data-ttu-id="fae47-115">**要测试项**</span><span class="sxs-lookup"><span data-stu-id="fae47-115">**Item to test**</span></span>|<span data-ttu-id="fae47-116">**预期的行为**</span><span class="sxs-lookup"><span data-stu-id="fae47-116">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fae47-117">联系人文件夹</span><span class="sxs-lookup"><span data-stu-id="fae47-117">Contacts folder</span></span>  <br/> |<span data-ttu-id="fae47-118">用户的默认 Outlook 存储中存在社交网络特定联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="fae47-118">The social network-specific contacts folder exists in the user's default Outlook store.</span></span>  <br/> |
|<span data-ttu-id="fae47-119">返回**ISocialPerson::GetFriendsAndColleagues**朋友的数据</span><span class="sxs-lookup"><span data-stu-id="fae47-119">Friends' data returned by **ISocialPerson::GetFriendsAndColleagues**</span></span> <br/> |<span data-ttu-id="fae47-120">每个朋友对应于特定于网络的联系人文件夹中的联系人。</span><span class="sxs-lookup"><span data-stu-id="fae47-120">Each friend corresponds to a contact in the network-specific contacts folder.</span></span>  <br/> |
|<span data-ttu-id="fae47-121">朋友的数据</span><span class="sxs-lookup"><span data-stu-id="fae47-121">Friends' data</span></span>  <br/> |<span data-ttu-id="fae47-122">为每个朋友联系人字段具有正确的数据。</span><span class="sxs-lookup"><span data-stu-id="fae47-122">Contact fields for each friend have the correct data.</span></span>  <br/> |
|<span data-ttu-id="fae47-123">返回**ISocialPerson::GetPicture**朋友的配置文件图片</span><span class="sxs-lookup"><span data-stu-id="fae47-123">Friends' profile pictures returned by **ISocialPerson::GetPicture**</span></span> <br/> |<span data-ttu-id="fae47-124">联系人项目的每个朋友包含配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="fae47-124">The contact item for each friend contains the profile picture.</span></span>  <br/> |

<span data-ttu-id="fae47-125"><a name="olosc_TestingFriends_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="fae47-125"></span></span>

## <a name="on-demand-synchronization"></a><span data-ttu-id="fae47-126">按需同步</span><span class="sxs-lookup"><span data-stu-id="fae47-126">On-demand synchronization</span></span>

<span data-ttu-id="fae47-127">OSC 提供程序实现**ISocialProvider::GetCapabilities**，后者 OSC 调用以确定提供程序是否支持朋友和非朋友的按需同步。</span><span class="sxs-lookup"><span data-stu-id="fae47-127">An OSC provider implements **ISocialProvider::GetCapabilities**, which the OSC calls to determine whether the provider supports on-demand synchronization of friends and non-friends.</span></span> <span data-ttu-id="fae47-128">在 Outlook 人员窗格中显示的人员，OSC 获取和哈希其 SMTP 地址，调用[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)，并将数据存储 （内存） 中返回这些人员。</span><span class="sxs-lookup"><span data-stu-id="fae47-128">For the persons displayed in the Outlook People Pane, the OSC obtains and hashes their SMTP addresses, calls [ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md), and stores (in memory) the data returned for these persons.</span></span> 
  
### <a name="determining-friends-and-non-friends"></a><span data-ttu-id="fae47-129">确定朋友和非朋友</span><span class="sxs-lookup"><span data-stu-id="fae47-129">Determining friends and non-friends</span></span>

<span data-ttu-id="fae47-130">传递给**GetPeopleDetails**的哈希的 SMTP 地址是确定联系人是否朋友或非朋友的关键。</span><span class="sxs-lookup"><span data-stu-id="fae47-130">The hashed SMTP addresses passed to **GetPeopleDetails** are the key to determining whether a person is a friend or non-friend.</span></span> <span data-ttu-id="fae47-131">如果某人未他/她的社交网络帐户中包含的 SMTP 地址或**GetPeopleDetails**即使这个人正朋友的社交网络上的不同的电子邮件地址，为该人为**仍返回**nonfriend**friendStatus** _personsCollection_参数中。</span><span class="sxs-lookup"><span data-stu-id="fae47-131">If a person does not include that SMTP address in his or her social network account, or even if that person is a friend by a different email address on the social network, **GetPeopleDetails** still returns **nonfriend** for that person as the **friendStatus** in the  _personsCollection_ parameter.</span></span> <span data-ttu-id="fae47-132">此外，对于不朋友但他/她的社交网络帐户中指定的 SMTP 地址的人员，返回的数据包括仅什么是可用于非-朋友允许由该联系人的隐私设置。</span><span class="sxs-lookup"><span data-stu-id="fae47-132">Also, for a person who is not a friend but specifies the SMTP address in his or her social network account, the data returned includes only what is available to a non-friend as allowed by the privacy settings of that person.</span></span> 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a><span data-ttu-id="fae47-133">创建测试主题朋友和非朋友</span><span class="sxs-lookup"><span data-stu-id="fae47-133">Creating test subjects for friends and non-friends</span></span>

<span data-ttu-id="fae47-134">若要创建朋友的测试主题，确定谁他/她的社交网络帐户中包括该地址和谁有朋友状态与登录用户的网络上的人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="fae47-134">To create a test subject for a friend, identify the SMTP address of a person who includes that address in his or her social network account and who has a friend status with the logged-on user on that network.</span></span> <span data-ttu-id="fae47-135">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fae47-135">Create an email message that includes that SMTP address.</span></span> <span data-ttu-id="fae47-136">同样，若要创建非朋友的测试主题，确定某个人的 SMTP 地址用户不是按该地址，登录用户的朋友和谁他/她隐私设置，以允许非朋友以查看其活动上社交网络中具有指定的尚未k。</span><span class="sxs-lookup"><span data-stu-id="fae47-136">Similarly, to create a test subject for a non-friend, identify the SMTP address of a person who is not a friend of the logged-on user by that address, and yet who has specified in his or her privacy settings to allow non-friends to view their activities on the social network.</span></span> <span data-ttu-id="fae47-137">创建包含该 SMTP 地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fae47-137">Create an email message that includes that SMTP address.</span></span> 
  
<span data-ttu-id="fae47-138">在 Outlook 资源管理器中，选择电子邮件，其中包括朋友 （或非朋友） 中，人员窗格中显示的收件人。</span><span class="sxs-lookup"><span data-stu-id="fae47-138">In the Outlook explorer, when you select the email message that includes a friend (or non-friend), the People Pane displays the recipients.</span></span> <span data-ttu-id="fae47-139">在人员窗格中选择的好朋友 （或非朋友） 允许您测试提供程序提供了有关此人的信息。</span><span class="sxs-lookup"><span data-stu-id="fae47-139">Selecting the friend (or non-friend) in the People Pane allows you to test that the provider is providing information about the person.</span></span>
  
### <a name="test-scenarios"></a><span data-ttu-id="fae47-140">测试方案</span><span class="sxs-lookup"><span data-stu-id="fae47-140">Test scenarios</span></span>

<span data-ttu-id="fae47-141">若要验证您的提供商提供信息朋友和非朋友相应地，测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="fae47-141">To verify that your provider is providing information about friends and non-friends appropriately, test for the following scenarios.</span></span>
  
|<span data-ttu-id="fae47-142">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="fae47-142">**Scenario**</span></span>|<span data-ttu-id="fae47-143">**预期的行为**</span><span class="sxs-lookup"><span data-stu-id="fae47-143">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fae47-144">在人员窗格中选择的人员是与社交网络上的登录用户朋友。</span><span class="sxs-lookup"><span data-stu-id="fae47-144">Person selected in the People Pane is a friend with the logged-on user on the social network.</span></span>  <br/> |<span data-ttu-id="fae47-145">人员窗格显示社交网络上的此人的活动。</span><span class="sxs-lookup"><span data-stu-id="fae47-145">The People Pane displays that person's activities on the social network.</span></span>  <br/> |
|<span data-ttu-id="fae47-146">在人员窗格中选择的人员非朋友，登录用户的社交网络中，但已允许通过非朋友查看他/她活动。</span><span class="sxs-lookup"><span data-stu-id="fae47-146">Person selected in the People Pane is a non-friend of the logged-on user on the social network, but has allowed his or her activities to be viewed by non-friends.</span></span>  <br/> |<span data-ttu-id="fae47-147">人员窗格显示社交网络上的此人的活动。</span><span class="sxs-lookup"><span data-stu-id="fae47-147">The People Pane displays that person's activities on the social network.</span></span>  <br/> |

<span data-ttu-id="fae47-148"><a name="olosc_TestingFriends_OnDemandSync"> </a></span><span class="sxs-lookup"><span data-stu-id="fae47-148"></span></span>

## <a name="hybrid-synchronization"></a><span data-ttu-id="fae47-149">混合同步</span><span class="sxs-lookup"><span data-stu-id="fae47-149">Hybrid synchronization</span></span>

<span data-ttu-id="fae47-150">如果 OSC 提供程序支持的朋友和非朋友混合同步，OSC 执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="fae47-150">If an OSC provider supports hybrid synchronization of friends and non-friends, the OSC does the following:</span></span> 
  
- <span data-ttu-id="fae47-151">OSC 社交网络特定联系人文件夹中存储的朋友登录用户的信息。</span><span class="sxs-lookup"><span data-stu-id="fae47-151">The OSC stores information for friends of the logged-on user in the social network-specific contact folder.</span></span>
    
- <span data-ttu-id="fae47-152">OSC 检索社交网络中，为非朋友需求的信息，并将其存储在内存中，但不能在一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="fae47-152">The OSC retrieves information for non-friends on-demand from the social network, and stores it only in memory, but not in a folder.</span></span>
    
<span data-ttu-id="fae47-153">若要测试混合同步，按照为朋友[缓存同步](#olosc_TestingFriends_CachedSync)部分中的测试建议和非朋友[按需同步](#olosc_TestingFriends_OnDemandSync)部分中。</span><span class="sxs-lookup"><span data-stu-id="fae47-153">To test hybrid synchronization, follow the testing suggestions in the [Cached Synchronization](#olosc_TestingFriends_CachedSync) section for friends, and those in the [On-Demand Synchronization](#olosc_TestingFriends_OnDemandSync) section for non-friends.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fae47-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fae47-154">See also</span></span>

- [<span data-ttu-id="fae47-155">同步朋友和活动</span><span class="sxs-lookup"><span data-stu-id="fae47-155">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md) 
- [<span data-ttu-id="fae47-156">朋友 XML</span><span class="sxs-lookup"><span data-stu-id="fae47-156">XML for Friends</span></span>](xml-for-friends.md)
- [<span data-ttu-id="fae47-157">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="fae47-157">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

