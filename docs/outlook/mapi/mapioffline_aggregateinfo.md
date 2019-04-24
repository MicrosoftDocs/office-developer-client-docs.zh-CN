---
title: MAPIOFFLINE_AGGREGATEINFO
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2e502d28-ae09-49d9-a35a-5d77acdcd6f4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4775de0707eb90549f07525e3aa54ec5842f6050
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357132"
---
# <a name="mapiofflineaggregateinfo"></a>MAPIOFFLINE_AGGREGATEINFO

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
结构与[HrCreateOfflineObj](hrcreateofflineobj.md)一起使用。 
  
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
  
> 指向要在其上聚合此对象的 IUnknown 对象的指针。 这将允许任何 QueryInterface 调用传递到已创建的对象。
    
 **pRefTrackRoot**
  
> 必须为 NULL。
    
## <a name="see-also"></a>另请参阅



[HrCreateOfflineObj](hrcreateofflineobj.md)
  
[MAPIOFFLINE_CREATEINFO](mapioffline_createinfo.md)

