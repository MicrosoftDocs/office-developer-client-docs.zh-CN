---
title: ISocialSession2GetPeopleDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8733aab9-3a8e-4924-b62f-4e871d991c72
description: 返回一个字符串，其中包含 personAddresses 参数指定的用户的人员和图片详细信息的集合。
ms.openlocfilehash: 08b6eca193da59bbdc3c9d21d4dc9b6d0e0c884f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404531"
---
# <a name="isocialsession2getpeopledetails"></a>ISocialSession2::GetPeopleDetails

返回一个字符串，其中包含  _personAddresses_ 参数指定的用户的人员和图片详细信息的集合。 
  
```cpp
HRESULT _stdcall GetPeopleDetails([in] BSTR personsAddresses, [out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a>参数

_personsAddresses_
  
> [in]一个 XML 字符串，用于指定一组用户的哈希 SMTP 地址。
    
_personsCollection_
  
> [out]包含人员集合和图片详细信息的 XML 字符串。
    
## <a name="remarks"></a>备注

如果 OSC (支持) 好友和非好友的按需同步或混合同步，则 OsC 中的 Outlook Social Connector 将调用 **GetPeopleDetails。** 
  
_the personsAddresses_ parameter must conform to the schema definition for **hashedAddresses**， as defined in the schema for OSC provider extensibility. _peopleAddresses_ 字符串表示显示在人员窗格中的每个用户的一组哈希 SMTP 地址。 用户无需是 [ISocialSession：：LoggedOnUserName](isocialsession-loggedonusername.md) 属性所代表的已登录用户的好友。 哈希 SMTP 地址使用提供程序的功能 XML 中 **hashFunction** 元素指定的哈希函数 **进行** 加密。 OSC 使用索引元素标识 _personAddresses_ 集合中的每个 **hashedAddress。**  当提供程序返回 **GetPeopleDetails** 的好友 **XML** 时，提供程序必须使用 **index** 元素标识收件人的人 XML。 如果收件人不是社交网络上的注册用户，则提供程序不得 **返回该收件人** 的任何人 XML。 person  **XML** 表示的每个网络用户的 index 元素对应于 _personAddresses_ 中收件人的索引元素。 
  
OSC 将  _由 personsCollection_ 参数返回的信息存储在内存中。 _the personsCollection_ XML string must conform to the schema definition for **friends**， as defined in the schema for OSC provider extensibility. 有关 OSC 如何在内存中使用和更新此信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)
- [同步好友和活动](synchronizing-friends-and-activities.md)

