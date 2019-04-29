---
title: 测试活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 98343c36-5e32-4d07-b474-adfeca693135
description: 本主题介绍了验证 Outlook Social Connector (.osc) 提供程序是否使用按需同步以适当地返回朋友和非好友活动的测试和方案。
ms.openlocfilehash: 0a40dca84681a9e758c2f17d2647c339ded70462
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436298"
---
# <a name="testing-activities"></a>测试活动

本主题介绍了验证 Outlook Social Connector (.osc) 提供程序是否使用按需同步以适当地返回朋友和非好友活动的测试和方案。

<a name="olosc_TestingActivities_OnDemandSync"> </a>

## <a name="on-demand-synchronization"></a>按需同步

一个 .osc 提供程序实现**ISocialProvider:: GetCapabilities**, 其中的 .osc 调用它可确定提供程序是否支持对朋友和非好友活动的按需同步。 对于在 Outlook 人员窗格中显示的人员, .osc 获取并散列其 SMTP 地址, 调用[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md), 并存储 (在内存中) 这些人员返回的活动数据。 
  
### <a name="determining-activities-to-get"></a>确定要获取的活动

传递给**GetActivitiesEx**的哈希 SMTP 地址是确定 .osc 是否会为朋友或非好友获取活动的关键。 如果用户在其社交网络帐户中指定了该 SMTP 地址, 则 .osc 将获取这些活动。 如果此人在其社交网络帐户中不包含该 SMTP 地址, 或者如果该用户是社交网络中的其他电子邮件地址, 则**GetActivitiesEx**不会获取此人的活动。 此外, 对于不是友元但在其社交网络帐户中指定了 SMTP 地址的人, 返回的数据只包括该人员的隐私设置允许的非友元所提供的内容。 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a>为朋友和非好友创建测试主题

若要为友元创建测试主题, 请确定在其社交网络帐户中包含该地址的人员的 SMTP 地址, 以及该网络上具有登录用户的好友状态。 创建包含该 SMTP 地址的电子邮件。 同样, 若要为非友元创建测试主题, 请确定该地址不是已登录用户的好友的用户的 SMTP 地址, 以及在他或她的隐私设置中指定的用户, 以允许非好友在社交网络上查看其配置文件。 创建包含该 SMTP 地址的电子邮件。 
  
在 Outlook 资源管理器中, 当您选择包含朋友 (或非好友) 的电子邮件时, "人员" 窗格将显示收件人。 通过选择 "人员" 窗格中的好友 (或非好友), 您可以测试提供商是否提供有关此人的信息。
  
### <a name="test-scenarios"></a>测试方案

若要验证您是否正在为朋友和非好友获取适当的活动, 请测试以下方案。
  
|**方案**|**预期行为**|
|:-----|:-----|
|在 "人员" 窗格中选择的人是社交网络中已登录用户的好友。  <br/> |"人员" 窗格显示该用户的配置文件以及在社交网络中发布的个人资料图片。  <br/> |
|在 "人员" 窗格中选择的人是社交网络中已登录用户的非朋友, 但允许非好友查看他或她的个人资料。  <br/> |"人员" 窗格显示该用户的配置文件以及在社交网络中发布的个人资料图片。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [同步好友和活动](synchronizing-friends-and-activities.md)  
- [适用于活动的 XML](xml-for-activities.md)
- [准备发布一个 .osc 提供程序](getting-ready-to-release-an-osc-provider.md)

