---
title: 功能 XML 示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: ae1abafe-160c-47c0-b4d5-4a689c8c4cb1
description: 本主题中的 XML 示例是一个 XML 字符串，它为社交网络调用 ISocialProvider::GetCapabilities 方法后，返回到 Outlook Social Connector (OSC)。 XML 演示如何 OSC 提供程序指定其功能和要求 OSC。
ms.openlocfilehash: 5cafd6d29de8b4357e9e0ce6dab30b125f53b8ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779204"
---
# <a name="capabilities-xml-example"></a><span data-ttu-id="b5924-104">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="b5924-104">Capabilities XML example</span></span>

<span data-ttu-id="b5924-105">本主题中的 XML 示例是一个 XML 字符串，它为社交网络调用[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法后，返回到 Outlook Social Connector (OSC)。</span><span class="sxs-lookup"><span data-stu-id="b5924-105">The XML example in this topic is an XML string returned to the Outlook Social Connector (OSC) after it calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method for a social network.</span></span> <span data-ttu-id="b5924-106">XML 演示如何 OSC 提供程序指定其功能和要求 OSC。</span><span class="sxs-lookup"><span data-stu-id="b5924-106">The XML shows how an OSC provider specifies its capabilities and requirements for the OSC.</span></span> 
  
## <a name="capabilities-for-friends"></a><span data-ttu-id="b5924-107">朋友的功能</span><span class="sxs-lookup"><span data-stu-id="b5924-107">Capabilities for friends</span></span>

<span data-ttu-id="b5924-108">本示例中，OSC 提供程序指定要支持朋友功能中显示其功能的以下元素：</span><span class="sxs-lookup"><span data-stu-id="b5924-108">In this example, the OSC provider specifies the following elements to show its capabilities in supporting the friends feature:</span></span>
  
- <span data-ttu-id="b5924-109">**getFriends**为**true**以指明 OSC 提供程序支持[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)方法以编程方式获取朋友的信息。</span><span class="sxs-lookup"><span data-stu-id="b5924-109">**getFriends** as **true** to indicate the OSC provider supports the [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) method to get friends' information programmatically.</span></span> 
    
- <span data-ttu-id="b5924-110">为**true**以支持在 Outlook 联系人文件夹中的缓存朋友信息**cacheFriends** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-110">**cacheFriends** as **true** to support caching friends' information in an Outlook contacts folder.</span></span> 
    
- <span data-ttu-id="b5924-111">为 60 表示该上错误**contactSyncRestartInterval** ，OSC 应该重试刷新缓存每隔 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="b5924-111">**contactSyncRestartInterval** as 60 to indicate that on error, the OSC should retry refreshing the cache every 60 minutes.</span></span> 
    
- <span data-ttu-id="b5924-112">为**true**以指明添加朋友社交网络上的功能**followPerson** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-112">**followPerson** as **true** to indicate the ability to add friends on the social network.</span></span> 
    
- <span data-ttu-id="b5924-113">**doNotFollowPerson**为**false**以指明 OSC 提供程序不支持删除为朋友社交网络上的某个人。</span><span class="sxs-lookup"><span data-stu-id="b5924-113">**doNotFollowPerson** as **false** to indicate the OSC provider does not support removing a person as a friend on the social network.</span></span> 
    
- <span data-ttu-id="b5924-114">为**false**以指明 OSC 不应在内存中存储朋友的信息**dynamicContactsLookup** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-114">**dynamicContactsLookup** as **false** to indicate that the OSC should not store friends' information in memory.</span></span> 
    
## <a name="capabilities-for-activities"></a><span data-ttu-id="b5924-115">活动的功能</span><span class="sxs-lookup"><span data-stu-id="b5924-115">Capabilities for activities</span></span>

<span data-ttu-id="b5924-116">OSC 提供程序指定要显示其功能支持活动的以下元素：</span><span class="sxs-lookup"><span data-stu-id="b5924-116">The OSC provider specifies the following elements to show its capability to support activities:</span></span>
  
- <span data-ttu-id="b5924-117">为**true**以指明 OSC 提供程序支持[ISocialProfile::GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md)方法以编程方式获取朋友的活动**getActivities** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-117">**getActivities** as **true** to indicate that the OSC provider supports the [ISocialProfile::GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md) method to get friends' activities programmatically.</span></span> 
    
- <span data-ttu-id="b5924-118">为**false**以隐藏 Outlook 新闻源文件夹中支持的朋友缓存活动**cacheActivities** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-118">**cacheActivities** as **false** to support caching activities of friends in the hidden Outlook News Feed folder.</span></span> 
    
- <span data-ttu-id="b5924-119">为**true**以指明 OSC 应在内存中存储朋友的活动**dynamicActivitiesLookupEx** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-119">**dynamicActivitiesLookupEx** as **true** to indicate that the OSC should store friends' activities in memory.</span></span> 
    
## <a name="capabilities-for-authentication-and-account-configuration"></a><span data-ttu-id="b5924-120">身份验证和帐户配置的功能</span><span class="sxs-lookup"><span data-stu-id="b5924-120">Capabilities for authentication and account configuration</span></span>

<span data-ttu-id="b5924-121">OSC 提供程序指定要显示其支持的身份验证和帐户配置的以下元素：</span><span class="sxs-lookup"><span data-stu-id="b5924-121">The OSC provider specifies the following elements to show its support for authentication and account configuration:</span></span>
  
- <span data-ttu-id="b5924-122">为**false**以指示 OSC 提供程序支持基本身份验证**useLogonWebAuth** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-122">**useLogonWebAuth** as **false** to indicate that the OSC provider supports basic authentication.</span></span> 
    
- <span data-ttu-id="b5924-123">为**false**以指明 OSC 不应尝试自动配置和登录到用户社交网络**supportsAutoConfigure** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-123">**supportsAutoConfigure** as **false** to indicate that the OSC should not attempt to automatically configure and log on to the social network for the user.</span></span> 
    
- <span data-ttu-id="b5924-124">**useLogonCached**和**hideRememberMyPassword**为**false**以指示 OSC 应提示输入密码每次时，不应使用缓存登录凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b5924-124">**useLogonCached** and **hideRememberMyPassword** as **false** to indicate that the OSC should prompt for password every time and should not use cached logon credentials to log on.</span></span> 
    
- <span data-ttu-id="b5924-125">为**false**以指明 OSC 帐户配置对话框应不显示社交网络的 URL **displayUrl** 。</span><span class="sxs-lookup"><span data-stu-id="b5924-125">**displayUrl** as **false** to indicate that the OSC should not display the URL for the social network in the account configuration dialog box.</span></span> 
    
- <span data-ttu-id="b5924-126">为**false**以指示 OSC 提供程序支持仅现有帐户与已知密码和 OSC 不应显示**创建一个帐户，请单击此处** **hideHyperlinks**和**忘记密码？** 中的超链接帐户配置对话框。</span><span class="sxs-lookup"><span data-stu-id="b5924-126">**hideHyperlinks** as **false** to indicate that the OSC provider supports only existing accounts with known passwords, and the OSC should not display the **Click here to create an account** and **Forgot your password?** hyperlinks in the account configuration dialog box.</span></span> 
    
## <a name="xml-example"></a><span data-ttu-id="b5924-127">XML 示例</span><span class="sxs-lookup"><span data-stu-id="b5924-127">XML example</span></span>

<span data-ttu-id="b5924-128">下面的示例演示**功能**的 OSC 提供程序的 XML。</span><span class="sxs-lookup"><span data-stu-id="b5924-128">The following example shows the **capabilities** XML of an OSC provider.</span></span> 
  
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
  <createAccountUrl>http://contoso.com/createAccount</createAccountUrl>
  <forgotPasswordUrl>http://contoso.com/forgotPassword</forgotPasswordUrl>
</capabilities>

```

## <a name="see-also"></a><span data-ttu-id="b5924-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5924-129">See also</span></span>

- [<span data-ttu-id="b5924-130">OSC 提供程序 XML 示例</span><span class="sxs-lookup"><span data-stu-id="b5924-130">OSC Provider XML Examples</span></span>](osc-provider-xml-examples.md)  
- [<span data-ttu-id="b5924-131">功能 XML</span><span class="sxs-lookup"><span data-stu-id="b5924-131">XML for Capabilities</span></span>](xml-for-capabilities.md)  
- [<span data-ttu-id="b5924-132">朋友 XML 示例</span><span class="sxs-lookup"><span data-stu-id="b5924-132">Friends XML Example</span></span>](friends-xml-example.md)  
- [<span data-ttu-id="b5924-133">活动源的 XML 示例</span><span class="sxs-lookup"><span data-stu-id="b5924-133">Activity Feed XML Example</span></span>](activity-feed-xml-example.md)  
- [<span data-ttu-id="b5924-134">Outlook Social Connector 提供程序的 XML 架构</span><span class="sxs-lookup"><span data-stu-id="b5924-134">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)

