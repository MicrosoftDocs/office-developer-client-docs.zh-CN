---
title: 获取好友信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d8a56746-4de4-4f24-af32-e85079c060b8
description: 'Outlook Social Connector (.osc) 调用 ISocialProvider:: GetCapabilities 方法来确定用于社交网络的 .osc 提供程序的功能。'
ms.openlocfilehash: 697902631b010afab015e9cfb73fac81ac427d6e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286320"
---
# <a name="getting-friends-information"></a>获取好友信息

Outlook Social Connector (.osc) 调用[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法来确定用于社交网络的 .osc 提供程序的功能。 如果返回的**功能**XML 中的**getFriends**和**cacheFriends**元素指示 .osc 提供程序支持将好友作为 Outlook 联系人项目放在相应的 "联系人" 文件夹中, 则 .osc 可以进行以下调用序列。 .osc 调用此序列中的方法, 以获取社交网络上的好友的信息和图片 (由[ISocialPerson](isocialpersoniunknown.md)接口支持)。 
  
> [!NOTE]
> .osc 将以默认间隔刷新缓存。 如果在缓存刷新期间发生错误, 则在其他预设间隔内进行的 .osc 重试, 也可以通过在**功能**XML 中指定**contactSyncRestartInterval**元素来对其进行控制。 有关刷新联系人缓存的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。 
  
1. [ISocialSession:: LoggedOnUserID](isocialsession-loggedonuserid.md) — .osc 获取登录到社交网络的 Office 用户的用户 ID。 
    
2. [ISocialSession:: GetPerson](isocialsession-getperson.md) —使用 Office 用户的用户 ID, .osc 获取该用户的**ISocialPerson**对象。 
    
3. [ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) — .osc 获取社交网络上的用户的友元列表。 
    
4. [ISocialSession:: GetPerson](isocialsession-getperson.md) -对于**GetFriendsAndColleagues**返回的 XML 中的每个人, .osc 获取一个**ISocialPerson**接口。 
    
5. [ISocialPerson:: GetPicture](isocialperson-getpicture.md) -对于**GetFriendsAndColleagues**返回的 XML 中的每个人, .osc 获取图片资源。
    
## <a name="see-also"></a>另请参阅

- [XML 的功能](xml-for-capabilities.md)
- [.osc 典型调用序列](osc-typical-calling-sequences.md)

