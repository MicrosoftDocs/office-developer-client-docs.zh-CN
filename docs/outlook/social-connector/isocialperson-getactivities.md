---
title: ISocialPersonGetActivities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cf727140-f6e7-4718-bd74-1f8feeccf70c
description: 此方法在 Outlook Social Connector 2013 中已被弃用。
ms.openlocfilehash: abad4fc2a3e3aaea8a7097ac7e6f56b0aadae299
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437740"
---
# <a name="isocialpersongetactivities"></a>ISocialPerson::GetActivities

此方法在 Outlook Social Connector 2013 中已被弃用。
  
```cpp
HRESULT _stdcall GetActivities([in] DATE startTime, [out, retval] BSTR* activities);
```

## <a name="remarks"></a>说明

从 Outlook Social Connector 2013 开始, .osc 仅支持对活动进行按需同步, 而不支持对活动进行缓存或混合同步。 .osc 忽略功能 XML 中的**cacheActivities**设置, 不会调用此方法。 若要支持动态活动查找, 请实现[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 将**cacheActivities**设置为**false**、 **getActivities**和**dynamicActivitiesLookupEx**为**true**, 这将提示 .osc 调用**ISocialSession2:: GetActivitiesEx** 。 
  
有关 .osc 如何获取好友活动的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。 
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)

