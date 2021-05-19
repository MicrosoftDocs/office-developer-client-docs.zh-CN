---
title: 提供程序的新增功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 92f59a0d-3834-424d-ad81-167fdeba9bd0
description: 本主题列出了 OSC Outlook Social Connector 2013 (的主要) 。 它比较了 Outlook Social Connector 2013 和 Outlook Social Connector 1.1 之间的可用功能。
ms.openlocfilehash: 6b735555d312c149d7dc8b827990b96bfc229678
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435451"
---
# <a name="whats-new-for-providers"></a>提供程序的新增功能

本主题列出了 OSC Outlook Social Connector 2013 (的主要) 。 它比较了 Outlook Social Connector 2013 和 Outlook Social Connector 1.1 之间的可用功能。 它还描述了已添加、更改或弃用的接口成员和 XML 元素。 
  
在 Office 2013 中，OSC 不仅适用于 Outlook，还适用于 SharePoint Server、SharePoint Workspace、Lync 客户端以及支持状态信息和联系人卡片的所有其他 Office 客户端应用程序。 OSC 提供程序可以在"人员"窗格的"新增功能"选项卡Outlook联系人卡片中显示社交信息更新。 
  
Social Connector 2013 Outlook一些主要更改包括： 
  
- 如果提供程序支持显示活动，提供程序将始终按需同步活动，并且不再依赖于之前缓存的活动。 这意味着提供程序将好友和非好友的活动存储在内存中，以显示更多当前活动。
    
- 出于安全考虑，通过 Internet 与服务器通信的提供程序应该将 HTTPS (超文本传输协议 (HTTP) 与安全套接字层 (SSL) ) 协议一同使用。 否则，在传输过程中可能会截获或公开电子邮件地址、社交网络活动和其他用户数据。
    
- 如果有使用早期版本的 Outlook，若要支持 Office 2013，应更新安装程序包。 有关详细信息 [，请参阅](installation-checklist.md) 安装清单。 
    
下表显示与 Outlook Social Connector 1.1 相比 Outlook Connector 2013 中各种功能的可用性。
  
|**功能**|**Outlook Social Connector 2013**|**OutlookSocial Connector 1.1**|
|:-----|:-----|:-----|
|最终用户界面  <br/> |SharePoint所有SharePoint客户端应用程序中的服务器、SharePoint Workspace、Lync 客户端、联系人Office和联系人窗格中Outlook  <br/> |"人员"窗格中Outlook  <br/> |
|基本身份验证  <br/> |是  <br/> |是  <br/> |
|基于表单的身份验证  <br/> |是  <br/> |是  <br/> |
|缓存身份验证  <br/> |是  <br/> |是  <br/> |
|默认存储上好友到联系人文件夹的缓存同步  <br/> |是  <br/> |是  <br/> |
|缓存活动将好友同步到隐藏的 **"新闻源"** 文件夹  <br/> |否  <br/> |是  <br/> |
|按需同步 (网络上好友) 好友和非好友的图片、姓名、标题和图片  <br/> |是  <br/> |是  <br/> |
|网络上好友和非好友的按需活动同步  <br/> |是  <br/> |是  <br/> |
|在网络中关注  <br/> |是  <br/> |是  <br/> |
|不关注网络  <br/> |是  <br/> |是  <br/> |
|访问用户配置文件页面  <br/> |通过链接  <br/> |通过网络锁屏提醒  <br/> |
|在社交网络上观察隐私 (例如，显示允许查看此类信息的非好友的个人资料)   <br/> |是  <br/> |是  <br/> |
|传递给提供程序的哈希电子邮件地址  <br/> |是  <br/> |是  <br/> |

<a name="OlSocialConnector_Changes"> </a>

## <a name="changes-from-the-previous-version-of-osc-provider-extensibility"></a>以前版本的 OSC 提供程序扩展性的更改

下表显示了已在相应接口中添加或弃用的成员。
  
|**接口和成员**|**Comment**|
|:-----|:-----|
|**ISocialProfile::GetActivitiesOfFriendsAndColleagues** <br/> |在 Social Connector 2013 Outlook弃用。 请注意，自 Social Connector 1.1 起 **，ISocialSession：：GetActivities** Outlook已弃用。  <br/> 若要同步活动源，应实现 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法。 将 **dynamicActivitiesLookupEx** 设置为 **true**，这将提示 OSC 改为调用 **ISocialSession2：：GetActivitiesEx。**  <br/> |
   
下表显示了已更改的架构元素。
  
|**Schema 元素**|**Comment**|
|:-----|:-----|
|**capabilities** <br/> |在 social Connector 2013 **Outlook：allowChangesToAutoConfigure 元素** 中添加。  <br/> 在 social Connector 2013 Outlook弃用 **：cacheActivities** 元素。  <br/> |
|**person** <br/> |在Outlook Social Connector 2013 中添加：askmeabout、businessAddress、businessCity、businessCountryOrRegion、businessState、businessZip、industries、interests、location、otherAddress、otherCity、otherCountryOrRegion、otherState、otherZip、skills、schools 和 website 元素。                  <br/> |
   
## <a name="see-also"></a>另请参阅

- [功能的 XML](xml-for-capabilities.md)
- [好友 XML](xml-for-friends.md)
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

