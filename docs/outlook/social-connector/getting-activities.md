---
title: 获取活动
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cb8f916-f061-4c4c-ad1b-40d44af3345a
description: OSC 调用 ISocialProvider::GetCapabilities 方法来确定社交网络 OSC 提供程序的功能。
ms.openlocfilehash: 82bb5322118fa3ebd7610f56b8f34ae95b59a40f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779201"
---
# <a name="getting-activities"></a>获取活动

OSC 调用[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法来确定社交网络 OSC 提供程序的功能。 如果返回**功能**XML 中的**getActivities**和**dynamicActivitiesLookupEx**元素指示 OSC 提供程序需求和存储在内存中的活动支持入门活动、 OSC 可以进行下列调用序列。 OSC 还备注**hashFunction**元素中指定的**功能**XML 中的哈希函数。 OSC 调用方法以获取活动和信息 （如[ISocialPerson](isocialpersoniunknown.md)接口支持） 朋友和社交网络上的非朋友按以下顺序： 
  
1. [ISocialSession::GetLoggedOnUser](isocialsession-getloggedonuser.md) — 在身份验证过程的末尾，OSC 调用**GetLoggedOnUser**获取[ISocialProfile](isocialprofileisocialperson.md)接口未经过身份验证的用户。 身份验证的详细信息，请参阅[基本身份验证](basic-authentication.md)和[基于表单的身份验证](forms-based-authentication.md)。
    
2. [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) — 为 Outlook 人员窗格中显示的人员，OSC 获取和返回哈希其 SMTP 地址，调用**ISocialSession2::GetActivitiesEx**，并将活动数据存储 （内存中）这些人员。 OSC 获取中输出参数，_活动_，它是一个字符串，包含朋友登录用户的活动的集合。 此字符串符合**activityFeed**元素的架构定义。 
    
3. [ISocialSession::GetPerson](isocialsession-getperson.md) — **activityFeed** **GetActivitiesEx**返回 XML 中的每个**activityDetails**元素，没有**ownerID**元素指示拥有该活动的人员。 OSC 使用该值**ownerID**来调用**GetPerson**以获取该用户**ISocialPerson**接口。 
    
4. [ISocialPerson::GetDetails](isocialperson-getdetails.md) — 基于**ISocialPerson**对象获取从步骤 3，OSC 调用**GetDetails**以获取该用户，例如名字和姓氏详细信息。 OSC 可执行相同的**activityDetails**元素**activityFeed** **GetActivitiesEx**在步骤 2 中返回的 XML 中指定每个活动。 
    
> [!NOTE]
> OSC 刷新按默认的时间间隔的活动缓存。 有关刷新活动缓存的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。 
  
## <a name="see-also"></a>另请参阅

- [功能 XML](xml-for-capabilities.md)
- [OSC 典型调用序列 （英文)](osc-typical-calling-sequences.md)

