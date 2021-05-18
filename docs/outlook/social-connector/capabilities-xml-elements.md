---
title: 功能 XML 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1951643d-e3ca-4d04-bc0c-10d9d0b35dad
description: 本主题中的表介绍了功能 XML 的子元素，并按它们支持的区域进行分组。
ms.openlocfilehash: 6816bbdcd24eceffc47d6b9d0835a90c7089c039
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281186"
---
# <a name="capabilities-xml-elements"></a>功能 XML 元素

本主题中的表介绍了功能 **XML** 的子元素，并按它们支持的区域进行分组。 每个 **capabilities** 元素的默认值为 **false**。 如果 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法返回的功能 **XML** 中未指定 元素，则元素的值等于 **false**。
  
有关功能 XML **的** 概述说明，请参阅 [功能的 XML。](xml-for-capabilities.md) 有关功能 XML **的示例** ，请参阅 [Capabilities XML Example](capabilities-xml-example.md)。 有关 Microsoft Outlook Social Connector 的完整定义 (OSC) 提供程序 XML 架构，包括哪些元素是必需的或可选的，请参阅[Outlook Social Connector Provider XML Schema。](outlook-social-connector-provider-xml-schema.md)
  
## <a name="capabilities-for-supporting-friends"></a>支持好友的功能

下表显示了适用于好友或非好友的任何形式的同步的元素。
  
|**元素**|**说明**|
|:-----|:-----|
|**doNotFollowPerson** <br/> |指示提供程序是否支持 [ISocialSession：：UnFollowPerson](isocialsession-unfollowperson.md) 方法调用。  <br/> **followPerson** 和 **doNotFollowPerson** 是 OSC 提供程序的独立功能。 OSC 提供程序可以指示能够将某人添加为好友 (将 **followPerson** 设置为 **true**) 或能够删除社交网络帐户 (将 **doNotFollowPerson** 设置为 **true**) 上的好友。 通常，能够关注并不意味着能够停止关注。 **followPerson** 是一项功能，不会被误解为跟踪特定人员或社交网络帐户上的每个人的操作。 **followPerson** being **true** 并不表示 **doNotFollowPerson** 为 **false**。  <br/> |
|**followPerson** <br/> |指示提供程序是否支持 [ISocialSession：：FollowPerson](isocialsession-followperson.md) 方法调用。 OSC 检查如果 **cacheFriends** 为 **true** (好友) 的缓存同步 **，dynamicContactsLookup** 为 **true** (好友和非好友) 的按需同步，或者 **cacheFriends** 和 **dynamicContactsLookup** 都是 true (好友和非好友) 的混合同步。 如果提供程序将 **followPerson** 设置为 true，OSC 将在人员窗格中为用户关注的人显示网络锁屏提醒，并启用"人员窗格"中"添加 **(+) "** 菜单上的"**在 \< 网络 \>** 名称"命令。  如果提供程序将 **followPerson** 设置 **为 false**，则不显示网络锁屏提醒，并且 **\< NetworkName \>** 命令处于隐藏状态。  <br/> |
|**getFriends** <br/> |指示提供程序是否支持 [ISocialPerson：：GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) 或 [ISocialSession2：：GetPeopleDetails](isocialsession2-getpeopledetails.md) 方法调用。 如果提供程序将 **getFriends** 设置为 **true，OSC** 将使用 cacheFriends 或 **dynamicContactsLookup** 的值来确定社交网络是否允许将好友存储为 Outlook 联系人项目或内存中。  如果提供程序将 **getFriends** 设置为 **false**，则社交网络不支持好友和 **ISocialPerson：：GetFriendsAndColleagues** 和 **ISocialSession2：：GetPeopleDetails** 方法，并且 OSC 将忽略 **cacheFriends** 和 **dynamicContactsLookup** 的值。  <br/> |
   
以下元素仅适用于好友的缓存同步或好友和非好友的混合同步。 有关同步好友详细信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。
  
