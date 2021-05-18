---
title: ISocialProfileGetActivitiesOfFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4aaf7417-0a03-42a4-a282-599327ec5381
description: Social Connector 2013 中Outlook弃用此方法。
ms.openlocfilehash: c02cf0e8a6d2da3f9fb7704c92e10e0409042393
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406890"
---
# <a name="isocialprofilegetactivitiesoffriendsandcolleagues"></a>ISocialProfile::GetActivitiesOfFriendsAndColleagues

Social Connector 2013 中Outlook弃用此方法。
  
```cpp
HRESULT _stdcall GetActivitiesOfFriendsAndColleagues([in] DATE startTime, [out, retval] BSTR* activitiesCollection);
```

## <a name="remarks"></a>备注

从 Outlook Social Connector 2013 开始，OSC 仅支持按需同步活动，而不允许缓存或混合同步活动。 OSC 将忽略功能 XML **中的 cacheActivities** 设置，并且不再调用此方法。 若要支持动态活动查找，请实现 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法。 将 **getActivities** 和 **dynamicActivitiesLookupEx** 设置为 **true**，这将提示 OSC 改为调用 **ISocialSession2：：GetActivitiesEx。** 
  
有关 OSC 如何获取好友活动的信息，请参阅同步好友 [和活动](synchronizing-friends-and-activities.md)。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProfile : ISocialPerson](isocialprofileisocialperson.md)

