---
title: 功能 XML 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1951643d-e3ca-4d04-bc0c-10d9d0b35dad
description: 本主题中的表介绍的功能 XML 子元素和分组依据它们支持的区域。
ms.openlocfilehash: 53bce69bbe22f6e950302a92b0ada21ed0f5a1f4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779197"
---
# <a name="capabilities-xml-elements"></a>功能 XML 元素

本主题中的表介绍的**功能**XML 子元素和分组依据它们支持的区域。 每个**功能**元素的默认值为**false**。 如果未指定中**功能** [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法返回的 XML 元素，元素的值等于**false**。
  
**功能**XML 概述说明，请参阅[功能的 XML](xml-for-capabilities.md)。 **功能**XML 的示例，请参阅[功能 XML 示例](capabilities-xml-example.md)。 完成定义的 Microsoft Outlook Social Connector (OSC) 提供程序 XML 架构，其中包括哪些元素必需或可选的请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。
  
## <a name="capabilities-for-supporting-friends"></a>支持朋友功能

下表显示了适用于任何形式的同步朋友或非朋友的元素。
  
|**元素**|**说明**|
|:-----|:-----|
|**doNotFollowPerson** <br/> |指示提供程序是否支持[ISocialSession::UnFollowPerson](isocialsession-unfollowperson.md)方法调用。  <br/> **followPerson**和**doNotFollowPerson**是独立的 OSC 提供程序的功能。 OSC 提供程序可以指示能够将某人添加为朋友 (设置**followPerson**为**true**) 或能够删除为朋友社交网络帐户 (设置**doNotFollowPerson**为**true**) 上的人员的功能。 一般情况下，能够按照并不意味着能够停止关注。 **followPerson**是一个能力，而且它是不被错误地解释为一个操作社交网络帐户关注特定人员或每个人。 **followPerson**均**为 true**不意味着**doNotFollowPerson**为**false**。  <br/> |
|**followPerson** <br/> |指示提供程序是否支持[ISocialSession::FollowPerson](isocialsession-followperson.md)方法调用。 OSC 检查**followPerson**如果**cacheFriends**为**true** （朋友缓存同步），则**dynamicContactsLookup**为**true** （按需同步朋友和非朋友），还是同时**cacheFriends**和**dynamicContactsLookup**属实 （朋友和非朋友混合同步）。 如果提供程序将**followPerson**设置为**true**，OSC 人员用户正在关注，并允许的人员窗格中显示网络徽章**上\<NetworkName\> ** **添加 （+）** 在人员菜单上的命令窗格。 如果提供程序将**followPerson**设置为**false**，则不会显示网络徽章，和**上\<NetworkName\>** 命令处于隐藏状态。  <br/> |
|**getFriends** <br/> |指示提供程序是否支持[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)或[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)方法调用。 如果提供程序将**getFriends**设置为**true**，OSC 使用**cacheFriends**或**dynamicContactsLookup**的值来确定社交网络是否允许存储朋友作为 Outlook 联系人项目或在内存中。 如果提供程序将**getFriends**设置为**false**，社交网络不支持朋友以及**ISocialPerson::GetFriendsAndColleagues**和**ISocialSession2::GetPeopleDetails**方法和 OSC 忽略的值**cacheFriends**和**dynamicContactsLookup**。  <br/> |
   
下列元素仅适用于缓存的同步朋友或朋友和非朋友的混合同步。 有关同步朋友的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。
  
|**元素**|**说明**|
|:-----|:-----|
|**cacheFriends** <br/> |指示 OSC 提供程序是否允许将朋友存储为 Outlook 联系人项目。 OSC 检查**cacheFriends**才**getFriends**为**true**。 如果提供程序将**cacheFriends**设置为**true**，OSC 同步朋友缓存，并在朋友联系人的用户的默认存储中创建特定于网络的联系人文件夹。 特定于网络的联系人文件夹的名称是[ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md)属性的值。 如果提供程序将**cacheFriends**设置为**false**，OSC 不创建特定于网络的联系人文件夹朋友联系人存储朋友。  <br/> |
|**contactSyncRestartInterval** <br/> |确定重试时间间隔，以分钟为单位，之间尝试同步朋友的信息与社交网络中，如果发生同步错误。 OSC OSC 提供程序支持缓存的同步或混合同步到特定社交网络的朋友联系人文件夹时，才使用此元素 （**cacheFriends**为**true**）。  <br/> 默认重试时间间隔为 30 分钟，除非默认被覆盖`ContactSyncRestartInterval`下键`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`。 如果提供程序集**contactSyncRestartInterval**、 提供程序值将覆盖默认的重试间隔 30 分钟或注册表项的值。  <br/> 有关同步朋友和非朋友信息需求的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。  <br/> |
   
下列元素将应用于只有按需同步或朋友和非朋友的混合同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**dynamicContactsLookup** <br/> |指示 OSC 提供程序是否支持[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)呼叫朋友和非朋友的按需同步。  <br/> OSC 检查**dynamicContactsLookup**才**getFriends**为**true**。**DynamicContactsLookup**的默认设置为**false**。  <br/> 如果 OSC 提供程序指定**dynamicContactsLookup**为**true**和**getFriends**为**true**，则 OSC 调用**ISocialSession2::GetPeopleDetails**每次刷新人员窗格。 在用户选择人员窗格或在 Outlook 资源管理器窗口中，另一个项目中的另一个用户或 Outlook 检查器窗口打开时刷新人员窗格。 动态联系人查找可以确保用户始终会看到的最新的用户图片和配置文件信息的人员窗格中，但增加到社交网络从提供程序的呼叫数。  <br/> 如果提供程序将**dynamicContactsLookup**设置为**false**，则 OSC 不调用**ISocialSession2::GetPeopleDetails**刷新人员窗格。  <br/> |
|**showOnDemandContactsWhenMinimized** <br/> |指示人员窗格最小化时是否 OSC 应执行的朋友和非朋友组成的按需同步。  <br/> |
   
## <a name="capabilities-for-supporting-activities"></a>支持活动的功能

下面的元素适用于任何形式的活动 OSC 提供程序支持的同步。
  
|**元素**|**说明**|
|:-----|:-----|
|**getActivities** <br/> |指示提供程序是否支持[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)或[ISocialPerson::GetActivities](isocialperson-getactivities.md)方法调用。 OSC 提供程序将**getActivities**设置为**true**，如果使用**cacheActivities**或**dynamicActivitiesLookupEx**的值来确定社交网络网站是否允许作为 Outlook RSS 项目或存储活动内存中的活动。 如果提供程序将**getActivities**设置为**false**，社交网络活动的**ISocialSession2::GetActivitiesEx**和**ISocialPerson::GetActivities**方法不支持和 OSC 忽略**的值cacheActivities**和**dynamicActivitiesLookupEx**。  <br/> |
   
下面的元素应用于仅缓存的同步或活动同步混合。
  
|**元素**|**说明**|
|:-----|:-----|
|**cacheActivities** <br/> |Outlook Social Connector 2013 中启动 OSC 忽略此元素的操作，因为提供程序不再可以通过在用户的存储区中的隐藏文件夹中缓存这些同步活动。  <br/> 如果提供程序支持活动，提供程序必须支持同步活动需求。 提供程序将**cacheActivities**设置为**false** ，并将**dynamicActivitesLookupEx**设置为**true**。 OSC 同步活动的点播和缓存在内存中的活动。 活动内存缓存刷新 30 分钟的时间间隔。  <br/> |
   
下列元素将应用于只有按需同步或活动同步混合。
  
|**元素**|**说明**|
|:-----|:-----|
|**dynamicActivitiesLookup** <br/> |OSC 1.1 中已弃用。  <br/> OSC 1.1 中启动 OSC 不再将呼叫[ISocialSession::GetActivities](isocialsession-getactivities.md) ，并忽略**dynamicActivitiesLookup**的值。 若要支持按需活动查找，将**cacheActivities**设置为**false**和**getActivities**和为**true**， **dynamicActivitiesLookupEx**和 OSC 将调用**ISocialSession2::GetActivitiesEx**。  <br/> |
|**dynamicActivitiesLookupEx** <br/> |指示是否 OSC 提供程序支持的活动的按需同步**ISocialSession2::GetActivitiesEx**呼叫。  <br/> 如果 OSC 提供程序支持按需活动同步，它将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**，和**cacheActivities**为**false**。 OSC 调用**ISocialSession2::GetActivitiesEx**每次刷新人员窗格。 在用户更改在 Outlook 资源管理器窗口中的选定的项或 Outlook 检查器窗口打开时刷新人员窗格。 动态活动查找可以确保用户始终会看到人员窗格中的最新活动，但会增加到社交网络从提供程序的呼叫数。  <br/> 如果提供程序将**dynamicActivitiesLookupEx**设置为**false**，OSC 不显示在人员窗格中的人员的调用**ISocialSession2::GetActivitiesEx** 。  <br/> |
|**showOnDemandActivitiesWhenMinimized** <br/> |指示时最小化人员窗格是否 OSC 应执行的活动的按需同步。  <br/> |
   
## <a name="common-capabilities-for-supporting-on-demand-or-hybrid-synchronization-of-friends-non-friends-and-activities"></a>支持的朋友、 非朋友和活动的点播或混合同步的常见功能

|**元素**|**说明**|
|:-----|:-----|
|**hashFunction** <br/> | 指定 OSC 提供程序支持的哈希函数。 若要保护的不在提供程序的社交网络或业务线应用程序的用户的个人身份信息，OSC 哈希电子邮件地址向传递**ISocialSession2::GetPeopleDetails**和**ISocialSession2::GetActivitiesEx**。  <br/>  如果设置为**true**时**dynamicContactsLookup**或**dynamicActivitiesLookupEx**设置为**true**，提供程序必须**hashFunction**设置为允许的值之一： **SHA1**、 **MD5**或**CRC32MD5**。 如果**hashFunction**缺失或指定一个不正确的值，OSC 将返回错误。  <br/> **SHA1**是 Internet 工程任务组 (IETF) 美国安全哈希算法 1 由[[RFC3174]](http://www.rfc-editor.org/rfc/rfc3174.txt)定义。 例如的电子邮件地址 melissa@contoso.com **SHA1**哈希值是`bb81577b567262a21a4df5f6e335c1250acd7b50`。  <br/> **MD5**是由[[RFC1321]](http://www.rfc-editor.org/rfc/rfc1321.txt)定义 Internet 工程任务组 (IETF) MD5 消息摘要算法。 例如的电子邮件地址 melissa@contoso.com **MD5**哈希值是`c8c39e61ca1662477b39b83d7b0a0615`。  <br/> **CRC32MD5** **CRC32**的组合， **MD5**定义，如下所示：  <br/>  删除前导和尾随空白将所有字符都转换为小写规范化的电子邮件地址。  <br/>  计算的规范化的电子邮件地址的**CRC32**值，并使用此值的小数的整数表示形式。 如果您的实现返回有符号的整数，您必须将有符号的整数转换为无符号整数。  <br/>  计算的规范化的电子邮件地址的**MD5**值，并使用此值 （使用小写 A 到 F） 的十六进制表示。  <br/>  合并这两个值以下划线。  <br/>  例如的电子邮件地址 melissa@contoso.com **CRC32MD5**哈希值是`2149665315_c8c39e61ca1662477b39b83d7b0a0615`。  <br/> |
   
## <a name="capabilities-for-supporting-authentication-and-account-configuration"></a>支持身份验证和帐户配置的功能

|**元素**|**说明**|
|:-----|:-----|
|**allowChangesToAutoConfigure** <br/> |指示社交网络是否允许用户更改自动配置设置，例如提供不同的 URL 登录。  <br/> |
|**createAccountUrl** <br/> |如果提供程序将**hideHyperlinks**设置为**false**，，当用户单击**帐户配置**对话框中**单击此处以创建一个帐户**，在默认浏览器将打开**createAccountUrl**由指定的 URL。  <br/> |
|**displayUrl** <br/> |指示 OSC 是否应显示在帐户配置对话框的**URL 地址**文本框中的社交网络。  <br/> |
|**forgotPasswordUrl** <br/> |如果提供程序将**hideHyperlinks**设置为**false**，当用户单击**忘记密码？** 在**帐户配置**对话框中，将打开在默认浏览器中的**forgotPasswordUrl**由指定的 URL。  <br/> |
|**hideHyperlinks** <br/> |指示应**创建一个帐户，请单击此处**来隐藏 OSC 和**忘记密码？** 帐户配置对话框中的超链接。  <br/> OSC 1.0 将忽略此设置，并且始终隐藏超链接。 OSC 1.1 遵循此设置的值。  <br/> |
|**hideRememberMyPassword** <br/> |指示是否 OSC 应隐藏帐户配置对话框中的**记住密码**复选框。  <br/> 如果提供程序将**hideRememberMyPassword**设置为**true**，就好像未选中**记住密码**框中，并将不会保存密码将 act OSC。  <br/> 如果提供程序将**hideRememberMyPassword**设置为**false**，OSC 将显示在帐户配置对话框的**记住密码**复选框。  <br/> |
|**supportsAutoConfigure** <br/> |指示 OSC 是否应尝试自动配置并登录到社交网络中的用户在**ISocialProvider**界面上调用**GetAutoConfiguredSession**函数。  <br/> |
|**useLogonCached** <br/> |指示 OSC 提供程序是否支持[ISocialSession2::LogonCached](isocialsession2-logoncached.md)呼叫缓存凭据登录。  <br/> 如果提供程序将**useLogonCached**设置为**true**，OSC 忽略**useLogonWebAuth**的设置，OSC 调用**ISocialSession2::LogonCached**程序身份验证。  <br/> 如果提供程序将**dynamicActivitiesLookupEx**设置为**false**，则 OSC 不进行身份验证调用**ISocialSession2::LogonCached** 。  <br/> |
|**useLogonWebAuth** <br/> |指示是否应使用 OSC，基于表单的身份验证和[ISocialSession::LogonWeb](isocialsession-logonweb.md)方法。 如果提供程序将**useLogonWebAuth**设置为**false**，则 OSC 使用基本身份验证，并调用[ISocialSession::Logon](isocialsession-logon.md)方法。 如果提供程序将**useLogonWebAuth**设置为**true**，则 OSC 使用基于表单的身份验证，并调用**ISocialSession::LogonWeb**。  <br/> |
   
根据**功能**XML 返回提供程序在**ISocialProvider::GetCapabilities**方法中，帐户配置对话框更改。 如图 1 显示了一个 TestProvider 示例的帐户配置对话框。 
  
**图 1。在帐户配置对话框的 TestProvider 示例**

![TestProvider 示例配置信息](media/odc_ol14_ta_OSCFigure4.jpg)
  
## <a name="see-also"></a>另请参阅

- [功能 XML](xml-for-capabilities.md)

