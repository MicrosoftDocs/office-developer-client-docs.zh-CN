---
title: 测试朋友
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 109c34b6-911b-4dfc-9799-aadf47172e84
description: 本主题介绍测试和方案，验证 Outlook Social Connector (OSC) 提供程序适当地返回数据的朋友和非朋友，如果适用，具体取决于提供程序支持的同步模式。
ms.openlocfilehash: 232977836833a9ef981ebef38c9ee243ea2dd2ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779350"
---
# <a name="testing-friends"></a>测试朋友

本主题介绍测试和方案，验证 Outlook Social Connector (OSC) 提供程序适当地返回数据的朋友和非朋友，如果适用，具体取决于提供程序支持的同步模式。

<a name="olosc_TestingFriends_CachedSync"> </a>

## <a name="cached-synchronization"></a>高速缓存的同步

OSC 提供程序实现[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)，后者 OSC 调用以确定提供程序是否支持朋友的数据缓存的同步。 调用[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)后, OSC 将返回的朋友的数据存储中特定于登录用户的默认 Outlook 存储区中的社交网络联系人文件夹。 OSC 还调用[ISocialSession::GetPerson](isocialsession-getperson.md)和[ISocialPerson::GetPicture](isocialperson-getpicture.md)来获取每个朋友配置文件图片。 
  
### <a name="initiate-synchronization"></a>启动同步

若要启动同步，您可以打开和使用 Microsoft Office Fluent 用户界面的功能区组件中的调试按钮**同步联系人**。 有关 OSC 调试按钮的详细信息，请参阅[调试提供程序](debugging-a-provider.md)。 
  
### <a name="test-scenarios"></a>测试方案

测试以下各项验证朋友的数据缓存正确。
  
|**要测试项**|**预期的行为**|
|:-----|:-----|
|联系人文件夹  <br/> |用户的默认 Outlook 存储中存在社交网络特定联系人文件夹。  <br/> |
|返回**ISocialPerson::GetFriendsAndColleagues**朋友的数据 <br/> |每个朋友对应于特定于网络的联系人文件夹中的联系人。  <br/> |
|朋友的数据  <br/> |为每个朋友联系人字段具有正确的数据。  <br/> |
|返回**ISocialPerson::GetPicture**朋友的配置文件图片 <br/> |联系人项目的每个朋友包含配置文件图片。  <br/> |

<a name="olosc_TestingFriends_OnDemandSync"> </a>

## <a name="on-demand-synchronization"></a>按需同步

OSC 提供程序实现**ISocialProvider::GetCapabilities**，后者 OSC 调用以确定提供程序是否支持朋友和非朋友的按需同步。 在 Outlook 人员窗格中显示的人员，OSC 获取和哈希其 SMTP 地址，调用[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)，并将数据存储 （内存） 中返回这些人员。 
  
### <a name="determining-friends-and-non-friends"></a>确定朋友和非朋友

传递给**GetPeopleDetails**的哈希的 SMTP 地址是确定联系人是否朋友或非朋友的关键。 如果某人未他/她的社交网络帐户中包含的 SMTP 地址或**GetPeopleDetails**即使这个人正朋友的社交网络上的不同的电子邮件地址，为该人为**仍返回**nonfriend**friendStatus** _personsCollection_参数中。 此外，对于不朋友但他/她的社交网络帐户中指定的 SMTP 地址的人员，返回的数据包括仅什么是可用于非-朋友允许由该联系人的隐私设置。 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a>创建测试主题朋友和非朋友

若要创建朋友的测试主题，确定谁他/她的社交网络帐户中包括该地址和谁有朋友状态与登录用户的网络上的人的 SMTP 地址。 创建包含该 SMTP 地址的电子邮件。 同样，若要创建非朋友的测试主题，确定某个人的 SMTP 地址用户不是按该地址，登录用户的朋友和谁他/她隐私设置，以允许非朋友以查看其活动上社交网络中具有指定的尚未k。 创建包含该 SMTP 地址的电子邮件。 
  
在 Outlook 资源管理器中，选择电子邮件，其中包括朋友 （或非朋友） 中，人员窗格中显示的收件人。 在人员窗格中选择的好朋友 （或非朋友） 允许您测试提供程序提供了有关此人的信息。
  
### <a name="test-scenarios"></a>测试方案

若要验证您的提供商提供信息朋友和非朋友相应地，测试以下方案。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|在人员窗格中选择的人员是与社交网络上的登录用户朋友。  <br/> |人员窗格显示社交网络上的此人的活动。  <br/> |
|在人员窗格中选择的人员非朋友，登录用户的社交网络中，但已允许通过非朋友查看他/她活动。  <br/> |人员窗格显示社交网络上的此人的活动。  <br/> |

<a name="olosc_TestingFriends_OnDemandSync"> </a>

## <a name="hybrid-synchronization"></a>混合同步

如果 OSC 提供程序支持的朋友和非朋友混合同步，OSC 执行以下任务： 
  
- OSC 社交网络特定联系人文件夹中存储的朋友登录用户的信息。
    
- OSC 检索社交网络中，为非朋友需求的信息，并将其存储在内存中，但不能在一个文件夹。
    
若要测试混合同步，按照为朋友[缓存同步](#olosc_TestingFriends_CachedSync)部分中的测试建议和非朋友[按需同步](#olosc_TestingFriends_OnDemandSync)部分中。 
  
## <a name="see-also"></a>另请参阅

- [同步朋友和活动](synchronizing-friends-and-activities.md) 
- [朋友 XML](xml-for-friends.md)
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

