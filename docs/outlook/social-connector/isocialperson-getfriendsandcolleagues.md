---
title: ISocialPersonGetFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62d5b815-f199-499e-85eb-2dff21a8216e
description: 获取一个代表人员集合的字符串。
ms.openlocfilehash: f755476f66ab2f91471b88c74baff899f31b83e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407653"
---
# <a name="isocialpersongetfriendsandcolleagues"></a>ISocialPerson::GetFriendsAndColleagues

获取一个代表人员集合的字符串。
  
```cpp
HRESULT _stdcall GetFriendsAndColleagues([out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a>参数

_personsCollection_
  
> [out]一个 XML 字符串，表示一组好友，并且符合 OUTLOOK Social Connector  (OSC 提供程序扩展的 XML 架构中定义的好友) 定义。 
    
## <a name="remarks"></a>备注

如果 OSC 提供程序支持社交网络上好友的缓存或混合同步，OSC 将调用 **GetFriendsAndColleagues。** 当 OSC 最初为登录到社交网络的 Outlook 用户调用 **GetFriendsAndColleagues** 方法时 **，GetFriendsAndColleagues** 将返回一个 XML 字符串，该字符串表示社交网络上已登录用户的好友。 XML 字符串符合 **好友** XML 架构定义，并指定 **person** 元素 (该元素还符合每个好友的 OSC 提供程序架构) 定义。 
  
当 **GetFriendsAndColleagues** 返回已登录用户的好友信息时，OSC 将该信息存储在联系人文件夹中。 此文件夹特定于社交网络，并驻留在登录用户的默认Outlook存储中。 有关 OSC 如何在联系人文件夹中缓存好友信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。
  
_personCollection_ 参数中返回的每个好友的信息都符合 person 的 XML 架构 **定义**。 **person** 元素支持每个好友的许多信息，包括映射到好友在社交网络上指定的 **emailAddress、emailAddress2** 和 **emailAddress3** 元素) 的 SMTP 电子邮件地址 (以及映射到标识社交网络上该好友的 **userID** 元素) 的用户 ID (。  
  
若要显示用户在人员Outlook选择的活动，OSC 会尝试将该用户与从 **GetFriendsAndColleagues** 返回的每个好友匹配。 OSC 通过匹配所选用户的 SMTP 地址Outlook每个好友在社交网络上指定的电子邮件地址来完成此操作。 如果 OSC 找到匹配的 SMTP 电子邮件地址，OSC 将使用好友的相应 **userID** 调用 [ISocialSession：：GetPerson](isocialsession-getperson.md) 方法。 它执行此操作以获取该好友的 [ISocialPerson](isocialpersoniunknown.md) 对象，然后 OSC 通过该对象从社交网络获取该好友的活动和图片。 
  
但是，如果所选的 Outlook 用户未在社交网络上的帐户上指定同一 SMTP 地址，或者 Outlook 用户没有该社交网络上的帐户，则 OSC 将无法找到该用户的匹配项，并且不会在社交网络上显示该用户的任何活动。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)
- [获取好友信息](getting-friends-information.md)

