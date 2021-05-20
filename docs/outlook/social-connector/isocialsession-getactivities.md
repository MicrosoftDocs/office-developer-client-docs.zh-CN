---
title: ISocialSessionGetActivities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6546be99-aee4-41a6-8297-ace378776503
description: OSC 1.1 中已弃用此方法。
ms.openlocfilehash: 29a7cdc9895dcfa2bd926d95dbd2089b7a5dc778
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439294"
---
# <a name="isocialsessiongetactivities"></a>ISocialSession::GetActivities

OSC 1.1 中已弃用此方法。
  
```cpp
HRESULT GetActivities([in] SAFEARRAY(BSTR) emailAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="remarks"></a>备注

从 OSC 1.1 开始，OSC 不再调用 **GetActivities**。 OSC 将忽略 **dynamicActivitiesLookup 的值**。 若要支持动态活动查找，请实现 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法。 将 **cacheActivities** 设置为 **false，** 将 **getActivities** 和 **dynamicActivitiesLookupEx** 设置为 **true**，这将提示 OSC 改为调用 **ISocialSession2：：GetActivitiesEx。** 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

