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
ms.openlocfilehash: 59911531b6d8f9c094ef8563510aaa176e3a63b8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778879"
---
# <a name="sshortarray"></a>SShortArray

  
  
**适用于**： Outlook 
  
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
    
## <a name="remarks"></a>说明

有关 PT_MV_SHORT 和其他属性类型的详细信息，请参阅[属性类型](property-types.md)。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

