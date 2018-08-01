---
title: 有关正确显示活动的指南
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 55268188-8432-4145-9527-f5888949fc24
description: Outlook Social Connector (OSC) 提供程序可以设置 getActivities 和 dynamicActivitiesLookupEx 元素具有 OSC 存储在内存中的活动项目。
ms.openlocfilehash: f8cb5850c8920f09f784343db18372bb75ca17a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779200"
---
# <a name="guidelines-for-properly-displaying-activities"></a>有关正确显示活动的指南

Outlook Social Connector (OSC) 提供程序可以设置**getActivities**和**dynamicActivitiesLookupEx**元素具有 OSC 存储在内存中的活动项目。 本主题介绍 Api OSC 调用来获取或刷新活动和活动所有者详细信息，如果 OSC 提供程序支持同步活动源与社交网络 OSC 提供程序扩展性。 主题还列出了为 OSC 提供程序无法正常显示活动，在 Office 联系人卡片或 Outlook 人员窗格 OSC **activityFeed**元素的一些子元素。 
  
- OSC 调用[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法获取和登录用户的新闻源文件夹中存储活动。 OSC 提供程序必须实现**GetActivitiesEx**返回符合 OSC 提供程序**activityFeed**元素的 XML 架构定义一个_活动_XML 字符串。 
    
- OSC 提供程序必须设置**ownerID**元素，它是**activityDetails**元素的子元素。 **ownerID**是活动的不透明字符串，标识社交网络上的所有者。 
    
- OSC 提供程序应在**templateVariables**元素的**publisherVariable**节点中设置的**nameHint**和**emailAddress**元素。 
    
   请注意，每个 OSC 提供程序 XML 架构， **nameHint**元素是可选的元素。 OSC 使用它来匹配的联系人卡片或人员窗格中选定的用户的显示名称。 同样， **emailAddress**元素是可选的 XML 架构中元素。 OSC 使用它来匹配的联系人卡片或人员窗格中选定的用户的 SMTP 地址。 
    
   如果只指定**ownerID**元素，但未指定一个或两个**nameHint**和**电子邮件地址**，OSC 调用[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)方法然后[ISocialPerson::GetDetails](isocialperson-getdetails.md)若要获取有关由**ownerID**标识的人员的详细信息的方法。 当 OSC 调用**ISocialPerson::GetDetails**时，提供程序必须返回**人**指定的**全名**和**emailAddress**元素的 XML。 
    
## <a name="see-also"></a>另请参阅

- [活动的 XML](xml-for-activities.md)  
- [朋友 XML](xml-for-friends.md)  
- [功能 XML](xml-for-capabilities.md)

