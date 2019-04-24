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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331694"
---
# <a name="sapptimearray"></a>SAppTimeArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含时间值的数组。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SAppTimeArray
{
  ULONG cValues;
  double FAR *lpat;
} SAppTimeArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpat**成员指向的数组中的值的计数。 
    
 **lpat**
  
> 指向应用程序时间值的数组的指针。 
    
## <a name="remarks"></a>注解

**SAppTimeArray**结构用于定义 PT_MV_APPTIME 类型的属性。 有关 PT_MV_APPTIME 的详细信息, 请参阅[属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

