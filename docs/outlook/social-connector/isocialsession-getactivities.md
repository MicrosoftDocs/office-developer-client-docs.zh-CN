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
ms.openlocfilehash: dc5fe25e4c4f83717309d407963d0046aa6063ec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779230"
---
# <a name="isocialsessiongetactivities"></a>ISocialSession::GetActivities

OSC 1.1 中已弃用此方法。
  
```cpp
HRESULT GetActivities([in] SAFEARRAY(BSTR) emailAddresses, [in] DATE startTime, [out, retval] BSTR *activities);
```

## <a name="remarks"></a>说明

OSC 1.1 中启动 OSC 不再调用**GetActivities**。 OSC 忽略**dynamicActivitiesLookup**的值。 若要支持动态活动查找，实现[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 设置为**false**，和**getActivities**和为**true**，这将会进行提示 OSC 改为呼叫**ISocialSession2::GetActivitiesEx** **dynamicActivitiesLookupEx** **cacheActivities** 。 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

