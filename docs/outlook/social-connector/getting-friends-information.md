---
title: 获取好友信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d8a56746-4de4-4f24-af32-e85079c060b8
description: Outlook Social Connector (OSC) 调用 ISocialProvider::GetCapabilities 方法来确定社交网络 OSC 提供程序的功能。
ms.openlocfilehash: 68443992351f4c83e8e560a753941e97bf91de67
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779198"
---
# <a name="getting-friends-information"></a>获取好友信息

Outlook Social Connector (OSC) 调用[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法来确定社交网络 OSC 提供程序的功能。 如果返回**功能**XML 中的**getFriends**和**cacheFriends**元素指示 OSC 提供程序支持入门朋友和缓存朋友作为 Outlook 联系人项目对应的联系人文件夹中，可以使 OSC下面的调用序列。 OSC 按此顺序获得信息和图片 （如[ISocialPerson](isocialpersoniunknown.md)接口支持） 的社交网络上的朋友调用方法。 
  
> [!NOTE]
> OSC 刷新按默认的时间间隔的缓存。 如果缓存期间发生错误刷新，在另一个预设的间隔，也可以通过在**功能**XML 中指定的**contactSyncRestartInterval**元素控制 OSC 重试。 有关刷新联系人缓存的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。 
  
1. [ISocialSession::LoggedOnUserID](isocialsession-loggedonuserid.md) — OSC 获取 Office 用户登录到社交网络的用户 ID。 
    
2. [ISocialSession::GetPerson](isocialsession-getperson.md) — 使用 Office 用户的用户 ID，OSC 该用户的中获取**ISocialPerson**对象。 
    
3. [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) — OSC 社交网络上获取用户的好朋友列表。 
    
4. [ISocialSession::GetPerson](isocialsession-getperson.md) — OSC 的 XML 中的每个人，则由**GetFriendsAndColleagues**返回，获取**ISocialPerson**接口。 
    
5. [ISocialPerson::GetPicture](isocialperson-getpicture.md) — OSC 的 XML 中的每个人，则由**GetFriendsAndColleagues**返回，获取图片的资源。
    
## <a name="see-also"></a>另请参阅

- [功能 XML](xml-for-capabilities.md)
- [OSC 典型调用序列 （英文)](osc-typical-calling-sequences.md)

