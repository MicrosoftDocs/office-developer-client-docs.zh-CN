---
title: ISocialSessionGetActivities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6546be99-aee4-41a6-8297-ace378776503
description: 在 .osc 1.1 中已弃用此方法。
ms.openlocfilehash: 29a7cdc9895dcfa2bd926d95dbd2089b7a5dc778
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285453"
---
# <a name="isocialsessiongetactivities"></a>ISocialSession::GetActivities

在 .osc 1.1 中已弃用此方法。
  
```cpp
HRESULT GetActivities([in] SAFEARRAY(BSTR) emailAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="remarks"></a>注解

从 .osc 1.1 开始, .osc 将不再调用**GetActivities**。 .osc 忽略**dynamicActivitiesLookup**的值。 若要支持动态活动查找, 请实现[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 将**cacheActivities**设置为**false**, 并将**getActivities**和**dynamicActivitiesLookupEx**设置为**true**, 这将提示 .osc 调用**ISocialSession2:: GetActivitiesEx**而不是。 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

