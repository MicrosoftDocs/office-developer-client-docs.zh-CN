---
title: ISocialProfileGetActivitiesOfFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4aaf7417-0a03-42a4-a282-599327ec5381
description: 此方法在 Outlook Social Connector 2013 中已被弃用。
ms.openlocfilehash: c02cf0e8a6d2da3f9fb7704c92e10e0409042393
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406890"
---
# <a name="isocialprofilegetactivitiesoffriendsandcolleagues"></a>ISocialProfile::GetActivitiesOfFriendsAndColleagues

此方法在 Outlook Social Connector 2013 中已被弃用。
  
```cpp
HRESULT _stdcall GetActivitiesOfFriendsAndColleagues([in] DATE startTime, [out, retval] BSTR* activitiesCollection);
```

## <a name="remarks"></a>说明

从 Outlook Social Connector 2013 开始, .osc 仅支持对活动进行按需同步, 而不支持对活动进行缓存或混合同步。 .osc 忽略功能 XML 中的**cacheActivities**设置, 并且不再调用此方法。 若要支持动态活动查找, 请实现[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**, 这将提示 .osc 调用**ISocialSession2:: GetActivitiesEx** 。 
  
有关 .osc 如何获取好友活动的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProfile : ISocialPerson](isocialprofileisocialperson.md)

