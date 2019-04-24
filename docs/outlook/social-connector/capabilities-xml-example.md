---
title: 功能 XML 示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: ae1abafe-160c-47c0-b4d5-4a689c8c4cb1
description: '本主题中的 xml 示例是在调用社交网络的 ISocialProvider:: GetCapabilities 方法后返回到 Outlook Social Connector (.osc) 的 xml 字符串。 XML 显示了 .osc 提供商如何为 .osc 指定其功能和要求。'
ms.openlocfilehash: 53bd250432e7b27d984a846d206adc812c47898f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281228"
---
# <a name="capabilities-xml-example"></a><span data-ttu-id="14030-104">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="14030-104">Capabilities XML example</span></span>

<span data-ttu-id="14030-105">本主题中的 xml 示例是在调用社交网络的[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法后返回到 Outlook Social Connector (.osc) 的 xml 字符串。</span><span class="sxs-lookup"><span data-stu-id="14030-105">The XML example in this topic is an XML string returned to the Outlook Social Connector (OSC) after it calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method for a social network.</span></span> <span data-ttu-id="14030-106">XML 显示了 .osc 提供商如何为 .osc 指定其功能和要求。</span><span class="sxs-lookup"><span data-stu-id="14030-106">The XML shows how an OSC provider specifies its capabilities and requirements for the OSC.</span></span> 
  
## <a name="capabilities-for-friends"></a><span data-ttu-id="14030-107">朋友的功能</span><span class="sxs-lookup"><span data-stu-id="14030-107">Capabilities for friends</span></span>

<span data-ttu-id="14030-108">在此示例中, .osc 提供程序将指定以下元素, 以显示其支持好友功能的功能:</span><span class="sxs-lookup"><span data-stu-id="14030-108">In this example, the OSC provider specifies the following elements to show its capabilities in supporting the friends feature:</span></span>
  
- <span data-ttu-id="14030-109">**getFriends**为**true** , 指示 .osc 提供程序支持[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)方法以编程方式获取友元信息。</span><span class="sxs-lookup"><span data-stu-id="14030-109">**getFriends** as **true** to indicate the OSC provider supports the [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) method to get friends' information programmatically.</span></span> 
    
- <span data-ttu-id="14030-110">**cacheFriends**为**true** , 以支持将朋友的信息缓存在 Outlook 联系人文件夹中。</span><span class="sxs-lookup"><span data-stu-id="14030-110">**cacheFriends** as **true** to support caching friends' information in an Outlook contacts folder.</span></span> 
    
- <span data-ttu-id="14030-111">**contactSyncRestartInterval**为60若要指示在出错时, .osc 应重试每60分钟刷新一次缓存。</span><span class="sxs-lookup"><span data-stu-id="14030-111">**contactSyncRestartInterval** as 60 to indicate that on error, the OSC should retry refreshing the cache every 60 minutes.</span></span> 
    
- <span data-ttu-id="14030-112">**followPerson**为**true** , 指示在社交网络上添加好友的功能。</span><span class="sxs-lookup"><span data-stu-id="14030-112">**followPerson** as **true** to indicate the ability to add friends on the social network.</span></span> 
    
- <span data-ttu-id="14030-113">**doNotFollowPerson**为**false** , 表示 .osc 提供商不支持在社交网络中删除某个人作为好友。</span><span class="sxs-lookup"><span data-stu-id="14030-113">**doNotFollowPerson** as **false** to indicate the OSC provider does not support removing a person as a friend on the social network.</span></span> 
    
- <span data-ttu-id="14030-114">**dynamicContactsLookup**为**false** , 以指示 .osc 不应将朋友的信息存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="14030-114">**dynamicContactsLookup** as **false** to indicate that the OSC should not store friends' information in memory.</span></span> 
    
## <a name="capabilities-for-activities"></a><span data-ttu-id="14030-115">活动的功能</span><span class="sxs-lookup"><span data-stu-id="14030-115">Capabilities for activities</span></span>

<span data-ttu-id="14030-116">.osc 提供程序指定以下元素以显示其支持活动的功能:</span><span class="sxs-lookup"><span data-stu-id="14030-116">The OSC provider specifies the following elements to show its capability to support activities:</span></span>
  
- <span data-ttu-id="14030-117">**getActivities**为**true** , 以指示 .osc 提供程序支持[ISocialProfile:: GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md)方法以编程方式获取朋友的活动。</span><span class="sxs-lookup"><span data-stu-id="14030-117">**getActivities** as **true** to indicate that the OSC provider supports the [ISocialProfile::GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md) method to get friends' activities programmatically.</span></span> 
    
- <span data-ttu-id="14030-118">**cacheActivities**为**false** , 以支持隐藏的 Outlook 新闻源文件夹中的朋友的缓存活动。</span><span class="sxs-lookup"><span data-stu-id="14030-118">**cacheActivities** as **false** to support caching activities of friends in the hidden Outlook News Feed folder.</span></span> 
    
- <span data-ttu-id="14030-119">**dynamicActivitiesLookupEx**为**true** , 以指示 .osc 应将朋友的活动存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="14030-119">**dynamicActivitiesLookupEx** as **true** to indicate that the OSC should store friends' activities in memory.</span></span> 
    
## <a name="capabilities-for-authentication-and-account-configuration"></a><span data-ttu-id="14030-120">身份验证和帐户配置的功能</span><span class="sxs-lookup"><span data-stu-id="14030-120">Capabilities for authentication and account configuration</span></span>

<span data-ttu-id="14030-121">.osc 提供程序指定以下元素, 以显示其对身份验证和帐户配置的支持:</span><span class="sxs-lookup"><span data-stu-id="14030-121">The OSC provider specifies the following elements to show its support for authentication and account configuration:</span></span>
  
- <span data-ttu-id="14030-122">**useLogonWebAuth**为**false** , 以指示 .osc 提供程序支持基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="14030-122">**useLogonWebAuth** as **false** to indicate that the OSC provider supports basic authentication.</span></span> 
    
- <span data-ttu-id="14030-123">**supportsAutoConfigure**为**false** , 以指示 .osc 不应尝试为用户自动配置和登录社交网络。</span><span class="sxs-lookup"><span data-stu-id="14030-123">**supportsAutoConfigure** as **false** to indicate that the OSC should not attempt to automatically configure and log on to the social network for the user.</span></span> 
    
- <span data-ttu-id="14030-124">**useLogonCached**和**hideRememberMyPassword**为**false** , 以指示 .osc 每次都应提示输入密码, 不应使用缓存登录凭据登录。</span><span class="sxs-lookup"><span data-stu-id="14030-124">**useLogonCached** and **hideRememberMyPassword** as **false** to indicate that the OSC should prompt for password every time and should not use cached logon credentials to log on.</span></span> 
    
- <span data-ttu-id="14030-125">**displayUrl**为**false** , 以指示 .osc 不应在 "帐户配置" 对话框中显示社交网络的 URL。</span><span class="sxs-lookup"><span data-stu-id="14030-125">**displayUrl** as **false** to indicate that the OSC should not display the URL for the social network in the account configuration dialog box.</span></span> 
    
- <span data-ttu-id="14030-126">**hideHyperlinks**为**false** , 以指示 .osc 提供商仅支持具有已知密码的现有帐户, 并且 .osc 不应显示 "**单击此处可创建帐户**并**忘记密码？** ""帐户配置" 对话框。</span><span class="sxs-lookup"><span data-stu-id="14030-126">**hideHyperlinks** as **false** to indicate that the OSC provider supports only existing accounts with known passwords, and the OSC should not display the **Click here to create an account** and **Forgot your password?** hyperlinks in the account configuration dialog box.</span></span> 
    
## <a name="xml-example"></a><span data-ttu-id="14030-127">XML 示例</span><span class="sxs-lookup"><span data-stu-id="14030-127">XML example</span></span>

<span data-ttu-id="14030-128">下面的示例演示了一个 .osc 提供程序的**功能**XML。</span><span class="sxs-lookup"><span data-stu-id="14030-128">The following example shows the **capabilities** XML of an OSC provider.</span></span> 
  
```XML
<?xml version="1.0" encoding="utf-8" ?>
<capabilities xmlns="https://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd">
  <getFriends>true</getFriends>
  <cacheFriends>true</cacheFriends>
  <followPerson>true</followPerson>
  <doNotFollowPerson>false</doNotFollowPerson>
  <getActivities>true</getActivities>
  <cacheActivities>false</cacheActivities>
  <displayUrl>false</displayUrl>
  <useLogonWebAuth>false</useLogonWebAuth>
  <hideHyperlinks>false</hideHyperlinks>
  <supportsAutoConfigure>false</supportsAutoConfigure>
  <contactSyncRestartInterval>60</contactSyncRestartInterval>
  <dynamicActivitiesLookupEx>true</dynamicActivitiesLookupEx>
  <dynamicContactsLookup>false</dynamicContactsLookup>
  <useLogonCached>false</useLogonCached>
  <hideRememberMyPassword>false</hideRememberMyPassword>
  <createAccountUrl>https://contoso.com/createAccount</createAccountUrl>
  <forgotPasswordUrl>https://contoso.com/forgotPassword</forgotPasswordUrl>
</capabilities>

```

## <a name="see-also"></a><span data-ttu-id="14030-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14030-129">See also</span></span>

- [<span data-ttu-id="14030-130">.osc 提供程序 XML 示例</span><span class="sxs-lookup"><span data-stu-id="14030-130">OSC Provider XML Examples</span></span>](osc-provider-xml-examples.md)  
- [<span data-ttu-id="14030-131">XML 的功能</span><span class="sxs-lookup"><span data-stu-id="14030-131">XML for Capabilities</span></span>](xml-for-capabilities.md)  
- [<span data-ttu-id="14030-132">友元 XML 示例</span><span class="sxs-lookup"><span data-stu-id="14030-132">Friends XML Example</span></span>](friends-xml-example.md)  
- [<span data-ttu-id="14030-133">活动源 XML 示例</span><span class="sxs-lookup"><span data-stu-id="14030-133">Activity Feed XML Example</span></span>](activity-feed-xml-example.md)  
- [<span data-ttu-id="14030-134">Outlook Social Connector 提供程序 XML 架构</span><span class="sxs-lookup"><span data-stu-id="14030-134">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)

