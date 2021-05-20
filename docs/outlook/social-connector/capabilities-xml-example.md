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
# <a name="capabilities-xml-example"></a>功能 XML 示例

本主题中的 XML 示例是调用社交网络的[ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法后返回到 Outlook Social Connector (OSC) 的 XML 字符串。 XML 显示 OSC 提供程序如何指定 OSC 的功能和要求。 
  
## <a name="capabilities-for-friends"></a>好友功能

在此例中，OSC 提供程序指定以下元素以显示其支持好友功能的功能：
  
- **getFriends** 为 **true，** 表示 OSC 提供程序支持 [ISocialPerson：：GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) 方法以编程方式获取好友的信息。 
    
- **cacheFriends** as **true，** 以支持将好友的信息缓存到Outlook联系人文件夹中。 
    
- **contactSyncRestartInterval** 为 60，指示出错时，OSC 应每 60 分钟重试刷新一次缓存。 
    
- **followPerson** as **true** 指示在社交网络上添加好友的能力。 
    
- **doNotFollowPerson** 为 **false，** 指示 OSC 提供程序不支持将某人作为好友删除在社交网络上。 
    
- **dynamicContactsLookup** 为 **false，** 指示 OSC 不应在内存中存储好友的信息。 
    
## <a name="capabilities-for-activities"></a>活动功能

OSC 提供程序指定以下元素以显示其支持活动的功能：
  
- **getActivities** 为 **true，** 指示 OSC 提供程序支持 [ISocialProfile：：GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md) 方法以编程方式获取好友的活动。 
    
- **cacheActivities** as **false，** 用于支持在隐藏的"新闻源"文件夹中Outlook好友的活动。 
    
- **dynamicActivitiesLookupEx** 为 **true，** 指示 OSC 应在内存中存储好友的活动。 
    
## <a name="capabilities-for-authentication-and-account-configuration"></a>身份验证和帐户配置的功能

OSC 提供程序指定以下元素以显示其对身份验证和帐户配置的支持：
  
- **useLogonWebAuth** 为 **false，** 指示 OSC 提供程序支持基本身份验证。 
    
- **supportsAutoConfigure** as **false** to indicate that the OSC should not attempt to automatically configure and log on to the social network for the user. 
    
- **useLogonCached** 和 **hideRememberMyPassword** 为 **false，** 以指示 OSC 应每次提示输入密码，并且不应使用缓存的登录凭据登录。 
    
- **displayUrl** 为 **false，** 指示 OSC 不应在帐户配置对话框中显示社交网络的 URL。 
    
- **hideHyperlinks** as **false** 指示 OSC 提供程序仅支持具有已知密码的现有帐户，并且 OSC 不应在帐户配置对话框中显示"单击此处创建帐户"和"**忘记** 密码？"超链接。 
    
## <a name="xml-example"></a>XML 示例

以下示例演示 OSC 提供程序的功能 **XML。** 
  
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

## <a name="see-also"></a>另请参阅

- [OSC 提供程序 XML 示例](osc-provider-xml-examples.md)  
- [功能的 XML](xml-for-capabilities.md)  
- [好友 XML 示例](friends-xml-example.md)  
- [活动源 XML 示例](activity-feed-xml-example.md)  
- [OutlookSocial Connector Provider XML 架构](outlook-social-connector-provider-xml-schema.md)

