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
# <a name="capabilities-xml-example"></a>功能 XML 示例

本主题中的 XML 示例是一个 XML 字符串，它为社交网络调用[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法后，返回到 Outlook Social Connector (OSC)。 XML 演示如何 OSC 提供程序指定其功能和要求 OSC。 
  
## <a name="capabilities-for-friends"></a>朋友的功能

本示例中，OSC 提供程序指定要支持朋友功能中显示其功能的以下元素：
  
- **getFriends**为**true**以指明 OSC 提供程序支持[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)方法以编程方式获取朋友的信息。 
    
- 为**true**以支持在 Outlook 联系人文件夹中的缓存朋友信息**cacheFriends** 。 
    
- 为 60 表示该上错误**contactSyncRestartInterval** ，OSC 应该重试刷新缓存每隔 60 分钟。 
    
- 为**true**以指明添加朋友社交网络上的功能**followPerson** 。 
    
- **doNotFollowPerson**为**false**以指明 OSC 提供程序不支持删除为朋友社交网络上的某个人。 
    
- 为**false**以指明 OSC 不应在内存中存储朋友的信息**dynamicContactsLookup** 。 
    
## <a name="capabilities-for-activities"></a>活动的功能

OSC 提供程序指定要显示其功能支持活动的以下元素：
  
- 为**true**以指明 OSC 提供程序支持[ISocialProfile::GetActivitiesOfFriendsAndColleagues](isocialprofile-getactivitiesoffriendsandcolleagues.md)方法以编程方式获取朋友的活动**getActivities** 。 
    
- 为**false**以隐藏 Outlook 新闻源文件夹中支持的朋友缓存活动**cacheActivities** 。 
    
- 为**true**以指明 OSC 应在内存中存储朋友的活动**dynamicActivitiesLookupEx** 。 
    
## <a name="capabilities-for-authentication-and-account-configuration"></a>身份验证和帐户配置的功能

OSC 提供程序指定要显示其支持的身份验证和帐户配置的以下元素：
  
- 为**false**以指示 OSC 提供程序支持基本身份验证**useLogonWebAuth** 。 
    
- 为**false**以指明 OSC 不应尝试自动配置和登录到用户社交网络**supportsAutoConfigure** 。 
    
- **useLogonCached**和**hideRememberMyPassword**为**false**以指示 OSC 应提示输入密码每次时，不应使用缓存登录凭据登录。 
    
- 为**false**以指明 OSC 帐户配置对话框应不显示社交网络的 URL **displayUrl** 。 
    
- 为**false**以指示 OSC 提供程序支持仅现有帐户与已知密码和 OSC 不应显示**创建一个帐户，请单击此处** **hideHyperlinks**和**忘记密码？** 中的超链接帐户配置对话框。 
    
## <a name="xml-example"></a>XML 示例

下面的示例演示**功能**的 OSC 提供程序的 XML。 
  
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

## <a name="see-also"></a>另请参阅

- [OSC 提供程序 XML 示例](osc-provider-xml-examples.md)  
- [功能 XML](xml-for-capabilities.md)  
- [朋友 XML 示例](friends-xml-example.md)  
- [活动源的 XML 示例](activity-feed-xml-example.md)  
- [Outlook Social Connector 提供程序的 XML 架构](outlook-social-connector-provider-xml-schema.md)

