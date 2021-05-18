---
title: 有关正确显示活动的指南
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 55268188-8432-4145-9527-f5888949fc24
description: OutlookSOCIAL Connector (OSC) 提供程序可以设置 getActivities 和 dynamicActivitiesLookupEx 元素，以将 OSC 存储活动项到内存中。
ms.openlocfilehash: b2fcaa125ac8bf7924726f4f09ff507769c3a3f7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422913"
---
# <a name="guidelines-for-properly-displaying-activities"></a>有关正确显示活动的指南

OutlookSOCIAL Connector (OSC) 提供程序可以设置 **getActivities** 和 **dynamicActivitiesLookupEx** 元素，以将 OSC 存储活动项内存中。 本主题介绍 OSC 提供程序扩展性 API，如果 OSC 提供程序支持从社交网络同步活动源，则 OSC 将调用这些 API 获取或刷新活动和活动所有者详细信息。 本主题还列出了 OSC 提供程序应为 OSC 设置的 **activityFeed** 元素的一些子元素，以在 Office 联系人卡片或联系人Outlook中正确显示活动。 
  
- OSC 调用 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法来获取活动，并存储登录用户的"新闻源"文件夹中的活动。 OSC 提供程序必须实现 **GetActivitiesEx** 以返回符合 **activityFeed** 元素的 OSC 提供程序 XML 架构定义的活动 _XML_ 字符串。 
    
- OSC 提供程序必须设置 **ownerID** 元素，它是 **activityDetails 元素的子** 元素。 **ownerID** 是一个不透明字符串，用于标识社交网络上活动的所有者。 
    
- OSC 提供程序应在 **templateVariables** 元素的 **publisherVariable** 节点中设置 **nameHint** 和 **emailAddress** 元素。 
    
   请注意，根据 OSC 提供程序 XML 架构 **，nameHint** 元素是可选元素。 OSC 使用它来匹配显示名称卡片或人员窗格中选择的用户的联系人。 同样 **，emailAddress** 元素是 XML 架构中的可选元素。 OSC 使用它来匹配在联系人卡片或人员窗格中选择的用户的 SMTP 地址。 
    
   如果仅指定了 **ownerID** 元素，但未指定 **nameHint** 和 **emailAddress** 的一个或两个，则 OSC 将调用 [ISocialSession2：：GetPeopleDetails](isocialsession2-getpeopledetails.md) 方法，然后调用 [ISocialPerson：：GetDetails](isocialperson-getdetails.md) 方法来获取有关 **ownerID** 标识的人详细信息。 当 OSC 调用 **ISocialPerson：：GetDetails** 时，提供程序必须返回 **指定** **fullName** 和 **emailAddress** 元素的 person XML。 
    
## <a name="see-also"></a>另请参阅

- [活动的 XML](xml-for-activities.md)  
- [好友 XML](xml-for-friends.md)  
- [功能的 XML](xml-for-capabilities.md)

