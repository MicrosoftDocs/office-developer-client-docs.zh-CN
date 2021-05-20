---
title: 测试活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 98343c36-5e32-4d07-b474-adfeca693135
description: 本主题介绍用于验证 Outlook Social Connector (OSC) 提供程序是否使用按需同步正确返回好友和非好友的活动的测试和方案。
ms.openlocfilehash: 0a40dca84681a9e758c2f17d2647c339ded70462
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436298"
---
# <a name="testing-activities"></a>测试活动

本主题介绍用于验证 Outlook Social Connector (OSC) 提供程序是否使用按需同步正确返回好友和非好友的活动的测试和方案。

<a name="olosc_TestingActivities_OnDemandSync"> </a>

## <a name="on-demand-synchronization"></a>按需同步

OSC 提供程序实现 **ISocialProvider：：GetCapabilities，OSC** 将调用它以确定提供程序是否支持好友和非好友的活动按需同步。 对于 Outlook 人员窗格中显示的人员，OSC 获取其 SMTP 地址并哈希，调用[ISocialSession2：：GetActivitiesEx，](isocialsession2-getactivitiesex.md)将 (存储在内存中) 为这些人员返回的活动数据。 
  
### <a name="determining-activities-to-get"></a>确定要获取的活动

传递给 **GetActivitiesEx** 的哈希 SMTP 地址是确定 OSC 是否将获取好友或非好友活动的关键。 如果某人在社交网络帐户中指定 SMTP 地址，OSC 将获取此人的活动。 如果用户的社交网络帐户中未包含该 SMTP 地址，或者此人是好友，但通过社交网络上的不同电子邮件地址， **则 GetActivitiesEx** 不会获取此人的活动。 此外，对于不是好友但指定其社交网络帐户中的 SMTP 地址的人，返回的数据仅包括非好友的隐私设置允许的可用内容。 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a>为好友和非好友创建测试主题

若要为好友创建测试主题，请确定其社交网络帐户中包含该地址的用户的 SMTP 地址，以及该网络上登录用户具有好友状态的用户的 SMTP 地址。 创建包含该 SMTP 地址的电子邮件。 同样，若要为非好友创建测试主题，请通过该地址标识非登录用户好友的用户的 SMTP 地址，以及已使用其隐私设置指定以允许非好友在社交网络上查看其个人资料的用户的 SMTP 地址。 创建包含该 SMTP 地址的电子邮件。 
  
在Outlook资源管理器中，选择包含好友或非好友 (的电子邮件时，) 窗格将显示收件人。 在人员 (选择好友或) 联系人，可以测试提供商是否提供有关该人员的信息。
  
### <a name="test-scenarios"></a>测试方案

若要验证是否正在获取好友和非好友的适当活动，请测试以下方案。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|在人员窗格中选择的人是社交网络上登录的用户的好友。  <br/> |人员窗格在社交网络上显示此人的个人资料和个人资料图片。  <br/> |
|在人员窗格中选择的人是社交网络上已登录用户的非好友，但允许非好友查看其个人资料。  <br/> |人员窗格在社交网络上显示此人的个人资料和个人资料图片。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [同步好友和活动](synchronizing-friends-and-activities.md)  
- [活动的 XML](xml-for-activities.md)
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

