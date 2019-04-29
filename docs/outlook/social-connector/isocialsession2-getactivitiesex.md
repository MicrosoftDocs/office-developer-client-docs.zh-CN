---
title: ISocialSession2GetActivitiesEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bfe30c22-017b-42e0-93be-c85d674c07e3
description: 获取一个字符串, 表示由 hashedAddresses 参数指定的每个用户的活动的集合。
ms.openlocfilehash: be29d0226eb137b1ad8ed025acfe3f4958efa85f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404335"
---
# <a name="isocialsession2getactivitiesex"></a>ISocialSession2::GetActivitiesEx

获取一个字符串, 表示由_hashedAddresses_参数指定的每个用户的活动的集合。 
  
```cpp
HRESULT _stdcall GetActivitiesEx([in] SAFEARRAY(BSTR) hashedAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="parameters"></a>参数

_hashedAddresses_
  
> 实时指定一组用户的哈希 SMTP 地址数组的结构。
    
_startTime_
  
> 实时在其后将返回创建的活动的时间。
    
_activities_
  
> 排除一个 XML 字符串, 表示自_startTime_以来由社交网络上的_hashedAddresses_指定的用户的一组活动。
    
## <a name="remarks"></a>说明

如果 .osc 提供程序支持按需同步的活动, 则 .osc 会调用**GetActivitiesEx** 。 .osc 将返回的信息存储在内存中的_活动_中。 有关 .osc 如何在内存中使用和更新此信息的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。
  
从 Outlook Social Connector 2013 开始, .osc 仅支持活动的按需同步, 并且仅调用**GetActivitiesEx**获取活动。 若要支持按需活动查找, 请将**cacheActivities**设置为**false**, 将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**, 并且 .osc 将调用**GetActivitiesEx**。
  
返回的 XML 字符串必须符合**microsoft.office.server.activityfeed**的架构定义, 如在您的 .osc 提供程序扩展性架构中定义的那样。
  
_hashedAddresses_ sring 表示在人员窗格中显示的每个用户的一组散列地址。 哈希 SMTP 地址通过使用提供程序的**功能**XML 中的**hashFunction**元素指定的哈希函数进行加密。 用户不必是[ISocialSession:: LoggedOnUserName](isocialsession-loggedonusername.md)属性所表示的已登录用户的友元。 
  
_startTime_参数是以协调通用时间 (UTC) 表示的**日期**值。 必须将本地时间值转换为 UTC**日期**值。 
  
**GetActivitiesEx**方法返回的活动必须具有大于_startTime_且小于或等于**当前**值的创建时间值。 如果在**startTime**和**Now**之间未发生更改, 则提供程序必须返回 OSC_E_NO_CHANGES 错误。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)
- [同步好友和活动](synchronizing-friends-and-activities.md)

