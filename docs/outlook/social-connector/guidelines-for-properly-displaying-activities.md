---
title: 有关正确显示活动的指南
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 55268188-8432-4145-9527-f5888949fc24
description: Outlook Social Connector (.osc) 提供程序可以设置 getActivities 和 dynamicActivitiesLookupEx 元素, 使其具有内存中的 .osc 存储活动项。
ms.openlocfilehash: b2fcaa125ac8bf7924726f4f09ff507769c3a3f7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422913"
---
# <a name="guidelines-for-properly-displaying-activities"></a>有关正确显示活动的指南

Outlook Social Connector (.osc) 提供程序可以设置**getActivities**和**dynamicActivitiesLookupEx**元素, 使其具有内存中的 .osc 存储活动项。 本主题介绍当 .osc 提供商支持从社交网络同步活动源时, .osc 调用以获取或刷新活动和活动所有者详细信息的 .osc 提供程序扩展性 api。 本主题还列出了**microsoft.office.server.activityfeed**元素的一些子元素, .osc 提供程序应为 .osc 设置这些子元素, 以便在 Office 联系人卡片或 Outlook 人员窗格中正确显示活动。 
  
- .osc 调用[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法来获取和存储登录用户的 "新闻源" 文件夹中的活动。 .osc 提供程序必须实现**GetActivitiesEx** , 以返回符合**microsoft.office.server.activityfeed**元素的 .osc 提供程序 XML 架构定义的_活动_XML 字符串。 
    
- .osc 提供程序必须设置**ownerID**元素, 该元素是**activityDetails**元素的子元素。 **ownerID**是一个不透明的字符串, 用于标识社交网络上活动的所有者。 
    
- .osc 提供程序应在**templateVariables**元素的**publisherVariable**节点中设置**nameHint**和**emailAddress**元素。 
    
   请注意, 根据 .osc 提供程序 XML 架构, **nameHint**元素是可选元素。 .osc 使用它来匹配 "联系人卡片" 或 "人员" 窗格中所选用户的显示名称。 同样, **emailAddress**元素是 XML 架构中的可选元素。 .osc 使用它来匹配在联系人卡片或人员窗格中选择的用户的 SMTP 地址。 
    
   如果只指定了**ownerID**元素, 但未指定其中一个或两个**nameHint**和**emailAddress** , 则 .osc 将调用[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md)方法, 然后调用[ISocialPerson:: GetDetails](isocialperson-getdetails.md)方法, 以获取有关由**ownerID**标识的人员的详细信息。 当 .osc 调用**ISocialPerson:: GetDetails**时, 提供程序必须返回指定**fullName**和**emailAddress**元素的**人员**XML。 
    
## <a name="see-also"></a>另请参阅

- [适用于活动的 XML](xml-for-activities.md)  
- [适用于好友的 XML](xml-for-friends.md)  
- [XML 的功能](xml-for-capabilities.md)

