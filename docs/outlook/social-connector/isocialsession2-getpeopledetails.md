---
title: ISocialSession2GetPeopleDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8733aab9-3a8e-4924-b62f-4e871d991c72
description: 返回一个字符串，包含一人和图片 personsAddresses 参数指定用户的详细信息。
ms.openlocfilehash: 756f8de3a0615420826fe725528c92351d521832
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779246"
---
# <a name="isocialsession2getpeopledetails"></a>ISocialSession2::GetPeopleDetails

返回一个字符串，包含一人和图片_personsAddresses_参数指定用户的详细信息。 
  
```cpp
HRESULT _stdcall GetPeopleDetails([in] BSTR personsAddresses, [out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a>参数

_personsAddresses_
  
> [in]指定一组用户的哈希的 SMTP 地址一个 XML 字符串。
    
_personsCollection_
  
> [输出]一个 XML 字符串，包含人和图片的详细信息的集合。
    
## <a name="remarks"></a>说明

Outlook Social Connector (OSC) 调用**GetPeopleDetails**如果 OSC 提供程序支持的朋友和非朋友点播或混合同步。 
  
OSC 提供程序扩展性的架构中定义， _personsAddresses_参数必须符合**hashedAddresses**，架构定义。 _PersonsAddresses_字符串表示为人员窗格中显示每个用户的哈希 SMTP 地址的一组。 用户不必是由[ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md)属性表示的登录用户的好帮手。 使用提供程序的**功能**XML 中指定**hashFunction**元素的哈希函数进行加密的哈希的 SMTP 地址。 OSC 标识与**索引**元素_personAddresses_集合中每个**hashedAddress** 。 提供程序必须使用**索引**元素时它返回**朋友**XML **GetPeopleDetails**标识收件人的**人员**XML。 如果收件人不是注册的用户社交网络上，提供的收件人必须不返回任何**人**XML。 由**人员**XML 每个网络用户的**索引**元素中_personsAddresses_收件人对应的**索引**元素。
  
OSC 存储在内存中_personsCollection_参数返回的信息。 OSC 提供程序扩展性的架构中定义， _personsCollection_ XML 字符串必须符合**朋友**架构定义。 有关如何 OSC 使用和更新内存中的此信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)
- [同步朋友和活动](synchronizing-friends-and-activities.md)

