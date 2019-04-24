---
title: SLongArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SLongArray
api_type:
- COM
ms.assetid: 57435634-202d-4998-9931-4562f1a66f5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9b1c5a09a60240efa9d4fa117f0d8fe8113169d5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361164"
---
# <a name="slongarray"></a>SLongArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于描述类型为 PT_MV_LONG 的属性的 LONG 值类型的数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SLongArray
{
  ULONG cValues;
  LONG FAR *lpl;
} SLongArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpl**成员指向的数组中的值的计数。 
    
 **lpl**
  
> 指向 LONG 值数组的指针。
    
## <a name="remarks"></a>注解

有关 PT_MV_LONG 的详细信息, 请参阅[属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

