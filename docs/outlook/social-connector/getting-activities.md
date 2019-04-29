---
title: 获取活动
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cb8f916-f061-4c4c-ad1b-40d44af3345a
description: '.osc 调用 ISocialProvider:: GetCapabilities 方法来确定用于社交网络的 .osc 提供程序的功能。'
ms.openlocfilehash: 9d504fb64368a6910feaa38f0ef19ed631b4d4e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420575"
---
# <a name="getting-activities"></a>获取活动

.osc 调用[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法来确定用于社交网络的 .osc 提供程序的功能。 如果返回的**功能**XML 中的**getActivities**和**dynamicActivitiesLookupEx**元素指示 .osc 提供程序支持按需获取活动并将活动存储在内存中, 则该 .osc 可以进行以下调用顺序。 该 .osc 还记录了**功能**XML 的**hashFunction**元素中指定的哈希函数。 .osc 调用以下序列中的方法, 以获取好友和社交网络中的非好友的活动和信息 (由[ISocialPerson](isocialpersoniunknown.md)接口支持): 
  
1. [ISocialSession:: GetLoggedOnUser](isocialsession-getloggedonuser.md) -在身份验证过程结束时, .osc 调用**GetLoggedOnUser**获取正在进行身份验证的用户的[ISocialProfile](isocialprofileisocialperson.md)接口。 有关身份验证的详细信息, 请参阅[基本身份验证](basic-authentication.md)和[基于表单的身份验证](forms-based-authentication.md)。
    
2. [ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md) -对于显示在 "Outlook 人员" 窗格中的人员, .osc 获取并散列其 SMTP 地址, 调用**ISocialSession2:: GetActivitiesEx**, 并在内存中存储为其返回的活动数据这些人员。 .osc 获取一个输出参数 ( _activity_), 它是一个字符串, 其中包含登录用户的好友活动的集合。 此字符串符合**microsoft.office.server.activityfeed**元素的架构定义。 
    
3. [ISocialSession:: GetPerson](isocialsession-getperson.md) -对于**GetActivitiesEx**返回的**microsoft.office.server.activityfeed** XML 中的每个**activityDetails**元素, 都有一个**ownerID**元素, 该元素指示拥有该活动的人员。 .osc 使用该**ownerID**值来调用**GetPerson** , 以获取该人员的**ISocialPerson**接口。 
    
4. [ISocialPerson:: GetDetails](isocialperson-getdetails.md) -基于从步骤3获取的**ISocialPerson**对象, .osc 调用**GetDetails**以获取该人员的详细信息, 例如名字和姓氏。 对于在步骤2中**GetActivitiesEx**返回的**microsoft.office.server.activityfeed** XML 中的**activityDetails**元素中指定的每个活动, .osc 可执行相同的操作。 
    
> [!NOTE]
> .osc 将按默认间隔刷新活动缓存。 有关刷新活动缓存的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。 
  
## <a name="see-also"></a>另请参阅

- [XML 的功能](xml-for-capabilities.md)
- [.osc 典型调用序列](osc-typical-calling-sequences.md)

