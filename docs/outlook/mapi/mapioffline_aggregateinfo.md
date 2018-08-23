---
title: MAPIOFFLINE_AGGREGATEINFO
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2e502d28-ae09-49d9-a35a-5d77acdcd6f4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eb182d9cc51c196558f9e9192a65352e87372bf0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582516"
---
# <a name="mapiofflineaggregateinfo"></a>MAPIOFFLINE_AGGREGATEINFO

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
结构用于[HrCreateOfflineObj](hrcreateofflineobj.md)。 
  
```cpp
typedef struct
{
  ULONG            ulSize;
  IUnknown*          pOuterObj;
  IUnknown*          pRefTrackRoot;
} MAPIOFFLINE_AGGREGATEINFO;
```

## <a name="members"></a>Members

 **ulSize**
  
> 结构的大小。
    
 **pOuterObj**
  
> 指向此对象正在聚合到 IUnknown 对象的指针。 这将允许任何 QueryInterface 的调用将传递到创建的对象。
    
 **pRefTrackRoot**
  
> 必须为 NULL。
    
## <a name="see-also"></a>另请参阅



[HrCreateOfflineObj](hrcreateofflineobj.md)
  
[MAPIOFFLINE_CREATEINFO](mapioffline_createinfo.md)

