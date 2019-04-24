---
title: 测试好友
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 109c34b6-911b-4dfc-9799-aadf47172e84
description: 本主题介绍测试和方案, 以验证 Outlook Social Connector (.osc) 提供程序是否根据提供程序支持的同步模式, 适当地返回了朋友和非朋友的数据 (如果适用)。
ms.openlocfilehash: 1c97342fd5b219b15b1f58dbc065fc268f8e81d7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338785"
---
# <a name="testing-friends"></a>测试好友

本主题介绍测试和方案, 以验证 Outlook Social Connector (.osc) 提供程序是否根据提供程序支持的同步模式, 适当地返回了朋友和非朋友的数据 (如果适用)。

<a name="olosc_TestingFriends_CachedSync"> </a>

## <a name="cached-synchronization"></a>缓存同步

一个 .osc 提供程序实现[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md), 其中的 .osc 调用它可确定提供程序是否支持朋友数据的缓存同步。 在调用[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)后, .osc 将返回的朋友的数据存储在登录用户的默认 Outlook 存储中的社交网络特定的联系人文件夹中。 此外, .osc 还调用[ISocialSession:: GetPerson](isocialsession-getperson.md)和[ISocialPerson:: GetPicture](isocialperson-getpicture.md)以获取每个朋友的个人资料图片。 
  
### <a name="initiate-synchronization"></a>启动同步

若要启动同步, 可以在 Microsoft Office 熟知用户界面的功能区组件中打开和使用 "调试" 按钮**同步联系人**。 有关 .osc 调试按钮的详细信息, 请参阅[调试提供程序](debugging-a-provider.md)。 
  
### <a name="test-scenarios"></a>测试方案

测试以下项目以验证是否正确缓存了朋友的数据。
  
|**要测试的项**|**预期行为**|
|:-----|:-----|
|"联系人" 文件夹  <br/> |用户的默认 Outlook 存储中存在 "社交网络特定的联系人" 文件夹。  <br/> |
|由 ISocialPerson 返回的好友数据 **:: GetFriendsAndColleagues** <br/> |每个朋友对应于特定于网络的 "联系人" 文件夹中的联系人。  <br/> |
|朋友的数据  <br/> |每个好友的联系人字段都有正确的数据。  <br/> |
|朋友的个人资料图片由**ISocialPerson 返回:: GetPicture** <br/> |每个朋友的联系人项目包含个人资料图片。  <br/> |

<a name="olosc_TestingFriends_OnDemandSync"> </a>

## <a name="on-demand-synchronization"></a>按需同步

一个 .osc 提供程序实现**ISocialProvider:: GetCapabilities**, 其中的 .osc 调用它可确定提供程序是否支持对朋友和非好友的按需同步。 对于在 Outlook 人员窗格中显示的人员, .osc 获取并散列其 SMTP 地址, 调用[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md), 并存储 (在内存中) 这些人员返回的数据。 
  
### <a name="determining-friends-and-non-friends"></a>确定朋友和非好友

传递给**GetPeopleDetails**的哈希 SMTP 地址是用于确定某人是否为朋友或非朋友的关键。 如果某个人在其社交网络帐户中不包含该 SMTP 地址, 或者即使此人是社交网络中的其他电子邮件地址的朋友, **GetPeopleDetails**仍将此人的**nonfriend**返回为**** _personsCollection_参数中的 friendStatus。 此外, 对于不是友元但在其社交网络帐户中指定了 SMTP 地址的人, 返回的数据只包括该人员的隐私设置允许的非友元所提供的内容。 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a>为朋友和非好友创建测试主题

若要为友元创建测试主题, 请确定在其社交网络帐户中包含该地址的人员的 SMTP 地址, 以及该网络上具有登录用户的好友状态。 创建包含该 SMTP 地址的电子邮件。 同样, 若要为非友元创建测试主题, 请确定该地址不是已登录用户的友元的用户的 SMTP 地址, 并且尚未在他或她的隐私设置中指定的用户, 以允许非朋友在社交 networ 上查看其活动。kb. 创建包含该 SMTP 地址的电子邮件。 
  
在 Outlook 资源管理器中, 当您选择包含朋友 (或非好友) 的电子邮件时, "人员" 窗格将显示收件人。 通过选择 "人员" 窗格中的好友 (或非好友), 您可以测试提供商是否提供有关此人的信息。
  
### <a name="test-scenarios"></a>测试方案

若要验证您的提供商是否已正确提供有关好友和非好友的信息, 请测试以下方案。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|在 "人员" 窗格中选择的人是社交网络中已登录用户的好友。  <br/> |"人员" 窗格在社交网络上显示此人的活动。  <br/> |
|在 "人员" 窗格中选择的人是社交网络中已登录用户的非朋友, 但允许非好友查看他或她的活动。  <br/> |"人员" 窗格在社交网络上显示此人的活动。  <br/> |

<a name="olosc_TestingFriends_OnDemandSync"> </a>

## <a name="hybrid-synchronization"></a>混合同步

如果 .osc 提供商支持朋友和非好友的混合同步, 则 .osc 将执行以下操作: 
  
- .osc 存储有关特定于社交网络的联系人文件夹中登录用户的好友信息。
    
- .osc 从社交网络检索非朋友的信息, 并将其存储在内存中, 而不是文件夹中。
    
若要测试混合同步, 请按照针对好友的[缓存的同步](#olosc_TestingFriends_CachedSync)部分中的测试建议, 以及非好友的[点播同步](#olosc_TestingFriends_OnDemandSync)部分中的测试建议。 
  
## <a name="see-also"></a>另请参阅

- [同步好友和活动](synchronizing-friends-and-activities.md) 
- [适用于好友的 XML](xml-for-friends.md)
- [准备发布一个 .osc 提供程序](getting-ready-to-release-an-osc-provider.md)

