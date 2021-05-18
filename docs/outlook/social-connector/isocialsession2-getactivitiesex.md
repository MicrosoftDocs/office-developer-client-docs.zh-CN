---
title: ISocialSession2GetActivitiesEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bfe30c22-017b-42e0-93be-c85d674c07e3
description: 获取一个字符串，代表 hashedAddresses 参数指定的每个用户的活动集合。
ms.openlocfilehash: be29d0226eb137b1ad8ed025acfe3f4958efa85f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404335"
---
# <a name="isocialsession2getactivitiesex"></a>ISocialSession2::GetActivitiesEx

获取一个字符串，代表  _hashedAddresses_ 参数指定的每个用户的活动集合。 
  
```cpp
HRESULT _stdcall GetActivitiesEx([in] SAFEARRAY(BSTR) hashedAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="parameters"></a>参数

_hashedAddresses_
  
> [in]为一组用户指定哈希 SMTP 地址数组的结构。
    
_startTime_
  
> [in]返回所创建活动的时间。
    
_activities_
  
> [out]一个 XML 字符串，表示自 startTime 以来社交网络上的  _hashedAddresses_ 指定的用户  _的活动集_。
    
## <a name="remarks"></a>备注

如果 OSC 提供程序支持按需同步活动，OSC 将调用 **GetActivitiesEx。** OSC 将返回的信息存储在  _内存中的活动_ 。 有关 OSC 如何在内存中使用和更新此信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。
  
从 Outlook Social Connector 2013 开始，OSC 仅支持按需同步活动，并仅调用 **GetActivitiesEx** 获取活动。 若要支持按需活动查找，将 **cacheActivities** 设置为 **false，** 将 **getActivities** 和 **dynamicActivitiesLookupEx** 设置为 **true，OSC** 将调用 **GetActivitiesEx**。
  
返回的 XML 字符串必须符合 **activityFeed** 的架构定义，如 OSC 提供程序扩展性架构中的定义。
  
_hashedAddresses_ sring 表示显示在人员窗格中的每个用户的一组哈希地址。 哈希 SMTP 地址使用提供程序的功能 XML 中 **hashFunction** 元素指定的哈希函数 **进行** 加密。 用户无需是 [ISocialSession：：LoggedOnUserName](isocialsession-loggedonusername.md) 属性所代表的已登录用户的好友。 
  
_startTime_ 参数是协调世界时与 UTC 时间 (Date) 。 本地时间值必须转换为 UTC **日期** 值。 
  
**GetActivitiesEx** 方法返回的活动必须具有大于 _startTime_ 且小于或等于 Now 的创建时间 **值**。 如果在 **startTime** 和 **Now** 之间未发生更改，则提供程序必须返回OSC_E_NO_CHANGES错误。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)
- [同步好友和活动](synchronizing-friends-and-activities.md)

