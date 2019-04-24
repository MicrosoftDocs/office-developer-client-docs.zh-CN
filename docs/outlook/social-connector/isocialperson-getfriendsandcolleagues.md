---
title: ISocialPersonGetFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62d5b815-f199-499e-85eb-2dff21a8216e
description: 获取表示人员集合的字符串。
ms.openlocfilehash: f755476f66ab2f91471b88c74baff899f31b83e3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331659"
---
# <a name="isocialpersongetfriendsandcolleagues"></a>ISocialPerson::GetFriendsAndColleagues

获取表示人员集合的字符串。
  
```cpp
HRESULT _stdcall GetFriendsAndColleagues([out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a>参数

_personsCollection_
  
> 排除一个 XML 字符串, 它表示人员的一组朋友, 并且符合 Outlook Social Connector (.osc) 提供程序可扩展性的 XML 架构中定义的**友元**定义。 
    
## <a name="remarks"></a>注解

如果 .osc 提供商支持社交网络上的友元缓存或混合同步, 则 .osc 调用**GetFriendsAndColleagues** 。 当 .osc 最初调用登录到社交网络的 Outlook 用户的**GetFriendsAndColleagues**方法时, **GetFriendsAndColleagues**将返回一个代表社交网络上登录用户的好友的 XML 字符串。 XML 字符串符合**好友**XML 架构定义, 并指定每个好友的**person**元素 (也符合 .osc 提供程序架构定义)。 
  
当**GetFriendsAndColleagues**返回已登录用户的好友信息时, .osc 会将该信息存储在 "联系人" 文件夹中。 此文件夹特定于社交网络, 并驻留在登录用户的默认 Outlook 存储中。 有关 .osc 如何将朋友的信息缓存在联系人文件夹中的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。
  
_personsCollection_参数中返回的每个友元的信息符合**人员**的 XML 架构定义。 **person**元素支持每个好友的多条信息, 包括 SMTP 电子邮件地址 (映射到好友在其上指定的**emailAddress**、 **emailAddress2**和**emailAddress3**元素)社交网络, 以及在社交网络上标识该好友的用户 ID (映射到**userID**元素)。 
  
若要显示在 "人员" 窗格中选定的 Outlook 用户的活动, .osc 将尝试使用户与从**GetFriendsAndColleagues**返回的每个朋友相匹配。 通过将所选 Outlook 用户的 SMTP 地址与每个好友在社交网络中指定的电子邮件地址相匹配, .osc 实现此目的。 如果 .osc 找到匹配的 SMTP 电子邮件地址, 则 .osc 将使用友元的相应**用户 id**调用[ISocialSession:: GetPerson](isocialsession-getperson.md)方法。 它将执行此操作以获取该好友的[ISocialPerson](isocialpersoniunknown.md)对象, 该对象随后使 .osc 能够从社交网络中获取该朋友的活动和图片。 
  
但是, 如果所选的 Outlook 用户未在社交网络上的帐户上指定相同的 SMTP 地址, 或者如果 outlook 用户在社交网络上没有帐户, 则该 .osc 将无法找到该用户的匹配项, 并且不会显示任何 activiti社交网络上该用户的 es。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)
- [获取好友信息](getting-friends-information.md)

