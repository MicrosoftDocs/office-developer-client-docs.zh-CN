---
title: 测试好友
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 109c34b6-911b-4dfc-9799-aadf47172e84
description: 本主题介绍用于验证 Outlook Social Connector (OSC) 提供程序是否适当返回好友和非好友的数据的测试和方案（如果适用，具体取决于提供程序支持的同步模式）。
ms.openlocfilehash: 1c97342fd5b219b15b1f58dbc065fc268f8e81d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433666"
---
# <a name="testing-friends"></a>测试好友

本主题介绍用于验证 Outlook Social Connector (OSC) 提供程序是否适当返回好友和非好友的数据的测试和方案（如果适用，具体取决于提供程序支持的同步模式）。

<a name="olosc_TestingFriends_CachedSync"> </a>

## <a name="cached-synchronization"></a>缓存同步

OSC 提供程序实现 [ISocialProvider：：GetCapabilities，OSC](isocialprovider-getcapabilities.md)将调用它来确定提供程序是否支持好友数据的缓存同步。 调用[ISocialPerson：：GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)后，OSC 将返回的好友数据存储在已登录用户的默认 Outlook 存储中特定于社交网络的联系人文件夹中。 OSC 还调用 [ISocialSession：：GetPerson](isocialsession-getperson.md) 和 [ISocialPerson：：GetPicture](isocialperson-getpicture.md) 以获取每个好友的个人资料图片。 
  
### <a name="initiate-synchronization"></a>启动同步

若要启动同步，您可以打开并使用调试按钮 **Sync Contacts** in the ribbon component of the Microsoft Office Fluent user interface. 有关 OSC 调试按钮详细信息，请参阅 [调试提供程序](debugging-a-provider.md)。 
  
### <a name="test-scenarios"></a>测试方案

测试以下项以验证好友的数据是否缓存正确。
  
|**要测试的项目**|**预期行为**|
|:-----|:-----|
|"联系人"文件夹  <br/> |特定于社交网络的联系人文件夹位于用户的默认联系人Outlook存储区中。  <br/> |
|**ISocialPerson：：GetFriendsAndColleagues** 返回的好友数据 <br/> |每个好友对应于特定于网络的联系人文件夹中的一个联系人。  <br/> |
|好友数据  <br/> |每个好友的联系人字段具有正确的数据。  <br/> |
|**ISocialPerson：：GetPicture** 返回的好友个人资料图片 <br/> |每个好友的联系人项目都包含个人资料图片。  <br/> |

<a name="olosc_TestingFriends_OnDemandSync"> </a>

## <a name="on-demand-synchronization"></a>按需同步

OSC 提供程序实现 **ISocialProvider：：GetCapabilities，OSC** 将调用它以确定提供程序是否支持好友和非好友的按需同步。 对于 Outlook 人员窗格中显示的人员，OSC 获取其 SMTP 地址并哈希，调用[ISocialSession2：：GetPeopleDetails，](isocialsession2-getpeopledetails.md)将 (存储在内存中) 为这些人员返回的数据。 
  
### <a name="determining-friends-and-non-friends"></a>确定好友和非好友

传递给 **GetPeopleDetails** 的哈希 SMTP 地址是确定某个人是好友还是非好友的关键。 如果某人的社交网络帐户中未包含该 SMTP 地址，或者即使此人是社交网络上其他电子邮件地址的好友 **，GetPeopleDetails** 仍将此人的不好友作为 _personCollection_ 参数中的 **friendStatus** 返回。  此外，对于不是好友但在社交网络帐户中指定 SMTP 地址的人，返回的数据仅包括非好友的隐私设置允许的可用内容。 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a>为好友和非好友创建测试主题

若要为好友创建测试主题，请确定其社交网络帐户中包含该地址的用户的 SMTP 地址，以及该网络上登录用户具有好友状态的用户的 SMTP 地址。 创建包含该 SMTP 地址的电子邮件。 同样，若要为非好友创建测试主题，请通过该地址标识非登录用户好友的用户的 SMTP 地址，以及已使用其隐私设置指定以允许非好友查看其社交网络上的活动的用户的 SMTP 地址。 创建包含该 SMTP 地址的电子邮件。 
  
在Outlook资源管理器中，选择包含好友或非好友 (的电子邮件时，) 窗格将显示收件人。 在人员 (选择好友或) 联系人，可以测试提供商是否提供有关该人员的信息。
  
### <a name="test-scenarios"></a>测试方案

若要验证你的提供商是否适当地提供有关好友和非好友的信息，请测试以下方案。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|在人员窗格中选择的人是社交网络上登录的用户的好友。  <br/> |人员窗格在社交网络上显示此人的活动。  <br/> |
|在人员窗格中选择的用户是社交网络上已登录用户的非好友，但允许非好友查看其活动。  <br/> |人员窗格在社交网络上显示此人的活动。  <br/> |

<a name="olosc_TestingFriends_OnDemandSync"> </a>

## <a name="hybrid-synchronization"></a>混合同步

如果 OSC 提供程序支持好友和非好友的混合同步，OSC 将执行以下操作： 
  
- OSC 将登录用户的好友信息存储在特定于社交网络的联系人文件夹中。
    
- OSC 从社交网络检索非好友按需信息，并仅将该信息存储在内存中，而不是存储在文件夹中。
    
若要测试混合同步，请按照"缓存同步"部分（[](#olosc_TestingFriends_CachedSync)对于好友）和非好友的"按需同步"部分[](#olosc_TestingFriends_OnDemandSync)中的测试建议操作。 
  
## <a name="see-also"></a>另请参阅

- [同步好友和活动](synchronizing-friends-and-activities.md) 
- [好友 XML](xml-for-friends.md)
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

