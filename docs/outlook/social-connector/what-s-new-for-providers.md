---
title: 提供程序的新增功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 92f59a0d-3834-424d-ad81-167fdeba9bd0
description: 本主题列出了 Outlook Social Connector 2013 (.osc) 中的主要更改。 它对 outlook social connector 2013 与 outlook social connector 1.1 之间可用的功能进行了比较。
ms.openlocfilehash: 6b735555d312c149d7dc8b827990b96bfc229678
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435451"
---
# <a name="whats-new-for-providers"></a>提供程序的新增功能

本主题列出了 Outlook Social Connector 2013 (.osc) 中的主要更改。 它对 outlook social connector 2013 与 outlook social connector 1.1 之间可用的功能进行了比较。 此外, 它还介绍了已添加、更改或弃用的接口成员和 XML 元素。 
  
在 Office 2013 中, .osc 不仅适用于 Outlook, 还支持 sharepoint Server、sharepoint Workspace、Lync 客户端, 以及所有其他支持状态信息和联系人卡片的 Office 客户端应用程序。 一个 .osc 提供者可以在 "Outlook 人员" 窗格的 "**新增功能**" 选项卡中以及联系人卡片中显示社交信息更新。 
  
Outlook Social Connector 2013 中的一些主要更改包括以下几种: 
  
- 如果提供程序支持显示活动, 则提供程序将始终按需同步活动, 不再依赖于以前缓存的活动。 这意味着提供程序会将朋友和非好友的活动存储在内存中, 以显示更多当前活动。
    
- 出于安全考虑, 通过 Internet 与服务器通信的提供程序应使用 HTTPS (带有安全套接字层 (SSL) 协议的超文本传输协议 (HTTP)) 协议。 否则, 在传输过程中, 电子邮件地址、社交网络活动和其他用户数据可能会被截获或暴露。
    
- 如果你有适用于早期版本的 Outlook 的提供程序, 若要支持 Office 2013, 应更新安装程序包。 有关详细信息, 请参阅[安装清单](installation-checklist.md)。 
    
下表显示了 outlook social connector 2013 中的各种功能 (与 outlook social connector 1.1 相比) 的可用性。
  
|**功能**|**Outlook Social Connector 2013**|**Outlook Social Connector 1。1**|
|:-----|:-----|:-----|
|最终用户界面  <br/> |Outlook 中所有 Office 客户端应用程序和人员窗格中的 sharepoint Server、sharepoint Workspace、Lync 客户端、联系人卡片  <br/> |Outlook 中的人员窗格  <br/> |
|基本身份验证  <br/> |是  <br/> |是  <br/> |
|基于表单的身份验证  <br/> |是  <br/> |是  <br/> |
|缓存的身份验证  <br/> |是  <br/> |是  <br/> |
|默认存储上将好友的缓存同步到 "联系人" 文件夹  <br/> |是  <br/> |是  <br/> |
|将朋友的缓存活动同步到隐藏的**新闻源**文件夹  <br/> |否  <br/> |可访问  <br/> |
|在网络上的朋友和非朋友的按需同步 (图片、名称、标题)  <br/> |是  <br/> |是  <br/> |
|按需活动与网络上的朋友和非朋友同步  <br/> |是  <br/> |是  <br/> |
|关注网络  <br/> |是  <br/> |是  <br/> |
|不要关注网络  <br/> |是  <br/> |是  <br/> |
|访问用户配置文件页  <br/> |通过链接  <br/> |通过网络徽章  <br/> |
|在社交网络上观察隐私设置 (例如, 显示允许查看此类的非朋友的个人资料和活动)  <br/> |是  <br/> |是  <br/> |
|传递给提供程序的哈希电子邮件地址  <br/> |是  <br/> |是  <br/> |

<a name="OlSocialConnector_Changes"> </a>

## <a name="changes-from-the-previous-version-of-osc-provider-extensibility"></a>来自以前版本的 .osc 提供程序扩展性的更改

下表显示了已添加或已从相应接口中弃用的成员。
  
|**Interface 和 member**|**备注**|
|:-----|:-----|
|**ISocialProfile::GetActivitiesOfFriendsAndColleagues** <br/> |在 Outlook Social Connector 2013 中已弃用。 请注意, 由于 Outlook Social Connector 1.1, **ISocialSession:: GetActivities**也已被弃用。  <br/> 若要同步活动源, 应实现[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 将**dynamicActivitiesLookupEx**设置为**true**, 这将提示 .osc 调用**ISocialSession2:: GetActivitiesEx**而不是。  <br/> |
   
下表显示了已更改的架构元素。
  
|**Schema 元素**|**备注**|
|:-----|:-----|
|**能力** <br/> |在 Outlook Social Connector 2013: **allowChangesToAutoConfigure**元素中添加。  <br/> 在 Outlook Social Connector 2013: **cacheActivities**元素中已弃用。  <br/> |
|**person** <br/> |在 Outlook Social Connector 2013 中添加: **askmeabout**、 **businessAddress**、 **businessCity**、 **businessCountryOrRegion**、 **businessState**、 **businessZip**、**工业**、**兴趣** **location**、 **otherAddress**、 **otherCity**、 **otherCountryOrRegion**、 **otherState**、 **otherZip**、**技能**、**学校**和**网站**元素。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [XML 的功能](xml-for-capabilities.md)
- [适用于好友的 XML](xml-for-friends.md)
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

