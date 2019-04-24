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
# <a name="capabilities-xml-example"></a>功能 XML 示例

本主题中的 xml 示例是在调用社交网络的[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法后返回到 Outlook Social Connector (.osc) 的 xml 字符串。 XML 显示了 .osc 提供商如何为 .osc 指定其功能和要求。 
  
## <a name="capabilities-for-friends"></a>朋友的功能

在此示例中, .osc 提供程序将指定以下元素, 以显示其支持好友功能的功能:
  
- **getFriends**为**true** , 指示 .osc 提供程序支持[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)方法以编程方式获取友元信息。 
    
- **cacheFriends**为**true** , 以支持将朋友的信息缓存在 Outlook 联系人文件夹中。 
    
- **contactSyncRestartInterval**为60若要指示在出错时, .osc 应重试每60分钟刷新一次缓存。 
    
- **followPerson**为**true** , 指示在社交网络上添加好友的功能。 
    
- **doNotFollowPerson**为**false** , 表示 .osc 提供商不支持在社交网络中删除某个人作为好友。 
    
- **dynamicContactsLookup**为**false** , 以指示 .osc 不应将朋友的信息存储在内存中。 
    
## <a name="capabilities-for-activities"></a>活动的功能

.osc 提供程序指定以下元素以显示其支持活动的功能:
  
- **getActivities**为**true** , 以指示 .osc 提供程序支持[ISocialProfile:: GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md)方法以编程方式获取朋友的活动。 
    
- **cacheActivities**为**false** , 以支持隐藏的 Outlook 新闻源文件夹中的朋友的缓存活动。 
    
- **dynamicActivitiesLookupEx**为**true** , 以指示 .osc 应将朋友的活动存储在内存中。 
    
## <a name="capabilities-for-authentication-and-account-configuration"></a>身份验证和帐户配置的功能

.osc 提供程序指定以下元素, 以显示其对身份验证和帐户配置的支持:
  
- **useLogonWebAuth**为**false** , 以指示 .osc 提供程序支持基本身份验证。 
    
- **supportsAutoConfigure**为**false** , 以指示 .osc 不应尝试为用户自动配置和登录社交网络。 
    
- **useLogonCached**和**hideRememberMyPassword**为**false** , 以指示 .osc 每次都应提示输入密码, 不应使用缓存登录凭据登录。 
    
- **displayUrl**为**false** , 以指示 .osc 不应在 "帐户配置" 对话框中显示社交网络的 URL。 
    
- **hideHyperlinks**为**false** , 以指示 .osc 提供商仅支持具有已知密码的现有帐户, 并且 .osc 不应显示 "**单击此处可创建帐户**并**忘记密码？** ""帐户配置" 对话框。 
    
## <a name="xml-example"></a>XML 示例

下面的示例演示了一个 .osc 提供程序的**功能**XML。 
  
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

## <a name="see-also"></a>另请参阅

- [.osc 提供程序 XML 示例](osc-provider-xml-examples.md)  
- [XML 的功能](xml-for-capabilities.md)  
- [友元 XML 示例](friends-xml-example.md)  
- [活动源 XML 示例](activity-feed-xml-example.md)  
- [Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)

