---
title: SWStringArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SWStringArray
api_type:
- COM
ms.assetid: c1ae24ad-1bbb-4dee-b414-b5226593b6fa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1578e26ec96f69975c2304cb185f352193a52c2d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778930"
---
# <a name="swstringarray"></a>SWStringArray

  
  
**适用于**： Outlook 
  
包含用于描述 PT_MV_UNICODE 类型的属性的字符串的数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SWStringArray
{
  ULONG cValues;
  LPWSTR FAR *lppszW;
} SWStringArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lppszW**成员指向的字符串数组中的计数。 
    
 **lppszW**
  
> 指向一个 null 结束 Unicode 字符的字符串数组。
    
## <a name="remarks"></a>说明

有关 PT_MV_UNICODE 的详细信息，请参阅[属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

