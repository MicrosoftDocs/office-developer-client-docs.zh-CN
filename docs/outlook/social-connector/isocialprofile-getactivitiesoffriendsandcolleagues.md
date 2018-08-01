---
title: ISocialProfileGetActivitiesOfFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4aaf7417-0a03-42a4-a282-599327ec5381
description: Outlook Social Connector 2013 中已弃用此方法。
ms.openlocfilehash: 54b5cd6d681aa1e8008eade024ef57783bf18ead
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779247"
---
# <a name="isocialprofilegetactivitiesoffriendsandcolleagues"></a>ISocialProfile::GetActivitiesOfFriendsAndColleagues

Outlook Social Connector 2013 中已弃用此方法。
  
```cpp
HRESULT _stdcall GetActivitiesOfFriendsAndColleagues([in] DATE startTime, [out, retval] BSTR* activitiesCollection);
```

## <a name="remarks"></a>说明

Outlook Social Connector 2013、 OSC 支持仅按需活动同步和不在缓存或活动同步混合中启动。 OSC 忽略的功能 XML 中的**cacheActivities**设置，无法再调用此方法。 若要支持动态活动查找，实现[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**，这将提示呼叫**ISocialSession2::GetActivitiesEx**改为 OSC。 
  
有关如何 OSC 获取朋友的活动的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProfile : ISocialPerson](isocialprofileisocialperson.md)

