---
title: SShortArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SShortArray
api_type:
- COM
ms.assetid: 201ceb76-41bc-4d7b-835d-5196bf3dc234
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8ea7d51b15a6e6acd44a3c0b6158378661f311bc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429612"
---
# <a name="sshortarray"></a>SShortArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个无符号整数值的数组，这些值用于描述类型为 PT_MV_SHORT。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SShortArray
{
  ULONG cValues;
  short int FAR *lpi;
} SShortArray;

```

## <a name="members"></a>Members

 **cValues**
  
> lpi 成员指向的数组 **中的值** 计数。 
    
 **lpi**
  
> 指向无符号整数值的数组的指针。
    
## <a name="remarks"></a>备注

有关属性类型PT_MV_SHORT，请参阅属性 [类型](property-types.md)。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