|**元素**|**说明**|
|:-----|:-----|
|**cacheFriends** <br/> |指示 OSC 提供程序是否允许将好友存储为 Outlook 联系人项目。 OSC 仅在 **getFriends** 为 **true** 时检查 **cacheFriends。** 如果提供程序将 **cacheFriends** 设置为 **true，** 则 OSC 通过缓存来同步好友，然后在用户的默认存储中为好友联系人创建特定于网络的联系人文件夹。 特定于网络的联系人文件夹的名称是 [ISocialProvider：：SocialNetworkName](isocialprovider-socialnetworkname.md) 属性的值。 如果提供程序将 **cacheFriends** 设置为 **false，** 则 OSC 不会为好友联系人创建特定于网络的联系人文件夹来存储好友。  <br/> |
|**contactSyncRestartInterval** <br/> |如果发生同步错误，则确定尝试从社交网络同步好友信息之间的重试间隔（分钟）。 OSC 仅在 OSC 提供程序支持缓存同步或好友到特定于社交网络的联系人文件夹的混合同步时使用此元素 (**cacheFriends** 为 **true**) 。  <br/> 默认重试间隔为 30 分钟，除非在 下由 键  `ContactSyncRestartInterval` 替代默认值  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector` 。 如果提供程序设置 **contactSyncRestartInterval**，则提供程序值将覆盖默认的重试间隔 30 分钟或注册表项值。  <br/> 有关按需同步好友和非好友信息详细信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。  <br/> |
   
以下元素仅适用于好友和非好友的按需同步或混合同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**dynamicContactsLookup** <br/> |指示 OSC 提供程序是否支持对好友和非好友进行按需同步的 [ISocialSession2：：GetPeopleDetails](isocialsession2-getpeopledetails.md) 调用。  <br/> OSC 仅在 getFriends 为 **true** 时检查 **dynamicContactsLookup。** **dynamicContactsLookup** 的默认设置为 **false**。  <br/> 如果 OSC 提供程序将 **dynamicContactsLookup** 指定为 **true，** 将 **getFriends** 指定为 **true，** 则 OSC 每次刷新人员窗格时都会调用 **ISocialSession2：：GetPeopleDetails。** 当用户在人员窗格中选择其他用户或 Outlook 资源管理器窗口中的另一个项目，或打开 Outlook 检查器窗口时，将刷新人员窗格。 动态联系人查找可确保用户始终在人员窗格中看到最新的用户图片和个人资料信息，但会增加从提供程序到社交网络的呼叫数。  <br/> 如果提供程序将 **dynamicContactsLookup** 设置为 **false，** 则 OSC 不会调用 **ISocialSession2：：GetPeopleDetails** 来刷新人员窗格。  <br/> |
|**showOnDemandContactsWhenMinimized** <br/> |指示在最小化人员窗格时，OSC 是否应为好友和非好友执行按需同步。  <br/> |
   
## <a name="capabilities-for-supporting-activities"></a>支持活动的功能

以下元素适用于 OSC 提供程序支持的任何形式的活动同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**getActivities** <br/> |指示提供程序是否支持 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 或 [ISocialPerson：：GetActivities](isocialperson-getactivities.md) 方法调用。 如果提供程序将 **getActivities** 设置为 **true，OSC** 将使用 **cacheActivities** 或 **dynamicActivitiesLookupEx** 的值来确定社交网络网站是否允许将活动存储为 Outlook RSS 项目或内存中活动。 如果提供程序将 **getActivities** 设置为 **false**，则社交网络不支持活动和 **ISocialSession2：：GetActivitiesEx** 和 **ISocialPerson：：GetActivities** 方法，OSC 将忽略 **cacheActivities** 和 **dynamicActivitiesLookupEx** 的值。  <br/> |
   
以下元素仅适用于活动的缓存同步或混合同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**cacheActivities** <br/> |从 Outlook Social Connector 2013 开始，OSC 将忽略此元素，因为提供程序无法再通过将其缓存到用户存储中的隐藏文件夹中来同步活动。  <br/> 如果提供程序支持活动，则提供程序必须支持按需同步活动。 提供程序将 **cacheActivities** 设置 **为 false，** 将 **dynamicActivitesLookupEx** 设置 **为 true**。 OSC 按需同步活动，并缓存内存中的活动。 以 30 分钟的间隔刷新活动内存缓存。  <br/> |
   
以下元素仅适用于按需同步或活动的混合同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**dynamicActivitiesLookup** <br/> |在 OSC 1.1 中已弃用。  <br/> 从 OSC 1.1 开始，OSC 不再调用 [ISocialSession：：GetActivities](isocialsession-getactivities.md) 并忽略 **dynamicActivitiesLookup 的值**。 若要支持按需活动查找，将 **cacheActivities** 设置为 **false，** 将 **getActivities** 和 **dynamicActivitiesLookupEx** 设置为 **true，OSC** 将调用 **ISocialSession2：：GetActivitiesEx**。  <br/> |
|**dynamicActivitiesLookupEx** <br/> |指示 OSC 提供程序是否支持 **ISocialSession2：：GetActivitiesEx** 调用按需同步活动。  <br/> 如果 OSC 提供程序支持按需活动同步，它会将 **getActivities** 和 **dynamicActivitiesLookupEx** 设置 **为 true，** 将 **cacheActivities** 设置为 **false**。 每次刷新人员窗格时，OSC 都会调用 **ISocialSession2：：GetActivitiesEx。** 当用户在 Outlook 资源管理器窗口中更改所选项目或打开 Outlook 检查器窗口时，将刷新人员窗格。 动态活动查找可确保用户始终在人员窗格中看到最新的活动，但会增加从提供程序到社交网络的呼叫数。  <br/> 如果提供程序将 **dynamicActivitiesLookupEx** 设置为 **false，** 则 OSC 不会为人员窗格中显示的人调用 **ISocialSession2：：GetActivitiesEx。**  <br/> |
|**showOnDemandActivitiesWhenMinimized** <br/> |指示在最小化人员窗格时，OSC 是否应该对活动执行按需同步。  <br/> |
   
## <a name="common-capabilities-for-supporting-on-demand-or-hybrid-synchronization-of-friends-non-friends-and-activities"></a>支持好友、非好友和活动按需或混合同步的常见功能

|**元素**|**说明**|
|:-----|:-----|
|**hashFunction** <br/> | 指定 OSC 提供程序支持的哈希函数。 为了保护不在提供商的社交网络或业务线应用程序上的用户的个人身份信息，OSC 将哈希电子邮件地址传递给 **ISocialSession2：：GetPeopleDetails** 和 **ISocialSession2：：GetActivitiesEx**。  <br/>  如果 **dynamicContactsLookup** 设置为 **true** 或 **dynamicActivitiesLookupEx** 设置为 **true，** 则提供程序必须将 **hashFunction** 设置为允许的值之一 **：SHA1、MD5** 或 **CRC32MD5。**  如果 **hashFunction** 缺失或指定了错误值，OSC 将返回错误。  <br/> **SHA1** 是 Internet 工程任务组 (IETF) 美国安全哈希算法 1 定义 [[RFC3174]](https://www.rfc-editor.org/rfc/rfc3174.txt)。 例如，电子邮件地址 **的 SHA1** 哈希值为 melissa@contoso.com  `bb81577b567262a21a4df5f6e335c1250acd7b50` 。  <br/> **MD5** 是由 [[RFC1321]](https://www.rfc-editor.org/rfc/rfc1321.txt)定义的 Internet 工程 (IETF) MD5 Message-Digest 算法。 例如，电子邮件地址的 **MD5** 哈希值 melissa@contoso.com 为  `c8c39e61ca1662477b39b83d7b0a0615` 。  <br/> **CRC32MD5** 是 **CRC32** 和 **MD5** 的组合，定义如下：  <br/>  通过删除前导空格和尾随空格并将所有字符转换为小写来规范化电子邮件地址。  <br/>  计算 **规范化电子邮件地址的 CRC32** 值，并使用此值的小数整数表示形式。 如果实现返回有符号整数，则必须将有符号整数转换为无符号整数。  <br/>  计算规范化电子邮件地址的 **MD5** 值并使用此值的十六进制表示形式 (A 到 F) 。  <br/>  将这两个值与下划线组合在一起。  <br/>  例如， **电子邮件地址的 CRC32MD5** 哈希值 melissa@contoso.com 为  `2149665315_c8c39e61ca1662477b39b83d7b0a0615` 。  <br/> |
   
## <a name="capabilities-for-supporting-authentication-and-account-configuration"></a>支持身份验证和帐户配置的功能

|**元素**|**说明**|
|:-----|:-----|
|**allowChangesToAutoConfigure** <br/> |指示社交网络是否允许用户更改自动配置设置，例如提供不同的 URL 进行登录。  <br/> |
|**createAccountUrl** <br/> |如果提供程序将 **hideHyperlinks** 设置为 **false**，当用户单击"单击此处创建帐户配置"对话框中的帐户时 **，createAccountUrl** 指定的 URL 将在默认浏览器中打开。  <br/> |
|**displayUrl** <br/> |指示 OSC 是否应该在帐户配置对话框中显示社交网络的 **URL** 地址文本框。  <br/> |
|**forgotPasswordUrl** <br/> |如果提供程序将 **hideHyperlinks** 设置为 **false，** 则当用户在"帐户配置"对话框中单击"忘记密码？"时，由 **forgotPasswordUrl** 指定的 URL 将在默认浏览器中打开。  <br/> |
|**hideHyperlinks** <br/> |指示 OSC 是否应该在帐户配置对话框中隐藏"单击此处创建帐户"和"忘记密码？"超链接。  <br/> OSC 1.0 将忽略此设置，并且超链接始终处于隐藏状态。 OSC 1.1 遵循此设置的值。  <br/> |
|**hideRememberMyPassword** <br/> |指示 OSC 是否应该在帐户配置对话框中 **隐藏** "记住密码"复选框。  <br/> 如果提供程序将 **hideRememberMyPassword** 设置 **为 true，** 则 OSC 将充当未选中的"记住 **我的** 密码"框，并且不会保存密码。  <br/> 如果提供程序将 **hideRememberMyPassword** 设置为 **false，OSC** 将在帐户配置对话框中显示"记住我的密码"复选框。  <br/> |
|**supportsAutoConfigure** <br/> |指示 OSC 是否应该在 **ISocialProvider** 接口上调用 **GetAutoConfiguredSession** 函数来尝试自动配置并登录到用户的社交网络。  <br/> |
|**useLogonCached** <br/> |指示 OSC 提供程序是否支持 [ISocialSession2：：LogonCached](isocialsession2-logoncached.md) 调用以使用缓存凭据登录。  <br/> 如果提供程序将 **useLogonCached** 设置为 **true，** 则 OSC 将忽略 **useLogonWebAuth** 的设置，OSC 将调用 **ISocialSession2：：LogonCached** 进行身份验证。  <br/> 如果提供程序将 **dynamicActivitiesLookupEx** 设置为 **false，** 则 OSC 不会调用 **ISocialSession2：：LogonCached** 进行身份验证。  <br/> |
|**useLogonWebAuth** <br/> |指示 OSC 是否应该使用基于表单的身份验证和 [ISocialSession：：LogonWeb](isocialsession-logonweb.md) 方法。 如果提供程序将 **useLogonWebAuth** 设置为 **false，** 则 OSC 将使用基本身份验证并调用 [ISocialSession：：Logon](isocialsession-logon.md) 方法。 如果提供程序将 **useLogonWebAuth** 设置 **为 true**，OSC 将使用基于表单的身份验证并调用 **ISocialSession：：LogonWeb**。  <br/> |
   
根据提供程序 **在** **ISocialProvider：：GetCapabilities** 方法中返回的功能 XML，帐户配置对话框会更改。 例如，图 1 显示了 TestProvider 示例的帐户配置对话框。 
  
**图 1.帐户配置对话框中的 TestProvider 示例**

![TestProvider 示例配置信息](media/odc_ol14_ta_OSCFigure4.jpg)
  
## <a name="see-also"></a>另请参阅

- [功能的 XML](xml-for-capabilities.md)

