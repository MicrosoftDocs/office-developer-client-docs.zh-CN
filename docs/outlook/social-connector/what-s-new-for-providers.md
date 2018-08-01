---
title: 提供程序的新增功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 92f59a0d-3834-424d-ad81-167fdeba9bd0
description: 本主题列出了在 Outlook Social Connector 2013 (OSC) 的主要更改。 它提供 Outlook Social Connector 2013 和 Outlook Social Connector 1.1 之间可用的功能的比较。
ms.openlocfilehash: bdd7f7998f34a0ad096964050543f3f687bd0841
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779347"
---
# <a name="whats-new-for-providers"></a>提供程序的新增功能

本主题列出了在 Outlook Social Connector 2013 (OSC) 的主要更改。 它提供 Outlook Social Connector 2013 和 Outlook Social Connector 1.1 之间可用的功能的比较。 该参数还描述接口成员和 XML 元素的已添加、 更改或弃用。 
  
Office 2013 中 OSC 适用于不仅 Outlook，但还 SharePoint Server、 SharePoint Workspace，Lync 客户端和所有其他 Office 客户端应用程序支持的状态信息和联系人卡片。 OSC 提供程序可以显示**WHAT 'S NEW**选项卡在 Outlook 的人员窗格中，以及在联系人卡片中的社交信息更新。 
  
Outlook Social Connector 2013 中的一些主要更改包括： 
  
- 如果提供程序支持显示活动，就始终将按需活动同步提供程序和不再依赖以前缓存活动。 这意味着提供程序以显示更多当前活动的内存中存储的朋友活动和非朋友。
    
- 出于安全考虑，通过 Internet 与服务器进行通信的提供程序应使用 HTTPS (超文本传输协议 (HTTP) 使用安全套接字层 (SSL)) 协议。 否则，为电子邮件地址、 社交网络活动和其他用户截获或在传输过程中公开的数据的风险。
    
- 如果必须使用 Outlook 的早期版本的提供程序，以支持 Office 2013，您应更新安装程序包。 有关详细信息，请参阅[安装清单](installation-checklist.md)。 
    
下表显示用于 Outlook Social Connector 1.1 Outlook Social Connector 2013 中的各种功能的可用性。
  
|**功能**|**Outlook Social Connector 2013**|**Outlook Social Connector 1.1**|
|:-----|:-----|:-----|
|最终用户界面  <br/> |SharePoint Server、 SharePoint Workspace Lync 客户端，所有 Office 客户端应用程序中的联系人卡片和 Outlook 中的人员窗格  <br/> |在 Outlook 中的人员窗格  <br/> |
|基本身份验证  <br/> |可访问  <br/> |可访问  <br/> |
|基于表单的身份验证  <br/> |可访问  <br/> |可访问  <br/> |
|缓存的身份验证  <br/> |可访问  <br/> |可访问  <br/> |
|缓存的同步到默认的联系人文件夹的朋友存储  <br/> |可访问  <br/> |可访问  <br/> |
|隐藏的**新闻源**文件夹朋友缓存的活动同步  <br/> |否  <br/> |可访问  <br/> |
|朋友和非朋友网络上的按需同步 （图片、 名称、 标题）  <br/> |可访问  <br/> |可访问  <br/> |
|朋友和非朋友网络上的按需活动同步  <br/> |可访问  <br/> |可访问  <br/> |
|请按照网络  <br/> |可访问  <br/> |可访问  <br/> |
|在网络上不会遵循  <br/> |可访问  <br/> |可访问  <br/> |
|访问用户配置文件页面  <br/> |通过链接  <br/> |通过网络徽章  <br/> |
|观察社交网络 （例如，显示配置文件和活动的非-朋友允许查看例如） 上的隐私设置  <br/> |可访问  <br/> |可访问  <br/> |
|传递给提供程序的哈希电子邮件地址  <br/> |可访问  <br/> |可访问  <br/> |

<a name="OlSocialConnector_Changes"> </a>

## <a name="changes-from-the-previous-version-of-osc-provider-extensibility"></a>从 OSC 提供程序扩展性的早期版本的更改

下表显示了已添加或从相应的接口已弃用的成员。
  
|**接口和成员**|**Comment**|
|:-----|:-----|
|**ISocialProfile::GetActivitiesOfFriendsAndColleagues** <br/> |Outlook Social Connector 2013 中弃用。 请注意**ISocialSession::GetActivities**也已被弃用以来 Outlook Social Connector 1.1。  <br/> 若要将活动源同步，应实现[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 设置为**true**，这将会进行提示 OSC 改为呼叫**ISocialSession2::GetActivitiesEx** **dynamicActivitiesLookupEx** 。  <br/> |
   
下表显示了已更改的架构元素。
  
|**架构元素**|**Comment**|
|:-----|:-----|
|**capabilities** <br/> |Outlook Social Connector 2013 中添加： **allowChangesToAutoConfigure**元素。  <br/> Outlook Social Connector 2013 中弃用： **cacheActivities**元素。  <br/> |
|**person** <br/> |Outlook Social Connector 2013 中添加： **askmeabout**、 **businessAddress**、 **businessCity**、 **businessCountryOrRegion**、 **businessState**、 **businessZip**、**行业**、**兴趣**、 **位置**， **otherAddress**、 **otherCity**、 **otherCountryOrRegion**、 **otherState**、 **otherZip**、**技能**、**学校**和**网站**的元素。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [功能 XML](xml-for-capabilities.md)
- [朋友 XML](xml-for-friends.md)
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

