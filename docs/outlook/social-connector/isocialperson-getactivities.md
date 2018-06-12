---
title: ISocialPersonGetActivities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cf727140-f6e7-4718-bd74-1f8feeccf70c
description: Outlook Social Connector 2013 中已弃用此方法。
ms.openlocfilehash: af952b6d57325e1b52093fcf655e6fdc271ca34f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779209"
---
# <a name="isocialpersongetactivities"></a>ISocialPerson::GetActivities

Outlook Social Connector 2013 中已弃用此方法。
  
```cpp
HRESULT _stdcall GetActivities([in] DATE startTime, [out, retval] BSTR* activities);
```

## <a name="remarks"></a>备注

Outlook Social Connector 2013、 OSC 支持仅按需活动同步和不在缓存或活动同步混合中启动。 OSC 将忽略的功能 XML 中**cacheActivities**设置，并且不调用此方法。 若要支持动态活动查找，实现[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 设置为**false**、 **getActivities**和**dynamicActivitiesLookupEx**为**true**，这将会进行提示 OSC 改为呼叫**ISocialSession2::GetActivitiesEx** **cacheActivities** 。 
  
有关如何 OSC 获取朋友的活动的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。 
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson: IUnknown](isocialpersoniunknown.md)

