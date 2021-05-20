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
ms.openlocfilehash: dee1de19ed61fa4f8edab69152315d77545b01b2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430383"
---
# <a name="sapptimearray"></a>SAppTimeArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含时间值的数组。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SAppTimeArray
{
  ULONG cValues;
  double FAR *lpat;
} SAppTimeArray;

```

## <a name="members"></a>Members

 **cValues**
  
> lpat 成员指向的数组 **中的值** 计数。 
    
 **lpat**
  
> 指向应用程序时间值的数组的指针。 
    
## <a name="remarks"></a>备注

**SAppTimeArray** 结构用于定义类型为 PT_MV_APPTIME。 有关属性类型PT_MV_APPTIME，请参阅 [属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

