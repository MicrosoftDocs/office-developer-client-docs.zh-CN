---
title: SAppTimeArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SAppTimeArray
api_type:
- COM
ms.assetid: 5a1ff95a-9862-4165-8a70-bd2eeb7fe683
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 834a7141f0e7150140fa27c21d88db422d6f5561
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778663"
---
# <a name="sapptimearray"></a>SAppTimeArray

  
  
**适用于**： Outlook 
  
包含数组的时间值。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SAppTimeArray
{
  ULONG cValues;
  double FAR *lpat;
} SAppTimeArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpat**成员指向数组中的值的数目。 
    
 **lpat**
  
> 指向的应用程序时间值的数组。 
    
## <a name="remarks"></a>说明

**SAppTimeArray**结构用于定义 PT_MV_APPTIME 类型的属性。 有关 PT_MV_APPTIME 的详细信息，请参阅[列表的属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

