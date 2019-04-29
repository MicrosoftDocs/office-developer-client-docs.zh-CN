---
title: ISocialSession2GetPeopleDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8733aab9-3a8e-4924-b62f-4e871d991c72
description: 返回一个字符串, 其中包含 personsAddresses 参数所指定用户的人员和图片详细信息的集合。
ms.openlocfilehash: 08b6eca193da59bbdc3c9d21d4dc9b6d0e0c884f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404531"
---
# <a name="isocialsession2getpeopledetails"></a>ISocialSession2::GetPeopleDetails

返回一个字符串, 其中包含_personsAddresses_参数所指定用户的人员和图片详细信息的集合。 
  
```cpp
HRESULT _stdcall GetPeopleDetails([in] BSTR personsAddresses, [out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a>参数

_personsAddresses_
  
> 实时一个 XML 字符串, 指定一组用户的哈希 SMTP 地址。
    
_personsCollection_
  
> 排除包含人员集合和图片详细信息的 XML 字符串。
    
## <a name="remarks"></a>说明

如果 .osc 提供商支持朋友和非好友的按需或混合同步, Outlook Social Connector (.osc) 将呼叫**GetPeopleDetails** 。 
  
_personsAddresses_参数必须符合用于 .osc 提供程序可扩展性架构中定义的**hashedAddresses**的架构定义。 _personsAddresses_字符串代表 "人员" 窗格中显示的每个用户的一组哈希 SMTP 地址。 用户不必是[ISocialSession:: LoggedOnUserName](isocialsession-loggedonusername.md)属性所表示的已登录用户的友元。 哈希 SMTP 地址通过使用提供程序的**功能**XML 中的**hashFunction**元素指定的哈希函数进行加密。 .osc 使用**index**元素标识_personAddresses_集合中的每个**hashedAddress** 。 提供程序在返回**GetPeopleDetails**的**好友**xml 时, 必须使用**** **index**元素来标识收件人的 xml。 如果收件人不是社交网络中已注册的用户, 则提供程序不得为该收件人返回任何**人员**XML。 **人员**XML 表示的每个网络用户的**index**元素对应于_personsAddresses_中的收件人的**index**元素。
  
.osc 将_personsCollection_参数返回的信息存储在内存中。 _personsCollection_ XML 字符串必须符合针对在 .osc 提供程序扩展性架构中定义的**友元**的架构定义。 有关 .osc 如何在内存中使用和更新此信息的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)
- [同步好友和活动](synchronizing-friends-and-activities.md)

