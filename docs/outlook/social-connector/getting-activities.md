---
title: 获取活动
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cb8f916-f061-4c4c-ad1b-40d44af3345a
description: OSC 调用 ISocialProvider：：GetCapabilities 方法以确定适用于社交网络的 OSC 提供程序的功能。
ms.openlocfilehash: 9d504fb64368a6910feaa38f0ef19ed631b4d4e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420575"
---
# <a name="getting-activities"></a>获取活动

OSC 调用 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md) 方法以确定适用于社交网络的 OSC 提供程序的功能。 如果返回的功能 **XML** 中的 **getActivities** 和 **dynamicActivitiesLookupEx** 元素指示 OSC 提供程序支持按需获取活动以及将活动存储在内存中，则 OSC 可以执行以下调用序列。 OSC 还记下功能 XML 中的 **hashFunction** 元素中指定的 **哈希函数** 。 OSC 按以下顺序调用方法， (社交网络上的好友和非好友的 [ISocialPerson](isocialpersoniunknown.md)) 支持的活动和信息： 
  
1. [ISocialSession：：GetLoggedOnUser](isocialsession-getloggedonuser.md) — 在身份验证过程结束时，OSC 调用 **GetLoggedOnUser** 以获取要进行身份验证的用户的 [ISocialProfile](isocialprofileisocialperson.md) 接口。 有关身份验证详细信息，请参阅[基本身份验证](basic-authentication.md)[和基于表单的身份验证](forms-based-authentication.md)。
    
2. [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) - 对于在 Outlook 人员窗格中显示的人员，OSC 获取其 SMTP 地址并哈希，调用 **ISocialSession2：：GetActivitiesEx，** 将 (存储在内存中) 这些人员返回的活动数据。 OSC 获取输出参数  _activities_，这是一个字符串，其中包含登录用户好友的活动集合。 此字符串符合 **activityFeed** 元素的架构定义。 
    
3. [ISocialSession：：GetPerson](isocialsession-getperson.md) - 对于 **GetActivitiesEx** 返回的 **activityFeed** XML 中的每个 **activityDetails** 元素，都有一个 **ownerID** 元素，用于指示拥有该活动的人。 OSC 使用该 **ownerID** 值调用 **GetPerson，** 获取此人的 **ISocialPerson** 接口。 
    
4. [ISocialPerson：：GetDetails](isocialperson-getdetails.md) —根据从步骤 3 获取的 **ISocialPerson** 对象，OSC 调用 **GetDetails** 以获取此人的详细信息，如名字和姓氏。 OSC 可以针对步骤 2 中 **GetActivitiesEx** 返回的 **activityFeed** XML 中的 **activityDetails** 元素中指定的每个活动执行相同的操作。 
    
> [!NOTE]
> OSC 以默认间隔刷新活动缓存。 有关刷新活动缓存的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。 
  
## <a name="see-also"></a>另请参阅

- [功能的 XML](xml-for-capabilities.md)
- [OSC 典型调用序列](osc-typical-calling-sequences.md)

