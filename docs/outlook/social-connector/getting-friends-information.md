---
title: 获取好友信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d8a56746-4de4-4f24-af32-e85079c060b8
description: osC Outlook Social Connector (OSC) 调用 ISocialProvider：：GetCapabilities 方法来确定 OSC 提供程序用于社交网络的功能。
ms.openlocfilehash: 697902631b010afab015e9cfb73fac81ac427d6e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428793"
---
# <a name="getting-friends-information"></a>获取好友信息

OUTLOOK Social Connector (OSC) 调用[ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法来确定 OSC 提供程序用于社交网络的功能。 如果返回的功能 **XML** 中的 **getFriends** 和 **cacheFriends** 元素指示 OSC 提供程序支持将好友作为 Outlook 联系人项目获取并缓存为对应的联系人文件夹中的联系人项目，则 OSC 可以执行以下调用序列。 OSC 调用此序列中的方法， ([ISocialPerson](isocialpersoniunknown.md) 接口支持的信息和图片，) 社交网络上的好友。 
  
> [!NOTE]
> OSC 以默认间隔刷新缓存。 如果在缓存刷新期间发生错误，OSC 将重新尝试另一个预设间隔，这可以通过在功能 **XML** 中指定 **contactSyncRestartInterval** 元素进行控制。 有关刷新联系人缓存的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。 
  
1. [ISocialSession：：LoggedOnUserID](isocialsession-loggedonuserid.md) — OSC 获取登录到社交网络的 Office 用户的用户 ID。 
    
2. [ISocialSession：：GetPerson](isocialsession-getperson.md) — OSC 使用 Office 用户的用户 ID 获取该用户的 **ISocialPerson** 对象。 
    
3. [ISocialPerson：：GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) — OSC 获取社交网络上的用户好友列表。 
    
4. [ISocialSession：：GetPerson](isocialsession-getperson.md) — 对于 **GetFriendsAndColleagues** 返回的 XML 中的每个人，OSC 获取 **ISocialPerson** 接口。 
    
5. [ISocialPerson：：GetPicture](isocialperson-getpicture.md) - 对于 **GetFriendsAndColleagues** 返回的 XML 中的每个人，OSC 获取图片资源。
    
## <a name="see-also"></a>另请参阅

- [功能的 XML](xml-for-capabilities.md)
- [OSC 典型调用序列](osc-typical-calling-sequences.md)

