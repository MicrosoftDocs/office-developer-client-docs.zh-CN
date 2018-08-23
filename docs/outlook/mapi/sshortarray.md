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
ms.openlocfilehash: b684309211bbc008856311158c67864d958c96a0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573031"
---
# <a name="sshortarray"></a>SShortArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含用于描述 PT_MV_SHORT 类型的属性的无符号的整数值的数组。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SShortArray
{
  ULONG cValues;
  short int FAR *lpi;
} SShortArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpi**成员指向数组中的值的数目。 
    
 **lpi**
  
> 为无符号的整数值的数组的指针。
    
## <a name="remarks"></a>注解

有关 PT_MV_SHORT 和其他属性类型的详细信息，请参阅[属性类型](property-types.md)。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

