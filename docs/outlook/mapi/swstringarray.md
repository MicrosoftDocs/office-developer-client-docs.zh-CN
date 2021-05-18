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
ms.openlocfilehash: ff69981e83d42e439936a3e4be47eabfd811b310
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413603"
---
# <a name="swstringarray"></a>SWStringArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个字符串数组，用于描述类型为 PT_MV_UNICODE。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SWStringArray
{
  ULONG cValues;
  LPWSTR FAR *lppszW;
} SWStringArray;

```

## <a name="members"></a>Members

 **cValues**
  
> **lppszW** 成员指向的数组中的字符串计数。 
    
 **lppszW**
  
> 指向以 null 结束的 Unicode 字符串数组的指针。
    
## <a name="remarks"></a>备注

有关属性类型PT_MV_UNICODE，请参阅 [属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

