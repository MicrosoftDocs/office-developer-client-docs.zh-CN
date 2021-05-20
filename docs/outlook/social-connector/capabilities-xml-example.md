---
title: 功能 XML 示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: ae1abafe-160c-47c0-b4d5-4a689c8c4cb1
description: 本主题中的 XML 示例是调用社交网络的 ISocialProvider：：GetCapabilities 方法后返回到 Outlook Social Connector (OSC) 的 XML 字符串。 XML 显示 OSC 提供程序如何指定 OSC 的功能和要求。
ms.openlocfilehash: 3340f5b1e0718edd1a062ab817c6621c338bee42
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542259"
---
# <a name="capabilities-xml-example"></a><span data-ttu-id="3202e-104">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="3202e-104">Capabilities XML example</span></span>

<span data-ttu-id="3202e-105">本主题中的 XML 示例是调用社交网络的[ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法后返回到 Outlook Social Connector (OSC) 的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="3202e-105">The XML example in this topic is an XML string returned to the Outlook Social Connector (OSC) after it calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method for a social network.</span></span> <span data-ttu-id="3202e-106">XML 显示 OSC 提供程序如何指定 OSC 的功能和要求。</span><span class="sxs-lookup"><span data-stu-id="3202e-106">The XML shows how an OSC provider specifies its capabilities and requirements for the OSC.</span></span> 
  
## <a name="capabilities-for-friends"></a><span data-ttu-id="3202e-107">好友功能</span><span class="sxs-lookup"><span data-stu-id="3202e-107">Capabilities for friends</span></span>

<span data-ttu-id="3202e-108">在此例中，OSC 提供程序指定以下元素以显示其支持好友功能的功能：</span><span class="sxs-lookup"><span data-stu-id="3202e-108">In this example, the OSC provider specifies the following elements to show its capabilities in supporting the friends feature:</span></span>
  
- <span data-ttu-id="3202e-109">**getFriends** 为 **true，** 表示 OSC 提供程序支持 [ISocialPerson：：GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) 方法以编程方式获取好友的信息。</span><span class="sxs-lookup"><span data-stu-id="3202e-109">**getFriends** as **true** to indicate the OSC provider supports the [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) method to get friends' information programmatically.</span></span> 
    
- <span data-ttu-id="3202e-110">**cacheFriends** as **true，** 以支持将好友的信息缓存到Outlook联系人文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3202e-110">**cacheFriends** as **true** to support caching friends' information in an Outlook contacts folder.</span></span> 
    
- <span data-ttu-id="3202e-111">**contactSyncRestartInterval** 为 60，指示出错时，OSC 应每 60 分钟重试刷新一次缓存。</span><span class="sxs-lookup"><span data-stu-id="3202e-111">**contactSyncRestartInterval** as 60 to indicate that on error, the OSC should retry refreshing the cache every 60 minutes.</span></span> 
    
- <span data-ttu-id="3202e-112">**followPerson** as **true** 指示在社交网络上添加好友的能力。</span><span class="sxs-lookup"><span data-stu-id="3202e-112">**followPerson** as **true** to indicate the ability to add friends on the social network.</span></span> 
    
- <span data-ttu-id="3202e-113">**doNotFollowPerson** 为 **false，** 指示 OSC 提供程序不支持将某人作为好友删除在社交网络上。</span><span class="sxs-lookup"><span data-stu-id="3202e-113">**doNotFollowPerson** as **false** to indicate the OSC provider does not support removing a person as a friend on the social network.</span></span> 
    
- <span data-ttu-id="3202e-114">**dynamicContactsLookup** 为 **false，** 指示 OSC 不应在内存中存储好友的信息。</span><span class="sxs-lookup"><span data-stu-id="3202e-114">**dynamicContactsLookup** as **false** to indicate that the OSC should not store friends' information in memory.</span></span> 
    
## <a name="capabilities-for-activities"></a><span data-ttu-id="3202e-115">活动功能</span><span class="sxs-lookup"><span data-stu-id="3202e-115">Capabilities for activities</span></span>

<span data-ttu-id="3202e-116">OSC 提供程序指定以下元素以显示其支持活动的功能：</span><span class="sxs-lookup"><span data-stu-id="3202e-116">The OSC provider specifies the following elements to show its capability to support activities:</span></span>
  
- <span data-ttu-id="3202e-117">**getActivities** 为 **true，** 指示 OSC 提供程序支持 [ISocialProfile：：GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md) 方法以编程方式获取好友的活动。</span><span class="sxs-lookup"><span data-stu-id="3202e-117">**getActivities** as **true** to indicate that the OSC provider supports the [ISocialProfile::GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md) method to get friends' activities programmatically.</span></span> 
    
- <span data-ttu-id="3202e-118">**cacheActivities** as **false，** 用于支持在隐藏的"新闻源"文件夹中Outlook好友的活动。</span><span class="sxs-lookup"><span data-stu-id="3202e-118">**cacheActivities** as **false** to support caching activities of friends in the hidden Outlook News Feed folder.</span></span> 
    
- <span data-ttu-id="3202e-119">**dynamicActivitiesLookupEx** 为 **true，** 指示 OSC 应在内存中存储好友的活动。</span><span class="sxs-lookup"><span data-stu-id="3202e-119">**dynamicActivitiesLookupEx** as **true** to indicate that the OSC should store friends' activities in memory.</span></span> 
    
## <a name="capabilities-for-authentication-and-account-configuration"></a><span data-ttu-id="3202e-120">身份验证和帐户配置的功能</span><span class="sxs-lookup"><span data-stu-id="3202e-120">Capabilities for authentication and account configuration</span></span>

<span data-ttu-id="3202e-121">OSC 提供程序指定以下元素以显示其对身份验证和帐户配置的支持：</span><span class="sxs-lookup"><span data-stu-id="3202e-121">The OSC provider specifies the following elements to show its support for authentication and account configuration:</span></span>
  
- <span data-ttu-id="3202e-122">**useLogonWebAuth** 为 **false，** 指示 OSC 提供程序支持基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="3202e-122">**useLogonWebAuth** as **false** to indicate that the OSC provider supports basic authentication.</span></span> 
    
- <span data-ttu-id="3202e-123">**supportsAutoConfigure** as **false** to indicate that the OSC should not attempt to automatically configure and log on to the social network for the user.</span><span class="sxs-lookup"><span data-stu-id="3202e-123">**supportsAutoConfigure** as **false** to indicate that the OSC should not attempt to automatically configure and log on to the social network for the user.</span></span> 
    
- <span data-ttu-id="3202e-124">**useLogonCached** 和 **hideRememberMyPassword** 为 **false，** 以指示 OSC 应每次提示输入密码，并且不应使用缓存的登录凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3202e-124">**useLogonCached** and **hideRememberMyPassword** as **false** to indicate that the OSC should prompt for password every time and should not use cached logon credentials to log on.</span></span> 
    
- <span data-ttu-id="3202e-125">**displayUrl** 为 **false，** 指示 OSC 不应在帐户配置对话框中显示社交网络的 URL。</span><span class="sxs-lookup"><span data-stu-id="3202e-125">**displayUrl** as **false** to indicate that the OSC should not display the URL for the social network in the account configuration dialog box.</span></span> 
    
- <span data-ttu-id="3202e-126">**hideHyperlinks** as **false** 指示 OSC 提供程序仅支持具有已知密码的现有帐户，并且 OSC 不应在帐户配置对话框中显示"单击此处创建帐户"和"**忘记** 密码？"超链接。</span><span class="sxs-lookup"><span data-stu-id="3202e-126">**hideHyperlinks** as **false** to indicate that the OSC provider supports only existing accounts with known passwords, and the OSC should not display the **Click here to create an account** and **Forgot your password?** hyperlinks in the account configuration dialog box.</span></span> 
    
## <a name="xml-example"></a><span data-ttu-id="3202e-127">XML 示例</span><span class="sxs-lookup"><span data-stu-id="3202e-127">XML example</span></span>

<span data-ttu-id="3202e-128">以下示例演示 OSC 提供程序的功能 **XML。**</span><span class="sxs-lookup"><span data-stu-id="3202e-128">The following example shows the **capabilities** XML of an OSC provider.</span></span> 
  
```XML
<?xml version="1.0" encoding="utf-8" ?>
<capabilities xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd">
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

## <a name="see-also"></a><span data-ttu-id="3202e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3202e-129">See also</span></span>

- [<span data-ttu-id="3202e-130">OSC 提供程序 XML 示例</span><span class="sxs-lookup"><span data-stu-id="3202e-130">OSC Provider XML Examples</span></span>](osc-provider-xml-examples.md)  
- [<span data-ttu-id="3202e-131">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="3202e-131">XML for Capabilities</span></span>](xml-for-capabilities.md)  
- [<span data-ttu-id="3202e-132">好友 XML 示例</span><span class="sxs-lookup"><span data-stu-id="3202e-132">Friends XML Example</span></span>](friends-xml-example.md)  
- [<span data-ttu-id="3202e-133">活动源 XML 示例</span><span class="sxs-lookup"><span data-stu-id="3202e-133">Activity Feed XML Example</span></span>](activity-feed-xml-example.md)  
- [<span data-ttu-id="3202e-134">OutlookSocial Connector Provider XML 架构</span><span class="sxs-lookup"><span data-stu-id="3202e-134">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)

