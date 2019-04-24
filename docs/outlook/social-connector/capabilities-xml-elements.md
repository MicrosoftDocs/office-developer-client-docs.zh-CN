---
title: 功能 XML 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1951643d-e3ca-4d04-bc0c-10d9d0b35dad
description: 本主题中的表描述了功能 XML 的子元素, 并按其支持的区域进行分组。
ms.openlocfilehash: 6816bbdcd24eceffc47d6b9d0835a90c7089c039
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281186"
---
# <a name="capabilities-xml-elements"></a>功能 XML 元素

本主题中的表描述了**功能**XML 的子元素, 并按其支持的区域进行分组。 每个**功能**元素的默认值为**false**。 如果未在[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法返回的**功能**XML 中指定该元素, 则该元素的值等于**false**。
  
有关**功能**xml 的概述说明, 请参阅[xml for 功能](xml-for-capabilities.md)。 有关 XML 的**功能**示例, 请参阅[功能 xml 示例](capabilities-xml-example.md)。 有关 Microsoft Outlook social connector (.osc) 提供程序 XML 架构的完整定义, 包括必需或可选的元素, 请参阅[Outlook Social Connector provider XML schema](outlook-social-connector-provider-xml-schema.md)。
  
## <a name="capabilities-for-supporting-friends"></a>支持好友的功能

下表显示了适用于任何形式的朋友或非好友同步的元素。
  
|**元素**|**说明**|
|:-----|:-----|
|**doNotFollowPerson** <br/> |指示提供程序是否支持[ISocialSession:: UnFollowPerson](isocialsession-unfollowperson.md)方法调用。  <br/> **followPerson**和**doNotFollowPerson**是一个 .osc 提供程序的独立功能。 一个 .osc 提供程序可以指示能够将某个人添加为朋友 (将**followPerson**设置为**true**), 或能够在社交网络帐户上将其删除为朋友 (将**doNotFollowPerson**设置为**true**)。 通常情况下, 能够遵循此功能并不意味着能够停止关注。 **followPerson**是一项功能, 不会被误解为对社交网络帐户上的特定人员或每个人执行的操作。 **followPerson** **为 true**并不意味着**doNotFollowPerson**为**false**。  <br/> |
|**followPerson** <br/> |指示提供程序是否支持[ISocialSession:: FollowPerson](isocialsession-followperson.md)方法调用。 .osc 检查**followPerson**如果**cacheFriends**为**true** (友元缓存同步)、 **dynamicContactsLookup**为**true** (对朋友和非好友的按需同步), 或同时进行这两个**cacheFriends**和**dynamicContactsLookup**为 true (友元和非好友的混合同步)。 如果提供程序将**followPerson**设置为**true**, 则 .osc 会在用户所关注的人员的人员窗格中显示网络徽章, 并在 "人员" 中的 "**添加 (+)** " 菜单上启用 " ** \<NetworkName\> ** " 命令。窗口. 如果提供程序将**followPerson**设置为**false**, 则不会显示网络标记, 并且**在\<NetworkName\> **命令处于隐藏状态。  <br/> |
|**getFriends** <br/> |指示提供程序是否支持[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)或[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md)方法调用。 如果提供程序将**getFriends**设置为**true**, 则 .osc 将使用**cacheFriends**或**dynamicContactsLookup**的值来确定社交网络是否允许将好友存储为 Outlook 联系人项目或在内存中。 如果提供程序将**getFriends**设置为**false**, 则社交网络不支持好友和**ISocialPerson:: GetFriendsAndColleagues**和**ISocialSession2:: GetPeopleDetails**方法, 并且 .osc 将忽略值**cacheFriends**和**dynamicContactsLookup**。  <br/> |
   
以下元素仅适用于朋友的缓存同步或朋友和非好友的混合同步。 有关同步朋友的详细信息, 请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。
  
|**元素**|**说明**|
|:-----|:-----|
|**cacheFriends** <br/> |指示 .osc 提供程序是否允许将好友存储为 Outlook 联系人项目。 仅当**getFriends**为**true**时, .osc 检查**cacheFriends** 。 如果提供程序将**cacheFriends**设置为**true**, 则 .osc 通过缓存同步朋友, 并在用户的默认存储区中为好友联系人创建一个特定于网络的联系人文件夹。 特定于网络的联系人文件夹的名称是[ISocialProvider:: SocialNetworkName](isocialprovider-socialnetworkname.md)属性的值。 如果提供程序将**cacheFriends**设置为**false**, 则 .osc 不会为好友联系人创建特定于网络的联系人文件夹来存储好友。  <br/> |
|**contactSyncRestartInterval** <br/> |确定同步错误发生时, 尝试从社交网络同步朋友的信息之间的重试间隔 (以分钟为单位)。 仅当 .osc 提供程序支持对社交网络特定的联系人文件夹 (**cacheFriends**为**true**) 的友元缓存同步或混合同步时, .osc 才使用此元素。  <br/> 默认重试间隔为30分钟, 除非默认值由下`ContactSyncRestartInterval` `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`的键替代。 如果提供程序设置**contactSyncRestartInterval**, 则提供程序值将替代30分钟或注册表项值的默认重试间隔。  <br/> 若要详细了解如何根据需求同步朋友和非好友信息, 请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。  <br/> |
   
以下元素仅适用于朋友和非好友的按需同步或混合同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**dynamicContactsLookup** <br/> |指示 .osc 提供程序是否支持[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md)呼叫以实现对朋友和非好友的按需同步。  <br/> 仅当**getFriends**为**true**时, .osc 检查**dynamicContactsLookup** 。**dynamicContactsLookup**的默认设置为**false**。  <br/> 如果 .osc 提供程序将**dynamicContactsLookup**指定为**true** , 并且**getFriends**为**true**, 则在每次刷新人员窗格时, .osc 都会调用**ISocialSession2:: GetPeopleDetails** 。 当用户在 "人员" 窗格或 outlook 资源管理器窗口中的其他项目中选择另一个用户或打开 outlook 检查器窗口时, 将刷新 "人员" 窗格。 动态联系人查找可确保用户在 "人员" 窗格中始终看到最新的用户图片和配置文件信息, 但会将提供商的呼叫数增加到社交网络。  <br/> 如果提供程序将**dynamicContactsLookup**设置为**false**, 则 .osc 不会调用**ISocialSession2:: GetPeopleDetails**刷新人员窗格。  <br/> |
|**showOnDemandContactsWhenMinimized** <br/> |指示当人员窗格最小化时, .osc 是否应为朋友和非好友执行按需同步。  <br/> |
   
## <a name="capabilities-for-supporting-activities"></a>支持活动的功能

以下元素适用于受 .osc 提供程序支持的活动的任何形式的同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**getActivities** <br/> |指示提供程序是否支持[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)或[ISocialPerson:: GetActivities](isocialperson-getactivities.md)方法调用。 如果提供程序将**getActivities**设置为**true**, 则 .osc 将使用**cacheActivities**或**dynamicActivitiesLookupEx**的值来确定社交网络网站是否允许将活动存储为 Outlook RSS 项目或内存中的活动。 如果提供程序将**getActivities**设置为**false**, 则社交网络不支持 activity 和**ISocialSession2:: GetActivitiesEx**和**ISocialPerson:: getActivities**方法, 而 .osc 将忽略值**cacheActivities**和**dynamicActivitiesLookupEx**。  <br/> |
   
以下元素仅适用于活动的缓存同步或混合同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**cacheActivities** <br/> |从 Outlook Social Connector 2013 开始, .osc 将忽略此元素, 因为提供程序无法再通过将其缓存在用户存储区中的隐藏文件夹中来同步活动。  <br/> 如果提供程序支持活动, 则提供程序必须支持按需同步活动。 提供程序将**cacheActivities**设置为**false** , 并将**dynamicActivitesLookupEx**设置为**true**。 .osc 按需同步活动, 并在内存中缓存活动。 活动内存缓存将按30分钟的间隔进行刷新。  <br/> |
   
以下元素仅适用于活动的按需同步或混合同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**dynamicActivitiesLookup** <br/> |在 .osc 1.1 中已弃用。  <br/> 从 .osc 1.1 开始, .osc 不再调用[ISocialSession:: GetActivities](isocialsession-getactivities.md)并忽略**dynamicActivitiesLookup**的值。 若要支持按需活动查找, 请将**cacheActivities**设置为**false** , 将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**, 并且 .osc 将调用**ISocialSession2:: GetActivitiesEx**。  <br/> |
|**dynamicActivitiesLookupEx** <br/> |指示 .osc 提供程序是否支持对活动的按需同步的**ISocialSession2:: GetActivitiesEx**调用。  <br/> 如果 .osc 提供程序支持按需活动同步, 它会将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**, 并将**cacheActivities**设置为**false**。 在每次刷新 "人员" 窗格时, .osc 都会调用**ISocialSession2:: GetActivitiesEx** 。 当用户在 Outlook 资源管理器窗口中更改所选的项或打开 outlook 检查器窗口时, 将刷新 "人员" 窗格。 动态活动查找可确保用户始终会看到 "人员" 窗格中的最新活动, 但会将从提供商到社交网络的呼叫数增加。  <br/> 如果提供程序将**dynamicActivitiesLookupEx**设置为**false**, 则 .osc 不会为人员窗格中显示的人员调用**ISocialSession2:: GetActivitiesEx** 。  <br/> |
|**showOnDemandActivitiesWhenMinimized** <br/> |指示当人员窗格最小化时, .osc 是否应执行活动的按需同步。  <br/> |
   
## <a name="common-capabilities-for-supporting-on-demand-or-hybrid-synchronization-of-friends-non-friends-and-activities"></a>支持朋友、非好友和活动的按需或混合同步的常见功能

|**元素**|**说明**|
|:-----|:-----|
|**hashFunction** <br/> | 指定 .osc 提供程序支持的哈希函数。 为了保护不在提供商的社交网络或业务线应用程序上的用户的个人身份信息, .osc 将哈希电子邮件地址传递给**ISocialSession2:: GetPeopleDetails**和**ISocialSession2::GetActivitiesEx**。  <br/>  如果将**dynamicContactsLookup**设置为**true**或**dynamicActivitiesLookupEx**设置为**true**, 则提供程序必须将**hashFunction**设置为允许的值之一: **SHA1**、 **MD5**或**CRC32MD5**。 如果**hashFunction**丢失或指定的值不正确, 则 .osc 将返回错误。  <br/> **SHA1**是 Internet 工程任务组 (IETF) 我们通过[[RFC3174]](https://www.rfc-editor.org/rfc/rfc3174.txt)定义的安全哈希算法1。 例如, 电子邮件地址 melissa@contoso.com 的**SHA1**哈希值为`bb81577b567262a21a4df5f6e335c1250acd7b50`。  <br/> **MD5**是由[[RFC1321]](https://www.rfc-editor.org/rfc/rfc1321.txt)定义的 Internet 工程任务组 (IETF) MD5 消息摘要算法。 例如, 电子邮件地址 melissa@contoso.com 的**MD5**哈希值为`c8c39e61ca1662477b39b83d7b0a0615`。  <br/> **CRC32MD5**是**CRC32**和**MD5**定义的组合, 如下所示:  <br/>  通过删除前导和尾随空格并将所有字符转换为小写形式来规范化电子邮件地址。  <br/>  计算正常化的电子邮件地址的**CRC32**值, 并使用此值的十进制整数表示形式。 如果您的实现返回带符号整数, 则必须将带符号整数转换为无符号整数。  <br/>  计算正常化的电子邮件地址的**MD5**值, 并使用此值的十六进制表示形式 (使用小写字母 A 到 F)。  <br/>  将这两个值与下划线组合。  <br/>  例如, 电子邮件地址 melissa@contoso.com 的**CRC32MD5**哈希值为`2149665315_c8c39e61ca1662477b39b83d7b0a0615`。  <br/> |
   
## <a name="capabilities-for-supporting-authentication-and-account-configuration"></a>支持身份验证和帐户配置的功能

|**元素**|**说明**|
|:-----|:-----|
|**allowChangesToAutoConfigure** <br/> |指示社交网络是否允许用户更改自动配置设置, 如提供用于登录的其他 URL。  <br/> |
|**createAccountUrl** <br/> |如果提供程序将**hideHyperlinks**设置为**false**, 则当用户单击 "**帐户配置**" 对话框中的 **"单击此处来创建帐户**" 时, **createAccountUrl**指定的 URL 将在默认浏览器中打开。  <br/> |
|**displayUrl** <br/> |指示 .osc 是否应在 "帐户配置" 对话框中显示社交网络的 " **URL 地址**" 文本框。  <br/> |
|**forgotPasswordUrl** <br/> |如果提供程序将**hideHyperlinks**设置**为 false**, 则当用户单击 "**忘记了密码？** " 在 "**帐户配置**" 对话框中, 由**forgotPasswordUrl**指定的 URL 将在默认浏览器中打开。  <br/> |
|**hideHyperlinks** <br/> |指示 .osc 是否应在 "帐户配置" 对话框中隐藏 "**单击此处创建帐户**并**忘记密码？** " 超链接。  <br/> .osc 1.0 忽略此设置, 并且始终隐藏超链接。 .osc 1.1 遵循此设置的价值。  <br/> |
|**hideRememberMyPassword** <br/> |指示 .osc 是否应在 "帐户配置" 对话框中隐藏 "**记住我的密码**" 复选框。  <br/> 如果提供程序将**hideRememberMyPassword**设置为**true**, 则该 .osc 将充当 "**记住我的密码**" 框处于未选中状态, 并且不会保存密码。  <br/> 如果提供程序将**hideRememberMyPassword**设置为**false**, 则 .osc 将在 "帐户配置" 对话框中显示 "**记住我的密码**" 复选框。  <br/> |
|**supportsAutoConfigure** <br/> |指示 .osc 是否应调用**ISocialProvider**接口上的**GetAutoConfiguredSession**函数, 以尝试自动配置并登录到用户的社交网络。  <br/> |
|**useLogonCached** <br/> |指示 .osc 提供程序是否支持使用缓存凭据登录的[ISocialSession2:: LogonCached](isocialsession2-logoncached.md)调用。  <br/> 如果提供程序将**useLogonCached**设置为**true**, 则 .osc 将忽略**useLogonWebAuth**的设置和 .osc 调用**ISocialSession2:: LogonCached**进行身份验证。  <br/> 如果提供程序将**dynamicActivitiesLookupEx**设置为**false**, 则 .osc 不会调用**ISocialSession2:: LogonCached**进行身份验证。  <br/> |
|**useLogonWebAuth** <br/> |指示 .osc 是否应使用基于表单的身份验证和[ISocialSession:: LogonWeb](isocialsession-logonweb.md)方法。 如果提供程序将**useLogonWebAuth**设置为**false**, 则 .osc 将使用基本身份验证, 并调用[ISocialSession:: Logon](isocialsession-logon.md)方法。 如果提供程序将**useLogonWebAuth**设置为**true**, 则 .osc 将使用基于表单的身份验证并调用**ISocialSession:: LogonWeb**。  <br/> |
   
根据**ISocialProvider:: GetCapabilities**方法中提供程序返回的 XML 的**功能**, "帐户配置" 对话框会发生更改。 例如, 图1显示了 TestProvider 示例的 "帐户配置" 对话框。 
  
**图1。"帐户配置" 对话框中的 TestProvider 示例**

![TestProvider 示例配置信息](media/odc_ol14_ta_OSCFigure4.jpg)
  
## <a name="see-also"></a>另请参阅

- [XML 的功能](xml-for-capabilities.md)

