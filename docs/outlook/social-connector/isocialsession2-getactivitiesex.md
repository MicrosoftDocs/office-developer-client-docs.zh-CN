---
title: ISocialSession2GetActivitiesEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bfe30c22-017b-42e0-93be-c85d674c07e3
description: 获取一个字符串，表示活动的每个 hashedAddresses 参数指定用户的集合。
ms.openlocfilehash: 7c24494d924b63f5e137f8e9928257967469f19c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779244"
---
# <a name="isocialsession2getactivitiesex"></a>ISocialSession2::GetActivitiesEx

获取一个字符串，表示活动的每个_hashedAddresses_参数指定用户的集合。 
  
```cpp
HRESULT _stdcall GetActivitiesEx([in] SAFEARRAY(BSTR) hashedAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="parameters"></a>参数

_hashedAddresses_
  
> [in]结构，它指定一个数组哈希 SMTP 地址的一组用户。
    
_startTime_
  
> [in]之后将返回活动创建的时间。
    
_活动_
  
> [输出]代表一组指定_startTime_以来_hashedAddresses_社交网络上的用户的活动的 XML 字符串。
    
## <a name="remarks"></a>备注

OSC 调用**GetActivitiesEx**如果 OSC 提供程序支持的活动的按需同步。 OSC 存储在内存中的_活动_中返回的信息。 有关如何 OSC 使用和更新内存中的此信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。
  
Outlook Social Connector 2013 中启动 OSC 支持仅按需活动同步，并调用仅**GetActivitiesEx**获取活动。 若要支持按需活动查找，将**cacheActivities**设置为**false**，和**getActivities**和为**true**， **dynamicActivitiesLookupEx**和 OSC 将调用**GetActivitiesEx**。
  
OSC 提供程序扩展性的架构中定义，则返回的 XML 字符串必须符合**activityFeed**，架构定义。
  
_HashedAddresses_字符串实例表示一组的人员窗格中显示每个用户的哈希地址。 使用提供程序的**功能**XML 中指定**hashFunction**元素的哈希函数进行加密的哈希的 SMTP 地址。 用户不必是由[ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md)属性表示的登录用户的好帮手。 
  
_StartTime_参数都是**日期**值以协调世界时 (UTC)。 必须是本地时间值转换为 UTC**日期**值。 
  
活动**GetActivitiesEx**方法返回的值必须为创建时间大于_startTime_且小于或等于**现在**。 如果之间**开始时间**和**立即**不发生了任何更改，提供程序必须返回 OSC_E_NO_CHANGES 错误。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2: IUnknown](isocialsession2iunknown.md)
- [同步朋友和活动](synchronizing-friends-and-activities.md)

