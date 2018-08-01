---
title: ISocialPersonGetFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62d5b815-f199-499e-85eb-2dff21a8216e
description: 获取一个字符串，表示的人员的集合。
ms.openlocfilehash: 36482a6068c592eb0ff07603b6458e8415c3586f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779217"
---
# <a name="isocialpersongetfriendsandcolleagues"></a>ISocialPerson::GetFriendsAndColleagues

获取一个字符串，表示的人员的集合。
  
```cpp
HRESULT _stdcall GetFriendsAndColleagues([out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a>参数

_personsCollection_
  
> [输出]表示一的人员，朋友和的符合**朋友**的定义中的 Outlook Social Connector (OSC) 提供程序扩展性的 XML 架构定义一个 XML 字符串。 
    
## <a name="remarks"></a>说明

OSC 社交网络上调用**GetFriendsAndColleagues**如果 OSC 提供程序支持缓存或朋友混合同步。 当 OSC 最初**GetFriendsAndColleagues**为调用方法的 Outlook 用户的登录到社交网络， **GetFriendsAndColleagues**返回 XML 字符串值，该值代表登录用户的社交网络的朋友。 XML 字符串符合**朋友**XML 架构定义，并为每个朋友指定**人员**元素 （其还符合 OSC 提供程序架构定义）。 
  
**GetFriendsAndColleagues**返回朋友登录用户的信息，OSC 将该信息存储在联系人文件夹中。 此文件夹特定于社交网络和驻留在登录用户的默认 Outlook 存储区。 有关如何 OSC 缓存联系人文件夹中的朋友的信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。
  
返回_personsCollection_参数中每个朋友信息符合**人**的 XML 架构定义。 **Person**元素支持每个朋友，包括的 SMTP 电子邮件地址 （其映射到的**电子邮件地址**、 **emailAddress2**和**emailAddress3**元素） 的信息的许多部分朋友具有在指定社交网络和用户 ID （其映射到**userID**元素），标识社交网络上的好帮手。 
  
若要显示在人员窗格中选择的 Outlook 用户的活动，OSC 尝试与从**GetFriendsAndColleagues**返回每个朋友相匹配用户。 OSC 匹配所选的 Outlook 用户的 SMTP 地址，每个朋友具有指定社交网络的电子邮件地址来达到此目的。 如果 OSC 找到匹配的 SMTP 电子邮件地址，OSC 使用朋友相应**userID**调用[ISocialSession::GetPerson](isocialsession-getperson.md)方法。 它这样做是为了获取该朋友，然后使 OSC 以获得社交网络活动和该朋友的图片[ISocialPerson](isocialpersoniunknown.md)对象。 
  
但是，如果所选的 Outlook 用户没有帐户的社交网络上指定的相同的 SMTP 地址或 Outlook 用户不具有该社交网络上的帐户，则 OSC 将不能以查找该用户的匹配并且不会显示任何 activities 社交网络上的用户。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)
- [获取好友信息](getting-friends-information.md)

